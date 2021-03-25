---
title: 使用 Microsoft 365 或 Office 365 部署 Microsoft Teams 会议室
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
description: 阅读本主题，了解如何使用 Microsoft 365 或 Office 365 部署 Microsoft Teams 会议室，其中 Teams 或 Skype for Business 和 Exchange 都联机。
ms.openlocfilehash: b5cfaab64840fe72dc989f00ed41760058afc765
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117330"
---
# <a name="deploy-microsoft-teams-rooms-with-microsoft-365-or-office-365"></a>使用 Microsoft 365 或 Office 365 部署 Microsoft Teams 会议室

阅读本主题，了解如何使用 Microsoft 365 或 Office 365 部署 Microsoft Teams 会议室，其中 Microsoft Teams 或 Skype for Business 和 Exchange 都联机。

设置用户帐户的最简单方法是使用远程Windows PowerShell。 Microsoft [ 提供了SkypeRoomProvisioningScript.ps1， ](https://go.microsoft.com/fwlink/?linkid=870105)此脚本可帮助创建新用户帐户或验证现有资源帐户，以帮助将其转换为兼容的 Microsoft Teams 会议室用户帐户。 如果愿意，可以按照以下步骤配置 Microsoft Teams 会议室设备将使用的帐户。

## <a name="requirements"></a>要求

使用 Microsoft 365 或 Office 365 部署 Microsoft Teams 会议室之前，请确保满足要求。 有关详细信息，请参阅 [Microsoft Teams 会议室要求](requirements.md)。

若要启用 Skype for Business，必须具有以下项：

- Skype for Business Online (计划 2 或基于企业的计划) Microsoft 365 或 Office 365 计划中的更高版本。 该计划需要允许电话拨入式会议功能。

- 如果需要会议中的拨入功能，则需要音频会议和电话系统许可证。  如果需要会议拨出功能，则需要音频会议许可证。

- 租户用户必须具有 Exchange 邮箱。

- 你的 Microsoft Teams 会议室帐户至少需要 Skype for Business Online (计划 2) 许可证，但它不需要 Exchange Online 许可证。 有关详细信息 [，请参阅 Microsoft Teams 会议室](rooms-licensing.md) 许可证。

有关 Skype for Business Online 计划的详细信息，请参阅 [Skype for Business Online 服务说明](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)。

### <a name="add-a-device-account"></a>添加设备帐户

1. 连接到 Exchange Online PowerShell。 有关说明，请参阅[连接到 Exchange Online PowerShell。](/powershell/exchange/connect-to-exchange-online-powershell)

2. 在 Exchange Online PowerShell 中，创建新的会议室邮箱或修改现有的会议室邮箱。 默认情况下，会议室邮箱没有关联的帐户，因此创建或修改允许其通过 Skype 会议室系统 v2 进行身份验证的会议室邮箱时，需要添加帐户。

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

   - AdditionalResponse："这是 Skype 会议室！"  (要添加到会议请求的其他文本。) 

   此示例在名为"Rigel-01"的会议室邮箱上配置这些设置。

   ``` PowerShell
   Set-CalendarProcessing -Identity "Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   有关详细的语法和参数信息，请参阅[Set-CalendarProcessing。](/powershell/module/exchange/mailboxes/set-calendarprocessing)

4. 通过运行 PowerShell cmdlet 连接到 MS Online PowerShell 以设置 `Connect-MsolService -Credential $cred` Active Directory。 有关 Active Directory 的详细信息，请参阅[Azure ActiveDirectory (MSOnline) 1.0。](/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [不支持 Azure Active Directory PowerShell 2.0。](/powershell/azure/active-directory/overview?view=azureadps-2.0)

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

6. 设备帐户需要具有有效的 Microsoft 365 或 Office 365 许可证，否则 Exchange 和 Microsoft Teams 或 Skype for Business 将不起作用。 如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。 可以使用 `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 检索 Microsoft 365 或 Office 365 组织的可用 SKUS 列表，如下所示：

   ```Powershell
   Get-MsolAccountSku
   ```

   <!--
   ```Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   接下来，可以使用 `Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet。 此示例将会议室许可证添加到帐户：

   ```PowerShell
   Set-MsolUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses "Contoso:MEETING_ROOM"
   ```

   <!-- 
   ```Powershell
   Set-AzureADUser -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -UsageLocation "US"
   Set-AzureADUserLicense -UserPrincipalName "Rigel1@contoso.onmicrosoft.com" -AddLicenses "Contoso:MEETING_ROOM"
   ```   -->

   有关详细说明，请参阅 [使用 Office 365 PowerShell 向用户帐户分配许可证](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。

   您也可以将电话系统功能添加到此帐户，但您必须首先对其进行配置。 有关详细信息 [，请参阅什么是手机](../what-is-phone-system-in-office-365.md) 系统？。 此示例添加 PSTN 国内和国际呼叫计划：

   ```PowerShell
   Set-MsolUserLicense -UserPrincipalName rigel1@contoso.onmicrosoft.com -AddLicenses "Contoso:MCOPSTN2"
   ```

7. 接下来，你需要使用 Skype for Business 启用设备帐户。 确保你的环境满足 [Microsoft Teams 会议室要求中定义的要求](requirements.md)。

   启动远程 [Windows PowerShell会话](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell) ，如下所示 (确保安装 [Skype for Business Online PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector) 组件) ：

> [!NOTE]
> Skype for Business Online 连接器当前是最新 Teams PowerShell 模块的一部分。
>
> 如果你使用的是最新的 [Teams PowerShell 公共版本](https://www.powershellgallery.com/packages/MicrosoftTeams/)，则不需要安装 Skype for Business Online 连接器。

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

   接下来，通过运行以下 cmdlet 为 Skype for Business Server 启用 Microsoft Teams 会议室帐户：

   ``` Powershell
   Enable-CsMeetingRoom -Identity "Rigel1@contoso.onmicrosoft.com" -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   > [!NOTE]
   > 可能无法在租户中的现有用户帐户相同的注册机构池上新建用户帐户。 上述命令将防止由于这种情况导致的帐户设置错误。

## <a name="validate"></a>验证

为了进行验证，你应当能够使用任何 Skype for Business 客户端登录到你创建的帐户。

## <a name="see-also"></a>另请参阅

[配置 Microsoft Teams 会议室的帐户](rooms-configure-accounts.md)

[Microsoft Teams 会议室规划](rooms-plan.md)

[部署 Microsoft Teams 会议室](rooms-deploy.md)

[配置 Microsoft Teams 会议室控制台](console.md)

[管理 Microsoft Teams 会议室](rooms-manage.md)

[Microsoft Teams 会议室许可](rooms-licensing.md)