---
title: 使用 Office 365 部署 Microsoft Teams 会议室
ms.author: v-lanac
author: lanachin
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
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 阅读本主题，了解如何在 Office 365 中部署 Microsoft 团队聊天室的相关信息。
ms.openlocfilehash: d3fcfdd0b2aabc5d69946ba60b5b8c6fbc73f713
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827440"
---
# <a name="deploy-microsoft-teams-rooms-with-office-365"></a>使用 Office 365 部署 Microsoft Teams 会议室

阅读本主题，了解如何在 Microsoft 团队或 Skype for business 和 Exchange 均在线的情况下，通过 Office 365 部署 Microsoft 团队聊天室的相关信息。

设置用户帐户最简单的方法是使用远程 Windows PowerShell 进行配置。 Microsoft 提供了[SkypeRoomProvisioningScript](https://go.microsoft.com/fwlink/?linkid=870105)，该脚本可帮助创建新的用户帐户，或验证你拥有的现有资源帐户，以帮助你将其转换为兼容的 Microsoft 团队聊天室用户帐户。 如果你愿意，可以按照以下步骤配置 Microsoft 团队聊天室设备将使用的帐户。

## <a name="requirements"></a>要求

在使用 Office 365 部署 Microsoft 团队聊天室之前，请确保满足这些要求。 有关详细信息，请参阅[Microsoft 团队会议室要求](requirements.md)。

若要启用 Skype for Business，您必须具有以下各项：

- Office 365 计划中的 Skype for business Online （计划2或基于企业的计划）或更高版本。 该计划需要允许电话拨入式会议功能。

- 如果需要来自会议的电话拨入式功能，您需要音频会议和电话系统许可证。  如果需要来自会议的拨出功能，您将需要国内或国内和国际通话计划。

- 租户用户必须具有 Exchange 邮箱。

- 您的 Microsoft 团队会议室帐户至少需要 Skype for business Online （计划2）许可证，但不需要 Exchange Online 许可证。 有关详细信息，请参阅[Microsoft 团队聊天室许可证](rooms-licensing.md)。

有关 Skype for Business Online 计划的详细信息，请参阅[skype for Business Online 服务说明](https://technet.microsoft.com/library/jj822172.aspx)。

### <a name="add-a-device-account"></a>添加设备帐户

1. 连接到 Exchange Online PowerShell。 有关说明，请参阅[连接到 Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)。

2. 在 Exchange Online PowerShell 中，创建新的会议室邮箱或修改现有的会议室邮箱。 默认情况下，会议室邮箱没有关联帐户，因此当您创建或修改允许它通过 Skype 会议室系统 v2 进行身份验证的会议室邮箱时，您将需要添加帐户。

   - 若要创建新的会议室邮箱，请使用以下语法：

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     此示例使用以下设置创建新的会议室邮箱：

     - 名称： Project-Rigel

     - 别名： ProjectRigel01

     - 帐户： ProjectRigel01@contoso.onmicrosoft.com

     - 帐户密码： P@ $ $W 0rd5959

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - 若要修改现有的会议室邮箱，请使用以下语法：

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     此示例启用具有 alias 值 ProjectRigel02 的现有聊天室邮箱的帐户，并将密码设置为 9898P@ $ $W 0rd。 请注意，由于现有的别名值，该帐户将 ProjectRigel02@contoso.onmicrosoft.com。

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   有关详细的语法和参数信息，请参阅[新邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox)和[设置邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)。


3. 在 Exchange Online PowerShell 中，在聊天室邮箱上配置以下设置以改进会议体验：

   - AutomateProcessing： AutoAccept （会议组织者直接收到会议室保留决定，无需人工干预：闲 = 接受; 忙 = 拒绝。）

   - AddOrganizerToSubject： $false （会议组织者未添加到会议请求的主题。）

   - DeleteComments： $false （保留收到的会议请求的邮件正文中的任何文本。）

   - DeleteSubject： $false （请保留收到的会议请求的主题。）

   - RemovePrivateProperty： $false （确保由会议组织者在原始会议请求中发送的私人标志保持指定。）

   - AddAdditionalResponse： $true （由 AdditionalResponse 参数指定的文本将添加到会议请求。）

   - AdditionalResponse： "这是 Skype 会议室！" （要添加到会议请求的其他文本。）

   此示例在名为 Project-01 的聊天室邮箱上配置这些设置 Rigel。

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   有关详细的语法和参数信息，请参阅[Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)。

4. 通过运行`Connect-MsolService -Credential $cred` PowerShell cmdlet 连接到 MS Online PowerShell 以进行 Active Directory 设置。   有关 Active Directory 的详细信息，请参阅[Azure ActiveDirectory （import-module msonline） 1.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)。 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)不受支持。 

5. 如果不希望密码过期，请使用以下语法：

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   此示例将帐户 ProjectRigel01@contoso.onmicrosoft.com 的密码设置为永不过期。

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   您也可以通过运行以下命令为帐户设置电话号码：

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. 设备帐户需要拥有有效的 Office 365 许可证，否则 Exchange 和 Microsoft 团队或 Skype for business 将无法正常工作。 如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。 你可以使用`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 若要检索 Office 365 租户的可用 Sku 列表，请执行以下操作：

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   接下来，你可以使用`Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet. 在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。

  ``` PowerShell
   Set-MsolUser -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
  ``` 
<!-- 
   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```   -->

   有关详细说明，请参阅[使用 Office 365 PowerShell 向用户帐户分配许可证](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。

7. 接下来，你需要启用 Skype for Business 设备帐户。 请确保你的环境满足[Microsoft 团队会议室要求](requirements.md)中定义的要求。

   启动远程[Windows PowerShell 会话](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)，如下所示（请务必[安装 Skype For business Online PowerShell 组件](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)）：

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   接下来，通过运行以下 cmdlet 为 Skype for business 服务器启用 Microsoft 团队聊天室帐户：

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   从正在设置的新用户帐户获取 RegistrarPool 信息，如下例所示：

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > 新用户帐户可能不会在与租户中的现有用户帐户相同的注册机构池中创建。 上面的命令将防止由于此情况而导致帐户设置出错。

完成上述步骤以在 Microsoft 团队或 Skype for business Online 中启用 Microsoft 团队聊天室帐户之后，你需要向 Microsoft 团队聊天室设备分配许可证。 使用 Office 365 管理门户为设备分配 Skype for business Online （计划2）或 Skype for business Online （计划3）许可证。

### <a name="assign-a-license-to-your-account"></a>向你的帐户分配许可证

1. 以租户管理员身份登录，打开 Office 365 管理门户，然后单击 "管理" 应用。

2. 单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。

3. 选择 "Microsoft 团队聊天室帐户"，然后单击或点击 "笔" 图标，这意味着 "编辑"。

4. 单击“**许可证**”选项。

5. 在 "**分配许可证**" 部分中，你需要选择 "Skype For business Online （计划2）" 或 "skype For business Online （计划3）"，具体取决于你的许可以及你根据需要企业语音确定的内容。 如果要在 Microsoft 团队聊天室使用云 PBX，则必须使用计划3许可证。 至少需要 CloudPBX 才能进行语音连接。 然后根据 PSTN 连接方法配置混合语音或 PSTN 呼叫。 有关详细信息，请参阅[Microsoft 团队聊天室许可证](rooms-licensing.md)。

6. 单击“**保存**”完成任务。

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>示例： Exchange Online 和 Skype for business Online 中的房间帐户设置

Exchange Online PowerShell 命令：

``` Powershell
New-Mailbox -MicrosoftOnlineServicesID Rigel1@contoso.com -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept-AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true
-AdditionalResponse "This is a Rigel room!"
```

Azure Active Directory PowerShell 命令：

``` PowerShell
Set-MsolUser -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-MsolUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```

<!-- 
``` PowerShell
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -PasswordNeverExpires $true -UsageLocation "US"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:O365_BUSINESS_PREMIUM"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOEV"
Set-AzureADUserLicense -UserPrincipalName rigel1@contoso.com -AddLicenses "sfblab:MCOPSTN2"
```  -->

Skype for business PowerShell 命令：

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> 这将添加 CloudPBX 和 PSTNCallingDomesticAndInternational。 此外，你需要使用管理员界面分配电话号码。

## <a name="validate"></a>复核

对于验证，你应该能够使用任何 Skype for Business 客户端登录到你创建的帐户。

## <a name="see-also"></a>另请参阅

[为 Microsoft 团队聊天室配置帐户](rooms-configure-accounts.md)

[规划 Microsoft 团队聊天室](rooms-plan.md)

[部署 Microsoft 团队聊天室](rooms-deploy.md)

[配置 Microsoft 团队聊天室控制台](console.md)

[管理 Microsoft Teams 会议室](rooms-manage.md)

[Microsoft 团队聊天室许可](rooms-licensing.md)
