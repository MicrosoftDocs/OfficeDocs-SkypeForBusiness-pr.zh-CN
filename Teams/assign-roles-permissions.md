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
ms.openlocfilehash: 423a12e8fce0c9d7508e97c1f57e17a0ba8a0ff0
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2019
ms.locfileid: "34493799"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="f9445-103">在 Microsoft Teams 中分配团队所有者和成员</span><span class="sxs-lookup"><span data-stu-id="f9445-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="f9445-104">Microsoft 团队内部有两个用户角色:**所有者**和**成员**。</span><span class="sxs-lookup"><span data-stu-id="f9445-104">Within Microsoft Teams there are two user roles: **Owner** and **Member**.</span></span> <span data-ttu-id="f9445-105">默认情况下, 会向创建新团队的用户授予所有者状态。</span><span class="sxs-lookup"><span data-stu-id="f9445-105">By default, a user who creates a new team is granted the Owner status.</span></span> <span data-ttu-id="f9445-106">如果团队是从现有 Office 365 组创建的，则将继承权限。</span><span class="sxs-lookup"><span data-stu-id="f9445-106">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="f9445-107">下表显示了所有者和成员之间的权限差异。</span><span class="sxs-lookup"><span data-stu-id="f9445-107">The table below shows the difference in permissions between an owner and a member.</span></span>


|                                   | <span data-ttu-id="f9445-108">团队所有者</span><span class="sxs-lookup"><span data-stu-id="f9445-108">Team Owner</span></span> | <span data-ttu-id="f9445-109">团队成员</span><span class="sxs-lookup"><span data-stu-id="f9445-109">Team Member</span></span> |
|-----------------------------------|------------|-------------|
|          <span data-ttu-id="f9445-110">**创建团队**</span><span class="sxs-lookup"><span data-stu-id="f9445-110">**Create team**</span></span>          |    <span data-ttu-id="f9445-111">是<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="f9445-111">Yes<sup>1</sup></span></span>     |     <span data-ttu-id="f9445-112">否</span><span class="sxs-lookup"><span data-stu-id="f9445-112">No</span></span>      |
|          <span data-ttu-id="f9445-113">**离开团队**</span><span class="sxs-lookup"><span data-stu-id="f9445-113">**Leave team**</span></span>           |    <span data-ttu-id="f9445-114">是</span><span class="sxs-lookup"><span data-stu-id="f9445-114">Yes</span></span>     |     <span data-ttu-id="f9445-115">是</span><span class="sxs-lookup"><span data-stu-id="f9445-115">Yes</span></span>     |
|  <span data-ttu-id="f9445-116">**编辑团队名称/说明**</span><span class="sxs-lookup"><span data-stu-id="f9445-116">**Edit team name/description**</span></span>   |    <span data-ttu-id="f9445-117">是</span><span class="sxs-lookup"><span data-stu-id="f9445-117">Yes</span></span>     |     <span data-ttu-id="f9445-118">否</span><span class="sxs-lookup"><span data-stu-id="f9445-118">No</span></span>      |
|          <span data-ttu-id="f9445-119">**删除团队**</span><span class="sxs-lookup"><span data-stu-id="f9445-119">**Delete team**</span></span>          |    <span data-ttu-id="f9445-120">是</span><span class="sxs-lookup"><span data-stu-id="f9445-120">Yes</span></span>     |     <span data-ttu-id="f9445-121">否</span><span class="sxs-lookup"><span data-stu-id="f9445-121">No</span></span>      |
|          <span data-ttu-id="f9445-122">**添加频道**</span><span class="sxs-lookup"><span data-stu-id="f9445-122">**Add channel**</span></span>          |    <span data-ttu-id="f9445-123">是</span><span class="sxs-lookup"><span data-stu-id="f9445-123">Yes</span></span>     |    <span data-ttu-id="f9445-124">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f9445-124">Yes<sup>2</sup></span></span>|
| <span data-ttu-id="f9445-125">**编辑频道名称/说明**</span><span class="sxs-lookup"><span data-stu-id="f9445-125">**Edit channel name/description**</span></span> |    <span data-ttu-id="f9445-126">是</span><span class="sxs-lookup"><span data-stu-id="f9445-126">Yes</span></span>     |    <span data-ttu-id="f9445-127">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f9445-127">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="f9445-128">**删除频道**</span><span class="sxs-lookup"><span data-stu-id="f9445-128">**Delete channel**</span></span>         |    <span data-ttu-id="f9445-129">是</span><span class="sxs-lookup"><span data-stu-id="f9445-129">Yes</span></span>     |    <span data-ttu-id="f9445-130">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f9445-130">Yes<sup>2</sup></span></span>|
|          <span data-ttu-id="f9445-131">**添加成员**</span><span class="sxs-lookup"><span data-stu-id="f9445-131">**Add members**</span></span>          |  <span data-ttu-id="f9445-132">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="f9445-132">Yes<sup>3</sup></span></span>   |     <span data-ttu-id="f9445-133">无<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="f9445-133">No<sup>4</sup></span></span>    |
|          <span data-ttu-id="f9445-134">**请求添加成员**</span><span class="sxs-lookup"><span data-stu-id="f9445-134">**Request to add members**</span></span>          |  <span data-ttu-id="f9445-135">不适用</span><span class="sxs-lookup"><span data-stu-id="f9445-135">N/A</span></span>   |     <span data-ttu-id="f9445-136">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="f9445-136">Yes<sup>5</sup></span></span>     |
|           <span data-ttu-id="f9445-137">**添加选项卡**</span><span class="sxs-lookup"><span data-stu-id="f9445-137">**Add tabs**</span></span>            |    <span data-ttu-id="f9445-138">是</span><span class="sxs-lookup"><span data-stu-id="f9445-138">Yes</span></span>     |    <span data-ttu-id="f9445-139">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f9445-139">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="f9445-140">**添加连接器**</span><span class="sxs-lookup"><span data-stu-id="f9445-140">**Add connectors**</span></span>         |    <span data-ttu-id="f9445-141">是</span><span class="sxs-lookup"><span data-stu-id="f9445-141">Yes</span></span>     |    <span data-ttu-id="f9445-142">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f9445-142">Yes<sup>2</sup></span></span>|
|           <span data-ttu-id="f9445-143">**添加聊天机器人**</span><span class="sxs-lookup"><span data-stu-id="f9445-143">**Add bots**</span></span>            |    <span data-ttu-id="f9445-144">是</span><span class="sxs-lookup"><span data-stu-id="f9445-144">Yes</span></span>     |    <span data-ttu-id="f9445-145">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="f9445-145">Yes<sup>2</sup></span></span>|

<span data-ttu-id="f9445-146"><sup>1</sup>团队所有者可以创建团队, 除非他们受到限制。</span><span class="sxs-lookup"><span data-stu-id="f9445-146"><sup>1</sup> Team owners can create teams unless they've been restricted from doing so.</span></span> <span data-ttu-id="f9445-147">请参阅下面的 "创建团队的权限"。</span><span class="sxs-lookup"><span data-stu-id="f9445-147">See "Permissions to create teams" below.</span></span>
>
<span data-ttu-id="f9445-148"><sup>2</sup>这些项目可以由团队级别的所有者关闭, 在这种情况下, 成员将无权访问它们。</span><span class="sxs-lookup"><span data-stu-id="f9445-148"><sup>2</sup> These items can be turned off by an owner at a team level, in which case members would not have access to them.</span></span>

<span data-ttu-id="f9445-149"><sup>3</sup>将成员添加到团队后, 所有者还可以将成员提升为所有者状态。</span><span class="sxs-lookup"><span data-stu-id="f9445-149"><sup>3</sup> After adding a member to a team, an owner can also promote a member to owner status.</span></span> <span data-ttu-id="f9445-150">所有者也可以将自己的状态降级为成员。</span><span class="sxs-lookup"><span data-stu-id="f9445-150">It is also possible for an owner to demote their own status to a member.</span></span>

<span data-ttu-id="f9445-151"><sup>4 个</sup>团队成员可以将其他成员添加到公共团队。</span><span class="sxs-lookup"><span data-stu-id="f9445-151"><sup>4</sup> Team members can add other members to a public team.</span></span>

<span data-ttu-id="f9445-152"><sup>5</sup>当团队成员无法直接将成员添加到专用团队时, 他们可以请求将某人添加到他们已成为其成员的团队。</span><span class="sxs-lookup"><span data-stu-id="f9445-152"><sup>5</sup> While a team member can't directly add members to a private team, they can request someone to be added to a team they're already a member of.</span></span> <span data-ttu-id="f9445-153">当成员请求将某人添加到团队时, 团队所有者会收到通知, 通知他们具有他们可以接受或拒绝的待定请求。</span><span class="sxs-lookup"><span data-stu-id="f9445-153">When a member requests someone to be added to a team, team owners receive an alert that they have a pending request that they can accept or deny.</span></span>



> [!NOTE]
> <span data-ttu-id="f9445-154">所有者可以在“查看团队”选项中将其他成员设为所有者。</span><span class="sxs-lookup"><span data-stu-id="f9445-154">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="f9445-155">一个团队最多可以有 100 个所有者。</span><span class="sxs-lookup"><span data-stu-id="f9445-155">A team can have up to 100 owners.</span></span> <span data-ttu-id="f9445-156">建议至少指定几个所有者以帮助管理团队；这样也可以防止当唯一的所有者离开贵组织时出现孤立的群组。</span><span class="sxs-lookup"><span data-stu-id="f9445-156">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="f9445-157">有关孤立群组的详细信息，请参阅[向孤立群组分配新所有者](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)。</span><span class="sxs-lookup"><span data-stu-id="f9445-157">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>


<a name="permissions-to-create-teams"></a><span data-ttu-id="f9445-158">创建团队的权限</span><span class="sxs-lookup"><span data-stu-id="f9445-158">Permissions to create teams</span></span>
---------------------------

<span data-ttu-id="f9445-159">默认情况下，在 Exchange Online 中有邮箱的所有用户都有权创建 Office 365 组，进而有权在 Microsoft Teams 中创建团队。</span><span class="sxs-lookup"><span data-stu-id="f9445-159">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="f9445-160">你可以通过向一组用户委派组创建和管理权限，更加严格地控制和限制新团队的创建，进而控制和限制新 Office 365 组的创建。</span><span class="sxs-lookup"><span data-stu-id="f9445-160">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="f9445-161">有关说明, 请参阅[管理可创建 Office 365 组的人员](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。</span><span class="sxs-lookup"><span data-stu-id="f9445-161">For instructions, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![表示决策点的图标](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="f9445-163">决策点</span><span class="sxs-lookup"><span data-stu-id="f9445-163">Decision Point</span></span>         |<span data-ttu-id="f9445-164">是否所有 Microsoft Teams 用户都将能够创建团队（建议）？</span><span class="sxs-lookup"><span data-stu-id="f9445-164">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![表示后续步骤的图标](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="f9445-166">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f9445-166">Next Steps</span></span>         |<span data-ttu-id="f9445-167">如果你需要限制可以创建团队的人员，请修改可以创建 Office 365 组的人员的默认权限</span><span class="sxs-lookup"><span data-stu-id="f9445-167">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
