---
title: 管理 Microsoft 团队管理中心中的团队
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: 了解如何在 Microsoft 团队管理中心查看或更新团队。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4fea7081ee66cbd7b103f4292f577aaf5d841e11
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37571930"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="e2ebf-103">管理 Microsoft 团队管理中心中的团队</span><span class="sxs-lookup"><span data-stu-id="e2ebf-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="e2ebf-104">概述</span><span class="sxs-lookup"><span data-stu-id="e2ebf-104">Overview</span></span>

<span data-ttu-id="e2ebf-105">作为管理员，你可能需要查看或更新你的组织为协作设置的团队，或者你可能需要执行补救操作，例如分配 ownerless 团队的所有者。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-105">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="e2ebf-106">你可以通过 Microsoft 团队 PowerShell 模块和 Microsoft 团队管理中心管理组织中使用的团队。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="e2ebf-107">对于使用这两个工具集的完全管理功能，您应该确保已为您分配了下列角色之一：</span><span class="sxs-lookup"><span data-stu-id="e2ebf-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="e2ebf-108">全局管理员</span><span class="sxs-lookup"><span data-stu-id="e2ebf-108">Global Administrator</span></span>
- <span data-ttu-id="e2ebf-109">Teams 服务管理员</span><span class="sxs-lookup"><span data-stu-id="e2ebf-109">Teams Service Administrator</span></span>

<span data-ttu-id="e2ebf-110">可以在[使用 Microsoft 团队管理员角色管理团队](using-admin-roles.md)的团队中了解有关管理员角色的详细信息，还可以阅读有关如何使用 PowerShell cmdlet 来管理[Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)中的团队的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-110">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>

<span data-ttu-id="e2ebf-111">本文概述了 Microsoft 团队管理中心中的团队管理工具。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-111">This article provides an overview of the management tools for teams in the Microsoft Teams admin center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="e2ebf-112">团队概述网格</span><span class="sxs-lookup"><span data-stu-id="e2ebf-112">Teams overview grid</span></span>

<span data-ttu-id="e2ebf-113">团队的管理工具位于 Microsoft 团队管理中心的 "**团队**" 节点下。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="e2ebf-114">（在管理中心中，选择 "**团队** > **管理团队**"。）每个团队由 Office 365 组支持，并且此节点提供已在你的组织中启用了 Microsoft 团队的组的视图。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![团队概述网格的屏幕截图](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="e2ebf-116">网格显示以下属性：</span><span class="sxs-lookup"><span data-stu-id="e2ebf-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="e2ebf-117">**团队名称**</span><span class="sxs-lookup"><span data-stu-id="e2ebf-117">**Team name**</span></span>
- <span data-ttu-id="e2ebf-118">**频道**-组中所有频道的计数，包括默认的 "常规" 通道。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="e2ebf-119">**团队成员**-总用户数，包括来自租户的所有者、来宾和成员。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-119">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="e2ebf-120">**所有者**-此团队的所有者计数。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="e2ebf-121">**来宾**-属于此团队成员的 Azure ACTIVE Directory B2B 来宾用户的计数。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="e2ebf-122">**隐私**-支持的 Office 365 组的可见性/AccessType。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="e2ebf-123">**状态**-此团队的已存档或活动状态。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-123">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="e2ebf-124">了解有关存档[或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)中的存档团队的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-124">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="e2ebf-125">**说明**-支持的 Office 365 组的说明。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-125">**Description** - the description of the backing Office 365 group.</span></span>
- <span data-ttu-id="e2ebf-126">**分类**-分配给支持 Office 365 组的分类（如果在您的组织中使用）。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span> <span data-ttu-id="e2ebf-127">了解有关分类的详细信息，请参阅[为组织中的 Office 组创建分类](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="e2ebf-128">**GroupID** -支持 Office 365 组的独特的 groupid。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-128">**GroupID** - the unique GroupID of the backing Office 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="e2ebf-129">如果在网格中看不到所有这些属性，请单击 "**编辑列**" 图标。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-129">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="e2ebf-130">在 "**编辑列**" 窗格中，可以使用切换功能打开或关闭网格中的列。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-130">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="e2ebf-131">完成后，单击 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-131">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="e2ebf-132">插件</span><span class="sxs-lookup"><span data-stu-id="e2ebf-132">Add</span></span>

<span data-ttu-id="e2ebf-133">若要添加新团队，请单击 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-133">To add a new team, click **Add**.</span></span> <span data-ttu-id="e2ebf-134">在 "**添加新团队**" 窗格中，为团队提供名称和说明，设置是要使其成为私有团队还是公共团队，并设置分类。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-134">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

### <a name="edit"></a><span data-ttu-id="e2ebf-135">编辑</span><span class="sxs-lookup"><span data-stu-id="e2ebf-135">Edit</span></span>

<span data-ttu-id="e2ebf-136">若要编辑组和团队特定的设置，请通过单击团队名称左侧的团队进行选择，然后选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-136">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="e2ebf-137">存档</span><span class="sxs-lookup"><span data-stu-id="e2ebf-137">Archive</span></span>

<span data-ttu-id="e2ebf-138">您可以存档团队。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-138">You can archive a team.</span></span> <span data-ttu-id="e2ebf-139">存档团队会将团队置于团队内的只读模式。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-139">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="e2ebf-140">作为管理员，你可以在管理中心中代表你的组织存档和 unarchive 团队。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-140">As an admin, you can archive and unarchive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="e2ebf-141">删除</span><span class="sxs-lookup"><span data-stu-id="e2ebf-141">Delete</span></span>

<span data-ttu-id="e2ebf-142">删除团队是对团队和对应的 Office 365 组的软删除。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-142">Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span> <span data-ttu-id="e2ebf-143">若要还原错误删除的团队，请按照[还原已删除的 Office 365 组](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-143">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>

### <a name="search"></a><span data-ttu-id="e2ebf-144">搜索</span><span class="sxs-lookup"><span data-stu-id="e2ebf-144">Search</span></span>

<span data-ttu-id="e2ebf-145">搜索当前支持字符串 "始于" 并搜索 "**团队名称**" 字段。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-145">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="e2ebf-146">团队档案</span><span class="sxs-lookup"><span data-stu-id="e2ebf-146">Team profile</span></span>

<span data-ttu-id="e2ebf-147">通过单击团队名称，可以从 "主团队概述" 网格导航到任何团队的团队配置文件页面。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-147">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="e2ebf-148">"团队配置文件" 页面显示属于团队（及其支持的 Office 365 组）的成员、所有者和来宾以及团队的频道和设置。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-148">The team profile page shows the members, owners, and guests that belong to the team (and its backing Office 365 group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="e2ebf-149">从 "团队个人资料" 页面，您可以：</span><span class="sxs-lookup"><span data-stu-id="e2ebf-149">From the team profile page, you can:</span></span>

- <span data-ttu-id="e2ebf-150">添加或删除成员和所有者。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-150">Add or remove members and owners.</span></span>
- <span data-ttu-id="e2ebf-151">添加或删除频道（请注意，您不能删除 "常规频道"）。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-151">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="e2ebf-152">更改团队和组设置。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-152">Change team and group settings.</span></span>
 
![示例团队档案的屏幕截图](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="e2ebf-154">对团队进行更改</span><span class="sxs-lookup"><span data-stu-id="e2ebf-154">Making changes to teams</span></span>

<span data-ttu-id="e2ebf-155">在团队的配置文件页面上，您可以更改团队的以下元素：</span><span class="sxs-lookup"><span data-stu-id="e2ebf-155">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="e2ebf-156">**成员**-添加或删除成员以及提升或降级所有者。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-156">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="e2ebf-157">**频道**-添加新频道、编辑或删除现有频道。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-157">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="e2ebf-158">请记住，您不能删除默认的常规频道。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-158">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="e2ebf-159">**团队名称**</span><span class="sxs-lookup"><span data-stu-id="e2ebf-159">**Team name**</span></span>
- <span data-ttu-id="e2ebf-160">**说明**</span><span class="sxs-lookup"><span data-stu-id="e2ebf-160">**Description**</span></span>
- <span data-ttu-id="e2ebf-161">**隐私**-设置团队是公共的还是私有的。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-161">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="e2ebf-162">**分类**-您的 Office 365 组分类支持此功能。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-162">**Classification** - this is backed by your Office 365 group classifications.</span></span> <span data-ttu-id="e2ebf-163">选择 "**机密**"、"**高度机密**" 或 "**常规**"。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-163">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="e2ebf-164">**对话设置**-设置成员是否可以编辑和删除已发送的邮件。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-164">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="e2ebf-165">**频道设置**-设置成员是否可以创建新频道和编辑现有频道，以及添加、编辑和删除选项卡、连接器和应用。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-165">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="e2ebf-166">将记录对团队所做的更改。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-166">The changes that you make to a team are logged.</span></span> <span data-ttu-id="e2ebf-167">如果你要修改组设置（更改名称、说明、照片、隐私、分类或团队成员），则通过审核管道对这些更改进行了设置。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-167">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="e2ebf-168">如果你正在针对特定于团队的设置执行操作，你的更改将在团队的常规频道中进行跟踪和设置。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-168">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="e2ebf-169">疑难解答</span><span class="sxs-lookup"><span data-stu-id="e2ebf-169">Troubleshooting</span></span>

<span data-ttu-id="e2ebf-170">**问题：团队概述网格中缺少团队**</span><span class="sxs-lookup"><span data-stu-id="e2ebf-170">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="e2ebf-171">团队概述网格中的团队列表中缺少某些团队。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-171">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="e2ebf-172">**原因**：当团队不正确（或尚未）被系统分析时，将出现此问题，这可能会导致它无法识别某个缺少的属性。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-172">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="e2ebf-173">**解决方案：通过 MS Graph 手动将属性设置为正确的值**</span><span class="sxs-lookup"><span data-stu-id="e2ebf-173">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="e2ebf-174">在查询中使用 **"[UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet 作为 "**ExternalDirectoryObjectId**" 属性替换 **{Groupid}** ，它可以通过 Exchange Online powershell 获得相关实际的 groupid。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-174">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="e2ebf-175">Access [Graph 资源管理器](https://developer.microsoft.com/en-us/graph/graph-explorer)。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-175">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer).</span></span>

2. <span data-ttu-id="e2ebf-176">在左侧菜单中登录到图形资源管理器。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-176">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="e2ebf-177">将查询行更改为： PATCH > v 1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-177">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="e2ebf-178">在请求正文中添加以下值： {"resourceProvisioningOptions"： ["Team"]}。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-178">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="e2ebf-179">在右上角运行查询。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-179">Run the query on the top-right.</span></span>

6. <span data-ttu-id="e2ebf-180">确认团队是否正确显示在 Microsoft 团队管理中心-团队概述。</span><span class="sxs-lookup"><span data-stu-id="e2ebf-180">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="e2ebf-181">了解更多信息</span><span class="sxs-lookup"><span data-stu-id="e2ebf-181">Learn more</span></span>

- [<span data-ttu-id="e2ebf-182">团队 cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="e2ebf-182">Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="e2ebf-183">使用团队管理员角色管理团队</span><span class="sxs-lookup"><span data-stu-id="e2ebf-183">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="e2ebf-184">在 Teams 中规划生命周期管理</span><span class="sxs-lookup"><span data-stu-id="e2ebf-184">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)
