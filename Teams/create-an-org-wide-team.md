---
title: 在 Microsoft Teams 中创建组织范围的团队
author: LanaChin
ms.author: v-lanac
ms.reviewer: phlouie
manager: serdars
ms.date: 09/27/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 了解如何在团队中创建和管理组织范围的团队。
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: b999419f8fec9c205ec9713181596fba1fb38999
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2019
ms.locfileid: "34494042"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a><span data-ttu-id="d7108-103">在 Microsoft Teams 中创建组织范围的团队</span><span class="sxs-lookup"><span data-stu-id="d7108-103">Create an org-wide team in Microsoft Teams</span></span>

<span data-ttu-id="d7108-104">组织范围的团队为一个规模较小的组织中的每个人提供自动方法, 以成为单个团队协作的一部分。</span><span class="sxs-lookup"><span data-stu-id="d7108-104">Org-wide teams provide an automatic way for everyone in a small to medium-sized organization to be a part of a single team for collaboration.</span></span> 
 
<span data-ttu-id="d7108-105">使用组织范围的团队, 全局管理员可以轻松地创建一个公共团队, 在组织中的每个用户都可以提取, 并在用户加入和离开组织时保持与 Active Directory 的成员身份保持最新。</span><span class="sxs-lookup"><span data-stu-id="d7108-105">With org-wide teams, global administrators can easily create a public team that pulls in every user in the organization and keeps the membership up to date with Active Directory as users join and leave the organization.</span></span> <span data-ttu-id="d7108-106">只有全局管理员可以创建组织范围的团队, 并且当前组织范围的团队仅限于不超过5000用户的组织。</span><span class="sxs-lookup"><span data-stu-id="d7108-106">Only global admins can create org-wide teams and currently an org-wide team is limited to organizations with no more than 5,000 users.</span></span> <span data-ttu-id="d7108-107">如果满足这些要求, 当创建团队时, 全局管理员会在选择 "**从头开始构建团队**" 时看到**组织范围**。</span><span class="sxs-lookup"><span data-stu-id="d7108-107">If these requirements are met, global admins will see **Org-wide** as an option when they select **Build a team from scratch** when creating a team.</span></span> 

<span data-ttu-id="d7108-108">![组织范围选项的屏幕截图, 用于创建组织范围的团队](media/create-org-wide-team.png "组织范围选项的屏幕截图, 用于创建组织范围的团队")</span><span class="sxs-lookup"><span data-stu-id="d7108-108">![Screen shot of the Org-wide option to create an org-wide team](media/create-org-wide-team.png "Screen shot of the Org-wide option to create an org-wide team")</span></span>

<span data-ttu-id="d7108-109">创建组织范围的团队后, 所有全局管理员都将添加为团队所有者, 并将所有活动用户添加为团队成员。</span><span class="sxs-lookup"><span data-stu-id="d7108-109">When an org-wide team is created, all global admins are added as team owners and all active users are added as team members.</span></span> <span data-ttu-id="d7108-110">对于团队、来宾用户和大多数聊天室禁用的用户不会添加到团队。</span><span class="sxs-lookup"><span data-stu-id="d7108-110">Users who are disabled for Teams, guest users, and most rooms aren't added to the team.</span></span> <span data-ttu-id="d7108-111">由于您的组织的目录已更新为包括新的活动用户, 或者如果用户在您的公司中不再工作, 并且他们的团队许可证已禁用, 则更改将自动同步, 并且用户将添加或从团队中删除。</span><span class="sxs-lookup"><span data-stu-id="d7108-111">As your organization's directory is updated to include new active users or if users no longer work at your company and their Teams license is disabled, changes are automatically synced and the users are added or removed from the team.</span></span> <span data-ttu-id="d7108-112">工作组成员无法离开组织范围的团队。</span><span class="sxs-lookup"><span data-stu-id="d7108-112">Team members can't leave an org-wide team.</span></span> <span data-ttu-id="d7108-113">作为团队所有者, 你可以根据需要手动添加或删除用户。</span><span class="sxs-lookup"><span data-stu-id="d7108-113">As a team owner, you can manually add or remove users if needed.</span></span>

> [!NOTE]
> - <span data-ttu-id="d7108-114">如果在创建团队时看不到**组织范围**选项, 并且您是全局管理员, 则该功能可能仍在进行滚动, 或者你的组织可能超过5000个成员的当前大小限制。</span><span class="sxs-lookup"><span data-stu-id="d7108-114">If you don't see the **Org-wide** option when creating a team and you're a global admin, the feature might still be rolling out or your organization might have more than the current size limit of 5,000 members.</span></span> <span data-ttu-id="d7108-115">我们希望今后增加此限额。</span><span class="sxs-lookup"><span data-stu-id="d7108-115">We're looking to increase this limit in future.</span></span>
> - <span data-ttu-id="d7108-116">不属于会议室列表、设备和资源帐户的会议室可能会添加或同步到组织范围的团队。</span><span class="sxs-lookup"><span data-stu-id="d7108-116">Rooms that aren't a part of a room list, equipment, and resource accounts might be added or synced to the org-wide team.</span></span> <span data-ttu-id="d7108-117">团队所有者可以轻松地从团队中删除这些帐户。</span><span class="sxs-lookup"><span data-stu-id="d7108-117">Team owners can easily remove these accounts from the team.</span></span>

## <a name="best-practices"></a><span data-ttu-id="d7108-118">最佳做法</span><span class="sxs-lookup"><span data-stu-id="d7108-118">Best practices</span></span>
<span data-ttu-id="d7108-119">为了充分利用组织范围的团队, 我们建议团队所有者执行下列操作。</span><span class="sxs-lookup"><span data-stu-id="d7108-119">To get the most out of your org-wide team, we recommend team owners do the following.</span></span>

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a><span data-ttu-id="d7108-120">仅允许团队所有者发布到常规频道</span><span class="sxs-lookup"><span data-stu-id="d7108-120">Allow only team owners to post to the General channel</span></span>
<span data-ttu-id="d7108-121">只需将团队所有者发布到常规频道, 即可减少频道噪音。</span><span class="sxs-lookup"><span data-stu-id="d7108-121">Reduce channel noise by having only team owners post to the General channel.</span></span> <span data-ttu-id="d7108-122">转到团队, 然后单击 "**更多选项 (...)** " > **管理团队**。</span><span class="sxs-lookup"><span data-stu-id="d7108-122">Go to the team and click **More options (…)** > **Manage Team**.</span></span> <span data-ttu-id="d7108-123">在 "**设置**" 选项卡上, 单击 "**成员权限**> 选择"**仅所有者可以发布邮件**"。</span><span class="sxs-lookup"><span data-stu-id="d7108-123">On the **Settings** tab, click **Member permissions** > select **Only owners can post messages**.</span></span>
### <a name="turn-off-team-and-team-name-mentions"></a><span data-ttu-id="d7108-124">关闭 @team 和 @ [团队名称] 提及</span><span class="sxs-lookup"><span data-stu-id="d7108-124">Turn off @team and @[team name] mentions</span></span>
 <span data-ttu-id="d7108-125">减少 @mentions 使其避免整个组织的过载。</span><span class="sxs-lookup"><span data-stu-id="d7108-125">Reduce @mentions to keep them from overloading the entire organization.</span></span> <span data-ttu-id="d7108-126">转到团队, 然后单击 "**更多选项 (...)** " > **管理团队**。</span><span class="sxs-lookup"><span data-stu-id="d7108-126">Go to the team and click **More options (…)** > **Manage Team**.</span></span> <span data-ttu-id="d7108-127">在 "**设置**" 选项卡上, 单击 " <strong>@mention</strong> > 关闭 **" 显示成员 "选项 @team 或 @ [团队名称]**。</span><span class="sxs-lookup"><span data-stu-id="d7108-127">On the **Settings** tab, click <strong>@mention</strong> > turn off **Show members the option to @team or @[team name]**.</span></span> 
### <a name="automatically-favorite-important-channels"></a><span data-ttu-id="d7108-128">自动收藏重要频道</span><span class="sxs-lookup"><span data-stu-id="d7108-128">Automatically favorite important channels</span></span>
 <span data-ttu-id="d7108-129">收藏的重要频道, 确保您的组织中的每个人都参与特定对话。</span><span class="sxs-lookup"><span data-stu-id="d7108-129">Favorite important channels to ensure everyone in your organization engages in specific conversations.</span></span> <span data-ttu-id="d7108-130">若要了解详细信息, 请参阅[整个团队的自动常用频道](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)。</span><span class="sxs-lookup"><span data-stu-id="d7108-130">To learn more, see [Auto-favorite channels for the whole team](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).</span></span>

### <a name="remove-accounts-that-might-not-belong"></a><span data-ttu-id="d7108-131">删除可能不属于的帐户</span><span class="sxs-lookup"><span data-stu-id="d7108-131">Remove accounts that might not belong</span></span>
<span data-ttu-id="d7108-132">即使成员不能离开组织范围的团队, 作为团队所有者, 你可以通过删除不属于的帐户来管理团队名单。</span><span class="sxs-lookup"><span data-stu-id="d7108-132">Even though members can’t leave an org-wide team, as a team owner, you can manage the team roster by removing accounts that don’t belong.</span></span> <span data-ttu-id="d7108-133">请确保使用团队从组织范围内的团队中删除用户。</span><span class="sxs-lookup"><span data-stu-id="d7108-133">Make sure you use Teams to remove users from your org-wide team.</span></span>  <span data-ttu-id="d7108-134">如果您使用另一种方法来删除用户 (如 Microsoft 365 管理中心或 Outlook 中的组), 则该用户可能会添加回组织范围的团队。</span><span class="sxs-lookup"><span data-stu-id="d7108-134">If you use another way to remove a user, such as the Microsoft 365 admin center or from a group in Outlook, the user might be added back to the org-wide team.</span></span> 

## <a name="faq"></a><span data-ttu-id="d7108-135">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="d7108-135">FAQ</span></span>

### <a name="is-there-a-way-to-create-an-org-wide-team-other-than-using-the-teams-client"></a><span data-ttu-id="d7108-136">是否有一种方法可用于创建组织范围之外的团队, 而不是使用团队客户端？</span><span class="sxs-lookup"><span data-stu-id="d7108-136">Is there a way to create an org-wide team other than using the Teams client?</span></span> 

<span data-ttu-id="d7108-137">全局管理员只能通过使用团队客户端来创建组织范围的团队。</span><span class="sxs-lookup"><span data-stu-id="d7108-137">Global admins can only create an org-wide team by using the Teams client.</span></span> <span data-ttu-id="d7108-138">如果你的组织限制创建团队使用 PowerShell, 则建议的解决方法是将全局管理员添加到可以创建团队的用户的安全组。</span><span class="sxs-lookup"><span data-stu-id="d7108-138">If your organization limits creating teams to using PowerShell, the recommended workaround is to add your global admins to the security group of users who can create a team.</span></span> <span data-ttu-id="d7108-139">有关详细信息，请参阅[管理哪些人可以创建 Office 365 组](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups)。</span><span class="sxs-lookup"><span data-stu-id="d7108-139">For more information, see [Manage who can create Office 365 Groups](https://docs.microsoft.com/office365/admin/create-groups/manage-creation-of-groups).</span></span> 

<span data-ttu-id="d7108-140">如果这不是一个选项, 则可以使用 PowerShell 创建公共团队, 并将全局管理员添加为团队所有者。</span><span class="sxs-lookup"><span data-stu-id="d7108-140">If this isn't an option, you can create a public team using PowerShell and add a global admin as the team owner.</span></span> <span data-ttu-id="d7108-141">然后, 让全局管理员单击 " **̇̇" ̇** "团队名称" 旁边的 "更多选项", 单击 "**编辑团队**", 然后将隐私更改为组织范围内的**所有人都将自动添加**。</span><span class="sxs-lookup"><span data-stu-id="d7108-141">Then, have the global admin click **˙˙˙ More options** next to the team name, click **Edit team**, and then change the privacy to **Org-wide - Everyone in your organization will be automatically added**.</span></span> <span data-ttu-id="d7108-142">请注意, 只有团队所有者可以访问 "**编辑团队**" 选项, 并且只有全局管理员才能看到**组织范围**的选项。</span><span class="sxs-lookup"><span data-stu-id="d7108-142">Note that only team owners can access the **Edit team** option and only global admins can see the **Org-wide** option.</span></span>

### <a name="is-there-a-way-to-convert-an-existing-team-to-an-org-wide-team"></a><span data-ttu-id="d7108-143">是否有办法将现有团队转换为组织范围的团队？</span><span class="sxs-lookup"><span data-stu-id="d7108-143">Is there a way to convert an existing team to an org-wide team?</span></span>

<span data-ttu-id="d7108-144">全局管理员可以将现有团队转换为组织范围内编辑团队客户端中的团队。</span><span class="sxs-lookup"><span data-stu-id="d7108-144">Global admins can convert an existing team to an org-wide team editing it in Teams client.</span></span>
<span data-ttu-id="d7108-145">转到团队名称, 然后单击 "更多选项 ..."(省略号) > "编辑团队"。</span><span class="sxs-lookup"><span data-stu-id="d7108-145">Go to the team name and click More options ...(ellipsis) > Edit team.</span></span>
