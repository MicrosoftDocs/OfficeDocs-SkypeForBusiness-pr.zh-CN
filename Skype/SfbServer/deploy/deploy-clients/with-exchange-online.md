---
title: 将 Skype 会议室系统 v2 与 Exchange Online 一起部署（混合）
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: 阅读有关如何部署使用 Exchange Online 的 Skype 的空间系统 v2 本主题。
ms.openlocfilehash: 59724ae9b0fc77f16a072e0e08b125407c6e43e3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-exchange-online-hybrid"></a>将 Skype 会议室系统 v2 与 Exchange Online 一起部署（混合）
 
阅读有关如何部署使用 Exchange Online 的 Skype 的空间系统 v2 本主题。
  
如果组织中有一些位于内部部署和联机寄宿某些服务，同时，然后您的配置将取决于每个服务所在。 本主题介绍与 Exchange 联机寄宿 Skype 的空间系统 v2 的混合部署。 由于有这么多的不同变体，这种类型的部署中，不可能提供有关它们的详细的说明。 以下过程适用于多种不同的配置。 如果过程不适合于您的安装程序，我们建议您使用 Windows PowerShell (请参见附录： PowerShell) 来实现相同的最终结果，因为有文档记录，和其他部署选项。 然后应使用提供的 Windows PowerShell 脚本以验证您的 Skype 的空间系统 v2 安装。 （请参阅帐户验证脚本）。
  
## <a name="deploy-skype-room-systems-v2-with-exchange-online"></a>将 Skype 会议室系统 v2 与 Exchange Online 一起部署

部署 Exchange online 的 Skype 的空间系统 v2 之前，请确保已满足要求。 有关详细信息，请参阅[Skype 的空间系统 v2 要求](../../plan-your-deployment/clients-and-devices/requirements.md)。
  
若要部署 Exchange online 的 Skype 的空间系统 v2，按照下面的步骤。 确保你有合适的权限来运行相关 cmdlet。 
  
### <a name="create-an-account-and-set-exchange-properties"></a>创建帐户并设置 Exchange 属性

1. 在计算机上启动远程 Windows PowerShell 会话和连接到 Exchange Online，如下所示：
    
  ```
  Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/ps1-liveid/ -Credential $cred -Authentication Basic 
-AllowRedirection

  ```

2. 之后建立会话，您将创建一个新邮箱和它启用为 RoomMailboxAccount，或者更改现有空间邮箱的设置。 这将允许进行到 Skype 的空间系统 v2 身份验证的帐户。
    
   如果要更改现有的资源邮箱：
    
   ```
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    如果您正在创建新的资源邮箱：
    
   ```
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 为了提高会议的经验，将需要的用户帐户设置 Exchange 属性如下：
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. 键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。
    
    > [!NOTE]
    > 选择**密码永不过期**是 Skype 的空间系统 v2 的业务服务器 2015年的 Skype 的要求。 你的域规则可能禁止使用不过期的密码。 如果是这样，您需要针对每一个 Skype 的空间系统 v2 用户帐户创建例外。
  
5. 单击“**完成**”创建帐户。
    
6. 创建该帐户后，运行目录同步。完成后，转至用户页面并验证在上述步骤中创建的两个帐户是否已合并。
    
7. 你需要连接至 Azure AD 来应用一些帐户设置。你可以通过运行此 cmdlet 来进行连接。
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>为你的本地域帐户添加电子邮件地址

1. 在**Active Directory 用户和计算机广告**工具中，右键单击文件夹或 Skype 的空间系统 v2 将为其创建帐户，请单击**新建**，然后单击**用户**的组织单位。
    
2. 将上一个 cmdlet 中的显示名称键入“**全名**”框中，将别名键入“**用户登录名**”框中。单击“**下一步**”。
    
### <a name="assign-an-office-365-license"></a>分配一个 Office 365 许可证

1. 用户帐户需要具有有效的 Office 365 提供许可证，以确保交换和业务服务器 2015年的 Skype 将起作用。 如果你有许可证，则需要为用户帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。
    
2. 接下来，使用 Get MsolAccountSku Office 365 租户为检索可用 Sku 列表。
    
3. 列出 SKU 后，便可使用 Set-MsolUserLicense cmdlet 来添加许可证。在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```

### <a name="enable-the-user-account-with-skype-for-business-server-2015"></a>使用 Skype for Business Server 2015 启用用户帐户

1. 从一台电脑，如下所示创建远程 Windows PowerShell 会话：
    
  ```
  Import-Module LyncOnlineConnector  
$cssess=New-CsOnlineSession -Credential $cred  
Import-PSSession $cssess -AllowClobber

  ```

2. 若要启用业务服务器 2015 Skype 的 Skype 的空间系统 v2 帐户，请运行以下命令：
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    如果不确定要用于您的环境中的 RegistrarPool 参数的值，您可以从现有 Skype 业务服务器 2015年用户使用此命令中获取的值
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-2015-license-to-your-skype-room-systems-v2-account"></a>向你的 Skype 会议室系统 v2 帐户分配一个 Skype for Business Server 2015 许可证

1. 租户管理员的身份登录，打开 Office 365 管理门户网站，然后单击管理应用程序。
    
2. 单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。
    
3. Skype 的空间系统 v2 帐户，单击，然后单击笔图标可编辑帐户信息。
    
4. 单击“**许可证**”。
    
5. 在“**分配许可证**”中，根据你的许可和企业语音要求，选择 Skype for Business（计划 2）或 Skype for Business（计划 3）。 您必须使用计划 3 许可证，如果您想要使用 Skype 的空间系统 v2 企业语音。
    
6. 单击" **保存**"。
    
进行验证，您应该能够使用任何 Skype 业务客户端登录到此帐户。
  
## <a name="see-also"></a>另请参阅

#### 

[Skype 的空间规划系统 v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[部署 Skype 的空间系统 v2](room-systems-v2.md)
  
[配置控制台，Skype 的空间系统 v2](console.md)
  
[Skype 的机房管理系统 v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)

