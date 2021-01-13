---
title: 用户体验质量 |Microsoft Teams |QoS |呼叫质量
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 管理员可以了解监视 Microsoft Teams 质量和使用情况所需的任务和活动。
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
ms.openlocfilehash: d57f01887961ad0c458b13db20ba79023272bcdf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808992"
---
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="da95c-103">体验质量检查指南</span><span class="sxs-lookup"><span data-stu-id="da95c-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="da95c-104">![突出显示升级旅程的操作卓越阶段的示意图](media/upgrade-banner-op-excellence.png "升级旅程的阶段，侧重于"运营优化"阶段")</span><span class="sxs-lookup"><span data-stu-id="da95c-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="da95c-105">本文是升级旅程的操作优化阶段的一部分，完成从 Skype for Business 到 Teams 的升级后，即会立即开始。</span><span class="sxs-lookup"><span data-stu-id="da95c-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

## <a name="improve-and-monitor-call-quality"></a><span data-ttu-id="da95c-106">改进和监视呼叫质量</span><span class="sxs-lookup"><span data-stu-id="da95c-106">Improve and monitor call quality</span></span>

<span data-ttu-id="da95c-107">[改进和监视 Teams](monitor-call-quality-qos.md) 的呼叫质量包括一组活动，这些活动在对改善用户体验影响最大的关键领域进行评估和提供补救指导，如下所示。</span><span class="sxs-lookup"><span data-stu-id="da95c-107">[Improve and monitor call quality for Teams](monitor-call-quality-qos.md) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="da95c-108">![在评审期间要检查的关键区域插图。](media/plan-my-service-management-image2.png "在体验质量评审期间要检查的关键方面：音频、可靠性和用户测试结果。")</span><span class="sxs-lookup"><span data-stu-id="da95c-108">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="da95c-109">通过持续评估和修正本指南中所述的方面，可以减少这些方面对用户体验造成负面影响的可能性。</span><span class="sxs-lookup"><span data-stu-id="da95c-109">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="da95c-110">在部署中遇到的大多数用户体验问题可以分为以下类别：</span><span class="sxs-lookup"><span data-stu-id="da95c-110">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="da95c-111">防火墙或代理配置不完整</span><span class="sxs-lookup"><span data-stu-id="da95c-111">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="da95c-112">Wi-Fi 覆盖范围较小</span><span class="sxs-lookup"><span data-stu-id="da95c-112">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="da95c-113">带宽不足</span><span class="sxs-lookup"><span data-stu-id="da95c-113">Insufficient bandwidth</span></span>

- <span data-ttu-id="da95c-114">VPN</span><span class="sxs-lookup"><span data-stu-id="da95c-114">VPN</span></span>

- <span data-ttu-id="da95c-115">使用了未优化或内置的音频设备</span><span class="sxs-lookup"><span data-stu-id="da95c-115">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="da95c-116">子网或网络设备存在问题</span><span class="sxs-lookup"><span data-stu-id="da95c-116">Problematic subnets or network devices</span></span>

<span data-ttu-id="da95c-117">[在改进](monitor-call-quality-qos.md)和监视 Teams 的呼叫质量中提供的指南侧重于使用呼叫质量仪表板 (CQD) Online 作为主要工具来报告并调查所述的每个领域，并侧重于音频以最大程度地提高采用和影响。</span><span class="sxs-lookup"><span data-stu-id="da95c-117">The guidance provided in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md) focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="da95c-118">为了改进音频体验而对网络所做的任何优化也将会直接带来视频和桌面共享的改进。</span><span class="sxs-lookup"><span data-stu-id="da95c-118">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="da95c-119">我们强烈建议你尽早提名质量好手。</span><span class="sxs-lookup"><span data-stu-id="da95c-119">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="da95c-120">提名后，他们应开始熟悉"改进和监视 Teams 通话质量 ["中的内容](monitor-call-quality-qos.md)。</span><span class="sxs-lookup"><span data-stu-id="da95c-120">After being nominated, they should start to familiarize themselves with the content in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md).</span></span>

<!--ENDOFSECTION-->
