---
title: 在 Microsoft Teams 管理中心中管理团队
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: 了解如何在 Microsoft 团队管理中心查看或更新团队。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c205c8d3b4f57935c1882530815643a90357d1aa
ms.sourcegitcommit: b5949233f8080a6cf0edb4b5e27272214feb1c22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2019
ms.locfileid: "34548267"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="5c84d-103">在 Microsoft Teams 管理中心中管理团队</span><span class="sxs-lookup"><span data-stu-id="5c84d-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================


## <a name="overview"></a><span data-ttu-id="5c84d-104">概述</span><span class="sxs-lookup"><span data-stu-id="5c84d-104">Overview</span></span>

<span data-ttu-id="5c84d-105">作为 IT 管理员, 你可能需要查看或更新你的组织为协作设置的团队, 或者你可能需要执行补救操作, 例如分配 ownerless 团队的所有者。</span><span class="sxs-lookup"><span data-stu-id="5c84d-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="5c84d-106">你可以通过 Microsoft 团队 PowerShell 模块和 Microsoft 团队管理中心管理组织中使用的团队。</span><span class="sxs-lookup"><span data-stu-id="5c84d-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="5c84d-107">对于使用这两个工具集的完全管理功能, 您应该确保已为您分配了下列角色之一:</span><span class="sxs-lookup"><span data-stu-id="5c84d-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="5c84d-108">全局管理员</span><span class="sxs-lookup"><span data-stu-id="5c84d-108">Global Administrator</span></span>
- <span data-ttu-id="5c84d-109">Teams 服务管理员</span><span class="sxs-lookup"><span data-stu-id="5c84d-109">Teams Service Administrator</span></span>

<span data-ttu-id="5c84d-110">可以在[使用 Microsoft 团队管理员角色管理团队](using-admin-roles.md)的团队中了解有关管理员角色的详细信息, 还可以阅读有关如何使用 PowerShell cmdlet 来管理[Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)中的团队的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5c84d-110">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="5c84d-111">本文概述了 Microsoft 团队管理中心中的团队管理工具。</span><span class="sxs-lookup"><span data-stu-id="5c84d-111">This article provides an overview of the management tools for teams in the Microsoft Teams admin center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="5c84d-112">团队概述网格</span><span class="sxs-lookup"><span data-stu-id="5c84d-112">Teams overview grid</span></span>

<span data-ttu-id="5c84d-113">团队的管理工具位于 Microsoft 团队管理中心的 "**团队**" 节点下。</span><span class="sxs-lookup"><span data-stu-id="5c84d-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="5c84d-114">(在管理中心中, 选择 "**团队** > **管理团队**"。)每个团队由 Office 365 组支持, 并且此节点提供已在你的组织中启用了 Microsoft 团队的组的视图。</span><span class="sxs-lookup"><span data-stu-id="5c84d-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![团队概述网格的屏幕截图](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="5c84d-116">网格显示以下属性:</span><span class="sxs-lookup"><span data-stu-id="5c84d-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="5c84d-117">**团队名称**</span><span class="sxs-lookup"><span data-stu-id="5c84d-117">**Team name**</span></span>
- <span data-ttu-id="5c84d-118">**频道**-组中所有频道的计数, 包括默认的 "常规" 通道。</span><span class="sxs-lookup"><span data-stu-id="5c84d-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="5c84d-119">**用户**-用户总数 (包括来自租户的所有者、来宾和成员) 的计数。</span><span class="sxs-lookup"><span data-stu-id="5c84d-119">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="5c84d-120">**所有者**-此团队的所有者计数。</span><span class="sxs-lookup"><span data-stu-id="5c84d-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="5c84d-121">**来宾**-属于此团队成员的 Azure ACTIVE Directory B2B 来宾用户的计数。</span><span class="sxs-lookup"><span data-stu-id="5c84d-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="5c84d-122">**隐私**-支持的 Office 365 组的可见性/AccessType。</span><span class="sxs-lookup"><span data-stu-id="5c84d-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="5c84d-123">**状态**-此团队的已存档或活动状态。</span><span class="sxs-lookup"><span data-stu-id="5c84d-123">**Status** - the Archived or Active status for this team.</span></span>  <span data-ttu-id="5c84d-124">了解有关存档中的团队[或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5c84d-124">Learn more about archiving teams in the [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="5c84d-125">**GroupID** -支持 Office 365 组的独特的 GroupID</span><span class="sxs-lookup"><span data-stu-id="5c84d-125">**GroupID** - the unique GroupID of the backing Office 365 group</span></span>
- <span data-ttu-id="5c84d-126">**分类**-分配给支持 Office 365 组的分类 (如果在您的组织中使用)。</span><span class="sxs-lookup"><span data-stu-id="5c84d-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span>  <span data-ttu-id="5c84d-127">了解有关分类的详细信息, 请参阅[为组织中的 Office 组创建分类](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="5c84d-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="5c84d-128">**说明**-针对支持的 Office 365 组设置的说明</span><span class="sxs-lookup"><span data-stu-id="5c84d-128">**Description** - the description set for the backing Office 365 group</span></span>

### <a name="search"></a><span data-ttu-id="5c84d-129">搜索</span><span class="sxs-lookup"><span data-stu-id="5c84d-129">Search</span></span>

<span data-ttu-id="5c84d-130">搜索当前支持字符串 "始于" 并搜索 "**团队名称**" 字段。</span><span class="sxs-lookup"><span data-stu-id="5c84d-130">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="5c84d-131">编辑</span><span class="sxs-lookup"><span data-stu-id="5c84d-131">Edit</span></span>

<span data-ttu-id="5c84d-132">通过从网格中选择团队, 然后选择 "**编辑**" 按钮, 可以编辑组和团队特定的设置。</span><span class="sxs-lookup"><span data-stu-id="5c84d-132">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

!["编辑团队选项" 的屏幕截图](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="5c84d-134">团队档案</span><span class="sxs-lookup"><span data-stu-id="5c84d-134">Team profile</span></span>

<span data-ttu-id="5c84d-135">通过单击团队名称, 可以从 "主团队概述" 网格导航到任何团队的团队个人资料页面。</span><span class="sxs-lookup"><span data-stu-id="5c84d-135">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="5c84d-136">"团队配置文件" 页面显示属于团队的成员、所有者和来宾 (及其支持的 O365 组) 以及团队的频道和设置。</span><span class="sxs-lookup"><span data-stu-id="5c84d-136">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="5c84d-137">从 "团队个人资料" 页面, 您可以:</span><span class="sxs-lookup"><span data-stu-id="5c84d-137">From the team profile page, you can:</span></span>

- <span data-ttu-id="5c84d-138">添加或删除成员和所有者。</span><span class="sxs-lookup"><span data-stu-id="5c84d-138">Add or remove members and owners.</span></span>
- <span data-ttu-id="5c84d-139">添加或删除频道 (请注意, 您不能删除 "常规频道")。</span><span class="sxs-lookup"><span data-stu-id="5c84d-139">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="5c84d-140">更新团队和组设置。</span><span class="sxs-lookup"><span data-stu-id="5c84d-140">Update team and group settings.</span></span>
 
![示例团队档案的屏幕截图](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="5c84d-142">对团队进行更改</span><span class="sxs-lookup"><span data-stu-id="5c84d-142">Making changes to teams</span></span>

<span data-ttu-id="5c84d-143">你可以更改团队的以下元素:</span><span class="sxs-lookup"><span data-stu-id="5c84d-143">You can change the following elements of a team:</span></span>
- <span data-ttu-id="5c84d-144">**团队中的用户**-你可以添加或删除成员, 以及提升或降级所有者</span><span class="sxs-lookup"><span data-stu-id="5c84d-144">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="5c84d-145">**频道**-您可以添加新频道或删除现有频道。</span><span class="sxs-lookup"><span data-stu-id="5c84d-145">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="5c84d-146">您不能删除默认的 "常规" 频道, 创建后只能编辑频道名称, 不能编辑描述。</span><span class="sxs-lookup"><span data-stu-id="5c84d-146">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="5c84d-147">**团队名称**</span><span class="sxs-lookup"><span data-stu-id="5c84d-147">**Team name**</span></span>
- <span data-ttu-id="5c84d-148">**团队说明**</span><span class="sxs-lookup"><span data-stu-id="5c84d-148">**Team description**</span></span>
- <span data-ttu-id="5c84d-149">**工作组隐私**-公共或私人</span><span class="sxs-lookup"><span data-stu-id="5c84d-149">**Team privacy** - public or private</span></span>
- <span data-ttu-id="5c84d-150">**团队分类**-由 Office 365 组分类支持</span><span class="sxs-lookup"><span data-stu-id="5c84d-150">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="5c84d-151">**工作组成员设置**-选择工作组成员设置</span><span class="sxs-lookup"><span data-stu-id="5c84d-151">**Team member settings** - select team member settings</span></span>

## <a name="other-supported-changes-to-teams"></a><span data-ttu-id="5c84d-152">对团队的其他受支持的更改</span><span class="sxs-lookup"><span data-stu-id="5c84d-152">Other supported changes to teams</span></span>

- <span data-ttu-id="5c84d-153">**删除**-删除团队是团队和对应的 Office 365 组的软删除。</span><span class="sxs-lookup"><span data-stu-id="5c84d-153">**Delete** - Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span>  <span data-ttu-id="5c84d-154">若要还原错误删除的团队, 请按照[还原已删除的 Office 365 组](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="5c84d-154">To restore a mistakenly deleted team, follow the instructions at [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>
- <span data-ttu-id="5c84d-155">**存档**-存档团队将团队置于 Microsoft 团队内的只读模式。</span><span class="sxs-lookup"><span data-stu-id="5c84d-155">**Archive** - Archiving a team puts the team into read-only mode within Microsoft Teams.</span></span>  <span data-ttu-id="5c84d-156">作为管理员, 你可以通过管理门户代表你的组织存档和 unarchive 团队。</span><span class="sxs-lookup"><span data-stu-id="5c84d-156">As an admin, you can archive and unarchive teams on behalf of your organization via the admin portal.</span></span>


<span data-ttu-id="5c84d-157">将记录对团队所做的更改。</span><span class="sxs-lookup"><span data-stu-id="5c84d-157">The changes that you make to a team are logged.</span></span> <span data-ttu-id="5c84d-158">如果你要修改组设置 (更改名称、说明、照片、隐私、分类或团队成员), 这些更改将通过审核管道向你开放。</span><span class="sxs-lookup"><span data-stu-id="5c84d-158">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="5c84d-159">如果你要针对特定于团队的设置执行操作, 你的更改将在团队的常规频道中进行跟踪和设置。</span><span class="sxs-lookup"><span data-stu-id="5c84d-159">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="5c84d-160">疑难解答</span><span class="sxs-lookup"><span data-stu-id="5c84d-160">Troubleshooting</span></span>

<span data-ttu-id="5c84d-161">**问题: 团队概述网格中缺少团队**</span><span class="sxs-lookup"><span data-stu-id="5c84d-161">**Issue: Teams missing from the Team Overview Grid**</span></span>

<span data-ttu-id="5c84d-162">输入 Microsoft 团队管理中心时, 在 "团队" 选项\*\*\*\* 下的 "团队概述" 网格列表中缺少某些团队。</span><span class="sxs-lookup"><span data-stu-id="5c84d-162">When you enter the Microsoft Teams admin center, under the **Teams** option some of your teams are missing from the listing in the Teams Overview Grid.</span></span>

<span data-ttu-id="5c84d-163">**原因**: 当团队不正确 (或尚未) 被系统分析时, 将出现此问题, 这可能会导致它无法识别某个缺少的属性。</span><span class="sxs-lookup"><span data-stu-id="5c84d-163">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="5c84d-164">**解决方案: 通过 MS Graph 手动将属性设置为正确的值**</span><span class="sxs-lookup"><span data-stu-id="5c84d-164">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="5c84d-165">在查询中使用 **"[UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet 作为 "**ExternalDirectoryObjectId**" 属性替换 **{Groupid}** , 它可以通过 Exchange Online powershell 获得相关实际的 groupid。</span><span class="sxs-lookup"><span data-stu-id="5c84d-165">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="5c84d-166">Access [Graph 资源管理器](https://developer.microsoft.com/en-us/graph/graph-explorer)</span><span class="sxs-lookup"><span data-stu-id="5c84d-166">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span></span>

2. <span data-ttu-id="5c84d-167">在左侧菜单中登录到图形资源管理器</span><span class="sxs-lookup"><span data-stu-id="5c84d-167">Sign in to Graph Explorer on the left menu</span></span>

3. <span data-ttu-id="5c84d-168">将查询行更改为: PATCH > v 1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}</span><span class="sxs-lookup"><span data-stu-id="5c84d-168">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}</span></span>

4. <span data-ttu-id="5c84d-169">在请求正文中添加以下值: {"resourceProvisioningOptions": ["Team"]}</span><span class="sxs-lookup"><span data-stu-id="5c84d-169">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}</span></span>

5. <span data-ttu-id="5c84d-170">在右上角运行查询。</span><span class="sxs-lookup"><span data-stu-id="5c84d-170">Run the query on the top-right.</span></span>

6. <span data-ttu-id="5c84d-171">确认团队是否正确显示在 Microsoft 团队管理中心-团队概述</span><span class="sxs-lookup"><span data-stu-id="5c84d-171">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview</span></span>


## <a name="learn-more"></a><span data-ttu-id="5c84d-172">了解更多信息</span><span class="sxs-lookup"><span data-stu-id="5c84d-172">Learn more</span></span>

[<span data-ttu-id="5c84d-173">Microsoft 团队 cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="5c84d-173">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="5c84d-174">Microsoft 团队中的管理员角色</span><span class="sxs-lookup"><span data-stu-id="5c84d-174">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

