---
title: Microsoft 365 组和 Microsoft 团队
ms.reviewer: kblevins
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
audience: admin
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-apr2020
description: 了解 Microsoft 365 组和组成员如何与 Microsoft 团队一起工作。
ms.openlocfilehash: a4227432ab3557ca5e74ee5a769641185c1e432c
ms.sourcegitcommit: f18941b6dc17b6ea411e10970602aee271242d43
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/14/2020
ms.locfileid: "48456076"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="10e5e-103">Microsoft 365 组和 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="10e5e-103">Microsoft 365 Groups and Microsoft Teams</span></span>

<span data-ttu-id="10e5e-104">Microsoft 365 组是 Microsoft 365 中的跨应用程序成员身份服务。</span><span class="sxs-lookup"><span data-stu-id="10e5e-104">Microsoft 365 Groups is the cross-application membership service in Microsoft 365.</span></span> <span data-ttu-id="10e5e-105">在基本级别，Microsoft 365 组是 Azure Active Directory 中的一个对象，其中包含一组成员以及与相关工作负荷（包括 SharePoint 团队网站、共享 Exchange 邮箱、Planner 和 Power BI 工作区）的耦合。</span><span class="sxs-lookup"><span data-stu-id="10e5e-105">At a basic level, a Microsoft 365 Group is an object in Azure Active Directory with a list of members and a coupling to related workloads including a SharePoint team site, shared Exchange mailbox, Planner and Power BI workspace.</span></span> <span data-ttu-id="10e5e-106">您可以像对待 Active Directory 中任何其他基于组的安全对象一样，在组中添加或删除人员。</span><span class="sxs-lookup"><span data-stu-id="10e5e-106">You can add or remove people to the group just as you would any other group-based security object in Active Directory.</span></span>

![显示 Microsoft 365 组和相关服务的图表](https://docs.microsoft.com/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

<span data-ttu-id="10e5e-108">默认情况下，Microsoft 365 中的用户可以创建和管理组。</span><span class="sxs-lookup"><span data-stu-id="10e5e-108">By default, users in Microsoft 365 can create and manage groups.</span></span> <span data-ttu-id="10e5e-109">有关 Microsoft 365 组的详细信息，请参阅 [了解 microsoft 365 组](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) 和 [MICROSOFT 365 for IT 设计师](teams-architecture-solutions-posters.md#groups-in-microsoft-365) 版海报中的组。</span><span class="sxs-lookup"><span data-stu-id="10e5e-109">For more information about Microsoft 365 Groups, see [Learn about Microsoft 365 Groups](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) and the [Groups in Microsoft 365 for IT Architects](teams-architecture-solutions-posters.md#groups-in-microsoft-365) poster.</span></span>

## <a name="how-microsoft-365-groups-work-with-teams"></a><span data-ttu-id="10e5e-110">Microsoft 365 组如何与团队协作</span><span class="sxs-lookup"><span data-stu-id="10e5e-110">How Microsoft 365 Groups work with Teams</span></span>

<span data-ttu-id="10e5e-111">创建团队时，将创建 Microsoft 365 组以管理团队成员身份。</span><span class="sxs-lookup"><span data-stu-id="10e5e-111">When you create a team, a Microsoft 365 group is created to manage team membership.</span></span> <span data-ttu-id="10e5e-112">组的相关服务（如 SharePoint 网站、Power BI 工作区等）同时创建。</span><span class="sxs-lookup"><span data-stu-id="10e5e-112">The group's related services, such as a SharePoint site, Power BI workspace, etc. are created at the same time.</span></span>

<span data-ttu-id="10e5e-113">创建团队的人员可以选择使用现有的 Microsoft 365 组（如果他们是该组的所有者）。</span><span class="sxs-lookup"><span data-stu-id="10e5e-113">People who create teams can choose to use an existing Microsoft 365 group if they are an owner of that group.</span></span> <span data-ttu-id="10e5e-114">团队中的每个频道在文档库中都有一个单独的文件夹。</span><span class="sxs-lookup"><span data-stu-id="10e5e-114">Each channel in the team has a separate folder in the document library.</span></span> <span data-ttu-id="10e5e-115">直接在文档库中创建文件夹不会在团队中创建频道。</span><span class="sxs-lookup"><span data-stu-id="10e5e-115">Creating folders directly in the document library does not create channels in the team.</span></span>

<span data-ttu-id="10e5e-116">在 Outlook 或 SharePoint 中创建 Microsoft 365 组时，组邮箱在 Outlook 中可见。</span><span class="sxs-lookup"><span data-stu-id="10e5e-116">When creating a Microsoft 365 group in Outlook or SharePoint, the group mailbox is visible in Outlook.</span></span> <span data-ttu-id="10e5e-117">在团队中创建团队时，默认情况下，组邮箱处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="10e5e-117">When creating a team in Teams, the group mailbox is hidden by default.</span></span> <span data-ttu-id="10e5e-118">你可以将 [UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) Cmdlet 与 **HiddenFromExchangeClientsEnabled** 参数配合使用，以使邮箱可见。</span><span class="sxs-lookup"><span data-stu-id="10e5e-118">You can use the [Set-UnifiedGroup](https://docs.microsoft.com/powershell/module/exchange/users-and-groups/set-unifiedgroup) cmdlet with the **HiddenFromExchangeClientsEnabled** parameter to make a mailbox visible.</span></span>

## <a name="group-membership"></a><span data-ttu-id="10e5e-119">组成员身份</span><span class="sxs-lookup"><span data-stu-id="10e5e-119">Group membership</span></span>

<span data-ttu-id="10e5e-120">如果删除团队的成员，也将从 Microsoft 365 组中删除这些成员。</span><span class="sxs-lookup"><span data-stu-id="10e5e-120">If you remove a member of a team, they are removed from the Microsoft 365 group as well.</span></span> <span data-ttu-id="10e5e-121">从组中删除立即从团队客户端删除团队和频道。</span><span class="sxs-lookup"><span data-stu-id="10e5e-121">Removal from the group immediately removes the team and channels from the Teams client.</span></span> <span data-ttu-id="10e5e-122">如果您使用 Microsoft 365 管理中心从组中删除人员，他们将无法再访问其他协作方面，例如 SharePoint Online 文档库、Yammer 组或共享的 OneNote。</span><span class="sxs-lookup"><span data-stu-id="10e5e-122">If you remove a person from a group using the Microsoft 365 admin center, they will no longer have access to the other collaborative aspects such as SharePoint Online document library, Yammer group, or shared OneNote.</span></span> <span data-ttu-id="10e5e-123">但是，他们在大约两个小时内仍可访问团队的聊天功能。</span><span class="sxs-lookup"><span data-stu-id="10e5e-123">However, they will still have access to the team's chat functionality for approximately two hours.</span></span>

<span data-ttu-id="10e5e-124">作为管理团队成员的最佳做法，可从团队客户端添加和删除它们，以确保快速连接其他组所连接的工作负荷的权限更新。</span><span class="sxs-lookup"><span data-stu-id="10e5e-124">As a best practice for managing team members, add and remove them from the Teams client to ensure that permissions updates for other group-connected workloads occur quickly.</span></span> <span data-ttu-id="10e5e-125">如果你在团队客户端 (使用 Microsoft 365 管理中心、Azure AD 或 Exchange Online PowerShell) 添加或删除团队成员，则可能最多需要24小时才能在团队中反映更改。</span><span class="sxs-lookup"><span data-stu-id="10e5e-125">If you add or remove team members outside of the Teams client (by using the Microsoft 365 admin center, Azure AD, or Exchange Online PowerShell), it can take up to 24 hours for changes to be reflected in Teams.</span></span>

## <a name="deleting-groups-and-teams"></a><span data-ttu-id="10e5e-126">删除组和团队</span><span class="sxs-lookup"><span data-stu-id="10e5e-126">Deleting groups and teams</span></span>

<span data-ttu-id="10e5e-127">删除 Microsoft 365 组将删除持久 Outlook/OWA 对话和团队会议邀请的邮箱别名，并将 SharePoint 网站标记为 "删除"。</span><span class="sxs-lookup"><span data-stu-id="10e5e-127">Deleting a Microsoft 365 group will remove the mailbox alias for persistent Outlook/OWA conversations and Teams meeting invites, and mark the SharePoint site for deletion.</span></span> <span data-ttu-id="10e5e-128">在团队中删除团队及其对 Outlook 的影响之间大约需要20分钟。</span><span class="sxs-lookup"><span data-stu-id="10e5e-128">It takes approximately 20 minutes between the removal of a team and its effect on Outlook.</span></span> <span data-ttu-id="10e5e-129">从团队客户端删除团队会将其从视图中立即删除为团队成员的所有人。</span><span class="sxs-lookup"><span data-stu-id="10e5e-129">Deleting a team from the Teams client will remove it immediately from view to all who are members of the team.</span></span> <span data-ttu-id="10e5e-130">如果删除了已启用团队功能的 Microsoft 365 组的成员，则在从团队客户端视图中删除团队客户端的视图之前，可能会延迟大约两个小时。</span><span class="sxs-lookup"><span data-stu-id="10e5e-130">If you remove members of a Microsoft 365 Group that has had Teams functionality enabled on it, there could be a delay of approximately two hours before the team is removed from view in the Teams client for the affected people who were removed.</span></span>

<span data-ttu-id="10e5e-131">有关组和团队结束生命周期选项的详细信息，请参阅  [组、团队和 Yammer 的生命周期选项结束](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) ，并 [在 Microsoft 团队中存档或删除团队](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team)。</span><span class="sxs-lookup"><span data-stu-id="10e5e-131">For details about groups and teams end of lifecycle options, see  [End of lifecycle options for groups, teams, and Yammer](https://docs.microsoft.com/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) and [Archive or delete a team in Microsoft Teams](https://docs.microsoft.com/microsoftteams/archive-or-delete-a-team).</span></span>

## <a name="related-topics"></a><span data-ttu-id="10e5e-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="10e5e-132">Related topics</span></span>

[<span data-ttu-id="10e5e-133">Microsoft 团队 (视频) 基础 </span><span class="sxs-lookup"><span data-stu-id="10e5e-133">Foundations of Microsoft Teams (video)</span></span>](https://aka.ms/teams-foundations)

[<span data-ttu-id="10e5e-134">还原已删除的组</span><span class="sxs-lookup"><span data-stu-id="10e5e-134">Restore a deleted Group</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/restore-deleted-group)