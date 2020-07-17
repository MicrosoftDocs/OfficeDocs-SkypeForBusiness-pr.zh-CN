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
description: 了解如何在团队中创建和管理组织范围内的团队，以便为中小型组织中的每个人提供自动方式进行协作。
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 222daeb76d24186078ac6a49581dbfb05f1711bd
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086219"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a><span data-ttu-id="c75cb-103">在 Microsoft Teams 中创建组织范围的团队</span><span class="sxs-lookup"><span data-stu-id="c75cb-103">Create an org-wide team in Microsoft Teams</span></span>

<span data-ttu-id="c75cb-104">组织范围的团队为中小型组织中的每个人提供了自动加入单个协作团队的方法。</span><span class="sxs-lookup"><span data-stu-id="c75cb-104">Org-wide teams provide an automatic way for everyone in a small to medium-sized organization to be a part of a single team for collaboration.</span></span>

<span data-ttu-id="c75cb-105">使用组织范围的团队，全局管理员可以轻松创建一个公共团队来将组织中的所有用户包含进来，并在用户加入和离开组织时在 Active Directory 中更新成员身份。</span><span class="sxs-lookup"><span data-stu-id="c75cb-105">With org-wide teams, global admins can easily create a public team that pulls in every user in the organization and keeps the membership up to date with Active Directory as users join and leave the organization.</span></span> <span data-ttu-id="c75cb-106">只有全局管理员可以创建组织范围的团队，当前组织范围的团队仅限于不超过5000用户的组织。</span><span class="sxs-lookup"><span data-stu-id="c75cb-106">Only global admins can create org-wide teams and currently, an org-wide team is limited to organizations with no more than 5,000 users.</span></span> <span data-ttu-id="c75cb-107">每个租户也有五个组织范围的团队的限制。</span><span class="sxs-lookup"><span data-stu-id="c75cb-107">There's also a limit of five org-wide teams per tenant.</span></span> <span data-ttu-id="c75cb-108">如果满足这些要求，则当全局管理员在创建团队时选择“**从头开始构建团队**”时，将看到“**组织范围**”选项。</span><span class="sxs-lookup"><span data-stu-id="c75cb-108">If these requirements are met, global admins will see **Org-wide** as an option when they select **Build a team from scratch** when creating a team.</span></span> 

<span data-ttu-id="c75cb-109">![用于创建组织范围团队的“组织范围”选项的屏幕截图](media/create-org-wide-team.png "用于创建组织范围团队的“组织范围”选项的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="c75cb-109">![Screenshot of the Org-wide option to create an org-wide team](media/create-org-wide-team.png "Screen shot of the Org-wide option to create an org-wide team")</span></span>

<span data-ttu-id="c75cb-110">创建组织范围的团队后，所有全局管理员都将添加为团队所有者，并且所有活动用户都会添加为团队成员。</span><span class="sxs-lookup"><span data-stu-id="c75cb-110">When an org-wide team is created, all global admins are added as team owners and all active users are added as team members.</span></span> <span data-ttu-id="c75cb-111">未经授权的用户也将添加到团队。</span><span class="sxs-lookup"><span data-stu-id="c75cb-111">Unlicensed users are also added to the team.</span></span> <span data-ttu-id="c75cb-112">当未经授权的用户第一次登录团队时，将为该用户分配 Microsoft 团队探索性许可证。</span><span class="sxs-lookup"><span data-stu-id="c75cb-112">The first time an unlicensed user signs in to Teams, the user is assigned a Microsoft Teams Exploratory license.</span></span> <span data-ttu-id="c75cb-113">若要了解有关探索性许可证的详细信息，请参阅[管理 Microsoft 团队探索性许可证](teams-exploratory.md)。</span><span class="sxs-lookup"><span data-stu-id="c75cb-113">To learn more about the Exploratory license, check out [Manage the Microsoft Teams Exploratory license](teams-exploratory.md).</span></span> 

<span data-ttu-id="c75cb-114">以下类型的帐户无法添加到组织范围的团队：</span><span class="sxs-lookup"><span data-stu-id="c75cb-114">These types of accounts won't be added to your org-wide team:</span></span>

- <span data-ttu-id="c75cb-115">阻止登录的帐户</span><span class="sxs-lookup"><span data-stu-id="c75cb-115">Accounts that are blocked from sign in</span></span>
- <span data-ttu-id="c75cb-116">来宾用户</span><span class="sxs-lookup"><span data-stu-id="c75cb-116">Guest users</span></span>
- <span data-ttu-id="c75cb-117">服务帐户</span><span class="sxs-lookup"><span data-stu-id="c75cb-117">Service accounts</span></span>
- <span data-ttu-id="c75cb-118">会议室或设备帐户</span><span class="sxs-lookup"><span data-stu-id="c75cb-118">Room or equipment accounts</span></span>
- <span data-ttu-id="c75cb-119">共享邮箱支持的帐户</span><span class="sxs-lookup"><span data-stu-id="c75cb-119">Accounts backed by a shared mailbox</span></span>

<span data-ttu-id="c75cb-120">当组织目录更新为包含新的活动用户时，或者如果用户不再在公司工作并且其帐户已被禁用，系统会自动同步更改，并从团队中添加或删除用户。</span><span class="sxs-lookup"><span data-stu-id="c75cb-120">As your organization's directory is updated to include new active users or if users no longer work at your company and their account is disabled, changes are automatically synced and the users are added or removed from the team.</span></span> <span data-ttu-id="c75cb-121">团队成员无法离开组织范围的团队。</span><span class="sxs-lookup"><span data-stu-id="c75cb-121">Team members can't leave an org-wide team.</span></span> <span data-ttu-id="c75cb-122">作为团队所有者，你可以根据需要手动添加或删除用户。</span><span class="sxs-lookup"><span data-stu-id="c75cb-122">As a team owner, you can manually add or remove users if needed.</span></span>

> [!NOTE]
> - <span data-ttu-id="c75cb-123">如果在创建团队时看不到**组织范围**选项，并且您是全局管理员，则你可能已达到5个组织范围的团队限制，或者你的组织可能超过了5000个成员的当前大小限制。</span><span class="sxs-lookup"><span data-stu-id="c75cb-123">If you don't see the **Org-wide** option when creating a team and you're a global admin, you might have reached the five org-wide teams limit, or your organization might have more than the current size limit of 5,000 members.</span></span> <span data-ttu-id="c75cb-124">我们想要在未来增加此限制。</span><span class="sxs-lookup"><span data-stu-id="c75cb-124">We're looking to increase this limit in the future.</span></span> <span data-ttu-id="c75cb-125">对于 Teams 教育版，组织范围的团队不可用。</span><span class="sxs-lookup"><span data-stu-id="c75cb-125">Org-wide teams aren't yet available for Teams for Education.</span></span>
> - <span data-ttu-id="c75cb-126">未出现在会议室列表中的会议室、设备和资源帐户可能会添加或同步到组织范围的团队。</span><span class="sxs-lookup"><span data-stu-id="c75cb-126">Rooms that aren't a part of a room list, equipment, and resource accounts might be added or synced to the org-wide team.</span></span> <span data-ttu-id="c75cb-127">团队所有者可轻松从团队中删除这些帐户。</span><span class="sxs-lookup"><span data-stu-id="c75cb-127">Team owners can easily remove these accounts from the team.</span></span>
> - <span data-ttu-id="c75cb-128">系统添加或删除成员的所有操作均发布在常规频道中。</span><span class="sxs-lookup"><span data-stu-id="c75cb-128">All actions by the system to add or remove members are posted in the General channel.</span></span> <span data-ttu-id="c75cb-129">该频道还将在 Teams 客户端中标记为具有新活动。</span><span class="sxs-lookup"><span data-stu-id="c75cb-129">The channel will also be marked as having new activity in the Teams client.</span></span>
> - <span data-ttu-id="c75cb-130">如果你的组织刚开始使用 Teams，且用户数不超过 5,000，我们将自动为贵组织创建一个组织范围的团队。</span><span class="sxs-lookup"><span data-stu-id="c75cb-130">We'll automatically create an org-wide team for your organization if your organization is new to Teams and has no more than 5,000 users.</span></span> <span data-ttu-id="c75cb-131">团队名称将反映租户名称，并且具有常规频道。</span><span class="sxs-lookup"><span data-stu-id="c75cb-131">The team name will reflect the tenant name and will have a General channel.</span></span> <span data-ttu-id="c75cb-132">全局管理员可像任何其他团队一样编辑此团队。</span><span class="sxs-lookup"><span data-stu-id="c75cb-132">Global admins can edit this team like any other team.</span></span> 

## <a name="best-practices"></a><span data-ttu-id="c75cb-133">最佳做法</span><span class="sxs-lookup"><span data-stu-id="c75cb-133">Best practices</span></span>

<span data-ttu-id="c75cb-134">若要充分利用组织范围的团队，建议团队所有者执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="c75cb-134">To get the most out of your org-wide team, we recommend team owners do the following.</span></span>

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a><span data-ttu-id="c75cb-135">仅允许团队所有者发布到常规频道</span><span class="sxs-lookup"><span data-stu-id="c75cb-135">Allow only team owners to post to the General channel</span></span>

<span data-ttu-id="c75cb-136">通过仅允许团队所有者发布到常规频道，减少频道中的杂乱信息。</span><span class="sxs-lookup"><span data-stu-id="c75cb-136">Reduce channel noise by having only team owners post to the General channel.</span></span> <span data-ttu-id="c75cb-137">转到团队并单击“**˙˙˙ 更多选项**” > “**管理团队**”。</span><span class="sxs-lookup"><span data-stu-id="c75cb-137">Go to the team and click **˙˙˙ More options** > **Manage Team**.</span></span> <span data-ttu-id="c75cb-138">在“**设置**”选项卡上，单击“**成员权限**”>选择“**仅所有者可以发布消息**”。</span><span class="sxs-lookup"><span data-stu-id="c75cb-138">On the **Settings** tab, click **Member permissions** > select **Only owners can post messages**.</span></span>

### <a name="turn-off-team-and-team-name-mentions"></a><span data-ttu-id="c75cb-139">关闭 @团队和 @[团队名称]提及</span><span class="sxs-lookup"><span data-stu-id="c75cb-139">Turn off @team and @[team name] mentions</span></span>

 <span data-ttu-id="c75cb-140">减少 @提及，以防止它们使整个组织超载。</span><span class="sxs-lookup"><span data-stu-id="c75cb-140">Reduce @mentions to keep them from overloading the entire organization.</span></span> <span data-ttu-id="c75cb-141">转到团队并单击“**˙˙˙ 更多选项**” > “**管理团队**”。</span><span class="sxs-lookup"><span data-stu-id="c75cb-141">Go to the team and click **˙˙˙ More options** > **Manage Team**.</span></span> <span data-ttu-id="c75cb-142">在“**设置**”选项卡上，单击“<strong>@提及</strong>”>关闭“**向成员显示用于 @团队或 @[团队名称]的选项**”。</span><span class="sxs-lookup"><span data-stu-id="c75cb-142">On the **Settings** tab, click <strong>@mentions</strong> > turn off **Show members the option to @team or @[team name]**.</span></span> 

### <a name="automatically-show-important-channels"></a><span data-ttu-id="c75cb-143">自动显示重要频道</span><span class="sxs-lookup"><span data-stu-id="c75cb-143">Automatically show important channels</span></span>

<span data-ttu-id="c75cb-144">显示重要频道，以确保组织中的每个人都能参与特定对话。</span><span class="sxs-lookup"><span data-stu-id="c75cb-144">Show important channels to ensure everyone in your organization engages in specific conversations.</span></span> <span data-ttu-id="c75cb-145">若要了解详细信息，请参阅[为整个团队自动收藏频道](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)。</span><span class="sxs-lookup"><span data-stu-id="c75cb-145">To learn more, see [Auto-favorite channels for the whole team](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).</span></span> 

### <a name="set-up-channel-moderation"></a><span data-ttu-id="c75cb-146">设置频道审阅</span><span class="sxs-lookup"><span data-stu-id="c75cb-146">Set up channel moderation</span></span>

<span data-ttu-id="c75cb-147">考虑设置频道审阅并向某些团队成员提供审阅人功能。</span><span class="sxs-lookup"><span data-stu-id="c75cb-147">Consider setting up channel moderation and giving moderator capabilities to certain team members.</span></span> <span data-ttu-id="c75cb-148">（设置审阅后，团队所有者将自动获得审阅人功能。）审阅人可以控制谁能够在频道中发布新帖子、添加和删除审阅人、控制团队成员是否可以回复现有频道消息，以及控制机器人和连接器是否可以提交频道消息。</span><span class="sxs-lookup"><span data-stu-id="c75cb-148">(When moderation is set up, team owners are given moderator capabilities automatically.) Moderators can control who can start a new post in a channel, add and remove moderators, control whether team members can reply to existing channel messages, and control whether bots and connectors can submit channel messages.</span></span> <span data-ttu-id="c75cb-149">有关详细信息，请参阅[在 Microsoft Teams 中设置和管理频道审核](manage-channel-moderation-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="c75cb-149">For more information, see [Set up and manage channel moderation in Microsoft Teams](manage-channel-moderation-in-teams.md).</span></span>

### <a name="remove-accounts-that-might-not-belong"></a><span data-ttu-id="c75cb-150">删除可能不属于成员的帐户</span><span class="sxs-lookup"><span data-stu-id="c75cb-150">Remove accounts that might not belong</span></span>

<span data-ttu-id="c75cb-151">即使成员不能离开组织范围的团队，作为团队所有者，你可以通过删除不属于的帐户来管理团队名单。</span><span class="sxs-lookup"><span data-stu-id="c75cb-151">Even though members can't leave an org-wide team, as a team owner, you can manage the team roster by removing accounts that don't belong.</span></span> <span data-ttu-id="c75cb-152">**请确保使用 Teams 从组织范围的团队中删除用户**。</span><span class="sxs-lookup"><span data-stu-id="c75cb-152">**Make sure you use Teams to remove users from your org-wide team**.</span></span> <span data-ttu-id="c75cb-153">如果使用其他方法删除用户（如 Microsoft 365 管理中心或 Outlook 中的组），则该用户可能会添加回组织范围的团队。</span><span class="sxs-lookup"><span data-stu-id="c75cb-153">If you use another way to remove a user, such as the Microsoft 365 admin center or from a group in Outlook, the user might be added back to the org-wide team.</span></span>

## <a name="faq"></a><span data-ttu-id="c75cb-154">常见问题</span><span class="sxs-lookup"><span data-stu-id="c75cb-154">FAQ</span></span>

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a><span data-ttu-id="c75cb-155">除了使用 Teams 客户端之外，是否有其他方法可以创建组织范围的团队？</span><span class="sxs-lookup"><span data-stu-id="c75cb-155">Is there a way to create an org-wide team other than using the Teams client?</span></span>

<span data-ttu-id="c75cb-156">全局管理员只能使用 Teams 客户端创建组织范围的团队。</span><span class="sxs-lookup"><span data-stu-id="c75cb-156">Global admins can only create an org-wide team by using the Teams client.</span></span> <span data-ttu-id="c75cb-157">如果贵组织将创建团队限制为使用 PowerShell，则建议的解决方法是将全局管理员添加到可以创建团队的用户安全组中。</span><span class="sxs-lookup"><span data-stu-id="c75cb-157">If your organization limits creating teams to using PowerShell, the recommended workaround is to add your global admins to the security group of users who can create a team.</span></span> <span data-ttu-id="c75cb-158">有关详细信息，请参阅[管理可以创建组的人员](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups)。</span><span class="sxs-lookup"><span data-stu-id="c75cb-158">For more information, see [Manage who can create groups](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups).</span></span>

<span data-ttu-id="c75cb-159">如果这样做行不通，则可以使用 PowerShell 创建公共团队，并将全局管理员添加为团队所有者。</span><span class="sxs-lookup"><span data-stu-id="c75cb-159">If this isn't an option, you can use PowerShell to create a public team and add a global admin as the team owner.</span></span> <span data-ttu-id="c75cb-160">然后，让全局管理员单击团队名称旁边的“**更多选项**”，单击“**编辑团队**”，然后将隐私更改为“**组织范围 - 将自动添加你的组织中的所有人**”。</span><span class="sxs-lookup"><span data-stu-id="c75cb-160">Then, have the global admin click **More options** next to the team name, click **Edit team**, and then change the privacy to **Org-wide - Everyone in your organization will be automatically added**.</span></span> <span data-ttu-id="c75cb-161">请注意，只有团队所有者才能访问“**编辑团队**”选项，并且只有全局管理员才能看到“**组织范围**”选项。</span><span class="sxs-lookup"><span data-stu-id="c75cb-161">Note that only team owners can access the **Edit team** option and only global admins can see the **Org-wide** option.</span></span>

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a><span data-ttu-id="c75cb-162">可通过某种方式将现有团队转换为组织范围的团队吗？</span><span class="sxs-lookup"><span data-stu-id="c75cb-162">Is there a way to convert an existing team to an org-wide team?</span></span>

<span data-ttu-id="c75cb-163">全局管理员可通过在 Teams 客户端中编辑来将现有团队转换为组织范围的团队。</span><span class="sxs-lookup"><span data-stu-id="c75cb-163">Global admins can convert an existing team to an org-wide team by editing it in Teams client.</span></span> <span data-ttu-id="c75cb-164">转到团队名称，单击“**更多选项**” > “**编辑团队**”。</span><span class="sxs-lookup"><span data-stu-id="c75cb-164">Go to the team name, click **More options** > **Edit team**.</span></span>

## <a name="see-also"></a><span data-ttu-id="c75cb-165">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c75cb-165">See also</span></span>

<span data-ttu-id="c75cb-166">观看有关[在 Microsoft Teams 中创建公司范围的团队](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3)的视频。</span><span class="sxs-lookup"><span data-stu-id="c75cb-166">Watch a video about about [creating a company-wide team in Microsoft Teams](https://support.office.com/article/037bb27a-bcc9-48fe-8d72-44d9482420a3).</span></span>
