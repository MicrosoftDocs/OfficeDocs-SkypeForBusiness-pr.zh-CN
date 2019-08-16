---
title: 使用 Exchange Online 部署 Microsoft Teams Rooms
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: 阅读本主题, 了解如何通过 Exchange Online 部署 Microsoft 团队聊天室的相关信息。
ms.openlocfilehash: de91560311aa3e1af72a3af69bf2b59780c09d6f
ms.sourcegitcommit: 1401ee484a2bc8e72d96649b0571bb59198f9dab
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2019
ms.locfileid: "36427749"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>使用 Exchange Online 部署 Microsoft Teams Rooms

阅读本主题, 了解如何在本地通过 Exchange Online 和 Skype for business 服务器部署 Microsoft 团队聊天室的相关信息。
  
如果你的组织具有混合服务, 并且某些托管在本地托管和某些托管网络, 则你的配置将取决于托管每个服务的位置。 本主题介绍 Microsoft 团队聊天室的混合部署和 Exchange 托管网络。 由于这种类型的部署中存在如此多的不同变体, 因此不可能提供所有这些类型的详细说明。 以下过程将适用于许多配置。 如果该进程不适合你的设置, 我们建议你使用 Windows PowerShell 获得相同的最终结果, 如此处所述以及其他部署选项。

设置用户帐户最简单的方法是使用远程 Windows PowerShell 进行配置。 Microsoft 提供了[SkypeRoomProvisioningScript](https://go.microsoft.com/fwlink/?linkid=870105), 该脚本可帮助创建新的用户帐户, 或验证你拥有的现有资源帐户, 以帮助你将其转换为兼容的 Microsoft 团队聊天室用户帐户。 如果你愿意, 可以按照以下步骤配置 Microsoft 团队聊天室设备将使用的帐户。

## <a name="requirements"></a>要求

在使用 Exchange Online 部署 Microsoft 团队聊天室之前, 请确保满足这些要求。 有关详细信息, 请参阅[Microsoft 团队会议室要求](requirements.md)。
  
若要通过 Exchange Online 部署 Microsoft 团队聊天室, 请按照下面的步骤操作。 确保你有合适的权限来运行相关 cmdlet。 

   > [!NOTE]
   >  此部分中的[适用于 Windows PowerShell cmdlet 的 Azure Active Directory 模块](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)(例如, Set-MsolUser) 已在为 Microsoft 团队聊天室设备设置帐户中进行了测试。 其他 cmdlet 可能有效, 但尚未在此特定方案中对其进行测试。
  
### <a name="create-an-account-and-set-exchange-properties"></a>创建帐户并设置 Exchange 属性

1. 在电脑上启动远程 Windows PowerShell 会话并连接到 Exchange Online, 如下所示:

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
```

2. 建立会话后, 你将创建一个新邮箱并将其作为 RoomMailboxAccount 启用, 或更改现有会议室邮箱的设置。 这将允许帐户在 Microsoft 团队聊天室中进行身份验证。

   如果要更改现有的资源邮箱：

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    如果要创建新的资源邮箱, 请执行以下操作:

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 若要改善会议体验, 你需要在用户帐户上设置 Exchange 属性, 如下所示:

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>为你的本地域帐户添加电子邮件地址

1. 在 " **Active Directory 用户和计算机广告**" 工具中, 右键单击将在其中创建 Microsoft 团队聊天室帐户的容器或组织单元, 单击 "**新建**", 然后单击 "**用户**"。
2. 在 "**完整名称**" 框中键入 "显示名称" (-Identity) 和 "**用户登录名**" 框中的别名 ("设置邮箱" 或 "新邮箱")。 单击“**下一步**”。
3. 键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。

    > [!NOTE]
    > 选择 "**密码永不过期**" 是 Microsoft 团队聊天室上的 Skype For business 服务器的要求。 你的域规则可能禁止使用不过期的密码。 如果是这样, 你将需要为每个 Microsoft 团队聊天室用户帐户创建一个例外。
  
4. 单击“**完成**”创建帐户。
5. 创建帐户后, 运行目录同步。 这可以通过在 PowerShell 中使用[MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0)来实现。 完成后, 转到 "用户" 页面并验证之前步骤中创建的两个帐户是否已合并。

### <a name="assign-an-office-365-license"></a>分配一个 Office 365 许可证

1. 首先, 连接到 Azure AD 以应用某些帐户设置。 你可以通过运行此 cmdlet 来进行连接。 有关 Active Directory 的详细信息, 请参阅[Azure ActiveDirectory (import-module msonline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0)。 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0)不受支持。 

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. 用户帐户需要拥有有效的 Office 365 许可证, 才能确保 Exchange 和 Skype for business 服务器能够正常工作。 如果你有许可证，则需要为用户帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。 您将按以下步骤进行分配。
3. 接下来, 使用`Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> 检索 Office 365 租户的可用 Sku 列表。
4. 列出 Sku 后, 您可以使用`Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> cmdlet. 在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。 

  ```
    Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-MsolAccountSku
   Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```
<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
   ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>使用 Skype for Business 服务器启用用户帐户

1. 从电脑创建远程 Windows PowerShell 会话, 如下所示:

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. 若要为 Skype for business Server 启用 Microsoft 团队聊天室帐户, 请运行以下命令:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    如果你不确定要在你的环境中使用 RegistrarPool 参数的值, 可以使用此命令从现有 Skype for Business 服务器用户获取该值

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>将 Skype for Business Server 许可证分配给你的 Microsoft 团队聊天室帐户

1. 以租户管理员身份登录, 打开 Office 365 管理门户, 然后单击 "管理" 应用。
2. 单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。
3. 单击 "Microsoft 团队聊天室帐户", 然后单击 "笔" 图标以编辑帐户信息。
4. 单击“**许可证**”。
5. 在“**分配许可证**”中，根据你的许可和企业语音要求，选择 Skype for Business（计划 2）或 Skype for Business（计划 3）。 如果要在 Microsoft 团队聊天室使用企业语音, 则必须使用计划3许可证。
6. 单击“**保存**”。

对于验证, 你应该能够使用任何 Skype for Business 客户端登录到此帐户。
  
## <a name="see-also"></a>另请参阅

[为 Microsoft 团队聊天室配置帐户](room-systems-v2-configure-accounts.md)

[规划 Microsoft 团队聊天室](skype-room-systems-v2-0.md)
  
[部署 Microsoft 团队聊天室](room-systems-v2.md)
  
[配置 Microsoft 团队聊天室控制台](console.md)
  
[管理 Microsoft Teams 会议室](skype-room-systems-v2.md)
