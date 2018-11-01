---
title: 在 Microsoft 团队中创建一个组织范围团队
author: LanaChin
ms.author: v-lanac
ms.reviewer: Phecda
manager: serdars
ms.date: 09/27/2018
ms.topic: article
ms.service: msteams
search.appverid: MET150
description: 了解如何创建和管理团队中的组织范围团队。
localization_priority: Normal
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b432629d6f76167da1f497cf88ae711e7792b34
ms.sourcegitcommit: 6d30cfdd8c8b8908d4e4f278c39fd22062f4a888
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2018
ms.locfileid: "25890672"
---
# <a name="create-an-org-wide-team-in-microsoft-teams"></a><span data-ttu-id="8eb0d-103">在 Microsoft 团队中创建一个组织范围团队</span><span class="sxs-lookup"><span data-stu-id="8eb0d-103">Create an org-wide team in Microsoft Teams</span></span>

<span data-ttu-id="8eb0d-104">组织范围团队提供的小型到中型组织成为进行协作的单个工作组中的每个人的自动方法。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-104">Org-wide teams provide an automatic way for everyone in a small to medium-sized organization to be a part of a single team for collaboration.</span></span> 
 
<span data-ttu-id="8eb0d-105">与组织范围团队全局管理员可以轻松创建拉入组织中的每个用户保留成员的最新的 Active Directory 作为用户加入和离开组织的公共团队。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-105">With org-wide teams, global administrators can easily create a public team that pulls in every user in the organization and keeps the membership up to date with Active Directory as users join and leave the organization.</span></span> <span data-ttu-id="8eb0d-106">仅全局管理员可创建组织范围团队和当前组织范围团队限于与不超过 1,000 个用户的组织。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-106">Only global admins can create org-wide teams and currently an org-wide team is limited to organizations with no more than 1,000 users.</span></span> <span data-ttu-id="8eb0d-107">如果满足这些要求，管理员将作为下**隐私**选项看到**组织范围内**，创建一个团队时。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-107">If these requirements are met, admins will see **Org-wide** as an option under **Privacy** when creating a team.</span></span>

<span data-ttu-id="8eb0d-108">![要创建一个组织范围团队的组织范围选项的屏幕截图](media/create-org-wide-team.png "要创建一个组织范围团队的组织范围选项的屏幕截图")</span><span class="sxs-lookup"><span data-stu-id="8eb0d-108">![Screen shot of the Org-wide option to create an org-wide team](media/create-org-wide-team.png "Screen shot of the Org-wide option to create an org-wide team")</span></span>

> [!NOTE]
> <span data-ttu-id="8eb0d-109">如果您是全局管理员创建团队时，看不到**组织范围**选项，该功能仍可能推出或您的组织可能具有超过 1000 个成员的当前大小限制。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-109">If you don't see the **Org-wide** option when creating a team and you're a global admin, the feature might still be rolling out or your organization might have more than the current size limit of 1,000 members.</span></span> <span data-ttu-id="8eb0d-110">我们希望在将来增加此限制。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-110">We're looking to increase this limit in future.</span></span>

<span data-ttu-id="8eb0d-111">创建一个组织范围团队后，所有的全局管理员添加作为团队所有者和所有活动用户将添加为工作组成员。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-111">When an org-wide team is created, all global admins are added as team owners and all active users are added as team members.</span></span> <span data-ttu-id="8eb0d-112">为团队、 来宾用户和大多数聊天室禁用的用户不会添加到团队。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-112">Users who are disabled for Teams, guest users, and most rooms aren't added to the team.</span></span> <span data-ttu-id="8eb0d-113">贵组织的目录将更新以包括新的活动用户或更改如果用户在贵公司不再起作用，并且禁用团队许可证，将自动同步，并添加或从组中删除用户。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-113">As your organization's directory is updated to include new active users or if users no longer work at your company and their Teams license is disabled, changes are automatically synced and the users are added or removed from the team.</span></span> <span data-ttu-id="8eb0d-114">工作组成员都能使组织范围团队。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-114">Team members can't leave an org-wide team.</span></span> <span data-ttu-id="8eb0d-115">作为团队所有者，您可以手动添加或删除用户，如果需要。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-115">As a team owner, you can manually add or remove users if needed.</span></span>

> [!NOTE]
> <span data-ttu-id="8eb0d-116">可能添加或与组织范围团队同步聊天室的不属于会议室列表、 equipment 和资源帐户。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-116">Rooms that aren't a part of a room list, equipment, and resource accounts might be added or synced to the org-wide team.</span></span> <span data-ttu-id="8eb0d-117">团队所有者可以轻松地从组中删除这些帐户。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-117">Team owners can easily remove these accounts from the team.</span></span>

## <a name="best-practices"></a><span data-ttu-id="8eb0d-118">最佳实践</span><span class="sxs-lookup"><span data-stu-id="8eb0d-118">Best practices</span></span>
<span data-ttu-id="8eb0d-119">若要充分利用您的组织范围团队，建议团队所有者执行下列操作。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-119">To get the most out of your org-wide team, we recommend team owners do the following.</span></span>

### <a name="allow-only-team-owners-to-post-to-the-general-channel"></a><span data-ttu-id="8eb0d-120">允许仅团队发布到常规通道所有者</span><span class="sxs-lookup"><span data-stu-id="8eb0d-120">Allow only team owners to post to the General channel</span></span>
<span data-ttu-id="8eb0d-121">减少通道干扰具有仅团队所有者发布到常规通道。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-121">Reduce channel noise by having only team owners post to the General channel.</span></span> <span data-ttu-id="8eb0d-122">转接至小组和单击**更多选项 （...）** > **管理团队**。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-122">Go to the team and click **More options (…)** > **Manage Team**.</span></span> <span data-ttu-id="8eb0d-123">在**设置**选项卡，单击**成员权限**> 选择**仅所有者可以发布消息**。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-123">On the **Settings** tab, click **Member permissions** > select **Only owners can post messages**.</span></span>
### <a name="turn-off-team-and-team-name-mentions"></a><span data-ttu-id="8eb0d-124">关闭 @team 和 @ 提及 [工作组名称]</span><span class="sxs-lookup"><span data-stu-id="8eb0d-124">Turn off @team and @[team name] mentions</span></span>
 <span data-ttu-id="8eb0d-125">减少 @mentions 以防止它们重载整个组织。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-125">Reduce @mentions to keep them from overloading the entire organization.</span></span> <span data-ttu-id="8eb0d-126">转接至小组和单击**更多选项 （...）** > **管理团队**。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-126">Go to the team and click **More options (…)** > **Manage Team**.</span></span> <span data-ttu-id="8eb0d-127">在**设置**选项卡，单击 **@mentions** > 关闭**显示 @team 选项的成员或 @[工作组名称]**。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-127">On the **Settings** tab, click **@mentions** > turn off **Show members the option to @team or @[team name]**.</span></span> 
### <a name="automatically-favorite-important-channels"></a><span data-ttu-id="8eb0d-128">自动最喜爱的重要通道</span><span class="sxs-lookup"><span data-stu-id="8eb0d-128">Automatically favorite important channels</span></span>
 <span data-ttu-id="8eb0d-129">最喜爱的重要通道，以确保您的组织中的每个人参与了一个特定的对话。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-129">Favorite important channels to ensure everyone in your organization engages in specific conversations.</span></span> <span data-ttu-id="8eb0d-130">若要了解详细信息，请参阅[自动收藏夹通道，整个团队](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6)。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-130">To learn more, see [Auto-favorite channels for the whole team](https://support.office.com/article/auto-favorite-channels-for-the-whole-team-a948272c-5aa5-429c-863c-4e1e1cd6b0f6).</span></span>

### <a name="remove-accounts-that-might-not-belong"></a><span data-ttu-id="8eb0d-131">删除可能不属于的帐户</span><span class="sxs-lookup"><span data-stu-id="8eb0d-131">Remove accounts that might not belong</span></span>
<span data-ttu-id="8eb0d-132">即使成员无法保留组织范围团队，作为团队所有者，您可以通过删除不属于帐户管理团队名单。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-132">Even though members can’t leave an org-wide team, as a team owner, you can manage the team roster by removing accounts that don’t belong.</span></span> <span data-ttu-id="8eb0d-133">请确保您使用团队从您的组织范围团队中移除用户。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-133">Make sure you use Teams to remove users from your org-wide team.</span></span>  <span data-ttu-id="8eb0d-134">如果您使用另一种方式删除用户，如 Microsoft 365 管理中心或从组在 Outlook 中，用户可能会重新添加到组织范围团队。</span><span class="sxs-lookup"><span data-stu-id="8eb0d-134">If you use another way to remove a user, such as the Microsoft 365 admin center or from a group in Outlook, the user might be added back to the org-wide team.</span></span> 
