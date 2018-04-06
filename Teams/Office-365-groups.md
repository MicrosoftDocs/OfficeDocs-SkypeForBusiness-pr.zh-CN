---
title: Office 365 组和 Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: 了解 Office 365 组和组成员身份与 Microsoft Teams 如何配合使用
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9f16a99f00add1e93bfdf4cde29f4b75f384a296
ms.sourcegitcommit: cacd16f596460c1400dd514437794afd04bddadc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2018
---
<a name="office-365-groups-and-microsoft-teams"></a><span data-ttu-id="a0664-103">Office 365 组和 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a0664-103">Office 365 groups and Microsoft Teams</span></span>
=====================================

<span data-ttu-id="a0664-104">Office 365 组是 Office 365 中跨应用的成员身份服务。</span><span class="sxs-lookup"><span data-stu-id="a0664-104">Office 365 Groups is the cross-application membership service in Office 365.</span></span> <span data-ttu-id="a0664-105">从基本层面上来说，Office 365 组是 Azure Active Directory 中的一个对象，包含一组成员以及与相关工作负荷（包括 SharePoint 团队网站、Yammer 组、共享的 Exchange 邮箱资源、Planner、PowerBI 和 OneNote）的松散耦合。</span><span class="sxs-lookup"><span data-stu-id="a0664-105">At the basic level, an Office 365 Group is an object in Azure Active Directory with a list of members and a loose coupling to related workloads including a SharePoint team site, Yammer Group, shared Exchange mailbox resources, Planner, PowerBI and OneNote.</span></span> <span data-ttu-id="a0664-106">你可以在组中添加或删除人员，就像 Active Directory 中的任何其他基于组的安全对象一样。</span><span class="sxs-lookup"><span data-stu-id="a0664-106">You can add or remove people to the Group just as you would any other group-based security object in Active Directory.</span></span>

<span data-ttu-id="a0664-107">Office 365 管理员可以定义 Office 365 组、添加成员以及利用 Exchange 共享邮箱、SharePoint 文档库、Yammer 组等功能。有关组的详细信息，请访问：[了解 Office 365 组](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)。</span><span class="sxs-lookup"><span data-stu-id="a0664-107">An Office 365 administrator can define an Office 365 Group, add members, and benefit from features such as an Exchange shared mailbox, SharePoint document library, Yammer Group, etc. For more information about Groups visit: [Learn about Office 365 Groups](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).</span></span>

<a name="how-office-365-groups-work"></a><span data-ttu-id="a0664-108">Office 365 组工作方式</span><span class="sxs-lookup"><span data-stu-id="a0664-108">How Office 365 groups work</span></span>
--------------------------

<span data-ttu-id="a0664-109">在 Microsoft Teams 中创建团队时，会在后台创建一个 Office 365 组、关联的 SharePoint 文档库、OneNote 笔记本以及与其他 Office 365 云应用的关联。</span><span class="sxs-lookup"><span data-stu-id="a0664-109">When you create a Microsoft Team, on the backend, you’re creating an Office 365 Group along with the associated SharePoint document library, OneNote notebook, along with ties into other Office 365 cloud applications.</span></span> <span data-ttu-id="a0664-110">如果创建团队的用户是现有 Office 365 公用组或专用组的所有者，则该用户可以向组添加 Teams 功能。</span><span class="sxs-lookup"><span data-stu-id="a0664-110">If the person creating the Team is an owner of an existing Office 365 Public or Private Group, they can add Teams functionality to the Group.</span></span> <span data-ttu-id="a0664-111">这将创建一个默认的“常规”频道，聊天消息、文档、OneNote 及其他对象位于该频道中。</span><span class="sxs-lookup"><span data-stu-id="a0664-111">This creates one default “General” channel in which chat messages, documents, OneNote, and other objects reside.</span></span> <span data-ttu-id="a0664-112">查看该频道的文档库将在团队中显示表示该频道的“常规”文件夹。</span><span class="sxs-lookup"><span data-stu-id="a0664-112">Viewing the document library for the channel will reveal the “General” folder representing the channel in the Team.</span></span> <span data-ttu-id="a0664-113">更重要的是，如果你在某个文档库中创建自己的文件夹结构，**它不会**以频道形式传播到 Teams；目前，它只从 Teams 转到 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="a0664-113">More importantly, if you create your own folder structure within a document library **it does not propagate** to Teams as a channel; for now, it only flows from Teams into SharePoint.</span></span>




> [!NOTE]
> <span data-ttu-id="a0664-114">删除 Office 365 组将删除持久 Outlook/OWA 对话和 Teams 会议邀请的邮箱别名，以及将 SharePoint 网站标记为删除。</span><span class="sxs-lookup"><span data-stu-id="a0664-114">Deleting an Office 365 Group will remove the mailbox alias for persistent Outlook/OWA conversations and Teams meeting invites, and mark the SharePoint site for deletion.</span></span> <span data-ttu-id="a0664-115">从删除团队到在 Outlook 中生效大约需要 20 分钟。</span><span class="sxs-lookup"><span data-stu-id="a0664-115">It takes approximately 20 minutes between the removal of a Team and its effect on Outlook.</span></span> <span data-ttu-id="a0664-116">从 Teams 客户端删除团队将从属于团队成员的所有用户的视图中立即删除该团队。</span><span class="sxs-lookup"><span data-stu-id="a0664-116">Deleting a Team from the Teams client will remove it immediately from view to all who are members of the team.</span></span> <span data-ttu-id="a0664-117">如果删除已启用了 Teams 功能的 Office 365 组的成员，可能会延迟大约一小时从已被删除的受影响用户的 Teams 客户端上视图中删除该团队。</span><span class="sxs-lookup"><span data-stu-id="a0664-117">If you remove a member of an Office 365 Group which has had Teams functionality enabled on it, there could be a delay of approximately one hour before the Team is removed from view in the Teams client for the effected people who were removed.</span></span>

<a name="group-membership"></a><span data-ttu-id="a0664-118">组成员身份</span><span class="sxs-lookup"><span data-stu-id="a0664-118">Group membership</span></span>
----------------

<span data-ttu-id="a0664-119">组功能和为您的用户的能力取决于驱动器中的组成员身份的地方。</span><span class="sxs-lookup"><span data-stu-id="a0664-119">Group features and capabilities for your users depends on where you drive group membership from.</span></span> <span data-ttu-id="a0664-120">例如，如果您删除一个团队的成员，他们会从 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="a0664-120">For example, if you remove a member of a team, they are removed from the Office 365 Group as well.</span></span> <span data-ttu-id="a0664-121">从组中删除成员将立即从 Teams 客户端中删除团队和频道。</span><span class="sxs-lookup"><span data-stu-id="a0664-121">Removal from the Group immediately removes the Team and channels from the Teams client.</span></span> <span data-ttu-id="a0664-122">如果从组中删除使用 Office 365 管理门户的用户，则该用户将不再有权访问其他协作项，例如 SharePoint Online 文档库、Yammer 组或共享的 OneNote。</span><span class="sxs-lookup"><span data-stu-id="a0664-122">If you remove a person from a Group using the Office 365 Admin portal, they will no longer have access to the other collaborative aspects such as SharePoint Online document library, Yammer Group, or shared OneNote.</span></span> <span data-ttu-id="a0664-123">但是，该用户仍有权访问团队的聊天功能大约一小时。</span><span class="sxs-lookup"><span data-stu-id="a0664-123">However, they will still have access to the Team’s chat functionality for approximately one hour.</span></span>

<span data-ttu-id="a0664-124">最佳管理团队成员的做法： 添加和删除成员，从团队客户端，以确保与其他相关的云应用程序级联的正确访问控制应用。</span><span class="sxs-lookup"><span data-stu-id="a0664-124">Best practice for managing Teams members: Add and remove members from the Teams client to ensure the correct cascading access control to other dependent cloud applications is applied.</span></span> <span data-ttu-id="a0664-125">此外，你还将避免出现不连贯的体验，让用户认为他们仍可访问曾经访问的资源（直到下一个同步周期，添加或撤消对服务的特定组件的访问权限）。</span><span class="sxs-lookup"><span data-stu-id="a0664-125">Additionally, you will avoid a disjointed experience leaving people with the impression they still have access to the resources they used to (until the next sync cycle either adds or revokes access to a particular component of the service).</span></span> <span data-ttu-id="a0664-126">不要添加或移除团队客户端之外的团队成员 (通过使用 Office 365 管理中心，Azure 的广告，或 Exchange 联机 PowerShell)，有时花费达一小时的更改将反映在工作组。</span><span class="sxs-lookup"><span data-stu-id="a0664-126">If you DO add or remove team members outside of the Teams client (by using Office 365 Admin Center, Azure AD, or Exchange Online PowerShell), it sometimes takes up to one hour for changes to be reflected in Teams.</span></span>
