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
ms.openlocfilehash: 5e3446349be8aaef666c02c73370758027736181
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117340"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="4195e-103">使用 Exchange Online 部署 Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="4195e-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="4195e-104">阅读本主题，了解如何在本地Microsoft Teams 会议室Exchange Online Skype for Business Server部署服务。</span><span class="sxs-lookup"><span data-stu-id="4195e-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="4195e-105">如果组织混合了一些服务，其中一些托管在本地，一些联机托管，则配置将取决于每个服务的托管位置。</span><span class="sxs-lookup"><span data-stu-id="4195e-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="4195e-106">本主题介绍使用联机托管Microsoft Teams 会议室的Exchange混合部署。</span><span class="sxs-lookup"><span data-stu-id="4195e-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="4195e-107">由于此类型的部署存在许多不同的变体，因此无法提供所有这些变体的详细说明。</span><span class="sxs-lookup"><span data-stu-id="4195e-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="4195e-108">以下过程适用于许多配置。</span><span class="sxs-lookup"><span data-stu-id="4195e-108">The following process will work for many configurations.</span></span> <span data-ttu-id="4195e-109">如果该过程不适用于你的设置，我们建议使用 Windows PowerShell 实现此处介绍的相同最终结果，并用于其他部署选项。</span><span class="sxs-lookup"><span data-stu-id="4195e-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="4195e-110">设置用户帐户的最简单方法是使用远程Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="4195e-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="4195e-111">Microsoft[提供SkypeRoomProvisioningScript.ps1，](https://go.microsoft.com/fwlink/?linkid=870105)这是一个脚本，可帮助创建新的用户帐户或验证现有资源帐户，以帮助你将其转换为兼容的Microsoft Teams 会议室用户帐户。</span><span class="sxs-lookup"><span data-stu-id="4195e-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="4195e-112">如果愿意，可以按照以下步骤配置设备Microsoft Teams 会议室帐户。</span><span class="sxs-lookup"><span data-stu-id="4195e-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="4195e-113">要求</span><span class="sxs-lookup"><span data-stu-id="4195e-113">Requirements</span></span>

<span data-ttu-id="4195e-114">使用 Microsoft Teams 会议室 部署Exchange Online，请确保满足要求。</span><span class="sxs-lookup"><span data-stu-id="4195e-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="4195e-115">有关详细信息，请参阅Microsoft Teams 会议室[要求](requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="4195e-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="4195e-116">若要使用 Microsoft Teams 会议室 部署Exchange Online，请执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="4195e-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="4195e-117">确保你有合适的权限来运行相关 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4195e-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="4195e-118">本部分[Windows PowerShell Azure Active Directory cmdlet](/powershell/azure/active-directory/overview?view=azureadps-1.0)的 Azure Active Directory 模块 (例如，Set-MsolUser) 已在为 Microsoft Teams 会议室 设备设置帐户中进行测试。</span><span class="sxs-lookup"><span data-stu-id="4195e-118">The [Azure Active Directory Module for Windows PowerShell cmdlets](/powershell/azure/active-directory/overview?view=azureadps-1.0) in this section (for example,  Set-MsolUser) have been tested in setting up accounts for Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="4195e-119">其他 cmdlet 可能正常工作，但是，它们尚未在此特定方案中进行测试。</span><span class="sxs-lookup"><span data-stu-id="4195e-119">It's possible that other cmdlets may work, however, they haven't been tested in this specific scenario.</span></span>

<span data-ttu-id="4195e-120">如果部署了 Active Directory 联合身份验证服务 (AD FS) ，则执行这些步骤之前，可能需要将用户帐户转换为托管用户，然后在完成这些步骤后将用户转换回联合用户。</span><span class="sxs-lookup"><span data-stu-id="4195e-120">If you deployed Active Directory Federation Services (AD FS), you may have to convert the user account to a managed user before you follow these steps, and then convert the user back to a federated user after you complete these steps.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="4195e-121">创建帐户并设置 Exchange 属性</span><span class="sxs-lookup"><span data-stu-id="4195e-121">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="4195e-122">在电脑上Windows PowerShell远程连接会话并连接到Exchange Online，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4195e-122">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

    ``` Powershell
    Set-ExecutionPolicy Unrestricted
    $org = 'contoso.microsoft.com'
    $cred = Get-Credential $admin@$org
    $sess = New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic -AllowRedirection
    Import-PSSession $sess -DisableNameChecking
    ```

2. <span data-ttu-id="4195e-123">建立会话后，将创建新邮箱并启用为 RoomMailboxAccount，或更改现有会议室邮箱的设置。</span><span class="sxs-lookup"><span data-stu-id="4195e-123">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="4195e-124">这将允许帐户在 Microsoft Teams 会议室。</span><span class="sxs-lookup"><span data-stu-id="4195e-124">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="4195e-125">如果要更改现有的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="4195e-125">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECT01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="4195e-126">如果要创建新的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="4195e-126">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECT01@contoso.com' -Alias PROJECT01 -Name "Project--01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="4195e-127">若要改善会议体验，需要在用户帐户上设置Exchange属性，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4195e-127">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECT01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="4195e-128">为你的本地域帐户添加电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="4195e-128">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="4195e-129">在 **"Active Directory** 用户和计算机 AD"工具中，右键单击要创建 Microsoft Teams 会议室 帐户的容器或组织单位，单击"新建"，然后单击"用户 **"。**</span><span class="sxs-lookup"><span data-stu-id="4195e-129">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="4195e-130">将显示名称 ( - ) cmdlet (Set-Mailbox 或 New-Mailbox) 键入到"全名"框中，将别名键入"用户登录名称"框中。 </span><span class="sxs-lookup"><span data-stu-id="4195e-130">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="4195e-131">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="4195e-131">Click **Next**.</span></span>
3. <span data-ttu-id="4195e-p108">键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。</span><span class="sxs-lookup"><span data-stu-id="4195e-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4195e-135">选择 **"密码永不过期**"是Skype for Business Server Microsoft Teams 会议室。</span><span class="sxs-lookup"><span data-stu-id="4195e-135">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="4195e-136">你的域规则可能禁止使用不过期的密码。</span><span class="sxs-lookup"><span data-stu-id="4195e-136">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="4195e-137">如果是这样，则需要为每个用户帐户创建Microsoft Teams 会议室异常。</span><span class="sxs-lookup"><span data-stu-id="4195e-137">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="4195e-138">单击“**完成**”创建帐户。</span><span class="sxs-lookup"><span data-stu-id="4195e-138">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="4195e-139">创建帐户后，运行目录同步。</span><span class="sxs-lookup"><span data-stu-id="4195e-139">After you have created the account, run a directory synchronization.</span></span> <span data-ttu-id="4195e-140">这可以通过在 PowerShell 中使用 [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) 实现。</span><span class="sxs-lookup"><span data-stu-id="4195e-140">This can be accomplished by using [Set-MsolDirSyncConfiguration](/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span></span> <span data-ttu-id="4195e-141">完成后，转到"用户"页，验证在之前步骤中创建的两个帐户已合并。</span><span class="sxs-lookup"><span data-stu-id="4195e-141">When that is complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-a-microsoft-365-or-office-365-license"></a><span data-ttu-id="4195e-142">分配Microsoft 365或Office 365许可证</span><span class="sxs-lookup"><span data-stu-id="4195e-142">Assign a Microsoft 365 or Office 365 license</span></span>

1. <span data-ttu-id="4195e-143">首先，连接到 Azure AD 以应用某些帐户设置。</span><span class="sxs-lookup"><span data-stu-id="4195e-143">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="4195e-144">你可以通过运行此 cmdlet 来进行连接。</span><span class="sxs-lookup"><span data-stu-id="4195e-144">You can run this cmdlet to connect.</span></span> <span data-ttu-id="4195e-145">有关 Active Directory 的详细信息，请参阅[Azure ActiveDirectory (MSOnline) 1.0。](/powershell/azure/active-directory/overview?view=azureadps-1.0)</span><span class="sxs-lookup"><span data-stu-id="4195e-145">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span>

   > [!NOTE]
   > <span data-ttu-id="4195e-146">[Azure Active Directory PowerShell 2.0。](/powershell/azure/active-directory/overview?view=azureadps-2.0)</span><span class="sxs-lookup"><span data-stu-id="4195e-146">[Azure Active Directory PowerShell 2.0](/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span>

    ``` PowerShell
   Connect-MsolService -Credential $cred
    ```
  <!--   ``` Powershell
     Connect-AzureAD -Credential $cred
     ``` -->

2. <span data-ttu-id="4195e-147">用户帐户需要具有有效的Microsoft 365或Office 365许可证，Exchange Skype for Business Server正常工作。</span><span class="sxs-lookup"><span data-stu-id="4195e-147">The user account needs to have a valid Microsoft 365 or Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="4195e-148">如果你有许可证，则需要为用户帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。</span><span class="sxs-lookup"><span data-stu-id="4195e-148">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="4195e-149">您将在以下步骤中完成分配。</span><span class="sxs-lookup"><span data-stu-id="4195e-149">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="4195e-150">接下来，使用 `Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="4195e-150">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="4195e-151">检索组织或组织的可用 SKUS Microsoft 365 Office 365列表。</span><span class="sxs-lookup"><span data-stu-id="4195e-151">to retrieve a list of available SKUs for your Microsoft 365 or Office 365 organization.</span></span>
4. <span data-ttu-id="4195e-152">列出 SKUS 后，可以使用 `Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="4195e-152">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="4195e-153">cmdlet。</span><span class="sxs-lookup"><span data-stu-id="4195e-153">cmdlet.</span></span> <span data-ttu-id="4195e-154">在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。</span><span class="sxs-lookup"><span data-stu-id="4195e-154">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

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

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="4195e-155">使用帐户启用Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4195e-155">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="4195e-156">从电脑Windows PowerShell远程会话，如下所示：</span><span class="sxs-lookup"><span data-stu-id="4195e-156">Create a remote Windows PowerShell session from a PC as follows:</span></span>

> [!NOTE]
> <span data-ttu-id="4195e-157">Skype for Business联机连接器当前是 PowerShell 模块Teams的一部分。</span><span class="sxs-lookup"><span data-stu-id="4195e-157">Skype for Business Online Connector is currently part of the latest Teams PowerShell module.</span></span>
>
> <span data-ttu-id="4195e-158">如果使用的是[PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams/)Teams最新版本，则无需安装 Skype for Business Online 连接器。</span><span class="sxs-lookup"><span data-stu-id="4195e-158">If you're using the latest [Teams PowerShell public release](https://www.powershellgallery.com/packages/MicrosoftTeams/), you don't need to install the Skype for Business Online Connector.</span></span>

    ``` Powershell
    # When using Teams PowerShell Module
    Import-Module MicrosoftTeams
    $credential = Get-Credential
    Connect-MicrosoftTeams -Credential $credential
    ```

2. <span data-ttu-id="4195e-159">若要为Microsoft Teams 会议室帐户Skype for Business Server，请运行此命令：</span><span class="sxs-lookup"><span data-stu-id="4195e-159">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="4195e-160">如果不确定要用于环境中 RegistrarPool 参数的值，可以使用此命令从现有Skype for Business Server获取该值</span><span class="sxs-lookup"><span data-stu-id="4195e-160">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="4195e-161">向Skype for Business Server帐户分配Microsoft Teams 会议室许可证</span><span class="sxs-lookup"><span data-stu-id="4195e-161">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="4195e-162">以租户管理员登录，打开Microsoft 365管理中心，然后单击"管理"应用。</span><span class="sxs-lookup"><span data-stu-id="4195e-162">Log in as a tenant administrator, open the Microsoft 365 admin center, and click on the Admin app.</span></span>
2. <span data-ttu-id="4195e-163">单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。</span><span class="sxs-lookup"><span data-stu-id="4195e-163">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="4195e-164">单击Microsoft Teams 会议室帐户，然后单击笔图标以编辑帐户信息。</span><span class="sxs-lookup"><span data-stu-id="4195e-164">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="4195e-165">单击“**许可证**”。</span><span class="sxs-lookup"><span data-stu-id="4195e-165">Click **Licenses**.</span></span>
5. <span data-ttu-id="4195e-166">在“**分配许可证**”中，根据你的许可和企业语音要求，选择 Skype for Business（计划 2）或 Skype for Business（计划 3）。</span><span class="sxs-lookup"><span data-stu-id="4195e-166">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="4195e-167">如果要在 Microsoft Teams 会议室 上使用计划 3 许可证，企业语音许可证。</span><span class="sxs-lookup"><span data-stu-id="4195e-167">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="4195e-168">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="4195e-168">Click **Save**.</span></span>

<span data-ttu-id="4195e-169">若要进行验证，应该能够使用客户端Skype for Business登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="4195e-169">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>

> [!NOTE]
> <span data-ttu-id="4195e-170">如果您当前使用带音频会议的计划 2 或 电话系统 和呼叫计划的 Skype for Business 计划 2 的 E1、E3、E4 或 E5 SKUS，这些功能将继续正常工作。</span><span class="sxs-lookup"><span data-stu-id="4195e-170">If you're currently using E1, E3, E4, or E5 SKUs with Skype for Business Plan 2 with Audio Conferencing or with Phone System and a Calling Plan, these will continue to work.</span></span> <span data-ttu-id="4195e-171">但是，应考虑在当前许可证过期后，根据 Teams 会议室更新 中所述[，](rooms-licensing.md)迁移到更简单的许可模型。</span><span class="sxs-lookup"><span data-stu-id="4195e-171">However, you should consider moving to a simpler licensing model as described in [Teams Meeting Room Licensing Update](rooms-licensing.md), after current licenses expire.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4195e-172">如果您使用的是计划 2 Skype for Business，则只能在"仅Microsoft Teams 会议室模式下Skype for Business会议，这意味着您的所有会议都将Skype for Business会议。</span><span class="sxs-lookup"><span data-stu-id="4195e-172">If you're using Skype for Business Plan 2, you can only use the Microsoft Teams Rooms in Skype for Business Only mode, meaning all of your meetings will be Skype for Business meetings.</span></span> <span data-ttu-id="4195e-173">若要为会议室启用会议Microsoft Teams，建议购买会议室许可证。</span><span class="sxs-lookup"><span data-stu-id="4195e-173">In order to enable your meeting room for Microsoft Teams meetings, we recommend you purchase the Meeting Room license.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="4195e-174">相关主题</span><span class="sxs-lookup"><span data-stu-id="4195e-174">Related topics</span></span>

[<span data-ttu-id="4195e-175">配置帐户Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="4195e-175">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="4195e-176">Microsoft Teams 会议室规划</span><span class="sxs-lookup"><span data-stu-id="4195e-176">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="4195e-177">部署 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="4195e-177">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="4195e-178">配置 Microsoft Teams 会议室控制台</span><span class="sxs-lookup"><span data-stu-id="4195e-178">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="4195e-179">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="4195e-179">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)