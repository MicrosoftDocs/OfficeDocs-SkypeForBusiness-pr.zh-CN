---
title: 分配团队所有者和中的 Microsoft 团队的成员
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中分配团队所有者和成员角色，包括创建团队的权限。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: a2fd9f611d616f368973ced432e886bf4ba9d8f5
ms.sourcegitcommit: ab4476127222d9f0aa9ee503132ff9bdabcaf9bc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/19/2018
ms.locfileid: "24021807"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="72013-103">分配团队所有者和中的 Microsoft 团队的成员</span><span class="sxs-lookup"><span data-stu-id="72013-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="72013-104">Microsoft 团队中有两个用户角色：**所有者**和**成员**。</span><span class="sxs-lookup"><span data-stu-id="72013-104">Within Microsoft Teams there are two user roles: **Owner** and **Member**.</span></span> <span data-ttu-id="72013-105">默认情况下，创建新的工作组的用户被授予所有者状态。</span><span class="sxs-lookup"><span data-stu-id="72013-105">By default, a user who creates a new team is granted the Owner status.</span></span> <span data-ttu-id="72013-106">如果团队是从现有 Office 365 组创建的，则将继承权限。</span><span class="sxs-lookup"><span data-stu-id="72013-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="72013-107">下表显示了所有者与成员之间的权限差异：</span><span class="sxs-lookup"><span data-stu-id="72013-107">The table below shows the difference in permissions between an owner and a member:</span></span>

|  |<span data-ttu-id="72013-108">团队所有者</span><span class="sxs-lookup"><span data-stu-id="72013-108">Team Owner</span></span>  |<span data-ttu-id="72013-109">团队成员</span><span class="sxs-lookup"><span data-stu-id="72013-109">Team Member</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="72013-110">**创建团队**</span><span class="sxs-lookup"><span data-stu-id="72013-110">**Create team**</span></span>     |<span data-ttu-id="72013-111">是</span><span class="sxs-lookup"><span data-stu-id="72013-111">Yes</span></span>        |<span data-ttu-id="72013-112">否</span><span class="sxs-lookup"><span data-stu-id="72013-112">No</span></span>         |
|<span data-ttu-id="72013-113">**离开团队**</span><span class="sxs-lookup"><span data-stu-id="72013-113">**Leave team**</span></span>     |<span data-ttu-id="72013-114">是</span><span class="sxs-lookup"><span data-stu-id="72013-114">Yes</span></span>         |<span data-ttu-id="72013-115">是</span><span class="sxs-lookup"><span data-stu-id="72013-115">Yes</span></span>         |
|<span data-ttu-id="72013-116">**编辑团队名称/说明**</span><span class="sxs-lookup"><span data-stu-id="72013-116">**Edit team name/description**</span></span>      |<span data-ttu-id="72013-117">是</span><span class="sxs-lookup"><span data-stu-id="72013-117">Yes</span></span>         |<span data-ttu-id="72013-118">否</span><span class="sxs-lookup"><span data-stu-id="72013-118">No</span></span>         |
|<span data-ttu-id="72013-119">**删除团队**</span><span class="sxs-lookup"><span data-stu-id="72013-119">**Delete team**</span></span>      |<span data-ttu-id="72013-120">是</span><span class="sxs-lookup"><span data-stu-id="72013-120">Yes</span></span>         |<span data-ttu-id="72013-121">否</span><span class="sxs-lookup"><span data-stu-id="72013-121">No</span></span>         |
|<span data-ttu-id="72013-122">**添加频道**</span><span class="sxs-lookup"><span data-stu-id="72013-122">**Add channel**</span></span>      |<span data-ttu-id="72013-123">是</span><span class="sxs-lookup"><span data-stu-id="72013-123">Yes</span></span>         |<span data-ttu-id="72013-124">是\*</span><span class="sxs-lookup"><span data-stu-id="72013-124">Yes\*</span></span>         |
|<span data-ttu-id="72013-125">**编辑频道名称/说明**</span><span class="sxs-lookup"><span data-stu-id="72013-125">**Edit channel name/description**</span></span>      |<span data-ttu-id="72013-126">是</span><span class="sxs-lookup"><span data-stu-id="72013-126">Yes</span></span>         |<span data-ttu-id="72013-127">是\*</span><span class="sxs-lookup"><span data-stu-id="72013-127">Yes\*</span></span>         |
|<span data-ttu-id="72013-128">**删除频道**</span><span class="sxs-lookup"><span data-stu-id="72013-128">**Delete channel**</span></span>      |<span data-ttu-id="72013-129">是</span><span class="sxs-lookup"><span data-stu-id="72013-129">Yes</span></span>         |<span data-ttu-id="72013-130">是\*</span><span class="sxs-lookup"><span data-stu-id="72013-130">Yes\*</span></span>         |
|<span data-ttu-id="72013-131">**添加成员**</span><span class="sxs-lookup"><span data-stu-id="72013-131">**Add members**</span></span>      |<span data-ttu-id="72013-132">是\*\*</span><span class="sxs-lookup"><span data-stu-id="72013-132">Yes\*\*</span></span>         |<span data-ttu-id="72013-133">否</span><span class="sxs-lookup"><span data-stu-id="72013-133">No</span></span>         |
|<span data-ttu-id="72013-134">**添加选项卡**</span><span class="sxs-lookup"><span data-stu-id="72013-134">**Add tabs**</span></span>      |<span data-ttu-id="72013-135">是</span><span class="sxs-lookup"><span data-stu-id="72013-135">Yes</span></span>         |<span data-ttu-id="72013-136">是\*</span><span class="sxs-lookup"><span data-stu-id="72013-136">Yes\*</span></span>         |
|<span data-ttu-id="72013-137">**添加连接器**</span><span class="sxs-lookup"><span data-stu-id="72013-137">**Add connectors**</span></span>      |<span data-ttu-id="72013-138">是</span><span class="sxs-lookup"><span data-stu-id="72013-138">Yes</span></span>         |<span data-ttu-id="72013-139">是\*</span><span class="sxs-lookup"><span data-stu-id="72013-139">Yes\*</span></span>         |
|<span data-ttu-id="72013-140">**添加聊天机器人**</span><span class="sxs-lookup"><span data-stu-id="72013-140">**Add bots**</span></span>      |<span data-ttu-id="72013-141">是</span><span class="sxs-lookup"><span data-stu-id="72013-141">Yes</span></span>         |<span data-ttu-id="72013-142">是\*</span><span class="sxs-lookup"><span data-stu-id="72013-142">Yes\*</span></span>         |
<span data-ttu-id="72013-143">\*这些项可以关闭所有者在团队级别中，在这种情况下成员不会对它们的访问。</span><span class="sxs-lookup"><span data-stu-id="72013-143">\* These items can be turned off by an owner at a team level, in which case members would not have access to them.</span></span>

<span data-ttu-id="72013-144">\*\*向团队添加成员后，所有者也可以将成员提升到所有者状态。</span><span class="sxs-lookup"><span data-stu-id="72013-144">\*\*After adding a member to a team, an Owner can also promote a Member to Owner status.</span></span> <span data-ttu-id="72013-145">此外，所有者也可以将自己的状态降级为成员。</span><span class="sxs-lookup"><span data-stu-id="72013-145">It is also possible for an Owner to demote their own status to a Member.</span></span>



> [!NOTE]
> <span data-ttu-id="72013-146">所有者可以在“查看团队”选项中将其他成员设为所有者。</span><span class="sxs-lookup"><span data-stu-id="72013-146">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="72013-147">一个团队最多可以有 100 个所有者。</span><span class="sxs-lookup"><span data-stu-id="72013-147">A team can have up to 100 owners.</span></span> <span data-ttu-id="72013-148">建议至少指定几个所有者以帮助管理团队；这样也可以防止当唯一的所有者离开贵组织时出现孤立的群组。</span><span class="sxs-lookup"><span data-stu-id="72013-148">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="72013-149">有关孤立群组的详细信息，请参阅[向孤立群组分配新所有者](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)。</span><span class="sxs-lookup"><span data-stu-id="72013-149">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="72013-150">创建团队的权限</span><span class="sxs-lookup"><span data-stu-id="72013-150">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="72013-151">默认情况下，在 Exchange Online 中有邮箱的所有用户都有权创建 Office 365 组，进而有权在 Microsoft Teams 中创建团队。</span><span class="sxs-lookup"><span data-stu-id="72013-151">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="72013-152">你可以通过向一组用户委派组创建和管理权限，更加严格地控制和限制新团队的创建，进而控制和限制新 Office 365 组的创建。</span><span class="sxs-lookup"><span data-stu-id="72013-152">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="72013-153">有关说明，请参阅[的管理可以创建 Office 365 组](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。</span><span class="sxs-lookup"><span data-stu-id="72013-153">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![决策点图标。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="72013-155">决策点</span><span class="sxs-lookup"><span data-stu-id="72013-155">Decision Point</span></span>         |<span data-ttu-id="72013-156">是否所有 Microsoft Teams 用户都将能够创建团队（建议）？</span><span class="sxs-lookup"><span data-stu-id="72013-156">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![后续步骤图标。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="72013-158">后续步骤</span><span class="sxs-lookup"><span data-stu-id="72013-158">Next Steps</span></span>         |<span data-ttu-id="72013-159">如果你需要限制可以创建团队的人员，请修改可以创建 Office 365 组的人员的默认权限</span><span class="sxs-lookup"><span data-stu-id="72013-159">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
