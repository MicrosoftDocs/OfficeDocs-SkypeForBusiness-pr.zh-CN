---
title: 升级到团队之前先评估你的环境
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解有关正确评估当前环境以便升级到团队的要求。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c783934128e2c1d3f971948c41e3481839ff0aa1
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578235"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a><span data-ttu-id="7a946-103">升级到团队之前先评估你的环境</span><span class="sxs-lookup"><span data-stu-id="7a946-103">Evaluate your environment before upgrading to Teams</span></span>

<span data-ttu-id="7a946-104">![升级旅行图，强调技术准备阶段](media/upgrade-banner-tech-readiness.png "升级旅程的阶段，重点介绍技术准备阶段")</span><span class="sxs-lookup"><span data-stu-id="7a946-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="7a946-105">本文是您的升级过程的技术准备阶段的一部分，与用户准备阶段并行完成的活动。</span><span class="sxs-lookup"><span data-stu-id="7a946-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="7a946-106">在继续之前，请确认您已完成以前阶段中的这些活动：</span><span class="sxs-lookup"><span data-stu-id="7a946-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="7a946-107">已登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="7a946-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="7a946-108">已定义项目范围</span><span class="sxs-lookup"><span data-stu-id="7a946-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="7a946-109">了解 Skype for Business 和团队的共存和互操作性</span><span class="sxs-lookup"><span data-stu-id="7a946-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="7a946-110">已选择升级旅程</span><span class="sxs-lookup"><span data-stu-id="7a946-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="7a946-111">本文概述了正确评估运营团队的当前环境的要求。</span><span class="sxs-lookup"><span data-stu-id="7a946-111">This article gives an overview of the requirements for properly evaluating your current environment for operating Teams.</span></span> <span data-ttu-id="7a946-112">通过评估你的环境，确定将影响你的整体部署的风险和要求。</span><span class="sxs-lookup"><span data-stu-id="7a946-112">By evaluating your environment, you identify risks and requirements that will influence your overall deployment.</span></span> <span data-ttu-id="7a946-113">通过预先确定这些项目，您可以调整计划以推动成功。</span><span class="sxs-lookup"><span data-stu-id="7a946-113">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-the-discovery-questionnaire"></a><span data-ttu-id="7a946-114">发现问卷问卷简介</span><span class="sxs-lookup"><span data-stu-id="7a946-114">Introduction to the Discovery Questionnaire</span></span>

<span data-ttu-id="7a946-115">为了实现客观的关键结果 (OKRs) ，您以前已做出关键服务决策。</span><span class="sxs-lookup"><span data-stu-id="7a946-115">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="7a946-116">下一步是执行环境发现以评估与你的 IT 基础结构、网络和操作相关的所有方面，以确认你的组织已准备好实施解决方案。</span><span class="sxs-lookup"><span data-stu-id="7a946-116">The next step is to perform environmental discovery to evaluate all aspects relating to your IT infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span> <span data-ttu-id="7a946-117">发现是在为团队进行规划时，首先要执行的关键步骤之一。</span><span class="sxs-lookup"><span data-stu-id="7a946-117">Discovery is one of the very first, key steps that you take when planning for your journey to Teams.</span></span> <span data-ttu-id="7a946-118">环境发现必须包含网络准备情况评估，以确保你的网络可以支持升级到团队。</span><span class="sxs-lookup"><span data-stu-id="7a946-118">Environmental discovery must include a network readiness assessment to ensure your network can support upgrading to Teams.</span></span> <span data-ttu-id="7a946-119">你可以对你的环境执行详细的发现，以更好地了解其当前状态，并揭示任何困难，甚至更重要的是，在团队推出的执行中可能会发生阻止。</span><span class="sxs-lookup"><span data-stu-id="7a946-119">You perform a detailed discovery of your environment to better understand its current state and to reveal any difficulties or—even more important—possible blockers to the execution of your Teams rollout.</span></span>

<span data-ttu-id="7a946-120">你可以将技术风险标识为环境评估和采纳准备情况评估的一部分，并针对每个确定的风险制定一个缓解计划。</span><span class="sxs-lookup"><span data-stu-id="7a946-120">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="7a946-121">您应将此信息合并到风险注册中。</span><span class="sxs-lookup"><span data-stu-id="7a946-121">You should incorporate this information in the risk register.</span></span>

<span data-ttu-id="7a946-122">环境发现问卷问卷中包括与您的现有协作基础结构和 Microsoft 365 或 Office 365 组织、网络、终结点、操作以及采纳和准备情况相关的所有事项。</span><span class="sxs-lookup"><span data-stu-id="7a946-122">All matters related to your existing collaboration infrastructure and Microsoft 365 or Office 365 organization, networking, endpoints, operations, and adoption and readiness are included as part of the environmental discovery questionnaire.</span></span> <span data-ttu-id="7a946-123">与你的项目团队协作，尽可能详细地提供所需的信息，以促进你的规划活动。</span><span class="sxs-lookup"><span data-stu-id="7a946-123">Work with your project team to provide the requested information with as much detail as possible to facilitate your planning activities.</span></span>

<span data-ttu-id="7a946-124">[调查表](upgrade-plan-journey-discovery-questionnaire.md) 划分为以下部分，以在以下几个主要方面确认您的组织准备好团队部署：</span><span class="sxs-lookup"><span data-stu-id="7a946-124">[The questionnaire](upgrade-plan-journey-discovery-questionnaire.md) is divided into the following sections to confirm your organization's readiness for your Teams deployment in several major areas:</span></span>

- <span data-ttu-id="7a946-125">Microsoft 365 或 Office 365 组织详细信息</span><span class="sxs-lookup"><span data-stu-id="7a946-125">Microsoft 365 or Office 365 organization details</span></span>
- <span data-ttu-id="7a946-126">现有协作平台摘要</span><span class="sxs-lookup"><span data-stu-id="7a946-126">Existing collaboration platform summary</span></span>
- <span data-ttu-id="7a946-127">协作平台部署详细信息</span><span class="sxs-lookup"><span data-stu-id="7a946-127">Collaboration platform deployment details</span></span>
- <span data-ttu-id="7a946-128">网络和访问 Microsoft 365 或 Office 365 服务</span><span class="sxs-lookup"><span data-stu-id="7a946-128">Networking and access to Microsoft 365 or Office 365 services</span></span>
- <span data-ttu-id="7a946-129">终结点</span><span class="sxs-lookup"><span data-stu-id="7a946-129">Endpoints</span></span>
- <span data-ttu-id="7a946-130">运营</span><span class="sxs-lookup"><span data-stu-id="7a946-130">Operations</span></span>
- <span data-ttu-id="7a946-131">采纳和准备情况</span><span class="sxs-lookup"><span data-stu-id="7a946-131">Adoption and readiness</span></span>

> [!TIP]
> <span data-ttu-id="7a946-132">你可以从将调查表复制到 Microsoft Word 文档中开始。</span><span class="sxs-lookup"><span data-stu-id="7a946-132">You can start by copying the questionnaire into a Microsoft Word document.</span></span> <span data-ttu-id="7a946-133">尝试回答所有问题，并在您移动浏览时捕获所有详细信息。</span><span class="sxs-lookup"><span data-stu-id="7a946-133">Try to answer all questions and capture all details as you move through.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="7a946-134">决策点</span><span class="sxs-lookup"><span data-stu-id="7a946-134">Decision point</span></span></td><td><ul><li><span data-ttu-id="7a946-135">谁将负责完成环境评估？</span><span class="sxs-lookup"><span data-stu-id="7a946-135">Who will be responsible for completing an environment assessment?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/><span data-ttu-id="7a946-136">后续步骤</span><span class="sxs-lookup"><span data-stu-id="7a946-136">Next step</span></span></td><td><ul><li><span data-ttu-id="7a946-137">记录环境评估的结果。</span><span class="sxs-lookup"><span data-stu-id="7a946-137">Document the results of the environment assessment.</span></span></li></ul></td></tr>
</table>


## <a name="project-team"></a><span data-ttu-id="7a946-138">项目团队</span><span class="sxs-lookup"><span data-stu-id="7a946-138">Project team</span></span>

<span data-ttu-id="7a946-139">确保您已为您的项目团队预定了合适的人员。</span><span class="sxs-lookup"><span data-stu-id="7a946-139">Ensure that you've engaged the right people for your project team.</span></span> <span data-ttu-id="7a946-140">验证在 [登记项目利益干系人](upgrade-enlist-stakeholders.md)时完成的步骤。</span><span class="sxs-lookup"><span data-stu-id="7a946-140">Verify the steps you completed in [Enlist your project stakeholders](upgrade-enlist-stakeholders.md).</span></span>

<span data-ttu-id="7a946-141">评估你的环境后，请继续下一步： [准备你的服务](upgrade-prepare-environment-prepare-service.md)。</span><span class="sxs-lookup"><span data-stu-id="7a946-141">After you evaluate your environment, proceed to the next step: [Prepare your service](upgrade-prepare-environment-prepare-service.md).</span></span>
