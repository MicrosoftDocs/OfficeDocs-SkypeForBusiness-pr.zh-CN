---
title: 管理团队中的 Microsoft 团队 & Business Admin Center 的 Skype
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/14/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: 了解如何查看或更新您的团队中的 Microsoft 团队 & Business Admin Center 的 Skype。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: df8e60f8a5d7aaf2638e1220baf1c41a59075ae0
ms.sourcegitcommit: 7f235c2c2cd350e8552a84ae1877b2d659a6aa53
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2019
ms.locfileid: "29706439"
---
<a name="manage-teams-in-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="c8bfa-103">管理团队中的 Microsoft 团队 & Business Admin Center 的 Skype</span><span class="sxs-lookup"><span data-stu-id="c8bfa-103">Manage teams in the Microsoft Teams & Skype for Business Admin Center</span></span>
==========================================

[!INCLUDE [new-feature-availability](includes/new-feature-availability.md)]

## <a name="overview"></a><span data-ttu-id="c8bfa-104">概述</span><span class="sxs-lookup"><span data-stu-id="c8bfa-104">Overview</span></span>

<span data-ttu-id="c8bfa-105">作为一名 IT 管理员，您可能需要查看或更新您的组织已设置的协作，或您的团队可能需要执行修正操作，如分配无所有者团队的所有者。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="c8bfa-106">您可以管理业务管理中心的通过 Microsoft 团队 PowerShell 模块和 Microsoft 团队 & Skype 您组织中使用的团队。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="c8bfa-107">对于使用以下两个工具集的完整的管理功能，您应该确保您已分配下列角色之一：</span><span class="sxs-lookup"><span data-stu-id="c8bfa-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="c8bfa-108">全局管理员</span><span class="sxs-lookup"><span data-stu-id="c8bfa-108">Global Administrator</span></span>
- <span data-ttu-id="c8bfa-109">Teams 服务管理员</span><span class="sxs-lookup"><span data-stu-id="c8bfa-109">Teams Service Administrator</span></span>

<span data-ttu-id="c8bfa-110">您还应确保您的帐户已被分配非试用团队许可证管理。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-110">You should also make sure that your account has been assigned a non-trial Teams license for management.</span></span> <span data-ttu-id="c8bfa-111">作为一个已知问题的一部分，您应该确保您的帐户具有只有**一个**管理角色分配。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-111">As part of a known issue, you should make sure that your account has only **one** admin role assigned.</span></span>  <span data-ttu-id="c8bfa-112">您可以了解有关 Microsoft 团队中[使用的 Microsoft 团队管理角色，来管理团队](using-admin-roles.md)，管理员角色的详细信息，并可以了解有关如何使用 PowerShell cmdlet 进行管理[的 Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/powershell/teams/?view=teams-ps)中的团队。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-112">You can learn more about admin roles in Microsoft Teams in [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="c8bfa-113">本文概述了团队中的 Microsoft 团队 & Business Admin Center 的 Skype 的管理工具。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-113">This article provides an overview of the management tools for teams in the Microsoft Teams & Skype for Business Admin Center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="c8bfa-114">团队概述网格</span><span class="sxs-lookup"><span data-stu-id="c8bfa-114">Teams overview grid</span></span>

<span data-ttu-id="c8bfa-115">团队的管理工具是 Microsoft 团队 & Skype 的业务管理中心中的**团队**节点下。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-115">Management tools for teams are under the **Teams** node in the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="c8bfa-116">(在管理中心中选择**团队** > **管理团队**。)此节点提供已 Microsoft 团队启用您的组织中的组的视图和每个工作组后盾 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-116">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of groups that have been Microsoft Teams-enabled in your organization.</span></span>

> [!NOTE]
> <span data-ttu-id="c8bfa-117">我们正在回填以前创建以确保它们将出现在此视图的团队。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-117">We are in the process of backfilling previously created Teams to ensure that they will show up in this view.</span></span>

![团队概述网格](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="c8bfa-119">网格中显示以下属性：</span><span class="sxs-lookup"><span data-stu-id="c8bfa-119">The grid displays the following properties:</span></span>

- <span data-ttu-id="c8bfa-120">**团队名称**</span><span class="sxs-lookup"><span data-stu-id="c8bfa-120">**Team name**</span></span>
- <span data-ttu-id="c8bfa-121">**通道**-团队，包括默认常规通道中的所有频道的计数。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-121">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="c8bfa-122">**用户**的用户总数，包括所有者、 来宾和从租户的成员计数。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-122">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="c8bfa-123">**所有者**-此团队的所有者的计数。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-123">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="c8bfa-124">**来宾**-的 Azure Active Directory B2B 来宾用户属于此团队的成员计数。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-124">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="c8bfa-125">**隐私**-备份 Office 365 组的 AccessType。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-125">**Privacy** - the AccessType of the backing Office 365 group.</span></span>

### <a name="search"></a><span data-ttu-id="c8bfa-126">搜索</span><span class="sxs-lookup"><span data-stu-id="c8bfa-126">Search</span></span>

<span data-ttu-id="c8bfa-127">搜索当前支持"始于"的字符串，并搜索**工作组名称**字段。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-127">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="c8bfa-128">编辑</span><span class="sxs-lookup"><span data-stu-id="c8bfa-128">Edit</span></span>

<span data-ttu-id="c8bfa-129">您可以通过从网格中选择一个团队，然后选择**编辑**按钮编辑组和团队特定设置。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-129">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![编辑团队](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="c8bfa-131">团队配置文件</span><span class="sxs-lookup"><span data-stu-id="c8bfa-131">Team profile</span></span>

<span data-ttu-id="c8bfa-132">您可以通过单击工作组名称来导航从主团队概述网格到任何团队的团队配置文件页。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-132">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="c8bfa-133">团队配置文件页用于显示成员、 所有者和属于团队的来宾 (并将其备份 O365 组)，以及团队的通道和设置。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-133">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="c8bfa-134">从工作组配置文件页，您可以：</span><span class="sxs-lookup"><span data-stu-id="c8bfa-134">From the team profile page, you can:</span></span>

- <span data-ttu-id="c8bfa-135">添加或删除成员和所有者。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-135">Add or remove members and owners.</span></span>
- <span data-ttu-id="c8bfa-136">添加或删除通道 （请注意，不能删除常规通道）。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-136">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="c8bfa-137">更新团队和组设置。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-137">Update team and group settings.</span></span>
 
![团队配置文件](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="c8bfa-139">向工作组进行更改</span><span class="sxs-lookup"><span data-stu-id="c8bfa-139">Making changes to teams</span></span>

<span data-ttu-id="c8bfa-140">您可以更改团队的以下元素：</span><span class="sxs-lookup"><span data-stu-id="c8bfa-140">You can change the following elements of a team:</span></span>
- <span data-ttu-id="c8bfa-141">**团队中的用户**-您可以添加或删除成员，以及升级或降级所有者</span><span class="sxs-lookup"><span data-stu-id="c8bfa-141">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="c8bfa-142">**通道**-您可以添加新频道或删除现有通道。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-142">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="c8bfa-143">无法删除默认的"常规"通道，并且一次创建您只能编辑的通道名称，不的说明。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-143">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="c8bfa-144">**团队名称**</span><span class="sxs-lookup"><span data-stu-id="c8bfa-144">**Team name**</span></span>
- <span data-ttu-id="c8bfa-145">**团队说明**</span><span class="sxs-lookup"><span data-stu-id="c8bfa-145">**Team description**</span></span>
- <span data-ttu-id="c8bfa-146">**团队隐私**-公共或专用</span><span class="sxs-lookup"><span data-stu-id="c8bfa-146">**Team privacy** - public or private</span></span>
- <span data-ttu-id="c8bfa-147">**团队分类**-通过您的 Office 365 组分类备份</span><span class="sxs-lookup"><span data-stu-id="c8bfa-147">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="c8bfa-148">**团队成员设置**-选择团队成员设置</span><span class="sxs-lookup"><span data-stu-id="c8bfa-148">**Team member settings** - select team member settings</span></span>


<span data-ttu-id="c8bfa-149">记录对团队所做的更改。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-149">The changes that you make to a team are logged.</span></span> <span data-ttu-id="c8bfa-150">如果您要修改组设置 （更改名称、 说明、 照片、 隐私、 分类或工作组成员），您将这些更改的归功于您通过审核管道。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-150">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="c8bfa-151">如果您执行的操作对特定于团队的设置，则将跟踪所做的更改，并将其团队的常规频道中属于您。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-151">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="c8bfa-152">故障排除</span><span class="sxs-lookup"><span data-stu-id="c8bfa-152">Troubleshooting</span></span>

<span data-ttu-id="c8bfa-153">**问题： 团队团队概述网格中缺少**</span><span class="sxs-lookup"><span data-stu-id="c8bfa-153">**Issue: Teams missing from the Team Overview Grid**</span></span>

<span data-ttu-id="c8bfa-154">当您输入的 Microsoft 团队 & Business Admin Center 的 Skype 时，**团队**选项下您的团队一些缺少团队概述网格中的列表。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-154">When you enter the Microsoft Teams & Skype for Business Admin Center, under the **Teams** option some of your teams are missing from the listing in the Teams Overview Grid.</span></span>

<span data-ttu-id="c8bfa-155">**原因**： 该团队已正确 （或尚未） 分析系统这会导致它才能被识别缺少属性，则会发生此问题。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-155">**Cause**: This issue occurs when the team was incorrectly (or not yet) profiled by the system which can lead to a missing property for it to be recognized.</span></span>

<span data-ttu-id="c8bfa-156">**解决方案： 手动将属性设置为正确值通过 MS 图**</span><span class="sxs-lookup"><span data-stu-id="c8bfa-156">**Resolution: Manually set the property to the correct value via MS Graph**</span></span>

<span data-ttu-id="c8bfa-157">替换为"**ExternalDirectoryObjectId**"属性 **"[Get UnifiedGroup](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet， **{groupid}** 中的查询的实际的 GroupId 问题，您可以通过 Exchange Online powershell 中，获取其。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-157">Replace **{groupid}** in the Query for the actual GroupId in question, which you can get via the Exchange Online powershell, with the **"[Get-UnifiedGroup](https://docs.microsoft.com/en-us/powershell/module/exchange/users-and-groups/get-unifiedgroup?view=exchange-ps)"** cmdlet, as the "**ExternalDirectoryObjectId**" attribute.</span></span>

1. <span data-ttu-id="c8bfa-158">访问[图表资源管理器](https://developer.microsoft.com/en-us/graph/graph-explorer)</span><span class="sxs-lookup"><span data-stu-id="c8bfa-158">Access [Graph Explorer](https://developer.microsoft.com/en-us/graph/graph-explorer)</span></span>

2. <span data-ttu-id="c8bfa-159">在左侧菜单上登录到图资源管理器</span><span class="sxs-lookup"><span data-stu-id="c8bfa-159">Sign in to Graph Explorer on the left-hand side menu</span></span>

3. <span data-ttu-id="c8bfa-160">更改查询行： 修补程序 > v1.0 >https://graph.microsoft.com/v1.0/groups/{groupid}</span><span class="sxs-lookup"><span data-stu-id="c8bfa-160">Change the query line to: PATCH > v1.0 > https://graph.microsoft.com/v1.0/groups/{groupid}</span></span>

4. <span data-ttu-id="c8bfa-161">在请求正文中添加以下值: {"resourceProvisioningOptions":"团队"}</span><span class="sxs-lookup"><span data-stu-id="c8bfa-161">Add the following value on the request body: {"resourceProvisioningOptions": ["Team"]}</span></span>

5. <span data-ttu-id="c8bfa-162">在右上角中运行查询。</span><span class="sxs-lookup"><span data-stu-id="c8bfa-162">Run the Query on the Top-Right.</span></span>

6. <span data-ttu-id="c8bfa-163">确认工作组正确显示回到上的 Microsoft 团队 & Business Admin Center-的 Skype 团队概述 （英文）</span><span class="sxs-lookup"><span data-stu-id="c8bfa-163">Confirm the team appears correctly back on the Microsoft Teams & Skype for Business Admin Center - Team Overview</span></span>


## <a name="learn-more"></a><span data-ttu-id="c8bfa-164">了解更多信息</span><span class="sxs-lookup"><span data-stu-id="c8bfa-164">Learn more</span></span>

[<span data-ttu-id="c8bfa-165">Microsoft 团队 cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="c8bfa-165">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="c8bfa-166">管理员角色中的 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="c8bfa-166">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

