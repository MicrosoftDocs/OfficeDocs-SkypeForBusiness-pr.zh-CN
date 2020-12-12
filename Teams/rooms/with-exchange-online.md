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
description: 阅读本主题，了解如何使用 Exchange Online 和 Skype for Business Server 本地部署 Microsoft Teams 会议室。
ms.openlocfilehash: 82fa0b1b521c7dd2feadcca2030869b746a444aa
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662307"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a>使用 Exchange Online 部署 Microsoft Teams Rooms

阅读本主题，了解如何使用 Exchange Online 和 Skype for Business Server 本地部署 Microsoft Teams 会议室。
  
如果组织混合了一些服务，其中一些托管在本地，一些服务联机托管，则配置将取决于每个服务的托管位置。 本主题介绍联机托管 Exchange 的 Microsoft Teams 会议室的混合部署。 由于此类型的部署存在许多不同的变体，因此无法针对所有这些变体提供详细说明。 以下过程适用于许多配置。 如果该过程不适合你的设置，我们建议使用Windows PowerShell实现此处介绍的相同最终结果，并用于其他部署选项。

设置用户帐户的最简单方法是使用远程客户端配置Windows PowerShell。 Microsoft [ 提供SkypeRoomProvisioningScript.ps1， ](https://go.microsoft.com/fwlink/?linkid=870105)此脚本可帮助创建新用户帐户或验证现有资源帐户，以帮助将其转换为兼容的 Microsoft Teams 会议室用户帐户。 如果愿意，可以按照以下步骤配置 Microsoft Teams 会议室设备将使用的帐户。

## <a name="requirements"></a>要求

使用 Exchange Online 部署 Microsoft Teams 会议室之前，请确保满足要求。 有关详细信息，请参阅 [Microsoft Teams 会议室要求](requirements.md)。
  
若要使用 Exchange Online 部署 Microsoft Teams 会议室，请执行以下步骤。 确保你有合适的权限来运行相关 cmdlet。 

   > [!NOTE]
   >  本部分中用于 [Windows PowerShell cmdlet](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) 的 Azure Active Directory 模块 (例如，Set-MsolUser) 在设置 Microsoft Teams 会议室设备帐户时已经过测试。 其他 cmdlet 可能正常工作，但是，它们尚未在此特定方案中进行测试。

如果部署了 Active Directory 联合身份验证服务 (AD FS) ，则执行这些步骤之前，可能需要将用户帐户转换为托管用户，然后在完成这些步骤后将用户转换回联合用户。
  
### <a name="create-an-account-and-set-exchange-properties"></a>创建帐户并设置 Exchange 属性

1. 在电脑上Windows PowerShell远程连接会话并连接到 Exchange Online，如下所示：

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. 建立会话后，您将创建新邮箱并启用为 RoomMailboxAccount，或更改现有会议室邮箱的设置。 这将允许帐户在 Microsoft Teams 会议室中进行身份验证。

   如果要更改现有的资源邮箱：

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    如果要创建新的资源邮箱：

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. 若要改善会议体验，您需要在用户帐户上设置 Exchange 属性，如下所示：

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a>为你的本地域帐户添加电子邮件地址

1. 在 **Active Directory** 用户和计算机 AD 工具中，右键单击要创建 Microsoft Teams 会议室帐户的容器或组织单位，单击"新建"，然后单击"**用户"。**
2. 将显示名称 ( - ) cmdlet (Set-Mailbox 或 New-Mailbox) 键入到"全名"框中，将别名键入到"用户登录名称"框中。  单击“**下一步**”。
3. 键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。

    > [!NOTE]
    > 选择 **"密码永不过期** "是 Microsoft Teams 会议室中的 Skype for Business Server 的一项要求。 你的域规则可能禁止使用不过期的密码。 如果是这样，则需要为每个 Microsoft Teams 会议室用户帐户创建一个例外。
  
4. 单击“**完成**”创建帐户。
5. 创建帐户后，运行目录同步。 这可以通过在 PowerShell 中使用 [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) 实现。 完成后，转到"用户"页，验证在之前步骤中创建的两个帐户已合并。

### <a name="assign-a-microsoft-365-or-office-365-license"></a>分配 Microsoft 365 或 Office 365 许可证

1. 首先，连接到 Azure AD 以应用某些帐户设置。 你可以通过运行此 cmdlet 来进行连接。 有关 Active Directory 的详细信息，请参阅[AZURE ActiveDirectory (MSOnline) 1.0。](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)

   > [!NOTE]
   > [不支持 Azure Active Directory PowerShell 2.0。](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-2.0)

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. 用户帐户需要具有有效的 Microsoft 365 或 Office 365 许可证，以确保 Exchange 和 Skype for Business Server 正常工作。 如果你有许可证，则需要为用户帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。 您将在以下步骤中完成该作业。
3. 接下来，使用 `Get-MsolAccountSku` <!--Get-AzureADSubscribedSku--> 以检索 Microsoft 365 或 Office 365 组织的可用 SKUS 列表。
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

### <a name="enable-the-user-account-with-skype-for-business-server"></a>使用 Skype for Business Server 启用用户帐户

1. 从电脑Windows PowerShell远程会话会话，如下所示：

> [!NOTE]
> Skype for Business Online 连接器当前是最新 Teams PowerShell 模块的一部分。
>
> 如果你使用的是最新的 [Teams PowerShell 公共](https://www.powershellgallery.com/packages/MicrosoftTeams/)版本，则无需安装 Skype for Business Online 连接器。

    ``` Powershell
    Import-Module -Name MicrosoftTeams
    $cred = Get-Credential
    $cssess = New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. 若要为 Skype for Business Server 启用 Microsoft Teams 会议室帐户，请运行此命令：

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    如果不确定要用于环境中 RegistrarPool 参数的值，可以使用此命令从现有 Skype for Business Server 用户获取该值

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a>将 Skype for Business Server 许可证分配给 Microsoft Teams 会议室帐户

1. 以租户管理员登录，打开 Microsoft 365 管理中心，然后单击"管理"应用。
2. 单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。
3. 单击 Microsoft Teams 会议室帐户，然后单击笔图标以编辑帐户信息。
4. 单击“**许可证**”。
5. 在“**分配许可证**”中，根据你的许可和企业语音要求，选择 Skype for Business（计划 2）或 Skype for Business（计划 3）。 如果要在 Microsoft Teams 会议室上使用计划 3 许可证，企业语音计划 3 许可证。
6. 单击“**保存**”。

为了进行验证，你应当能够使用任何 Skype for Business 客户端登录到此帐户。

> [!NOTE]
> 如果你当前将 E1、E3、E4 或 E5 SK 与带音频会议或电话系统和通话计划的 Skype for Business 计划 2 一起使用，这些 SKUS 将继续工作。 但是，你应考虑在当前许可证过期后，根据 [Teams 会议室](rooms-licensing.md)许可更新中所述，迁移到更简单的许可模型。

> [!IMPORTANT]
> 如果你使用的是 Skype for Business 计划 2，则只能在"仅 Skype for Business"模式下使用 Microsoft Teams 会议室，这意味着你的所有会议都将是 Skype for Business 会议。 若要为 Microsoft Teams 会议启用会议室，建议购买会议室许可证。
  
## <a name="related-topics"></a>相关主题

[为 Microsoft Teams 会议室配置帐户](rooms-configure-accounts.md)

[Microsoft Teams 会议室规划](rooms-plan.md)
  
[部署 Microsoft Teams 会议室](rooms-deploy.md)
  
[配置 Microsoft Teams 会议室控制台](console.md)
  
[管理 Microsoft Teams 会议室](rooms-manage.md)
