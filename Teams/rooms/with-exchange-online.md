---
title: 使用 Exchange Online 部署 Microsoft Teams Rooms
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
ms.collection:
- M365-collaboration
ms.custom: seo-marvel-apr2020
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: 阅读本主题，了解如何在本地Microsoft Teams 会议室Exchange Online Skype for Business Server部署服务。
ms.openlocfilehash: a72fb8cfb484c9838253b9d87452c745c5e6695525bb0eed380ea6b21be64ee2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54280677"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>使用 Exchange Online 部署 Microsoft Teams Rooms

阅读本主题，了解如何在本地Microsoft Teams 会议室Exchange Online Skype for Business Server部署服务。
  
如果组织混合了一些服务，其中一些托管在本地，一些联机托管，则配置将取决于每个服务的托管位置。 本主题介绍使用联机托管Microsoft Teams 会议室的Exchange混合部署。 由于此类型的部署存在许多不同的变体，因此无法提供所有这些变体的详细说明。 以下过程适用于许多配置。 如果该过程不适用于你的设置，我们建议使用 Windows PowerShell 实现此处介绍的相同最终结果，并用于其他部署选项。

设置用户帐户的最简单方法是使用远程Windows PowerShell。 Microsoft[提供SkypeRoomProvisioningScript.ps1，](https://go.microsoft.com/fwlink/?linkid=870105)这是一个脚本，可帮助创建新的用户帐户或验证现有资源帐户，以帮助你将其转换为兼容的Microsoft Teams 会议室用户帐户。 如果愿意，可以按照以下步骤配置设备Microsoft Teams 会议室帐户。

## <a name="requirements"></a>要求

使用 Microsoft Teams 会议室 部署Exchange Online，请确保满足要求。 有关详细信息，请参阅Microsoft Teams 会议室[要求](requirements.md)。
  
若要使用 Microsoft Teams 会议室 部署Exchange Online，请执行以下步骤。 确保你有合适的权限来运行相关 cmdlet。 

   > [!NOTE]
   >  本部分[Windows PowerShell Azure Active Directory cmdlet](/powershell/azure/active-directory/overview)的 Azure Active Directory 模块 (例如，Set-MsolUser) 已在为 Microsoft Teams 会议室 设备设置帐户中进行测试。 其他 cmdlet 可能正常工作，但是，它们尚未在此特定方案中进行测试。

如果部署了 Active Directory 联合身份验证服务 (AD FS) ，则执行这些步骤之前，可能需要将用户帐户转换为托管用户，然后在完成这些步骤后将用户转换回联合用户。
  
### <a name="create-an-account-and-set-exchange-properties"></a>创建帐户并设置 Exchange 属性

1. 在电脑上Windows PowerShell远程连接会话并连接到Exchange Online，如下所示：

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. 建立会话后，将创建新邮箱并启用为 RoomMailboxAccount，或更改现有会议室邮箱的设置。 这将允许帐户在 Microsoft Teams 会议室。

   如果要更改现有的资源邮箱：

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    如果要创建新的资源邮箱：

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 若要改善会议体验，需要在用户帐户上设置Exchange属性，如下所示：

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>为你的本地域帐户添加电子邮件地址

1. 在 **"Active Directory** 用户和计算机 AD"工具中，右键单击要创建 Microsoft Teams 会议室 帐户的容器或组织单位，单击"新建"，然后单击"用户 **"。**
2. 将显示名称 ( - ) cmdlet (Set-Mailbox 或 New-Mailbox) 键入到"全名"框中，将别名键入"用户登录名称"框中。  单击“**下一步**”。
3. 键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。

    > [!NOTE]
    > 选择 **"密码永不过期**"是Skype for Business Server Microsoft Teams 会议室。 你的域规则可能禁止使用不过期的密码。 如果是这样，则需要为每个用户帐户创建Microsoft Teams 会议室异常。
  
4. 单击“**完成**”创建帐户。
5. 创建帐户后，运行目录同步。 这可以通过在 PowerShell 中使用 [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration) 实现。 完成后，转到"用户"页，验证在之前步骤中创建的两个帐户已合并。

### <a name="assign-a-microsoft-365-or-office-365-license"></a>分配Microsoft 365或Office 365许可证

1. 首先，连接到 Azure AD 以应用某些帐户设置。 你可以通过运行此 cmdlet 来进行连接。 有关 Active Directory 的详细信息，请参阅[Azure ActiveDirectory (MSOnline) 1.0。](/powershell/azure/active-directory/overview)

   > [!NOTE]
   > [Azure Active Directory PowerShell 2.0。](/powershell/azure/active-directory/overview)

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. 用户帐户需要具有有效的Microsoft 365或Office 365许可证，Exchange Skype for Business Server正常工作。 如果你有许可证，则需要为用户帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。 您将在以下步骤中完成分配。
3. 接下来，使用 `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> 检索组织或组织的可用 SKUS Microsoft 365 Office 365列表。
4. 列出 SKUS 后，可以使用 `Set-MsolUserLicense` <!-- Set-AzureADUserLicense--> cmdlet。 在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。 

    ```PowerShell
    Set-MsolUser -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
    Get-MsolAccountSku
    Set-MsolUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
    ```
  <!--   ``` Powershell
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -UsageLocation 'US'
     Get-AzureADSubscribedSku
     Set-AzureADUserLicense -UserPrincipalName 'PROJECT01@contoso.com' -AddLicenses $strLicense
     ``` -->

### <a name="enable-the-user-account-with-skype-for-business-server"></a>使用帐户启用Skype for Business Server

> [!NOTE]
> 如果要将会议设置为Teams 会议室仅Microsoft Teams会议，则无需执行以下步骤。 只有在需要启用对应用程序的支持时，才需要Skype for Business。

1. 从电脑Windows PowerShell远程会话，如下所示：

   > [!NOTE]
   > Skype for Business Online 连接器目前是最新 Teams PowerShell 模块的一部分。
   >
   > 如果使用的是[PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)Teams最新版本，则无需安装 Skype for Business Online 连接器。

   ``` Powershell
   # When using Teams PowerShell Module
   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

2. 若要为Microsoft Teams 会议室帐户Skype for Business Server，请运行此命令：

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    如果不确定要用于环境中 RegistrarPool 参数的值，可以使用此命令从现有Skype for Business Server获取该值

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>向Skype for Business Server帐户分配Microsoft Teams 会议室许可证

> [!NOTE]
> 如果要将会议设置为Teams 会议室仅Microsoft Teams会议，则无需执行以下步骤。 只有在需要启用对应用程序的支持时，才需要Skype for Business。

1. 以租户管理员角色登录，打开Microsoft 365 管理中心，然后单击"管理"应用。
2. 单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。
3. 单击Microsoft Teams 会议室帐户，然后单击笔图标以编辑帐户信息。
4. 单击“**许可证**”。
5. 在“**分配许可证**”中，根据你的许可和企业语音要求，选择 Skype for Business（计划 2）或 Skype for Business（计划 3）。 如果要在 Microsoft Teams 会议室 上使用计划 3 许可证，企业语音许可证。
6. 单击“**保存**”。

若要进行验证，应该能够使用客户端Skype for Business登录到此帐户。

> [!NOTE]
> 如果您当前使用带音频会议的计划 2 或 电话系统 和呼叫计划的 Skype for Business 计划 2 的 E1、E3、E4 或 E5 SKUS，这些功能将继续正常工作。 但是，应考虑在当前许可证过期后，根据 Teams 会议室更新 中所述[，](rooms-licensing.md)迁移到更简单的许可模型。

> [!IMPORTANT]
> 如果您使用的是计划 2 Skype for Business，则只能在"仅Microsoft Teams 会议室模式下Skype for Business会议，这意味着您的所有会议都将Skype for Business会议。 若要为会议室启用会议Microsoft Teams，建议购买会议室许可证。
  
## <a name="related-topics"></a>相关主题

[配置帐户Microsoft Teams 会议室](rooms-configure-accounts.md)

[Microsoft Teams 会议室规划](rooms-plan.md)
  
[部署 Microsoft Teams 会议室](rooms-deploy.md)
  
[配置 Microsoft Teams 会议室控制台](console.md)
  
[管理 Microsoft Teams 会议室](rooms-manage.md)
