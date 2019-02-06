---
title: 在 Microsoft Teams 中实施 QoS 和监控通话分析
author: jambirk
ms.author: jambirk
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: jambirk
description: 使用服务质量 (QoS) 设置，然后调用分析和呼叫质量仪表板中的 Microsoft 团队。
localization_priority: Normal
search.appverid: MET150
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.openlocfilehash: 505409ac51552a99fabc4eb41801a1f19a737877
ms.sourcegitcommit: 6205201cb1314e753f672654dade11dd4adbfe8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2019
ms.locfileid: "29742947"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a><span data-ttu-id="33d53-103">在 Microsoft 团队中实现 QoS 和监视呼叫质量</span><span class="sxs-lookup"><span data-stu-id="33d53-103">Implement QoS and Monitor Call Quality in Microsoft Teams</span></span>

## <a name="get-started"></a><span data-ttu-id="33d53-104">入门</span><span class="sxs-lookup"><span data-stu-id="33d53-104">Get Started</span></span>

<span data-ttu-id="33d53-105">换 ups 当用户开始使用团队进行呼叫和按住会议，它们都可能会发现扬声器或 chopping 注销呼叫或会议。</span><span class="sxs-lookup"><span data-stu-id="33d53-105">As your users start using Teams for making calls and holding meetings, they may find speakers breaking ups or chopping in and out of a call or meeting.</span></span> <span data-ttu-id="33d53-106">共享的视频可能会冻结或 pixellate，或完全失败。</span><span class="sxs-lookup"><span data-stu-id="33d53-106">Shared video may freeze or pixellate, or fail altogether.</span></span> <span data-ttu-id="33d53-107">这是由于表示语音和视频流量遇到网络拥塞和到达按顺序或者根本不 IP 数据包。</span><span class="sxs-lookup"><span data-stu-id="33d53-107">This is due to the IP packets that represent voice and video traffic encountering network congestion and arriving out of sequence or not at all.</span></span> <span data-ttu-id="33d53-108">有方法可以防止出现这种以及如何确定其他问题时它们公开，主要的服务质量 (QoS)。</span><span class="sxs-lookup"><span data-stu-id="33d53-108">There are ways to prevent this and identify other problems when they surface, primarily Quality of Service (QoS).</span></span>

<span data-ttu-id="33d53-109">[**服务质量 (QoS)**](monitor-call-quality-qos.md)是一种方法，以确定对延迟和拥塞现象，敏感的数据包，然后与优先处理提供数据包，以便他们遇到远远小于拥塞。</span><span class="sxs-lookup"><span data-stu-id="33d53-109">[**Quality of Service (QoS)**](monitor-call-quality-qos.md)  is a way to identify packets that are sensitive to delays and congestion, and then provide the packets with preferential treatment so they encounter far less congestion.</span></span> <span data-ttu-id="33d53-110">现在，我们将只需说，它十分相似发送至邮件信件： 如果您将其发送它获取很快存在并且的足够了，如果您将其发送它获取大量更快、 存在的第一个类和如果优先级邮件发送的书籍速率它在两天内那里获取。</span><span class="sxs-lookup"><span data-stu-id="33d53-110">For now, we'll just say that it's a lot like sending a letter through the Mail: If you send it book rate it gets there pretty soon and that's good enough, if you send it first class it gets there a lot faster, and if you send it Priority Mail, it gets there within two days.</span></span> <span data-ttu-id="33d53-111">当然网络运行速度大于邮件，但它仍然运行速度是关键某些应用程序，而不是其他人如此重要，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="33d53-111">Of course networks run faster than the mail, but it still runs true that speed is critical for some applications and is not so critical for others.</span></span> <span data-ttu-id="33d53-112">本主题本质上是详细和难理解，但它使用户体验，以便它具有巨大区别值得方面投入时间和能耗提前。</span><span class="sxs-lookup"><span data-stu-id="33d53-112">This subject is inherently detailed and tricky to understand at first, but it makes a huge difference in the user experience so it's worth investing time and energy upfront.</span></span>

<span data-ttu-id="33d53-113">理想情况下将在内部网络时设置团队上实现 QoS，但如果您是小型足够它可以为可选。</span><span class="sxs-lookup"><span data-stu-id="33d53-113">Ideally you would implement QoS on your internal network while setting up Teams, but if you're small enough it can be optional.</span></span> <span data-ttu-id="33d53-114">这样的延迟敏感语音和视频流量以获取其他通信之前确定其优先级。</span><span class="sxs-lookup"><span data-stu-id="33d53-114">This allows the delay-sensitive voice and video traffic to get prioritized ahead of other traffic.</span></span> <span data-ttu-id="33d53-115">在网络中，可以实现此上的所有客户端设备，以及开关和路由器上的优先顺序。</span><span class="sxs-lookup"><span data-stu-id="33d53-115">You'd do this prioritization on all the client devices, as well as on the switches and routers in your network.</span></span>

<span data-ttu-id="33d53-116">[**调用分析和呼叫质量仪表板**](difference-between-call-analytics-and-call-quality-dashboard.md)用于查找和解决日常操作过程中遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="33d53-116">[**Call Analytics and Call Quality Dashboard**](difference-between-call-analytics-and-call-quality-dashboard.md) are used to find and troubleshoot problems that come up during ongoing operation.</span></span>  

<span data-ttu-id="33d53-117">呼叫分析显示设备、 网络和与特定的呼叫和会议中每个用户的 Microsoft 团队或 Skype 业务帐户相关的连接的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="33d53-117">Call Analytics shows detailed information about the devices, networks, and connectivity related to the specific calls and meetings for each user in a Microsoft Teams or Skype for Business account.</span></span> <span data-ttu-id="33d53-118">如果您是 Office 365 管理员，您可以使用调用分析解决特定呼叫中有经验的呼叫质量和连接问题。</span><span class="sxs-lookup"><span data-stu-id="33d53-118">If you're an Office 365 admin, you can use Call Analytics to troubleshoot call quality and connection problems experienced in a specific call.</span></span> <span data-ttu-id="33d53-119">这可以帮助您确定并消除问题。</span><span class="sxs-lookup"><span data-stu-id="33d53-119">This can help you to identify and eliminate problems.</span></span>

<span data-ttu-id="33d53-120">呼叫质量仪表板 (CQD) 旨在帮助管理员和网络工程师将优化**网络**、 不分析和疑难解答单个呼叫。</span><span class="sxs-lookup"><span data-stu-id="33d53-120">Call Quality Dashboard (CQD) is designed to help admins and network engineers optimize a **network**, not analyze and troubleshoot a single call.</span></span> <span data-ttu-id="33d53-121">CQD 将焦点转移从特定的用户可以这样看待为整个组织的聚合信息。</span><span class="sxs-lookup"><span data-stu-id="33d53-121">CQD shifts focus from specific users to look at aggregated information for an entire organization.</span></span> <span data-ttu-id="33d53-122">这可以帮助您确定并消除问题。</span><span class="sxs-lookup"><span data-stu-id="33d53-122">This can also help you to identify and eliminate problems.</span></span>

## <a name="related-topics"></a><span data-ttu-id="33d53-123">相关主题</span><span class="sxs-lookup"><span data-stu-id="33d53-123">Related Topics</span></span>

[<span data-ttu-id="33d53-124">视频： 呼叫质量概述</span><span class="sxs-lookup"><span data-stu-id="33d53-124">Video: Call Quality Overview</span></span>](https://aka.ms/teams-quality)

[<span data-ttu-id="33d53-125">设置呼叫分析</span><span class="sxs-lookup"><span data-stu-id="33d53-125">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="33d53-126">使用通话分析解决通话质量不佳的问题</span><span class="sxs-lookup"><span data-stu-id="33d53-126">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="33d53-127">打开和使用呼叫质量仪表板</span><span class="sxs-lookup"><span data-stu-id="33d53-127">Turning on and using Call Quality Dashboard </span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="33d53-128">通话质量仪表板中可用的维度和衡量指标</span><span class="sxs-lookup"><span data-stu-id="33d53-128">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="33d53-129">通话质量仪表板中的流分类</span><span class="sxs-lookup"><span data-stu-id="33d53-129">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)