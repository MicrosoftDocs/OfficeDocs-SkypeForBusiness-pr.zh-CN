---
title: 使用 Exchange on premises 部署 Microsoft Teams Rooms
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection: M365-voice
description: 阅读本主题, 了解如何使用 Exchange on on-premises 在混合环境中部署 Microsoft 团队聊天室的相关信息。
ms.openlocfilehash: 7e855ece643d3412047b4d01a9250b17f699ac98
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288480"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>使用 Exchange on premises 部署 Microsoft Teams Rooms

阅读本主题, 了解如何使用 Exchange on on-premises 和 Microsoft 团队或 Skype for business Online 在混合环境中部署 Microsoft 团队聊天室。
  
如果你的组织具有混合服务, 并且某些托管在本地托管和某些托管网络, 则你的配置将取决于托管每个服务的位置。 本主题介绍 Microsoft 团队聊天室的混合部署, Exchange 托管于本地托管。 由于这种类型的部署中存在如此多的不同变体, 因此不可能提供所有这些类型的详细说明。 以下过程将适用于许多配置。 如果该进程不适合你的设置, 我们建议你使用 Windows PowerShell 获得相同的最终结果, 如此处所述以及其他部署选项。

Microsoft 提供了[SkypeRoomProvisioningScript](https://go.microsoft.com/fwlink/?linkid=870105), 该脚本可帮助创建新的用户帐户, 或验证你拥有的现有资源帐户, 以帮助你将其转换为兼容的 Microsoft 团队聊天室用户帐户。 如果你愿意, 可以按照以下步骤配置 Microsoft 团队聊天室设备将使用的帐户。
  
## <a name="requirements"></a>要求

在使用 Exchange 内部部署部署 Microsoft 团队聊天室之前, 请确保满足这些要求。 有关详细信息, 请参阅[Microsoft 团队会议室要求](requirements.md)。
  
如果要使用 Exchange on on-premises 部署 Microsoft 团队聊天室, 您将使用 Active Directory 管理工具为本地域帐户添加电子邮件地址。 此帐户将同步到 Office 365。 你将需要执行以下操作：
  
- 创建一个帐户并将该帐户与 Active Directory 同步。

- 启用远程邮箱并设置属性。

- 分配 Office 365 许可证。

- 启用使用 Skype for Business 服务器的设备帐户。 要启用设备帐户，你的环境需要满足以下先决条件：

  - 您需要在 Office 365 计划中安装 Skype for Business Online (计划 2) 或更高版本。 该计划需要支持会议功能。
  
  - - 如果您需要使用适用于 Microsoft 团队聊天室的电话服务提供商的企业语音 (PSTN 电话), 您需要 Skype for Business Online (计划 3)。
  
  - - 租户用户必须具有 Exchange 邮箱。
  
  - - 您的 Microsoft 团队会议室帐户需要 Skype for business Online (计划 2) 或 Skype for business Online (计划 3) 许可证, 但不需要 Exchange Online 许可证。

- 将 Skype for Business Server 许可证分配给你的 Microsoft 团队聊天室帐户。

### <a name="create-an-account-and-synchronize-with-active-directory"></a>创建一个帐户并与 Active Directory 同步

1. 在 " **Active Directory 用户和计算机**" 工具中, 右键单击将在其中创建 Microsoft 团队聊天室帐户的文件夹或组织单位, 单击 "**新建**", 然后单击 "**用户**"。

2. 将上一个 cmdlet 中的显示名称键入“**全名**”框中，将别名键入“**用户登录名**”框中。单击“**下一步**”。

3. 键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。

    > [!NOTE]
    > 选择 "**密码永不过期**" 是 Microsoft 团队聊天室上的 Skype For business 服务器的要求。 你的域规则可能禁止使用不过期的密码。 如果是这样, 你将需要为每个 Microsoft 团队聊天室设备帐户创建一个例外。
  
4. 创建该帐户后，运行目录同步。 完成后, 转到 Microsoft 365 管理中心中的 "用户" 页面, 并验证在先前步骤中创建的帐户是否已合并到 "联机"。

### <a name="enable-the-remote-mailbox-and-set-properties"></a>启用远程邮箱并设置属性

1. [打开 Exchange 命令行管理](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell)程序或[使用远程 PowerShell 连接到 exchange 服务器](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。

2. 在 Exchange PowerShell 中, 通过运行以下命令为帐户 (邮箱启用帐户) 包装箱提供邮箱:

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   有关详细语法和参数信息, 请参阅[启用-邮箱](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox)。

3. 在 Exchange PowerShell 中, 在聊天室邮箱上配置以下设置以改进会议体验:

   - AutomateProcessing: AutoAccept (会议组织者直接收到会议室保留决定, 无需人工干预: 闲 = 接受; 忙 = 拒绝。)

   - AddOrganizerToSubject: $false (会议组织者未添加到会议请求的主题。)

   - DeleteComments: $false (保留收到的会议请求的邮件正文中的任何文本。)

   - DeleteSubject: $false (请保留收到的会议请求的主题。)

   - RemovePrivateProperty: $false (确保由会议组织者在原始会议请求中发送的私人标志保持指定。)

   - AddAdditionalResponse: $true (由 AdditionalResponse 参数指定的文本将添加到会议请求。)

   - AdditionalResponse: "这是 Skype 会议室!" (要添加到会议请求的其他文本。)

   此示例在名为 Project-01 的聊天室邮箱上配置这些设置 Rigel。

   ``` PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   有关详细的语法和参数信息, 请参阅[Set-CalendarProcessing](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)。

### <a name="assign-an-office-365-license"></a>分配一个 Office 365 许可证

1. 连接到 Azure Active Directory。 有关 Active Directory 的详细信息, 请参阅[Azure ActiveDirectory (import-module msonline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0)。 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0)不受支持。 

2. 设备帐户需要拥有有效的 Office 365 许可证, 否则 Exchange 和 Microsoft 团队将不起作用。 如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。 你可以使用`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 检索可用 Sku 的列表。

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. 接下来, 你可以使用`Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> cmdlet. 在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。

  ``` PowerShell
  Set-MsolUser -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -UsageLocation 'US'
  Get-MsolAccountSku
  Set-MsolUserLicense -UserPrincipalName 'PROJECTRIGEL01@contoso.com' -AddLicenses $strLicense
  ```

<!--   ``` Powershell
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -UsageLocation "US"
   Get-AzureADSubscribedSku
   Set-AzureADUserLicense -UserPrincipalName $acctUpn -AddLicenses $strLicense
   ```  -->

   有关详细说明, 请参阅[使用 Office 365 PowerShell 向用户帐户分配许可证](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。

### <a name="enable-the-device-account"></a>启用设备帐户

Skype for Business Online PowerShell 用于管理 Microsoft 团队和 Skype for business Online 的服务。

1. 从电脑创建远程 Windows PowerShell 会话, 如下所示:

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. 若要启用 Microsoft 团队聊天室帐户, 请运行以下命令:

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   如果你不确定要在你的环境中使用 RegistrarPool 参数的值, 可以使用此命令从现有用户获取值:

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>将许可证分配给你的 Microsoft 团队聊天室帐户

1. 以租户管理员身份登录, 打开 Office 365 管理门户, 然后单击 "管理" 应用。
2. 单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。
3. 单击 "Microsoft 团队聊天室帐户", 然后单击 "笔" 图标以编辑帐户信息。
4. 单击“**许可证**”。
5. 在“**分配许可证**”中，根据你的许可和企业语音要求，选择 Skype for Business（计划 2）或 Skype for Business（计划 3）。 如果要在 Microsoft 团队聊天室上使用企业语音, 则必须使用计划3许可证。
6. 单击“**保存**”。

对于验证, 你应该能够使用任何客户端登录到此帐户。
  
## <a name="see-also"></a>另请参阅

[为 Microsoft 团队聊天室配置帐户](room-systems-v2-configure-accounts.md)

[规划 Microsoft 团队聊天室](skype-room-systems-v2-0.md)
  
[部署 Microsoft 团队聊天室](room-systems-v2.md)
  
[配置 Microsoft 团队聊天室控制台](console.md)
  
[管理 Microsoft Teams 会议室](skype-room-systems-v2.md)
