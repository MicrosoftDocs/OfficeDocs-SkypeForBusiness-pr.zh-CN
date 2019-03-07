---
title: 为从 Skype for Business 升级到 Teams 准备环境
author: turgayo
ms.author: turgayo
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: 在开始升级到团队从 Skype for Business 之前验证环境和网络准备。
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 485bd42198e54c5ccacc6296c31a19298d66ccf7
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/07/2019
ms.locfileid: "30464953"
---
<span data-ttu-id="1ca11-103">![升级旅程，重点强调的技术的准备阶段的阶段](media/upgrade-banner-tech-readiness.png "升级旅程，重点强调的技术的准备阶段的阶段")</span><span class="sxs-lookup"><span data-stu-id="1ca11-103">![Stages of the upgrade journey, with emphasis on the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="1ca11-104">本文是您升级旅程，与用户准备阶段并行完成的活动的技术的准备阶段的一部分。</span><span class="sxs-lookup"><span data-stu-id="1ca11-104">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="1ca11-105">在继续之前，确认您已完成从以前的阶段的这些活动：</span><span class="sxs-lookup"><span data-stu-id="1ca11-105">Before proceeding, confirm that you’ve completed these activities from previous stages:</span></span>

- [<span data-ttu-id="1ca11-106">登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="1ca11-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="1ca11-107">定义您的项目范围</span><span class="sxs-lookup"><span data-stu-id="1ca11-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="1ca11-108">商业和团队理解共存和 Skype 的互操作性</span><span class="sxs-lookup"><span data-stu-id="1ca11-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="1ca11-109">选择您升级旅程</span><span class="sxs-lookup"><span data-stu-id="1ca11-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prepare-your-environment-for-upgrading-to-teams"></a><span data-ttu-id="1ca11-110">准备升级到团队环境</span><span class="sxs-lookup"><span data-stu-id="1ca11-110">Prepare your environment for upgrading to Teams</span></span>

<span data-ttu-id="1ca11-111">您的组织中驱动团队升级成功，很重要，验证您当前的 Skype 业务环境和网络准备。</span><span class="sxs-lookup"><span data-stu-id="1ca11-111">To drive a successful Teams upgrade in your organization, it’s important that you validate your current Skype for Business environment and your network readiness.</span></span> <span data-ttu-id="1ca11-112">准备您的当前环境有助于确保高品质用户体验现在，除了提高用户质量体验中的团队。</span><span class="sxs-lookup"><span data-stu-id="1ca11-112">Preparing your current environment will help ensure a high-quality user experience now, in addition to improving the quality of the user experience in Teams.</span></span> <span data-ttu-id="1ca11-113">花点时间规划各个步骤可帮助加快您的部署，并确保您没有已跳过任何重要操作项目。</span><span class="sxs-lookup"><span data-stu-id="1ca11-113">Taking time to plan individual steps can help accelerate your deployment and ensure that you haven’t skipped any important action items.</span></span>

<span data-ttu-id="1ca11-114">完成与您的用户准备情况准备并行的这些活动：</span><span class="sxs-lookup"><span data-stu-id="1ca11-114">Complete these activities in parallel with your user readiness preparation:</span></span>

- <span data-ttu-id="1ca11-115">[准备您的 IT 员工](upgrade-prepare-IT-pros.md)，以帮助确保拥有所需的成功升级旅程什么。</span><span class="sxs-lookup"><span data-stu-id="1ca11-115">[Prepare your IT staff](upgrade-prepare-IT-pros.md) to help ensure they have what they need for a successful upgrade journey.</span></span>
- <span data-ttu-id="1ca11-116">确认环境满足所有[先决条件](upgrade-plan-journey-prerequisites.md)，并了解 Office 365 服务和团队之间的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="1ca11-116">Verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md), and understand dependencies among Office 365 services and Teams.</span></span>
- <span data-ttu-id="1ca11-117">通过使用示例调查表确认贵组织的就绪性将要向工作组成功升级旅程执行环境发现[评估您的环境](upgrade-plan-journey-evaluate-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="1ca11-117">[Evaluate your environment](upgrade-plan-journey-evaluate-environment.md) by performing environmental discovery by using a sample questionnaire to confirm your organization’s readiness to undertake a successful upgrade journey to Teams.</span></span>
- <span data-ttu-id="1ca11-118">[准备您的网络](upgrade-prepare-environment-prepare-network.md)规划、 准备，并使您的网络任何所需的补救步骤以支持团队工作负载。</span><span class="sxs-lookup"><span data-stu-id="1ca11-118">[Prepare your network](upgrade-prepare-environment-prepare-network.md) through planning, preparation, and taking any necessary remediation steps for your network to support Teams workloads.</span></span>
- <span data-ttu-id="1ca11-119">使用入职培训清单以确保您的团队配置已准备好支持从 for Business 的 Skype 的用户迁移到团队的推出[准备您的服务](upgrade-prepare-environment-prepare-service.md)。</span><span class="sxs-lookup"><span data-stu-id="1ca11-119">[Prepare your service](upgrade-prepare-environment-prepare-service.md) for rollout by using onboarding checklists to ensure that your Teams configuration is ready to support migrating your users from Skype for Business to Teams.</span></span>