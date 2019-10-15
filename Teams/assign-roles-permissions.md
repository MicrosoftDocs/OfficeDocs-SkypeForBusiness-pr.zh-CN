---
title: 在 Microsoft Teams 中分配团队所有者和成员
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
ms.reviewer: dansteve
search.appverid: MET150
description: 了解如何在 Microsoft Teams 中分配团队所有者和成员角色，包括创建团队的权限。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 29619fce9f3f9d03f887f632d25b4ae7abe474c9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241718"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="8b5ad-103">在 Microsoft Teams 中分配团队所有者和成员</span><span class="sxs-lookup"><span data-stu-id="8b5ad-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="8b5ad-104">在 Microsoft Teams 中有两种用户角色：**所有者**和**成员**。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-104">Within Microsoft Teams there are two roles: **Owner** and **Member**.</span></span> <span data-ttu-id="8b5ad-105">默认情况下，会为创建新团队的用户授予所有者状态。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-105">By default, a user that creates a new team is granted the Owner status.</span></span> <span data-ttu-id="8b5ad-106">此外，团队所有者和成员可以拥有频道的审核员功能（前提是设置了审核）。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-106">In addition, owners and members can have moderator capabilities for a channel (provided that moderation has been set up).</span></span> <span data-ttu-id="8b5ad-107">如果团队是通过现有 Office 365 组创建的，则会继承权限。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-107">If a team is created from an existing Office 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="8b5ad-108">下表显示了所有者与成员之间的权限差异。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-108">The table below shows the difference in permissions between an owner and a member:</span></span>


|                                   | <span data-ttu-id="8b5ad-109">团队所有者</span><span class="sxs-lookup"><span data-stu-id="8b5ad-109">Team Owner</span></span> | <span data-ttu-id="8b5ad-110">工作组成员</span><span class="sxs-lookup"><span data-stu-id="8b5ad-110">Team Member</span></span> |
|-----------------------------------|------------|-------------|
|          <span data-ttu-id="8b5ad-111">**创建团队**</span><span class="sxs-lookup"><span data-stu-id="8b5ad-111">**Create team**</span></span>          |    <span data-ttu-id="8b5ad-112">是<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="8b5ad-112">Yes<sup>1</sup></span></span>     |     <span data-ttu-id="8b5ad-113">否</span><span class="sxs-lookup"><span data-stu-id="8b5ad-113">No</span></span>      |
|          <span data-ttu-id="8b5ad-114">**离开团队**</span><span class="sxs-lookup"><span data-stu-id="8b5ad-114">**Leave team**</span></span>           |    <span data-ttu-id="8b5ad-115">是</span><span class="sxs-lookup"><span data-stu-id="8b5ad-115">Yes</span></span>     |     <span data-ttu-id="8b5ad-116">是</span><span class="sxs-lookup"><span data-stu-id="8b5ad-116">Yes</span></span>     |
|  <span data-ttu-id="8b5ad-117">**编辑团队名称/说明**</span><span class="sxs-lookup"><span data-stu-id="8b5ad-117">**Edit team name/description**</span></span>   |    <span data-ttu-id="8b5ad-118">是</span><span class="sxs-lookup"><span data-stu-id="8b5ad-118">Yes</span></span>     |     <span data-ttu-id="8b5ad-119">否</span><span class="sxs-lookup"><span data-stu-id="8b5ad-119">No</span></span>      |
|          <span data-ttu-id="8b5ad-120">**删除团队**</span><span class="sxs-lookup"><span data-stu-id="8b5ad-120">**Delete team**</span></span>          |    <span data-ttu-id="8b5ad-121">是</span><span class="sxs-lookup"><span data-stu-id="8b5ad-121">Yes</span></span>     |     <span data-ttu-id="8b5ad-122">否</span><span class="sxs-lookup"><span data-stu-id="8b5ad-122">No</span></span>      |
|          <span data-ttu-id="8b5ad-123">**添加频道**</span><span class="sxs-lookup"><span data-stu-id="8b5ad-123">**Add channel**</span></span>          |    <span data-ttu-id="8b5ad-124">是</span><span class="sxs-lookup"><span data-stu-id="8b5ad-124">Yes</span></span>     |    <span data-ttu-id="8b5ad-125">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8b5ad-125">Yes<sup>2</sup></span></span>|
| <span data-ttu-id="8b5ad-126">**编辑频道名称/说明**</span><span class="sxs-lookup"><span data-stu-id="8b5ad-126">**Edit channel name/description**</span></span> |    <span data-ttu-id="8b5ad-127">是</span><span class="sxs-lookup"><span data-stu-id="8b5ad-127">Yes</span></span>     |    <span data-ttu-id="8b5ad-128">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8b5ad-128">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="8b5ad-129">**删除频道**</span><span class="sxs-lookup"><span data-stu-id="8b5ad-129">**Delete channel**</span></span>         |    <span data-ttu-id="8b5ad-130">是</span><span class="sxs-lookup"><span data-stu-id="8b5ad-130">Yes</span></span>     |    <span data-ttu-id="8b5ad-131">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8b5ad-131">Yes<sup>2</sup></span></span>|
|          <span data-ttu-id="8b5ad-132">**添加成员**</span><span class="sxs-lookup"><span data-stu-id="8b5ad-132">**Add members**</span></span>          |  <span data-ttu-id="8b5ad-133">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="8b5ad-133">Yes<sup>3</sup></span></span>   |     <span data-ttu-id="8b5ad-134">否<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="8b5ad-134">No<sup>4</sup></span></span>    |
|          <span data-ttu-id="8b5ad-135">**请求添加成员**</span><span class="sxs-lookup"><span data-stu-id="8b5ad-135">**Request to add members**</span></span>          |  <span data-ttu-id="8b5ad-136">不适用</span><span class="sxs-lookup"><span data-stu-id="8b5ad-136">N/A</span></span>   |     <span data-ttu-id="8b5ad-137">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="8b5ad-137">Yes<sup>5</sup></span></span>     |
|           <span data-ttu-id="8b5ad-138">**添加选项卡**</span><span class="sxs-lookup"><span data-stu-id="8b5ad-138">**Add tabs**</span></span>            |    <span data-ttu-id="8b5ad-139">是</span><span class="sxs-lookup"><span data-stu-id="8b5ad-139">Yes</span></span>     |    <span data-ttu-id="8b5ad-140">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8b5ad-140">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="8b5ad-141">**添加连接器**</span><span class="sxs-lookup"><span data-stu-id="8b5ad-141">**Add connectors**</span></span>         |    <span data-ttu-id="8b5ad-142">是</span><span class="sxs-lookup"><span data-stu-id="8b5ad-142">Yes</span></span>     |    <span data-ttu-id="8b5ad-143">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8b5ad-143">Yes<sup>2</sup></span></span>|
|           <span data-ttu-id="8b5ad-144">**添加聊天机器人**</span><span class="sxs-lookup"><span data-stu-id="8b5ad-144">**Add bots**</span></span>            |    <span data-ttu-id="8b5ad-145">是</span><span class="sxs-lookup"><span data-stu-id="8b5ad-145">Yes</span></span>     |    <span data-ttu-id="8b5ad-146">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="8b5ad-146">Yes<sup>2</sup></span></span>|

<span data-ttu-id="8b5ad-147"><sup>1</sup> 团队所有者可创建团队，除非他们受到限制。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-147"><sup>1</sup> Team owners can create teams unless they've been restricted from doing so.</span></span> <span data-ttu-id="8b5ad-148">如下[创建团队的权限](#permissions-to-create-teams)。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-148">Permissions to create teams</span></span><br>
><span data-ttu-id="8b5ad-149"><sup>2</sup> 所有者可以在团队级别关闭这些项目，在这种情况下，成员将不能访问它们。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-149"><sup>2</sup> An owner can turn off these items at the team level, in which case members would not have access to them.</span></span><br>
<span data-ttu-id="8b5ad-150"><sup>3</sup> 向团队添加成员后，所有者也可以将成员提升到所有者状态。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-150"> After adding a member to a team, an Owner can also promote a Member to Owner status.</span></span> <span data-ttu-id="8b5ad-151">此外，所有者也可以将自己的状态降级为成员。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-151">It is also possible for an Owner to demote their own status to a Member.</span></span><br>
<span data-ttu-id="8b5ad-152"><sup>4</sup> 团队成员可以向公共团队中添加其他成员。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-152"><sup>4</sup> Team members can add other members to a public team.</span></span><br>
<span data-ttu-id="8b5ad-153"><sup>5</sup> 尽管团队成员无法直接将成员添加到私人团队，但可以请求将某人添加到他们所属的团队。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-153"><sup>5</sup> While a team member can't directly add members to a private team, they can request someone to be added to a team they're already a member of.</span></span> <span data-ttu-id="8b5ad-154">当成员请求将某人添加到团队时，团队所有者将收到通知，告知他们有一个可接受或拒绝的待定请求。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-154">When a member requests someone to be added to a team, team owners receive an alert that they have a pending request that they can accept or deny.</span></span>

> [!NOTE]
> <span data-ttu-id="8b5ad-155">所有者可以在“查看团队”\*\*\*\* 选项中将其他成员设为所有者。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-155">Owners can make other members owners in the View teams option.</span></span> <span data-ttu-id="8b5ad-156">一个团队可以拥有最多 100 个所有者。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-156">A team can have up to 100 owners.</span></span> <span data-ttu-id="8b5ad-157">建议至少指定几个所有者以帮助管理团队；这样也可以防止当唯一的所有者离开贵组织时出现孤立的群组。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-157">It's recommended to have at least a few owners to help manage the team; this will also prevent orphaned groups if the sole owner leaves your organization.</span></span> <span data-ttu-id="8b5ad-158">有关孤立组的详细信息，请参阅[将新的所有者分配到孤立组](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-158">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>

## <a name="moderator-capabilities"></a><span data-ttu-id="8b5ad-159">审核员功能</span><span class="sxs-lookup"><span data-stu-id="8b5ad-159">Moderator capabilities</span></span>

<span data-ttu-id="8b5ad-160">除了其他功能之外，团队所有者和成员还可以拥有频道的审核员功能（前提是针对团队启用了审核）。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-160">In addition to other capabilities, team owners and members can have moderator capabilities for a channel (provided that moderation is turned on for a team).</span></span> <span data-ttu-id="8b5ad-161">审核员可以在频道中发布新帖子，并控制团队成员能否回复现有频道消息。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-161">Moderators can start new posts in a channel and control whether team members can reply to existing channel messages.</span></span> <span data-ttu-id="8b5ad-162">他们还可以控制机器人和连接器是否可以提交频道邮件。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-162">They can also control whether bots and connectors can submit channel messages.</span></span>

<span data-ttu-id="8b5ad-163">审核员功能在频道级别分配。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-163">Moderator capabilities are assigned at the channel level.</span></span> <span data-ttu-id="8b5ad-164">默认情况下，团队所有者拥有审核员功能。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-164">Team owners have moderator capabilities by default.</span></span> <span data-ttu-id="8b5ad-165">默认情况下，团队成员已关闭审核员功能，但是团队所有者可向团队成员提供频道审核员功能。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-165">Team members have moderator capabilities turned off by default, but a team owner can give moderator capabilities for a channel to a team member.</span></span> <span data-ttu-id="8b5ad-166">频道内的审核员可在该渠道中添加或删除其他审核员。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-166">Moderators within a channel can add and remove other moderators within that channel.</span></span>

<span data-ttu-id="8b5ad-167">有关审核员功能详细信息，请参阅[在 Microsoft Teams 中设置和管理频道审核](manage-channel-moderation-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-167">For more information about moderator capabilities, see [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md).</span></span>

## <a name="assign-a-user-role"></a><span data-ttu-id="8b5ad-168">分配用户角色</span><span class="sxs-lookup"><span data-stu-id="8b5ad-168">Assign a user role</span></span>

<span data-ttu-id="8b5ad-169">若要分配用户角色，请在 Teams 中选择团队名称，然后单击“更多选项”\*\*\*\* > “管理团队”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-169">To assign a user role, in Teams, select the team name and click **More options** > **Manage team**.</span></span> <span data-ttu-id="8b5ad-170">在“成员”\*\*\*\* 选项卡上，可以添加成员并选择所有者和审核员（如果你有足够的权限）。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-170">On the **Members** tab, you can add members and choose owners and moderators (if you have sufficient permissions).</span></span> <span data-ttu-id="8b5ad-171">有关详细信息，请参阅 [Teams 中的团队设置](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc)</span><span class="sxs-lookup"><span data-stu-id="8b5ad-171">For more information , see [Change team settings in Teams](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc).</span></span>

## <a name="permissions-to-create-teams"></a><span data-ttu-id="8b5ad-172">创建团队的权限</span><span class="sxs-lookup"><span data-stu-id="8b5ad-172">Permissions to create teams</span></span>

<span data-ttu-id="8b5ad-173">默认情况下，在 Exchange Online 中有邮箱的所有用户都有权创建 Office 365 组，进而有权在 Microsoft Teams 中创建团队。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-173">By default, all users with a mailbox in Exchange Online have permissions to create Office 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="8b5ad-174">你可以通过向一组用户委派组创建和管理权限，更加严格地控制和限制新团队的创建，进而控制和限制新 Office 365 组的创建。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-174">You can have tighter control and restrict the creation of new teams and thus the creation of new Office 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="8b5ad-175">有关说明，请参阅[管理哪些人可以创建 Office 365 组](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。</span><span class="sxs-lookup"><span data-stu-id="8b5ad-175">For more information, see [Manage who can create Office 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![代表决策点的图标](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="8b5ad-177">决策点</span><span class="sxs-lookup"><span data-stu-id="8b5ad-177">Decision Point</span></span>         |<span data-ttu-id="8b5ad-178">是否所有 Microsoft Teams 用户都将能够创建团队（建议）？</span><span class="sxs-lookup"><span data-stu-id="8b5ad-178">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![表示后续步骤的图标](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="8b5ad-180">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8b5ad-180">Next Steps</span></span>         |<span data-ttu-id="8b5ad-181">如果你需要限制可以创建团队的人员，请修改可以创建 Office 365 组的人员的默认权限</span><span class="sxs-lookup"><span data-stu-id="8b5ad-181">Modify the default permissions for who can create Office 365 groups if you need to limit who can create Teams</span></span>         |
