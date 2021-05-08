---
title: 管理中心Microsoft Teams团队
author: SerdarSoysal
ms.author: serdars
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
search.appverid: MET150
ms.reviewer: islubin, jastark
description: 了解如何在管理中心查看或更新组织为协作Microsoft Teams团队。
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
ms.openlocfilehash: ea81ad854224e08142f9c87725d25176dcc60d44
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237538"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="47dee-103">管理中心Microsoft Teams团队</span><span class="sxs-lookup"><span data-stu-id="47dee-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="47dee-104">概述</span><span class="sxs-lookup"><span data-stu-id="47dee-104">Overview</span></span>

<span data-ttu-id="47dee-105">本文概述了 Teams 管理中心Microsoft Teams管理工具。</span><span class="sxs-lookup"><span data-stu-id="47dee-105">This article provides an overview of the management tools for Teams in the Microsoft Teams admin center.</span></span>

<span data-ttu-id="47dee-106">作为管理员，可能需要查看或更新组织为协作而设置的团队，或者可能需要执行补救措施，例如为无所有者团队分配所有者。</span><span class="sxs-lookup"><span data-stu-id="47dee-106">As an admin, you may need to view or update the teams that your organization set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="47dee-107">可以通过 PowerShell 模块和 Microsoft Teams 管理中心管理Microsoft Teams团队。</span><span class="sxs-lookup"><span data-stu-id="47dee-107">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="47dee-108">可以在 访问管理中心 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> 。</span><span class="sxs-lookup"><span data-stu-id="47dee-108">You can access the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span> <span data-ttu-id="47dee-109">对于使用这两个工具集的完整管理功能，应确保分配有以下角色之一：</span><span class="sxs-lookup"><span data-stu-id="47dee-109">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="47dee-110">全局管理员</span><span class="sxs-lookup"><span data-stu-id="47dee-110">Global Administrator</span></span>
- <span data-ttu-id="47dee-111">Teams 管理员</span><span class="sxs-lookup"><span data-stu-id="47dee-111">Teams Administrator</span></span>

<span data-ttu-id="47dee-112">可以在使用 Microsoft Teams 管理员角色管理[Teams](using-admin-roles.md)中详细了解 Teams 中的管理员角色，还可以在 Microsoft Teams cmdlet 参考中详细了解如何使用[PowerShell cmdlet 管理](/powershell/teams/?view=teams-ps)团队。</span><span class="sxs-lookup"><span data-stu-id="47dee-112">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](/powershell/teams/?view=teams-ps).</span></span>



## <a name="teams-overview-grid"></a><span data-ttu-id="47dee-113">Teams概述网格</span><span class="sxs-lookup"><span data-stu-id="47dee-113">Teams overview grid</span></span>

<span data-ttu-id="47dee-114">团队管理工具位于管理 **Teams** 节点Microsoft Teams下。</span><span class="sxs-lookup"><span data-stu-id="47dee-114">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="47dee-115"> (在管理中心中，选择 **"Teams** 管理团队") 每个团队都由 Microsoft 365 组支持，并且此节点提供组织中已启用Microsoft Teams组的  >  视图。</span><span class="sxs-lookup"><span data-stu-id="47dee-115">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by a Microsoft 365 Group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![屏幕截图：Teams概述网格](media/manage-teams-in-modern-portal-grid.png)  

<span data-ttu-id="47dee-117">网格显示以下属性：</span><span class="sxs-lookup"><span data-stu-id="47dee-117">The grid displays the following properties:</span></span>

- <span data-ttu-id="47dee-118">**团队名称**</span><span class="sxs-lookup"><span data-stu-id="47dee-118">**Team name**</span></span>
- <span data-ttu-id="47dee-119">**频道** - 团队中所有频道的计数，包括默认常规频道。</span><span class="sxs-lookup"><span data-stu-id="47dee-119">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="47dee-120">**团队成员** - 用户总数，包括租户中的所有者、来宾和成员。</span><span class="sxs-lookup"><span data-stu-id="47dee-120">**Team members** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="47dee-121">**所有者** - 此团队的所有者计数。</span><span class="sxs-lookup"><span data-stu-id="47dee-121">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="47dee-122">**来宾**- Azure Active Directory B2B 来宾用户的计数。</span><span class="sxs-lookup"><span data-stu-id="47dee-122">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="47dee-123">**隐私**- 支持组组的 Visibility/Accesstype Microsoft 365类型。</span><span class="sxs-lookup"><span data-stu-id="47dee-123">**Privacy** - the Visibility/AccessType of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="47dee-124">**状态** - 此团队的"已存档"或"活动"状态。</span><span class="sxs-lookup"><span data-stu-id="47dee-124">**Status** - the Archived or Active status for this team.</span></span> <span data-ttu-id="47dee-125">在存档或还原团队 [中详细了解如何存档团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)。</span><span class="sxs-lookup"><span data-stu-id="47dee-125">Learn more about archiving teams in [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="47dee-126">**说明**- 备份组Microsoft 365说明。</span><span class="sxs-lookup"><span data-stu-id="47dee-126">**Description** - the description of the backing Microsoft 365 group.</span></span>
- <span data-ttu-id="47dee-127">**分类**- 分类 (在组织中使用的分类) 分配给后备组Microsoft 365组。</span><span class="sxs-lookup"><span data-stu-id="47dee-127">**Classification** - the classification (if used in your organization) assigned to the backing Microsoft 365 group.</span></span> <span data-ttu-id="47dee-128">若要详细了解分类，请[通过为Office组创建分类](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="47dee-128">Learn more about classifications at [Create classifications for Office groups in your organization](/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="47dee-129">**GroupID** - 备份组的唯Microsoft 365 ID。</span><span class="sxs-lookup"><span data-stu-id="47dee-129">**GroupID** - the unique GroupID of the backing Microsoft 365 group.</span></span>

> [!NOTE]
> <span data-ttu-id="47dee-130">如果在网格中看不到所有这些属性，请单击"编辑列 **"** 图标。</span><span class="sxs-lookup"><span data-stu-id="47dee-130">If you don't see all these properties in the grid, click the **Edit columns** icon.</span></span> <span data-ttu-id="47dee-131">在 **"编辑列** "窗格中，可以使用切换开关打开或关闭网格中的列。</span><span class="sxs-lookup"><span data-stu-id="47dee-131">In the **Edit columns** pane, you can use the toggles to turn on or turn off columns in the grid.</span></span> <span data-ttu-id="47dee-132">完成后，单击"应用 **"。**</span><span class="sxs-lookup"><span data-stu-id="47dee-132">When you're finished, click **Apply**.</span></span>

### <a name="add"></a><span data-ttu-id="47dee-133">添加</span><span class="sxs-lookup"><span data-stu-id="47dee-133">Add</span></span>

<span data-ttu-id="47dee-134">若要添加新团队，请单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="47dee-134">To add a new team, click **Add**.</span></span> <span data-ttu-id="47dee-135">在 **"添加新团队"窗格中** ，为团队指定名称和说明，设置是将其设为专用团队还是公共团队，并设置分类。</span><span class="sxs-lookup"><span data-stu-id="47dee-135">In the **Add a new team** pane, give the team a name and description, set whether you want to make it a private or public team, and set the classification.</span></span>

> [!NOTE]
> <span data-ttu-id="47dee-136">新创建的团队可以在管理中心内Teams管理，不同于其他客户端（例如，Outlook）。</span><span class="sxs-lookup"><span data-stu-id="47dee-136">Newly created teams can be managed right away in the Teams Admin Center, unlike the experience in other clients like, Outlook.</span></span>

### <a name="edit"></a><span data-ttu-id="47dee-137">编辑</span><span class="sxs-lookup"><span data-stu-id="47dee-137">Edit</span></span>

<span data-ttu-id="47dee-138">若要编辑组和特定于团队的设置，请通过单击团队名称左侧选择团队，然后选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="47dee-138">To edit group and team-specific settings, select the team by clicking to the left of the team name, and then select **Edit**.</span></span>

### <a name="archive"></a><span data-ttu-id="47dee-139">存档</span><span class="sxs-lookup"><span data-stu-id="47dee-139">Archive</span></span>

<span data-ttu-id="47dee-140">可以存档团队。</span><span class="sxs-lookup"><span data-stu-id="47dee-140">You can archive a team.</span></span> <span data-ttu-id="47dee-141">存档团队会将团队置于只读模式，Teams。</span><span class="sxs-lookup"><span data-stu-id="47dee-141">Archiving a team puts the team into read-only mode within Teams.</span></span> <span data-ttu-id="47dee-142">作为管理员，你可以代表组织在管理中心存档和取消存档团队。</span><span class="sxs-lookup"><span data-stu-id="47dee-142">As an admin, you can archive and un-archive teams on behalf of your organization in the admin center.</span></span> 

### <a name="delete"></a><span data-ttu-id="47dee-143">删除</span><span class="sxs-lookup"><span data-stu-id="47dee-143">Delete</span></span>

<span data-ttu-id="47dee-144">删除团队是软删除团队和相应的Microsoft 365组。</span><span class="sxs-lookup"><span data-stu-id="47dee-144">Deleting a team is a soft-delete of the team and corresponding Microsoft 365 group.</span></span> <span data-ttu-id="47dee-145">若要还原错误删除的团队，请按照还原已删除的 [组 中的说明进行操作](/microsoft-365/admin/create-groups/restore-deleted-group)。</span><span class="sxs-lookup"><span data-stu-id="47dee-145">To restore a mistakenly deleted team, follow the instructions in [Restore a deleted Group](/microsoft-365/admin/create-groups/restore-deleted-group).</span></span>

### <a name="search"></a><span data-ttu-id="47dee-146">搜索</span><span class="sxs-lookup"><span data-stu-id="47dee-146">Search</span></span>

<span data-ttu-id="47dee-147">搜索当前支持字符串"开头为"，并搜索" **团队名称"** 字段。</span><span class="sxs-lookup"><span data-stu-id="47dee-147">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

## <a name="team-profile"></a><span data-ttu-id="47dee-148">团队配置文件</span><span class="sxs-lookup"><span data-stu-id="47dee-148">Team profile</span></span>

<span data-ttu-id="47dee-149">可以通过单击团队名称，从主团队概述网格导航到任何团队的团队配置文件页面。</span><span class="sxs-lookup"><span data-stu-id="47dee-149">You can navigate to the team profile page of any team from the main teams overview grid by clicking  the team name.</span></span> <span data-ttu-id="47dee-150">团队配置文件页面显示属于团队组的成员、所有者和来宾 (及其Microsoft 365组) 以及团队的频道和设置。</span><span class="sxs-lookup"><span data-stu-id="47dee-150">The team profile page shows the members, owners, and guests that belong to the team (and its backing Microsoft 365 group), as well as the team's channels and settings.</span></span> <span data-ttu-id="47dee-151">在团队配置文件页中，可以：</span><span class="sxs-lookup"><span data-stu-id="47dee-151">From the team profile page, you can:</span></span>

- <span data-ttu-id="47dee-152">添加或删除成员和所有者。</span><span class="sxs-lookup"><span data-stu-id="47dee-152">Add or remove members and owners.</span></span>
- <span data-ttu-id="47dee-153">添加或删除 (请注意，不能删除常规频道) 。</span><span class="sxs-lookup"><span data-stu-id="47dee-153">Add or remove channels (note that you can't remove the General channel).</span></span>
- <span data-ttu-id="47dee-154">更改团队和组设置。</span><span class="sxs-lookup"><span data-stu-id="47dee-154">Change team and group settings.</span></span>
 
![示例团队配置文件的屏幕截图](media/manage-teams-in-modern-portal-team-profile-page.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="47dee-156">对团队进行更改</span><span class="sxs-lookup"><span data-stu-id="47dee-156">Making changes to teams</span></span>

<span data-ttu-id="47dee-157">在团队的个人资料页面上，可以更改团队的以下元素：</span><span class="sxs-lookup"><span data-stu-id="47dee-157">On the team's profile page, you can change the following elements of a team:</span></span>

- <span data-ttu-id="47dee-158">**成员** - 添加或删除成员以及提升或降级所有者。</span><span class="sxs-lookup"><span data-stu-id="47dee-158">**Members** - add or remove members and promote or demote owners.</span></span>
- <span data-ttu-id="47dee-159">**频道** - 添加新频道，以及编辑或删除现有频道。</span><span class="sxs-lookup"><span data-stu-id="47dee-159">**Channels** - add new channels, and edit or remove existing channels.</span></span> <span data-ttu-id="47dee-160">请记住，不能删除默认"常规"频道。</span><span class="sxs-lookup"><span data-stu-id="47dee-160">Remember that you can't delete the default General channel.</span></span>
- <span data-ttu-id="47dee-161">**团队名称**</span><span class="sxs-lookup"><span data-stu-id="47dee-161">**Team name**</span></span>
- <span data-ttu-id="47dee-162">**说明**</span><span class="sxs-lookup"><span data-stu-id="47dee-162">**Description**</span></span>
- <span data-ttu-id="47dee-163">**隐私** - 设置团队是公共团队还是专用团队。</span><span class="sxs-lookup"><span data-stu-id="47dee-163">**Privacy** - set whether the team is public or private.</span></span>
- <span data-ttu-id="47dee-164">**分类**- 这由组Microsoft 365支持。</span><span class="sxs-lookup"><span data-stu-id="47dee-164">**Classification** - this is backed by your Microsoft 365 group classifications.</span></span> <span data-ttu-id="47dee-165">选择 **"机密\*\*\*\*"、"高度机密"** 或"**常规"。**</span><span class="sxs-lookup"><span data-stu-id="47dee-165">Choose **Confidential**, **Highly Confidential**, or **General**.</span></span>
- <span data-ttu-id="47dee-166">**对话设置** - 设置成员是否可以编辑和删除已发送的消息。</span><span class="sxs-lookup"><span data-stu-id="47dee-166">**Conversations settings** - set whether members can edit and delete sent messages.</span></span>
- <span data-ttu-id="47dee-167">**频道设置** - 设置成员是否可以创建新频道和编辑现有频道，以及添加、编辑和删除选项卡、连接器和应用。</span><span class="sxs-lookup"><span data-stu-id="47dee-167">**Channels settings** - set whether members can create new channels and edit existing ones, and add, edit, and remove tabs, connectors, and apps.</span></span>

<span data-ttu-id="47dee-168">将记录对团队所做的更改。</span><span class="sxs-lookup"><span data-stu-id="47dee-168">The changes that you make to a team are logged.</span></span> <span data-ttu-id="47dee-169">如果要修改组设置 (更改姓名、说明、照片、隐私、分类或) ，则更改会通过审核管道归你所有。</span><span class="sxs-lookup"><span data-stu-id="47dee-169">If you're modifying group settings (changing the name, description, photo, privacy, classification, or team members), the changes are attributed to you through the audit pipeline.</span></span> <span data-ttu-id="47dee-170">如果针对特定设置Teams操作，则团队的"常规"频道中会跟踪所做的更改并归你所有。</span><span class="sxs-lookup"><span data-stu-id="47dee-170">If you're performing actions against Teams-specific settings, your changes are tracked and attributed to you in the General channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="47dee-171">疑难解答</span><span class="sxs-lookup"><span data-stu-id="47dee-171">Troubleshooting</span></span>

<span data-ttu-id="47dee-172">**问题：Teams概述网格中缺少**</span><span class="sxs-lookup"><span data-stu-id="47dee-172">**Issue: Teams missing from the Team overview grid**</span></span>

<span data-ttu-id="47dee-173">在"概述"网格中的团队列表中，缺少Teams团队。</span><span class="sxs-lookup"><span data-stu-id="47dee-173">Some of your teams are missing from the list of teams in the Teams overview grid.</span></span>

<span data-ttu-id="47dee-174">**原因**：当团队未正确 (或) 系统分析时，会出现此问题，这可能会导致缺少属性，从而无法识别它。</span><span class="sxs-lookup"><span data-stu-id="47dee-174">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="47dee-175">**解决方法：通过 MS Graph 手动将 属性设置为正确的Graph**</span><span class="sxs-lookup"><span data-stu-id="47dee-175">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="47dee-176">将"查询"中的 **{groupid}** 替换为 **"ExternalDirectoryObjectId"** 属性（可通过 Exchange Online powershell 获取的实际 GroupId），将 **["Get-UnifiedGroup"](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)** cmdlet 替换为 " ExternalDirectoryObjectId"属性。</span><span class="sxs-lookup"><span data-stu-id="47dee-176">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="47dee-177">访问[Graph 资源管理器](https://developer.microsoft.com/graph/graph-explorer)。</span><span class="sxs-lookup"><span data-stu-id="47dee-177">Access [Graph Explorer](https://developer.microsoft.com/graph/graph-explorer).</span></span>

2. <span data-ttu-id="47dee-178">登录到左侧Graph资源管理器"。</span><span class="sxs-lookup"><span data-stu-id="47dee-178">Sign in to Graph Explorer on the left menu.</span></span>

3. <span data-ttu-id="47dee-179">将查询行更改为：patch > v1.0 https://graph.microsoft.com/v1.0/groups/{groupid} >。</span><span class="sxs-lookup"><span data-stu-id="47dee-179">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}.</span></span>

4. <span data-ttu-id="47dee-180">在请求正文上添加以下值：{"resourceProvisioningOptions"：["Team"]}。</span><span class="sxs-lookup"><span data-stu-id="47dee-180">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}.</span></span>

5. <span data-ttu-id="47dee-181">在右上方运行查询。</span><span class="sxs-lookup"><span data-stu-id="47dee-181">Run the query on the top-right.</span></span>

6. <span data-ttu-id="47dee-182">确认团队正确显示在"Microsoft Teams中心 - 团队概述"中。</span><span class="sxs-lookup"><span data-stu-id="47dee-182">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview.</span></span>

## <a name="learn-more"></a><span data-ttu-id="47dee-183">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="47dee-183">Learn more</span></span>

- [<span data-ttu-id="47dee-184">Teams cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="47dee-184">Teams cmdlet reference</span></span>](/powershell/teams/?view=teams-ps)  
- [<span data-ttu-id="47dee-185">使用Teams管理员角色来管理Teams</span><span class="sxs-lookup"><span data-stu-id="47dee-185">Use Teams administrator roles to manage Teams</span></span>](using-admin-roles.md)
- [<span data-ttu-id="47dee-186">在 Teams 中规划生命周期管理</span><span class="sxs-lookup"><span data-stu-id="47dee-186">Plan for lifecycle management in Teams</span></span>](plan-teams-lifecycle.md)