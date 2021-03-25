---
title: 将本地 Skype for Business 升级到 Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解如何将组织从 Skype for Business 本地部署过渡到 Microsoft Teams。
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
ms.openlocfilehash: 0585f0ad829f19334d5a970461f1f3248a107e9d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115550"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="e2c0b-103">从 Skype for Business 本地部署升级到 Teams</span><span class="sxs-lookup"><span data-stu-id="e2c0b-103">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="e2c0b-104">![升级旅程的阶段，着重强调部署和实施阶段](media/upgrade-banner-deployment.png "升级旅程的阶段，着重强调部署和实施阶段")</span><span class="sxs-lookup"><span data-stu-id="e2c0b-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="e2c0b-105">本文是升级旅程的部署和实施阶段的一部分。</span><span class="sxs-lookup"><span data-stu-id="e2c0b-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="e2c0b-106">在继续之前，请确认已经完成了以下活动:</span><span class="sxs-lookup"><span data-stu-id="e2c0b-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="e2c0b-107">登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="e2c0b-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="e2c0b-108">请确定项目范围</span><span class="sxs-lookup"><span data-stu-id="e2c0b-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="e2c0b-109">了解 Skype for Business 和 Teams 的共存和互操作性</span><span class="sxs-lookup"><span data-stu-id="e2c0b-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="e2c0b-110">选择了升级旅程</span><span class="sxs-lookup"><span data-stu-id="e2c0b-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="e2c0b-111">准备环境</span><span class="sxs-lookup"><span data-stu-id="e2c0b-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="e2c0b-112">准备组织</span><span class="sxs-lookup"><span data-stu-id="e2c0b-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)
- [<span data-ttu-id="e2c0b-113">开展试点</span><span class="sxs-lookup"><span data-stu-id="e2c0b-113">Conducted a pilot</span></span>](./pilot-essentials.md)

<span data-ttu-id="e2c0b-114">如果你已在本地部署 Skype for Business 或 Microsoft Lync，并且你的组织想要选择性地升级到 Microsoft Teams（通过使用多种共存模式）或一切功能，请按照本文中的指导操作。</span><span class="sxs-lookup"><span data-stu-id="e2c0b-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="e2c0b-115">步骤 1：部署混合连接</span><span class="sxs-lookup"><span data-stu-id="e2c0b-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="e2c0b-116">将用户升级到 Teams 的关键先决条件是部署混合连接。</span><span class="sxs-lookup"><span data-stu-id="e2c0b-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="e2c0b-117">有关详细信息，请参阅在 Skype for Business Server 和 [Skype for Business Online 之间部署混合连接](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="e2c0b-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="e2c0b-118">步骤 2：为组织实施所选的升级过程</span><span class="sxs-lookup"><span data-stu-id="e2c0b-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="e2c0b-119">完成混合设置后，可以计划将用户移动到 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="e2c0b-119">After you've completed your hybrid setup, you can plan to move your users to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="e2c0b-120">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="e2c0b-120">For more information, see:</span></span>

- <span data-ttu-id="e2c0b-121">[TeamsUpgradePolicy：管理迁移和共存](upgrade-to-teams-on-prem-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="e2c0b-121">[TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

- <span data-ttu-id="e2c0b-122">[将用户从本地移动到 Skype for Business Online。](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="e2c0b-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="e2c0b-123">手机系统和 Teams 升级</span><span class="sxs-lookup"><span data-stu-id="e2c0b-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="e2c0b-124">从本地电话系统转换到 Teams 将允许你利用电话系统直接路由 ("直接路由") 或 Microsoft 提供的适用于 Microsoft 365 或 Office 365 的呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="e2c0b-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing ("Direct Routing") or the Microsoft-provided Calling Plans for Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="e2c0b-125">如果不使用呼叫计划，则需要在升级到 Teams 期间，将企业语音部署转换为电话系统直接路由。</span><span class="sxs-lookup"><span data-stu-id="e2c0b-125">If you're not using Calling Plans, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="e2c0b-126">有关详细信息，请参阅 [电话系统直接路由的其他注意事项](./direct-routing-landing-page.md)。</span><span class="sxs-lookup"><span data-stu-id="e2c0b-126">For more information, see [additional considerations for Phone System Direct Routing](./direct-routing-landing-page.md).</span></span> <span data-ttu-id="e2c0b-127">如果你计划使用通话套餐，请参阅我们的指南，将你的电话号码转移到[Teams。](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="e2c0b-127">If you are planning to use Calling Plans, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>