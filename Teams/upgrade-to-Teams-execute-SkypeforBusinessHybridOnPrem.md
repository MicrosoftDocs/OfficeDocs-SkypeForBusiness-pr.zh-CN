---
title: 将本地 Skype for Business 升级到 Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: bjwhalen
description: 了解如何从 Skype for Business 内部部署将你的组织升级到 Microsoft 团队。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1981640ab06d00e7895e11c0e15adf7555577908
ms.sourcegitcommit: b23d3d583910aa21a62ea69b554ab614c1ae8079
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648603"
---
# <a name="upgrade-from-skype-for-business-on-premises-to-teams"></a><span data-ttu-id="6ef89-103">从本地 Skype for Business 升级到团队</span><span class="sxs-lookup"><span data-stu-id="6ef89-103">Upgrade from Skype for Business on-premises to Teams</span></span>

<span data-ttu-id="6ef89-104">![升级旅行图，强调部署和实现](media/upgrade-banner-deployment.png "升级旅程的阶段，重点介绍部署和实施阶段")</span><span class="sxs-lookup"><span data-stu-id="6ef89-104">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="6ef89-105">本文是升级过程的部署和实施阶段的一部分。</span><span class="sxs-lookup"><span data-stu-id="6ef89-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="6ef89-106">继续之前，请确认你已完成以下活动：</span><span class="sxs-lookup"><span data-stu-id="6ef89-106">Before proceeding, confirm that you've completed the following activities:</span></span>

-   [<span data-ttu-id="6ef89-107">已登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="6ef89-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="6ef89-108">已定义项目范围</span><span class="sxs-lookup"><span data-stu-id="6ef89-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="6ef89-109">了解 Skype for Business 和团队的共存和互操作性</span><span class="sxs-lookup"><span data-stu-id="6ef89-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="6ef89-110">已选择升级旅程</span><span class="sxs-lookup"><span data-stu-id="6ef89-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="6ef89-111">准备好你的环境</span><span class="sxs-lookup"><span data-stu-id="6ef89-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="6ef89-112">准备好您的组织</span><span class="sxs-lookup"><span data-stu-id="6ef89-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="6ef89-113">开展了一个试验</span><span class="sxs-lookup"><span data-stu-id="6ef89-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="6ef89-114">如果你已部署 Skype for Business 服务器或 Microsoft Lync 本地版，并且你的组织希望升级到团队，请按照本文中的指南操作。</span><span class="sxs-lookup"><span data-stu-id="6ef89-114">If you've deployed Skype for Business Server or Microsoft Lync on-premises and your organization wants to upgrade to Teams, follow the guidance in this article.</span></span> <span data-ttu-id="6ef89-115">你需要设置与 Microsoft 365 或 Office 365 组织的混合连接，并确定在阶段将用户移动到团队的共存要求。</span><span class="sxs-lookup"><span data-stu-id="6ef89-115">You need to set up hybrid connectivity with your Microsoft 365 or Office 365 organization, and determine coexistence requirements if you are moving your users to Teams in phases.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="6ef89-116">Skype for Business Online 将于 2021 年 7 月 31 日停用，在此日期之后它将不再可用或受支持。</span><span class="sxs-lookup"><span data-stu-id="6ef89-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="6ef89-117">为了最大程度地实现收益并确保你的组织有适当的时间实施升级，我们鼓励你立即开始迁移到 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="6ef89-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="6ef89-118">请记住，成功升级会使技术和用户准备相一致，因此，在您向 Microsoft 团队导航旅行时，请务必利用本指南。</span><span class="sxs-lookup"><span data-stu-id="6ef89-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="step-1-configure-hybrid-connectivity"></a><span data-ttu-id="6ef89-119">步骤1：配置混合连接</span><span class="sxs-lookup"><span data-stu-id="6ef89-119">Step 1: Configure hybrid connectivity</span></span> 

<span data-ttu-id="6ef89-120">将本地用户升级到团队的主要先决条件是为您的 Skype for Business Server 内部部署配置混合连接。</span><span class="sxs-lookup"><span data-stu-id="6ef89-120">The key prerequisite for upgrading your on-premises users to Teams is to configure hybrid connectivity for your Skype for Business Server on-premises deployment.</span></span> 

<span data-ttu-id="6ef89-121">首先阅读 [计划混合连接](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json)，然后按照[配置混合连接](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)中概述的任务操作。</span><span class="sxs-lookup"><span data-stu-id="6ef89-121">Start by reading [Plan hybrid connectivity](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-hybrid-connectivity?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and then follow the tasks outlined in [Configure hybrid connectivity](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span></span>


## <a name="step-2-set-transitional-coexistence-mode-optional"></a><span data-ttu-id="6ef89-122">步骤2：设置过渡的共存模式 (可选) </span><span class="sxs-lookup"><span data-stu-id="6ef89-122">Step 2: Set transitional coexistence mode (optional)</span></span>

<span data-ttu-id="6ef89-123">Skype for Business 和团队客户端和用户之间的共存和互操作性由团队升级模式定义。</span><span class="sxs-lookup"><span data-stu-id="6ef89-123">Coexistence and interoperability between Skype for Business and Teams clients and users are defined by Teams Upgrade modes.</span></span>  <span data-ttu-id="6ef89-124">默认情况下，组织处于 "孤岛" 模式，允许用户并排使用团队和 Skype for business 客户端。</span><span class="sxs-lookup"><span data-stu-id="6ef89-124">By default, organizations are in Islands mode, which allows users to use both Teams and Skype for Business clients side by side.</span></span>

<span data-ttu-id="6ef89-125">对于迁移到团队的组织，TeamsOnly 模式是每个用户的最终目标，但并非所有用户都需要同时分配 TeamsOnly (或任何其他模式) 。</span><span class="sxs-lookup"><span data-stu-id="6ef89-125">For an organization moving to Teams, TeamsOnly mode is the final destination for each user--though not all users need to be assigned TeamsOnly (or any other mode) at the same time.</span></span>

<span data-ttu-id="6ef89-126">在用户到达 TeamsOnly 模式之前，组织可以选择使用任何 Skype for Business 共存模式，以确保处于 TeamsOnly 模式的用户和尚未使用的用户之间可预测的通信。</span><span class="sxs-lookup"><span data-stu-id="6ef89-126">Prior to users reaching TeamsOnly mode, organizations can optionally use any of the Skype for Business coexistence modes to ensure predictable communication between users who are in TeamsOnly mode and users who aren't yet.</span></span>  <span data-ttu-id="6ef89-127">Skype for Business 共存模式的用途 (SfBOnly、SfBWithTeamsCollab、SfBWithTeamsCollabAndMeetings) 是为最终用户提供简单、可预测的体验，因为组织从 Skype for Business 过渡到团队。</span><span class="sxs-lookup"><span data-stu-id="6ef89-127">The purpose of the Skype for Business coexistence modes (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) is to provide a simple, predictable experience for end users as organizations transition from Skype for Business to Teams.</span></span> 

<span data-ttu-id="6ef89-128">当用户处于任何 Skype for Business 模式时，所有传入聊天和通话都将路由到用户的 Skype for business 客户端。</span><span class="sxs-lookup"><span data-stu-id="6ef89-128">When a user is in any of the Skype for Business modes, all incoming chats and calls are routed to the user's Skype for Business client.</span></span> <span data-ttu-id="6ef89-129">为避免最终用户混淆和确保正确路由，当用户处于任何 Skype for Business 模式时，将禁用团队客户端中的 "调用和聊天" 功能。</span><span class="sxs-lookup"><span data-stu-id="6ef89-129">To avoid end-user confusion and ensure proper routing, calling and chat functionality in the Teams client is disabled when a user is in any of the Skype for Business modes.</span></span> <span data-ttu-id="6ef89-130">同样，当用户处于 SfBOnly 或 SfBWithTeamsCollab 模式时，将显式禁用团队中的会议计划，并在用户处于 SfBWithTeamsCollabAndMeetings 模式时显式启用。</span><span class="sxs-lookup"><span data-stu-id="6ef89-130">Similarly, meeting scheduling in Teams is explicitly disabled when users are in the SfBOnly or SfBWithTeamsCollab modes, and explicitly enabled when a user is in the SfBWithTeamsCollabAndMeetings mode.</span></span>

<span data-ttu-id="6ef89-131">根据你的需求，你可以根据你的组织选择的升级路径分配适当的共存模式。</span><span class="sxs-lookup"><span data-stu-id="6ef89-131">Depending on your requirements, you can assign the appropriate coexistence mode based on the upgrade path that your organization has chosen.</span></span> <span data-ttu-id="6ef89-132">有关详细信息，请参阅与 Skype for Business 一起使用团队和[设置共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)[的组织的迁移和互操作指南](migration-interop-guidance-for-teams-with-skype.md)。</span><span class="sxs-lookup"><span data-stu-id="6ef89-132">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md) and [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence).</span></span>


## <a name="step-3-move-users-from-skype-for-business-on-premises-to-teams-only"></a><span data-ttu-id="6ef89-133">步骤3：仅将用户从本地 Skype for business 移动到团队</span><span class="sxs-lookup"><span data-stu-id="6ef89-133">Step 3: Move users from Skype for Business on-premises to Teams Only</span></span>

<span data-ttu-id="6ef89-134">最后，你需要将用户移动到 TeamsOnly 模式。</span><span class="sxs-lookup"><span data-stu-id="6ef89-134">Ultimately, you'll want to move your users to TeamsOnly mode.</span></span> <span data-ttu-id="6ef89-135">这可能会涉及一个或两个步骤，具体取决于你的本地环境。</span><span class="sxs-lookup"><span data-stu-id="6ef89-135">This might involve one or two steps depending on your on-premises environment.</span></span>  

<span data-ttu-id="6ef89-136">有关详细信息，请参阅 [在本地和云之间移动用户](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud)以及[将用户从本地移动到团队](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams)。</span><span class="sxs-lookup"><span data-stu-id="6ef89-136">For more information, see [Move users between on-premises and the cloud](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-between-on-premises-and-cloud) and [Move users from on-premises to Teams](https://docs.microsoft.com/SkypeForBusiness/hybrid/move-users-from-on-premises-to-teams).</span></span> 

## <a name="step-4-disable-hybrid-to-complete-your-migration-to-the-cloud"></a><span data-ttu-id="6ef89-137">步骤4：禁用混合以完成到云的迁移</span><span class="sxs-lookup"><span data-stu-id="6ef89-137">Step 4: Disable hybrid to complete your migration to the cloud</span></span>

<span data-ttu-id="6ef89-138">将所有用户从本地迁移到云后，您可以取消本地 Skype for business 部署。</span><span class="sxs-lookup"><span data-stu-id="6ef89-138">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="6ef89-139">有关详细信息，请参阅[禁用混合以完成到云的迁移](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid)。</span><span class="sxs-lookup"><span data-stu-id="6ef89-139">For more information, see [Disable hybrid to complete migration to the cloud](https://docs.microsoft.com/skypeforbusiness/hybrid/cloud-consolidation-disabling-hybrid).</span></span>


## <a name="phone-system-and-pstn-connectivity-options"></a><span data-ttu-id="6ef89-140">电话系统和 PSTN 连接选项</span><span class="sxs-lookup"><span data-stu-id="6ef89-140">Phone System and PSTN connectivity options</span></span>

<span data-ttu-id="6ef89-141">用户处于 TeamsOnly 模式后，支持团队的电话系统。</span><span class="sxs-lookup"><span data-stu-id="6ef89-141">Phone System with Teams is supported after the user is in TeamsOnly mode.</span></span> <span data-ttu-id="6ef89-142"> (如果用户处于 "孤岛" 模式，则只有 Skype for Business 才支持电话系统。 ) </span><span class="sxs-lookup"><span data-stu-id="6ef89-142">(If the user is in Islands mode, Phone System is only supported with Skype for Business.)</span></span> 

### <a name="pstn-connectivity-options"></a><span data-ttu-id="6ef89-143">PSTN 连接选项</span><span class="sxs-lookup"><span data-stu-id="6ef89-143">PSTN connectivity options</span></span>

<span data-ttu-id="6ef89-144">当考虑公共交换电话网络 (PSTN) 连接选项时，在从 Skype for Business 从本地迁移到 TeamsOnly 模式时，有两种可能的方案：</span><span class="sxs-lookup"><span data-stu-id="6ef89-144">When considering Public Switched Telephone Network (PSTN) connectivity options, there are two possible scenarios when moving from Skype for Business on premises to TeamsOnly mode:</span></span>

- <span data-ttu-id="6ef89-145">使用企业语音的 Skype for Business online 中的用户，这些用户将移动到联机并使用 Microsoft 通话计划。</span><span class="sxs-lookup"><span data-stu-id="6ef89-145">A user in Skype for Business on-premises with Enterprise Voice, who will be moving to online and using a Microsoft Calling plan.</span></span> <span data-ttu-id="6ef89-146">将此用户迁移到团队需要将用户的本地 Skype for business 帐户移动到云，并使用) 该用户电话号码的端口与 Microsoft 通话计划或 B 进行协调，) 从可用区域分配新的订户号码。</span><span class="sxs-lookup"><span data-stu-id="6ef89-146">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with either A) the port of that user’s phone number to a Microsoft Calling Plan or B) assigning a new subscriber number from available regions.</span></span>  <span data-ttu-id="6ef89-147">有关详细信息，请参阅[从本地 Skype For Business 服务器（具有企业语音）到 Microsoft 通话计划](upgrade-to-teams-on-prem-overview.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan)。</span><span class="sxs-lookup"><span data-stu-id="6ef89-147">For more information, see [From Skype for Business Server on-premises, with Enterprise Voice, to Microsoft Calling Plan](upgrade-to-teams-on-prem-overview.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-microsoft-calling-plan).</span></span>

- <span data-ttu-id="6ef89-148">使用企业语音的 Skype for Business online 中的用户，这些用户将移动到联机状态并保持本地 PSTN 连接。</span><span class="sxs-lookup"><span data-stu-id="6ef89-148">A user in Skype for Business on-premises with Enterprise Voice, who will be moving to online and keeping on-premises PSTN connectivity.</span></span> <span data-ttu-id="6ef89-149">将此用户迁移到团队需要将用户的本地 Skype for business 帐户移动到云，并通过将用户迁移到直接路由来协调该用户。</span><span class="sxs-lookup"><span data-stu-id="6ef89-149">Migrating this user to Teams requires moving the user’s on-premises Skype for Business account to the cloud, and coordinating that move with migration of the user to Direct Routing.</span></span> <span data-ttu-id="6ef89-150">有关详细信息，请参阅[从本地 Skype For Business 服务器（具有企业语音）到直接路由](upgrade-to-teams-on-prem-overview.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="6ef89-150">For more information, see [From Skype for Business Server on-premises, with Enterprise Voice, to Direct Routing](upgrade-to-teams-on-prem-overview.md#from-skype-for-business-server-on-premises-with-enterprise-voice-to-direct-routing).</span></span>
