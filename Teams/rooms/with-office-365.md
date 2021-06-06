---
title: 使用 Microsoft Teams 会议室 或 Microsoft 365 部署Office 365
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 阅读本主题，了解如何使用 Microsoft Teams 会议室 或 Microsoft 365 Office 365 部署 Teams，Skype for Business 和 Exchange 联机。
ms.openlocfilehash: 64567cd9925a0a11d9e9b896c522a2c4bfe13f40
ms.sourcegitcommit: 3840d72f9ad1c0c7803dc3662a0318f558fe92ab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739642"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>使用 Microsoft Teams 会议室 或 Microsoft 365 部署Office 365

阅读本主题，了解如何使用 Microsoft Teams 会议室 或 Microsoft 365 Office 365 部署 Microsoft Teams 或 Skype for Business Exchange。

设置用户帐户的最简单方法是使用远程Windows PowerShell。 Microsoft[提供SkypeRoomProvisioningScript.ps1，](https://go.microsoft.com/fwlink/?linkid=870105)这是一个脚本，可帮助创建新的用户帐户或验证现有资源帐户，以帮助你将其转换为兼容的Microsoft Teams 会议室用户帐户。 如果愿意，可以按照以下步骤配置设备Microsoft Teams 会议室帐户。

## <a name="requirements"></a>要求

使用 Microsoft Teams 会议室 或 Microsoft 365 部署Office 365，请确保已满足要求。 有关详细信息，请参阅Microsoft Teams 会议室[要求](requirements.md)。

若要Skype for Business，必须具有以下项：

- Skype for Business在线 (计划 2，或Enterprise计划) 或更高版本的Microsoft 365计划Office 365计划。 该计划需要允许电话拨入式会议功能。

- 如果需要会议中的拨入功能，则需要音频会议电话系统许可证。  如果需要会议拨出功能，则需要音频会议许可证。

- 租户用户必须具有Exchange邮箱。

- 你的Microsoft Teams 会议室帐户至少需要 Skype for Business Online (计划 2) 许可证，但它不需要Exchange Online许可证。 有关详细信息[，Microsoft Teams 会议室许可证](rooms-licensing.md)。

有关联机Skype for Business的详细信息，请参阅 Skype for Business [Online 服务说明](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)。

### <a name="add-a-device-account"></a>添加设备帐户

1. 连接 PowerShell Exchange Online。 有关说明，请参阅 连接[Exchange Online PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)

2. 在 Exchange Online PowerShell 中，创建新的会议室邮箱或修改现有的会议室邮箱。 默认情况下，会议室邮箱没有关联的帐户，因此创建或修改会议室邮箱时，需要添加一个帐户，以便使用 Skype 会议室系统 v2 进行身份验证。

   - 若要创建新的会议室邮箱，请使用以下语法：

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     此示例使用以下设置创建新的会议室邮箱：

     - 名称：Rigel-01

     - 别名：Rigel1

     - 帐户：Rigel1@contoso.onmicrosoft.com

     - 帐户密码：P@$$W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Rigel-01" -Alias Rigel1 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID Rigel1@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - 若要修改现有会议室邮箱，请使用以下语法：

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     此示例为别名为"Rigel2"的现有会议室邮箱启用帐户，将密码9898P@$$W 0rd。 请注意，帐户 Rigel2@contoso.onmicrosoft.com 现有别名值。

     ``` PowerShell
     Set-Mailbox -Identity Rigel2 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   有关详细的语法和参数信息，请参阅[New-Mailbox](/powershell/module/exchange/mailboxes/new-mailbox)和[Set-Mailbox。](/powershell/module/exchange/mailboxes/set-mailbox)

3. 在 Exchange Online PowerShell 中，在会议室邮箱上配置以下设置以改进会议体验：

   - AutomateProcessing：自动 (会议组织者直接接收会议室预订决策，无需人工干预：free = accept;busy = decline.) 

   - AddOrganizerToSubject：$false (会议组织者未添加到会议请求的主题。) 

   - DeleteComments：$false (在传入会议请求的邮件正文中保留任何文本。) 

   - DeleteSubject：$false (保留传入会议请求的主题。) 

   - RemovePrivateProperty：$false (确保会议组织者在原始会议请求中发送的专用标志保持指定。) 

   - AddAdditionalResponse：$true (AdditionalResponse 参数指定的文本添加到会议请求.) 

   - AdditionalResponse："这是一个Skype 会议房间！"  (要添加到会议请求的其他文本。) 

   此示例在名为"Rigel-01"的会议室邮箱上配置这些设置。

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   有关详细的语法和参数信息，请参阅[Set-CalendarProcessing。](/powershell/module/exchange/mailboxes/set-calendarprocessing)

4. 连接运行 PowerShell cmdlet，通过 MS Online PowerShell 创建 `Connect-MsolService -Credential $cred` Active Directory 设置。 有关 Active Directory 的详细信息，请参阅[Azure ActiveDirectory (MSOnline) 1.0。](/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0。](/powershell/azure/active-directory/overview?view=azureadps-2.0)

5. 如果不希望密码过期，请使用以下语法：

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PasswordNeverExpires $true
   ```

   <!--
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   此示例将帐户的密码 Rigel1@contoso.onmicrosoft.com 永不过期。

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -PasswordNeverExpires $true
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUserPassword -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -EnforceChangePasswordPolicy $false
   ``` -->

   还可以运行以下命令，为帐户设置电话号码：

   ```PowerShell
   Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
   ```

   <!-- 
   ```PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

    > [!NOTE]
    > 如果密码未设置为"永不过期"，则帐户达到到期期限后，该帐户将不再在设备上登录。 然后，需要更改帐户的密码，并在本地更新到"一切"设备。

6. 设备帐户需要具有有效的Microsoft 365或Office 365许可证，Exchange Microsoft Teams或Skype for Business无效。 如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。 可以使用 `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 检索组织或组织的可用 SKUS Microsoft 365 Office 365，如下所示：

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   接下来，可以使用 `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet。 此示例将会议室添加到帐户：

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   有关详细说明，请参阅[使用 PowerShell 向用户帐户Office 365许可证](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。

   还可以将电话系统添加到此帐户，但首先必须对其进行配置。 有关详细信息[，请参阅电话系统？。](../what-is-phone-system-in-office-365.md) 此示例添加 PSTN 国内和国际呼叫计划：

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

    > [!NOTE]
    > 如果要将Teams 会议室配置为仅以本机Microsoft Teams加入会议，则不应继续执行以下步骤。 只有在还要在本地启用对 Skype for Business 的支持时，才需要以下项。

7. 若要在本地启用设备帐户Skype for Business帐户，请确保环境满足 Microsoft Teams 会议室[要求](requirements.md)。

   启动远程[Windows PowerShell会话](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)，如下所示 (确保安装Skype for Business [Online PowerShell 组件](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)) ：

   > [!NOTE]
   > Skype for Business联机连接器当前是 PowerShell 模块Teams的一部分。
   >
   > 如果使用的是[PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)Teams最新版本，则无需安装 Skype for Business Online 连接器。

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

   从正在设置的新用户帐户获取 RegistrarPool 信息，如以下示例所示：

   ``` Powershell
    Get-CsOnlineUser -Identity "Rigel1@contoso.onmicrosoft.com" | Select -Expand RegistrarPool
   ```

   接下来，通过Microsoft Teams 会议室 cmdlet Skype for Business Server帐户：

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > 可能无法在租户中的现有用户帐户相同的注册机构池上新建用户帐户。 上述命令将防止由于这种情况导致的帐户设置错误。

## <a name="validate"></a>验证

若要进行验证，应该可以使用任何Skype for Business客户端登录到创建的帐户。

## <a name="see-also"></a>另请参阅

[配置帐户Microsoft Teams 会议室](rooms-configure-accounts.md)

[Microsoft Teams 会议室规划](rooms-plan.md)

[部署 Microsoft Teams 会议室](rooms-deploy.md)

[配置 Microsoft Teams 会议室控制台](console.md)

[管理 Microsoft Teams 会议室](rooms-manage.md)

[Microsoft Teams 会议室许可](rooms-licensing.md)
