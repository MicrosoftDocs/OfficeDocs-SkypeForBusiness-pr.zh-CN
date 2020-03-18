---
title: 用户体验质量 |Microsoft 团队 |QoS |通话质量
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: 监视 Microsoft 团队的质量和使用所需的任务和活动
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
ms.openlocfilehash: e870c6e6561bac991e7b9498ef76162ec1fa2eb9
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706972"
---
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="3f950-103">体验质量检查指南</span><span class="sxs-lookup"><span data-stu-id="3f950-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="3f950-104">![图表突出显示升级旅程的操作卓越阶段](media/upgrade-banner-op-excellence.png "升级旅行阶段，重点关注运营卓越阶段")</span><span class="sxs-lookup"><span data-stu-id="3f950-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="3f950-105">本文是升级过程的 "卓越运营" 阶段的一部分，在您从 Skype for Business 升级到团队后立即开始。</span><span class="sxs-lookup"><span data-stu-id="3f950-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

<span data-ttu-id="3f950-106">[体验质量检查指南](https://aka.ms/qerguide)包括一组活动，这些活动在对改善用户体验有最大影响的关键领域中评估和提供补救指南，如下所示。</span><span class="sxs-lookup"><span data-stu-id="3f950-106">The [Quality of Experience Review Guide](https://aka.ms/qerguide) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="3f950-107">![查看过程中要检查的关键区域的插图。](media/plan-my-service-management-image2.png "在体验质量评审期间要检查的关键方面：音频、可靠性和用户调查结果。")</span><span class="sxs-lookup"><span data-stu-id="3f950-107">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="3f950-108">通过不断评估和修正指南中所述的区域，你可以降低对用户体验产生负面影响的可能性。</span><span class="sxs-lookup"><span data-stu-id="3f950-108">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="3f950-109">在部署中遇到的大多数用户体验问题可以分为以下类别：</span><span class="sxs-lookup"><span data-stu-id="3f950-109">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="3f950-110">防火墙或代理配置不完整</span><span class="sxs-lookup"><span data-stu-id="3f950-110">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="3f950-111">Wi-Fi 覆盖范围较小</span><span class="sxs-lookup"><span data-stu-id="3f950-111">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="3f950-112">带宽不足</span><span class="sxs-lookup"><span data-stu-id="3f950-112">Insufficient bandwidth</span></span>

- <span data-ttu-id="3f950-113">VPN</span><span class="sxs-lookup"><span data-stu-id="3f950-113">VPN</span></span>

- <span data-ttu-id="3f950-114">使用了未优化或内置的音频设备</span><span class="sxs-lookup"><span data-stu-id="3f950-114">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="3f950-115">子网或网络设备存在问题</span><span class="sxs-lookup"><span data-stu-id="3f950-115">Problematic subnets or network devices</span></span>

<span data-ttu-id="3f950-116">体验质量评审指南中提供的指南重点介绍如何使用呼叫质量仪表板（CQD）作为主要工具来报告和调查所述的每个区域，并重点关注音频以最大程度地提高采纳和影响。</span><span class="sxs-lookup"><span data-stu-id="3f950-116">The guidance provided in the Quality of Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="3f950-117">为了改进音频体验而对网络所做的任何优化也将会直接带来视频和桌面共享的改进。</span><span class="sxs-lookup"><span data-stu-id="3f950-117">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="3f950-118">我们强烈建议您提前提名本《质量专家提名。</span><span class="sxs-lookup"><span data-stu-id="3f950-118">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="3f950-119">在进行命名后，他们应开始熟悉[体验质量审核指南](https://aka.ms/qerguide)中的内容。</span><span class="sxs-lookup"><span data-stu-id="3f950-119">After being nominated, they should start to familiarize themselves with the content in the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

<!--ENDOFSECTION-->
