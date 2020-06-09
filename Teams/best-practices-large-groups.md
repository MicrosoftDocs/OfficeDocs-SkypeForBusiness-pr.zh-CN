---
title: 在 Microsoft 团队中管理大型团队-最佳做法
ms.reviewer: abgupta
author: lolaj
ms.author: lolaj
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
description: 了解在 Microsoft 团队中管理大型团队以满足组织的需求的最佳做法。
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d939b4be4fcd5f3a1045f2f9adde750197b92f29
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638902"
---
<a name="manage-large-teams-in-microsoft-teams---best-practices"></a><span data-ttu-id="2fd2a-103">在 Microsoft 团队中管理大型团队-最佳做法</span><span class="sxs-lookup"><span data-stu-id="2fd2a-103">Manage large teams in Microsoft Teams - Best practices</span></span>
======================================================

<span data-ttu-id="2fd2a-104">Microsoft 团队同样有效，可促进具有数十个成员的小型组与具有上千个成员的大型组之间的通信。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-104">Microsoft Teams is equally effective at facilitating communications between small groups with dozens of members and large groups with thousands of members.</span></span> <span data-ttu-id="2fd2a-105">查看团队有关团队规模更新的[限制和规范](limits-specifications-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-105">Review [Limits and specifications for Teams](limits-specifications-teams.md) for updates on team sizes.</span></span> <span data-ttu-id="2fd2a-106">团队规模的增加导致了独特的管理和运营挑战。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-106">Increase in team size leads to unique management and operational challenges.</span></span> <span data-ttu-id="2fd2a-107">本文介绍创建和管理数千个成员组成的大型团队的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-107">This article describes best practices for creating and managing large teams comprised of thousands of members.</span></span>

## <a name="value-of-large-teams"></a><span data-ttu-id="2fd2a-108">大型团队的价值</span><span class="sxs-lookup"><span data-stu-id="2fd2a-108">Value of large teams</span></span>

<span data-ttu-id="2fd2a-109">大型团队在启用以下协作方案方面非常有用：</span><span class="sxs-lookup"><span data-stu-id="2fd2a-109">Large teams are very useful in enabling the following collaboration scenarios:</span></span>

- <span data-ttu-id="2fd2a-110">**部门范围的协作**：如果您的组织具有多个部门（如财务、运营、&D 等），则可以创建一个团队，其中包含特定部门中的所有成员。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-110">**Department-wide collaboration**: If your organization has multiple departments such as Finance, Operations, R&D etc., then you can create a single team that includes all members in a specific department.</span></span> <span data-ttu-id="2fd2a-111">现在，与部门相关的所有通信都可以在此团队中共享，从而促进来自成员的即时访问和参与。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-111">Now all communications relevant to a department can be shared in this team, which facilitates instant reach and engagement from members.</span></span>

- <span data-ttu-id="2fd2a-112">**员工资源组中的协作**：组织通常具有属于不同部门或工作组的共同兴趣的大型用户组。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-112">**Collaboration in employee resource groups**: Organizations often have large groups of people with mutual interests who belong to a different department or work group.</span></span> <span data-ttu-id="2fd2a-113">例如，可以有一群人分享个人财务和投资的热情。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-113">As an example, there can be a group of people who share a passion for personal finance and investing.</span></span> <span data-ttu-id="2fd2a-114">在大型组织中，通常很难连接。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-114">It's often hard to connect in a large organization.</span></span> <span data-ttu-id="2fd2a-115">若要为此类组开发社区，租户管理员可以创建一个大型团队，作为任何人都可以加入和利用的公共公司范围的资源组。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-115">To develop communities for such groups, tenant admins can create a large team that serves as a public company-wide resource group that anyone can join and take advantage of.</span></span> <span data-ttu-id="2fd2a-116">最终，这些社区将收集新成员和现有成员都可以享用的信息。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-116">Eventually, these communities collect information that both new and existing members can enjoy.</span></span>

- <span data-ttu-id="2fd2a-117">**内部和外部成员之间的协作**：常用产品通常开发一个早期使用者社区，让他们积极尝试新产品版本并提供反馈。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-117">**Collaboration between internal and external members**: Popular products often develop a community of early adopters who are eager to try new product releases and provide feedback.</span></span> <span data-ttu-id="2fd2a-118">早期使用者开发与产品组之间的关系，以帮助形成产品。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-118">Early adopters develop a relationship with product groups to help shape the product.</span></span> <span data-ttu-id="2fd2a-119">在这种情况下，租户管理员可以设置一个包含内部产品组和外部产品评估程序的大型团队，以促进丰富的产品开发过程。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-119">In such scenarios, tenant admins can set up a large team which includes both internal product groups and external product evaluators to facilitate a rich product development process.</span></span> <span data-ttu-id="2fd2a-120">这些团队还可以向一组选定的客户提供客户支持。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-120">These teams can also provide customer support to a select set of customers.</span></span>

## <a name="create-teams-from-existing-groups"></a><span data-ttu-id="2fd2a-121">从现有组创建团队</span><span class="sxs-lookup"><span data-stu-id="2fd2a-121">Create teams from existing groups</span></span>

<span data-ttu-id="2fd2a-122">使用联系人组、安全组或 Office 组快速开始团队。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-122">Use contact groups, security groups, or Office groups to jump start your team.</span></span> <span data-ttu-id="2fd2a-123">可以导入组以从 Office 组中创建团队或创建团队。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-123">You can import a group to make a team or create a team from an Office group.</span></span>

<span data-ttu-id="2fd2a-124">**导入团队以创建团队**：将多达3500个成员的组导入到团队时，团队会自动计算组中的成员总数。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-124">**Import a group to make a team**: When you import a group with up to 3,500 members into Teams, Teams automatically calculates the total number of members in the group.</span></span> <span data-ttu-id="2fd2a-125">这只是一次性导入，组中的未来更改不会自动在团队中更新。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-125">This is a one-time import only and future changes in the group will not automatically be updated in Teams.</span></span>

<span data-ttu-id="2fd2a-126">**从大型 microsoft 365 组创建团队**：当您从大型 microsoft 365 组创建团队时，成员将自动成为 microsoft 365 组**和**团队的一部分。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-126">**Create a team from a large Microsoft 365 group**: When you create a team from a large Microsoft 365 group, members are automatically part of the Microsoft 365 group **and** the team.</span></span> <span data-ttu-id="2fd2a-127">将来，随着团队成员加入或离开 Microsoft 365 组，他们会自动添加或从团队中删除。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-127">In the future, as team members join or leave the Microsoft 365 group, they're automatically added or removed from the team.</span></span>

## <a name="create-channels-to-focus-discussions"></a><span data-ttu-id="2fd2a-128">创建以讨论为重点的频道</span><span class="sxs-lookup"><span data-stu-id="2fd2a-128">Create channels to focus discussions</span></span>

<span data-ttu-id="2fd2a-129">你可以通过创建重点频道缩小组讨论范围。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-129">You can narrow the group discussions by creating focused channels.</span></span> <span data-ttu-id="2fd2a-130">请参阅[组织团队的最佳做法](best-practices-organizing.md)。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-130">See [Best practices for organizing teams](best-practices-organizing.md).</span></span>

## <a name="restrict-channel-creation"></a><span data-ttu-id="2fd2a-131">限制频道创建</span><span class="sxs-lookup"><span data-stu-id="2fd2a-131">Restrict channel creation</span></span>

<span data-ttu-id="2fd2a-132">如果允许任何团队成员创建频道，则该团队可以有渠道蔓延。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-132">If any team member is allowed to create channels, that team can have channel sprawl.</span></span> <span data-ttu-id="2fd2a-133">团队所有者应为 "**设置 > 成员权限**" 中的成员关闭频道创建、更新、删除和还原。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-133">Team owners should turn off channel create, update, delete, and restore for members in **Settings > Member permissions**.</span></span> <span data-ttu-id="2fd2a-134">请参阅[团队和频道概述](teams-channels-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-134">See [Overview of teams and channels](teams-channels-overview.md).</span></span>

<span data-ttu-id="2fd2a-135">![显示 "管理控制台设置" 选项卡的 "成员权限" 部分的屏幕图像。](media/no-channel-creation.png ""管理控制台设置" 选项卡的 "成员权限" 部分的屏幕图像。"允许成员创建或删除频道" 选项处于未选中状态。")</span><span class="sxs-lookup"><span data-stu-id="2fd2a-135">![Screen image that shows the member permissions section of the admin console Settings tab.](media/no-channel-creation.png "Screen image that member permissions section of the admin console Settings tab. The allow members to create or delete channels options are unchecked.")</span></span>

## <a name="add-favorite-channels"></a><span data-ttu-id="2fd2a-136">添加常用频道</span><span class="sxs-lookup"><span data-stu-id="2fd2a-136">Add favorite channels</span></span>

<span data-ttu-id="2fd2a-137">为了加快新用户的参与和内容发现，你可以选择默认可供用户使用的常用频道。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-137">In order to speed up new user engagement and content discovery, you can select favorite channels that are available to the user by default.</span></span> <span data-ttu-id="2fd2a-138">在管理中心的 "**通道**" 窗格中，检查 "**成员显示**" 列下的频道。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-138">In the **Channels** pane of the admin center, check the channels under the **Show for members** column.</span></span>

<span data-ttu-id="2fd2a-139">![显示管理控制台的频道窗格的屏幕图像。](media/favorite-channels.png "显示管理员控制台的频道窗格的屏幕图像。将为成员选中 "显示" 部分频道。")</span><span class="sxs-lookup"><span data-stu-id="2fd2a-139">![Screen image that shows the channels pane of the admin console.](media/favorite-channels.png "Screen image that shows channels pane of the admin console. Some channels are checked for Show for members.")</span></span>

 <span data-ttu-id="2fd2a-140">有关详细信息，请参阅[创建您的第一个团队和频道](get-started-with-teams-create-your-first-teams-and-channels.md)。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-140">See [Create your first teams and channels](get-started-with-teams-create-your-first-teams-and-channels.md) for details.</span></span>

## <a name="regulate-applications-and-bots-in-large-teams"></a><span data-ttu-id="2fd2a-141">调节大型团队中的应用程序和机器人</span><span class="sxs-lookup"><span data-stu-id="2fd2a-141">Regulate applications and bots in large teams</span></span>

<span data-ttu-id="2fd2a-142">为了防止添加分散的应用程序或 bot，团队所有者可以禁用、添加、删除和上载团队成员的应用和连接器。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-142">To prevent addition of distracting applications or bots, team owners can disable, add, remove, and upload apps and connectors for team members.</span></span> <span data-ttu-id="2fd2a-143">在管理中心的 "**设置" > "成员权限**" 下，取消选中允许成员添加应用或连接器的三个选项。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-143">In the admin center under **Settings > Member permissions**, uncheck the three options that allow members to add apps or connectors.</span></span>

<span data-ttu-id="2fd2a-144">![显示 "设置" 窗格的 "成员权限" 部分的屏幕图像。](media/disable-bots-connectors.png "显示 "设置" 窗格的 "成员权限" 部分的屏幕图像。"允许成员添加应用或连接器" 的选项未选中。")</span><span class="sxs-lookup"><span data-stu-id="2fd2a-144">![Screen image that shows the Member permissions section of the Settings pane.](media/disable-bots-connectors.png "Screen image that shows the Member permission section of the Settings pane. The options for allow members to add apps or connectors are unchecked.")</span></span>

<span data-ttu-id="2fd2a-145">请参阅[应用、bot、& 连接器](deploy-apps-microsoft-teams-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-145">See [Apps, bots, & connectors](deploy-apps-microsoft-teams-landing-page.md).</span></span>

## <a name="regulate-team-and-channel-mentions"></a><span data-ttu-id="2fd2a-146">调节团队和频道提及</span><span class="sxs-lookup"><span data-stu-id="2fd2a-146">Regulate team and channel mentions</span></span>

<span data-ttu-id="2fd2a-147">团队和频道提及可用于将整个团队的注意力吸引到某些频道发布。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-147">Team and channel mentions can be used to draw the attention of the whole team to certain channel posts.</span></span> <span data-ttu-id="2fd2a-148">在帖子中使用提及后，会向数以千计的团队成员发送通知。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-148">Once a mention is used in a post, a notification is sent to thousands of team members.</span></span> <span data-ttu-id="2fd2a-149">如果通知太频繁，则团队成员可能会过载，并可能会向团队所有者发出投诉。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-149">If the notifications are too frequent, then team members can become overloaded and might complain to team owners.</span></span> <span data-ttu-id="2fd2a-150">若要防止团队或频道提及，请通过取消选中 "团队**设置" > @mentions**窗格中的框来关闭成员的团队和频道提及。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-150">To prevent team or channel mentions, turn off team and channel mentions for members by unchecking the boxes in the teams **Settings > @mentions** pane.</span></span>

<span data-ttu-id="2fd2a-151">![显示 "设置" 窗格中提及部分的屏幕图像。](media/no-at-mentions.png "显示 "设置" 窗格中提及部分的屏幕图像。未选中 "用于显示和授予成员对提及的访问权限" 选项。")</span><span class="sxs-lookup"><span data-stu-id="2fd2a-151">![Screen image that shows the at Mentions section of the Settings pane.](media/no-at-mentions.png "Screen image that shows the at Mentions section of the Settings pane. The options for show and give members access to at mentions are unchecked.")</span></span>

## <a name="consider-setting-up-moderation-in-your-channels"></a><span data-ttu-id="2fd2a-152">考虑在频道中设置审核</span><span class="sxs-lookup"><span data-stu-id="2fd2a-152">Consider setting up moderation in your channels</span></span>

<span data-ttu-id="2fd2a-153">团队所有者可以对频道启用审核，以控制谁能在此频道中发起新帖子并回复帖子。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-153">Team owners can turn on moderation for a channel to control who can start new posts and reply to posts in that channel.</span></span> <span data-ttu-id="2fd2a-154">设置审核后，可以选择一个或多个团队成员作为审核员。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-154">When you set up moderation, you can choose one or more team members to be moderators.</span></span> <span data-ttu-id="2fd2a-155">团队所有者默认为 "审阅者"。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-155">Team owners are moderators by default.</span></span> <span data-ttu-id="2fd2a-156">有关详细信息，请参阅[设置和管理通道裁决](manage-channel-moderation-in-teams.md)。</span><span class="sxs-lookup"><span data-stu-id="2fd2a-156">For more information, see [Set up and manage channel moderation](manage-channel-moderation-in-teams.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2fd2a-157">相关主题</span><span class="sxs-lookup"><span data-stu-id="2fd2a-157">Related topics</span></span>

- [<span data-ttu-id="2fd2a-158">组织团队的最佳做法</span><span class="sxs-lookup"><span data-stu-id="2fd2a-158">Best practices for organizing Teams</span></span>](best-practices-organizing.md)
- [<span data-ttu-id="2fd2a-159">创建组织范围的团队</span><span class="sxs-lookup"><span data-stu-id="2fd2a-159">Create an org-wide team</span></span>](create-an-org-wide-team.md)
