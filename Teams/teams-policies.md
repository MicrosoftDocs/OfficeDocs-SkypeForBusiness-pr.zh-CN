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
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何使用和管理组织中的团队策略, 以控制用户可在团队和频道中执行的操作。
f1keywords:
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discoverteams
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.createchannels
- ms.teamsadmincenter.teams.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teamsandchannelpolicies.overview
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.discover
- ms.teamsadmincenter.teams.teamspolicies.new.tooltip.create
ms.openlocfilehash: 6a562f9a271a9771796fd73424a94f2820c2f966
ms.sourcegitcommit: 25c30baec1c969eef95b725251a3f4ad3706a19d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/24/2019
ms.locfileid: "36622057"
---
# <a name="manage-teams-policies-in-microsoft-teams"></a><span data-ttu-id="4f29f-103">管理 Microsoft 团队中的团队策略</span><span class="sxs-lookup"><span data-stu-id="4f29f-103">Manage teams policies in Microsoft Teams</span></span>

<span data-ttu-id="4f29f-104">作为管理员, 你可以使用 Microsoft 团队中的团队策略控制你的组织中的哪些用户可以在团队和频道中执行的操作。</span><span class="sxs-lookup"><span data-stu-id="4f29f-104">As an admin, you can use teams policies in Microsoft Teams to control what users in your organization can do in teams and channels.</span></span> <span data-ttu-id="4f29f-105">例如, 你可以设置是否允许用户在搜索结果和团队库中发现专用团队以及是否允许用户创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="4f29f-105">For example, you can set whether users are allowed to discover private teams in search results and in the team gallery and whether users are allowed to create private channels.</span></span>

<span data-ttu-id="4f29f-106">通过转到 Microsoft 团队管理中心中的**团队** > **团队策略**管理团队策略。</span><span class="sxs-lookup"><span data-stu-id="4f29f-106">You manage teams policies by going to **Teams** > **Teams policies** in the Microsoft Teams admin center.</span></span> <span data-ttu-id="4f29f-107">你可以使用全局 (组织范围默认) 策略或创建自定义策略并将其分配给用户。</span><span class="sxs-lookup"><span data-stu-id="4f29f-107">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="4f29f-108">除非你创建并分配自定义策略, 否则你组织中的用户将自动获取全局策略。</span><span class="sxs-lookup"><span data-stu-id="4f29f-108">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="4f29f-109">你可以编辑全局策略, 也可以创建并分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="4f29f-109">You can edit the global policy or create and assign a custom policy.</span></span> <span data-ttu-id="4f29f-110">如果向用户分配了自定义策略, 则该策略将应用于用户。</span><span class="sxs-lookup"><span data-stu-id="4f29f-110">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="4f29f-111">如果未向用户分配自定义策略, 则全局策略将应用于该用户。</span><span class="sxs-lookup"><span data-stu-id="4f29f-111">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span> <span data-ttu-id="4f29f-112">编辑全局策略或分配策略后, 所做的更改可能需要长达24小时才能生效。</span><span class="sxs-lookup"><span data-stu-id="4f29f-112">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

## <a name="create-a-custom-teams-policy"></a><span data-ttu-id="4f29f-113">创建自定义团队策略</span><span class="sxs-lookup"><span data-stu-id="4f29f-113">Create a custom teams policy</span></span>

1. <span data-ttu-id="4f29f-114">在 Microsoft 团队管理中心的左侧导航中, 转到 "**团队** > **团队策略**"。</span><span class="sxs-lookup"><span data-stu-id="4f29f-114">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="4f29f-115">单击“添加”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="4f29f-115">Click **Add**.</span></span>
3. <span data-ttu-id="4f29f-116">输入策略的名称和说明。</span><span class="sxs-lookup"><span data-stu-id="4f29f-116">Enter a name and description for the policy.</span></span>

    ![团队策略设置的屏幕截图](media/teams-policies.png)
4. <span data-ttu-id="4f29f-118">选择所需的设置:</span><span class="sxs-lookup"><span data-stu-id="4f29f-118">Choose the settings that you want:</span></span>

- <span data-ttu-id="4f29f-119">[**发现专用团队**](https://docs.microsoft.com/MicrosoftTeams/teams-policies#discoverteams): 启用此设置可允许用户在搜索结果和团队库中发现个人团队。</span><span class="sxs-lookup"><span data-stu-id="4f29f-119">[**Discover private teams**](https://docs.microsoft.com/MicrosoftTeams/teams-policies#discoverteams): Turn on this setting to allow users to discover private teams in search results and in the team gallery.</span></span>
- <span data-ttu-id="4f29f-120">[**创建专用通道**](https://docs.microsoft.com/MicrosoftTeams/teams-policies#createchannels): 启用此设置可允许用户创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="4f29f-120">[**Create private channels**](https://docs.microsoft.com/MicrosoftTeams/teams-policies#createchannels): Turn on this setting to allow users to create private channels.</span></span>

5. <span data-ttu-id="4f29f-121">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="4f29f-121">Click **Save**.</span></span>

## <a name="edit-a-teams-policy"></a><span data-ttu-id="4f29f-122">编辑团队策略</span><span class="sxs-lookup"><span data-stu-id="4f29f-122">Edit a teams policy</span></span>

<span data-ttu-id="4f29f-123">你可以编辑全局策略或你创建的任何自定义策略。</span><span class="sxs-lookup"><span data-stu-id="4f29f-123">You can edit the global policy or any custom policies that you create.</span></span>

1. <span data-ttu-id="4f29f-124">在 Microsoft 团队管理中心的左侧导航中, 转到 "**团队** > **团队策略**"。</span><span class="sxs-lookup"><span data-stu-id="4f29f-124">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="4f29f-125">通过单击策略名称左侧, 然后单击 "**编辑**", 选择策略。</span><span class="sxs-lookup"><span data-stu-id="4f29f-125">Select the policy by clicking to the left of the policy name, and then click **Edit**.</span></span>
3. <span data-ttu-id="4f29f-126">打开或关闭所需设置, 然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="4f29f-126">Turn on or turn off the settings that you want, and then click **Save**.</span></span>

## <a name="assign-a-custom-teams-policy-to-users"></a><span data-ttu-id="4f29f-127">向用户分配自定义团队策略</span><span class="sxs-lookup"><span data-stu-id="4f29f-127">Assign a custom teams policy to users</span></span>

<span data-ttu-id="4f29f-128">你可以使用 Microsoft 团队管理中心将自定义策略分配给一个或多个用户或 Skype for business PowerShell 模块, 以便为用户组 (如安全组或通讯组) 分配自定义策略。</span><span class="sxs-lookup"><span data-stu-id="4f29f-128">You can use the Microsoft Teams admin center to assign a custom policy to one or more users or the Skype for Business PowerShell module to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

### <a name="assign-a-custom-teams-policy-to-a-user"></a><span data-ttu-id="4f29f-129">向用户分配自定义团队策略</span><span class="sxs-lookup"><span data-stu-id="4f29f-129">Assign a custom teams policy to a user</span></span>

1. <span data-ttu-id="4f29f-130">在 Microsoft 团队管理中心的左侧导航中, 转到 "**用户**", 然后单击 "用户"。</span><span class="sxs-lookup"><span data-stu-id="4f29f-130">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click  the user.</span></span>
2. <span data-ttu-id="4f29f-131">单击 "**策略**", 然后单击 "**分配的策略**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="4f29f-131">Click **Policies**, and then next to **Assigned policies**, click **Edit**.</span></span>
3. <span data-ttu-id="4f29f-132">在 "**团队策略**" 下, 选择要分配的策略, 然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="4f29f-132">Under **Teams policies**, select the policy you want to assign, and then click **Save**.</span></span>

<span data-ttu-id="4f29f-133">若要一次为多个用户分配自定义团队策略, 请参阅[批量编辑团队用户设置](edit-user-settings-in-bulk.md)。</span><span class="sxs-lookup"><span data-stu-id="4f29f-133">To assign a custom teams policy to multiple users at a time, see [Edit Teams user settings in bulk](edit-user-settings-in-bulk.md).</span></span>

<span data-ttu-id="4f29f-134">或者, 您也可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="4f29f-134">Or, you can also do the following:</span></span>

1. <span data-ttu-id="4f29f-135">在 Microsoft 团队管理中心的左侧导航中, 转到 "**团队** > **团队策略**"。</span><span class="sxs-lookup"><span data-stu-id="4f29f-135">In the left navigation of the Microsoft Teams admin center, go to **Teams** > **Teams policies**.</span></span>
2. <span data-ttu-id="4f29f-136">通过单击策略名称的左侧, 选择策略。</span><span class="sxs-lookup"><span data-stu-id="4f29f-136">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="4f29f-137">选择 "**管理用户**"。</span><span class="sxs-lookup"><span data-stu-id="4f29f-137">Select **Manage users**.</span></span>
4. <span data-ttu-id="4f29f-138">在 "**管理用户**" 窗格中, 按 "显示名称" 或 "按用户名搜索用户", 选择名称, 然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="4f29f-138">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="4f29f-139">对要添加的每个用户重复此步骤。</span><span class="sxs-lookup"><span data-stu-id="4f29f-139">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="4f29f-140">添加完用户后, 单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="4f29f-140">When you're finished adding users, click **Save**.</span></span>

### <a name="assign-a-custom-teams-policy-to-users-in-a-group"></a><span data-ttu-id="4f29f-141">向组中的用户分配自定义团队策略</span><span class="sxs-lookup"><span data-stu-id="4f29f-141">Assign a custom teams policy to users in a group</span></span>

<span data-ttu-id="4f29f-142">你可能需要向已标识的多个用户分配自定义团队策略。</span><span class="sxs-lookup"><span data-stu-id="4f29f-142">You may want to assign a custom teams policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="4f29f-143">例如, 你可能想要向安全组中的所有用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="4f29f-143">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="4f29f-144">你可以通过连接到 Azure Active Directory PowerShell for Graph 模块和 Skype for Business PowerShell 模块来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="4f29f-144">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="4f29f-145">有关使用 PowerShell 管理团队的详细信息, 请参阅[团队 PowerShell 概述](teams-powershell-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="4f29f-145">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="4f29f-146">在此示例中, 我们将名为 "市场营销团队" 策略的团队策略分配给 "Contoso 市场营销" 组中的所有用户。</span><span class="sxs-lookup"><span data-stu-id="4f29f-146">In this example, we assign a teams policy called Marketing Teams Policy to all users in the Contoso Marketing group.</span></span>  

> [!NOTE]
> <span data-ttu-id="4f29f-147">请按照[连接到单个 Windows PowerShell 窗口中的所有 Office 365 服务](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window)中的步骤, 确保首先连接到用于 Graph 模块和 Skype For business powershell 模块的 Azure Active Directory powershell。</span><span class="sxs-lookup"><span data-stu-id="4f29f-147">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="4f29f-148">获取特定组的 GroupObjectId。</span><span class="sxs-lookup"><span data-stu-id="4f29f-148">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Marketing"
```
<span data-ttu-id="4f29f-149">获取指定组的成员。</span><span class="sxs-lookup"><span data-stu-id="4f29f-149">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="4f29f-150">将组中的所有用户分配到特定团队策略。</span><span class="sxs-lookup"><span data-stu-id="4f29f-150">Assign all users in the group to a particular teams policy.</span></span> <span data-ttu-id="4f29f-151">在此示例中, 它是市场营销团队政策。</span><span class="sxs-lookup"><span data-stu-id="4f29f-151">In this example, it's Marketing Teams Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsChannelsPolicy -PolicyName "Marketing Teams Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="4f29f-152">此命令可能需要几分钟才能执行, 具体取决于组中的成员数量。</span><span class="sxs-lookup"><span data-stu-id="4f29f-152">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4f29f-153">相关主题</span><span class="sxs-lookup"><span data-stu-id="4f29f-153">Related topics</span></span>

- [<span data-ttu-id="4f29f-154">在 Teams 中管理私人团队的发现</span><span class="sxs-lookup"><span data-stu-id="4f29f-154">Manage discovery of private teams in Teams</span></span>](manage-discovery-of-private-teams.md)
