---
title: 管理 Microsoft 团队管理中心中的团队
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 03/08/2019
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: 了解如何查看或更新您的 Microsoft 团队管理中心中的团队。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2d2903e65e4ef4876f41d367ce961530020e775c
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32202728"
---
<a name="manage-teams-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="7193d-103">管理 Microsoft 团队管理中心中的团队</span><span class="sxs-lookup"><span data-stu-id="7193d-103">Manage teams in the Microsoft Teams admin center</span></span>
==========================================


## <a name="overview"></a><span data-ttu-id="7193d-104">概述</span><span class="sxs-lookup"><span data-stu-id="7193d-104">Overview</span></span>

<span data-ttu-id="7193d-105">作为一名 IT 管理员，您可能需要查看或更新您的组织已设置的协作，或您的团队可能需要执行修正操作，如分配无所有者团队的所有者。</span><span class="sxs-lookup"><span data-stu-id="7193d-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="7193d-106">您可以管理通过 Microsoft 团队 PowerShell 模块和 Microsoft 团队管理中心您组织中使用的团队。</span><span class="sxs-lookup"><span data-stu-id="7193d-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams admin center.</span></span> <span data-ttu-id="7193d-107">对于使用以下两个工具集的完整的管理功能，您应该确保您已分配下列角色之一：</span><span class="sxs-lookup"><span data-stu-id="7193d-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="7193d-108">全局管理员</span><span class="sxs-lookup"><span data-stu-id="7193d-108">Global Administrator</span></span>
- <span data-ttu-id="7193d-109">Teams 服务管理员</span><span class="sxs-lookup"><span data-stu-id="7193d-109">Teams Service Administrator</span></span>

<span data-ttu-id="7193d-110">您可以了解有关管理角色的团队中[使用的 Microsoft 团队管理角色，来管理团队](using-admin-roles.md)，并且您可以阅读更多有关如何使用 PowerShell cmdlet 进行管理[的 Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)中的团队。</span><span class="sxs-lookup"><span data-stu-id="7193d-110">You can learn more about admin roles in Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="7193d-111">本文概述了 Microsoft 团队管理中心中的团队的管理工具。</span><span class="sxs-lookup"><span data-stu-id="7193d-111">This article provides an overview of the management tools for teams in the Microsoft Teams admin center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="7193d-112">团队概述网格</span><span class="sxs-lookup"><span data-stu-id="7193d-112">Teams overview grid</span></span>

<span data-ttu-id="7193d-113">团队的管理工具是 Microsoft 团队管理中心中的**团队**节点下。</span><span class="sxs-lookup"><span data-stu-id="7193d-113">Management tools for teams are under the **Teams** node in the Microsoft Teams admin center.</span></span> <span data-ttu-id="7193d-114">(在管理中心中选择**团队** > **管理团队**。)此节点提供已 Microsoft 团队启用您的组织中的组的视图和每个工作组后盾 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="7193d-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

![团队概述网格](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="7193d-116">网格中显示以下属性：</span><span class="sxs-lookup"><span data-stu-id="7193d-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="7193d-117">**团队名称**</span><span class="sxs-lookup"><span data-stu-id="7193d-117">**Team name**</span></span>
- <span data-ttu-id="7193d-118">**通道**-团队，包括默认常规通道中的所有频道的计数。</span><span class="sxs-lookup"><span data-stu-id="7193d-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="7193d-119">**用户**的用户总数，包括所有者、 来宾和从租户的成员计数。</span><span class="sxs-lookup"><span data-stu-id="7193d-119">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="7193d-120">**所有者**-此团队的所有者的计数。</span><span class="sxs-lookup"><span data-stu-id="7193d-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="7193d-121">**来宾**-的 Azure Active Directory B2B 来宾用户属于此团队的成员计数。</span><span class="sxs-lookup"><span data-stu-id="7193d-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="7193d-122">**隐私**-备份 Office 365 组的可见性/AccessType。</span><span class="sxs-lookup"><span data-stu-id="7193d-122">**Privacy** - the Visibility/AccessType of the backing Office 365 group.</span></span>
- <span data-ttu-id="7193d-123">**状态**-已存档或此团队活动状态。</span><span class="sxs-lookup"><span data-stu-id="7193d-123">**Status** - the Archived or Active status for this team.</span></span>  <span data-ttu-id="7193d-124">了解有关存档[存档或还原团队](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7)中的团队。</span><span class="sxs-lookup"><span data-stu-id="7193d-124">Learn more about archiving teams in the [Archive or restore a team](https://support.office.com/article/archive-or-restore-a-team-dc161cfd-b328-440f-974b-5da5bd98b5a7).</span></span>
- <span data-ttu-id="7193d-125">**GroupID** -备份 Office 365 组的唯一 GroupID</span><span class="sxs-lookup"><span data-stu-id="7193d-125">**GroupID** - the unique GroupID of the backing Office 365 group</span></span>
- <span data-ttu-id="7193d-126">**分类**-分配给备份 Office 365 组的分类 （如果您的组织中使用）。</span><span class="sxs-lookup"><span data-stu-id="7193d-126">**Classification** - the classification (if used in your organization) assigned to the backing Office 365 group.</span></span>  <span data-ttu-id="7193d-127">了解有关在[创建您的组织中的 Office 组分类](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization)的分类。</span><span class="sxs-lookup"><span data-stu-id="7193d-127">Learn more about classifications at [Create classifications for Office groups in your organization](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell#create-classifications-for-office-groups-in-your-organization).</span></span>
- <span data-ttu-id="7193d-128">**说明**-备份 Office 365 组设置的说明</span><span class="sxs-lookup"><span data-stu-id="7193d-128">**Description** - the description set for the backing Office 365 group</span></span>

### <a name="search"></a><span data-ttu-id="7193d-129">搜索</span><span class="sxs-lookup"><span data-stu-id="7193d-129">Search</span></span>

<span data-ttu-id="7193d-130">搜索当前支持"始于"的字符串，并搜索**工作组名称**字段。</span><span class="sxs-lookup"><span data-stu-id="7193d-130">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="7193d-131">编辑</span><span class="sxs-lookup"><span data-stu-id="7193d-131">Edit</span></span>

<span data-ttu-id="7193d-132">您可以通过从网格中选择一个团队，然后选择**编辑**按钮编辑组和团队特定设置。</span><span class="sxs-lookup"><span data-stu-id="7193d-132">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![编辑团队](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="7193d-134">团队配置文件</span><span class="sxs-lookup"><span data-stu-id="7193d-134">Team profile</span></span>

<span data-ttu-id="7193d-135">您可以通过单击工作组名称来导航从主团队概述网格到任何团队的团队配置文件页。</span><span class="sxs-lookup"><span data-stu-id="7193d-135">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="7193d-136">团队配置文件页用于显示成员、 所有者和属于团队的来宾 (并将其备份 O365 组)，以及团队的通道和设置。</span><span class="sxs-lookup"><span data-stu-id="7193d-136">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="7193d-137">从工作组配置文件页，您可以：</span><span class="sxs-lookup"><span data-stu-id="7193d-137">From the team profile page, you can:</span></span>

- <span data-ttu-id="7193d-138">添加或删除成员和所有者。</span><span class="sxs-lookup"><span data-stu-id="7193d-138">Add or remove members and owners.</span></span>
- <span data-ttu-id="7193d-139">添加或删除通道 （请注意，不能删除常规通道）。</span><span class="sxs-lookup"><span data-stu-id="7193d-139">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="7193d-140">更新团队和组设置。</span><span class="sxs-lookup"><span data-stu-id="7193d-140">Update team and group settings.</span></span>
 
![团队配置文件](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="7193d-142">向工作组进行更改</span><span class="sxs-lookup"><span data-stu-id="7193d-142">Making changes to teams</span></span>

<span data-ttu-id="7193d-143">您可以更改团队的以下元素：</span><span class="sxs-lookup"><span data-stu-id="7193d-143">You can change the following elements of a team:</span></span>
- <span data-ttu-id="7193d-144">**团队中的用户**-您可以添加或删除成员，以及升级或降级所有者</span><span class="sxs-lookup"><span data-stu-id="7193d-144">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="7193d-145">**通道**-您可以添加新频道或删除现有通道。</span><span class="sxs-lookup"><span data-stu-id="7193d-145">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="7193d-146">无法删除默认的"常规"通道，并且一次创建您只能编辑的通道名称，不的说明。</span><span class="sxs-lookup"><span data-stu-id="7193d-146">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="7193d-147">**团队名称**</span><span class="sxs-lookup"><span data-stu-id="7193d-147">**Team name**</span></span>
- <span data-ttu-id="7193d-148">**团队说明**</span><span class="sxs-lookup"><span data-stu-id="7193d-148">**Team description**</span></span>
- <span data-ttu-id="7193d-149">**团队隐私**-公共或专用</span><span class="sxs-lookup"><span data-stu-id="7193d-149">**Team privacy** - public or private</span></span>
- <span data-ttu-id="7193d-150">**团队分类**-通过您的 Office 365 组分类备份</span><span class="sxs-lookup"><span data-stu-id="7193d-150">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="7193d-151">**团队成员设置**-选择团队成员设置</span><span class="sxs-lookup"><span data-stu-id="7193d-151">**Team member settings** - select team member settings</span></span>

## <a name="other-supported-changes-to-teams"></a><span data-ttu-id="7193d-152">向工作组其他受支持的更改</span><span class="sxs-lookup"><span data-stu-id="7193d-152">Other supported changes to teams</span></span>

- <span data-ttu-id="7193d-153">**删除**-删除团队是团队和相应的 Office 365 组软删除。</span><span class="sxs-lookup"><span data-stu-id="7193d-153">**Delete** - Deleting a team is a soft-delete of the team and corresponding Office 365 group.</span></span>  <span data-ttu-id="7193d-154">若要还原的错误地删除的工作组，按照在[还原已删除的 Office 365 组](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide)的说明。</span><span class="sxs-lookup"><span data-stu-id="7193d-154">To restore a mistakenly deleted team, follow the instructions at [Restore a deleted Office 365 Group](https://docs.microsoft.com/office365/admin/create-groups/restore-deleted-group?view=o365-worldwide).</span></span>
- <span data-ttu-id="7193d-155">**存档**的存档团队将置于只读模式中的 Microsoft 团队的团队。</span><span class="sxs-lookup"><span data-stu-id="7193d-155">**Archive** - Archiving a team puts the team into read-only mode within Microsoft Teams.</span></span>  <span data-ttu-id="7193d-156">作为一名管理员，您可以存档和代表通过管理门户组织 unarchive 团队。</span><span class="sxs-lookup"><span data-stu-id="7193d-156">As an admin, you can archive and unarchive teams on behalf of your organization via the admin portal.</span></span>


<span data-ttu-id="7193d-157">记录对团队所做的更改。</span><span class="sxs-lookup"><span data-stu-id="7193d-157">The changes that you make to a team are logged.</span></span> <span data-ttu-id="7193d-158">如果您要修改组设置 （更改名称、 说明、 照片、 隐私、 分类或工作组成员），您将这些更改的归功于您通过审核管道。</span><span class="sxs-lookup"><span data-stu-id="7193d-158">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="7193d-159">如果您执行的操作对特定于团队的设置，则将跟踪所做的更改，并将其团队的常规频道中属于您。</span><span class="sxs-lookup"><span data-stu-id="7193d-159">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="7193d-160">疑难解答</span><span class="sxs-lookup"><span data-stu-id="7193d-160">Troubleshooting</span></span>

<span data-ttu-id="7193d-161">**问题： 团队团队概述网格中缺少**</span><span class="sxs-lookup"><span data-stu-id="7193d-161">**Issue: Teams missing from the Team Overview Grid**</span></span>

<span data-ttu-id="7193d-162">输入的 Microsoft 团队管理中心时，**团队**选项下您的团队丢失了一些来自团队概述网格中的列表。</span><span class="sxs-lookup"><span data-stu-id="7193d-162">When you enter the Microsoft Teams admin center, under the **Teams** option some of your teams are missing from the listing in the Teams Overview Grid.</span></span>

<span data-ttu-id="7193d-163">**原因**： 该团队已正确 （或尚未） 分析系统这会导致它才能被识别缺少属性，则会发生此问题。</span><span class="sxs-lookup"><span data-stu-id="7193d-163">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="7193d-164">**解决方案： 手动将属性设置为正确值通过 MS 图**</span><span class="sxs-lookup"><span data-stu-id="7193d-164">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="7193d-165">替换为"**ExternalDirectoryObjectId**"属性 **"[Get UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet， **{groupid}** 中的查询的实际的 GroupId 问题，您可以通过 Exchange Online powershell 中，获取其。</span><span class="sxs-lookup"><span data-stu-id="7193d-165">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="7193d-166">访问[图表资源管理器](https://developer.microsoft.com/en-us/graph/graph-explorer)</span><span class="sxs-lookup"><span data-stu-id="7193d-166">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span></span>

2. <span data-ttu-id="7193d-167">在左侧菜单上登录到图资源管理器</span><span class="sxs-lookup"><span data-stu-id="7193d-167">Sign in to Graph Explorer on the left menu</span></span>

3. <span data-ttu-id="7193d-168">更改查询行： 修补程序 > v1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}</span><span class="sxs-lookup"><span data-stu-id="7193d-168">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}</span></span>

4. <span data-ttu-id="7193d-169">在请求正文中添加以下值: {"resourceProvisioningOptions":"团队"}</span><span class="sxs-lookup"><span data-stu-id="7193d-169">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}</span></span>

5. <span data-ttu-id="7193d-170">在右上角中运行查询。</span><span class="sxs-lookup"><span data-stu-id="7193d-170">Run the query on the top-right.</span></span>

6. <span data-ttu-id="7193d-171">确认工作组能够正确显示在 Microsoft 团队管理中心-团队概述 （英文）</span><span class="sxs-lookup"><span data-stu-id="7193d-171">Confirm the team appears correctly in the Microsoft Teams admin center - Team Overview</span></span>


## <a name="learn-more"></a><span data-ttu-id="7193d-172">了解更多信息</span><span class="sxs-lookup"><span data-stu-id="7193d-172">Learn more</span></span>

[<span data-ttu-id="7193d-173">Microsoft 团队 cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="7193d-173">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="7193d-174">管理员角色中的 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="7193d-174">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

