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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 45cfe8ed255e889093044672cb738152adaaf6ae
ms.sourcegitcommit: fa567451f8f7af6d915e33809d88f26b415db54c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "44610134"
---
<a name="assign-team-owners-and-members-in-microsoft-teams"></a><span data-ttu-id="6a724-103">在 Microsoft Teams 中分配团队所有者和成员</span><span class="sxs-lookup"><span data-stu-id="6a724-103">Assign team owners and members in Microsoft Teams</span></span>
=================================================

> [!IMPORTANT]
> [!INCLUDE [new-teams-sfb-admin-center-notice](includes/new-teams-sfb-admin-center-notice.md)]

<span data-ttu-id="6a724-104">在 Microsoft Teams 中有两种用户角色：**所有者**和**成员**。</span><span class="sxs-lookup"><span data-stu-id="6a724-104">Within Microsoft Teams there are two user roles: **owner** and **member**.</span></span> <span data-ttu-id="6a724-105">默认情况下，会为创建新团队的用户授予所有者状态。</span><span class="sxs-lookup"><span data-stu-id="6a724-105">By default, a user who creates a new team is granted the owner status.</span></span> <span data-ttu-id="6a724-106">此外，团队所有者和成员可以拥有频道的审核员功能（前提是设置了审核）。</span><span class="sxs-lookup"><span data-stu-id="6a724-106">In addition, owners and members can have moderator capabilities for a channel (provided that moderation has been set up).</span></span> <span data-ttu-id="6a724-107">如果团队是从现有 Microsoft 365 组创建的，则权限将被继承。</span><span class="sxs-lookup"><span data-stu-id="6a724-107">If a team is created from an existing Microsoft 365 Group, permissions are inherited.</span></span>

<span data-ttu-id="6a724-108">下表显示了所有者与成员之间的权限差异。</span><span class="sxs-lookup"><span data-stu-id="6a724-108">The table below shows the difference in permissions between an owner and a member.</span></span>


|                                   | <span data-ttu-id="6a724-109">团队所有者</span><span class="sxs-lookup"><span data-stu-id="6a724-109">Team Owner</span></span> | <span data-ttu-id="6a724-110">工作组成员</span><span class="sxs-lookup"><span data-stu-id="6a724-110">Team Member</span></span> |
|-----------------------------------|------------|-------------|
|          <span data-ttu-id="6a724-111">**创建团队**</span><span class="sxs-lookup"><span data-stu-id="6a724-111">**Create team**</span></span>          |    <span data-ttu-id="6a724-112">是<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="6a724-112">Yes<sup>1</sup></span></span>     |     <span data-ttu-id="6a724-113">否</span><span class="sxs-lookup"><span data-stu-id="6a724-113">No</span></span>      |
|          <span data-ttu-id="6a724-114">**离开团队**</span><span class="sxs-lookup"><span data-stu-id="6a724-114">**Leave team**</span></span>           |    <span data-ttu-id="6a724-115">是</span><span class="sxs-lookup"><span data-stu-id="6a724-115">Yes</span></span>     |     <span data-ttu-id="6a724-116">是</span><span class="sxs-lookup"><span data-stu-id="6a724-116">Yes</span></span>     |
|  <span data-ttu-id="6a724-117">**编辑团队名称/说明**</span><span class="sxs-lookup"><span data-stu-id="6a724-117">**Edit team name/description**</span></span>   |    <span data-ttu-id="6a724-118">是</span><span class="sxs-lookup"><span data-stu-id="6a724-118">Yes</span></span>     |     <span data-ttu-id="6a724-119">否</span><span class="sxs-lookup"><span data-stu-id="6a724-119">No</span></span>      |
|          <span data-ttu-id="6a724-120">**删除团队**</span><span class="sxs-lookup"><span data-stu-id="6a724-120">**Delete team**</span></span>          |    <span data-ttu-id="6a724-121">是</span><span class="sxs-lookup"><span data-stu-id="6a724-121">Yes</span></span>     |     <span data-ttu-id="6a724-122">否</span><span class="sxs-lookup"><span data-stu-id="6a724-122">No</span></span>      |
|          <span data-ttu-id="6a724-123">**添加标准频道**</span><span class="sxs-lookup"><span data-stu-id="6a724-123">**Add standard channel**</span></span>          |    <span data-ttu-id="6a724-124">是</span><span class="sxs-lookup"><span data-stu-id="6a724-124">Yes</span></span>     |    <span data-ttu-id="6a724-125">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="6a724-125">Yes<sup>2</sup></span></span>|
| <span data-ttu-id="6a724-126">**编辑标准频道名称/说明**</span><span class="sxs-lookup"><span data-stu-id="6a724-126">**Edit standard channel name/description**</span></span> |    <span data-ttu-id="6a724-127">是</span><span class="sxs-lookup"><span data-stu-id="6a724-127">Yes</span></span>     |    <span data-ttu-id="6a724-128">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="6a724-128">Yes<sup>2</sup></span></span>|
|        <span data-ttu-id="6a724-129">**删除标准频道**</span><span class="sxs-lookup"><span data-stu-id="6a724-129">**Delete standard channel**</span></span>         |    <span data-ttu-id="6a724-130">是</span><span class="sxs-lookup"><span data-stu-id="6a724-130">Yes</span></span>     |    <span data-ttu-id="6a724-131">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="6a724-131">Yes<sup>2</sup></span></span>|
|          <span data-ttu-id="6a724-132">\***添加专用频道**</span><span class="sxs-lookup"><span data-stu-id="6a724-132">\***Add private channel**</span></span>          |    <span data-ttu-id="6a724-133">是</span><span class="sxs-lookup"><span data-stu-id="6a724-133">Yes</span></span>     |    <span data-ttu-id="6a724-134">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="6a724-134">Yes<sup>2</sup></span></span>|
| <span data-ttu-id="6a724-135">\***编辑专用频道名称/说明**</span><span class="sxs-lookup"><span data-stu-id="6a724-135">\***Edit private channel name/description**</span></span> |    <span data-ttu-id="6a724-136">否</span><span class="sxs-lookup"><span data-stu-id="6a724-136">No</span></span>     |    <span data-ttu-id="6a724-137">不适用</span><span class="sxs-lookup"><span data-stu-id="6a724-137">N/A</span></span>|
|        <span data-ttu-id="6a724-138">\***删除专用频道**</span><span class="sxs-lookup"><span data-stu-id="6a724-138">\***Delete private channel**</span></span>         |    <span data-ttu-id="6a724-139">是</span><span class="sxs-lookup"><span data-stu-id="6a724-139">Yes</span></span>     |    <span data-ttu-id="6a724-140">否</span><span class="sxs-lookup"><span data-stu-id="6a724-140">No</span></span>|
|          <span data-ttu-id="6a724-141">**添加成员**</span><span class="sxs-lookup"><span data-stu-id="6a724-141">**Add members**</span></span>          |  <span data-ttu-id="6a724-142">是<sup>3</sup></span><span class="sxs-lookup"><span data-stu-id="6a724-142">Yes<sup>3</sup></span></span>   |     <span data-ttu-id="6a724-143">否<sup>4</sup></span><span class="sxs-lookup"><span data-stu-id="6a724-143">No<sup>4</sup></span></span>    |
|          <span data-ttu-id="6a724-144">**请求添加成员**</span><span class="sxs-lookup"><span data-stu-id="6a724-144">**Request to add members**</span></span>          |  <span data-ttu-id="6a724-145">不适用</span><span class="sxs-lookup"><span data-stu-id="6a724-145">N/A</span></span>   |     <span data-ttu-id="6a724-146">是<sup>5</sup></span><span class="sxs-lookup"><span data-stu-id="6a724-146">Yes<sup>5</sup></span></span>     |
|           <span data-ttu-id="6a724-147">**添加应用**</span><span class="sxs-lookup"><span data-stu-id="6a724-147">**Add apps**</span></span>            |    <span data-ttu-id="6a724-148">是</span><span class="sxs-lookup"><span data-stu-id="6a724-148">Yes</span></span>     |    <span data-ttu-id="6a724-149">是<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="6a724-149">Yes<sup>2</sup></span></span>|

<span data-ttu-id="6a724-150"><sup>1</sup> 团队所有者可创建团队，除非他们受到限制。</span><span class="sxs-lookup"><span data-stu-id="6a724-150"><sup>1</sup> Team owners can create teams unless they've been restricted from doing so.</span></span> <span data-ttu-id="6a724-151">如下[创建团队的权限](#permissions-to-create-teams)。</span><span class="sxs-lookup"><span data-stu-id="6a724-151">[Permissions to create teams](#permissions-to-create-teams) below.</span></span><br>
<span data-ttu-id="6a724-152"><sup>2</sup> 所有者可以在团队级别关闭这些项目，在这种情况下，成员将不能访问它们。</span><span class="sxs-lookup"><span data-stu-id="6a724-152"><sup>2</sup> An owner can turn off these items at the team level, in which case members would not have access to them.</span></span><br>
<span data-ttu-id="6a724-153"><sup>3</sup> 向团队添加成员后，所有者也可以将成员提升到所有者状态。</span><span class="sxs-lookup"><span data-stu-id="6a724-153"><sup>3</sup> After adding a member to a team, an owner can also promote a member to owner status.</span></span> <span data-ttu-id="6a724-154">此外，所有者也可以将自己的状态降级为成员。</span><span class="sxs-lookup"><span data-stu-id="6a724-154">It is also possible for an owner to demote their own status to a member.</span></span><br>
<span data-ttu-id="6a724-155"><sup>4</sup> 团队成员可以向公共团队中添加其他成员。</span><span class="sxs-lookup"><span data-stu-id="6a724-155"><sup>4</sup> Team members can add other members to a public team.</span></span><br>
<span data-ttu-id="6a724-156"><sup>5</sup> 尽管团队成员无法直接将成员添加到私人团队，但可以请求将某人添加到他们所属的团队。</span><span class="sxs-lookup"><span data-stu-id="6a724-156"><sup>5</sup> While a team member can't directly add members to a private team, they can request someone to be added to a team they're already a member of.</span></span> <span data-ttu-id="6a724-157">当成员请求将某人添加到团队时，团队所有者将收到通知，告知他们有一个可接受或拒绝的待定请求。</span><span class="sxs-lookup"><span data-stu-id="6a724-157">When a member requests someone to be added to a team, team owners receive an alert that they have a pending request that they can accept or deny.</span></span>

<span data-ttu-id="6a724-158">\* 若要了解有关专用频道的权限的详细信息，请参阅[团队中的专用频道](private-channels.md)。</span><span class="sxs-lookup"><span data-stu-id="6a724-158">\*To learn more about permissions for private channels, see [Private channels in Teams](private-channels.md).</span></span>

> [!NOTE]
> <span data-ttu-id="6a724-159">所有者可以在“查看团队”\*\*\*\* 选项中将其他成员设为所有者。</span><span class="sxs-lookup"><span data-stu-id="6a724-159">Owners can make other members owners in the **View teams** option.</span></span> <span data-ttu-id="6a724-160">一个团队可以拥有最多 100 个所有者。</span><span class="sxs-lookup"><span data-stu-id="6a724-160">A team can have up to 100 owners.</span></span> <span data-ttu-id="6a724-161">建议至少指定几个所有者以帮助管理团队；这样也可以防止当唯一的所有者离开贵组织时出现孤立的群组。</span><span class="sxs-lookup"><span data-stu-id="6a724-161">We recommend that you have at least a few owners to help manage the team; this will also prevent orphaned groups if a sole owner leaves your organization.</span></span> <span data-ttu-id="6a724-162">有关孤立组的详细信息，请参阅[将新的所有者分配到孤立组](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732)。</span><span class="sxs-lookup"><span data-stu-id="6a724-162">For more information about orphaned groups, see [Assign a new owner to an orphaned group](https://support.office.com/article/Assign-a-new-owner-to-an-orphaned-group-86bb3db6-8857-45d1-95c8-f6d540e45732).</span></span>

## <a name="moderator-capabilities"></a><span data-ttu-id="6a724-163">审核员功能</span><span class="sxs-lookup"><span data-stu-id="6a724-163">Moderator capabilities</span></span>

<span data-ttu-id="6a724-164">除了其他功能之外，团队所有者和成员还可以拥有频道的审核员功能（前提是针对团队启用了审核）。</span><span class="sxs-lookup"><span data-stu-id="6a724-164">In addition to other capabilities, team owners and members can have moderator capabilities for a channel (provided that moderation is turned on for a team).</span></span> <span data-ttu-id="6a724-165">审核员可以在频道中发布新帖子，并控制团队成员能否回复现有频道消息。</span><span class="sxs-lookup"><span data-stu-id="6a724-165">Moderators can start new posts in a channel and control whether team members can reply to existing channel messages.</span></span> <span data-ttu-id="6a724-166">他们还可以控制机器人和连接器是否可以提交频道邮件。</span><span class="sxs-lookup"><span data-stu-id="6a724-166">They can also control whether bots and connectors can submit channel messages.</span></span>

<span data-ttu-id="6a724-167">审核员功能在频道级别分配。</span><span class="sxs-lookup"><span data-stu-id="6a724-167">Moderator capabilities are assigned at the channel level.</span></span> <span data-ttu-id="6a724-168">默认情况下，团队所有者拥有审核员功能。</span><span class="sxs-lookup"><span data-stu-id="6a724-168">Team owners have moderator capabilities by default.</span></span> <span data-ttu-id="6a724-169">默认情况下，团队成员已关闭审核员功能，但是团队所有者可向团队成员提供频道审核员功能。</span><span class="sxs-lookup"><span data-stu-id="6a724-169">Team members have moderator capabilities turned off by default, but a team owner can give moderator capabilities for a channel to a team member.</span></span> <span data-ttu-id="6a724-170">频道内的审核员可在该渠道中添加或删除其他审核员。</span><span class="sxs-lookup"><span data-stu-id="6a724-170">Moderators within a channel can add and remove other moderators within that channel.</span></span>

<span data-ttu-id="6a724-171">有关审核员功能详细信息，请参阅[在 Microsoft Teams 中设置和管理频道审核](manage-channel-moderation-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="6a724-171">For more information about moderator capabilities, see [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md).</span></span>

## <a name="assign-a-user-role"></a><span data-ttu-id="6a724-172">分配用户角色</span><span class="sxs-lookup"><span data-stu-id="6a724-172">Assign a user role</span></span>

<span data-ttu-id="6a724-173">若要分配用户角色，请在 Teams 中选择团队名称，然后单击“更多选项”\*\*\*\* > “管理团队”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6a724-173">To assign a user role, in Teams, select the team name and click **More options** > **Manage team**.</span></span> <span data-ttu-id="6a724-174">在“成员”\*\*\*\* 选项卡上，可以添加成员并选择所有者和审核员（如果你有足够的权限）。</span><span class="sxs-lookup"><span data-stu-id="6a724-174">On the **Members** tab, you can add members and choose owners and moderators (if you have sufficient permissions).</span></span> <span data-ttu-id="6a724-175">有关详细信息，请参阅 [Teams 中的团队设置](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc)</span><span class="sxs-lookup"><span data-stu-id="6a724-175">For more information , see [Change team settings in Teams](https://support.office.com/article/ce053b04-1b8e-4796-baa8-90dc427b3acc).</span></span>

## <a name="permissions-to-create-teams"></a><span data-ttu-id="6a724-176">创建团队的权限</span><span class="sxs-lookup"><span data-stu-id="6a724-176">Permissions to create teams</span></span>

<span data-ttu-id="6a724-177">默认情况下，在 Exchange Online 中拥有邮箱的所有用户都具有创建 Microsoft 365 组的权限，因此在 Microsoft 团队内有一个团队。</span><span class="sxs-lookup"><span data-stu-id="6a724-177">By default, all users with a mailbox in Exchange Online have permissions to create Microsoft 365 groups and therefore a team within Microsoft Teams.</span></span> <span data-ttu-id="6a724-178">你可以通过将组创建和管理权限委派给一组用户，让你更严格地控制和限制新团队的创建，从而创建新的 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="6a724-178">You can have tighter control and restrict the creation of new teams and thus the creation of new Microsoft 365 groups by delegating group creation and management rights to a set of users.</span></span> <span data-ttu-id="6a724-179">有关说明，请参阅[管理可创建 Microsoft 365 组的人员](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618)。</span><span class="sxs-lookup"><span data-stu-id="6a724-179">For instructions, see [Manage who can create Microsoft 365 Groups](https://support.office.com/article/manage-who-can-create-office-365-groups-4c46c8cb-17d0-44b5-9776-005fced8e618).</span></span>


||||
|---------|---------|---------|
| ![代表决策点的图标](media/Assign_roles_and_permissions_in_Microsoft_Teams_image2.png)     |<span data-ttu-id="6a724-181">决策点</span><span class="sxs-lookup"><span data-stu-id="6a724-181">Decision Point</span></span>         |<span data-ttu-id="6a724-182">是否所有 Microsoft Teams 用户都将能够创建团队（建议）？</span><span class="sxs-lookup"><span data-stu-id="6a724-182">Will all Microsoft Teams users be able to create Teams (recommended)?</span></span>         |
| ![表示后续步骤的图标](media/Assign_roles_and_permissions_in_Microsoft_Teams_image3.png)    |<span data-ttu-id="6a724-184">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6a724-184">Next Steps</span></span>         |<span data-ttu-id="6a724-185">如果需要限制可以创建团队的人员，请修改可创建 Microsoft 365 组的用户的默认权限</span><span class="sxs-lookup"><span data-stu-id="6a724-185">Modify the default permissions for who can create Microsoft 365 groups if you need to limit who can create Teams</span></span>         |
