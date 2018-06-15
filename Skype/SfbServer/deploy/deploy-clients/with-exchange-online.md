---
title: 将 Skype 会议室系统 v2 与 Exchange Online 一起部署
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Priority
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: 阅读此主题以获取如何部署与 Exchange Online 的 Skype 会议室系统 v2 的信息。
ms.openlocfilehash: dad47f56d96da0f84383b2638684c65554e5a8f9
ms.sourcegitcommit: 4e9f4e2297cea3372a97f4ea178eb75ba6f8753f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2018
ms.locfileid: "19887889"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-online"></a>将 Skype 会议室系统 v2 与 Exchange Online 一起部署 
 
阅读此主题以获取如何部署与 Exchange Online 和 Skype 业务服务器本地的 Skype 会议室系统 v2 的信息。
  
如果您的组织具有其中的部分位于内部部署和一些在线承载的服务，组合，然后您的配置将取决于承载每个服务。 本主题介绍了与 Exchange online 承载的混合部署的 Skype 会议室系统 v2。 由于存在太多不同的变体在这种部署，不能提供的所有这些详细的说明。 以下过程将用于许多配置。 如果过程不适合您的安装程序，我们建议您使用 Windows PowerShell 可以获得相同的最终结果记录在这里，以及其他部署选项的。 

设置用户帐户的最简单方式是它们使用远程 Windows PowerShell 进行配置。 Microsoft 提供的[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)，脚本将帮助创建新的用户帐户，或验证必须以帮助您将它们转换为兼容的 Skype 会议室系统 v2 用户帐户的现有资源帐户。 如果您愿意，您可以按照以下步骤来配置您的 Skype 会议室系统 v2 设备将使用的帐户。


  
## <a name="deploy-skype-room-systems-v2-with-exchange-online"></a>将 Skype 会议室系统 v2 与 Exchange Online 一起部署

部署与 Exchange Online 的 Skype 会议室系统 v2 之前，请确保已满足的要求。 有关详细信息，请参阅[Skype 会议室系统 v2 要求](../../plan-your-deployment/clients-and-devices/requirements.md)。
  
若要部署与 Exchange Online 的 Skype 会议室系统 v2，按照以下步骤。 确保你有合适的权限来运行相关 cmdlet。 
  
### <a name="create-an-account-and-set-exchange-properties"></a>创建帐户并设置 Exchange 属性

1. 在 PC 上启动远程 Windows PowerShell 会话并连接到 Exchange Online，如下所示：
    
```
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. 后建立会话，您将创建新邮箱并启用作为 RoomMailboxAccount 或更改现有的会议室邮箱的设置。 这将使到 Skype 会议室系统 v2 进行身份验证的帐户。
    
   如果要更改现有的资源邮箱：
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    如果您正在创建新的资源邮箱：
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 为了改进的会议体验，您需要设置 Exchange 属性，如下所示的用户帐户：
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

    
4. 你需要连接至 Azure AD 来应用一些帐户设置。你可以通过运行此 cmdlet 来进行连接。
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>为你的本地域帐户添加电子邮件地址

1. 在**Active Directory 用户和计算机 AD**工具中，右键单击 Skype 会议室系统 v2 帐户将创建中，单击**新建**，然后单击**用户**的组织单位的文件夹。
    
2. 将上一个 cmdlet 中的显示名称键入“**全名**”框中，将别名键入“**用户登录名**”框中。单击“**下一步**”。


3. 键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。
    
    > [!NOTE]
    > 选择**密码永不过期**是 Skype 会议室系统 v2 上的业务服务器 2015 Skype 的要求。 你的域规则可能禁止使用不过期的密码。 如果是这样，您将需要针对每个 Skype 会议室系统 v2 用户帐户创建例外。
  
4. 单击“**完成**”创建帐户。
    
5. 创建该帐户后，运行目录同步。完成后，转至用户页面并验证在上述步骤中创建的两个帐户是否已合并。
    
### <a name="assign-an-office-365-license"></a>分配一个 Office 365 许可证

1. 需要有有效的 Office 365 许可，以确保 Exchange 和 Skype 的业务服务器 2015年将工作的用户帐户。 如果你有许可证，则需要为用户帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。
    
2. 接下来，使用 Get-msolaccountsku 的 Office 365 租户中检索可用的 Sku 的列表。
    
3. 列出 SKU 后，便可使用 Set-MsolUserLicense cmdlet 来添加许可证。在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```


### <a name="enable-the-user-account-with-skype-for-business-server-2015"></a>使用 Skype for Business Server 2015 启用用户帐户

1. 从 PC 创建远程 Windows PowerShell 会话，如下所示：
    
    ```
    Import-Module LyncOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. 若要启用业务服务器 2015 Skype 的 Skype 会议室系统 v2 帐户，请运行以下命令：
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    如果不确定哪些值用于您的环境中的 RegistrarPool 参数，您可以从现有 Skype 业务服务器 2015年用户使用此命令获取值
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-2015-license-to-your-skype-room-systems-v2-account"></a>向你的 Skype 会议室系统 v2 帐户分配一个 Skype for Business Server 2015 许可证

1. 以租户管理员身份登录，打开 Office 365 管理门户，并单击管理中心应用程序。
    
2. 单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。
    
3. 单击 Skype 会议室系统 v2 帐户，，然后单击笔图标可编辑帐户信息。
    
4. 单击“**许可证**”。
    
5. 在“**分配许可证**”中，根据你的许可和企业语音要求，选择 Skype for Business（计划 2）或 Skype for Business（计划 3）。 您将需要使用规划 3 许可证，如果您想要使用 Skype 会议室系统 v2 企业语音。
    
6. 单击" **保存**"。
    
进行验证，您应该能够使用任何 Skype 业务客户端登录到此帐户。
  
## <a name="see-also"></a>另请参阅

[配置帐户 Skype 会议室系统 v2](room-systems-v2-configure-accounts.md)

[规划 Skype 会议室系统 v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[部署 Skype 会议室系统 v2](room-systems-v2.md)
  
[配置 Skype 会议室系统 v2 控制台](console.md)
  
[管理 Skype 会议室系统 v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

