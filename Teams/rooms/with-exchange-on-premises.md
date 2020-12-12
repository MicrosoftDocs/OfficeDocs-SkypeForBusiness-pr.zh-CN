---
title: 使用 Exchange 本地部署 Microsoft Teams 会议室
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom:
- Strat_SB_Admin
- seo-marvel-apr2020
ms.assetid: 24860c05-40a4-436b-a44e-f5fcb9129e98
ms.collection:
- M365-collaboration
description: 阅读本主题，了解如何使用 Exchange 在本地的混合环境中部署 Microsoft Teams 会议室。
ms.openlocfilehash: f9f80f5b993b9be95e35c8178d996973558e2512
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662317"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>使用 Exchange on premises 部署 Microsoft Teams Rooms

阅读本主题，了解如何使用 Exchange 本地和 Microsoft Teams 或 Skype for Business Online 在混合环境中部署 Microsoft Teams 会议室。
  
如果组织混合了一些服务，其中一些托管在本地，一些服务联机托管，则配置将取决于每个服务的托管位置。 本主题介绍在本地托管 Exchange 的 Microsoft Teams 会议室的混合部署。 由于这种类型的部署存在许多不同的变体，因此无法针对所有这些变体提供详细说明。 以下过程适用于许多配置。 如果该过程不适合你的设置，我们建议使用Windows PowerShell实现此处介绍的相同最终结果，并用于其他部署选项。

Microsoft [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105)一个脚本，可帮助创建新的用户帐户或验证现有资源帐户，以帮助将其转换为兼容的 Microsoft Teams 会议室用户帐户。 如果愿意，可以按照以下步骤配置 Microsoft Teams 会议室设备将使用的帐户。
  
## <a name="requirements"></a>要求

将 Microsoft Teams 会议室部署在本地 Exchange 之前，请确保已满足要求。 有关详细信息，请参阅 [Microsoft Teams 会议室要求](requirements.md)。
  
如果要在本地部署具有 Exchange 的 Microsoft Teams 会议室，你将使用 Active Directory 管理工具为本地域帐户添加电子邮件地址。 此帐户将同步到 Microsoft 365 或 Office 365。 你将需要执行以下操作：
  
- 创建一个帐户并将该帐户与 Active Directory 同步。

- 启用远程邮箱并设置属性。

- 分配 Microsoft 365 或 Office 365 许可证。

- 使用 Skype for Business Server 启用设备帐户。 要启用设备帐户，你的环境需要满足以下先决条件：

  - 你需要在 Microsoft 365 或 Office 365 计划中 (Skype for Business Online) 计划 2 或更高版本。 该计划需要支持会议功能。
  
  - 如果你需要使用企业语音 (Microsoft Teams 会议室的电话服务提供商) PSTN 电话服务，则需要 Skype for Business Online (计划 3) 。
  
  - 租户用户必须具有 Exchange 邮箱。
  
  - 你的 Microsoft Teams 会议室帐户需要 Skype for Business Online (计划 2) 或 Skype for Business Online (计划 3) 许可证，但它不需要 Exchange Online 许可证。

- 将 Skype for Business Server 许可证分配给 Microsoft Teams 会议室帐户。

### <a name="create-an-account-and-synchronize-with-active-directory"></a>创建一个帐户并与 Active Directory 同步

1. 在 **"Active Directory** 用户和计算机"工具中，右键单击要创建 Microsoft Teams 会议室帐户的文件夹或组织单位，单击"新建"，然后单击"**用户"。**

2. 将上一个 cmdlet 中的显示名称键入“**全名**”框中，将别名键入“**用户登录名**”框中。单击“**下一步**”。

3. 键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。

    > [!NOTE]
    > 选择 **"密码永不过期** "是 Microsoft Teams 会议室中的 Skype for Business Server 的一项要求。 你的域规则可能禁止使用不过期的密码。 如果是这样，则需要为每个 Microsoft Teams 会议室设备帐户创建一个例外。
  
4. 创建该帐户后，运行目录同步。 完成后，转到 Microsoft 365 管理中心的用户页面，验证在之前步骤中创建的帐户已合并到联机。

### <a name="enable-the-remote-mailbox-and-set-properties"></a>启用远程邮箱并设置属性

1. [打开 Exchange 命令行管理程序](https://docs.microsoft.com/powershell/exchange/exchange-server/open-the-exchange-management-shell)[，或者使用远程 PowerShell 连接到 Exchange 服务器](https://docs.microsoft.com/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。

2. 在 Exchange PowerShell 中，通过运行以下 (为帐户创建邮箱，) 启用该帐户：

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   有关详细的语法和参数信息，请参阅[Enable-Mailbox。](https://docs.microsoft.com/powershell/module/exchange/mailboxes/enable-mailbox)

3. 在 Exchange PowerShell 中，在会议室邮箱上配置以下设置以改进会议体验：

   - AutomateProcessing：AutoAccept (会议组织者无需人工干预即可直接接收会议室预订决策：free = accept;busy = decline.) 

   - AddOrganizerToSubject：$false (会议组织者未添加到会议请求的主题。) 

   - DeleteComments：$false (在传入会议请求的邮件正文中保留任何文本。) 

   - DeleteSubject：$false (保留传入会议请求的主题。) 

   - RemovePrivateProperty：$false (确保会议组织者在原始会议请求中发送的专用标志保持指定。) 

   - AddAdditionalResponse：$true (AdditionalResponse 参数指定的文本添加到会议请求。) 

   - AdditionalResponse： "这是 Skype 会议室！"  (要添加到会议请求的其他文本。) 

   此示例在名为 Project-Rigel-01 的会议室邮箱上配置这些设置。

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   有关详细的语法和参数信息，请参阅[Set-CalendarProcessing。](https://docs.microsoft.com/powershell/module/exchange/mailboxes/set-calendarprocessing)

### <a name="assign-a-microsoft-365-or-office-365-license"></a>分配 Microsoft 365 或 Office 365 许可证

1. 连接到 Azure Active Directory。 有关 Active Directory 的详细信息，请参阅[AZURE ActiveDirectory (MSOnline) 1.0。](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [不支持 Azure Active Directory PowerShell 2.0。](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0) 

2. 设备帐户需要具有有效的 Microsoft 365 或 Office 365 许可证，否则 Exchange 和 Microsoft Teams 将不起作用。 如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。 可以使用 `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 以检索可用 SKUS 的列表。

<!--   ``` Powershell
   Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
   ``` -->

3. 接下来，可以使用 `Set-MsolUserLicense` <!-- Set-AzureADUserLicense --> cmdlet。 在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。

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

   有关详细说明，请参阅使用 [Office 365 PowerShell 向用户帐户分配许可证](https://docs.microsoft.com/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。

### <a name="enable-the-device-account"></a>启用设备帐户

Skype for Business Online PowerShell 用于管理 Microsoft Teams 和 Skype for Business Online 的服务。

1. 从电脑Windows PowerShell远程会话会话，如下所示：
> [!NOTE]
> Skype for Business Online 连接器当前是最新 Teams PowerShell 模块的一部分。
>
> 如果你使用的是最新的 [Teams PowerShell 公共](https://www.powershellgallery.com/packages/MicrosoftTeams/)版本，则无需安装 Skype for Business Online 连接器。

   ``` Powershell
   Import-Module -Name MicrosoftTeams  
   $cssess=New-CsOnlineSession -Credential $cred  
   Import-PSSession $cssess -AllowClobber
   ```

2. 获取帐户的 SIP 地址：

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. 若要启用 Microsoft Teams 会议室帐户，请运行此命令：

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   如果不确定要用于环境中 RegistrarPool 参数的值，可以使用以下命令从现有用户获取该值：

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>为 Microsoft Teams 会议室帐户分配许可证

1. 以租户管理员登录，打开 Microsoft 365 管理中心，然后单击"管理"应用。
2. 单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。
3. 单击 Microsoft Teams 会议室帐户，然后单击笔图标以编辑帐户信息。
4. 单击“**许可证**”。
5. 在“**分配许可证**”中，根据你的许可和企业语音要求，选择 Skype for Business（计划 2）或 Skype for Business（计划 3）。 如果要在 Microsoft Teams 会议室中企业语音计划 3 许可证。
6. 单击“**保存**”。

若要进行验证，应该可以使用任何客户端登录到此帐户。
  
## <a name="related-topics"></a>相关主题

[为 Microsoft Teams 会议室配置帐户](rooms-configure-accounts.md)

[Microsoft Teams 会议室规划](rooms-plan.md)
  
[部署 Microsoft Teams 会议室](rooms-deploy.md)
  
[配置 Microsoft Teams 会议室控制台](console.md)
  
[管理 Microsoft Teams 会议室](rooms-manage.md)
