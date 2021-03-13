---
title: 在 Microsoft Teams 中管理大型团队 - 最佳做法
ms.reviewer: abgupta
author: lolaj
ms.author: serdars
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 了解在 Microsoft Teams 中管理大型团队的最佳实践，以满足组织的需求。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 52b1e50cfd29aa6916f7b816f3639953d27d6526
ms.sourcegitcommit: da2a70a9b5e05d0fd7ecc150b451f5805667514c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/12/2021
ms.locfileid: "50756238"
---
<a name="manage-large-teams-in-microsoft-teams---best-practices"></a><span data-ttu-id="33ee3-103">在 Microsoft Teams 中管理大型团队 - 最佳做法</span><span class="sxs-lookup"><span data-stu-id="33ee3-103">Manage large teams in Microsoft Teams - Best practices</span></span>
======================================================

<span data-ttu-id="33ee3-104">Microsoft Teams 在促进具有数十个成员和具有数千个成员的大型组之间的通信方面同样有效。</span><span class="sxs-lookup"><span data-stu-id="33ee3-104">Microsoft Teams is equally effective at facilitating communications between small groups with dozens of members and large groups with thousands of members.</span></span> <span data-ttu-id="33ee3-105">有关 [团队大小更新，](limits-specifications-teams.md) 请查看 Teams 的限制和规范。</span><span class="sxs-lookup"><span data-stu-id="33ee3-105">Review [Limits and specifications for Teams](limits-specifications-teams.md) for updates on team sizes.</span></span> <span data-ttu-id="33ee3-106">团队规模增加会导致独特的管理和运营挑战。</span><span class="sxs-lookup"><span data-stu-id="33ee3-106">Increase in team size leads to unique management and operational challenges.</span></span> <span data-ttu-id="33ee3-107">本文介绍创建和管理由数千个成员组成的大型团队的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="33ee3-107">This article describes best practices for creating and managing large teams comprised of thousands of members.</span></span>

## <a name="value-of-large-teams"></a><span data-ttu-id="33ee3-108">大型团队的价值</span><span class="sxs-lookup"><span data-stu-id="33ee3-108">Value of large teams</span></span>

<span data-ttu-id="33ee3-109">大型团队在启用以下协作方案方面非常有用：</span><span class="sxs-lookup"><span data-stu-id="33ee3-109">Large teams are very useful in enabling the following collaboration scenarios:</span></span>

- <span data-ttu-id="33ee3-110">**部门范围的协作**：如果组织有多个部门（如财务、运营、R&D 等），可以创建一个包含特定部门所有成员的团队。</span><span class="sxs-lookup"><span data-stu-id="33ee3-110">**Department-wide collaboration**: If your organization has multiple departments such as Finance, Operations, R&D etc., then you can create a single team that includes all members in a specific department.</span></span> <span data-ttu-id="33ee3-111">现在，可以在此团队中共享与部门相关的所有通信，这便于成员即时联系和参与。</span><span class="sxs-lookup"><span data-stu-id="33ee3-111">Now all communications relevant to a department can be shared in this team, which facilitates instant reach and engagement from members.</span></span>

- <span data-ttu-id="33ee3-112">**员工资源组协作**：组织通常有一大群共同感兴趣的人员，这些人员属于不同的部门或工作组。</span><span class="sxs-lookup"><span data-stu-id="33ee3-112">**Collaboration in employee resource groups**: Organizations often have large groups of people with mutual interests who belong to a different department or work group.</span></span> <span data-ttu-id="33ee3-113">例如，可以有一组人对个人财务和投资有一种热情。</span><span class="sxs-lookup"><span data-stu-id="33ee3-113">As an example, there can be a group of people who share a passion for personal finance and investing.</span></span> <span data-ttu-id="33ee3-114">在大型组织中连接通常很难。</span><span class="sxs-lookup"><span data-stu-id="33ee3-114">It's often hard to connect in a large organization.</span></span> <span data-ttu-id="33ee3-115">若要为此类组开发社区，租户管理员可以创建一个大型团队，充当公司范围内任何人都可以加入和利用的公共资源组。</span><span class="sxs-lookup"><span data-stu-id="33ee3-115">To develop communities for such groups, tenant admins can create a large team that serves as a public company-wide resource group that anyone can join and take advantage of.</span></span> <span data-ttu-id="33ee3-116">最终，这些社区收集新成员和现有成员都可以享受的信息。</span><span class="sxs-lookup"><span data-stu-id="33ee3-116">Eventually, these communities collect information that both new and existing members can enjoy.</span></span>

- <span data-ttu-id="33ee3-117">**内部和外部成员之间的协作**：热门产品通常开发一个早期采用者社区，这些用户希望尝试新产品发布并提供反馈。</span><span class="sxs-lookup"><span data-stu-id="33ee3-117">**Collaboration between internal and external members**: Popular products often develop a community of early adopters who are eager to try new product releases and provide feedback.</span></span> <span data-ttu-id="33ee3-118">早期采用者与产品组发展关系，帮助塑造产品。</span><span class="sxs-lookup"><span data-stu-id="33ee3-118">Early adopters develop a relationship with product groups to help shape the product.</span></span> <span data-ttu-id="33ee3-119">在这种情况下，租户管理员可以设置包括内部产品组和外部产品评估人员的大型团队，以简化丰富的产品开发过程。</span><span class="sxs-lookup"><span data-stu-id="33ee3-119">In such scenarios, tenant admins can set up a large team which includes both internal product groups and external product evaluators to facilitate a rich product development process.</span></span> <span data-ttu-id="33ee3-120">这些团队还可以为一组选定客户提供客户支持。</span><span class="sxs-lookup"><span data-stu-id="33ee3-120">These teams can also provide customer support to a select set of customers.</span></span>

## <a name="create-teams-from-existing-groups"></a><span data-ttu-id="33ee3-121">从现有组创建团队</span><span class="sxs-lookup"><span data-stu-id="33ee3-121">Create teams from existing groups</span></span>

<span data-ttu-id="33ee3-122">使用联系人组、安全组或 Office 组快速启动团队。</span><span class="sxs-lookup"><span data-stu-id="33ee3-122">Use contact groups, security groups, or Office groups to jump start your team.</span></span> <span data-ttu-id="33ee3-123">可以导入组以创建团队，也可以从 Office 组创建团队。</span><span class="sxs-lookup"><span data-stu-id="33ee3-123">You can import a group to make a team or create a team from an Office group.</span></span>

<span data-ttu-id="33ee3-124">**导入组以** 创建团队：将最多 3，500 个成员的组导入 Teams 时，Teams 会自动计算组中成员的总数。</span><span class="sxs-lookup"><span data-stu-id="33ee3-124">**Import a group to make a team**: When you import a group with up to 3,500 members into Teams, Teams automatically calculates the total number of members in the group.</span></span> <span data-ttu-id="33ee3-125">这是一次导入，组的未来更改不会在 Teams 中自动更新。</span><span class="sxs-lookup"><span data-stu-id="33ee3-125">This is a one-time import only and future changes in the group will not automatically be updated in Teams.</span></span>

<span data-ttu-id="33ee3-126">**从大型 Microsoft 365** 组创建团队：从大型 Microsoft 365 组创建团队时，成员自动成为 Microsoft 365组和团队的一部分。</span><span class="sxs-lookup"><span data-stu-id="33ee3-126">**Create a team from a large Microsoft 365 group**: When you create a team from a large Microsoft 365 group, members are automatically part of the Microsoft 365 group **and** the team.</span></span> <span data-ttu-id="33ee3-127">将来，当团队成员加入或离开 Microsoft 365 组时，将自动添加或删除他们。</span><span class="sxs-lookup"><span data-stu-id="33ee3-127">In the future, as team members join or leave the Microsoft 365 group, they're automatically added or removed from the team.</span></span>

## <a name="bulk-importexportremove-members-in-a-team"></a><span data-ttu-id="33ee3-128">批量导入/导出/删除团队中的成员</span><span class="sxs-lookup"><span data-stu-id="33ee3-128">Bulk import/export/remove members in a team</span></span>

<span data-ttu-id="33ee3-129">Azure 门户允许用户批量导入/导出/删除 Microsoft 365 组中的成员。</span><span class="sxs-lookup"><span data-stu-id="33ee3-129">The Azure portal allows users to bulk import/export/remove members in a Microsoft 365 Group.</span></span> <span data-ttu-id="33ee3-130">有关详细信息，请参阅批量 [导入组成员](https://docs.microsoft.com/azure/active-directory/enterprise-users/groups-bulk-import-members#to-bulk-import-group-members)。</span><span class="sxs-lookup"><span data-stu-id="33ee3-130">For more information, see [To bulk import group members](https://docs.microsoft.com/azure/active-directory/enterprise-users/groups-bulk-import-members#to-bulk-import-group-members).</span></span>

<span data-ttu-id="33ee3-131">由于每个团队都由 Microsoft 365 组支持，因此可以使用 Azure 门户在对应于该团队的组中执行这些操作。</span><span class="sxs-lookup"><span data-stu-id="33ee3-131">Since every team is backed by a Microsoft 365 Group, you can use the Azure portal to perform these operations in the group corresponding to the team.</span></span> <span data-ttu-id="33ee3-132">成员操作将在 24 小时内反映在团队中。</span><span class="sxs-lookup"><span data-stu-id="33ee3-132">The member operations will be reflected in the team within 24 hours.</span></span>

## <a name="create-channels-to-focus-discussions"></a><span data-ttu-id="33ee3-133">创建以讨论为重点的频道</span><span class="sxs-lookup"><span data-stu-id="33ee3-133">Create channels to focus discussions</span></span>

<span data-ttu-id="33ee3-134">您可以通过创建重点频道来缩小组讨论范围。</span><span class="sxs-lookup"><span data-stu-id="33ee3-134">You can narrow the group discussions by creating focused channels.</span></span> <span data-ttu-id="33ee3-135">请参阅 [组织团队的最佳实践](best-practices-organizing.md)。</span><span class="sxs-lookup"><span data-stu-id="33ee3-135">See [Best practices for organizing teams](best-practices-organizing.md).</span></span>

## <a name="restrict-channel-creation"></a><span data-ttu-id="33ee3-136">限制通道创建</span><span class="sxs-lookup"><span data-stu-id="33ee3-136">Restrict channel creation</span></span>

<span data-ttu-id="33ee3-137">如果允许任何团队成员创建频道，该团队可以扩大频道。</span><span class="sxs-lookup"><span data-stu-id="33ee3-137">If any team member is allowed to create channels, that team can have channel sprawl.</span></span> <span data-ttu-id="33ee3-138">团队所有者应在"设置"和"成员权限"中为成员关闭 **>、更新、删除和还原**。</span><span class="sxs-lookup"><span data-stu-id="33ee3-138">Team owners should turn off channel create, update, delete, and restore for members in **Settings > Member permissions**.</span></span> <span data-ttu-id="33ee3-139">请参阅 [团队和频道概述](teams-channels-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="33ee3-139">See [Overview of teams and channels](teams-channels-overview.md).</span></span>

<span data-ttu-id="33ee3-140">![显示管理员控制台"设置"选项卡的"成员权限"部分的屏幕图像。](media/no-channel-creation.png "显示管理员控制台"设置"选项卡上成员权限部分的图像。"允许成员创建或删除频道"选项未选中。")</span><span class="sxs-lookup"><span data-stu-id="33ee3-140">![Screen image that shows the member permissions section of the admin console Settings tab.](media/no-channel-creation.png "Screen image that member permissions section of the admin console Settings tab. The allow members to create or delete channels options are unchecked.")</span></span>

## <a name="add-favorite-channels"></a><span data-ttu-id="33ee3-141">添加收藏频道</span><span class="sxs-lookup"><span data-stu-id="33ee3-141">Add favorite channels</span></span>

<span data-ttu-id="33ee3-142">为了加速新的用户参与和内容发现，可以选择默认可供用户使用的收藏频道。</span><span class="sxs-lookup"><span data-stu-id="33ee3-142">In order to speed up new user engagement and content discovery, you can select favorite channels that are available to the user by default.</span></span> <span data-ttu-id="33ee3-143">在 **管理中心的"** 频道"窗格中，检查"显示 **成员"列下的** 频道。</span><span class="sxs-lookup"><span data-stu-id="33ee3-143">In the **Channels** pane of the admin center, check the channels under the **Show for members** column.</span></span>

<span data-ttu-id="33ee3-144">![显示管理控制台的通道窗格的屏幕图像。](media/favorite-channels.png "显示管理控制台的通道窗格的屏幕图像。某些频道将选中"针对成员显示"。")</span><span class="sxs-lookup"><span data-stu-id="33ee3-144">![Screen image that shows the channels pane of the admin console.](media/favorite-channels.png "Screen image that shows channels pane of the admin console. Some channels are checked for Show for members.")</span></span>

 <span data-ttu-id="33ee3-145">有关详细信息 [，请参阅创建你的第一个团队](get-started-with-teams-create-your-first-teams-and-channels.md) 和频道。</span><span class="sxs-lookup"><span data-stu-id="33ee3-145">See [Create your first teams and channels](get-started-with-teams-create-your-first-teams-and-channels.md) for details.</span></span>

## <a name="regulate-applications-and-bots-in-large-teams"></a><span data-ttu-id="33ee3-146">管理大型团队中的应用程序和机器人</span><span class="sxs-lookup"><span data-stu-id="33ee3-146">Regulate applications and bots in large teams</span></span>

<span data-ttu-id="33ee3-147">为了防止添加让人分心的应用程序或机器人，团队所有者可以禁用、添加、删除和上传团队成员的应用和连接器。</span><span class="sxs-lookup"><span data-stu-id="33ee3-147">To prevent addition of distracting applications or bots, team owners can disable, add, remove, and upload apps and connectors for team members.</span></span> <span data-ttu-id="33ee3-148">在管理 **中心的"设置**">"成员权限"下，取消选中允许成员添加应用或连接器的三个选项。</span><span class="sxs-lookup"><span data-stu-id="33ee3-148">In the admin center under **Settings > Member permissions**, uncheck the three options that allow members to add apps or connectors.</span></span>

<span data-ttu-id="33ee3-149">![显示"设置"窗格的"成员权限"部分的屏幕图像。](media/disable-bots-connectors.png "显示"设置"窗格的"成员权限"部分的屏幕图像。将取消选中允许成员添加应用或连接器的选项。")</span><span class="sxs-lookup"><span data-stu-id="33ee3-149">![Screen image that shows the Member permissions section of the Settings pane.](media/disable-bots-connectors.png "Screen image that shows the Member permission section of the Settings pane. The options for allow members to add apps or connectors are unchecked.")</span></span>

<span data-ttu-id="33ee3-150">请参阅 [应用、机器人&连接器](deploy-apps-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="33ee3-150">See [Apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md).</span></span>

## <a name="regulate-team-and-channel-mentions"></a><span data-ttu-id="33ee3-151">管理团队和频道提及</span><span class="sxs-lookup"><span data-stu-id="33ee3-151">Regulate team and channel mentions</span></span>

<span data-ttu-id="33ee3-152">团队和频道提及可用于引起整个团队对某些频道帖子的注意。</span><span class="sxs-lookup"><span data-stu-id="33ee3-152">Team and channel mentions can be used to draw the attention of the whole team to certain channel posts.</span></span> <span data-ttu-id="33ee3-153">在帖子中使用提及后，会向成千上万的团队成员发送通知。</span><span class="sxs-lookup"><span data-stu-id="33ee3-153">Once a mention is used in a post, a notification is sent to thousands of team members.</span></span> <span data-ttu-id="33ee3-154">如果通知过于频繁，则团队成员可能会过载，并可能向团队所有者投诉。</span><span class="sxs-lookup"><span data-stu-id="33ee3-154">If the notifications are too frequent, then team members can become overloaded and might complain to team owners.</span></span> <span data-ttu-id="33ee3-155">若要阻止团队或频道提及，请通过取消选中团队"设置"窗格中的框来为成员关闭团队 **> @mentions** 提及。</span><span class="sxs-lookup"><span data-stu-id="33ee3-155">To prevent team or channel mentions, turn off team and channel mentions for members by unchecking the boxes in the teams **Settings > @mentions** pane.</span></span>

<span data-ttu-id="33ee3-156">![屏幕图像，显示"设置"窗格的"提及"部分。](media/no-at-mentions.png "屏幕图像，显示"设置"窗格的"提及"部分。取消选中显示和向成员授予提及访问权限的选项。")</span><span class="sxs-lookup"><span data-stu-id="33ee3-156">![Screen image that shows the at Mentions section of the Settings pane.](media/no-at-mentions.png "Screen image that shows the at Mentions section of the Settings pane. The options for show and give members access to at mentions are unchecked.")</span></span>

## <a name="consider-setting-up-moderation-in-your-channels"></a><span data-ttu-id="33ee3-157">考虑在频道中设置审核</span><span class="sxs-lookup"><span data-stu-id="33ee3-157">Consider setting up moderation in your channels</span></span>

<span data-ttu-id="33ee3-158">团队所有者可以对频道启用审核，以控制谁能在此频道中发起新帖子并回复帖子。</span><span class="sxs-lookup"><span data-stu-id="33ee3-158">Team owners can turn on moderation for a channel to control who can start new posts and reply to posts in that channel.</span></span> <span data-ttu-id="33ee3-159">设置审核后，可以选择一个或多个团队成员作为审核员。</span><span class="sxs-lookup"><span data-stu-id="33ee3-159">When you set up moderation, you can choose one or more team members to be moderators.</span></span> <span data-ttu-id="33ee3-160">默认情况下，团队所有者是审阅人。</span><span class="sxs-lookup"><span data-stu-id="33ee3-160">Team owners are moderators by default.</span></span> <span data-ttu-id="33ee3-161">有关详细信息，请参阅 [设置和管理频道审核](manage-channel-moderation-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="33ee3-161">For more information, see [Set up and manage channel moderation](manage-channel-moderation-in-teams.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="33ee3-162">相关主题</span><span class="sxs-lookup"><span data-stu-id="33ee3-162">Related topics</span></span>

- [<span data-ttu-id="33ee3-163">组织 Teams 的最佳实践</span><span class="sxs-lookup"><span data-stu-id="33ee3-163">Best practices for organizing Teams</span></span>](best-practices-organizing.md)
- [<span data-ttu-id="33ee3-164">创建组织范围的团队</span><span class="sxs-lookup"><span data-stu-id="33ee3-164">Create an org-wide team</span></span>](create-an-org-wide-team.md)
