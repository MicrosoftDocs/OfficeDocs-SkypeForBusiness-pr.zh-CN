---
title: 从 Skype for Business 混合或本地部署升级到 Teams - Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 从 Skype for Business 混合或内部部署升级到团队的注意事项。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 118bae776f4bb3709d62dea1f384ccaa0707397b
ms.sourcegitcommit: 75b2cd0d2d39c50dc1e1513860841e2ae3f84324
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2019
ms.locfileid: "34493976"
---
<span data-ttu-id="30ec6-103">![升级旅行图, 强调部署和实现](media/upgrade-banner-deployment.png "升级旅程的阶段, 重点介绍部署和实施阶段")</span><span class="sxs-lookup"><span data-stu-id="30ec6-103">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="30ec6-104">本文是升级过程的部署和实施阶段的一部分。</span><span class="sxs-lookup"><span data-stu-id="30ec6-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="30ec6-105">继续之前, 请确认你已完成以下活动:</span><span class="sxs-lookup"><span data-stu-id="30ec6-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

-   [<span data-ttu-id="30ec6-106">已登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="30ec6-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="30ec6-107">已定义项目范围</span><span class="sxs-lookup"><span data-stu-id="30ec6-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="30ec6-108">了解 Skype for Business 和团队的共存和互操作性</span><span class="sxs-lookup"><span data-stu-id="30ec6-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="30ec6-109">已选择升级旅程</span><span class="sxs-lookup"><span data-stu-id="30ec6-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="30ec6-110">准备好你的环境</span><span class="sxs-lookup"><span data-stu-id="30ec6-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="30ec6-111">准备好您的组织</span><span class="sxs-lookup"><span data-stu-id="30ec6-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="30ec6-112">开展了一个试验</span><span class="sxs-lookup"><span data-stu-id="30ec6-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a><span data-ttu-id="30ec6-113">从 Skype for Business 混合或内部部署升级到团队</span><span class="sxs-lookup"><span data-stu-id="30ec6-113">Upgrade to Teams from a Skype for Business hybrid or on-premises deployment</span></span>

<span data-ttu-id="30ec6-114">如果你已部署 Skype for business 或 Microsoft Lync 本地版, 并且你的组织希望通过使用多个共存模式 (或全部) 升级到团队, 请按照本文中的指南操作。</span><span class="sxs-lookup"><span data-stu-id="30ec6-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="30ec6-115">第一步是设置与 Office 365 租户的混合连接, 然后将用户移动到 Skype for business Online, 并为他们分配适当的共存和升级模式。</span><span class="sxs-lookup"><span data-stu-id="30ec6-115">The first step is to set up hybrid connectivity with your Office 365 tenant, and then move your users to Skype for Business Online and assign them the appropriate coexistence and upgrade mode.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="30ec6-116">步骤 1: 部署混合连接</span><span class="sxs-lookup"><span data-stu-id="30ec6-116">Step 1: Deploy hybrid connectivity</span></span> 

<span data-ttu-id="30ec6-117">将用户升级到团队的关键先决条件是部署混合连接。</span><span class="sxs-lookup"><span data-stu-id="30ec6-117">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span> <span data-ttu-id="30ec6-118">这可能涉及为现有 Skype for Business 或 Lync 部署部署新的外部连接, 或者只需配置与你的 Office 365 租户的混合关系。</span><span class="sxs-lookup"><span data-stu-id="30ec6-118">This might involve deploying new external connectivity for your existing Skype for Business or Lync deployment, or simply configuring a hybrid relationship with your Office 365 tenant.</span></span> 

<span data-ttu-id="30ec6-119">有关详细信息, 请参阅 [在 skype for Business 服务器与 skype for Business Online 之间部署混合连接](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)。</span><span class="sxs-lookup"><span data-stu-id="30ec6-119">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span></span>

## <a name="step-2-move-users-to-skype-for-business-online"></a><span data-ttu-id="30ec6-120">步骤 2: 将用户移动到 Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="30ec6-120">Step 2: Move users to Skype for Business Online</span></span> 

<span data-ttu-id="30ec6-121">完成混合设置后, 将用户移动到 Skype for business Online。</span><span class="sxs-lookup"><span data-stu-id="30ec6-121">After you’ve completed your hybrid setup, move users to Skype for Business Online.</span></span> 

<span data-ttu-id="30ec6-122">有关详细信息, 请参阅 [将用户从本地移动到 Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="30ec6-122">For more information, see [Move users from on premises to Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span> 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="30ec6-123">步骤 3: 分配共存和升级模式</span><span class="sxs-lookup"><span data-stu-id="30ec6-123">Step 3: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="30ec6-124">将用户移动到 Skype for Business Online 后, 您可以根据组织选择的升级历程为他们分配适当的共存模式。</span><span class="sxs-lookup"><span data-stu-id="30ec6-124">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="30ec6-125">有关详细信息, 请参阅[设置共存和升级设置](https://aka.ms/SkypeToTeams-SetCoexistence)和[TeamsUpgradePolicy: 管理迁移和共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。</span><span class="sxs-lookup"><span data-stu-id="30ec6-125">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="30ec6-126">使用 Skype for business Server 2019 和 Skype for Business Server 2015 的未来累积更新, 你将能够执行步骤 2 (将用户移动到 Skype for business Online) 和步骤 3 (在将用户升级到团队) 中执行一步操作。</span><span class="sxs-lookup"><span data-stu-id="30ec6-126">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 2 (moving users to Skype for Business Online) and Step 3 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="30ec6-127">在发布 Skype for Business Server 2019 后, 将提供详细信息。</span><span class="sxs-lookup"><span data-stu-id="30ec6-127">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="30ec6-128">电话系统和团队升级</span><span class="sxs-lookup"><span data-stu-id="30ec6-128">Phone System and Teams upgrade</span></span>

<span data-ttu-id="30ec6-129">如果你正在将 Skype for Business 混合部署转换为带有呼叫计划的电话系统, Microsoft 将成为您的公共交换电话网络 (PSTN) 提供商, 并假设你已完成电话号码移植-升级你的用户以团队将向团队自动切换入站 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="30ec6-129">If you’re transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="30ec6-130">如果通话计划不可用, 则需要将企业语音部署切换到 Microsoft Phone 系统直接路由。</span><span class="sxs-lookup"><span data-stu-id="30ec6-130">If Calling Plans isn’t available, you need to transition your enterprise voice deployment to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="30ec6-131">若要将用户升级到团队, 请参阅[手机系统直接路由的其他注意事项](2-envision-make-my-service-decisions-direct-routing.md)。</span><span class="sxs-lookup"><span data-stu-id="30ec6-131">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
