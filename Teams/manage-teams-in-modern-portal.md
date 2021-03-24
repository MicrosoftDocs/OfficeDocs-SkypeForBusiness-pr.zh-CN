---
title: 在 Microsoft Teams 管理中心内管理团队
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: 了解如何在 Microsoft Teams 管理中心查看或更新组织为协作而设置的团队。
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6bf864fefd3ac60c7531bd339a5587c8f2f0dd72
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094232"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="1c416-103">在 Microsoft Teams 管理中心内管理团队</span><span class="sxs-lookup"><span data-stu-id="1c416-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="1c416-104">概述</span><span class="sxs-lookup"><span data-stu-id="1c416-104">Overview</span></span>

<span data-ttu-id="1c416-105">本文概述了 Microsoft Teams 管理中心的 Teams 管理工具。</span><span class="sxs-lookup"><span data-stu-id="1c416-105">This article provides an overview of the management tools for Teams in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="1c416-106">作为管理员，可能需要查看或更新组织为协作而设置的团队，或者可能需要执行补救措施，例如为无所有者团队分配所有者。</span><span class="sxs-lookup"><span data-stu-id="1c416-106">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="1c416-107">可以通过 Microsoft Teams PowerShell 模块和 Microsoft Teams 管理中心管理组织中使用的团队。</span><span class="sxs-lookup"><span data-stu-id="1c416-107">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="1c416-108">可以在 访问管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="1c416-108">You can access the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> <span data-ttu-id="1c416-109">对于使用这两个工具集的完整管理功能，应确保分配有以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="1c416-109">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="1c416-110">全局管理员</span><span class="sxs-lookup"><span data-stu-id="1c416-110">Global Administrator</span></span>
- <span data-ttu-id="1c416-111">Teams 服务管理员</span><span class="sxs-lookup"><span data-stu-id="1c416-111">Teams Service Administrator</span></span>

<span data-ttu-id="1c416-112">可以在使用 [Microsoft Teams](using-admin-roles.md)管理员角色管理 Teams 中详细了解 Teams 中的管理员角色，还可以在 Microsoft [Teams cmdlet](/powershell/teams/?view=teams-ps)参考中详细了解如何使用 PowerShell cmdlet 管理团队。</span><span class="sxs-lookup"><span data-stu-id="1c416-112">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](/powershell/teams/?view=teams-ps).</span></span>



## <a name="teams-overview-grid"></a><span data-ttu-id="1c416-113">Teams 概述网格</span><span class="sxs-lookup"><span data-stu-id="1c416-113">Teams overview grid</span></span>

<span data-ttu-id="1c416-114">团队管理工具位于 Microsoft Teams 管理中心的 **Teams** 节点下。</span><span class="sxs-lookup"><span data-stu-id="1c416-114">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="1c416-115"> (在管理中心中，选择 **"Teams** 管理团队"。) 每个团队都由  >  Microsoft 365 组支持，此节点提供组织中已启用 Microsoft Teams 的组的视图。</span><span class="sxs-lookup"><span data-stu-id="1c416-115">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by a Microsoft 365 Group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![Teams 概述网格的屏幕截图](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="1c416-117">网格显示以下属性：</span><span class="sxs-lookup"><span data-stu-id="1c416-117">The grid displays the following properties:</span></span>

- <span data-ttu-id="1c416-118">**团队名称**</span><span class="sxs-lookup"><span data-stu-id="1c416-118">**Team name**</span></span>
- <span data-ttu-id="1c416-119">**频道** - 团队中所有频道的计数，包括默认常规频道。</span><span class="sxs-lookup"><span data-stu-id="1c416-119">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="1c416-120">**团队成员** - 用户总数，包括租户中的所有者、来宾和成员。</span><span class="sxs-lookup"><span data-stu-id="1c416-120">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="1c416-121">**所有者** - 此团队的所有者计数。</span><span class="sxs-lookup"><span data-stu-id="1c416-121">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="1c416-122">**来宾** - 此团队成员的 Azure Active Directory B2B 来宾用户计数。</span><span class="sxs-lookup"><span data-stu-id="1c416-122">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="1c416-123">**隐私** - 支持 Microsoft 365 组的 Visibility/AccessType。</span><span class="sxs-lookup"><span data-stu-id="1c416-123">**Privacy** - the Visibility/AccessType of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="1c416-124">**状态** - 此团队的"已存档"或"活动"状态。</span><span class="sxs-lookup"><span data-stu-id="1c416-124">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="1c416-125">在存档或还原团队 [中详细了解如何存档团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。</span><span class="sxs-lookup"><span data-stu-id="1c416-125">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="1c416-126">**说明** - 支持 Microsoft 365 组的说明。</span><span class="sxs-lookup"><span data-stu-id="1c416-126">**Description** - the description of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="1c416-127">**分类** - 如果 (使用的分类) Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="1c416-127">**Classification** - the classification (if used in your organization) assigned to the backing Microsoft 365 group.</span></span> <span data-ttu-id="1c416-128">若要详细了解分类，请 [通过为组织的 Office 组创建分类](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="1c416-128">Learn more about classifications at [Create classifications for Office groups in your organization](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="1c416-129">GroupID - 支持 Microsoft 365 组的唯一 **GroupID。**</span><span class="sxs-lookup"><span data-stu-id="1c416-129">**GroupID** - the unique GroupID of the backing Microsoft 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="1c416-130">如果在网格中看不到所有这些属性，请单击"编辑列 **"** 图标。</span><span class="sxs-lookup"><span data-stu-id="1c416-130">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="1c416-131">在 **"编辑列** "窗格中，可以使用切换开关打开或关闭网格中的列。</span><span class="sxs-lookup"><span data-stu-id="1c416-131">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="1c416-132">完成后，单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="1c416-132">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="1c416-133">添加</span><span class="sxs-lookup"><span data-stu-id="1c416-133">Add</span></span>

<span data-ttu-id="1c416-134">若要添加新团队，请单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="1c416-134">To add a new team, click **Add**.</span></span> <span data-ttu-id="1c416-135">在 **"添加新团队"窗格中** ，为团队指定名称和说明，设置是将其设为专用团队还是公共团队，并设置分类。</span><span class="sxs-lookup"><span data-stu-id="1c416-135">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

> [!NOTE]
> <span data-ttu-id="1c416-136">与 Outlook 等其他客户端的体验不同，新创建的团队可以马上在 Teams 管理中心进行管理。</span><span class="sxs-lookup"><span data-stu-id="1c416-136">Newly created teams can be managed right away in the Teams Admin Center, unlike the experience in other clients like, Outlook.</span></span>

### <a name="edit"></a><span data-ttu-id="1c416-137">编辑</span><span class="sxs-lookup"><span data-stu-id="1c416-137">Edit</span></span>

<span data-ttu-id="1c416-138">若要编辑组和特定于团队的设置，请通过单击团队名称左侧选择团队，然后选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="1c416-138">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="1c416-139">存档</span><span class="sxs-lookup"><span data-stu-id="1c416-139">Archive</span></span>

<span data-ttu-id="1c416-140">可以存档团队。</span><span class="sxs-lookup"><span data-stu-id="1c416-140">You can archive a team.</span></span> <span data-ttu-id="1c416-141">存档团队会将团队置于 Teams 中的只读模式。</span><span class="sxs-lookup"><span data-stu-id="1c416-141">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="1c416-142">作为管理员，你可以代表组织在管理中心存档和取消存档团队。</span><span class="sxs-lookup"><span data-stu-id="1c416-142">As an admin, you can archive and un-archive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="1c416-143">删除</span><span class="sxs-lookup"><span data-stu-id="1c416-143">Delete</span></span>

<span data-ttu-id="1c416-144">删除团队是软删除团队和相应的 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="1c416-144">Deleting a team is a soft-delete of the team and corresponding Microsoft 365 group.</span></span> <span data-ttu-id="1c416-145">若要还原错误删除的团队，请按照还原已删除的 [组 中的说明进行操作](/microsoft-365/admin/create-groups/restore-deleted-group)。</span><span class="sxs-lookup"><span data-stu-id="1c416-145">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Group](/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="search"></a><span data-ttu-id="1c416-146">搜索</span><span class="sxs-lookup"><span data-stu-id="1c416-146">Search</span></span>

<span data-ttu-id="1c416-147">搜索当前支持字符串"开头为"，并搜索" **团队名称"** 字段。</span><span class="sxs-lookup"><span data-stu-id="1c416-147">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="1c416-148">团队配置文件</span><span class="sxs-lookup"><span data-stu-id="1c416-148">Team profile</span></span>

<span data-ttu-id="1c416-149">可以通过单击团队名称，从主团队概述网格导航到任何团队的团队配置文件页面。</span><span class="sxs-lookup"><span data-stu-id="1c416-149">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="1c416-150">团队配置文件页面显示属于团队 (及其支持 Microsoft 365 组) 的成员、所有者和来宾，以及团队的频道和设置。</span><span class="sxs-lookup"><span data-stu-id="1c416-150">The team profile page shows the members, owners, and guests that belong to the team (and its backing Microsoft 365 group), as well as the team's channels and settings.</span></span> <span data-ttu-id="1c416-151">在团队配置文件页中，可以：</span><span class="sxs-lookup"><span data-stu-id="1c416-151">From the team profile page, you can:</span></span>

- <span data-ttu-id="1c416-152">添加或删除成员和所有者。</span><span class="sxs-lookup"><span data-stu-id="1c416-152">Add or remove members and owners.</span></span>
- <span data-ttu-id="1c416-153">添加或删除 (请注意，不能删除常规频道) 。</span><span class="sxs-lookup"><span data-stu-id="1c416-153">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="1c416-154">更改团队和组设置。</span><span class="sxs-lookup"><span data-stu-id="1c416-154">Change team and group settings.</span></span>
 
![示例团队配置文件的屏幕截图](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="1c416-156">对团队进行更改</span><span class="sxs-lookup"><span data-stu-id="1c416-156">Making changes to teams</span></span>

<span data-ttu-id="1c416-157">在团队的个人资料页面上，可以更改团队的以下元素：</span><span class="sxs-lookup"><span data-stu-id="1c416-157">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="1c416-158">**成员** - 添加或删除成员以及提升或降级所有者。</span><span class="sxs-lookup"><span data-stu-id="1c416-158">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="1c416-159">**频道** - 添加新频道，以及编辑或删除现有频道。</span><span class="sxs-lookup"><span data-stu-id="1c416-159">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="1c416-160">请记住，不能删除默认"常规"频道。</span><span class="sxs-lookup"><span data-stu-id="1c416-160">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="1c416-161">**团队名称**</span><span class="sxs-lookup"><span data-stu-id="1c416-161">**Team name**</span></span>
- <span data-ttu-id="1c416-162">**说明**</span><span class="sxs-lookup"><span data-stu-id="1c416-162">**Description**</span></span>
- <span data-ttu-id="1c416-163">**隐私** - 设置团队是公共团队还是专用团队。</span><span class="sxs-lookup"><span data-stu-id="1c416-163">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="1c416-164">**分类** - 这受 Microsoft 365 组分类的支持。</span><span class="sxs-lookup"><span data-stu-id="1c416-164">**Classification** - this is backed by your Microsoft 365 group classifications.</span></span> <span data-ttu-id="1c416-165">选择 **"机密\*\*\*\*"、"高度机密"** 或"**常规"。**</span><span class="sxs-lookup"><span data-stu-id="1c416-165">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="1c416-166">**对话设置** - 设置成员是否可以编辑和删除已发送的消息。</span><span class="sxs-lookup"><span data-stu-id="1c416-166">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="1c416-167">**频道设置** - 设置成员是否可以创建新频道和编辑现有频道，以及添加、编辑和删除选项卡、连接器和应用。</span><span class="sxs-lookup"><span data-stu-id="1c416-167">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="1c416-168">将记录对团队所做的更改。</span><span class="sxs-lookup"><span data-stu-id="1c416-168">The changes that you make to a team are logged.</span></span> <span data-ttu-id="1c416-169">如果要修改组设置 (更改姓名、说明、照片、隐私、分类或) ，则更改会通过审核管道归你所有。</span><span class="sxs-lookup"><span data-stu-id="1c416-169">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="1c416-170">如果对特定于 Teams 的设置执行操作，则团队的"常规"频道中会跟踪所做的更改并归你所有。</span><span class="sxs-lookup"><span data-stu-id="1c416-170">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="1c416-171">疑难解答</span><span class="sxs-lookup"><span data-stu-id="1c416-171">Troubleshooting</span></span>

<span data-ttu-id="1c416-172">**问题：团队概述网格中缺少团队**</span><span class="sxs-lookup"><span data-stu-id="1c416-172">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="1c416-173">Teams 概述网格中的团队列表中缺少某些团队。</span><span class="sxs-lookup"><span data-stu-id="1c416-173">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="1c416-174">**原因**：当团队未正确 (或) 系统分析时，会出现此问题，这可能会导致缺少属性，从而无法识别它。</span><span class="sxs-lookup"><span data-stu-id="1c416-174">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="1c416-175">**解决方法：通过 MS Graph 手动将 属性设置为正确的值**</span><span class="sxs-lookup"><span data-stu-id="1c416-175">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="1c416-176">将"查询"中的 **{groupid}** 替换为 **"ExternalDirectoryObjectId"** 属性，以 **["Get-UnifiedGroup"cmdlet](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)** 作为"ExternalDirectoryObjectId"属性，通过 Exchange Online powershell 获取实际 GroupId。</span><span class="sxs-lookup"><span data-stu-id="1c416-176">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="1c416-177">访问 [图形资源管理器](https://developer.microsoft.com/graph/graph-explorer)。</span><span class="sxs-lookup"><span data-stu-id="1c416-177">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

2. <span data-ttu-id="1c416-178">登录到左侧菜单上的"图形资源管理器"。</span><span class="sxs-lookup"><span data-stu-id="1c416-178">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="1c416-179">将查询行更改为：patch > v1.0 https://graph.microsoft.com/v1.0/groups/{groupid} >。</span><span class="sxs-lookup"><span data-stu-id="1c416-179">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="1c416-180">在请求正文上添加以下值：{"resourceProvisioningOptions"：["Team"]}。</span><span class="sxs-lookup"><span data-stu-id="1c416-180">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="1c416-181">在右上方运行查询。</span><span class="sxs-lookup"><span data-stu-id="1c416-181">Run the query on the top-right.</span></span>

6. <span data-ttu-id="1c416-182">确认团队在 Microsoft Teams 管理中心 - 团队概述中正确显示。</span><span class="sxs-lookup"><span data-stu-id="1c416-182">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="1c416-183">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="1c416-183">Learn more</span></span>

- [<span data-ttu-id="1c416-184">Teams cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="1c416-184">Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="1c416-185">使用 Teams 管理员角色管理 Teams</span><span class="sxs-lookup"><span data-stu-id="1c416-185">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="1c416-186">在 Teams 中规划生命周期管理</span><span class="sxs-lookup"><span data-stu-id="1c416-186">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)