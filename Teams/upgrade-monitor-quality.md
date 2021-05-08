---
title: 用户体验质量|Microsoft Teams |QoS |呼叫质量
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: 管理员可以了解监视应用程序质量和使用情况所需的任务Microsoft Teams。
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
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="d2781-103">体验质量检查指南</span><span class="sxs-lookup"><span data-stu-id="d2781-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="d2781-104">![突出显示升级旅程的操作优化阶段的示意图](media/upgrade-banner-op-excellence.png "升级旅程的阶段，着重强调&quot;运营优化&quot;阶段")</span><span class="sxs-lookup"><span data-stu-id="d2781-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="d2781-105">本文是升级过程的操作优化阶段的一部分，一旦完成从 Skype for Business 到 Teams。</span><span class="sxs-lookup"><span data-stu-id="d2781-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

## <a name="improve-and-monitor-call-quality"></a><span data-ttu-id="d2781-106">改进和监视呼叫质量</span><span class="sxs-lookup"><span data-stu-id="d2781-106">Improve and monitor call quality</span></span>

<span data-ttu-id="d2781-107">[改进和](monitor-call-quality-qos.md)监视Teams包括一组活动，这些活动在对改善用户体验影响最大的关键领域进行评估和提供补救指导，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="d2781-107">[Improve and monitor call quality for Teams](monitor-call-quality-qos.md) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="d2781-108">![说明在评审期间要检查的关键区域。](media/plan-my-service-management-image2.png "在体验质量评审期间要检查的关键方面：音频、可靠性和用户测试结果。")</span><span class="sxs-lookup"><span data-stu-id="d2781-108">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="d2781-109">通过持续评估和修正本指南中所述的区域，可以减少它们可能对用户体验造成负面影响的可能性。</span><span class="sxs-lookup"><span data-stu-id="d2781-109">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="d2781-110">在部署中遇到的大多数用户体验问题可以分为以下类别：</span><span class="sxs-lookup"><span data-stu-id="d2781-110">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="d2781-111">防火墙或代理配置不完整</span><span class="sxs-lookup"><span data-stu-id="d2781-111">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="d2781-112">Wi-Fi 覆盖范围较小</span><span class="sxs-lookup"><span data-stu-id="d2781-112">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="d2781-113">带宽不足</span><span class="sxs-lookup"><span data-stu-id="d2781-113">Insufficient bandwidth</span></span>

- <span data-ttu-id="d2781-114">VPN</span><span class="sxs-lookup"><span data-stu-id="d2781-114">VPN</span></span>

- <span data-ttu-id="d2781-115">使用了未优化或内置的音频设备</span><span class="sxs-lookup"><span data-stu-id="d2781-115">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="d2781-116">子网或网络设备存在问题</span><span class="sxs-lookup"><span data-stu-id="d2781-116">Problematic subnets or network devices</span></span>

<span data-ttu-id="d2781-117">改进和监视[Teams](monitor-call-quality-qos.md)呼叫质量中提供的指南侧重于使用呼叫质量仪表板 (CQD) Online 作为主要工具来报告并调查所述的每个区域，并侧重于音频，以最大程度地提高采用和影响。</span><span class="sxs-lookup"><span data-stu-id="d2781-117">The guidance provided in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md) focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="d2781-118">为了改进音频体验而对网络所做的任何优化也将会直接带来视频和桌面共享的改进。</span><span class="sxs-lookup"><span data-stu-id="d2781-118">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="d2781-119">我们强烈建议你尽早提名质量冠军。</span><span class="sxs-lookup"><span data-stu-id="d2781-119">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="d2781-120">获得提名后，应开始熟悉改进和监视呼叫质量中的内容，以便[Teams。](monitor-call-quality-qos.md)</span><span class="sxs-lookup"><span data-stu-id="d2781-120">After being nominated, they should start to familiarize themselves with the content in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md).</span></span>

<!--ENDOFSECTION-->
