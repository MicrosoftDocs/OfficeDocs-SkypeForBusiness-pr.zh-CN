---
title: 管理团队中的 Microsoft 团队业务管理中心的 Skype
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/14/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: islubin
description: 了解如何查看或更新您的团队中的 Microsoft 团队业务管理中心的 Skype。
localization_priority: Normal
ms.custom:
- NewAdminCenter_Update
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1dbfddf2f9cfba12943b8b2e18326de1877e1de3
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2018
ms.locfileid: "25018820"
---
<a name="manage-teams-in-the-microsoft-teams--skype-for-business-admin-center"></a><span data-ttu-id="fbab4-103">管理团队中的 Microsoft 团队业务管理中心的 Skype</span><span class="sxs-lookup"><span data-stu-id="fbab4-103">Manage teams in the Microsoft Teams & Skype for Business Admin Center</span></span>
==========================================

## <a name="overview"></a><span data-ttu-id="fbab4-104">概述</span><span class="sxs-lookup"><span data-stu-id="fbab4-104">Overview</span></span>

<span data-ttu-id="fbab4-105">作为一名 IT 管理员，您可能需要查看或更新您的组织已设置的协作，或您的团队可能需要执行修正操作，如分配无所有者团队的所有者。</span><span class="sxs-lookup"><span data-stu-id="fbab4-105">As an IT admin, you may need to view or update the teams that your organization has set up for collaboration, or you might need to perform remediation actions such as assigning owners for ownerless teams.</span></span> <span data-ttu-id="fbab4-106">您可以管理业务管理中心的 Microsoft 团队 PowerShell 模块以及相关的 Microsoft 团队与 Skype 通过组织中使用的团队。</span><span class="sxs-lookup"><span data-stu-id="fbab4-106">You can manage the teams used in your organization through both the Microsoft Teams PowerShell module and the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="fbab4-107">对于使用以下两个工具集的完整的管理功能，您应该确保您已分配下列角色之一：</span><span class="sxs-lookup"><span data-stu-id="fbab4-107">For full administration capabilities using these two toolsets, you should make sure that you are assigned one of the following roles:</span></span>

- <span data-ttu-id="fbab4-108">全局管理员</span><span class="sxs-lookup"><span data-stu-id="fbab4-108">Global Administrator</span></span>
- <span data-ttu-id="fbab4-109">团队服务管理员</span><span class="sxs-lookup"><span data-stu-id="fbab4-109">Teams Service Administrator</span></span>

<span data-ttu-id="fbab4-110">您可以了解有关 Microsoft 团队中的管理角色的详细信息[此处](using-admin-roles.md)，您可以读取多有关如何使用 PowerShell cmdlet 进行管理[的 Microsoft 团队 cmdlet 参考](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps)中的团队。</span><span class="sxs-lookup"><span data-stu-id="fbab4-110">You can learn more about admin roles in Microsoft Teams [here](using-admin-roles.md), and you can read more about how to use the PowerShell cmdlets for managing teams in the [Microsoft Teams cmdlet reference](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps).</span></span>  

<span data-ttu-id="fbab4-111">本文概述了团队中的 Microsoft 团队业务管理中心的 Skype 的管理工具。</span><span class="sxs-lookup"><span data-stu-id="fbab4-111">This article provides an overview of the management tools for teams in the Microsoft Teams & Skype for Business Admin Center.</span></span>

## <a name="teams-overview-grid"></a><span data-ttu-id="fbab4-112">团队概述网格</span><span class="sxs-lookup"><span data-stu-id="fbab4-112">Teams overview grid</span></span>

<span data-ttu-id="fbab4-113">团队的管理工具是中的 Microsoft 团队 Skype 业务管理中心的**团队**节点下。</span><span class="sxs-lookup"><span data-stu-id="fbab4-113">Management tools for teams are under the **Teams** node in the Microsoft Teams & Skype for Business Admin Center.</span></span> <span data-ttu-id="fbab4-114">(在管理中心中选择**团队** > **管理团队**。)此节点提供的所有组的已启用团队的组织中的 Microsoft 的视图和每个工作组后盾 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="fbab4-114">(In the admin center, select **Teams** > **Manage teams**.) Each team is backed by an Office 365 group, and this node provides a view of all groups that have been Microsoft Teams-enabled in your organization.</span></span>

![团队概述网格](media/manage-teams-in-modern-portal-image1.png)  

<span data-ttu-id="fbab4-116">网格中显示以下属性：</span><span class="sxs-lookup"><span data-stu-id="fbab4-116">The grid displays the following properties:</span></span>

- <span data-ttu-id="fbab4-117">**团队名称**</span><span class="sxs-lookup"><span data-stu-id="fbab4-117">**Team name**</span></span>
- <span data-ttu-id="fbab4-118">**通道**-团队，包括默认常规通道中的所有频道的计数。</span><span class="sxs-lookup"><span data-stu-id="fbab4-118">**Channels** - a count of all channels in the team, including the default General channel.</span></span>
- <span data-ttu-id="fbab4-119">**用户**的用户总数，包括所有者、 来宾和从租户的成员计数。</span><span class="sxs-lookup"><span data-stu-id="fbab4-119">**Users** - a count of total users, including owners, guests, and members from your tenant.</span></span>
- <span data-ttu-id="fbab4-120">**所有者**-此团队的所有者的计数。</span><span class="sxs-lookup"><span data-stu-id="fbab4-120">**Owners** - a count of owners for this team.</span></span>
- <span data-ttu-id="fbab4-121">**来宾**-的 Azure Active Directory B2B 来宾用户属于此团队的成员计数。</span><span class="sxs-lookup"><span data-stu-id="fbab4-121">**Guests** - a count of Azure Active Directory B2B guest users who are members of this team.</span></span>
- <span data-ttu-id="fbab4-122">**隐私**-备份 Office 365 组的 AccessType。</span><span class="sxs-lookup"><span data-stu-id="fbab4-122">**Privacy** - the AccessType of the backing Office 365 group.</span></span>

### <a name="search"></a><span data-ttu-id="fbab4-123">搜索</span><span class="sxs-lookup"><span data-stu-id="fbab4-123">Search</span></span>

<span data-ttu-id="fbab4-124">搜索当前支持"始于"的字符串，并搜索**工作组名称**字段。</span><span class="sxs-lookup"><span data-stu-id="fbab4-124">Search currently supports the string "Begins with" and searches the **Team name** field.</span></span>

### <a name="edit"></a><span data-ttu-id="fbab4-125">编辑</span><span class="sxs-lookup"><span data-stu-id="fbab4-125">Edit</span></span>

<span data-ttu-id="fbab4-126">您可以通过从网格中选择一个团队，然后选择**编辑**按钮编辑组和团队特定设置。</span><span class="sxs-lookup"><span data-stu-id="fbab4-126">You can edit group and team-specific settings by selecting a team from the grid and then selecting the **Edit** button.</span></span>

![编辑团队](media/manage-teams-in-modern-portal-image2.png)

## <a name="team-profile"></a><span data-ttu-id="fbab4-128">团队配置文件</span><span class="sxs-lookup"><span data-stu-id="fbab4-128">Team profile</span></span>

<span data-ttu-id="fbab4-129">您可以通过单击工作组名称来导航从主团队概述网格到任何团队的团队配置文件页。</span><span class="sxs-lookup"><span data-stu-id="fbab4-129">You can navigate to the team profile page of any team from the main teams overview grid by clicking on the team name.</span></span> <span data-ttu-id="fbab4-130">团队配置文件页用于显示成员、 所有者和属于团队的来宾 (并将其备份 O365 组)，以及团队的通道和设置。</span><span class="sxs-lookup"><span data-stu-id="fbab4-130">The team profile page shows the members, owners, and guests that belong to the team (and its backing O365 Group), as well as the team’s channels and settings.</span></span> <span data-ttu-id="fbab4-131">从工作组配置文件页，您可以：</span><span class="sxs-lookup"><span data-stu-id="fbab4-131">From the team profile page, you can:</span></span>

- <span data-ttu-id="fbab4-132">添加或删除成员和所有者。</span><span class="sxs-lookup"><span data-stu-id="fbab4-132">Add or remove members and owners.</span></span>
- <span data-ttu-id="fbab4-133">添加或删除通道 （请注意，不能删除常规通道）。</span><span class="sxs-lookup"><span data-stu-id="fbab4-133">Add or remove channels (Note that you cannot remove the General channel).</span></span>
- <span data-ttu-id="fbab4-134">更新团队和组设置。</span><span class="sxs-lookup"><span data-stu-id="fbab4-134">Update team and group settings.</span></span>
 
![团队配置文件](media/manage-teams-in-modern-portal-image3.png)

## <a name="making-changes-to-teams"></a><span data-ttu-id="fbab4-136">向工作组进行更改</span><span class="sxs-lookup"><span data-stu-id="fbab4-136">Making changes to teams</span></span>

<span data-ttu-id="fbab4-137">您可以更改团队的以下元素：</span><span class="sxs-lookup"><span data-stu-id="fbab4-137">You can change the following elements of a team:</span></span>
- <span data-ttu-id="fbab4-138">**团队中的用户**-您可以添加或删除成员，以及升级或降级所有者</span><span class="sxs-lookup"><span data-stu-id="fbab4-138">**Users in the team** - you can add or remove members, and promote or demote owners</span></span>
- <span data-ttu-id="fbab4-139">**通道**-您可以添加新频道或删除现有通道。</span><span class="sxs-lookup"><span data-stu-id="fbab4-139">**Channels** - you can add new channels or remove existing channels.</span></span>  <span data-ttu-id="fbab4-140">无法删除默认的"常规"通道，并且一次创建您只能编辑的通道名称，不的说明。</span><span class="sxs-lookup"><span data-stu-id="fbab4-140">You cannot delete the default "General" channel, and once created you can only edit channel name, not description.</span></span>
- <span data-ttu-id="fbab4-141">**团队名称**</span><span class="sxs-lookup"><span data-stu-id="fbab4-141">**Team name**</span></span>
- <span data-ttu-id="fbab4-142">**团队说明**</span><span class="sxs-lookup"><span data-stu-id="fbab4-142">**Team description**</span></span>
- <span data-ttu-id="fbab4-143">**团队照片**</span><span class="sxs-lookup"><span data-stu-id="fbab4-143">**Team photo**</span></span>
- <span data-ttu-id="fbab4-144">**团队隐私**-公共或专用</span><span class="sxs-lookup"><span data-stu-id="fbab4-144">**Team privacy** - public or private</span></span>
- <span data-ttu-id="fbab4-145">**团队分类**-通过您的 Office 365 组分类备份</span><span class="sxs-lookup"><span data-stu-id="fbab4-145">**Team classification** - backed by your Office 365 group classifications</span></span>
- <span data-ttu-id="fbab4-146">**团队成员设置**-选择团队成员设置</span><span class="sxs-lookup"><span data-stu-id="fbab4-146">**Team member settings** - select team member settings</span></span>


<span data-ttu-id="fbab4-147">记录对团队所做的更改。</span><span class="sxs-lookup"><span data-stu-id="fbab4-147">The changes that you make to a team are logged.</span></span> <span data-ttu-id="fbab4-148">如果您要修改组设置 （更改名称、 说明、 照片、 隐私、 分类或工作组成员），您将这些更改的归功于您通过审核管道。</span><span class="sxs-lookup"><span data-stu-id="fbab4-148">If you are modifying group settings (changing the name, description, photo, privacy, classification, or team members), these changes will be attributed to you through the audit pipeline.</span></span> <span data-ttu-id="fbab4-149">如果您执行的操作对特定于团队的设置，则将跟踪所做的更改，并将其团队的常规频道中属于您。</span><span class="sxs-lookup"><span data-stu-id="fbab4-149">If you are performing actions against Teams-specific settings, your changes will be tracked and attributed to you in the general channel of the team.</span></span>


## <a name="learn-more"></a><span data-ttu-id="fbab4-150">了解更多信息</span><span class="sxs-lookup"><span data-stu-id="fbab4-150">Learn more</span></span>

[<span data-ttu-id="fbab4-151">Microsoft 团队 cmdlet 参考</span><span class="sxs-lookup"><span data-stu-id="fbab4-151">Microsoft Teams cmdlet reference</span></span>](https://docs.microsoft.com/en-us/powershell/teams/?view=teams-ps)  
[<span data-ttu-id="fbab4-152">管理员角色中的 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="fbab4-152">Admin roles in Microsoft Teams</span></span>](using-admin-roles.md)
<!--
[Plan for Teams Lifecycle Management](plan-for-teams-lifecycle-management.md)
-->

