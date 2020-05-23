---
title: 管理 Microsoft 团队中的团队策略
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理组织中的团队策略，以控制用户可在团队和频道中执行的操作。
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: ce387ec406a9ccfd6ee45a67f2613a45c219f21f
ms.sourcegitcommit: ee2b4c207b3c9f993309f66cf8016e137c001c7f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/23/2020
ms.locfileid: "44349696"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="d9fb1-103">管理 Microsoft 团队中的团队策略</span><span class="sxs-lookup"><span data-stu-id="d9fb1-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="d9fb1-104">作为管理员，你可以使用 Microsoft 团队中的团队策略控制你的组织中的哪些用户可以在团队和频道中执行的操作。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="d9fb1-105">例如，你可以设置是否允许用户在搜索结果和团队库中发现专用团队以及是否允许用户创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-105">For example, you can set whether users are allowed to discover private teams in search results and in the team gallery and whether users are allowed to create private channels.</span></span>

<span data-ttu-id="d9fb1-106">通过转到**Teams**  >  Microsoft 团队管理中心中的团队**团队策略**管理团队策略。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="d9fb1-107">可使用全局（组织范围的默认）策略，或者创建自定义策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-107">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="d9fb1-108">除非你创建并分配了自定义策略，你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="d9fb1-109">你可以编辑全局策略，也可以创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="d9fb1-110">如果向用户分配了自定义策略，则该策略将应用于用户。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-110">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="d9fb1-111">如果未向用户分配自定义策略，则全局策略将应用于该用户。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-111">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="d9fb1-112">编辑全局策略或分配策略后，可能需要几个小时才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-112">After you edit the global policy or assign a policy, it can take a few hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="d9fb1-113">创建自定义团队策略</span><span class="sxs-lookup"><span data-stu-id="d9fb1-113">Create a custom teams policy</span></span>

1. <span data-ttu-id="d9fb1-114">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队**  >  **团队策略**"。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-114">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="d9fb1-115">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-115">Click **Add**.</span></span>
3. <span data-ttu-id="d9fb1-116">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-116">Enter a name and description for the policy.</span></span>

    ![团队策略设置的屏幕截图](media/teams-policies.png)
4. <span data-ttu-id="d9fb1-118">选择所需的设置：</span><span class="sxs-lookup"><span data-stu-id="d9fb1-118">Choose the settings that you want:</span></span>

- <span data-ttu-id="d9fb1-119">**发现专用团队**：<a name="discoverteams"> </a>启用此设置可允许用户在搜索结果和团队库中发现个人团队。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-119">**Discover private teams**:<a name="discoverteams"> </a> Turn on this setting to allow users to discover private teams in search results and in the team gallery.</span></span>
- <span data-ttu-id="d9fb1-120">**创建专用通道**： <a name="createchannels"> </a>启用此设置可允许用户创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-120">**Create private channels**: <a name="createchannels"> </a>Turn on this setting to allow users to create private channels.</span></span>

5. <span data-ttu-id="d9fb1-121">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-121">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="d9fb1-122">编辑团队策略</span><span class="sxs-lookup"><span data-stu-id="d9fb1-122">Edit a teams policy</span></span>

<span data-ttu-id="d9fb1-123">你可以编辑全局策略或你创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-123">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="d9fb1-124">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队**  >  **团队策略**"。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-124">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="d9fb1-125">通过单击策略名称左侧，然后单击 "**编辑**"，选择策略。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-125">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="d9fb1-126">打开或关闭所需设置，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-126">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="d9fb1-127">向用户分配自定义团队策略</span><span class="sxs-lookup"><span data-stu-id="d9fb1-127">Assign a custom teams policy to users</span></span>

<span data-ttu-id="d9fb1-128">你可以使用 Microsoft 团队管理中心将自定义策略分配给一个或多个用户或 Skype for business PowerShell 模块，以便为用户组（如安全组或通讯组）分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-128">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="d9fb1-129">向用户分配自定义团队策略</span><span class="sxs-lookup"><span data-stu-id="d9fb1-129">Assign a custom teams policy to users</span></span>

<span data-ttu-id="d9fb1-130">若要向一个用户分配策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d9fb1-130">To assign a policy to one user:</span></span>

1. <span data-ttu-id="d9fb1-131">在 Microsoft Teams 管理员中心的左侧导航中，转到“用户”，然后单击相应的用户。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="d9fb1-131">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="d9fb1-132">单击 "**策略**"，然后单击 "**分配的策略**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-132">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="d9fb1-133">在 "**团队策略**" 下，选择要分配的策略，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-133">Under **Teams policies**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="d9fb1-134">要一次为多个用户分配策略，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d9fb1-134">To assign a policy to multiple users at a time:</span></span>

1. <span data-ttu-id="d9fb1-135">在 Microsoft 团队管理中心的左侧导航中，转到 "**用户**"，然后搜索用户或筛选视图以显示所需的用户。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-135">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then search for the users or filter the view to show the users you want.</span></span>
2. <span data-ttu-id="d9fb1-136">在 " **&#x2713;** " （复选标记）列中，选择用户。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-136">In the **&#x2713;** (check mark) column, select the users.</span></span> <span data-ttu-id="d9fb1-137">若要选择 "所有用户"，请单击表格顶部的 "&#x2713;" （复选标记）。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-137">To select all users, click the &#x2713; (check mark) at the top of the table.</span></span>
3. <span data-ttu-id="d9fb1-138">单击 "**编辑设置**"，进行所需的更改，然后单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-138">Click **Edit settings**, make the changes that you want, and then click **Apply**.</span></span>  

<span data-ttu-id="d9fb1-139">或者，您也可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d9fb1-139">Or, you can also do the following:</span></span>

1. <span data-ttu-id="d9fb1-140">在 Microsoft 团队管理中心的左侧导航中，转到 "**团队**  >  **团队策略**"。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-140">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="d9fb1-141">单击策略名称的左侧以选择该策略。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-141">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="d9fb1-142">选择“管理用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-142">Select **Manage users**.</span></span>
4. <span data-ttu-id="d9fb1-143">在“**管理用户**”窗格中，按显示名称或用户名搜索用户，选择用户名，然后选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-143">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="d9fb1-144">对想要添加的每一个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-144">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="d9fb1-145">添加完用户后，单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-145">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a><span data-ttu-id="d9fb1-146">向组中的用户分配自定义团队策略</span><span class="sxs-lookup"><span data-stu-id="d9fb1-146">Assign a custom teams policy to users in a group</span></span>

<span data-ttu-id="d9fb1-147">你可能需要向已标识的多个用户分配自定义团队策略。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-147">You may want to assign a custom teams policy to multiple users that you've already identified.</span></span> <span data-ttu-id="d9fb1-148">例如，你可能想要向安全组中的所有用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-148">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="d9fb1-149">你可以通过连接到 Azure Active Directory PowerShell for Graph 模块和 Skype for Business PowerShell 模块来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-149">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="d9fb1-150">有关使用 PowerShell 管理团队的详细信息，请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-150">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="d9fb1-151">在此示例中，我们将名为 "市场营销团队" 策略的团队策略分配给 "Contoso 市场营销" 组中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-151">In this example, we assign a teams policy called Marketing Teams Policy to all users in the Contoso Marketing group.</span></span>  

> [!NOTE]
> <span data-ttu-id="d9fb1-152">请按照[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤，确保首先连接到用于 Graph 模块和 Skype For business powershell 模块的 Azure Active Directory powershell。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-152">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="d9fb1-153">获取特定组的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-153">Get the GroupObjectId of the particular group.</span></span>
```PowerShell
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
<span data-ttu-id="d9fb1-154">获取指定组的成员。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-154">Get the members of the specified group.</span></span>
```PowerShell
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="d9fb1-155">将组中的所有用户分配到特定团队策略。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-155">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="d9fb1-156">在此示例中，它是市场营销团队政策。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-156">In this example, it's Marketing Teams Policy.</span></span>
```PowerShell
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.UserPrincipalName}
``` 
<span data-ttu-id="d9fb1-157">此命令可能需要几分钟才能执行，具体取决于组中的成员数量。</span><span class="sxs-lookup"><span data-stu-id="d9fb1-157">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="d9fb1-158">相关主题</span><span class="sxs-lookup"><span data-stu-id="d9fb1-158">Related topics</span></span>

- [<span data-ttu-id="d9fb1-159">在 Teams 中管理私人团队的发现</span><span class="sxs-lookup"><span data-stu-id="d9fb1-159">Manage discovery of private teams in Teams</span></span>](manage-discovery-of-private-teams.md)
- [<span data-ttu-id="d9fb1-160">团队中的专用频道</span><span class="sxs-lookup"><span data-stu-id="d9fb1-160">Private channels in Teams</span></span>](private-channels.md)
- [<span data-ttu-id="d9fb1-161">向团队中的用户分配策略</span><span class="sxs-lookup"><span data-stu-id="d9fb1-161">Assign policies to your users in Teams</span></span>](assign-policies.md)
