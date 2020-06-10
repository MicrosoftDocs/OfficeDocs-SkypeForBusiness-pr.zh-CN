---
title: 将本地 Skype for Business 升级到 Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解如何从 Skype for Business 内部部署将组织切换到 Microsoft 团队。
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
ms.openlocfilehash: 34502fe9883c98179a6b2e23cd8360ae823c1853
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/09/2020
ms.locfileid: "44666014"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="93096-103">从 Skype for Business 内部部署升级到团队</span><span class="sxs-lookup"><span data-stu-id="93096-103">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="93096-104">![升级旅程的阶段，重点介绍部署和实施阶段](media/upgrade-banner-deployment.png "升级旅程的阶段，重点介绍部署和实施阶段")</span><span class="sxs-lookup"><span data-stu-id="93096-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="93096-105">本文是升级过程的部署和实施阶段的一部分。</span><span class="sxs-lookup"><span data-stu-id="93096-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="93096-106">继续之前，请确认你已完成以下活动：</span><span class="sxs-lookup"><span data-stu-id="93096-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="93096-107">已登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="93096-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="93096-108">已定义项目范围</span><span class="sxs-lookup"><span data-stu-id="93096-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="93096-109">了解 Skype for Business 和团队的共存和互操作性</span><span class="sxs-lookup"><span data-stu-id="93096-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="93096-110">已选择升级旅程</span><span class="sxs-lookup"><span data-stu-id="93096-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="93096-111">准备好你的环境</span><span class="sxs-lookup"><span data-stu-id="93096-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="93096-112">准备好您的组织</span><span class="sxs-lookup"><span data-stu-id="93096-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="93096-113">开展了一个试验</span><span class="sxs-lookup"><span data-stu-id="93096-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="93096-114">如果你已部署 Skype for business 或 Microsoft Lync 本地版，并且你的组织希望通过使用多个共存模式（或全部）升级到 Microsoft 团队，请按照本文中的指南操作。</span><span class="sxs-lookup"><span data-stu-id="93096-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="93096-115">步骤1：部署混合连接</span><span class="sxs-lookup"><span data-stu-id="93096-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="93096-116">将用户升级到团队的关键先决条件是部署混合连接。</span><span class="sxs-lookup"><span data-stu-id="93096-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="93096-117">有关详细信息，请参阅[在 skype for Business 服务器与 skype for Business Online 之间部署混合连接](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="93096-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="93096-118">步骤2：为你的组织实施所选升级旅程</span><span class="sxs-lookup"><span data-stu-id="93096-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="93096-119">完成混合设置后，您可以计划将用户移动到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="93096-119">After you've completed your hybrid setup, you can plan to move your users to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="93096-120">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="93096-120">For more information, see:</span></span>

- <span data-ttu-id="93096-121">[TeamsUpgradePolicy：管理迁移和共存](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)。</span><span class="sxs-lookup"><span data-stu-id="93096-121">[TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

- <span data-ttu-id="93096-122">[将用户从本地移动到 Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)。</span><span class="sxs-lookup"><span data-stu-id="93096-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="93096-123">电话系统和团队升级</span><span class="sxs-lookup"><span data-stu-id="93096-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="93096-124">从本地电话系统过渡到团队将允许你利用手机系统直接路由（"直接路由"）或 microsoft 为 Microsoft 365 或 Office 365 提供的呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="93096-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing ("Direct Routing") or the Microsoft-provided Calling Plans for Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="93096-125">如果未使用通话计划，则需要将企业语音部署转换为手机系统直接路由，作为团队的升级的一部分。</span><span class="sxs-lookup"><span data-stu-id="93096-125">If you're not using Calling Plans, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="93096-126">有关详细信息，请参阅[手机系统直接路由的其他注意事项](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing)。</span><span class="sxs-lookup"><span data-stu-id="93096-126">For more information, see [additional considerations for Phone System Direct Routing](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span></span> <span data-ttu-id="93096-127">如果您计划使用通话计划，请参阅我们关于将[电话号码转移到团队](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)的指南。</span><span class="sxs-lookup"><span data-stu-id="93096-127">If you are planning to use Calling Plans, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>