---
title: 将 Skype 会议室系统 v2 与本地 Exchange 一起部署
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: Strat_SB_Admin
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
description: 阅读此主题以获取如何部署与 Exchange 内部部署混合环境中的 Skype 会议室系统 v2 的信息。
ms.openlocfilehash: 9ebd7463465d8b2fbf11e95d71c8fcb557666b3a
ms.sourcegitcommit: cad74f2546a6384747b1280c3d9244aa13fd0989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/21/2019
ms.locfileid: "30737792"
---
# <a name="deploy-skype-room-systems-v2-with-exchange-on-premises"></a>将 Skype 会议室系统 v2 与本地 Exchange 一起部署

阅读本主题有关如何为业务 Online 部署在混合环境与本地 Exchange 和 Skype 的 Skype 会议室系统 v2 的信息。
  
如果您的组织具有其中的部分位于内部部署和一些在线承载的服务，组合，然后您的配置将取决于承载每个服务。 本主题介绍与部署上承载的 Exchange 混合部署的 Skype 会议室系统 v2。 由于存在太多不同的变体在这种部署，不能提供的所有这些详细的说明。 以下过程将用于许多配置。 如果过程不适合您的安装程序，我们建议您使用 Windows PowerShell 可以获得相同的最终结果记录在这里，以及其他部署选项的。

Microsoft 提供的[SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)，脚本将帮助创建新的用户帐户，或验证必须以帮助您将它们转换为兼容的 Skype 会议室系统 v2 用户帐户的现有资源帐户。 如果您愿意，您可以按照以下步骤来配置您的 Skype 会议室系统 v2 设备将使用的帐户。
  
## <a name="requirements"></a>要求

部署与 Exchange 本地 Skype 会议室系统 v2 之前，请确保已满足的要求。 有关详细信息，请参阅 [Skype Room Systems v2 requirements](../../plan-your-deployment/clients-and-devices/requirements.md)。
  
如果您正在部署与本地 Exchange 的 Skype 会议室系统 v2，您将使用 Active Directory 管理工具添加您的内部部署域帐户的电子邮件地址。 此帐户将同步到 Office 365 中。 你将需要执行以下操作：
  
- 创建一个帐户并将该帐户与 Active Directory 同步。

- 启用远程邮箱并设置属性。

- 分配 Office 365 许可证。

- 启用 Business Server Skype 的设备帐户。 要启用设备帐户，你的环境需要满足以下先决条件：

  - 您需要在您的 Office 365 计划中具有 Skype 业务 online (计划 2) 或更高。 该计划需要支持会议功能。
  
  - - 如果您需要企业语音 （PSTN 电话） 使用 Skype 会议室系统 v2 电话服务提供程序需要 Skype 业务 online (计划 3)。
  
  - - 您的租户用户必须拥有 Exchange 邮箱。
  
  - - Skype 会议室系统 v2 帐户确实需要 Skype 业务 online (计划 2) 或 Skype 业务 Online (计划 3) 许可证，但它不需要的 Exchange Online 的许可证。

- 将业务服务器许可证 Skype 分配给您的 Skype 会议室系统 v2 帐户。

### <a name="create-an-account-and-synchronize-with-active-directory"></a>创建一个帐户并与 Active Directory 同步

1. 在**Active Directory 用户和计算机 AD**工具中，右键单击该组织单位 Skype 会议室系统 v2 帐户将创建中，单击**新建**，然后单击**用户**或文件夹。

2. 将上一个 cmdlet 中的显示名称键入“**全名**”框中，将别名键入“**用户登录名**”框中。单击“**下一步**”。

3. 键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。

    > [!NOTE]
    > 选择**密码永不过期**是在 Skype 会议室系统 v2 Skype 业务服务器的要求。 你的域规则可能禁止使用不过期的密码。 如果是这样，您需要创建的每个 Skype 会议室系统 v2 设备帐户异常。
  
4. 创建该帐户后，运行目录同步。 完成后，转到您的 Office 365 管理中心中用户页，并验证已联机合并到上一步骤中创建的帐户。

### <a name="enable-the-remote-mailbox-and-set-properties"></a>启用远程邮箱并设置属性

1. [打开 Exchange 命令行管理程序](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell)或[连接到 Exchange 服务器使用远程 PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。

2. 在 Exchange PowerShell 中，通过运行以下命令创建的帐户 （邮箱启用的帐户） 的邮箱：

   ``` Powershell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   有关详细的语法和参数信息，请参阅[Enable-mailbox](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox)。

3. 在 Exchange PowerShell 中，在要改进的会议体验的会议室邮箱上配置以下设置：

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

### <a name="assign-an-office-365-license"></a>分配一个 Office 365 许可证

1. 连接到 PowerShell 的 Azure Active Directory。 有关说明，请参阅[使用图模块 Azure Active Directory PowerShell 连接](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)

2. 设备帐户需要具有有效的 Office 365 许可证，或 Exchange 和 Skype for Business 将不起作用。 如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。 您可以使用`Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 若要检索可用的 Sku 的列表。

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. 接下来，添加许可证使用`Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> cmdlet。 在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。

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

   有关详细说明，请参阅[分配到与 Office 365 PowerShell 中的用户帐户的许可证](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。

### <a name="enable-the-device-account-with-skype-for-business"></a>使用 Skype for Business 启用设备帐户

1. 从 PC 创建远程 Windows PowerShell 会话，如下所示：

   ``` Powershell
   Import-Module SkypeOnlineConnector  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. 为业务服务器启用 Skype Skype 会议室系统 v2 帐户，请运行以下命令：

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   如果不确定哪些值用于您的环境中的 RegistrarPool 参数，您可以从现有 Skype 企业服务器用户使用此命令获取值

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-license-to-your-skype-room-systems-v2-account"></a>向你的 Skype 会议室系统 v2 帐户分配一个 Skype for Business 许可证

1. 以租户管理员身份登录，打开 Office 365 管理门户，并单击管理中心应用程序。
2. 单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。
3. 单击 Skype 会议室系统 v2 帐户，，然后单击笔图标可编辑帐户信息。
4. 单击“**许可证**”。
5. 在“**分配许可证**”中，根据你的许可和企业语音要求，选择 Skype for Business（计划 2）或 Skype for Business（计划 3）。 您将需要使用规划 3 许可证，如果您想要使用 Skype 会议室系统 v2 企业语音。
6. 单击“**保存**”。

进行验证，您应该能够使用任何 Skype 业务客户端登录到此帐户。
  
## <a name="see-also"></a>另请参阅

[配置帐户 Skype 会议室系统 v2](room-systems-v2-configure-accounts.md)

[Plan for Skype Room Systems v2](../../plan-your-deployment/clients-and-devices/skype-room-systems-v2-0.md)
  
[部署 Skype 会议室系统 v2](room-systems-v2.md)
  
[配置 Skype 会议室系统 v2 控制台](console.md)
  
[管理 Skype 会议室系统 v2](../../manage/skype-room-systems-v2/skype-room-systems-v2.md)