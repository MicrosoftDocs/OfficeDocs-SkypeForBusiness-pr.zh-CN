---
title: 将 Skype 会议室系统 v2 与本地 Exchange 一起部署（混合）
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 1/18/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
description: 请阅读有关如何部署 Skype 的空间系统 v2 使用内部部署 Exchange 的混合环境中此主题。
ms.openlocfilehash: a0a53b7f8be916d1c0c1a69a23a0f8c604420d9a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deploy-skype-room-systems-v2-with-exchange-on-premises-hybrid"></a>将 Skype 会议室系统 v2 与本地 Exchange 一起部署（混合）
 
请阅读有关如何部署 Skype 的空间系统 v2 使用内部部署 Exchange 的混合环境中此主题。
  
如果组织中有一些位于内部部署和联机寄宿某些服务，同时，然后您的配置将取决于每个服务所在。 本主题介绍与投放在内部部署的 Exchange Skype 的空间系统 v2 的混合部署。 由于有这么多的不同变体，这种类型的部署中，不可能提供有关它们的详细的说明。 以下过程适用于多种不同的配置。 如果过程不适合于您的安装程序，我们建议使用 Windows PowerShell 来实现相同的最终结果，因为有文档记录，和其他部署选项。 然后应使用提供的 Windows PowerShell 脚本以验证您的 Skype 的空间系统 v2 安装。 （请参阅帐户验证脚本）。
  
## <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a>将 Skype 会议室系统 v2 与本地 Exchange 一起部署

Skype 的空间系统 v2 与内部部署的 Exchange 部署之前，请确保已满足要求。 有关详细信息，请参阅[Skype 的空间系统 v2 要求](../../plan-your-deployment/clients-and-devices/requirements.md)。
  
如果您正在部署 Skype 的空间系统 v2 与内部部署的 Exchange，您将使用 Active Directory 管理工具为您内部的域帐户添加电子邮件地址。 此帐户将被同步到 Office 365。 你将需要执行以下操作：
  
- 创建一个帐户并将该帐户与 Active Directory 同步。
    
- 启用远程邮箱并设置属性。
    
- 分配一个 Office 365 提供许可证。
    
- 为业务服务器启用设备与 Skype 的帐户。 要启用设备帐户，你的环境需要满足以下先决条件：
    
  - 您需要在您的 Office 365 计划有 Skype 的在线业务 (计划 2) 或更高版本。 该计划需要支持会议功能。
    
  - 如果您需要企业语音 （PSTN 电话服务） 对 Skype 的空间系统 v2 使用电话服务提供程序需要 Skype 业务联机 (计划 3)。
    
  - 租户用户必须具有 Exchange 邮箱。
    
  - Skype 的空间系统 v2 帐户需要 Skype 的在线业务 (计划 2) 或 Skype 的在线业务 (计划 3) 许可证，但它不需要 Exchange Online 的许可证。
    
- 分配到 Skype 的空间系统 v2 帐户业务服务器许可证 Skype。
    
### <a name="create-an-account-and-synchronize-with-active-directory"></a>创建一个帐户并与 Active Directory 同步

1. 在**Active Directory 用户和计算机 AD**工具中，右键单击文件夹或 Skype 的空间系统 v2 将为其创建帐户，单击**新建**，然后单击**用户**的组织单位。
    
2. 将上一个 cmdlet 中的显示名称键入“**全名**”框中，将别名键入“**用户登录名**”框中。单击“**下一步**”。
    
3. 键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。
    
    > [!NOTE]
    > 选择**密码永不过期**是 Skype 的空间系统 v2 为 Skype 业务服务器的要求。 你的域规则可能禁止使用不过期的密码。 如果是这样，您需要针对每个 Skype 的空间系统 v2 设备帐户创建例外。
  
4. 创建该帐户后，运行目录同步。 完成时，请转到 Office 365 管理中心用户页，并验证具有在线合并到前面的步骤中创建的帐户。
    
### <a name="enable-the-remote-mailbox-and-set-properties"></a>启用远程邮箱并设置属性

1. 通过使用管理员权限打开您内部 Exchange 管理外壳程序启用远程邮箱并运行下面的命令：
     
   ```
   Enable-Mailbox 'PROJECTRIGEL01@contoso.com' -RemoteRoutingAddress 'PROJECTRIGEL01@contoso.com' -Room
   ```

2. 启动远程 Windows PowerShell 会话，并连接到 Microsoft Exchange。 从您的 Office 365 租户，运行以下命令：
    
   ```
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri 'https://outlook.office365.com/ps1-liveid/' -Credential $cred -Authentication Basic -AllowRedirection 
   Import-PSSession $sess
   ```

3. 为了提高会议的经验，需要对设备帐户设置 Exchange 属性如下：
    
   ```
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false 
   -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse 'This is a Skype Meeting room!'
   ```
    您需要的属性有关的设置的详细信息，请参阅 Exchange 属性。
    
4. 你需要连接至 Azure AD 来应用一些帐户设置。 你可以通过运行此命令来连接：
    
   ```
   Connect-MsolService -Credential $cred
   ```

### <a name="assign-an-office-365-license"></a>分配一个 Office 365 许可证

1. 设备的帐户需要有有效的 Office 365 许可证以确保 Exchange 和 Skype 业务服务器将起作用。 如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。
    
2. 接下来，使用 Get MsolAccountSku Office 365 租户为检索可用 Sku 列表。
    
3. 列出 SKU 后，便可使用 Set-MsolUserLicense cmdlet 来添加许可证。在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。
    
   ```
   Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ```

### <a name="enable-the-device-account-with-skype-for-business"></a>使用 Skype for Business 启用设备帐户

1. 从一台电脑，如下所示创建远程 Windows PowerShell 会话：
    
   ```
   Import-Module LyncOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. 若要启用业务服务器的 Skype Skype 的空间系统 v2 帐户，请运行以下命令：
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   如果您不确定要用于您的环境中的 RegistrarPool 参数的值，您可以从现有业务服务器使用此命令的用户的 Skype 获得价值
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-license-to-your-skype-room-systems-v2-account"></a>向你的 Skype 会议室系统 v2 帐户分配一个 Skype for Business 许可证

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

