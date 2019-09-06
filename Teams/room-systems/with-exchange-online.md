---
title: 使用 Exchange Online 部署 Microsoft Teams Rooms
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
- M365-voice
ms.custom: ''
ms.assetid: f3ba85b8-442c-4133-963f-76f1c8a1fff9
description: 阅读本主题，了解如何通过 Exchange Online 部署 Microsoft 团队聊天室的相关信息。
ms.openlocfilehash: d2e410eeb04ac65f7fc458bc6c1d8e67579c0f8b
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/06/2019
ms.locfileid: "36774931"
---
# <a name="deploy-microsoft-teams-rooms-with-exchange-online"></a><span data-ttu-id="0af12-103">使用 Exchange Online 部署 Microsoft Teams Rooms</span><span class="sxs-lookup"><span data-stu-id="0af12-103">Deploy Microsoft Teams Rooms with Exchange Online</span></span>

<span data-ttu-id="0af12-104">阅读本主题，了解如何在本地通过 Exchange Online 和 Skype for business 服务器部署 Microsoft 团队聊天室的相关信息。</span><span class="sxs-lookup"><span data-stu-id="0af12-104">Read this topic for information on how to deploy Microsoft Teams Rooms with Exchange Online and Skype for Business Server on-premises.</span></span>
  
<span data-ttu-id="0af12-105">如果你的组织具有混合服务，并且某些托管在本地托管和某些托管网络，则你的配置将取决于托管每个服务的位置。</span><span class="sxs-lookup"><span data-stu-id="0af12-105">If your organization has a mix of services, with some hosted on premises and some hosted online, then your configuration will depend on where each service is hosted.</span></span> <span data-ttu-id="0af12-106">本主题介绍 Microsoft 团队聊天室的混合部署和 Exchange 托管网络。</span><span class="sxs-lookup"><span data-stu-id="0af12-106">This topic covers hybrid deployments for Microsoft Teams Rooms with Exchange hosted online.</span></span> <span data-ttu-id="0af12-107">由于这种类型的部署中存在如此多的不同变体，因此不可能提供所有这些类型的详细说明。</span><span class="sxs-lookup"><span data-stu-id="0af12-107">Because there are so many different variations in this type of deployment, it's not possible to provide detailed instructions for all of them.</span></span> <span data-ttu-id="0af12-108">以下过程将适用于许多配置。</span><span class="sxs-lookup"><span data-stu-id="0af12-108">The following process will work for many configurations.</span></span> <span data-ttu-id="0af12-109">如果该进程不适合你的设置，我们建议你使用 Windows PowerShell 获得相同的最终结果，如此处所述以及其他部署选项。</span><span class="sxs-lookup"><span data-stu-id="0af12-109">If the process isn't right for your setup, we recommend that you use Windows PowerShell to achieve the same end result as documented here, and for other deployment options.</span></span>

<span data-ttu-id="0af12-110">设置用户帐户最简单的方法是使用远程 Windows PowerShell 进行配置。</span><span class="sxs-lookup"><span data-stu-id="0af12-110">The easiest way to set up user accounts is to configure them using remote Windows PowerShell.</span></span> <span data-ttu-id="0af12-111">Microsoft 提供了[SkypeRoomProvisioningScript](https://go.microsoft.com/fwlink/?linkid=870105)，该脚本可帮助创建新的用户帐户，或验证你拥有的现有资源帐户，以帮助你将其转换为兼容的 Microsoft 团队聊天室用户帐户。</span><span class="sxs-lookup"><span data-stu-id="0af12-111">Microsoft provides [SkypeRoomProvisioningScript.ps1](https://go.microsoft.com/fwlink/?linkid=870105), a script that will help create new user accounts, or validate existing resource accounts you have in order to help you turn them into compatible Microsoft Teams Rooms user accounts.</span></span> <span data-ttu-id="0af12-112">如果你愿意，可以按照以下步骤配置 Microsoft 团队聊天室设备将使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="0af12-112">If you prefer, you can follow the steps below to configure accounts your Microsoft Teams Rooms device will use.</span></span>

## <a name="requirements"></a><span data-ttu-id="0af12-113">要求</span><span class="sxs-lookup"><span data-stu-id="0af12-113">Requirements</span></span>

<span data-ttu-id="0af12-114">在使用 Exchange Online 部署 Microsoft 团队聊天室之前，请确保满足这些要求。</span><span class="sxs-lookup"><span data-stu-id="0af12-114">Before you deploy Microsoft Teams Rooms with Exchange Online, be sure you have met the requirements.</span></span> <span data-ttu-id="0af12-115">有关详细信息，请参阅[Microsoft 团队会议室要求](requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="0af12-115">For more information, see [Microsoft Teams Rooms requirements](requirements.md).</span></span>
  
<span data-ttu-id="0af12-116">若要通过 Exchange Online 部署 Microsoft 团队聊天室，请按照下面的步骤操作。</span><span class="sxs-lookup"><span data-stu-id="0af12-116">To deploy Microsoft Teams Rooms with Exchange Online, follow the steps below.</span></span> <span data-ttu-id="0af12-117">确保你有合适的权限来运行相关 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="0af12-117">Be sure you have the right permissions to run the associated cmdlets.</span></span> 

   > [!NOTE]
   >  <span data-ttu-id="0af12-118">此部分中的[适用于 Windows PowerShell cmdlet 的 Azure Active Directory 模块](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)（例如，Set-MsolUser）已在为 Microsoft 团队聊天室设备设置帐户中进行了测试。</span><span class="sxs-lookup"><span data-stu-id="0af12-118">The [Azure Active Directory Module for Windows PowerShell cmdlets](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0) in this section (for example,  Set-MsolUser) have been tested in setting up accounts for Microsoft Teams Rooms devices.</span></span> <span data-ttu-id="0af12-119">其他 cmdlet 可能有效，但尚未在此特定方案中对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="0af12-119">It's possible that other cmdlets may work, however, they haven't been tested in this specific scenario.</span></span>
  
### <a name="create-an-account-and-set-exchange-properties"></a><span data-ttu-id="0af12-120">创建帐户并设置 Exchange 属性</span><span class="sxs-lookup"><span data-stu-id="0af12-120">Create an account and set Exchange properties</span></span>

1. <span data-ttu-id="0af12-121">在电脑上启动远程 Windows PowerShell 会话并连接到 Exchange Online，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0af12-121">Start a remote Windows PowerShell session on a PC and connect to Exchange Online as follows:</span></span>

``` Powershell
Set-ExecutionPolicy Unrestricted
$org='contoso.microsoft.com'
$cred=Get-Credential $admin@$org
$sess= New-PSSession -ConfigurationName Microsoft.Exchange -ConnectionUri https://outlook.office365.com/powershell-liveid/ -Credential $cred -Authentication Basic  -AllowRedirection
Import-PSSession $Session -DisableNameChecking
```

2. <span data-ttu-id="0af12-122">建立会话后，你将创建一个新邮箱并将其作为 RoomMailboxAccount 启用，或更改现有会议室邮箱的设置。</span><span class="sxs-lookup"><span data-stu-id="0af12-122">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="0af12-123">这将允许帐户在 Microsoft 团队聊天室中进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="0af12-123">This will allow the account to authenticate into Microsoft Teams Rooms.</span></span>

   <span data-ttu-id="0af12-124">如果要更改现有的资源邮箱：</span><span class="sxs-lookup"><span data-stu-id="0af12-124">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

    <span data-ttu-id="0af12-125">如果要创建新的资源邮箱，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="0af12-125">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -MicrosoftOnlineServicesID 'PROJECTRIGEL01@contoso.com' -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="0af12-126">若要改善会议体验，你需要在用户帐户上设置 Exchange 属性，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0af12-126">To improve the meeting experience, you'll need to set the Exchange properties on the user account as follows:</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity 'PROJECTRIGEL01@contoso.com' -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```



### <a name="add-an-email-address-for-your-on-premises-domain-account"></a><span data-ttu-id="0af12-127">为你的本地域帐户添加电子邮件地址</span><span class="sxs-lookup"><span data-stu-id="0af12-127">Add an email address for your on-premises domain account</span></span>

1. <span data-ttu-id="0af12-128">在 " **Active Directory 用户和计算机广告**" 工具中，右键单击将在其中创建 Microsoft 团队聊天室帐户的容器或组织单元，单击 "**新建**"，然后单击 "**用户**"。</span><span class="sxs-lookup"><span data-stu-id="0af12-128">In **Active Directory Users and Computers AD** tool, right-click on the container or Organizational Unit that your Microsoft Teams Rooms accounts will be created in, click **New**, and then click **User**.</span></span>
2. <span data-ttu-id="0af12-129">在 "**完整名称**" 框中键入 "显示名称" （-Identity）和 "**用户登录名**" 框中的别名（"设置邮箱" 或 "新邮箱"）。</span><span class="sxs-lookup"><span data-stu-id="0af12-129">Type the display name (- Identity ) from the prior cmdlet (Set-Mailbox or New-Mailbox) into the **Full name** box, and the alias into the **User logon name** box.</span></span> <span data-ttu-id="0af12-130">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="0af12-130">Click **Next**.</span></span>
3. <span data-ttu-id="0af12-p108">键入此帐户的密码。你需要重新键入密码进行确认。确保“**密码永不过期**”复选框是选中的唯一选项。</span><span class="sxs-lookup"><span data-stu-id="0af12-p108">Type the password for this account. You'll need to retype it for verification. Make sure the **Password never expires** checkbox is the only option selected.</span></span>

    > [!NOTE]
    > <span data-ttu-id="0af12-134">选择 "**密码永不过期**" 是 Microsoft 团队聊天室上的 Skype For business 服务器的要求。</span><span class="sxs-lookup"><span data-stu-id="0af12-134">Selecting **Password never expires** is a requirement for Skype for Business Server on Microsoft Teams Rooms.</span></span> <span data-ttu-id="0af12-135">你的域规则可能禁止使用不过期的密码。</span><span class="sxs-lookup"><span data-stu-id="0af12-135">Your domain rules may prohibit passwords that don't expire.</span></span> <span data-ttu-id="0af12-136">如果是这样，你将需要为每个 Microsoft 团队聊天室用户帐户创建一个例外。</span><span class="sxs-lookup"><span data-stu-id="0af12-136">If so, you'll need to create an exception for each Microsoft Teams Rooms user account.</span></span>
  
4. <span data-ttu-id="0af12-137">单击“**完成**”创建帐户。</span><span class="sxs-lookup"><span data-stu-id="0af12-137">Click **Finish** to create the account.</span></span>
5. <span data-ttu-id="0af12-138">创建帐户后，运行目录同步。</span><span class="sxs-lookup"><span data-stu-id="0af12-138">After you have created the account, run a directory synchronization.</span></span> <span data-ttu-id="0af12-139">这可以通过在 PowerShell 中使用[MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0)来实现。</span><span class="sxs-lookup"><span data-stu-id="0af12-139">This can be accomplished by using [Set-MsolDirSyncConfiguration](https://docs.microsoft.com/powershell/module/msonline/set-msoldirsyncconfiguration?view=azureadps-1.0) in PowerShell.</span></span> <span data-ttu-id="0af12-140">完成后，转到 "用户" 页面并验证之前步骤中创建的两个帐户是否已合并。</span><span class="sxs-lookup"><span data-stu-id="0af12-140">When that is complete, go to the users page and verify that the two accounts created in the previous steps have merged.</span></span>

### <a name="assign-an-office-365-license"></a><span data-ttu-id="0af12-141">分配一个 Office 365 许可证</span><span class="sxs-lookup"><span data-stu-id="0af12-141">Assign an Office 365 license</span></span>

1. <span data-ttu-id="0af12-142">首先，连接到 Azure AD 以应用某些帐户设置。</span><span class="sxs-lookup"><span data-stu-id="0af12-142">First, connect to Azure AD to apply some account settings.</span></span> <span data-ttu-id="0af12-143">你可以通过运行此 cmdlet 来进行连接。</span><span class="sxs-lookup"><span data-stu-id="0af12-143">You can run this cmdlet to connect.</span></span> <span data-ttu-id="0af12-144">有关 Active Directory 的详细信息，请参阅[Azure ActiveDirectory （import-module msonline） 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0)。</span><span class="sxs-lookup"><span data-stu-id="0af12-144">For details about Active Directory, see [Azure ActiveDirectory (MSOnline) 1.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-1.0).</span></span> 

   > [!NOTE]
   > <span data-ttu-id="0af12-145">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0)不受支持。</span><span class="sxs-lookup"><span data-stu-id="0af12-145">[Azure Active Directory PowerShell 2.0](https://docs.microsoft.com/en-us/powershell/azure/active-directory/overview?view=azureadps-2.0) is not supported.</span></span> 

  ``` PowerShell
 Connect-MsolService -Credential $cred
  ```
<!--   ``` Powershell
   Connect-AzureAD -Credential $cred
   ``` -->

2. <span data-ttu-id="0af12-146">用户帐户需要拥有有效的 Office 365 许可证，才能确保 Exchange 和 Skype for business 服务器能够正常工作。</span><span class="sxs-lookup"><span data-stu-id="0af12-146">The user account needs to have a valid Office 365 license to ensure that Exchange and Skype for Business Server will work.</span></span> <span data-ttu-id="0af12-147">如果你有许可证，则需要为用户帐户分配使用位置—此位置确定可供帐户使用的许可证 SKU。</span><span class="sxs-lookup"><span data-stu-id="0af12-147">If you have the license, you need to assign a usage location to your user account—this determines what license SKUs are available for your account.</span></span> <span data-ttu-id="0af12-148">您将按以下步骤进行分配。</span><span class="sxs-lookup"><span data-stu-id="0af12-148">You'll make the assignment in a following step.</span></span>
3. <span data-ttu-id="0af12-149">接下来，使用`Get-MsolAccountSku`</span><span class="sxs-lookup"><span data-stu-id="0af12-149">Next, use `Get-MsolAccountSku`</span></span> <!--Get-AzureADSubscribedSku--> <span data-ttu-id="0af12-150">检索 Office 365 租户的可用 Sku 列表。</span><span class="sxs-lookup"><span data-stu-id="0af12-150">to retrieve a list of available SKUs for your Office 365 tenant.</span></span>
4. <span data-ttu-id="0af12-151">列出 Sku 后，您可以使用`Set-MsolUserLicense`</span><span class="sxs-lookup"><span data-stu-id="0af12-151">Once you list out the SKUs, you can add a license using the `Set-MsolUserLicense`</span></span> <!-- Set-AzureADUserLicense--> <span data-ttu-id="0af12-152">cmdlet.</span><span class="sxs-lookup"><span data-stu-id="0af12-152">cmdlet.</span></span> <span data-ttu-id="0af12-153">在此示例中，$strLicense 是你看到的 SKU 代码（例如，contoso:STANDARDPACK）。</span><span class="sxs-lookup"><span data-stu-id="0af12-153">In this case, $strLicense is the SKU code that you see (for example, contoso:STANDARDPACK).</span></span> 

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

### <a name="enable-the-user-account-with-skype-for-business-server"></a><span data-ttu-id="0af12-154">使用 Skype for Business 服务器启用用户帐户</span><span class="sxs-lookup"><span data-stu-id="0af12-154">Enable the user account with Skype for Business Server</span></span>

1. <span data-ttu-id="0af12-155">从电脑创建远程 Windows PowerShell 会话，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0af12-155">Create a remote Windows PowerShell session from a PC as follows:</span></span>

    ``` Powershell
    Import-Module SkypeOnlineConnector  
    $cssess=New-CsOnlineSession -Credential $cred  
    Import-PSSession $cssess -AllowClobber
    ```

2. <span data-ttu-id="0af12-156">若要为 Skype for business Server 启用 Microsoft 团队聊天室帐户，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="0af12-156">To enable your Microsoft Teams Rooms account for Skype for Business Server, run this command:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool 'sippoolbl20a04.infra.lync.com' -SipAddressType EmailAddress
   ```

    <span data-ttu-id="0af12-157">如果你不确定要在你的环境中使用 RegistrarPool 参数的值，可以使用此命令从现有 Skype for Business 服务器用户获取该值</span><span class="sxs-lookup"><span data-stu-id="0af12-157">If you aren't sure what value to use for the RegistrarPool parameter in your environment, you can get the value from an existing Skype for Business Server user using this command</span></span>

   ``` Powershell
   Get-CsOnlineUser -Identity 'alice@contoso.com'| fl *registrarpool*
   ```

### <a name="assign-a-skype-for-business-server-license-to-your-microsoft-teams-rooms-account"></a><span data-ttu-id="0af12-158">将 Skype for Business Server 许可证分配给你的 Microsoft 团队聊天室帐户</span><span class="sxs-lookup"><span data-stu-id="0af12-158">Assign a Skype for Business Server license to your Microsoft Teams Rooms account</span></span>

1. <span data-ttu-id="0af12-159">以租户管理员身份登录，打开 Office 365 管理门户，然后单击 "管理" 应用。</span><span class="sxs-lookup"><span data-stu-id="0af12-159">Log in as a tenant administrator, open the Office 365 Administrative Portal, and click on the Admin app.</span></span>
2. <span data-ttu-id="0af12-160">单击“**用户和组**”，然后单击“**添加用户、重置密码等**”。</span><span class="sxs-lookup"><span data-stu-id="0af12-160">Click on **Users and Groups** and then click **Add users, reset passwords, and more**.</span></span>
3. <span data-ttu-id="0af12-161">单击 "Microsoft 团队聊天室帐户"，然后单击 "笔" 图标以编辑帐户信息。</span><span class="sxs-lookup"><span data-stu-id="0af12-161">Click the Microsoft Teams Rooms account, and then click the pen icon to edit the account information.</span></span>
4. <span data-ttu-id="0af12-162">单击“**许可证**”。</span><span class="sxs-lookup"><span data-stu-id="0af12-162">Click **Licenses**.</span></span>
5. <span data-ttu-id="0af12-163">在“**分配许可证**”中，根据你的许可和企业语音要求，选择 Skype for Business（计划 2）或 Skype for Business（计划 3）。</span><span class="sxs-lookup"><span data-stu-id="0af12-163">In **Assign licenses**, select Skype for Business (Plan 2) or Skype for Business (Plan 3), depending on your licensing and Enterprise Voice requirements.</span></span> <span data-ttu-id="0af12-164">如果要在 Microsoft 团队聊天室使用企业语音，则必须使用计划3许可证。</span><span class="sxs-lookup"><span data-stu-id="0af12-164">You'll have to use a Plan 3 license if you want to use Enterprise Voice on Microsoft Teams Rooms.</span></span>
6. <span data-ttu-id="0af12-165">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="0af12-165">Click **Save**.</span></span>

<span data-ttu-id="0af12-166">对于验证，你应该能够使用任何 Skype for Business 客户端登录到此帐户。</span><span class="sxs-lookup"><span data-stu-id="0af12-166">For validation, you should be able to use any Skype for Business client to log in to this account.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0af12-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0af12-167">See also</span></span>

[<span data-ttu-id="0af12-168">为 Microsoft 团队聊天室配置帐户</span><span class="sxs-lookup"><span data-stu-id="0af12-168">Configure accounts for Microsoft Teams Rooms</span></span>](room-systems-v2-configure-accounts.md)

[<span data-ttu-id="0af12-169">规划 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="0af12-169">Plan for Microsoft Teams Rooms</span></span>](skype-room-systems-v2-0.md)
  
[<span data-ttu-id="0af12-170">部署 Microsoft 团队聊天室</span><span class="sxs-lookup"><span data-stu-id="0af12-170">Deploy Microsoft Teams Rooms</span></span>](room-systems-v2.md)
  
[<span data-ttu-id="0af12-171">配置 Microsoft 团队聊天室控制台</span><span class="sxs-lookup"><span data-stu-id="0af12-171">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="0af12-172">管理 Microsoft Teams 会议室</span><span class="sxs-lookup"><span data-stu-id="0af12-172">Manage Microsoft Teams Rooms</span></span>](skype-room-systems-v2.md)
