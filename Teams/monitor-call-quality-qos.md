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
ms.openlocfilehash: 097426e60ebcd141d1c8375343509db5607c50e2
ms.sourcegitcommit: ad126165b6440b98e550ab48e6b3491aeba9402b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/22/2019
ms.locfileid: "30205768"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a><span data-ttu-id="4b959-103">在 Microsoft 团队中实现 QoS 和监视呼叫质量</span><span class="sxs-lookup"><span data-stu-id="4b959-103">Implement QoS and Monitor Call Quality in Microsoft Teams</span></span>

## <a name="get-started"></a><span data-ttu-id="4b959-104">入门</span><span class="sxs-lookup"><span data-stu-id="4b959-104">Get Started</span></span>

<span data-ttu-id="4b959-105">用户开始使用团队进行呼叫和按住会议，它们可能会遇到分解 chopping 注销呼叫或会议的呼叫者的语音。</span><span class="sxs-lookup"><span data-stu-id="4b959-105">As your users start using Teams for making calls and holding meetings, they may experience a caller's voice breaking up or chopping in and out of a call or meeting.</span></span> <span data-ttu-id="4b959-106">共享视频年 5 月冻结或像素化，或完全失败。</span><span class="sxs-lookup"><span data-stu-id="4b959-106">Shared video may freeze or pixelate, or fail altogether.</span></span> <span data-ttu-id="4b959-107">这是由于表示语音和视频流量遇到网络拥塞和到达按顺序或者根本不 IP 数据包。</span><span class="sxs-lookup"><span data-stu-id="4b959-107">This is due to the IP packets that represent voice and video traffic encountering network congestion and arriving out of sequence or not at all.</span></span> <span data-ttu-id="4b959-108">有显现和防止其返回时，主要的服务质量 (QoS) 时确定这些问题的方法。</span><span class="sxs-lookup"><span data-stu-id="4b959-108">There are ways to identify these problems when they surface and prevent their return, primarily Quality of Service (QoS).</span></span>

<span data-ttu-id="4b959-109">**服务质量 (QoS)** 是一种方法，以允许 （如语音或视频流） 网络延迟"剪切行中"（如下载新应用程序，其中下载的额外的第二个不太敏感的通信之前对敏感的实时网络流量不大不了）。</span><span class="sxs-lookup"><span data-stu-id="4b959-109">**Quality of Service (QoS)** is a way to allow real-time network traffic (like voice or video streams) that is sensitive to network delays to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal).</span></span> <span data-ttu-id="4b959-110">QoS 标识标记中使用 Windows 组策略对象的实时流的所有数据包和名为基于端口的访问控制列表，然后帮助您为提供语音、 视频和屏幕共享的网络的路由功能流自己专用的部分网络带宽。</span><span class="sxs-lookup"><span data-stu-id="4b959-110">QoS identifies and marks all packets in real-time streams using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, which then helps your network to give voice, video, and screen share streams their own dedicated portions of network bandwidth.</span></span>

 <span data-ttu-id="4b959-111">现在，我们将只需说，它十分相似发送至邮件信件： 如果您将其发送它获取很快存在并且的足够了，如果您将其发送它获取大量更快、 存在的第一个类和如果优先级邮件发送的书籍速率它在两天内那里获取。</span><span class="sxs-lookup"><span data-stu-id="4b959-111">For now, we'll just say that it's a lot like sending a letter through the mail: If you send it book rate it gets there pretty soon and that's good enough, if you send it first class it gets there a lot faster, and if you send it Priority Mail, it gets there within two days.</span></span> <span data-ttu-id="4b959-112">当然网络运行速度大于邮件，但它仍然运行速度是关键某些应用程序，而不是其他人如此重要，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="4b959-112">Of course networks run faster than the mail, but it still runs true that speed is critical for some applications and is not so critical for others.</span></span> <span data-ttu-id="4b959-113">本主题本质上是详细和难理解，但它使用户体验，以便它具有巨大区别值得方面投入时间和能耗提前。</span><span class="sxs-lookup"><span data-stu-id="4b959-113">This subject is inherently detailed and tricky to understand at first, but it makes a huge difference in the user experience so it's worth investing time and energy upfront.</span></span> <span data-ttu-id="4b959-114">读取[实现的服务质量 (QoS) 中的 Microsoft 团队](QoS-in-Teams.md)的更详细的讨论。</span><span class="sxs-lookup"><span data-stu-id="4b959-114">Read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md) for a more detailed discussion.</span></span>

<span data-ttu-id="4b959-115">理想情况下将在内部网络时设置团队上实现 QoS，但如果您是小型足够它可以为可选。</span><span class="sxs-lookup"><span data-stu-id="4b959-115">Ideally you would implement QoS on your internal network while setting up Teams, but if you're small enough it can be optional.</span></span> <span data-ttu-id="4b959-116">这样的延迟敏感语音和视频流量以获取其他通信之前确定其优先级。</span><span class="sxs-lookup"><span data-stu-id="4b959-116">This allows the delay-sensitive voice and video traffic to get prioritized ahead of other traffic.</span></span> <span data-ttu-id="4b959-117">在网络中，可以实现此上的所有[客户端设备](QoS-in-Teams-clients.md)，在[Microsoft 团队管理中心](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)中，以及开关和路由器上的优先顺序。</span><span class="sxs-lookup"><span data-stu-id="4b959-117">You'd do this prioritization on all the [client devices](QoS-in-Teams-clients.md), in the [Microsoft Teams admin center](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings), as well as on the switches and routers in your network.</span></span>

<span data-ttu-id="4b959-118">[**调用分析和呼叫质量仪表板**](difference-between-call-analytics-and-call-quality-dashboard.md)用于查找和解决日常操作过程中遇到的问题。</span><span class="sxs-lookup"><span data-stu-id="4b959-118">[**Call Analytics and Call Quality Dashboard**](difference-between-call-analytics-and-call-quality-dashboard.md) are used to find and troubleshoot problems that come up during ongoing operation.</span></span>  

<span data-ttu-id="4b959-119">**调用分析**显示设备、 网络和连接到***特定的呼叫和会议的***每个用户的 Microsoft 团队或 Skype 中业务帐户相关的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="4b959-119">**Call Analytics** shows detailed information about the devices, networks, and connectivity related to  ***specific calls and meetings*** for each user in a Microsoft Teams or Skype for Business account.</span></span> <span data-ttu-id="4b959-120">如果您是 Office 365 管理员，您可以使用调用分析解决特定呼叫中有经验的呼叫质量和连接问题。</span><span class="sxs-lookup"><span data-stu-id="4b959-120">If you're an Office 365 admin, you can use Call Analytics to troubleshoot call quality and connection problems experienced in a specific call.</span></span> <span data-ttu-id="4b959-121">这可以帮助您确定并消除问题。</span><span class="sxs-lookup"><span data-stu-id="4b959-121">This can help you to identify and eliminate problems.</span></span>

<span data-ttu-id="4b959-122">**呼叫质量仪表板 (CQD)** 旨在帮助管理员和网络工程师将优化***网络***、 不分析和疑难解答单个呼叫。</span><span class="sxs-lookup"><span data-stu-id="4b959-122">**Call Quality Dashboard (CQD)** is designed to help admins and network engineers optimize their ***network***, not analyze and troubleshoot a single call.</span></span> <span data-ttu-id="4b959-123">CQD 将焦点转移从特定的用户可以这样看待为整个组织的聚合信息。</span><span class="sxs-lookup"><span data-stu-id="4b959-123">CQD shifts focus from specific users to look at aggregated information for an entire organization.</span></span> <span data-ttu-id="4b959-124">这可以帮助您确定并消除问题。</span><span class="sxs-lookup"><span data-stu-id="4b959-124">This can also help you to identify and eliminate problems.</span></span>

## <a name="related-topics"></a><span data-ttu-id="4b959-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="4b959-125">Related Topics</span></span>

[<span data-ttu-id="4b959-126">在 Microsoft 团队中实现服务质量 (QoS)</span><span class="sxs-lookup"><span data-stu-id="4b959-126">Implement Quality of Service (QoS) in Microsoft Teams</span></span>](QoS-in-Teams.md)

[<span data-ttu-id="4b959-127">视频： 呼叫质量概述</span><span class="sxs-lookup"><span data-stu-id="4b959-127">Video: Call Quality Overview</span></span>](https://aka.ms/teams-quality)

[<span data-ttu-id="4b959-128">设置通话分析</span><span class="sxs-lookup"><span data-stu-id="4b959-128">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="4b959-129">使用通话分析来排查通话质量不良问题</span><span class="sxs-lookup"><span data-stu-id="4b959-129">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="4b959-130">打开并使用通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="4b959-130">Turning on and using Call Quality Dashboard</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="4b959-131">通话质量仪表板中可用的维度和衡量指标</span><span class="sxs-lookup"><span data-stu-id="4b959-131">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="4b959-132">通话质量仪表板中的流分类</span><span class="sxs-lookup"><span data-stu-id="4b959-132">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)