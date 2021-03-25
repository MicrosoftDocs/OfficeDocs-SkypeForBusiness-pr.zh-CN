---
title: 在升级到 Teams 之前评估环境
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 了解正确评估当前环境以升级到 Teams 的要求。
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
ms.openlocfilehash: 119a80f5a25b4a2d8599df3df6a573a1f5554c1a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119101"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a><span data-ttu-id="36870-103">在升级到 Teams 之前评估环境</span><span class="sxs-lookup"><span data-stu-id="36870-103">Evaluate your environment before upgrading to Teams</span></span>

<span data-ttu-id="36870-104">![升级过程图，强调技术准备阶段](media/upgrade-banner-tech-readiness.png "升级过程阶段，着重强调技术准备阶段")</span><span class="sxs-lookup"><span data-stu-id="36870-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="36870-105">本文是升级过程的技术准备阶段（与用户准备阶段并行完成的活动）的一部分。</span><span class="sxs-lookup"><span data-stu-id="36870-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="36870-106">在继续之前，请确认已完成之前阶段中的这些活动：</span><span class="sxs-lookup"><span data-stu-id="36870-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="36870-107">登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="36870-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="36870-108">请确定项目范围</span><span class="sxs-lookup"><span data-stu-id="36870-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="36870-109">了解 Skype for Business 和 Teams 的共存和互操作性</span><span class="sxs-lookup"><span data-stu-id="36870-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="36870-110">选择了升级旅程</span><span class="sxs-lookup"><span data-stu-id="36870-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="36870-111">本文概述了正确评估当前运行 Teams 环境的要求。</span><span class="sxs-lookup"><span data-stu-id="36870-111">This article gives an overview of the requirements for properly evaluating your current environment for operating Teams.</span></span> <span data-ttu-id="36870-112">通过评估环境，可以识别影响整体部署的风险和要求。</span><span class="sxs-lookup"><span data-stu-id="36870-112">By evaluating your environment, you identify risks and requirements that will influence your overall deployment.</span></span> <span data-ttu-id="36870-113">通过事先确定这些项目，可以调整规划以推动成功。</span><span class="sxs-lookup"><span data-stu-id="36870-113">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-the-discovery-questionnaire"></a><span data-ttu-id="36870-114">发现调查问卷简介</span><span class="sxs-lookup"><span data-stu-id="36870-114">Introduction to the Discovery Questionnaire</span></span>

<span data-ttu-id="36870-115">为了在 OKR (目标) ，你之前做出过关键服务决策。</span><span class="sxs-lookup"><span data-stu-id="36870-115">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="36870-116">下一步是执行环境发现，评估与 IT 基础结构、网络和操作相关的所有方面，以确认组织已准备好实施解决方案。</span><span class="sxs-lookup"><span data-stu-id="36870-116">The next step is to perform environmental discovery to evaluate all aspects relating to your IT infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span> <span data-ttu-id="36870-117">发现是规划 Teams 之旅时首先执行的关键步骤之一。</span><span class="sxs-lookup"><span data-stu-id="36870-117">Discovery is one of the very first, key steps that you take when planning for your journey to Teams.</span></span> <span data-ttu-id="36870-118">环境发现必须包含网络就绪性评估，以确保你的网络可以支持升级到 Teams。</span><span class="sxs-lookup"><span data-stu-id="36870-118">Environmental discovery must include a network readiness assessment to ensure your network can support upgrading to Teams.</span></span> <span data-ttu-id="36870-119">你可以对环境执行详细发现，以更好地了解其当前状态，并揭示任何困难，或者（甚至更重要的是）可能阻碍 Teams 推广的执行。</span><span class="sxs-lookup"><span data-stu-id="36870-119">You perform a detailed discovery of your environment to better understand its current state and to reveal any difficulties or—even more important—possible blockers to the execution of your Teams rollout.</span></span>

<span data-ttu-id="36870-120">在环境评估和采用就绪性评估中识别技术风险，并针对每个已识别的风险制定缓解计划。</span><span class="sxs-lookup"><span data-stu-id="36870-120">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="36870-121">应该将此信息合并到风险寄存器中。</span><span class="sxs-lookup"><span data-stu-id="36870-121">You should incorporate this information in the risk register.</span></span>

<span data-ttu-id="36870-122">与现有协作基础结构和 Microsoft 365 或 Office 365 组织、网络、终结点、操作、采用和准备相关的所有事项均包含在环境发现调查问卷中。</span><span class="sxs-lookup"><span data-stu-id="36870-122">All matters related to your existing collaboration infrastructure and Microsoft 365 or Office 365 organization, networking, endpoints, operations, and adoption and readiness are included as part of the environmental discovery questionnaire.</span></span> <span data-ttu-id="36870-123">与项目团队合作，尽可能详细地提供请求的信息，促进规划活动。</span><span class="sxs-lookup"><span data-stu-id="36870-123">Work with your project team to provide the requested information with as much detail as possible to facilitate your planning activities.</span></span>

<span data-ttu-id="36870-124">[调查问卷](upgrade-plan-journey-discovery-questionnaire.md) 分为以下部分，以确认组织在以下几个主要方面对 Teams 部署的准备情况：</span><span class="sxs-lookup"><span data-stu-id="36870-124">[The questionnaire](upgrade-plan-journey-discovery-questionnaire.md) is divided into the following sections to confirm your organization's readiness for your Teams deployment in several major areas:</span></span>

- <span data-ttu-id="36870-125">Microsoft 365 或 Office 365 组织详细信息</span><span class="sxs-lookup"><span data-stu-id="36870-125">Microsoft 365 or Office 365 organization details</span></span>
- <span data-ttu-id="36870-126">现有协作平台摘要</span><span class="sxs-lookup"><span data-stu-id="36870-126">Existing collaboration platform summary</span></span>
- <span data-ttu-id="36870-127">协作平台部署详细信息</span><span class="sxs-lookup"><span data-stu-id="36870-127">Collaboration platform deployment details</span></span>
- <span data-ttu-id="36870-128">网络和访问 Microsoft 365 或 Office 365 服务</span><span class="sxs-lookup"><span data-stu-id="36870-128">Networking and access to Microsoft 365 or Office 365 services</span></span>
- <span data-ttu-id="36870-129">终结点</span><span class="sxs-lookup"><span data-stu-id="36870-129">Endpoints</span></span>
- <span data-ttu-id="36870-130">运营</span><span class="sxs-lookup"><span data-stu-id="36870-130">Operations</span></span>
- <span data-ttu-id="36870-131">采用和准备情况</span><span class="sxs-lookup"><span data-stu-id="36870-131">Adoption and readiness</span></span>

> [!TIP]
> <span data-ttu-id="36870-132">首先，可以将调查问卷复制到 Microsoft Word 文档中。</span><span class="sxs-lookup"><span data-stu-id="36870-132">You can start by copying the questionnaire into a Microsoft Word document.</span></span> <span data-ttu-id="36870-133">尝试回答所有问题，在浏览时捕获所有详细信息。</span><span class="sxs-lookup"><span data-stu-id="36870-133">Try to answer all questions and capture all details as you move through.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="36870-134">决策点</span><span class="sxs-lookup"><span data-stu-id="36870-134">Decision point</span></span></td><td><ul><li><span data-ttu-id="36870-135">谁负责完成环境评估？</span><span class="sxs-lookup"><span data-stu-id="36870-135">Who will be responsible for completing an environment assessment?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/><span data-ttu-id="36870-136">后续步骤</span><span class="sxs-lookup"><span data-stu-id="36870-136">Next step</span></span></td><td><ul><li><span data-ttu-id="36870-137">记录环境评估的结果。</span><span class="sxs-lookup"><span data-stu-id="36870-137">Document the results of the environment assessment.</span></span></li></ul></td></tr>
</table>


## <a name="project-team"></a><span data-ttu-id="36870-138">项目团队</span><span class="sxs-lookup"><span data-stu-id="36870-138">Project team</span></span>

<span data-ttu-id="36870-139">确保已与项目团队的合适人员合作。</span><span class="sxs-lookup"><span data-stu-id="36870-139">Ensure that you've engaged the right people for your project team.</span></span> <span data-ttu-id="36870-140">验证在登记项目利益 [干系人 中完成的步骤](upgrade-enlist-stakeholders.md)。</span><span class="sxs-lookup"><span data-stu-id="36870-140">Verify the steps you completed in [Enlist your project stakeholders](upgrade-enlist-stakeholders.md).</span></span>

<span data-ttu-id="36870-141">评估环境后，继续执行下一步： [准备服务](upgrade-prepare-environment-prepare-service.md)。</span><span class="sxs-lookup"><span data-stu-id="36870-141">After you evaluate your environment, proceed to the next step: [Prepare your service](upgrade-prepare-environment-prepare-service.md).</span></span>