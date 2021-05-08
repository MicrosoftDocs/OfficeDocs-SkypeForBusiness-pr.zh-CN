---
title: Microsoft 365组和Microsoft Teams
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
description: 了解如何Microsoft 365组和组成员身份与Microsoft Teams。
ms.openlocfilehash: d258fa4252f6bbb02d2b9a8211dd5919c2d7a67b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51105238"
---
# <a name="microsoft-365-groups-and-microsoft-teams"></a><span data-ttu-id="3ad91-103">Microsoft 365组和Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3ad91-103">Microsoft 365 Groups and Microsoft Teams</span></span>

<span data-ttu-id="3ad91-104">Microsoft 365组是应用程序中的跨应用程序成员身份Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="3ad91-104">Microsoft 365 Groups is the cross-application membership service in Microsoft 365.</span></span> <span data-ttu-id="3ad91-105">在基本级别，Microsoft 365 组是 Azure Active Directory 中的对象，包含成员列表，并且与相关工作负荷（包括 SharePoint 团队网站、共享 Exchange 邮箱、Planner 和 Power BI 工作区）耦合。</span><span class="sxs-lookup"><span data-stu-id="3ad91-105">At a basic level, a Microsoft 365 Group is an object in Azure Active Directory with a list of members and a coupling to related workloads including a SharePoint team site, shared Exchange mailbox, Planner and Power BI workspace.</span></span> <span data-ttu-id="3ad91-106">可以添加或删除组人员，就像在 Active Directory 中添加或删除任何其他基于组的安全对象一样。</span><span class="sxs-lookup"><span data-stu-id="3ad91-106">You can add or remove people to the group just as you would any other group-based security object in Active Directory.</span></span>

![显示组Microsoft 365相关服务的图表](/microsoft-365/media/microsoft-365-groups-hub-spoke.png?view=o365-worldwide)

<span data-ttu-id="3ad91-108">默认情况下，Microsoft 365可以创建和管理组。</span><span class="sxs-lookup"><span data-stu-id="3ad91-108">By default, users in Microsoft 365 can create and manage groups.</span></span> <span data-ttu-id="3ad91-109">有关组Microsoft 365，请参阅了解 Microsoft 365[组](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2)和 Microsoft 365 [FOR IT 架构师海报](teams-architecture-solutions-posters.md#groups-in-microsoft-365)中的组。</span><span class="sxs-lookup"><span data-stu-id="3ad91-109">For more information about Microsoft 365 Groups, see [Learn about Microsoft 365 Groups](https://support.office.com/article/b565caa1-5c40-40ef-9915-60fdb2d97fa2) and the [Groups in Microsoft 365 for IT Architects](teams-architecture-solutions-posters.md#groups-in-microsoft-365) poster.</span></span>

## <a name="how-microsoft-365-groups-work-with-teams"></a><span data-ttu-id="3ad91-110">组Microsoft 365组如何Teams</span><span class="sxs-lookup"><span data-stu-id="3ad91-110">How Microsoft 365 Groups work with Teams</span></span>

<span data-ttu-id="3ad91-111">创建团队时，会Microsoft 365组来管理团队成员身份。</span><span class="sxs-lookup"><span data-stu-id="3ad91-111">When you create a team, a Microsoft 365 group is created to manage team membership.</span></span> <span data-ttu-id="3ad91-112">组的相关服务（例如SharePoint站点、Power BI工作区等）会同时创建。</span><span class="sxs-lookup"><span data-stu-id="3ad91-112">The group's related services, such as a SharePoint site, Power BI workspace, etc. are created at the same time.</span></span>

<span data-ttu-id="3ad91-113">创建团队的人可以选择使用现有Microsoft 365组（如果他们是该组的所有者）。</span><span class="sxs-lookup"><span data-stu-id="3ad91-113">People who create teams can choose to use an existing Microsoft 365 group if they are an owner of that group.</span></span> <span data-ttu-id="3ad91-114">团队的每个频道在文档库中都有一个单独的文件夹。</span><span class="sxs-lookup"><span data-stu-id="3ad91-114">Each channel in the team has a separate folder in the document library.</span></span> <span data-ttu-id="3ad91-115">直接在文档库中创建文件夹不会在团队中创建频道。</span><span class="sxs-lookup"><span data-stu-id="3ad91-115">Creating folders directly in the document library does not create channels in the team.</span></span>

<span data-ttu-id="3ad91-116">在 Microsoft 365 或 Outlook SharePoint 组时，组邮箱显示在Outlook。</span><span class="sxs-lookup"><span data-stu-id="3ad91-116">When creating a Microsoft 365 group in Outlook or SharePoint, the group mailbox is visible in Outlook.</span></span> <span data-ttu-id="3ad91-117">在 Teams 中创建团队时，组邮箱默认处于隐藏状态。</span><span class="sxs-lookup"><span data-stu-id="3ad91-117">When creating a team in Teams, the group mailbox is hidden by default.</span></span> <span data-ttu-id="3ad91-118">可以将 [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) cmdlet 与 **HiddenFromExchangeClientsEnabled** 参数一起用于使邮箱可见。</span><span class="sxs-lookup"><span data-stu-id="3ad91-118">You can use the [Set-UnifiedGroup](/powershell/module/exchange/users-and-groups/set-unifiedgroup) cmdlet with the **HiddenFromExchangeClientsEnabled** parameter to make a mailbox visible.</span></span>

## <a name="group-membership"></a><span data-ttu-id="3ad91-119">组成员身份</span><span class="sxs-lookup"><span data-stu-id="3ad91-119">Group membership</span></span>

<span data-ttu-id="3ad91-120">如果删除团队的成员，则他们Microsoft 365组中删除。</span><span class="sxs-lookup"><span data-stu-id="3ad91-120">If you remove a member of a team, they are removed from the Microsoft 365 group as well.</span></span> <span data-ttu-id="3ad91-121">从组中删除会立即从客户端中删除团队Teams频道。</span><span class="sxs-lookup"><span data-stu-id="3ad91-121">Removal from the group immediately removes the team and channels from the Teams client.</span></span> <span data-ttu-id="3ad91-122">如果使用 Microsoft 365 管理中心从组中删除人员，他们将不再有权访问其他协作方面，例如 SharePoint Online 文档库、Yammer 组或共享OneNote。</span><span class="sxs-lookup"><span data-stu-id="3ad91-122">If you remove a person from a group using the Microsoft 365 admin center, they will no longer have access to the other collaborative aspects such as SharePoint Online document library, Yammer group, or shared OneNote.</span></span> <span data-ttu-id="3ad91-123">但是，他们仍可在大约两小时内访问团队的聊天功能。</span><span class="sxs-lookup"><span data-stu-id="3ad91-123">However, they will still have access to the team's chat functionality for approximately two hours.</span></span>

<span data-ttu-id="3ad91-124">作为管理团队成员的最佳实践，在 Teams 客户端中添加和删除这些成员，以确保快速更新其他组连接的工作负荷的权限。</span><span class="sxs-lookup"><span data-stu-id="3ad91-124">As a best practice for managing team members, add and remove them from the Teams client to ensure that permissions updates for other group-connected workloads occur quickly.</span></span> <span data-ttu-id="3ad91-125">如果使用 Microsoft 365 管理中心、Azure AD 或 Exchange Online PowerShell) 在 Teams 客户端 (外部添加或删除团队成员，则更改最多可能需要 24 小时才能反映在 Teams 中。</span><span class="sxs-lookup"><span data-stu-id="3ad91-125">If you add or remove team members outside of the Teams client (by using the Microsoft 365 admin center, Azure AD, or Exchange Online PowerShell), it can take up to 24 hours for changes to be reflected in Teams.</span></span>

## <a name="deleting-groups-and-teams"></a><span data-ttu-id="3ad91-126">删除组和团队</span><span class="sxs-lookup"><span data-stu-id="3ad91-126">Deleting groups and teams</span></span>

<span data-ttu-id="3ad91-127">删除Microsoft 365组将删除持久 Outlook/OWA 对话和 Teams 会议邀请的邮箱别名，并SharePoint网站进行删除。</span><span class="sxs-lookup"><span data-stu-id="3ad91-127">Deleting a Microsoft 365 group will remove the mailbox alias for persistent Outlook/OWA conversations and Teams meeting invites, and mark the SharePoint site for deletion.</span></span> <span data-ttu-id="3ad91-128">删除团队及其对团队的影响大约需要 20 Outlook。</span><span class="sxs-lookup"><span data-stu-id="3ad91-128">It takes approximately 20 minutes between the removal of a team and its effect on Outlook.</span></span> <span data-ttu-id="3ad91-129">从客户端中删除团队Teams团队将立即将其从视图中删除，所有团队成员都查看该团队。</span><span class="sxs-lookup"><span data-stu-id="3ad91-129">Deleting a team from the Teams client will remove it immediately from view to all who are members of the team.</span></span> <span data-ttu-id="3ad91-130">如果删除已启用 Teams 功能的 Microsoft 365 组的成员，则删除受影响人员在 Teams 客户端中将团队从视图中删除之前，可能会延迟大约两小时。</span><span class="sxs-lookup"><span data-stu-id="3ad91-130">If you remove members of a Microsoft 365 Group that has had Teams functionality enabled on it, there could be a delay of approximately two hours before the team is removed from view in the Teams client for the affected people who were removed.</span></span>

<span data-ttu-id="3ad91-131">有关组和团队生命周期结束选项的详细信息，请参阅组、团队和团队的生命周期结束选项[Yammer存档或删除](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer)组中[Microsoft Teams。](./archive-or-delete-a-team.md)</span><span class="sxs-lookup"><span data-stu-id="3ad91-131">For details about groups and teams end of lifecycle options, see  [End of lifecycle options for groups, teams, and Yammer](/microsoft-365/solutions/end-life-cycle-groups-teams-sites-yammer) and [Archive or delete a team in Microsoft Teams](./archive-or-delete-a-team.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="3ad91-132">相关主题</span><span class="sxs-lookup"><span data-stu-id="3ad91-132">Related topics</span></span>

[<span data-ttu-id="3ad91-133">视频Microsoft Teams (的基础) </span><span class="sxs-lookup"><span data-stu-id="3ad91-133">Foundations of Microsoft Teams (video)</span></span>](https://aka.ms/teams-foundations)

[<span data-ttu-id="3ad91-134">还原已删除的组</span><span class="sxs-lookup"><span data-stu-id="3ad91-134">Restore a deleted Group</span></span>](/microsoft-365/admin/create-groups/restore-deleted-group)