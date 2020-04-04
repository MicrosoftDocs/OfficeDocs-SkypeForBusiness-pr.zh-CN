---
title: 实施 QoS 和监控呼叫分析
author: dstrome
ms.author: dstrome
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: ''
description: 使用 "服务质量（QoS）" 设置，然后在 Microsoft 团队中调用分析和通话质量仪表板。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5ecf199f5027774684f5a626c416f789293926d7
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43140051"
---
# <a name="implement-qos-and-monitor-call-quality-in-microsoft-teams"></a><span data-ttu-id="6eb48-103">在 Microsoft 团队中实施 QoS 和监控通话质量</span><span class="sxs-lookup"><span data-stu-id="6eb48-103">Implement QoS and Monitor Call Quality in Microsoft Teams</span></span>

## <a name="get-started"></a><span data-ttu-id="6eb48-104">入门</span><span class="sxs-lookup"><span data-stu-id="6eb48-104">Get Started</span></span>

<span data-ttu-id="6eb48-105">当用户开始使用团队进行呼叫和召开会议时，他们可能会遇到呼叫或会议的呼叫者语音或 chopping。</span><span class="sxs-lookup"><span data-stu-id="6eb48-105">As your users start using Teams for making calls and holding meetings, they may experience a caller's voice breaking up or chopping in and out of a call or meeting.</span></span> <span data-ttu-id="6eb48-106">共享视频可能冻结或像素化，或者完全失败。</span><span class="sxs-lookup"><span data-stu-id="6eb48-106">Shared video may freeze or pixelate, or fail altogether.</span></span> <span data-ttu-id="6eb48-107">这是由于表示语音和视频流量导致网络拥塞的 IP 数据包，或者根本就不在序列中。</span><span class="sxs-lookup"><span data-stu-id="6eb48-107">This is due to the IP packets that represent voice and video traffic encountering network congestion and arriving out of sequence or not at all.</span></span> <span data-ttu-id="6eb48-108">有多种方法可在它们表面上发现这些问题并防止其返回，主要是服务质量（QoS）。</span><span class="sxs-lookup"><span data-stu-id="6eb48-108">There are ways to identify these problems when they surface and prevent their return, primarily Quality of Service (QoS).</span></span>

<span data-ttu-id="6eb48-109">**服务质量（QoS）** 是一种允许实时网络流量（如语音或视频流）的一种方法，该功能对网络延迟非常敏感（如下载新应用程序，这种情况下，下载不太多的情况）。</span><span class="sxs-lookup"><span data-stu-id="6eb48-109">**Quality of Service (QoS)** is a way to allow real-time network traffic (like voice or video streams) that is sensitive to network delays to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal).</span></span> <span data-ttu-id="6eb48-110">QoS 使用 Windows 组策略对象和一个名为基于端口的访问控制列表的路由功能，在实时流中标识和标记所有数据包，这样就可以帮助您的网络提供语音、视频和屏幕共享，以流出自己专用的网络带宽部分。</span><span class="sxs-lookup"><span data-stu-id="6eb48-110">QoS identifies and marks all packets in real-time streams using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, which then helps your network to give voice, video, and screen share streams their own dedicated portions of network bandwidth.</span></span>

 <span data-ttu-id="6eb48-111">现在，我们将只是说它非常喜欢通过邮件发送信件：如果你向其发送一条短信，那么，如果你将其发送到第一类，它获得的速度会更快，并且如果你发送它的优先级邮件，它将在两天内收到。</span><span class="sxs-lookup"><span data-stu-id="6eb48-111">For now, we'll just say that it's a lot like sending a letter through the mail: If you send it book rate it gets there pretty soon and that's good enough, if you send it first class it gets there a lot faster, and if you send it Priority Mail, it gets there within two days.</span></span> <span data-ttu-id="6eb48-112">当然，网络比邮件运行速度更快，但它仍会运行，速度对某些应用程序至关重要，对其他应用不太重要。</span><span class="sxs-lookup"><span data-stu-id="6eb48-112">Of course networks run faster than the mail, but it still runs true that speed is critical for some applications and is not so critical for others.</span></span> <span data-ttu-id="6eb48-113">这种主题在最初的理解中很难理解，但它在用户体验方面的差异非常大，因此需要提前投入大量时间和精力。</span><span class="sxs-lookup"><span data-stu-id="6eb48-113">This subject is inherently detailed and tricky to understand at first, but it makes a huge difference in the user experience so it's worth investing time and energy upfront.</span></span> <span data-ttu-id="6eb48-114">阅读[Microsoft 团队中的实施服务质量（QoS）](QoS-in-Teams.md) ，以便更详细地讨论。</span><span class="sxs-lookup"><span data-stu-id="6eb48-114">Read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md) for a more detailed discussion.</span></span>

<span data-ttu-id="6eb48-115">理想情况下，你可以在你的内部网络上实现 QoS，同时设置团队，但如果你的空间足够小，则可以选择。</span><span class="sxs-lookup"><span data-stu-id="6eb48-115">Ideally you would implement QoS on your internal network while setting up Teams, but if you're small enough it can be optional.</span></span> <span data-ttu-id="6eb48-116">这允许对延迟敏感的语音和视频流量进行优先排列，使其优先于其他流量。</span><span class="sxs-lookup"><span data-stu-id="6eb48-116">This allows the delay-sensitive voice and video traffic to get prioritized ahead of other traffic.</span></span> <span data-ttu-id="6eb48-117">你将在[Microsoft 团队管理中心](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)以及你的网络中的交换机和路由器上对所有[客户端设备](QoS-in-Teams-clients.md)执行此优先顺序。</span><span class="sxs-lookup"><span data-stu-id="6eb48-117">You'd do this prioritization on all the [client devices](QoS-in-Teams-clients.md), in the [Microsoft Teams admin center](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings), as well as on the switches and routers in your network.</span></span>

<span data-ttu-id="6eb48-118">"[**呼叫分析" 和 "呼叫质量" 仪表板**](difference-between-call-analytics-and-call-quality-dashboard.md)用于查找和解决正在进行的操作中出现的问题。</span><span class="sxs-lookup"><span data-stu-id="6eb48-118">[**Call Analytics and Call Quality Dashboard**](difference-between-call-analytics-and-call-quality-dashboard.md) are used to find and troubleshoot problems that come up during ongoing operation.</span></span>  

<span data-ttu-id="6eb48-119">"**呼叫分析**" 显示与 Microsoft 团队或 Skype for business 帐户中每个用户的***特定呼叫和会议***相关的设备、网络和连接的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6eb48-119">**Call Analytics** shows detailed information about the devices, networks, and connectivity related to  ***specific calls and meetings*** for each user in a Microsoft Teams or Skype for Business account.</span></span> <span data-ttu-id="6eb48-120">如果你是 Office 365 管理员，则可以使用呼叫分析解决特定呼叫中遇到的通话质量和连接问题。</span><span class="sxs-lookup"><span data-stu-id="6eb48-120">If you're an Office 365 admin, you can use Call Analytics to troubleshoot call quality and connection problems experienced in a specific call.</span></span> <span data-ttu-id="6eb48-121">这可以帮助你识别和消除问题。</span><span class="sxs-lookup"><span data-stu-id="6eb48-121">This can help you to identify and eliminate problems.</span></span>

<span data-ttu-id="6eb48-122">**通话质量仪表板（CQD）** 旨在帮助管理员和网络工程师优化***网络***，而不是分析和解决单个通话。</span><span class="sxs-lookup"><span data-stu-id="6eb48-122">**Call Quality Dashboard (CQD)** is designed to help admins and network engineers optimize their ***network***, not analyze and troubleshoot a single call.</span></span> <span data-ttu-id="6eb48-123">CQD 将焦点从特定用户转移，以查看整个组织的聚合信息。</span><span class="sxs-lookup"><span data-stu-id="6eb48-123">CQD shifts focus from specific users to look at aggregated information for an entire organization.</span></span> <span data-ttu-id="6eb48-124">这还可以帮助你识别和消除问题。</span><span class="sxs-lookup"><span data-stu-id="6eb48-124">This can also help you to identify and eliminate problems.</span></span>

## <a name="related-topics"></a><span data-ttu-id="6eb48-125">相关主题</span><span class="sxs-lookup"><span data-stu-id="6eb48-125">Related Topics</span></span>

[<span data-ttu-id="6eb48-126">在 Microsoft 团队中实施服务质量（QoS）</span><span class="sxs-lookup"><span data-stu-id="6eb48-126">Implement Quality of Service (QoS) in Microsoft Teams</span></span>](QoS-in-Teams.md)

[<span data-ttu-id="6eb48-127">视频：通话质量概述</span><span class="sxs-lookup"><span data-stu-id="6eb48-127">Video: Call Quality Overview</span></span>](https://aka.ms/teams-quality)

[<span data-ttu-id="6eb48-128">设置通话分析</span><span class="sxs-lookup"><span data-stu-id="6eb48-128">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="6eb48-129">使用通话分析来排查通话质量不良问题</span><span class="sxs-lookup"><span data-stu-id="6eb48-129">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="6eb48-130">打开并使用通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="6eb48-130">Turning on and using Call Quality Dashboard</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="6eb48-131">通话质量仪表板中可用的维度和衡量指标</span><span class="sxs-lookup"><span data-stu-id="6eb48-131">Dimensions and measures available in Call Quality Dashboard</span></span>](dimensions-and-measures-available-in-call-quality-dashboard.md)

[<span data-ttu-id="6eb48-132">通话质量仪表板中的流分类</span><span class="sxs-lookup"><span data-stu-id="6eb48-132">Stream Classification in Call Quality Dashboard</span></span>](stream-classification-in-call-quality-dashboard.md)