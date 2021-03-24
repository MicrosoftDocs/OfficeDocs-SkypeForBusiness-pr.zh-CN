---
title: 监视和改进 Microsoft Teams 的通话质量
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: vkorlep, siunies
description: 使用服务质量 (QoS) 设置，然后在 Microsoft Teams 中调用分析和呼叫质量仪表板。
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 62e687de154fadffd6ac95bd628fec6f9454cc51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51162678"
---
# <a name="monitor-and-improve-call-quality-for-microsoft-teams"></a><span data-ttu-id="62ad2-103">监视和改进 Microsoft Teams 的通话质量</span><span class="sxs-lookup"><span data-stu-id="62ad2-103">Monitor and improve call quality for Microsoft Teams</span></span>

<span data-ttu-id="62ad2-104">本文介绍三种关键工具，可用于监视、排查、管理和提高 Microsoft Teams 中的呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="62ad2-104">This article introduces three key tools you can use to monitor, troubleshoot, manage, and improve call quality in Microsoft Teams.</span></span> 

- <span data-ttu-id="62ad2-105">**调用质量仪表板 (CQD) ：** 要分析组织范围内的趋势或问题，请推动性能改进</span><span class="sxs-lookup"><span data-stu-id="62ad2-105">**Call Quality Dashboard (CQD)**: To analyze org-wide trends or problems, drive improvements to performance</span></span>

- <span data-ttu-id="62ad2-106">**呼叫分析**：分析单个用户的呼叫和会议质量</span><span class="sxs-lookup"><span data-stu-id="62ad2-106">**Call analytics**: To analyze call and meeting quality for individual users</span></span>

- <span data-ttu-id="62ad2-107">**QoS (服务质量) ：** 确定重要网络流量的优先级</span><span class="sxs-lookup"><span data-stu-id="62ad2-107">**Quality of Service (QoS)**: To prioritize important network traffic</span></span>



## <a name="monitor-and-troubleshoot-call-quality"></a><span data-ttu-id="62ad2-108">监视和排查呼叫质量问题</span><span class="sxs-lookup"><span data-stu-id="62ad2-108">Monitor and troubleshoot call quality</span></span>
<span data-ttu-id="62ad2-109">你将使用按用户的呼叫分析和呼叫质量 **仪表板** 来查找和排查正在进行的操作期间出现呼叫质量问题。</span><span class="sxs-lookup"><span data-stu-id="62ad2-109">You'll use per-user **Call analytics** and **Call Quality Dashboard** to find and troubleshoot call-quality problems that come up during ongoing operation.</span></span> <span data-ttu-id="62ad2-110">这样，可以在整个网络中推动性能改进。</span><span class="sxs-lookup"><span data-stu-id="62ad2-110">This lets you drive performance improvements across your network.</span></span> <span data-ttu-id="62ad2-111">这两个工具都位于 Teams 管理中心。</span><span class="sxs-lookup"><span data-stu-id="62ad2-111">Both of these tools are in the Teams admin center.</span></span>

 - <span data-ttu-id="62ad2-112">**通话分析** 显示与 Teams 中每个用户的特定通话和会议相关的设备、网络和 \*\*\*\* 连接的详细信息。</span><span class="sxs-lookup"><span data-stu-id="62ad2-112">**Call analytics** shows detailed information about the devices, networks, and connectivity related to  **_specific calls and meetings_** for each user in Teams.</span></span> <span data-ttu-id="62ad2-113">Teams 管理员和技术支持代理将使用此信息来排查特定呼叫中的呼叫质量和连接问题。</span><span class="sxs-lookup"><span data-stu-id="62ad2-113">Teams admin and helpdesk agents will use this information to troubleshoot call quality and connection problems in a specific call.</span></span> <span data-ttu-id="62ad2-114">有关详细信息，请阅读[设置呼叫分析和](set-up-call-analytics.md)[使用呼叫分析来排查通话质量不佳的问题](use-call-analytics-to-troubleshoot-poor-call-quality.md)。</span><span class="sxs-lookup"><span data-stu-id="62ad2-114">To learn more, read [Set up call analytics](set-up-call-analytics.md) and [Use Call Analytics to troubleshoot poor call quality](use-call-analytics-to-troubleshoot-poor-call-quality.md).</span></span>
 
 - <span data-ttu-id="62ad2-115">**使用 CQD** (") "呼叫质量仪表板"可让你 \*\*\*\* 在整个网络中查看呼叫质量。</span><span class="sxs-lookup"><span data-stu-id="62ad2-115">**Call Quality Dashboard (CQD)** gives you a **_network-wide view_** of call quality across your organization.</span></span> <span data-ttu-id="62ad2-116">使用 CQD 信息来帮助识别和修复问题。</span><span class="sxs-lookup"><span data-stu-id="62ad2-116">Use CQD information to help you identify and fix problems.</span></span> <span data-ttu-id="62ad2-117">首先 [，设置 CQD](turning-on-and-using-call-quality-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="62ad2-117">First, [Set up CQD](turning-on-and-using-call-quality-dashboard.md).</span></span> <span data-ttu-id="62ad2-118">然后阅读 [在 Teams 中管理呼叫和会议质量](quality-of-experience-review-guide.md)。</span><span class="sxs-lookup"><span data-stu-id="62ad2-118">Then read [Manage call and meeting quality in Teams](quality-of-experience-review-guide.md).</span></span>

 <span data-ttu-id="62ad2-119">调用分析和 CQD 并行运行，可以独立或一起使用。</span><span class="sxs-lookup"><span data-stu-id="62ad2-119">Call analytics and CQD run in parallel and can be used independently or together.</span></span> <span data-ttu-id="62ad2-120">例如，如果通信支持专家确定他们需要更多帮助来排查用户的呼叫问题，他们会将呼叫上报给通信支持工程师，该工程师有权访问有关呼叫的其他信息。</span><span class="sxs-lookup"><span data-stu-id="62ad2-120">For example, if a communications support specialist determines that they need more help troubleshooting a user's call problem, they escalate the call to a communications support engineer, who has access to additional information about the call.</span></span> <span data-ttu-id="62ad2-121">反过来，通信支持工程师会向网络工程师发出警报，提醒他们注意呼叫分析中可能发现的网站相关问题。</span><span class="sxs-lookup"><span data-stu-id="62ad2-121">In turn, the communications support engineer alerts a network engineer to a possible site-related issue they noticed in the call analytics.</span></span> <span data-ttu-id="62ad2-122">网络工程师会检查 CQD，以查看与网站相关的整体问题是否可能是用户呼叫问题的促成原因。</span><span class="sxs-lookup"><span data-stu-id="62ad2-122">The network engineer checks CQD to see if an overall site-related issue could be a contributing cause of the user's call problem.</span></span>


## <a name="prioritize-important-network-traffic-using-qos"></a><span data-ttu-id="62ad2-123">使用 QoS 确定重要网络流量的优先级</span><span class="sxs-lookup"><span data-stu-id="62ad2-123">Prioritize important network traffic using QoS</span></span>
<span data-ttu-id="62ad2-124">当用户开始使用 Teams 进行呼叫和会议时，他们可能会遇到呼叫者的声音中断或呼叫或会议中断。</span><span class="sxs-lookup"><span data-stu-id="62ad2-124">As your users start using Teams for calls and meetings, they may experience a caller's voice breaking up or cutting in and out of a call or meeting.</span></span> <span data-ttu-id="62ad2-125">共享视频可能会冻结或像素化，或完全失败。</span><span class="sxs-lookup"><span data-stu-id="62ad2-125">Shared video may freeze or pixelate, or fail altogether.</span></span> <span data-ttu-id="62ad2-126">这是由于表示语音和视频流量遇到网络拥塞并按顺序到达或者完全无法到达的 IP 数据包造成的。</span><span class="sxs-lookup"><span data-stu-id="62ad2-126">This is due to the IP packets that represent voice and video traffic encountering network congestion and arriving out of sequence or not at all.</span></span> <span data-ttu-id="62ad2-127">如果发生这种情况 (或防止它最初) ，请使用服务质量 (**QoS) 。**</span><span class="sxs-lookup"><span data-stu-id="62ad2-127">If this happens (or to prevent it from happening in the first place), use **Quality of Service (QoS)**.</span></span> 

<span data-ttu-id="62ad2-128">使用 QoS，可以优先处理延迟敏感的网络流量 (例如语音或视频流) ，从而允许它在不太敏感的流量前面"切线" (例如下载新应用，其中额外下载秒数不是一个大问题) 。</span><span class="sxs-lookup"><span data-stu-id="62ad2-128">With QoS, you prioritize delay-sensitive network traffic (for example, voice or video streams), allowing it to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal).</span></span> <span data-ttu-id="62ad2-129">QoS 使用 Windows 组策略对象和一种称为基于端口的访问控制列表的路由功能来识别和标记实时流中的所有数据包，该功能指示网络提供语音、视频和屏幕共享其自己的专用网络带宽。</span><span class="sxs-lookup"><span data-stu-id="62ad2-129">QoS identifies and marks all packets in real-time streams using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, which instructs your network to give voice, video, and screen sharing their own dedicated network bandwidth.</span></span>

<span data-ttu-id="62ad2-130">理想情况下，你将在准备推出 Teams 的同时在内部网络上实现 QoS，但你可以随时实现。</span><span class="sxs-lookup"><span data-stu-id="62ad2-130">Ideally, you'll implement QoS on your internal network while getting ready to roll out Teams, but you can do it anytime.</span></span> <span data-ttu-id="62ad2-131">如果足够小，可能不需要 QoS。</span><span class="sxs-lookup"><span data-stu-id="62ad2-131">If you're small enough, you might not need QoS.</span></span>

<span data-ttu-id="62ad2-132">准备就绪后，请阅读在[Microsoft Teams (QoS) 服务质量。](QoS-in-Teams.md)</span><span class="sxs-lookup"><span data-stu-id="62ad2-132">When you're ready, read [Implement Quality of Service (QoS) in Microsoft Teams](QoS-in-Teams.md).</span></span>

<span data-ttu-id="62ad2-133">若要使用 QoS 管理会议流量，请阅读设置如何处理 Teams 会议 [实时媒体流量](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。</span><span class="sxs-lookup"><span data-stu-id="62ad2-133">To use QoS to manage meeting traffic, read [Set how you want to handle real-time media traffic for Teams meetings](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).</span></span>


## <a name="related-topics"></a><span data-ttu-id="62ad2-134">相关主题</span><span class="sxs-lookup"><span data-stu-id="62ad2-134">Related Topics</span></span>

[<span data-ttu-id="62ad2-135">设置呼叫分析</span><span class="sxs-lookup"><span data-stu-id="62ad2-135">Set up call analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="62ad2-136">使用通话分析来排查通话质量不良问题</span><span class="sxs-lookup"><span data-stu-id="62ad2-136">Use Call Analytics to troubleshoot poor call quality</span></span>](use-call-analytics-to-troubleshoot-poor-call-quality.md)

[<span data-ttu-id="62ad2-137">设置 CQD</span><span class="sxs-lookup"><span data-stu-id="62ad2-137">Set up CQD</span></span>](turning-on-and-using-call-quality-dashboard.md)

[<span data-ttu-id="62ad2-138">在 Teams 中管理呼叫和会议质量</span><span class="sxs-lookup"><span data-stu-id="62ad2-138">Manage call and meeting quality in Teams</span></span>](quality-of-experience-review-guide.md)

[<span data-ttu-id="62ad2-139">Teams 疑难解答</span><span class="sxs-lookup"><span data-stu-id="62ad2-139">Teams Troubleshooting</span></span>](/MicrosoftTeams/troubleshoot/teams)