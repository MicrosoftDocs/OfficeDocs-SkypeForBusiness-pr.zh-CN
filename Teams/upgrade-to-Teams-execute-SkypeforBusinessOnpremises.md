---
title: 将本地 Skype for business 升级到 Microsoft 团队 |部署 |Lync
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 从 Skype for Business 内部部署升级到团队的注意事项。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 971accd5211c0d8f861ff03db115933f3c75b570
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925393"
---
<span data-ttu-id="1fd15-103">![升级旅程的阶段，重点介绍部署和实施阶段](media/upgrade-banner-deployment.png "升级旅程的阶段，重点介绍部署和实施阶段")</span><span class="sxs-lookup"><span data-stu-id="1fd15-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="1fd15-104">本文是升级过程的部署和实施阶段的一部分。</span><span class="sxs-lookup"><span data-stu-id="1fd15-104">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="1fd15-105">继续之前，请确认你已完成以下活动：</span><span class="sxs-lookup"><span data-stu-id="1fd15-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="1fd15-106">已登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="1fd15-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="1fd15-107">已定义项目范围</span><span class="sxs-lookup"><span data-stu-id="1fd15-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="1fd15-108">了解 Skype for Business 和团队的共存和互操作性</span><span class="sxs-lookup"><span data-stu-id="1fd15-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="1fd15-109">已选择升级旅程</span><span class="sxs-lookup"><span data-stu-id="1fd15-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="1fd15-110">准备好你的环境</span><span class="sxs-lookup"><span data-stu-id="1fd15-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="1fd15-111">准备好您的组织</span><span class="sxs-lookup"><span data-stu-id="1fd15-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="1fd15-112">开展了一个试验</span><span class="sxs-lookup"><span data-stu-id="1fd15-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="1fd15-113">从 Skype for Business 内部部署升级到团队</span><span class="sxs-lookup"><span data-stu-id="1fd15-113">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="1fd15-114">如果你已部署 Skype for business 或 Microsoft Lync 本地版，并且你的组织希望通过使用多个共存模式（或全部）升级到 Microsoft 团队，请按照本文中的指南操作。</span><span class="sxs-lookup"><span data-stu-id="1fd15-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="1fd15-115">步骤1：部署混合连接</span><span class="sxs-lookup"><span data-stu-id="1fd15-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="1fd15-116">将用户升级到团队的关键先决条件是部署混合连接。</span><span class="sxs-lookup"><span data-stu-id="1fd15-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="1fd15-117">有关详细信息，请参阅[在 skype for Business 服务器与 skype for Business Online 之间部署混合连接](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="1fd15-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="1fd15-118">步骤2：为你的组织实施所选升级旅程</span><span class="sxs-lookup"><span data-stu-id="1fd15-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="1fd15-119">完成混合设置后，您可以计划将用户移动到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="1fd15-119">After you’ve completed your hybrid setup, you can plan to move your users to Office 365.</span></span>

<span data-ttu-id="1fd15-120">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="1fd15-120">For more information, see:</span></span>

- <span data-ttu-id="1fd15-121">[TeamsUpgradePolicy：管理迁移和共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。</span><span class="sxs-lookup"><span data-stu-id="1fd15-121">[TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

- <span data-ttu-id="1fd15-122">[将用户从本地移动到 Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="1fd15-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="1fd15-123">电话系统和团队升级</span><span class="sxs-lookup"><span data-stu-id="1fd15-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="1fd15-124">从本地电话系统过渡到团队将允许你利用手机系统直接路由（"直接路由"）或 Microsoft 提供的适用于 Office 365 的呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="1fd15-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing (“Direct Routing”) or the Microsoft-provided Calling Plans for Office 365.</span></span>

<span data-ttu-id="1fd15-125">如果您不使用 Office 365 中的通话计划，则您需要将企业语音部署切换到手机系统直接路由，作为您的团队升级的一部分。</span><span class="sxs-lookup"><span data-stu-id="1fd15-125">If you're not using Calling Plans in Office 365, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="1fd15-126">有关详细信息，请参阅[手机系统直接路由的其他注意事项](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="1fd15-126">For more information, see [additional considerations for Phone System Direct Routing](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span></span> <span data-ttu-id="1fd15-127">如果您计划在 Office 365 中使用呼叫计划，请参阅我们关于将[电话号码转移到团队](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)的指南。</span><span class="sxs-lookup"><span data-stu-id="1fd15-127">If you are planning to use Calling Plans in Office 365, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>