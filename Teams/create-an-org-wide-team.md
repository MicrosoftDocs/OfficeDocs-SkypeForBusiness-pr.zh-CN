---
title: 在 Microsoft Teams 中创建组织范围的团队
author: LanaChin
ms.author: v-lanac
ms.reviewer: phlouie
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: 了解如何在团队中创建和管理组织范围的团队。
localization_priority: Normal
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 881996d5f8acbc7458a775e02adfad9b38a231a9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241231"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a><span data-ttu-id="cc9f8-103">在 Microsoft Teams 中创建组织范围的团队</span><span class="sxs-lookup"><span data-stu-id="cc9f8-103">Create an org-wide team in Microsoft Teams</span></span>

<span data-ttu-id="cc9f8-104">组织范围的团队为一个规模较小的组织中的每个人提供自动方法, 以成为单个团队协作的一部分。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-104">Org-wide teams provide an automatic way for everyone in a small to medium-sized organization to be a part of a single team for collaboration.</span></span>

<span data-ttu-id="cc9f8-105">有了组织范围的团队, 全局管理员可以轻松地创建一个公共团队, 在组织中的每个用户中提取, 并在用户加入和离开组织时保持与 Active Directory 的成员身份保持最新。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-105">With org-wide teams, global admins can easily create a public team that pulls in every user in the organization and keeps the membership up to date with Active Directory as users join and leave the organization.</span></span> <span data-ttu-id="cc9f8-106">只有全局管理员可以创建组织范围的团队, 并且当前组织范围的团队仅限于不超过5000用户的组织。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-106">Only global admins can create org-wide teams and currently an org-wide team is limited to organizations with no more than 5,000 users.</span></span> <span data-ttu-id="cc9f8-107">每个租户也有五个组织范围的团队限制。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-107">There's also a limit of five org-wide teams per tenant.</span></span> <span data-ttu-id="cc9f8-108">如果满足这些要求, 当创建团队时, 全局管理员会在选择 "**从头开始构建团队**" 时看到**组织范围**。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-108">If these requirements are met, global admins will see **Org-wide** as an option when they select **Build a team from scratch** when creating a team.</span></span> 

<span data-ttu-id="cc9f8-109">![组织范围选项的屏幕截图, 用于创建组织范围的团队](media/create-org-wide-team.png "组织范围选项的屏幕截图, 用于创建组织范围的团队")</span><span class="sxs-lookup"><span data-stu-id="cc9f8-109">![Screen shot of the Org-wide option to create an org-wide team](media/create-org-wide-team.png "Screen shot of the Org-wide option to create an org-wide team")</span></span>

<span data-ttu-id="cc9f8-110">创建组织范围的团队后, 所有全局管理员都将添加为团队所有者, 并将所有活动用户添加为团队成员。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-110">When an org-wide team is created, all global admins are added as team owners and all active users are added as team members.</span></span> <span data-ttu-id="cc9f8-111">未经授权的用户也将添加到团队。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-111">Unlicensed users are also added to the team.</span></span> <span data-ttu-id="cc9f8-112">当未经授权的用户第一次登录团队时, 将为用户分配 Microsoft 团队商业云试用版许可证。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-112">The first time an unlicensed user signs in to Teams, the user is assigned a Microsoft Teams Commercial Cloud Trial license.</span></span> <span data-ttu-id="cc9f8-113">若要了解有关试用许可证的详细信息, 请查看[管理团队商业云试用版优惠](iw-trial-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-113">To learn more about the trial license, check out [Manage the Teams Commercial Cloud Trial offer](iw-trial-teams.md).</span></span> 

<span data-ttu-id="cc9f8-114">这些类型的帐户不会添加到组织范围的团队:</span><span class="sxs-lookup"><span data-stu-id="cc9f8-114">These types of accounts won't be added to your org-wide team:</span></span>

- <span data-ttu-id="cc9f8-115">阻止登录的帐户</span><span class="sxs-lookup"><span data-stu-id="cc9f8-115">Accounts that are blocked from sign in</span></span>
- <span data-ttu-id="cc9f8-116">来宾用户</span><span class="sxs-lookup"><span data-stu-id="cc9f8-116">Guest users</span></span>
- <span data-ttu-id="cc9f8-117">服务帐户</span><span class="sxs-lookup"><span data-stu-id="cc9f8-117">Service accounts</span></span>
- <span data-ttu-id="cc9f8-118">会议室或设备帐户</span><span class="sxs-lookup"><span data-stu-id="cc9f8-118">Room or equipment accounts</span></span>
- <span data-ttu-id="cc9f8-119">由共享邮箱支持的帐户</span><span class="sxs-lookup"><span data-stu-id="cc9f8-119">Accounts backed by a shared mailbox</span></span>

<span data-ttu-id="cc9f8-120">由于您的组织的目录已更新为包括新的活动用户, 或者如果用户在您的公司中不再工作, 并且他们的团队许可证已禁用, 则更改将自动同步, 并且用户将添加或从团队中删除。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-120">As your organization's directory is updated to include new active users or if users no longer work at your company and their Teams license is disabled, changes are automatically synced and the users are added or removed from the team.</span></span> <span data-ttu-id="cc9f8-121">工作组成员无法离开组织范围的团队。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-121">Team members can't leave an org-wide team.</span></span> <span data-ttu-id="cc9f8-122">作为团队所有者, 你可以根据需要手动添加或删除用户。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-122">As a team owner, you can manually add or remove users if needed.</span></span>

> [!NOTE]
> - <span data-ttu-id="cc9f8-123">如果在创建团队时看不到**组织范围**选项, 并且您是全局管理员, 则该功能可能仍在进行滚动, 或者你的组织可能超过5000个成员的当前大小限制。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-123">If you don't see the **Org-wide** option when creating a team and you're a global admin, the feature might still be rolling out or your organization might have more than the current size limit of 5,000 members.</span></span> <span data-ttu-id="cc9f8-124">我们希望将来增加此限额。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-124">We're looking to increase this limit in the future.</span></span>
> - <span data-ttu-id="cc9f8-125">不属于会议室列表、设备和资源帐户的会议室可能会添加或同步到组织范围的团队。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-125">Rooms that aren't a part of a room list, equipment, and resource accounts might be added or synced to the org-wide team.</span></span> <span data-ttu-id="cc9f8-126">团队所有者可以轻松地从团队中删除这些帐户。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-126">Team owners can easily remove these accounts from the team.</span></span>

## <a name="best-practices"></a><span data-ttu-id="cc9f8-127">最佳做法</span><span class="sxs-lookup"><span data-stu-id="cc9f8-127">Best practices</span></span>

<span data-ttu-id="cc9f8-128">为了充分利用组织范围的团队, 我们建议团队所有者执行下列操作。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-128">To get the most out of your org-wide team, we recommend team owners do the following.</span></span>

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a><span data-ttu-id="cc9f8-129">仅允许团队所有者发布到常规频道</span><span class="sxs-lookup"><span data-stu-id="cc9f8-129">Allow only team owners to post to the General channel</span></span>

<span data-ttu-id="cc9f8-130">只需将团队所有者发布到常规频道, 即可减少频道噪音。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-130">Reduce channel noise by having only team owners post to the General channel.</span></span> <span data-ttu-id="cc9f8-131">转到团队, 然后单击 " **̇̇̇更多选项** > "**管理团队**。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-131">Go to the team and click **˙˙˙ More options** > **Manage Team**.</span></span> <span data-ttu-id="cc9f8-132">在 "**设置**" 选项卡上, 单击 "**成员权限**" > 选择 "**仅所有者可以发布邮件**"。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-132">On the **Settings** tab, click **Member permissions** > select **Only owners can post messages**.</span></span>

### <a name="turn-off-team-and-team-name-mentions"></a><span data-ttu-id="cc9f8-133">关闭 @team 和 @ [团队名称] 提及</span><span class="sxs-lookup"><span data-stu-id="cc9f8-133">Turn off @team and @[team name] mentions</span></span>

 <span data-ttu-id="cc9f8-134">减少 @mentions 使其避免整个组织的过载。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-134">Reduce @mentions to keep them from overloading the entire organization.</span></span> <span data-ttu-id="cc9f8-135">转到团队, 然后单击 " **̇̇̇更多选项** > "**管理团队**。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-135">Go to the team and click **˙˙˙ More options** > **Manage Team**.</span></span> <span data-ttu-id="cc9f8-136">在 "**设置**" 选项卡上, 单击 " <strong>@mentions</strong> " > 关闭 **"显示成员" 选项 @team 或 @ [团队名称]**。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-136">On the **Settings** tab, click <strong>@mentions</strong> > turn off **Show members the option to @team or @[team name]**.</span></span> 

### <a name="automatically-favorite-important-channels"></a><span data-ttu-id="cc9f8-137">自动收藏重要频道</span><span class="sxs-lookup"><span data-stu-id="cc9f8-137">Automatically favorite important channels</span></span>

<span data-ttu-id="cc9f8-138">收藏的重要频道, 确保您的组织中的每个人都参与特定对话。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-138">Favorite important channels to ensure everyone in your organization engages in specific conversations.</span></span> <span data-ttu-id="cc9f8-139">若要了解详细信息, 请参阅[整个团队的自动常用频道](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-139">To learn more, see [Auto-favorite channels for the whole team](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).</span></span>

### <a name="set-up-channel-moderation"></a><span data-ttu-id="cc9f8-140">设置频道裁决</span><span class="sxs-lookup"><span data-stu-id="cc9f8-140">Set up channel moderation</span></span>

<span data-ttu-id="cc9f8-141">考虑设置渠道裁决并向特定团队成员提供版主功能。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-141">Consider setting up channel moderation and giving moderator capabilities to certain team members.</span></span> <span data-ttu-id="cc9f8-142">(如果设置了 "裁决", 团队所有者将自动获得仲裁人功能。)审阅人可以控制哪些人可以在频道中开始新文章、添加和删除审阅人、控制团队成员是否可以答复现有频道邮件以及控制机器人和连接器是否可以提交频道消息。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-142">(When moderation is set up, team owners are given moderator capabilities automatically.) Moderators can control who can start a new post in a channel, add and remove moderators, control whether team members can reply to existing channel messages, and control whether bots and connectors can submit channel messages.</span></span> <span data-ttu-id="cc9f8-143">有关详细信息, 请参阅[在 Microsoft 团队中设置和管理通道裁决](manage-channel-moderation-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-143">For more information, see [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md).</span></span>

### <a name="remove-accounts-that-might-not-belong"></a><span data-ttu-id="cc9f8-144">删除可能不属于的帐户</span><span class="sxs-lookup"><span data-stu-id="cc9f8-144">Remove accounts that might not belong</span></span>

<span data-ttu-id="cc9f8-145">即使成员不能离开组织范围的团队, 作为团队所有者, 你可以通过删除不属于的帐户来管理团队名单。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-145">Even though members can’t leave an org-wide team, as a team owner, you can manage the team roster by removing accounts that don’t belong.</span></span> <span data-ttu-id="cc9f8-146">请确保使用团队从组织范围内的团队中删除用户。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-146">Make sure you use Teams to remove users from your org-wide team.</span></span> <span data-ttu-id="cc9f8-147">如果您使用另一种方法来删除用户 (如 Microsoft 365 管理中心或 Outlook 中的组), 则该用户可能会添加回组织范围的团队。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-147">If you use another way to remove a user, such as the Microsoft 365 admin center or from a group in Outlook, the user might be added back to the org-wide team.</span></span>

## <a name="faq"></a><span data-ttu-id="cc9f8-148">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="cc9f8-148">FAQ</span></span>

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a><span data-ttu-id="cc9f8-149">是否有一种方法可用于创建组织范围之外的团队, 而不是使用团队客户端？</span><span class="sxs-lookup"><span data-stu-id="cc9f8-149">Is there a way to create an org-wide team other than using the Teams client?</span></span>

<span data-ttu-id="cc9f8-150">全局管理员只能通过使用团队客户端来创建组织范围的团队。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-150">Global admins can only create an org-wide team by using the Teams client.</span></span> <span data-ttu-id="cc9f8-151">如果你的组织限制创建团队使用 PowerShell, 则建议的解决方法是将全局管理员添加到可以创建团队的用户的安全组。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-151">If your organization limits creating teams to using PowerShell, the recommended workaround is to add your global admins to the security group of users who can create a team.</span></span> <span data-ttu-id="cc9f8-152">有关详细信息，请参阅[管理哪些人可以创建 Office 365 组](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-152">For more information, see [Manage who can create Office 365 Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups).</span></span>

<span data-ttu-id="cc9f8-153">如果这不是一个选项, 则可以使用 PowerShell 创建公共团队, 并将全局管理员添加为团队所有者。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-153">If this isn't an option, you can use PowerShell to create a public team and add a global admin as the team owner.</span></span> <span data-ttu-id="cc9f8-154">然后, 让全局管理员单击团队名称旁边的 "**更多选项**", 单击 "**编辑团队**", 然后将隐私更改为组织范围内的**所有人都将自动添加**。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-154">Then, have the global admin click **More options** next to the team name, click **Edit team**, and then change the privacy to **Org-wide - Everyone in your organization will be automatically added**.</span></span> <span data-ttu-id="cc9f8-155">请注意, 只有团队所有者可以访问 "**编辑团队**" 选项, 并且只有全局管理员才能看到**组织范围**的选项。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-155">Note that only team owners can access the **Edit team** option and only global admins can see the **Org-wide** option.</span></span>

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a><span data-ttu-id="cc9f8-156">是否有办法将现有团队转换为组织范围的团队？</span><span class="sxs-lookup"><span data-stu-id="cc9f8-156">Is there a way to convert an existing team to an org-wide team?</span></span>

<span data-ttu-id="cc9f8-157">全局管理员可以通过在团队客户端中编辑现有团队, 将其转换为组织范围的团队。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-157">Global admins can convert an existing team to an org-wide team by editing it in Teams client.</span></span> <span data-ttu-id="cc9f8-158">转到团队名称, 单击 "**更多选项** > "**编辑团队**。</span><span class="sxs-lookup"><span data-stu-id="cc9f8-158">Go to the team name, click **More options** > **Edit team**.</span></span>
