---
title: 将 Skype 会议室系统 v2 与 Office 365 一起部署
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f09f4c2a-2608-473a-9a27-f94017d6e9dd
description: 阅读此主题以获取如何部署与 Office 365 的 Skype 会议室系统 v2 的信息。
ms.openlocfilehash: 5d2a756fafe616db22d968a3e946e468a6d063b4
ms.sourcegitcommit: cad74f2546a6384747b1280c3d9244aa13fd0989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2019
ms.locfileid: "30737846"
---
# <a name="deploy-skype-room-systems-v2-with-office-365"></a>将 Skype 会议室系统 v2 与 Office 365 一起部署 

阅读此主题以获取如何部署与 Office 365，其中的业务和 Exchange Skype 都联机 Skype 会议室系统 v2 的信息。

设置用户帐户的最简单方式是它们使用远程 Windows PowerShell 进行配置。 Microsoft 提供的[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)，脚本将帮助创建新的用户帐户，或验证必须以帮助您将它们转换为兼容的 Skype 会议室系统 v2 用户帐户的现有资源帐户。 如果您愿意，您可以按照以下步骤来配置您的 Skype 会议室系统 v2 设备将使用的帐户。

## <a name="requirements"></a>要求

部署与 Office 365 的 Skype 会议室系统 v2 之前，请确保已满足的要求。 有关详细信息，请参阅 [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md)。

若要启用 for Business 的 Skype，您必须：

- Skype 业务 online （计划 2 中或基于企业的规划） 或更高版本 Office 365 计划中。 计划需要允许电话拨入式会议功能。

- 如果您需要电话拨入式会议的功能，您将需要的音频会议和电话系统许可证。  如果您需要从会议拨出功能，您将需要国内或国内和国际呼叫规划。

- 您的租户用户必须拥有 Exchange 邮箱。

- Skype 会议室系统 v2 帐户确实需要至少 Skype 业务 Online (计划 2) 许可证，但它不需要的 Exchange Online 的许可证。 有关详细信息，请参阅[Skype 会议室系统 v2 许可](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)。

Skype 的业务 Online 计划的详细信息，请参阅[Skype for Business Online 服务说明](https://technet.microsoft.com/library/jj822172.aspx)。

### <a name="add-a-device-account"></a>添加设备帐户

1. 连接到 Exchange Online PowerShell 中。 有关说明，请参阅[Connect to Exchange Online PowerShell 中](https://go.microsoft.com/fwlink/p/?linkid=396554)。

2. 在 Exchange Online PowerShell 中，创建新会议室邮箱或修改现有的会议室邮箱。 默认情况下，会议室邮箱不具有关联的帐户，因此您需要创建或修改会议室邮箱，使其可以通过 Skype 会议室系统 v2 进行身份验证时添加帐户。

   - 若要创建新的会议室邮箱，请使用以下语法：

     ``` PowerShell
     New-Mailbox -Name "<Unique Name>" -Alias <Alias> -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID <Account> -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     本示例创建新的会议室邮箱，使用以下设置：

     - 名称： 项目-Rigel-01

     - 别名： ProjectRigel01

     - 帐户： ProjectRigel01@contoso.onmicrosoft.com

     - 帐户密码： P@$$W0rd5959

     ``` PowerShell
     New-Mailbox -Name "Project-Rigel-01" -Alias ProjectRigel01 -Room -EnableRoomMailboxAccount $true -MicrosoftOnlineServicesID ProjectRigel01@contoso.onmicrosoft.com -RoomMailboxPassword (ConvertTo-SecureString -String 'P@$$W0rd5959' -AsPlainText -Force)
     ```

   - 若要修改现有的会议室邮箱，请使用以下语法：

     ``` PowerShell
     Set-Mailbox -Identity <RoomMailboxIdentity> -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '<Password>' -AsPlainText -Force)
     ```

     本示例启用现有的会议室邮箱的别名值 ProjectRigel02，并将密码设置为 9898P@$$W0rd 的帐户。 请注意，帐户将由于现有别名值是 ProjectRigel02@contoso.onmicrosoft.com。

     ``` PowerShell
     Set-Mailbox -Identity ProjectRigel02 -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String '9898P@$$W0rd' -AsPlainText -Force)
     ```

   有关详细的语法和参数信息，请参阅[New-mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/new-mailbox)和[Set-mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-mailbox)。


3. 在 Exchange Online PowerShell 中，在要改进的会议体验的会议室邮箱上配置以下设置：

   - 如果不将 AutomateProcessing: AutoAccept (会议组织者接收直接不需要人工干预的会议室预订决策： 免费 = 接受; 闲 = 拒绝。)

   - AddOrganizerToSubject: $false （会议组织者未添加到会议请求中的主题。）

   - DeleteComments: $false （传入会议请求邮件正文中保留任何文本）。

   - DeleteSubject: $false （保留传入会议请求的主题。）

   - RemovePrivateProperty: $false （确保的私有标志： 由会议组织者在原始的会议中发送的请求保持指定）。

   - AddAdditionalResponse: $true （AdditionalResponse 参数指定的文本添加到会议请求中）。

   - AdditionalResponse:"This is Skype 会议室 ！" （其他文本添加到会议请求。）

   本示例在名为项目-Rigel-01 的会议室邮箱上配置这些设置。

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   有关详细的语法和参数信息，请参阅[Set-calendarprocessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)。

4. 连接到 MS 联机 PowerShell，可以通过运行使 Active directory 设置`Connect-MsolService -Credential $cred`如果您已有 For 详细信息，请参阅[Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0)。 <!-- or [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) for the new module -->  
    1. 如果您不希望密码过期，使用以下语法：

    ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
    ```
<!--
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName <Account> -EnforceChangePasswordPolicy $false
   ```  -->

   本示例设置 ProjectRigel01@contoso.onmicrosoft.com 为永不过期的帐户的密码。

  ``` PowerShell
    Set-MsolUser -UserPrincipalName $acctUpn -PasswordNeverExpires $true
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUserPassword -UserPrincipalName ProjectRigel01@contoso.onmicrosoft.com -EnforceChangePasswordPolicy $false
   ``` -->

   您还可以设置帐户的电话的号码，通过运行以下命令：

  ``` PowerShell
    Set-MsolUser -UserPrincipalName <upn> -PhoneNumber <phone number>
  ```
<!-- 
   ``` PowerShell
   Set-AzureADUser -UserPrincipalName <Account> -PhoneNumber "<PhoneNumber>"
   ```  -->

6. 设备帐户需要具有有效的 Office 365 许可证，或 Exchange 和 Skype for Business 将不起作用。 如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。 您可以使用`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 若要为 Office 365 租户检索可用的 Sku 的列表，如下所示：

  ``` Powershell
  Get-MsolAccountSku
  ```
<!--
   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ```  -->

   接下来，添加许可证使用`Set-MsolUserLicense` <!--Set-AzureADUserLicense --> cmdlet。 在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。

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

   有关详细说明，请参阅[分配到与 Office 365 PowerShell 中的用户帐户的许可证](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。

7. 接下来，您需要启用 for Business 的 Skype 的设备帐户。 确保你的环境满足 [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md)中定义的要求。

   启动远程[Windows PowerShell 会话](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)，如下所示 （确保[安装 Skype 业务 Online PowerShell 组件](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector)）：

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

   接下来，您 Skype 会议室系统 v2 帐户启用 Skype 业务服务器通过运行以下 cmdlet:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

   本示例中所示，请从正在安装程序的新用户帐户中获取 RegistrarPool 信息：

    ``` Powershell
    Get-CsOnlineUser -Identity $rm | Select -Expand RegistrarPool
    ```

    > [!NOTE]
    > 不可能在租户中的现有用户帐户相同的注册器池上创建新的用户帐户。 上面的命令将防止由于这种情况下的帐户设置中的错误。

您已完成上述步骤中 Skype 您 Skype 会议室系统 v2 帐户启用业务联机后，您需要将许可证分配给 Skype 会议室系统 v2 设备。 使用 Office 365 管理门户，为业务 Online (计划 2) 或业务 Online (计划 3) 许可证设备 Skype 分配任一 Skype。

### <a name="assign-a-license-to-your-account"></a>向你的帐户分配许可证

1. 登录以租户管理员，打开 Office 365 管理门户，并单击管理应用程序。

2. 单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。

3. 选择 Skype 会议室系统 v2 帐户，然后单击或点击笔图标，表示编辑。

4. 单击“**许可证**”选项。

5. 在**分配许可证**部分中，您需要选择 Skype 业务 Online (计划 2) 或 Skype 的业务 Online (计划 3)，具体取决于您的授权和决定方面需要企业语音。 您将需要使用规划 3 许可证，如果您想要使用 Skype 会议室系统 v2 云 PBX。 至少需要 CloudPBX 才能进行语音连接。 然后根据 PSTN 连接方法配置混合语音或 PSTN 呼叫。 有关详细信息，请参阅[Skype 会议室系统 v2 许可证](https://docs.microsoft.com/en-us/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2)。

6. 单击“**保存**”完成任务。

## <a name="sample-room-account-setup-in-exchange-online-and-skype-for-business-online"></a>示例： 会议室帐户安装在 Exchange Online 和 Skype 业务 online

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

Skype 业务 PowerShell 命令：

``` PowerShell
Enable-CsMeetingRoom -Identity rigel1@contoso.onmicrosoft.com -RegistrarPool sippooldm21a05.infra.lync.com
-SipAddressType EmailAddress
```

> [!NOTE]
> 这将添加 CloudPBX 和 PSTNCallingDomesticAndInternational。 此外，需要使用管理中心界面分配电话号码。

## <a name="validate"></a>验证

进行验证，您应该能够使用任何 Skype 业务客户端登录到您创建的帐户。

## <a name="see-also"></a>另请参阅

[配置帐户 Skype 会议室系统 v2](room-systems-v2-configure-accounts.md)

[Plan for Skype Room Systems v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)

[部署 Skype 会议室系统 v2](room-systems-v2.md)

[配置 Skype 会议室系统 v2 控制台](console.md)

[管理 Skype 会议室系统 v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

[Skype 会议室系统 v2 许可](/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/license-options-based-on-your-plan/skype-room-systems-v2.md)
