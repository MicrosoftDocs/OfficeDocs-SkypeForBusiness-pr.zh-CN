---
title: 在本地Microsoft Teams 会议室部署Exchange部署
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
description: 请阅读本主题，了解如何在本地Microsoft Teams 会议室混合环境中部署Exchange部署。
ms.openlocfilehash: 3931ba89dd4ad0dfd994fdf27a3f209275850116
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117350"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-on-premises"></a>使用 Exchange on premises 部署 Microsoft Teams Rooms

阅读本主题，了解如何在本地或 Microsoft Teams 会议室 Online Exchange混合Microsoft Teams部署Skype for Business部署。
  
如果组织混合了一些服务，其中一些托管在本地，一些联机托管，则配置将取决于每个服务的托管位置。 本主题介绍在本地托管的Microsoft Teams 会议室的Exchange混合部署。 由于此类型的部署存在许多不同的变体，因此无法提供所有这些变体的详细说明。 以下过程适用于许多配置。 如果该过程不适用于你的设置，我们建议使用 Windows PowerShell 实现此处介绍的相同最终结果，并用于其他部署选项。

Microsoft[提供SkypeRoomProvisioningScript.ps1，](https://go.microsoft.com/fwlink/?linkid=870105)这是一个脚本，可帮助创建新的用户帐户或验证现有资源帐户，以帮助你将其转换为兼容的Microsoft Teams 会议室用户帐户。 如果愿意，可以按照以下步骤配置设备Microsoft Teams 会议室帐户。
  
## <a name="requirements"></a>要求

在本地使用 Microsoft Teams 会议室部署Exchange之前，请确保满足要求。 有关详细信息，请参阅Microsoft Teams 会议室[要求](requirements.md)。
  
如果要在本地使用 Microsoft Teams 会议室部署Exchange，则你将使用 Active Directory 管理工具为本地域帐户添加电子邮件地址。 此帐户将同步到 Microsoft 365 或 Office 365。 你将需要执行以下操作：
  
- 创建一个帐户并将该帐户与 Active Directory 同步。

- 启用远程邮箱并设置属性。

- 分配Microsoft 365或Office 365许可证。

- 使用设备帐户启用Skype for Business Server。 要启用设备帐户，你的环境需要满足以下先决条件：

  - 你需要在计划或Skype for Business计划 (计划 2) 或更高版本Microsoft 365 Office 365计划。 该计划需要支持会议功能。
  
  - 如果需要使用企业语音 (服务提供商) PSTN 电话Microsoft Teams 会议室，则需要Skype for Business Online (计划 3) 。

  - 使用 Microsoft Teams 或 Skype for Business Online 配置会议室帐户时，应在将帐户启用为会议室帐户之前分配电话号码。
  
  - 租户用户必须具有Exchange邮箱。
  
  - 你的 Microsoft Teams 会议室 帐户需要 Skype for Business Online (计划 2) 或 Skype for Business Online (计划 3) 许可证，但它不需要 Exchange Online 许可证。

- 向Skype for Business Server帐户分配Microsoft Teams 会议室许可证。

### <a name="create-an-account-and-synchronize-with-active-directory"></a>创建一个帐户并与 Active Directory 同步

1. 在 **"Active Directory** 用户和计算机"工具中，右键单击要创建 Microsoft Teams 会议室 帐户的文件夹或组织单位，单击"新建"，然后单击"用户 **"。**

2. 将上一个 cmdlet 中的显示名称键入“**全名**”框中，将别名键入“**用户登录名**”框中。单击“**下一步**”。

3. 键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。

    > [!NOTE]
    > 选择 **"密码永不过期**"是Skype for Business Server Microsoft Teams 会议室。 你的域规则可能禁止使用不过期的密码。 如果是这样，则需要为每个设备帐户创建Microsoft Teams 会议室异常。
  
4. 创建该帐户后，运行目录同步。 完成后，转到管理中心中的"用户"Microsoft 365，验证在之前步骤中创建的帐户已合并到联机状态。

### <a name="enable-the-remote-mailbox-and-set-properties"></a>启用远程邮箱并设置属性

1. [打开 Exchange 命令行管理程序](/powershell/exchange/exchange-server/open-the-exchange-management-shell)，或者[使用远程 PowerShell Exchange服务器](/powershell/exchange/exchange-server/connect-to-exchange-servers-using-remote-powershell)。

2. 在 Exchange PowerShell 中，通过运行以下 (为帐户创建邮箱，) 启用该帐户：

   ```PowerShell
   Enable-Mailbox PROJECTRIGEL01@contoso.com -Room
   ```

   有关详细的语法和参数信息，请参阅[Enable-Mailbox。](/powershell/module/exchange/mailboxes/enable-mailbox)

3. 在 Exchange PowerShell 中，在会议室邮箱上配置以下设置以改进会议体验：

   - AutomateProcessing：自动 (会议组织者直接接收会议室预订决策，无需人工干预：free = accept;busy = decline.) 

   - AddOrganizerToSubject：$false (会议组织者未添加到会议请求的主题。) 

   - DeleteComments：$false (在传入会议请求的邮件正文中保留任何文本。) 

   - DeleteSubject：$false (保留传入会议请求的主题。) 

   - RemovePrivateProperty：$false (确保会议组织者在原始会议请求中发送的专用标志保持指定。) 

   - AddAdditionalResponse：$true (AdditionalResponse 参数指定的文本添加到会议请求.) 

   - AdditionalResponse："这是一个Skype 会议房间！"  (要添加到会议请求的其他文本。) 

   此示例在名为 Project-Rigel-01 的会议室邮箱上配置这些设置。

   ```PowerShell
   Set-CalendarProcessing -Identity "Project-Rigel-01" -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

   有关详细的语法和参数信息，请参阅[Set-CalendarProcessing。](/powershell/module/exchange/mailboxes/set-calendarprocessing)

### <a name="assign-a-microsoft-365-or-office-365-license"></a>分配Microsoft 365或Office 365许可证

1. 连接Azure Active Directory。 有关 Active Directory 的详细信息，请参阅[Azure ActiveDirectory (MSOnline) 1.0。](/powershell/azure/active-directory/overview?view=azureadps-1.0) 

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0。](/powershell/azure/active-directory/overview?view=azureadps-2.0) 

2. 设备帐户需要具有有效的Microsoft 365或Office 365许可证，Exchange Microsoft Teams无效。 如果你有许可证，则需为设备帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。 可以使用 `Get-MsolAccountSku` <!-- Get-AzureADSubscribedSku --> 以检索可用 SKUS 的列表。

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

   有关详细说明，请参阅[使用 PowerShell 向用户帐户Office 365许可证](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell#use-the-microsoft-azure-active-directory-module-for-windows-powershell)。

### <a name="enable-the-device-account"></a>启用设备帐户

Skype for Business联机 PowerShell 用于管理服务 Microsoft Teams Skype for Business Online。

1. 从电脑Windows PowerShell远程会话，如下所示：
> [!NOTE]
> Skype for Business联机连接器当前是 PowerShell 模块Teams的一部分。
>
> 如果使用的是[PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)Teams最新版本，则无需安装 Skype for Business Online 连接器。

   ``` Powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

2. 获取帐户的 SIP 地址：

   ``` Powershell
    $rm = Get-Csonlineuser -identity <insert SIP address> | select -expandproperty sipaddress
    ```

3. **可选。** 如果要向帐户分配电话号码，此时应执行该操作。 如果要分配直接路由电话号码：

   ``` Powershell
    Set-CsUser -Identity $rm -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:+14255550012
    ```
    如果要分配 Microsoft 提供的电话号码，请使用以下 cmdlet，在向用户预配呼叫计划许可证后：
    
    ``` Powershell
    Set-CsOnlineVoiceUser -Identity $rm -TelephoneNumber +14255550011 -LocationID xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx
    ```
    
4. 若要启用Microsoft Teams 会议室帐户，请运行此命令：

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

   如果不确定要用于环境中 RegistrarPool 参数的值，可以使用以下命令从现有用户获取该值：

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-license-to-your-microsoft-teams-rooms-account"></a>向帐户分配Microsoft Teams 会议室许可证

1. 以租户管理员登录，打开Microsoft 365管理中心，然后单击"管理"应用。
2. 单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。
3. 单击Microsoft Teams 会议室帐户，然后单击笔图标以编辑帐户信息。
4. 单击“**许可证**”。
5. 在“**分配许可证**”中，根据你的许可和企业语音要求，选择 Skype for Business（计划 2）或 Skype for Business（计划 3）。 如果要在应用程序上使用计划 3 许可证，企业语音计划Microsoft Teams 会议室。
6. 单击“**保存**”。

若要进行验证，应该可以使用任何客户端登录到此帐户。
  
## <a name="related-topics"></a>相关主题

[配置帐户Microsoft Teams 会议室](rooms-configure-accounts.md)

[Microsoft Teams 会议室规划](rooms-plan.md)
  
[部署 Microsoft Teams 会议室](rooms-deploy.md)
  
[配置 Microsoft Teams 会议室控制台](console.md)
  
[管理 Microsoft Teams 会议室](rooms-manage.md)