---
title: 在 Microsoft Teams 中分配团队所有者和成员
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/27/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中分配团队所有者和成员角色，包括创建团队的权限。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 0c7343f294f18d5aaacf01059459524cdd2700a2
ms.sourcegitcommit: bc2b227b4ac0a9521993f808a1361b4f9bc7faad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/14/2019
ms.locfileid: "30569955"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="a2e0c-103">在 Microsoft Teams 中分配团队所有者和成员</span><span class="sxs-lookup"><span data-stu-id="a2e0c-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="a2e0c-104">Microsoft 团队中有两个用户角色：**所有者**和**成员**。</span><span class="sxs-lookup"><span data-stu-id="a2e0c-104">Within Microsoft Teams there are two user roles: **Owner** and **Member**.</span></span> <span data-ttu-id="a2e0c-105">默认情况下，创建新的工作组的用户被授予所有者状态。</span><span class="sxs-lookup"><span data-stu-id="a2e0c-105">By default, a user who creates a new team is granted the Owner status.</span></span> <span data-ttu-id="a2e0c-106">如果团队是从现有 Office 365 组创建的，则将继承权限。</span><span class="sxs-lookup"><span data-stu-id="a2e0c-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="a2e0c-107">下表显示在权限所有者和某个成员之间的差异。</span><span class="sxs-lookup"><span data-stu-id="a2e0c-107">The table below shows the difference in permissions between an owner and a member.</span></span>


|                                   | <span data-ttu-id="a2e0c-108">团队所有者</span><span class="sxs-lookup"><span data-stu-id="a2e0c-108">Team Owner</span></span> | <span data-ttu-id="a2e0c-109">团队成员</span><span class="sxs-lookup"><span data-stu-id="a2e0c-109">Team Member</span></span> |
|-----------------------------------|------------|-------------|
|          <span data-ttu-id="a2e0c-110">**创建团队**</span><span class="sxs-lookup"><span data-stu-id="a2e0c-110">**Create team**</span></span>          |    <span data-ttu-id="a2e0c-111">是<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="a2e0c-111">Yes<sup>1</sup></span></span>     |     <span data-ttu-id="a2e0c-112">否</span><span class="sxs-lookup"><span data-stu-id="a2e0c-112">No</span></span>      |
|          <span data-ttu-id="a2e0c-113">**离开团队**</span><span class="sxs-lookup"><span data-stu-id="a2e0c-113">**Leave team**</span></span>           |    <span data-ttu-id="a2e0c-114">是</span><span class="sxs-lookup"><span data-stu-id="a2e0c-114">Yes</span></span>     |     <span data-ttu-id="a2e0c-115">是</span><span class="sxs-lookup"><span data-stu-id="a2e0c-115">Yes</span></span>     |
|  <span data-ttu-id="a2e0c-116">**编辑团队名称/说明**</span><span class="sxs-lookup"><span data-stu-id="a2e0c-116">**Edit team name/description**</span></span>   |    <span data-ttu-id="a2e0c-117">是</span><span class="sxs-lookup"><span data-stu-id="a2e0c-117">Yes</span></span>     |     <span data-ttu-id="a2e0c-118">否</span><span class="sxs-lookup"><span data-stu-id="a2e0c-118">No</span></span>      |
|          <span data-ttu-id="a2e0c-119">**删除团队**</span><span class="sxs-lookup"><span data-stu-id="a2e0c-119">**Delete team**</span></span>          |    <span data-ttu-id="a2e0c-120">是</span><span class="sxs-lookup"><span data-stu-id="a2e0c-120">Yes</span></span>     |     <span data-ttu-id="a2e0c-121">否</span><span class="sxs-lookup"><span data-stu-id="a2e0c-121">No</span></span>      |
|          <span data-ttu-id="a2e0c-122">**添加频道**</span><span class="sxs-lookup"><span data-stu-id="a2e0c-122">**Add channel**</span></span>          |    <span data-ttu-id="a2e0c-123">是</span><span class="sxs-lookup"><span data-stu-id="a2e0c-123">Yes</span></span>     |    <span data-ttu-id="a2e0c-124">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a2e0c-124">Yes<sup>2</sup></span></span>|
| <span data-ttu-id="a2e0c-125">**编辑频道名称/说明**</span><span class="sxs-lookup"><span data-stu-id="a2e0c-125">**Edit channel name/description**</span></span> |    <span data-ttu-id="a2e0c-126">是</span><span class="sxs-lookup"><span data-stu-id="a2e0c-126">Yes</span></span>     |    <span data-ttu-id="a2e0c-127">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a2e0c-127">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="a2e0c-128">**删除频道**</span><span class="sxs-lookup"><span data-stu-id="a2e0c-128">**Delete channel**</span></span>         |    <span data-ttu-id="a2e0c-129">是</span><span class="sxs-lookup"><span data-stu-id="a2e0c-129">Yes</span></span>     |    <span data-ttu-id="a2e0c-130">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a2e0c-130">Yes<sup>2</sup></span></span>|
|          <span data-ttu-id="a2e0c-131">**添加成员**</span><span class="sxs-lookup"><span data-stu-id="a2e0c-131">**Add members**</span></span>          |  <span data-ttu-id="a2e0c-132">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="a2e0c-132">Yes<sup>3</sup></span></span>   |     <span data-ttu-id="a2e0c-133">没有<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="a2e0c-133">No<sup>4</sup></span></span>    |
|          <span data-ttu-id="a2e0c-134">**请求添加成员**</span><span class="sxs-lookup"><span data-stu-id="a2e0c-134">**Request to add members**</span></span>          |  <span data-ttu-id="a2e0c-135">不适用</span><span class="sxs-lookup"><span data-stu-id="a2e0c-135">N/A</span></span>   |     <span data-ttu-id="a2e0c-136">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="a2e0c-136">Yes<sup>5</sup></span></span>     |
|           <span data-ttu-id="a2e0c-137">**添加选项卡**</span><span class="sxs-lookup"><span data-stu-id="a2e0c-137">**Add tabs**</span></span>            |    <span data-ttu-id="a2e0c-138">是</span><span class="sxs-lookup"><span data-stu-id="a2e0c-138">Yes</span></span>     |    <span data-ttu-id="a2e0c-139">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a2e0c-139">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="a2e0c-140">**添加连接器**</span><span class="sxs-lookup"><span data-stu-id="a2e0c-140">**Add connectors**</span></span>         |    <span data-ttu-id="a2e0c-141">是</span><span class="sxs-lookup"><span data-stu-id="a2e0c-141">Yes</span></span>     |    <span data-ttu-id="a2e0c-142">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a2e0c-142">Yes<sup>2</sup></span></span>|
|           <span data-ttu-id="a2e0c-143">**添加聊天机器人**</span><span class="sxs-lookup"><span data-stu-id="a2e0c-143">**Add bots**</span></span>            |    <span data-ttu-id="a2e0c-144">是</span><span class="sxs-lookup"><span data-stu-id="a2e0c-144">Yes</span></span>     |    <span data-ttu-id="a2e0c-145">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="a2e0c-145">Yes<sup>2</sup></span></span>|

<span data-ttu-id="a2e0c-146"><sup>1</sup>除非他们已被禁止这样做，团队所有者可创建团队。</span><span class="sxs-lookup"><span data-stu-id="a2e0c-146"><sup>1</sup> Team owners can create teams unless they've been restricted from doing so.</span></span> <span data-ttu-id="a2e0c-147">请参阅下面的"创建工作组的权限"。</span><span class="sxs-lookup"><span data-stu-id="a2e0c-147">See "Permissions to create teams" below.</span></span>
>
<span data-ttu-id="a2e0c-148"><sup>2</sup>这些项可以关闭所有者在团队级别中，在这种情况下成员不会对它们的访问。</span><span class="sxs-lookup"><span data-stu-id="a2e0c-148"><sup>2</sup> These items can be turned off by an owner at a team level, in which case members would not have access to them.</span></span>

<span data-ttu-id="a2e0c-149"><sup>3</sup>后添加到团队的成员，所有者可以升级到所有者状态成员。</span><span class="sxs-lookup"><span data-stu-id="a2e0c-149"><sup>3</sup> After adding a member to a team, an owner can also promote a member to owner status.</span></span> <span data-ttu-id="a2e0c-150">还有可能的所有者降级成员自己状态。</span><span class="sxs-lookup"><span data-stu-id="a2e0c-150">It is also possible for an owner to demote their own status to a member.</span></span>

<span data-ttu-id="a2e0c-151"><sup>4</sup>工作组成员可以将其他成员添加到公共团队。</span><span class="sxs-lookup"><span data-stu-id="a2e0c-151"><sup>4</sup> Team members can add other members to a public team.</span></span>

<span data-ttu-id="a2e0c-152"><sup>5</sup>时团队成员无法直接将成员添加到专用团队，它们可以请求某人添加到组中已经存在的成员。</span><span class="sxs-lookup"><span data-stu-id="a2e0c-152"><sup>5</sup> While a team member can't directly add members to a private team, they can request someone to be added to a team they're already a member of.</span></span> <span data-ttu-id="a2e0c-153">当成员请求某人添加到组中时，团队所有者将收到通知他们具有挂起的申请，他们可以接受或拒绝。</span><span class="sxs-lookup"><span data-stu-id="a2e0c-153">When a member requests someone to be added to a team, team owners receive an alert that they have a pending request that they can accept or deny.</span></span>



> [!NOTE]
> <span data-ttu-id="a2e0c-154">所有者可以在“查看团队”选项中将其他成员设为所有者。</span><span class="sxs-lookup"><span data-stu-id="a2e0c-154">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="a2e0c-155">一个团队最多可以有 100 个所有者。</span><span class="sxs-lookup"><span data-stu-id="a2e0c-155">A team can have up to 100 owners.</span></span> <span data-ttu-id="a2e0c-156">建议至少指定几个所有者以帮助管理团队；这样也可以防止当唯一的所有者离开贵组织时出现孤立的群组。</span><span class="sxs-lookup"><span data-stu-id="a2e0c-156">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="a2e0c-157">有关孤立群组的详细信息，请参阅[向孤立群组分配新所有者](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)。</span><span class="sxs-lookup"><span data-stu-id="a2e0c-157">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="a2e0c-158">创建团队的权限</span><span class="sxs-lookup"><span data-stu-id="a2e0c-158">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="a2e0c-159">默认情况下，在 Exchange Online 中有邮箱的所有用户都有权创建 Office 365 组，进而有权在 Microsoft Teams 中创建团队。</span><span class="sxs-lookup"><span data-stu-id="a2e0c-159">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="a2e0c-160">你可以通过向一组用户委派组创建和管理权限，更加严格地控制和限制新团队的创建，进而控制和限制新 Office 365 组的创建。</span><span class="sxs-lookup"><span data-stu-id="a2e0c-160">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="a2e0c-161">有关说明，请参阅[的管理可以创建 Office 365 组](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。</span><span class="sxs-lookup"><span data-stu-id="a2e0c-161">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![决策点图标。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="a2e0c-163">决策点</span><span class="sxs-lookup"><span data-stu-id="a2e0c-163">Decision Point</span></span>         |<span data-ttu-id="a2e0c-164">是否所有 Microsoft Teams 用户都将能够创建团队（建议）？</span><span class="sxs-lookup"><span data-stu-id="a2e0c-164">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![后续步骤图标。](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="a2e0c-166">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a2e0c-166">Next Steps</span></span>         |<span data-ttu-id="a2e0c-167">如果你需要限制可以创建团队的人员，请修改可以创建 Office 365 组的人员的默认权限</span><span class="sxs-lookup"><span data-stu-id="a2e0c-167">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
