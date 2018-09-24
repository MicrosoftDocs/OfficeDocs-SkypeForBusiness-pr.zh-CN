---
title: Office 365 组和 Microsoft 团队
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 08/29/2018
ms.topic: article
ms.service: msteams
description: 了解 Office 365 组和组成员身份与 Microsoft Teams 如何配合使用
localization_priority: Normal
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 386dc9ba6552f4b8cb8110b3351e8073e76a6113
ms.sourcegitcommit: c864a4b5337960deed01ff8c481326dbbd23c960
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/24/2018
ms.locfileid: "24975105"
---
<a name="office-365-groups-and-microsoft-teams"></a><span data-ttu-id="fc357-103">Office 365 组和 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="fc357-103">Office 365 Groups and Microsoft Teams</span></span>
=====================================

> [!Tip]
> <span data-ttu-id="fc357-104">观看下面的会话，若要了解与 Azure Active Directory (AAD)、 Office 365 组、 Exchange、 SHarePoint 和 OneDrive for Business 团队交互的方式：[基础的 Microsoft 团队](https://aka.ms/teams-foundations)</span><span class="sxs-lookup"><span data-stu-id="fc357-104">Watch the following session to learn how Teams interacts with Azure Active Directory (AAD), Office 365 Groups, Exchange, SHarePoint and OneDrive for Business: [Foundations of Microsoft Teams](https://aka.ms/teams-foundations)</span></span>

<span data-ttu-id="fc357-105">Office 365 组是 Office 365 中跨应用的成员身份服务。</span><span class="sxs-lookup"><span data-stu-id="fc357-105">Office 365 Groups is the cross-application membership service in Office 365.</span></span> <span data-ttu-id="fc357-106">从基本层面上来说，Office 365 组是 Azure Active Directory 中的一个对象，包含一组成员以及与相关工作负荷（包括 SharePoint 团队网站、Yammer 组、共享的 Exchange 邮箱资源、Planner、PowerBI 和 OneNote）的松散耦合。</span><span class="sxs-lookup"><span data-stu-id="fc357-106">At the basic level, an Office 365 Group is an object in Azure Active Directory with a list of members and a loose coupling to related workloads including a SharePoint team site, Yammer Group, shared Exchange mailbox resources, Planner, PowerBI and OneNote.</span></span> <span data-ttu-id="fc357-107">您可以添加或删除到组的人员，就像在 Active Directory 中的任何其他基于组的安全对象。</span><span class="sxs-lookup"><span data-stu-id="fc357-107">You can add or remove people to the group just as you would any other group-based security object in Active Directory.</span></span>

<span data-ttu-id="fc357-108">Office 365 管理员可以定义一个 Office 365 组、 添加成员，以及受益功能，如 Exchange 共享邮箱、 SharePoint 文档库、 Yammer 组等。</span><span class="sxs-lookup"><span data-stu-id="fc357-108">An Office 365 administrator can define an Office 365 Group, add members, and benefit from features such as an Exchange shared mailbox, SharePoint document library, Yammer Group, and so on.</span></span> <span data-ttu-id="fc357-109">有关 Office 365 组的详细信息，请访问：[了解 Office 365 组](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2)。</span><span class="sxs-lookup"><span data-stu-id="fc357-109">For more information about Office 365 Groups, visit: [Learn about Office 365 Groups](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).</span></span>

<a name="how-office-365-groups-work"></a><span data-ttu-id="fc357-110">Office 365 组的工作方式</span><span class="sxs-lookup"><span data-stu-id="fc357-110">How Office 365 Groups work</span></span>
--------------------------

<span data-ttu-id="fc357-111">当创建 Microsoft 团队后, 端时，您正在创建 Office 365 组关联的 SharePoint 文档库和 OneNote 笔记本，以及其他 Office 365 云应用程序的关系。</span><span class="sxs-lookup"><span data-stu-id="fc357-111">When you create a Microsoft Team, on the backend, you’re creating an Office 365 Group and the associated SharePoint document library and OneNote notebook, along with ties into other Office 365 cloud applications.</span></span> <span data-ttu-id="fc357-112">如果创建团队的人是现有 Office 365 公共或专用组的所有者，他们可以向组添加团队功能。</span><span class="sxs-lookup"><span data-stu-id="fc357-112">If the person creating the team is an owner of an existing Office 365 Public or Private Group, they can add Teams functionality to the group.</span></span> <span data-ttu-id="fc357-113">这将创建一个默认**常规**频道的聊天消息、 文档、 OneNote 和其他对象驻留。</span><span class="sxs-lookup"><span data-stu-id="fc357-113">This creates one default **General** channel in which chat messages, documents, OneNote, and other objects reside.</span></span> <span data-ttu-id="fc357-114">查看该频道的文档库将揭示代表团队中的通道的**一般**文件夹。</span><span class="sxs-lookup"><span data-stu-id="fc357-114">Viewing the document library for the channel will reveal the **General** folder representing the channel in the team.</span></span> <span data-ttu-id="fc357-115">更重要的是，如果你在某个文档库中创建自己的文件夹结构，**它不会**以频道形式传播到 Teams；目前，它只从 Teams 转到 SharePoint。</span><span class="sxs-lookup"><span data-stu-id="fc357-115">More importantly, if you create your own folder structure within a document library **it does not propagate** to Teams as a channel; for now, it only flows from Teams into SharePoint.</span></span>

> [!NOTE]
> <span data-ttu-id="fc357-116">删除 Office 365 组将删除持久 Outlook/OWA 对话和 Teams 会议邀请的邮箱别名，以及将 SharePoint 网站标记为删除。</span><span class="sxs-lookup"><span data-stu-id="fc357-116">Deleting an Office 365 Group will remove the mailbox alias for persistent Outlook/OWA conversations and Teams meeting invites, and mark the SharePoint site for deletion.</span></span> <span data-ttu-id="fc357-117">计大约 20 分钟团队的删除操作之间 Outlook 受到影响。</span><span class="sxs-lookup"><span data-stu-id="fc357-117">It takes approximately 20 minutes between the removal of a team and its effect on Outlook.</span></span> <span data-ttu-id="fc357-118">删除团队来自团队客户端会将其立即从视图的所有用户的工作组成员。</span><span class="sxs-lookup"><span data-stu-id="fc357-118">Deleting a team from the Teams client will remove it immediately from view to all who are members of the team.</span></span> <span data-ttu-id="fc357-119">如果删除了具有团队功能在其上启用 Office 365 组的成员，可能有约为两个小时，团队删除从视图中已删除的受影响人员的团队客户端之前的延迟。</span><span class="sxs-lookup"><span data-stu-id="fc357-119">If you remove members of an Office 365 Group that has had Teams functionality enabled on it, there could be a delay of approximately two hours before the team is removed from view in the Teams client for the affected people who were removed.</span></span>
>
><span data-ttu-id="fc357-120">阅读[此](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54)有关还原已删除 Office 365 组信息。</span><span class="sxs-lookup"><span data-stu-id="fc357-120">Read [this](https://support.office.com/article/Restore-a-deleted-Office-365-Group-b7c66b59-657a-4e1a-8aa0-8163b1f4eb54) for information about restoring an Office 365 Group that you deleted.</span></span>

<a name="group-membership"></a><span data-ttu-id="fc357-121">组成员身份</span><span class="sxs-lookup"><span data-stu-id="fc357-121">Group membership</span></span>
----------------

<span data-ttu-id="fc357-122">组特性和功能为您的用户取决于其中驱动器中的组成员身份。</span><span class="sxs-lookup"><span data-stu-id="fc357-122">Group features and capabilities for your users depend on where you drive group membership from.</span></span> <span data-ttu-id="fc357-123">例如，如果您删除的工作组成员，请删除这些空格从 Office 365 组。</span><span class="sxs-lookup"><span data-stu-id="fc357-123">For example, if you remove a member of a team, they are removed from the Office 365 Group as well.</span></span> <span data-ttu-id="fc357-124">从组中删除立即删除工作组和通道来自团队客户端。</span><span class="sxs-lookup"><span data-stu-id="fc357-124">Removal from the group immediately removes the team and channels from the Teams client.</span></span> <span data-ttu-id="fc357-125">如果从一组使用 Office 365 管理门户中移除用户，他们不再将如 Yammer 组或共享的 OneNote 的在线 SharePoint 文档库中有权访问其他协作方面。</span><span class="sxs-lookup"><span data-stu-id="fc357-125">If you remove a person from a group using the Office 365 Admin portal, they will no longer have access to the other collaborative aspects such as SharePoint Online document library, Yammer Group, or shared OneNote.</span></span> <span data-ttu-id="fc357-126">但是，他们仍将约为两个小时内有权团队的聊天功能。</span><span class="sxs-lookup"><span data-stu-id="fc357-126">However, they will still have access to the team’s chat functionality for approximately two hours.</span></span>

<span data-ttu-id="fc357-127">最佳实践管理团队成员： 添加和删除工作组客户端以确保正确的级联访问控件其他相关的云应用程序应用的成员。</span><span class="sxs-lookup"><span data-stu-id="fc357-127">Best practice for managing Teams members: Add and remove members from the Teams client to ensure that the correct cascading access control to other dependent cloud applications is applied.</span></span> <span data-ttu-id="fc357-128">此外，你还将避免出现不连贯的体验，让用户认为他们仍可访问曾经访问的资源（直到下一个同步周期，添加或撤消对服务的特定组件的访问权限）。</span><span class="sxs-lookup"><span data-stu-id="fc357-128">Additionally, you will avoid a disjointed experience leaving people with the impression they still have access to the resources they used to (until the next sync cycle either adds or revokes access to a particular component of the service).</span></span> <span data-ttu-id="fc357-129">如果您执行添加或删除外部团队客户端的工作组成员 (通过使用 Office 365 管理中心、 Azure AD 或 Exchange Online PowerShell)，可能需要更改可以反映在工作组达两个小时。</span><span class="sxs-lookup"><span data-stu-id="fc357-129">If you DO add or remove team members outside of the Teams client (by using the Office 365 Admin Center, Azure AD, or Exchange Online PowerShell), it can take up to two hours for changes to be reflected in Teams.</span></span>
