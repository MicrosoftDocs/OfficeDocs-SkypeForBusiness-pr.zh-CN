---
title: 使用 Microsoft Teams 会议室 或 Microsoft 365 部署Office 365
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 阅读本主题，了解如何使用 Microsoft Teams 会议室 或 Microsoft 365 Office 365 部署 Teams Skype for Business 和 Exchange 联机。
ms.openlocfilehash: e3f72c86f88ab449b48b80d6bef06d0858c44b53
ms.sourcegitcommit: 1165a74b1d2e79e1a085b01e0e00f7c65483d729
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/08/2021
ms.locfileid: "61355641"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>使用 Microsoft Teams 会议室 或 Microsoft 365 部署Office 365

阅读本主题，了解如何使用 Microsoft Teams 会议室 或 Microsoft 365 Office 365 部署Microsoft Teams Exchange两者。

## <a name="requirements"></a>要求

使用 Microsoft Teams 会议室 或 Microsoft 365 部署Office 365，请确保已满足要求。 有关详细信息，请参阅Microsoft Teams 会议室[要求](requirements.md)。

### <a name="add-a-resource-account"></a>添加资源帐户

1. 连接 PowerShell Exchange Online。 有关说明，请参阅 连接[Exchange Online PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)

2. 在 Exchange Online PowerShell 中，创建新的会议室邮箱或修改现有会议室邮箱。 默认情况下，会议室邮箱没有关联的帐户，因此创建或修改会议室邮箱时需要添加帐户，以便使用 Microsoft Teams。

   - 若要创建新的会议室邮箱，请使用以下语法：

     ``` PowerShell
     New-Mailbox -MicrosoftOnlineServicesID <Office365 ID> -Name <String> -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```
     此示例使用以下设置创建新的会议室邮箱：

     - 帐户：ConferenceRoom01@contoso.com
  
     - 名称：ConferenceRoom01

     - 别名：ConferenceRoom01

     - 帐户密码：P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -MicrosoftOnlineServicesID ConferenceRoom01@contoso.com -Name "ConferenceRoom01" -Alias ConferenceRoom01 -Room -EnableRoomMailboxAccount $true  -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - 若要修改现有会议室邮箱，请使用以下语法：

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     此示例为别名为 ConferenceRoom02 的现有会议室邮箱启用帐户，将密码9898P@$$W 0rd。 请注意，帐户 ConferenceRoom02@contoso.com 现有别名值。

     ``` PowerShell
     Set-Mailbox -Identity ConferenceRoom02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   有关详细的语法和参数信息，请参阅[New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox)和[Set-Mailbox。](/powershell/module/exchange/mailboxes/set-mailbox)

3. 在 Exchange Online PowerShell 中，在会议室邮箱上配置以下设置以改进会议体验：

   - AutomateProcessing：会议组织者 (自动接收会议室预订决策，无需人工干预。) 

   - AddOrganizerToSubject：$false (会议组织者不会添加到会议请求的主题。) 

   - DeleteComments：$false (在传入会议请求的邮件正文中保留任何文本。) 

   - DeleteSubject：$false (保留传入会议请求的主题。) 

   - RemovePrivateProperty：$false (确保会议组织者在原始会议请求中发送的专用标志保持不变。) 

   - AddAdditionalResponse：$true (AdditionalResponse 参数指定的文本添加到会议请求.) 

   - AdditionalResponse："这是Microsoft Teams会议室！"  (要添加到会议请求的其他文本。) 

   此示例在名为 ConferenceRoom01 的会议室邮箱上配置这些设置。

   ``` PowerShell
   Set-CalendarProcessing -Identity "ConferenceRoom01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams Meeting room!"
   ```

   有关详细的语法和参数信息，请参阅[Set-CalendarProcessing。](/powershell/module/exchange/mailboxes/set-calendarprocessing)

4. 连接 MS Online PowerShell，通过 `Connect-MsolService` 运行PowerShell cmdlet。 有关 Active Directory 的详细信息，请参阅[Azure ActiveDirectory (MSOnline) 1.0。](/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0)不支持。

5. 使用以下语法将密码设置为永不过期：

   ```PowerShell
   Set-MsolUser -UserPrincipalName <UPN> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   此示例将帐户的密码 ConferenceRoom01@contoso.onmicrosoft.com 永不过期。

   ```PowerShell
   Set-MsolUser -UserPrincipalName "ConferenceRoom01@contoso.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   还可以运行以下命令，为帐户设置电话号码：

   ```PowerShell
   Set-MsolUser -UserPrincipalName <UPN> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

    > [!NOTE]
    > 如果密码未设置为"永不过期"，则帐户达到到期期限后，该帐户将不再在设备上登录。 然后，需要更改帐户的密码，并在本地更新Teams 会议室。 密码过期时，Teams 会议室无法加入会议。

6. 资源帐户需要具有有效的Microsoft 365或Office 365许可证，Exchange Microsoft Teams无效。 如果拥有许可证，则需要向资源帐户分配使用位置，这决定了可用于帐户的许可证 SKUS。 可以使用 `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 检索组织或组织的可用 SKUS Microsoft 365 Office 365，如下所示：

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   接下来，可以使用 `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet。 此示例将会议室许可证添加到帐户：

   ```PowerShell
   Set-MsolUser -UserPrincipalName "ConferenceRoom01@contoso.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName "ConferenceRoom01@contoso.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   有关详细说明，请参阅[使用 PowerShell](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)向用户帐户Office 365许可证。

   还可以将电话系统添加到此帐户，但首先必须对其进行配置。 有关详细信息[，请参阅电话系统？。](../what-is-phone-system-in-office-365.md) 此示例添加 PSTN 国内和国际呼叫计划：

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName ConferenceRoom01@contoso.com -AddLicenses "Contoso:MCOPSTN2"
   ```


## <a name="validate"></a>验证

若要进行验证，应该可以使用任何Microsoft Teams客户端登录到创建的帐户。

## <a name="see-also"></a>另请参阅

[配置帐户Microsoft Teams 会议室](rooms-configure-accounts.md)

[Microsoft Teams 会议室规划](rooms-plan.md)

[部署 Microsoft Teams 会议室](rooms-deploy.md)

[配置 Microsoft Teams 会议室控制台](console.md)

[管理 Microsoft Teams 会议室](rooms-manage.md)

[Microsoft Teams 会议室许可](rooms-licensing.md)
