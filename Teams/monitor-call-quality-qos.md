---
title: 监控和提高 Microsoft 团队的通话质量
author: lolajacobsen
ms.author: lolaj
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
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
ms.openlocfilehash: 2d5db11bbd9608aebb1eb2b73ebacc9793629e44
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085930"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a><span data-ttu-id="0103e-103">监控和提高 Microsoft 团队的通话质量</span><span class="sxs-lookup"><span data-stu-id="0103e-103">Monitor and improve call quality for Microsoft Teams</span></span>

<span data-ttu-id="0103e-104">本文介绍了可用于在 Microsoft 团队中监控、解决、管理和改进通话质量的三个关键工具。</span><span class="sxs-lookup"><span data-stu-id="0103e-104">This article introduces three key tools you can use to monitor, troubleshoot, manage, and improve call quality in Microsoft Teams.</span></span> 

- <span data-ttu-id="0103e-105">**通话质量仪表板（CQD）**：分析组织范围内的趋势或问题，提高性能</span><span class="sxs-lookup"><span data-stu-id="0103e-105">**Call Quality Dashboard (CQD)**: To analyze org-wide trends or problems, drive improvements to performance</span></span>

- <span data-ttu-id="0103e-106">**调用分析**：分析单个用户的通话和会议质量</span><span class="sxs-lookup"><span data-stu-id="0103e-106">**Call analytics**: To analyze call and meeting quality for individual users</span></span>

- <span data-ttu-id="0103e-107">**服务质量（QoS）**：确定重要网络流量的优先级</span><span class="sxs-lookup"><span data-stu-id="0103e-107">**Quality of Service (QoS)**: To prioritize important network traffic</span></span>



## <a name="monitor-and-troubleshoot-call-quality"></a><span data-ttu-id="0103e-108">监控通话质量并解决问题</span><span class="sxs-lookup"><span data-stu-id="0103e-108">Monitor and troubleshoot call quality</span></span>
<span data-ttu-id="0103e-109">您将使用每用户**呼叫分析**和**通话质量仪表板**查找并解决正在进行的操作中出现的通话质量问题。</span><span class="sxs-lookup"><span data-stu-id="0103e-109">You'll use per-user **Call analytics** and **Call Quality Dashboard** to find and troubleshoot call-quality problems that come up during ongoing operation.</span></span> <span data-ttu-id="0103e-110">这可让你在网络上推动性能改进。</span><span class="sxs-lookup"><span data-stu-id="0103e-110">This lets you drive performance improvements across your network.</span></span> <span data-ttu-id="0103e-111">这两个工具均位于团队管理中心。</span><span class="sxs-lookup"><span data-stu-id="0103e-111">Both of these tools are in the Teams admin center.</span></span>

 - <span data-ttu-id="0103e-112">"**呼叫分析**" 显示与团队中每个用户的***特定呼叫和会议***相关的设备、网络和连接的详细信息。</span><span class="sxs-lookup"><span data-stu-id="0103e-112">**Call analytics** shows detailed information about the devices, networks, and connectivity related to  ***specific calls and meetings*** for each user in Teams.</span></span> <span data-ttu-id="0103e-113">团队管理员和帮助台工程师将使用此信息来解决特定呼叫中的通话质量和连接问题。</span><span class="sxs-lookup"><span data-stu-id="0103e-113">Teams admin and helpdesk agents will use this information to troubleshoot call quality and connection problems in a specific call.</span></span> <span data-ttu-id="0103e-114">若要了解详细信息，请参阅[设置呼叫分析](set-up-call-analytics.md)和[使用呼叫分析解决较差的通话质量](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="0103e-114">To learn more, read [Set up call analytics](set-up-call-analytics.md) and [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
 
 - <span data-ttu-id="0103e-115">**通话质量仪表板（CQD）** 在整个组织内为您提供通话质量的***网络视图***。</span><span class="sxs-lookup"><span data-stu-id="0103e-115">**Call Quality Dashboard (CQD)** gives you a ***network-wide view*** of call quality across your organization.</span></span> <span data-ttu-id="0103e-116">使用 CQD 信息帮助您识别并解决问题。</span><span class="sxs-lookup"><span data-stu-id="0103e-116">Use CQD information to help you identify and fix problems.</span></span> <span data-ttu-id="0103e-117">首先，[设置 CQD](turning-on-and-using-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="0103e-117">First, [Set up CQD](turning-on-and-using-call-quality-dashboard.md).</span></span> <span data-ttu-id="0103e-118">然后阅读[团队中的 "管理通话和会议质量"](quality-of-experience-review-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="0103e-118">Then read [Manage call and meeting quality in Teams](quality-of-experience-review-guide.md).</span></span>

 <span data-ttu-id="0103e-119">调用分析和 CQD 并行运行，并且可以独立使用，也可以一起使用。</span><span class="sxs-lookup"><span data-stu-id="0103e-119">Call analytics and CQD run in parallel and can be used independently or together.</span></span> <span data-ttu-id="0103e-120">例如，如果通信支持专家确定他们需要更多的帮助来解决用户的呼叫问题，他们将呼叫提升到通信支持工程师，该工程师有权访问有关呼叫的其他信息。</span><span class="sxs-lookup"><span data-stu-id="0103e-120">For example, if a communications support specialist determines that they need more help troubleshooting a user's call problem, they escalate the call to a communications support engineer, who has access to additional information about the call.</span></span> <span data-ttu-id="0103e-121">然后，通信支持工程师将向网络工程师发出警报，通知他们可能会在通话分析中注意到的与网站相关的问题。</span><span class="sxs-lookup"><span data-stu-id="0103e-121">In turn, the communications support engineer alerts a network engineer to a possible site-related issue they noticed in the call analytics.</span></span> <span data-ttu-id="0103e-122">网络工程师检查 CQD 以了解网站的总体相关问题是否可能是导致用户呼叫问题的原因。</span><span class="sxs-lookup"><span data-stu-id="0103e-122">The network engineer checks CQD to see if an overall site-related issue could be a contributing cause of the user's call problem.</span></span>


## <a name="prioritize-important-network-traffic-using-qos"></a><span data-ttu-id="0103e-123">使用 QoS 确定重要网络流量的优先级</span><span class="sxs-lookup"><span data-stu-id="0103e-123">Prioritize important network traffic using QoS</span></span>
<span data-ttu-id="0103e-124">当用户开始使用团队进行呼叫和会议时，他们可能会遇到呼叫者的语音或通话或会议。</span><span class="sxs-lookup"><span data-stu-id="0103e-124">As your users start using Teams for calls and meetings, they may experience a caller's voice breaking up or cutting in and out of a call or meeting.</span></span> <span data-ttu-id="0103e-125">共享视频可能冻结或像素化，或者完全失败。</span><span class="sxs-lookup"><span data-stu-id="0103e-125">Shared video may freeze or pixelate, or fail altogether.</span></span> <span data-ttu-id="0103e-126">这是由于表示语音和视频流量导致网络拥塞的 IP 数据包，或者根本就不在序列中。</span><span class="sxs-lookup"><span data-stu-id="0103e-126">This is due to the IP packets that represent voice and video traffic encountering network congestion and arriving out of sequence or not at all.</span></span> <span data-ttu-id="0103e-127">如果发生这种情况（或阻止其在第一个位置发生），请使用 "**服务质量（QoS）**"。</span><span class="sxs-lookup"><span data-stu-id="0103e-127">If this happens (or to prevent it from happening in the first place), use **Quality of Service (QoS)**.</span></span> 

<span data-ttu-id="0103e-128">使用 QoS，你可以为延迟敏感的网络流量（例如，语音或视频流）设置优先级，从而允许它 "在不太敏感的通信（如下载新应用，要下载的额外第二秒）" 之前 "在行中剪切"。</span><span class="sxs-lookup"><span data-stu-id="0103e-128">With QoS, you prioritize delay-sensitive network traffic (for example, voice or video streams), allowing it to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal).</span></span> <span data-ttu-id="0103e-129">QoS 使用 Windows 组策略对象和一个名为基于端口的访问控制列表的路由功能在实时流中标识和标记所有数据包，这将指示你的网络为语音、视频和屏幕共享自己的专用网络带宽。</span><span class="sxs-lookup"><span data-stu-id="0103e-129">QoS identifies and marks all packets in real-time streams using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, which instructs your network to give voice, video, and screen sharing their own dedicated network bandwidth.</span></span>

<span data-ttu-id="0103e-130">理想情况下，你将在你的内部网络上实施 QoS，同时准备好部署团队，但你可以随时执行此操作。</span><span class="sxs-lookup"><span data-stu-id="0103e-130">Ideally, you'll implement QoS on your internal network while getting ready to roll out Teams, but you can do it anytime.</span></span> <span data-ttu-id="0103e-131">如果您非常小，则可能不需要 QoS。</span><span class="sxs-lookup"><span data-stu-id="0103e-131">If you're small enough, you might not need QoS.</span></span>

<span data-ttu-id="0103e-132">准备就绪后，请阅读[Microsoft 团队中的实施服务质量（QoS）](QoS-in-Teams.md)。</span><span class="sxs-lookup"><span data-stu-id="0103e-132">When you're ready, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span>

<span data-ttu-id="0103e-133">若要使用 QoS 管理会议流量，请参阅[设置你希望如何处理团队会议的实时媒体流量](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。</span><span class="sxs-lookup"><span data-stu-id="0103e-133">To use QoS to manage meeting traffic, read [Set how you want to handle real-time media traffic for Teams meetings](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).</span></span>


## <a name="related-topics"></a><span data-ttu-id="0103e-134">相关主题</span><span class="sxs-lookup"><span data-stu-id="0103e-134">Related Topics</span></span>

[<span data-ttu-id="0103e-135">设置呼叫分析</span><span class="sxs-lookup"><span data-stu-id="0103e-135">Set up call analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="0103e-136">使用通话分析来排查通话质量不良问题</span><span class="sxs-lookup"><span data-stu-id="0103e-136">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="0103e-137">设置 CQD</span><span class="sxs-lookup"><span data-stu-id="0103e-137">Set up CQD</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="0103e-138">在团队中管理通话和会议质量</span><span class="sxs-lookup"><span data-stu-id="0103e-138">Manage call and meeting quality in Teams</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="0103e-139">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="0103e-139">Teams Troubleshooting</span></span>](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams)

