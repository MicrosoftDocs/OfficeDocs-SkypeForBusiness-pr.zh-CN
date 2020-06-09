---
title: 管理 Microsoft 团队中的紧急呼叫策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark, roykuntz
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-voice
f1.keywords: ms.teamsadmincenter.voice.emergencycallingpolicies.overview
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理 Microsoft 团队中的紧急呼叫策略，定义当组织中的团队用户拨打紧急电话时会发生什么情况。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 79332a8675273e86476a68f43489c202b03faea9
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638681"
---
# <a name="manage-emergency-calling-policies-in-microsoft-teams"></a><span data-ttu-id="c444c-103">管理 Microsoft 团队中的紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="c444c-103">Manage emergency calling policies in Microsoft Teams</span></span>

<span data-ttu-id="c444c-104">如果您的组织使用[呼叫计划](set-up-calling-plans.md)或部署的[电话系统直接路由](direct-routing-landing-page.md)，则可以使用 Microsoft 团队中的紧急呼叫策略定义当组织中的团队用户进行紧急呼叫时发生的情况。</span><span class="sxs-lookup"><span data-stu-id="c444c-104">If your organization uses [Calling Plans](set-up-calling-plans.md) or deployed [Phone System Direct Routing](direct-routing-landing-page.md), you can use emergency calling policies in Microsoft Teams to define what happens when a Teams user in your organization makes an emergency call.</span></span> <span data-ttu-id="c444c-105">你可以设置被分配了策略的用户呼叫紧急服务时通知的人员以及通知的方式。</span><span class="sxs-lookup"><span data-stu-id="c444c-105">You can set who to notify and how they are notified when a user who is assigned the policy calls emergency services.</span></span> <span data-ttu-id="c444c-106">例如，你可以将策略设置配置为自动通知组织的安全桌面，并让他们在紧急呼叫中进行侦听。</span><span class="sxs-lookup"><span data-stu-id="c444c-106">For example, you can configure policy settings to automatically notify your organization's security desk and have them listen in emergency calls.</span></span>  

<span data-ttu-id="c444c-107">通过转到**Voice**  >  Microsoft 团队管理中心或使用 Windows PowerShell 中的语音**紧急策略**来管理紧急呼叫策略。</span><span class="sxs-lookup"><span data-stu-id="c444c-107">You manage emergency calling policies by going to **Voice** > **Emergency policies** in the Microsoft Teams admin center or by using Windows PowerShell.</span></span> <span data-ttu-id="c444c-108">可将策略分配给用户和[网络站点](cloud-voice-network-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="c444c-108">The policies can be assigned to users and [network sites](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="c444c-109">对于用户，你可以使用全局（组织范围默认）策略或创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="c444c-109">For users, you can use the global (Org-wide default) policy or create and assign custom policies.</span></span> <span data-ttu-id="c444c-110">除非你创建并分配自定义策略，否则用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="c444c-110">Users will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="c444c-111">请记住，你可以编辑全局策略中的设置，但不能重命名或删除它。</span><span class="sxs-lookup"><span data-stu-id="c444c-111">Keep in mind that you can edit the settings in the global policy but you can't rename or delete it.</span></span> <span data-ttu-id="c444c-112">对于网络站点，您可以创建和分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="c444c-112">For network sites, you create and assign custom policies.</span></span>

<span data-ttu-id="c444c-113">如果你为某个网络网站和用户分配了紧急呼叫策略，并且该用户在该网络站点上，则分配给网络网站的策略将覆盖分配给该用户的策略。</span><span class="sxs-lookup"><span data-stu-id="c444c-113">If you assigned an emergency calling policy to a network site and to a user and if that user is at that network site, the policy that's assigned to the network site overrides the policy that's assigned to the user.</span></span>

## <a name="create-a-custom-emergency-calling-policy"></a><span data-ttu-id="c444c-114">创建自定义紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="c444c-114">Create a custom emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c444c-115">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="c444c-115">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="c444c-116">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **紧急策略**"，然后单击 "**呼叫策略**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="c444c-116">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="c444c-117">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c444c-117">Click **Add**.</span></span>
3. <span data-ttu-id="c444c-118">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="c444c-118">Enter a name and description for the policy.</span></span>
4. <span data-ttu-id="c444c-119">设置当进行紧急呼叫时，您希望将组织中的人员（通常是安全桌面）通知的方式。</span><span class="sxs-lookup"><span data-stu-id="c444c-119">Set how you want to notify people in your organization, typically the security desk, when an emergency call is made.</span></span> <span data-ttu-id="c444c-120">若要执行此操作，请在 "**通知模式**" 下，选择下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="c444c-120">To do this, under **Notification mode**, select one of the following:</span></span>
    - <span data-ttu-id="c444c-121">**仅发送通知**：团队聊天消息将发送到您指定的用户和组。</span><span class="sxs-lookup"><span data-stu-id="c444c-121">**Send notification only**: A Teams chat message is sent to the users and groups that you specify.</span></span>
    - <span data-ttu-id="c444c-122">**Conferenced in 但静音**：将团队聊天消息发送给你指定的用户和组，他们可以在呼叫方和 PSAP 运营商之间的对话中侦听（但不参与）。</span><span class="sxs-lookup"><span data-stu-id="c444c-122">**Conferenced in but are muted**: A Teams chat message is sent to the users and groups that you specify and they can listen (but not participate) in the conversation between the caller and the PSAP operator.</span></span>
    - <span data-ttu-id="c444c-123">**Conferenced 在已取消静音** **（即将推出）**：团队聊天消息将发送给你指定的用户和组，并且可以取消静音以侦听和参与调用方和 PSAP 运算符之间的对话。</span><span class="sxs-lookup"><span data-stu-id="c444c-123">**Conferenced in and are unmuted** **(coming soon)**: A Teams chat message is sent to the users and groups that you specify and they can unmute to listen and participate in the conversation between the caller and the PSAP operator.</span></span>
5.  <span data-ttu-id="c444c-124">如果您选择了 "Conferenced"，**但处于静音**通知模式，请在 "**拨打紧急电话通知的号码**" 框中，输入用户或组的 PSTN 电话号码以呼叫并加入紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="c444c-124">If you selected the **Conferenced in but are muted** notification mode, in the **Numbers to dial for emergency calls notifications** box, you can enter a PSTN phone number of a user or group to call and join the emergency call.</span></span> <span data-ttu-id="c444c-125">例如，输入您的组织的安全桌面号码，当进行紧急呼叫时，您将收到呼叫，然后就能接听电话。</span><span class="sxs-lookup"><span data-stu-id="c444c-125">For example, enter the number of your organization's security desk, who will receive a call when an emergency call is made and can then listen in on the call.</span></span>
6. <span data-ttu-id="c444c-126">搜索并选择一个或多个用户或组（如组织的安全桌面），以便在发生紧急呼叫时发出通知。</span><span class="sxs-lookup"><span data-stu-id="c444c-126">Search for and select one or more users or groups, such as your organization's security desk, to notify when an emergency call is made.</span></span>  <span data-ttu-id="c444c-127">通知可以发送到用户、通讯组和安全组的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="c444c-127">The notification can be sent to email addresses of users, distribution groups, and security groups.</span></span> <span data-ttu-id="c444c-128">最多可通知50用户。</span><span class="sxs-lookup"><span data-stu-id="c444c-128">A maximum of 50 users can be notified.</span></span>
7. <span data-ttu-id="c444c-129">单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="c444c-129">Click **Apply**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="c444c-130">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c444c-130">Using PowerShell</span></span>

<span data-ttu-id="c444c-131">请参阅[新-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="c444c-131">See [New-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csteamsemergencycallingpolicy).</span></span>

## <a name="edit-an-emergency-calling-policy"></a><span data-ttu-id="c444c-132">编辑紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="c444c-132">Edit an emergency calling policy</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c444c-133">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="c444c-133">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="c444c-134">你可以编辑全局策略或你创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="c444c-134">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="c444c-135">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **紧急策略**"，然后单击 "**呼叫策略**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="c444c-135">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="c444c-136">通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。</span><span class="sxs-lookup"><span data-stu-id="c444c-136">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="c444c-137">进行所需的更改，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="c444c-137">Make the changes that you want, and then click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="c444c-138">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c444c-138">Using PowerShell</span></span>

<span data-ttu-id="c444c-139">请参阅[设置-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="c444c-139">See [Set-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsemergencycallingpolicy).</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-users"></a><span data-ttu-id="c444c-140">为用户分配自定义紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="c444c-140">Assign a custom emergency calling policy to users</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c444c-141">使用 Microsoft Teams 管理中心</span><span class="sxs-lookup"><span data-stu-id="c444c-141">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="c444c-142">若要向一个用户分配策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c444c-142">To assign a policy to one user:</span></span>

1. <span data-ttu-id="c444c-143">在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="c444c-143">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="c444c-144">单击 "**策略**"，然后单击 "**分配的策略**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="c444c-144">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="c444c-145">在 "**紧急呼叫策略**" 下，选择要分配的策略，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="c444c-145">Under **Emergency calling policy**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="c444c-146">若要一次向多个用户分配策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c444c-146">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="c444c-147">在 Microsoft Teams 管理中心的左侧导航栏中，转到“**用户**”，然后搜索用户或筛选视图，以显示所需的用户。</span><span class="sxs-lookup"><span data-stu-id="c444c-147">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="c444c-148">在 **&#x2713;**（复选标记）列，选择用户。</span><span class="sxs-lookup"><span data-stu-id="c444c-148">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="c444c-149">若要选择所有用户，请单击表格顶部的 &#x2713;（复选标记）。</span><span class="sxs-lookup"><span data-stu-id="c444c-149">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="c444c-150">单击“**编辑设置**”，执行所需的更改，然后单击“**应用**”。</span><span class="sxs-lookup"><span data-stu-id="c444c-150">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="c444c-151">或者，您也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="c444c-151">Or, you can also do the following:</span></span>

1. <span data-ttu-id="c444c-152">在 Microsoft 团队管理中心的左侧导航中，转到 "**语音**  >  **紧急策略**"，然后单击 "**呼叫策略**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="c444c-152">In the left navigation of the Microsoft Teams admin center, go to **Voice** > **Emergency policies**, and then click the **Calling policies** tab.</span></span>
2. <span data-ttu-id="c444c-153">单击策略名称的左侧以选择该策略。</span><span class="sxs-lookup"><span data-stu-id="c444c-153">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="c444c-154">选择“管理用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c444c-154">Select **Manage users**.</span></span>
4. <span data-ttu-id="c444c-155">在“**管理用户**”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="c444c-155">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="c444c-156">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="c444c-156">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="c444c-157">添加完用户后，单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="c444c-157">When you're finished adding users, click **Save**.</span></span>

### <a name="using-powershell"></a><span data-ttu-id="c444c-158">使用 PowerShell</span><span class="sxs-lookup"><span data-stu-id="c444c-158">Using PowerShell</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-a-user"></a><span data-ttu-id="c444c-159">为用户分配自定义紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="c444c-159">Assign a custom emergency calling policy to a user</span></span>

<span data-ttu-id="c444c-160">请参阅[授权-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy)。</span><span class="sxs-lookup"><span data-stu-id="c444c-160">See [Grant-CsTeamsEmergencyCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsemergencycallingpolicy).</span></span>

#### <a name="assign-a-custom-emergency-calling-policy-to-users-in-a-group"></a><span data-ttu-id="c444c-161">为组中的用户分配自定义紧急呼叫策略</span><span class="sxs-lookup"><span data-stu-id="c444c-161">Assign a custom emergency calling policy to users in a group</span></span>

<span data-ttu-id="c444c-162">您可能希望将自定义紧急呼叫策略分配给已标识的多个用户。</span><span class="sxs-lookup"><span data-stu-id="c444c-162">You may want to assign a custom emergency calling policy to multiple users that you've already identified.</span></span> <span data-ttu-id="c444c-163">例如，你可能想要向安全组中的所有用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="c444c-163">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="c444c-164">你可以通过连接到 Azure Active Directory PowerShell for Graph 模块和 Skype for Business PowerShell 模块来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="c444c-164">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span>

<span data-ttu-id="c444c-165">在此示例中，我们将名为 "操作紧急呼叫策略" 的策略分配给 "Contoso 操作" 组中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="c444c-165">In this example, we assign a policy called Operations Emergency Calling Policy to all users in the Contoso Operations group.</span></span>  

> [!NOTE]
> <span data-ttu-id="c444c-166">通过按照[连接到单个 Windows PowerShell 窗口中的所有 Microsoft 365 或 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤，确保首先连接到用于 Graph 模块和 Skype For business powershell 模块的 Azure Active Directory powershell。</span><span class="sxs-lookup"><span data-stu-id="c444c-166">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Microsoft 365 or Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="c444c-167">获取特定组的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="c444c-167">Get the GroupObjectId of the particular group.</span></span>
```powershell
$group = Get-AzureADGroup -SearchString "Contoso Operations"
```
<span data-ttu-id="c444c-168">获取指定组的成员。</span><span class="sxs-lookup"><span data-stu-id="c444c-168">Get the members of the specified group.</span></span>
```powershell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="c444c-169">将组中的所有用户分配到特定团队策略。</span><span class="sxs-lookup"><span data-stu-id="c444c-169">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="c444c-170">在此示例中，它是运行紧急呼叫路由策略的操作。</span><span class="sxs-lookup"><span data-stu-id="c444c-170">In this example, it's Operations Emergency Call Routing Policy.</span></span>
```powershell
$members | ForEach-Object {Grant-CsTeamsEmergencyCallingPolicy -PolicyName "Operations Emergency Calling Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="c444c-171">此命令可能需要几分钟才能执行，具体取决于组中的成员数量。</span><span class="sxs-lookup"><span data-stu-id="c444c-171">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="assign-a-custom-emergency-calling-policy-to-a-network-site"></a><span data-ttu-id="c444c-172">将自定义紧急呼叫策略分配给网络站点</span><span class="sxs-lookup"><span data-stu-id="c444c-172">Assign a custom emergency calling policy to a network site</span></span>

<span data-ttu-id="c444c-173">使用[CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet 将紧急呼叫策略分配给网络站点。</span><span class="sxs-lookup"><span data-stu-id="c444c-173">Use the [Set-CsTenantNetworkSite](https://docs.microsoft.com/powershell/module/skype/set-cstenantnetworksite) cmdlet to assign an emergency calling policy to a network site.</span></span>

<span data-ttu-id="c444c-174">以下示例显示了如何将名为 Contoso 紧急呼叫策略1的策略分配给 Site1 网站。</span><span class="sxs-lookup"><span data-stu-id="c444c-174">The following example shows how to assign a policy called Contoso Emergency Calling Policy 1 to the Site1 site.</span></span>

```powershell
Set-CsTenantNetworkSite -identity "site1" -EmergencyCallingPolicy "Contoso Emergency Calling Policy 1"
```

## <a name="related-topics"></a><span data-ttu-id="c444c-175">相关主题</span><span class="sxs-lookup"><span data-stu-id="c444c-175">Related topics</span></span>

- [<span data-ttu-id="c444c-176">管理团队中的紧急呼叫路由策略</span><span class="sxs-lookup"><span data-stu-id="c444c-176">Manage emergency call routing policies in Teams</span></span>](manage-emergency-call-routing-policies.md)
- [<span data-ttu-id="c444c-177">Teams PowerShell 概览</span><span class="sxs-lookup"><span data-stu-id="c444c-177">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="c444c-178">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="c444c-178">Assign policies to your users in Teams</span></span>](assign-policies.md)
