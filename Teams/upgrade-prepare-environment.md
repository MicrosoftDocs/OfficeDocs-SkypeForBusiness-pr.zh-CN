---
title: 准备环境以升级到 Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: 在开始从云到云的升级之前，请验证Skype for Business和网络Teams。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e154dc5844c4b8f3994c8c7bc00865c494a4c8c6
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282139"
---
# <a name="prepare-your-environment-for-upgrading-to-teams"></a><span data-ttu-id="968a0-103">准备环境以升级到 Teams</span><span class="sxs-lookup"><span data-stu-id="968a0-103">Prepare your environment for upgrading to Teams</span></span>

<span data-ttu-id="968a0-104">![升级过程图，强调技术准备阶段](media/upgrade-banner-tech-readiness.png "升级过程阶段，着重强调技术准备阶段")</span><span class="sxs-lookup"><span data-stu-id="968a0-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="968a0-105">本文是升级过程的技术准备阶段（与用户准备阶段并行完成的活动）的一部分。</span><span class="sxs-lookup"><span data-stu-id="968a0-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="968a0-106">在继续之前，请确认已完成之前阶段中的这些活动：</span><span class="sxs-lookup"><span data-stu-id="968a0-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="968a0-107">登记项目利益干系人</span><span class="sxs-lookup"><span data-stu-id="968a0-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="968a0-108">请确定项目范围</span><span class="sxs-lookup"><span data-stu-id="968a0-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="968a0-109">了解两者共存Skype for Business互操作性Teams</span><span class="sxs-lookup"><span data-stu-id="968a0-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="968a0-110">选择了升级旅程</span><span class="sxs-lookup"><span data-stu-id="968a0-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="968a0-111">若要在组织中Teams升级，必须验证当前Skype for Business网络就绪性。</span><span class="sxs-lookup"><span data-stu-id="968a0-111">To drive a successful Teams upgrade in your organization, it's important that you validate your current Skype for Business environment and your network readiness.</span></span> <span data-ttu-id="968a0-112">准备当前环境有助于确保现在获得高质量的用户体验，此外，还有助于改善用户在 Teams。</span><span class="sxs-lookup"><span data-stu-id="968a0-112">Preparing your current environment will help ensure a high-quality user experience now, in addition to improving the quality of the user experience in Teams.</span></span> <span data-ttu-id="968a0-113">花时间规划各个步骤有助于加快部署，并确保未跳过任何重要操作项目。</span><span class="sxs-lookup"><span data-stu-id="968a0-113">Taking time to plan individual steps can help accelerate your deployment and ensure that you haven't skipped any important action items.</span></span>

<span data-ttu-id="968a0-114">在用户准备准备的同时完成这些活动：</span><span class="sxs-lookup"><span data-stu-id="968a0-114">Complete these activities in parallel with your user readiness preparation:</span></span>

- <span data-ttu-id="968a0-115">[让 IT 人员](upgrade-prepare-IT-pros.md) 做好准备，帮助确保他们拥有成功完成升级旅程所需的功能。</span><span class="sxs-lookup"><span data-stu-id="968a0-115">[Prepare your IT staff](upgrade-prepare-IT-pros.md) to help ensure they have what they need for a successful upgrade journey.</span></span>
- <span data-ttu-id="968a0-116">验证环境是否满足所有[先决条件](upgrade-plan-journey-prerequisites.md)，并了解Microsoft 365或Office 365服务Teams。</span><span class="sxs-lookup"><span data-stu-id="968a0-116">Verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md), and understand dependencies among Microsoft 365 or Office 365 services and Teams.</span></span>
- <span data-ttu-id="968a0-117">[通过使用示例](upgrade-plan-journey-evaluate-environment.md)调查问卷执行环境发现来评估环境，以确认组织是否准备好进行成功的升级过程，Teams。</span><span class="sxs-lookup"><span data-stu-id="968a0-117">[Evaluate your environment](upgrade-plan-journey-evaluate-environment.md) by performing environmental discovery by using a sample questionnaire to confirm your organization's readiness to undertake a successful upgrade journey to Teams.</span></span>
- <span data-ttu-id="968a0-118">[通过规划](prepare-network.md)、准备和采取任何必要的补救措施为网络准备网络，以支持Teams工作负荷。</span><span class="sxs-lookup"><span data-stu-id="968a0-118">[Prepare your network](prepare-network.md) through planning, preparation, and taking any necessary remediation steps for your network to support Teams workloads.</span></span>
- <span data-ttu-id="968a0-119">[使用载入](upgrade-prepare-environment-prepare-service.md)清单准备推出服务，以确保 Teams 配置已准备好支持将用户从 Skype for Business 迁移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="968a0-119">[Prepare your service](upgrade-prepare-environment-prepare-service.md) for rollout by using onboarding checklists to ensure that your Teams configuration is ready to support migrating your users from Skype for Business to Teams.</span></span>