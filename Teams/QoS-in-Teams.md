---
title: 在 Microsoft Teams 中实施服务质量
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: 了解如何为 Microsoft 团队中的服务质量 (QoS) 准备组织的网络。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.qos
- ms.teamsadmincenter.meetingsettings.network.qosmarkers
- seo-marvel-apr2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 52b1d03be3e5d54260084bbf44ad6695404607c9
ms.sourcegitcommit: 0a51738879b13991986a3a872445daa8bd20533d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48766575"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a><span data-ttu-id="ce6ab-103">在 Microsoft 团队中实施服务质量 (QoS) </span><span class="sxs-lookup"><span data-stu-id="ce6ab-103">Implement Quality of Service (QoS) in Microsoft Teams</span></span>

<span data-ttu-id="ce6ab-104">Microsoft 团队中的服务质量 (QoS) 允许对网络延迟敏感的实时网络流量 (例如，语音或视频流) 在不太敏感的流量 (（如下载新应用）的情况下进行 "在行中剪切"，这种情况不是很大的交易) 。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-104">Quality of Service (QoS) in Microsoft Teams allows real-time network traffic that's sensitive to network delays (for example, voice or video streams) to "cut in line" in front of traffic that's less sensitive (like downloading a new app, where an extra second to download isn't a large deal).</span></span> <span data-ttu-id="ce6ab-105">QoS 使用 Windows 组策略对象和基于端口的访问控制列表来标识和标记实时流中的所有数据包。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-105">QoS uses Windows Group Policy Objects and Port-based Access Control Lists to identify and mark all packets in real-time streams.</span></span> <span data-ttu-id="ce6ab-106">这可帮助你的网络为语音、视频和屏幕共享提供特定的网络带宽部分的流。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-106">This helps your network to give voice, video, and screen share streams a dedicated portion of network bandwidth.</span></span>

<span data-ttu-id="ce6ab-107">如果你支持的大型用户组遇到本文所述的任何问题，则你可能需要实现 QoS。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-107">If you support a large group of users who are experiencing any of the problems described in this article, then you probably need to implement QoS.</span></span> <span data-ttu-id="ce6ab-108">用户数较少的小型企业可能不需要 QoS，但甚至应该有帮助。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-108">A small business with few users might not need QoS, but even there it should be helpful.</span></span>

<span data-ttu-id="ce6ab-109">如果没有某种形式的 QoS，您可能会在语音和视频中看到以下质量问题：</span><span class="sxs-lookup"><span data-stu-id="ce6ab-109">Without some form of QoS, you might see the following quality issues in voice and video:</span></span>

- <span data-ttu-id="ce6ab-110">抖动-媒体数据包以不同的费率收取，这可能会导致通话中缺少单词或音节</span><span class="sxs-lookup"><span data-stu-id="ce6ab-110">Jitter – media packets arriving at different rates, which can result in missing words or syllables in calls</span></span>
- <span data-ttu-id="ce6ab-111">数据包丢失-丢弃的数据包，还可能导致更低的语音质量，并且难以理解语音</span><span class="sxs-lookup"><span data-stu-id="ce6ab-111">Packet loss – packets dropped, which can also result in lower voice quality and hard to understand speech</span></span>
- <span data-ttu-id="ce6ab-112">延迟的往返时间 (RTT) -媒体数据包在到达其目标时花费很长时间，从而导致对话中两方之间出现明显延迟，并使用户相互通话</span><span class="sxs-lookup"><span data-stu-id="ce6ab-112">Delayed round-trip time (RTT) – media packets taking a long time to reach their destinations, which result in noticeable delays between two parties in a conversation and causes people to talk over each other</span></span>

<span data-ttu-id="ce6ab-113">解决这些问题的最简单的方法是在内部和 internet 上增加数据连接的大小。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-113">The least complex way to address these issues is to increase the size of the data connections, both internally and out to the internet.</span></span> <span data-ttu-id="ce6ab-114">由于这通常是成本不受影响的，因此 QoS 提供了一种更高效地管理您所拥有的资源（而不是增加带宽）的方法。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-114">Since that is often cost-prohibitive, QoS provides a way to more effectively manage the resources you have instead of adding bandwidth.</span></span> <span data-ttu-id="ce6ab-115">若要解决质量问题，我们建议你首先使用 QoS，然后仅在必要时才添加带宽。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-115">To address quality issues, we recommend that you first use QoS, then add bandwidth only where necessary.</span></span>

<span data-ttu-id="ce6ab-116">为使 QoS 有效，您必须在整个组织中应用一致的 QoS 设置。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-116">For QoS to be effective, you must apply consistent QoS settings throughout your organization.</span></span> <span data-ttu-id="ce6ab-117">无法支持 QoS 优先级的路径的任何部分可能会降低呼叫、视频和屏幕共享的质量。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-117">Any part of the path that fails to support your QoS priorities can degrade the quality of calls, video, and screen sharing.</span></span> <span data-ttu-id="ce6ab-118">这包括将设置应用到所有用户电脑或设备、网络交换机、互联网路由器以及团队服务。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-118">This includes applying settings to all user PCs or devices, network switches, routers to the internet, and the Teams service.</span></span>

<span data-ttu-id="ce6ab-119">_图1。组织的网络与 Microsoft 365 或 Office 365 服务之间的关系_</span><span class="sxs-lookup"><span data-stu-id="ce6ab-119">_Figure 1. The relationship between an organization's networks and Microsoft 365 or Office 365 services_</span></span>

<span data-ttu-id="ce6ab-120">![网络和服务之间的关系的插图](media/Qos-in-Teams-Image1.png "组织的网络和 Microsoft 365 或 Office 365 服务之间的关系：本地网络和设备与互连网络连接，后者又与 Microsoft 365 或 Office 365 云语音和音频会议服务连接。")</span><span class="sxs-lookup"><span data-stu-id="ce6ab-120">![Illustration of the relationship between networks and services](media/Qos-in-Teams-Image1.png "The relationship between an organization's networks and Microsoft 365 or Office 365 services: on-premises network and devices connect with an interconnect network, which in turn connects with Microsoft 365 or Office 365 Cloud Voice and Audio Conferencing services.")</span></span>

## <a name="qos-implementation-checklist"></a><span data-ttu-id="ce6ab-121">QoS 实施清单</span><span class="sxs-lookup"><span data-stu-id="ce6ab-121">QoS implementation checklist</span></span>

<span data-ttu-id="ce6ab-122">在高级别上，执行以下操作来实现 QoS：</span><span class="sxs-lookup"><span data-stu-id="ce6ab-122">At a high level, do the following to implement QoS:</span></span>

1. [<span data-ttu-id="ce6ab-123">请确保您的网络已准备就绪</span><span class="sxs-lookup"><span data-stu-id="ce6ab-123">Make sure your network is ready</span></span>](#make-sure-your-network-is-ready)

1. [<span data-ttu-id="ce6ab-124">选择 QoS 实现方法</span><span class="sxs-lookup"><span data-stu-id="ce6ab-124">Select a QoS implementation method</span></span>](#select-a-qos-implementation-method)

1. [<span data-ttu-id="ce6ab-125">为每种媒体类型选择初始端口范围</span><span class="sxs-lookup"><span data-stu-id="ce6ab-125">Choose initial port ranges for each media type</span></span>](#choose-initial-port-ranges-for-each-media-type)

1. <span data-ttu-id="ce6ab-126">实施 QoS 设置：</span><span class="sxs-lookup"><span data-stu-id="ce6ab-126">Implement QoS settings:</span></span>
   1. <span data-ttu-id="ce6ab-127">在使用组策略对象的客户端 (GPO) [设置客户端设备端口范围和标记](QoS-in-Teams-clients.md)</span><span class="sxs-lookup"><span data-stu-id="ce6ab-127">On clients using a Group Policy Object (GPO) to [set client device port ranges and markings](QoS-in-Teams-clients.md)</span></span>
   2. <span data-ttu-id="ce6ab-128">在路由器 (查看制造商文档) 或其他网络设备。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-128">On routers (see the manufacturer documentation) or other network devices.</span></span> <span data-ttu-id="ce6ab-129">这可能包括基于端口的访问控制列表 (Acl) 或者简单地定义 QoS 队列和 DSCP 标记，或者所有这些操作。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-129">This might include port-based Access Control Lists (ACLs) or simply defining the QoS queues and DSCP markings, or all of these.</span></span>

      > [!IMPORTANT]
      > <span data-ttu-id="ce6ab-130">我们建议使用客户端源端口和来源和目标 IP 地址 "any" 实现这些 QoS 策略。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-130">We recommend implementing these QoS policies using the client source ports and a source and destination IP address of “any.”</span></span> <span data-ttu-id="ce6ab-131">这将在内部网络上捕获传入和传出媒体流量。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-131">This will catch both incoming and outgoing media traffic on the internal network.</span></span>  

   3. [<span data-ttu-id="ce6ab-132">设置你希望如何处理团队会议的媒体流量</span><span class="sxs-lookup"><span data-stu-id="ce6ab-132">Set how you want to handle media traffic for Teams meetings</span></span>](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. <span data-ttu-id="ce6ab-133">通过分析网络上的团队通信来[验证你的 QoS 实施](#validate-your-qos-implementation)情况。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-133">[Validate your QoS implementation](#validate-your-qos-implementation) by analyzing Teams traffic on the network.</span></span>

<span data-ttu-id="ce6ab-134">准备实施 QoS 时，请牢记以下准则：</span><span class="sxs-lookup"><span data-stu-id="ce6ab-134">As you prepare to implement QoS, keep the following guidelines in mind:</span></span>

- <span data-ttu-id="ce6ab-135">最短的 Microsoft 365 路径最短</span><span class="sxs-lookup"><span data-stu-id="ce6ab-135">The shortest path to Microsoft 365 is best</span></span>
- <span data-ttu-id="ce6ab-136">关闭端口仅会导致质量下降</span><span class="sxs-lookup"><span data-stu-id="ce6ab-136">Closing ports will only lead to quality degradation</span></span>
- <span data-ttu-id="ce6ab-137">不建议在任何情况下（如代理）中的任何障碍</span><span class="sxs-lookup"><span data-stu-id="ce6ab-137">Any obstacles in between, such as proxies, aren't recommended</span></span>
- <span data-ttu-id="ce6ab-138">限制跃点的数量：</span><span class="sxs-lookup"><span data-stu-id="ce6ab-138">Limit the number of hops:</span></span>
  - <span data-ttu-id="ce6ab-139">客户端到网络边缘-3 到5个跃点</span><span class="sxs-lookup"><span data-stu-id="ce6ab-139">Client to network edge – 3 to 5 hops</span></span>
  - <span data-ttu-id="ce6ab-140">ISP 到 Microsoft network edge –3个跃点</span><span class="sxs-lookup"><span data-stu-id="ce6ab-140">ISP to Microsoft network edge – 3 hops</span></span>
  - <span data-ttu-id="ce6ab-141">Microsoft 网络边缘到最终目标-不相关</span><span class="sxs-lookup"><span data-stu-id="ce6ab-141">Microsoft network edge to final destination – irrelevant</span></span>

<span data-ttu-id="ce6ab-142">有关配置防火墙端口的信息，请转到 [Office 365 url 和 IP 范围](office-365-urls-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-142">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

## <a name="make-sure-your-network-is-ready"></a><span data-ttu-id="ce6ab-143">请确保您的网络已准备就绪</span><span class="sxs-lookup"><span data-stu-id="ce6ab-143">Make sure your network is ready</span></span>

<span data-ttu-id="ce6ab-144">如果你正在考虑 QoS 实施，你应该已确定带宽要求和其他 [网络要求](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-144">If you're considering a QoS implementation, you should already have determined your bandwidth requirements and other [network requirements](prepare-network.md).</span></span>
  
<span data-ttu-id="ce6ab-145">网络上的流量拥塞将显著影响媒体质量。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-145">Traffic congestion across a network will greatly impact media quality.</span></span> <span data-ttu-id="ce6ab-146">缺少带宽会导致性能下降和用户体验较差。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-146">A lack of bandwidth leads to performance degradation and a poor user experience.</span></span> <span data-ttu-id="ce6ab-147">当团队采纳和使用增加时，请使用 "报告"、" [每用户呼叫分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)" 和 " [呼叫质量" 仪表板 (CQD) ](turning-on-and-using-call-quality-dashboard.md) 识别问题，然后使用 QoS 和选择性带宽增加进行调整。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-147">As Teams adoption and usage grows, use reporting, [per-user call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md), and [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to identify problems and then make adjustments using QoS and selective bandwidth additions.</span></span>

### <a name="vpn-considerations"></a><span data-ttu-id="ce6ab-148">VPN 注意事项</span><span class="sxs-lookup"><span data-stu-id="ce6ab-148">VPN considerations</span></span>

<span data-ttu-id="ce6ab-149">仅当在调用方之间的所有链接上实现时，QoS 才按预期工作。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-149">QoS only works as expected when implemented on all links between callers.</span></span> <span data-ttu-id="ce6ab-150">如果在内部网络上使用 QoS，并且用户从远程位置登录，则只能在内部托管网络中设置优先级。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-150">If you use QoS on an internal network and a user signs in from a remote location, you can only prioritize within your internal, managed network.</span></span> <span data-ttu-id="ce6ab-151">虽然远程位置可以通过实现虚拟专用网络 (VPN) 来接收托管连接，但 VPN 本身会增加数据包开销并在实时流量中产生延迟。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-151">Although remote locations can receive a managed connection by implementing a virtual private network (VPN),  a VPN inherently adds packet overhead and creates delays in real-time traffic.</span></span> <span data-ttu-id="ce6ab-152">我们建议你避免通过 VPN 运行实时通信流量。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-152">We  recommend that you avoid running real-time communications traffic over a VPN.</span></span>

<span data-ttu-id="ce6ab-153">在具有跨大洲的托管链接的全球组织中，我们强烈建议使用 QoS，因为与 LAN 相比，这些链接的带宽受到限制。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-153">In a global organization with managed links that span continents, we strongly recommend QoS because bandwidth for those links is limited in comparison to the LAN.</span></span>

## <a name="introduction-to-qos-queues"></a><span data-ttu-id="ce6ab-154">QoS 队列简介</span><span class="sxs-lookup"><span data-stu-id="ce6ab-154">Introduction to QoS queues</span></span>

<span data-ttu-id="ce6ab-155">为了提供 QoS，网络设备必须能够对流量进行分类，并且必须能够将语音或视频与其他网络流量区分开。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-155">To provide QoS, network devices must have a way to classify traffic and must be able to distinguish voice or video from other network traffic.</span></span>

<span data-ttu-id="ce6ab-156">当网络流量进入路由器时，流量将放入队列中。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-156">When network traffic enters a router, the traffic is placed into a queue.</span></span> <span data-ttu-id="ce6ab-157">如果未配置 QoS 策略，则仅有一个队列，所有数据将按具有相同优先级的第一项处理。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-157">If a QoS policy isn't configured, there is only one queue, and all data is treated as first-in, first-out with the same priority.</span></span> <span data-ttu-id="ce6ab-158">这意味着语音通信 (这对延迟非常敏感，) 可能会陷入通信量不足的情况，但延迟额外的毫秒不会出现问题。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-158">That means voice traffic (which is very sensitive to delays) might get stuck behind traffic where a delay of a few extra milliseconds wouldn't be a problem.</span></span>

<span data-ttu-id="ce6ab-159">当你实现 QoS 时，你可以使用以下几个拥塞管理功能之一定义多个队列，例如 Cisco 的优先级队列和 [基于类的加权公平队列 (CBWFQ) ](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) 和拥塞避免功能，例如 [加权随机检测 (WRED) ](https://en.wikipedia.org/wiki/Weighted_random_early_detection)。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-159">When you implement QoS, you define multiple queues using one of several congestion management features, such as Cisco’s priority queuing and [Class-Based Weighted Fair Queueing (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) and congestion avoidance features, such as [weighted random early detection (WRED)](https://en.wikipedia.org/wiki/Weighted_random_early_detection).</span></span>

<span data-ttu-id="ce6ab-160">_图2。QoS 队列的示例_</span><span class="sxs-lookup"><span data-stu-id="ce6ab-160">_Figure 2. Examples of QoS queues_</span></span>

<span data-ttu-id="ce6ab-161">![QoS 队列和带宽划分的插图](media/Qos-in-Teams-Image2.png "可用带宽的总可用带宽分为多个队列：音频、视频和其他流量，这些队列已被分配不同的优先级。")</span><span class="sxs-lookup"><span data-stu-id="ce6ab-161">![Illustration of QoS queues and bandwidth division](media/Qos-in-Teams-Image2.png "Total available bandwidth is divided among multiple queues—audio, video, and other traffic—that have been assigned different priorities.")</span></span>

<span data-ttu-id="ce6ab-162">简单的类比是 QoS 在数据网络中创建虚拟的 "carpool 车道"，因此某些类型的数据从不或几乎不会遇到延迟。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-162">A simple analogy is that QoS creates virtual "carpool lanes" in your data network so some types of data never or rarely encounter a delay.</span></span> <span data-ttu-id="ce6ab-163">创建这些泳道后，您可以调整其相对大小，并更有效地管理您拥有的连接带宽，同时还可以为您的组织的用户提供业务级体验。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-163">Once you create those lanes, you can adjust their relative size and much more effectively manage the connection bandwidth you have, while still delivering business-grade experiences for your organization's users.</span></span>

## <a name="select-a-qos-implementation-method"></a><span data-ttu-id="ce6ab-164">选择 QoS 实现方法</span><span class="sxs-lookup"><span data-stu-id="ce6ab-164">Select a QoS implementation method</span></span>

<span data-ttu-id="ce6ab-165">你可以通过基于端口的标记实现 QoS，使用网络路由器上 (Acl) 访问控制列表。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-165">You could implement QoS via port-based tagging, using Access Control Lists (ACLs) on your network's routers.</span></span> <span data-ttu-id="ce6ab-166">基于端口的标记是最可靠的方法，因为它在混合的 Windows、Mac 和 Linux 环境中工作，并且最容易实现。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-166">Port-based tagging is the most reliable method because it works in mixed Windows, Mac, and Linux environments and is the easiest to implement.</span></span> <span data-ttu-id="ce6ab-167">移动客户端不提供使用 DSCP 值标记流量的机制，因此需要使用此方法。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-167">Mobile clients don't provide a mechanism to mark traffic by using DSCP values, so they'll require this method.</span></span>  

<span data-ttu-id="ce6ab-168">使用基于端口的标记，你的网络路由器将检查传入的数据包，如果该数据包使用特定的端口或端口范围接收，则它将其标识为特定媒体类型，并将其放入该类型的队列中，将预定义的 [DSCP](https://tools.ietf.org/html/rfc2474) 标记添加到 IP 数据包标头，以便其他设备可以识别其流量类型，并在其队列中授予其优先级</span><span class="sxs-lookup"><span data-stu-id="ce6ab-168">Using port-based tagging, your network's router examines an incoming packet, and if the packet arrived using a certain port or range of ports, it identifies it as a certain media type and puts it in the queue for that type, adding a predetermined [DSCP](https://tools.ietf.org/html/rfc2474) mark to the IP Packet header so other devices can recognize its traffic type and give it priority in their queue.</span></span>

<span data-ttu-id="ce6ab-169">虽然基于端口的标记可跨平台使用，但它仅将流量标记在 WAN edge 中 (客户端计算机不会一直) ，并会产生管理开销。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-169">Although port-based tagging works across platforms, it only marks traffic at the WAN edge (not all the way to the client machine) and creates management overhead.</span></span> <span data-ttu-id="ce6ab-170">有关实施此方法的说明，请参阅路由器制造商提供的文档。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-170">Refer to the documentation provided by the router manufacturer for instructions on implementing this method.</span></span>

### <a name="insert-dscp-markers"></a><span data-ttu-id="ce6ab-171">插入 DSCP 标记</span><span class="sxs-lookup"><span data-stu-id="ce6ab-171">Insert DSCP markers</span></span>

<span data-ttu-id="ce6ab-172">你还可以通过使用组策略对象来实现 QoS， (GPO) 直接在 IP 数据包标题中插入 DSCP 标记，将其识别为特定类型的流量 (例如，语音) 。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-172">You could also implement QoS by using a Group Policy Object (GPO) to direct client devices to insert a DSCP marker in IP packet headers identifying it as particular type of traffic (for example, voice).</span></span> <span data-ttu-id="ce6ab-173">路由器和其他网络设备可以配置为识别此项，并将流量放在一个单独的、优先级较高的队列中。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-173">Routers and other network devices can be configured to recognize this and put the traffic in a separate, higher-priority queue.</span></span>

<span data-ttu-id="ce6ab-174">虽然此方案完全有效，但它仅适用于加入域的 Windows 客户端。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-174">Although this scenario is entirely valid, it will only work for domain-joined Windows clients.</span></span> <span data-ttu-id="ce6ab-175">任何不是加入域的 Windows 客户端的设备都不会启用 DSCP 标记。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-175">Any device that isn't a domain-joined Windows client won't be enabled for DSCP tagging.</span></span> <span data-ttu-id="ce6ab-176">客户端（如 Mac OS）具有硬编码的标记，并且将始终标记流量。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-176">Clients such as Mac OS have hard-coded tags and will always tag traffic.</span></span>

<span data-ttu-id="ce6ab-177">在加号，通过 GPO 控制 DSCP 标记可确保所有加入域的计算机接收相同的设置，并且只有管理员可以管理它们。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-177">On the plus side, controlling the DSCP marking via GPO ensures that all domain-joined computers receive the same settings and that only an administrator can manage them.</span></span> <span data-ttu-id="ce6ab-178">可以使用 GPO 的客户端将在原始设备上进行标记，然后配置的网络设备可以通过 DSCP 代码识别实时流并为其提供相应优先级。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-178">Clients that can use GPO will be tagged on the originating device, and then configured network devices can recognize the real-time stream by the DSCP code and give it an appropriate priority.</span></span>

### <a name="best-practice"></a><span data-ttu-id="ce6ab-179">最佳做法</span><span class="sxs-lookup"><span data-stu-id="ce6ab-179">Best practice</span></span>

<span data-ttu-id="ce6ab-180">我们建议在路由器上的终结点和基于端口的 Acl 中使用 DSCP 标记组合（如有可能）。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-180">We recommend a combination of DSCP markings at the endpoint and port-based ACLs on routers, if possible.</span></span> <span data-ttu-id="ce6ab-181">使用 GPO 捕获大多数客户端，并且还使用基于端口的 DSCP 标记，可确保移动设备、Mac 和其他客户端仍可 (至少部分) 中获得 QoS 处理。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-181">Using a GPO to catch the majority of clients, and also using port-based DSCP tagging will ensure that mobile, Mac, and other clients will still get QoS treatment (at least partially).</span></span>

<span data-ttu-id="ce6ab-182">DSCP 标记可以是 likened 到邮票，用于向邮政标志指明邮政的重要程度，以及如何对其进行排序以实现快速交付。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-182">DSCP markings can be likened to postage stamps that indicate to postal workers how urgent the delivery is and how best to sort it for speedy delivery.</span></span> <span data-ttu-id="ce6ab-183">将您的网络配置为为实时媒体流提供优先级后，丢失数据包和后期数据包应该会显著降低。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-183">Once you've configured your network to give priority to real-time media streams, lost packets and late packets should diminish greatly.</span></span>

<span data-ttu-id="ce6ab-184">一旦网络中的所有设备使用相同的分类、标记和优先级，就可以通过更改分配给每个流量类型使用的队列的端口范围的大小来减少或消除延迟、丢弃的数据包和抖动。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-184">Once all devices in the network are using the same classifications, markings, and priorities, it's possible to reduce or eliminate delays, dropped packets, and jitter by changing the size of the port ranges assigned to the queues used for each traffic type.</span></span> <span data-ttu-id="ce6ab-185">从 "团队" 角度来看，最重要的配置步骤是数据包的分类和标记。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-185">From the Teams perspective, the most important configuration step is the classification and marking of packets.</span></span> <span data-ttu-id="ce6ab-186">但是，为了使端到端 QoS 成功，你还需要将应用程序的配置与基础网络配置仔细对齐。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-186">However, for end-to-end QoS to be successful, you also need to carefully align the application's configuration with the underlying network configuration.</span></span> <span data-ttu-id="ce6ab-187">当 QoS 完全实施后，持续管理是根据组织的需求和实际使用情况调整分配给每个流量类型的端口范围的问题。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-187">Once QoS is fully implemented, ongoing management is a question of adjusting the port ranges assigned to each traffic type based on your organization's needs and actual usage.</span></span>

## <a name="choose-initial-port-ranges-for-each-media-type"></a><span data-ttu-id="ce6ab-188">为每种媒体类型选择初始端口范围</span><span class="sxs-lookup"><span data-stu-id="ce6ab-188">Choose initial port ranges for each media type</span></span>

<span data-ttu-id="ce6ab-189">DSCP 值会将相应的配置的网络通知到相应配置的网络，提供数据包或流的优先级，无论是由客户还是基于 ACL 设置为网络本身分配了 DSCP 标记。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-189">The DSCP value tells a correspondingly configured network what priority to give a packet or stream, whether the DSCP mark is assigned by clients or the network itself based on ACL settings.</span></span> <span data-ttu-id="ce6ab-190">每个媒体工作负荷获取自己的唯一 DSCP 值 (其他服务可能允许工作负荷共享 DSCP 标记，团队不) 以及用于每种媒体类型的已定义和单独端口范围。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-190">Each media workload gets its own unique DSCP value (other services might allow workloads to share a DSCP marking, Teams doesn't) and a defined and separate port range used for each media type.</span></span> <span data-ttu-id="ce6ab-191">其他环境可能具有现有的 QoS 策略，这将帮助你确定网络工作负荷的优先级。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-191">Other environments might have an existing QoS strategy in place, which will help you determine the priority of network workloads.</span></span>

<span data-ttu-id="ce6ab-192">不同实时流工作负荷的端口范围的相对大小设置专用于该工作负荷的总可用带宽的比例。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-192">The relative size of the port ranges for different real-time streaming workloads sets the proportion of the total available bandwidth dedicated to that workload.</span></span> <span data-ttu-id="ce6ab-193">若要返回到我们以前的邮政编码，请执行以下操作：带有 "Air Mail" 图章的信函可能会在一个小时内进入最接近的机场，而标记为 "大宗邮件" 的小程序包可以在一天前等待一天。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-193">To return to our earlier postal analogy: a letter with an "Air Mail" stamp might get taken within an hour to the nearest airport, while a small package marked "Bulk Mail" mark can wait for a day before traveling over land on a series of trucks.</span></span>

<span data-ttu-id="ce6ab-194">_推荐的初始端口范围_</span><span class="sxs-lookup"><span data-stu-id="ce6ab-194">_Recommended initial port ranges_</span></span>

|<span data-ttu-id="ce6ab-195">媒体流量类型</span><span class="sxs-lookup"><span data-stu-id="ce6ab-195">Media traffic type</span></span>| <span data-ttu-id="ce6ab-196">客户端源端口范围</span><span class="sxs-lookup"><span data-stu-id="ce6ab-196">Client source port range</span></span> |<span data-ttu-id="ce6ab-197">协议</span><span class="sxs-lookup"><span data-stu-id="ce6ab-197">Protocol</span></span>|<span data-ttu-id="ce6ab-198">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="ce6ab-198">DSCP value</span></span>|<span data-ttu-id="ce6ab-199">DSCP 类</span><span class="sxs-lookup"><span data-stu-id="ce6ab-199">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="ce6ab-200">音频</span><span class="sxs-lookup"><span data-stu-id="ce6ab-200">Audio</span></span>| <span data-ttu-id="ce6ab-201">50,000–50,019</span><span class="sxs-lookup"><span data-stu-id="ce6ab-201">50,000–50,019</span></span>|<span data-ttu-id="ce6ab-202">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ce6ab-202">TCP/UDP</span></span>|<span data-ttu-id="ce6ab-203">46</span><span class="sxs-lookup"><span data-stu-id="ce6ab-203">46</span></span>|<span data-ttu-id="ce6ab-204">加速转发 (EF)</span><span class="sxs-lookup"><span data-stu-id="ce6ab-204">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="ce6ab-205">视频</span><span class="sxs-lookup"><span data-stu-id="ce6ab-205">Video</span></span>| <span data-ttu-id="ce6ab-206">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="ce6ab-206">50,020–50,039</span></span>|<span data-ttu-id="ce6ab-207">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ce6ab-207">TCP/UDP</span></span>|<span data-ttu-id="ce6ab-208">34</span><span class="sxs-lookup"><span data-stu-id="ce6ab-208">34</span></span>|<span data-ttu-id="ce6ab-209">保证转发 (AF41)</span><span class="sxs-lookup"><span data-stu-id="ce6ab-209">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="ce6ab-210">应用程序/屏幕共享</span><span class="sxs-lookup"><span data-stu-id="ce6ab-210">Application/Screen Sharing</span></span>| <span data-ttu-id="ce6ab-211">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="ce6ab-211">50,040–50,059</span></span>|<span data-ttu-id="ce6ab-212">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="ce6ab-212">TCP/UDP</span></span>|<span data-ttu-id="ce6ab-213">18</span><span class="sxs-lookup"><span data-stu-id="ce6ab-213">18</span></span>|<span data-ttu-id="ce6ab-214">保证转发 (AF21)</span><span class="sxs-lookup"><span data-stu-id="ce6ab-214">Assured Forwarding (AF21)</span></span>|
||||||

<span data-ttu-id="ce6ab-215">使用这些设置时，请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="ce6ab-215">Be aware of the following when you use these settings:</span></span>

- <span data-ttu-id="ce6ab-216">如果你计划在将来实施 ExpressRoute，但尚未实现 QoS，我们建议你按照指南进行操作，以便从发送方到接收方的 DSCP 值相同。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-216">If you plan to implement ExpressRoute in the future and haven't yet implemented QoS, we recommend that you follow the guidance so that DSCP values are the same from sender to receiver.</span></span>
- <span data-ttu-id="ce6ab-217">所有客户（包括移动客户端和团队设备）将使用这些端口范围，并且将受到你使用这些源端口范围实现的任何 DSCP 策略的影响。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-217">All clients, including mobile clients and Teams devices, will use these port ranges and will be affected by any DSCP policy you implement that uses these source port ranges.</span></span> <span data-ttu-id="ce6ab-218">将继续使用动态端口的客户端仅是基于浏览器的客户端 (客户端，让参与者使用其浏览器加入会议) 。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-218">The only clients that will continue to use dynamic ports are the browser-based clients (clients that let participants join meetings by using their browsers).</span></span>
- <span data-ttu-id="ce6ab-219">虽然 Mac 客户端使用相同的端口范围，但它还会对音频 (EF 使用硬编码的值，) 和视频 (AF41) 。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-219">Although the Mac client uses the same port ranges, it also uses hard-coded values for audio (EF) and video (AF41).</span></span> <span data-ttu-id="ce6ab-220">这些值不可配置。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-220">These values aren't configurable.</span></span>
- <span data-ttu-id="ce6ab-221">如果稍后需要调整端口范围以提高用户体验，则端口范围不会重叠，并且应彼此相邻。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-221">If you later need to adjust the port ranges to improve user experience, the port ranges can't overlap and should be adjacent to each other.</span></span>

## <a name="migrate-qos-to-teams"></a><span data-ttu-id="ce6ab-222">将 QoS 迁移到团队</span><span class="sxs-lookup"><span data-stu-id="ce6ab-222">Migrate QoS to Teams</span></span>

<span data-ttu-id="ce6ab-223">如果你以前已部署 Skype for business Online，包括 QoS 标记和端口范围，并且现在正在部署。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-223">If you've previously deployed Skype for Business Online, including QoS tagging and port ranges, and are now deploying.</span></span> <span data-ttu-id="ce6ab-224">团队、团队将尊重现有配置，并且将使用相同的端口范围，并将其标记为 Skype for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-224">Teams, Teams will respect the existing configuration and will use the same port ranges and tagging as the Skype for Business client.</span></span> <span data-ttu-id="ce6ab-225">在大多数情况下，不需要额外的配置。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-225">In most cases, no additional configuration will be needed.</span></span>

> [!NOTE]
> <span data-ttu-id="ce6ab-226">如果你通过组策略使用应用程序名称 QoS 标记，则必须添加 Teams.exe 作为应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-226">If you're using Application Name QoS tagging via Group Policy, you must add Teams.exe as the application name.</span></span>

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a><span data-ttu-id="ce6ab-227">使用 PowerShell 在 Windows 上的团队中实施 QoS</span><span class="sxs-lookup"><span data-stu-id="ce6ab-227">Implement QoS in Teams on Windows using PowerShell</span></span>

<span data-ttu-id="ce6ab-228">**设置音频的 QoS**</span><span class="sxs-lookup"><span data-stu-id="ce6ab-228">**Set QoS for audio**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000
-IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

<span data-ttu-id="ce6ab-229">**设置视频的 QoS**</span><span class="sxs-lookup"><span data-stu-id="ce6ab-229">**Set QoS for video**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020
-IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

<span data-ttu-id="ce6ab-230">**设置共享的 QoS**</span><span class="sxs-lookup"><span data-stu-id="ce6ab-230">**Set QoS for sharing**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040
-IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a><span data-ttu-id="ce6ab-231">管理团队管理中心中的源端口</span><span class="sxs-lookup"><span data-stu-id="ce6ab-231">Managing source ports in the Teams admin center</span></span>

<span data-ttu-id="ce6ab-232">在团队中，不同工作负荷使用的 QoS 源端口应处于主动管理状态，并根据需要进行调整。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-232">In Teams, QoS source ports used by the different workloads should be actively managed, and adjusted as necessary.</span></span> <span data-ttu-id="ce6ab-233">在 [选择每个媒体类型的初始端口范围](#choose-initial-port-ranges-for-each-media-type)中引用表，可调整端口范围，但无法配置 DSCP 标记。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-233">Referring to the table in [Choose initial port ranges for each media type](#choose-initial-port-ranges-for-each-media-type), the port ranges are adjustable, but the DSCP markings aren't configurable.</span></span> <span data-ttu-id="ce6ab-234">实现这些设置后，你可能会发现给定媒体类型需要更多或更少的端口。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-234">Once you have implemented these settings, you might find that more or fewer ports are needed for a given media type.</span></span> <span data-ttu-id="ce6ab-235">[每用户呼叫分析](use-call-analytics-to-troubleshoot-poor-call-quality.md) 和 [通话质量仪表板 (CQD) ](turning-on-and-using-call-quality-dashboard.md) 应该用于决定在团队实施后调整端口范围，以及按需定期进行更改。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-235">[Per-user call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md) and [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) should be used in making a decision to adjust port ranges after Teams has been implemented, and periodically as needs change.</span></span>

> [!NOTE]
> <span data-ttu-id="ce6ab-236">如果你已基于 Skype for business Online 的源端口范围和 DSCP 标记配置了 QoS，则同一配置将应用到团队，并且不需要进一步的客户端或网络更改，但你可能需要 [将团队中使用的区域](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) 与 skype For business Online 配置相匹配。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-236">If you've already configured QoS based on source port ranges and DSCP markings for Skype for Business Online, the same configuration will apply to Teams and no further client or network changes to the mapping will be required, though you may have to [set the ranges used in Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) to match what was configured for Skype for Business Online.</span></span>

<span data-ttu-id="ce6ab-237">如果以前已部署了本地 Skype for business 服务器，你可能需要重新检查 QoS 策略。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-237">If you’ve previously deployed Skype for Business Server on-premises, you might need to re-examine your QoS policies.</span></span> <span data-ttu-id="ce6ab-238">调整策略以匹配已验证的端口范围设置为团队提供了高质量的用户体验。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-238">Adjust the policies to match port range settings you've verified provide a quality user experience for Teams.</span></span>

## <a name="validate-your-qos-implementation"></a><span data-ttu-id="ce6ab-239">验证你的 QoS 实施</span><span class="sxs-lookup"><span data-stu-id="ce6ab-239">Validate your QoS implementation</span></span>

<span data-ttu-id="ce6ab-240">为了使 QoS 有效，由 GPO 设置的 DSCP 值需要存在于调用的两端。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-240">For QoS to be effective, the DSCP value set by the GPO needs to be present at both ends of a call.</span></span> <span data-ttu-id="ce6ab-241">通过分析由团队客户端生成的流量，可以验证当团队工作负载流量通过网络移动时，DSCP 值不会更改或去除。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-241">By analyzing the traffic generated by the Teams client, you can verify that the DSCP value isn’t changed or stripped out when the Teams workload traffic moves through the network.</span></span>

<span data-ttu-id="ce6ab-242">最好是在网络出口点处捕获流量。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-242">Preferably, you capture traffic at the network egress point.</span></span> <span data-ttu-id="ce6ab-243">可以在交换机或路由器上使用端口镜像来帮助解决此情况。</span><span class="sxs-lookup"><span data-stu-id="ce6ab-243">You can use port mirroring on a switch or router to help with this.</span></span>

## <a name="implement-qos-for-other-devices"></a><span data-ttu-id="ce6ab-244">为其他设备实现 QoS</span><span class="sxs-lookup"><span data-stu-id="ce6ab-244">Implement QoS for other devices</span></span>

<span data-ttu-id="ce6ab-245">阅读以下主题，了解有关如何实现 Intune、Surface、iOS、Android 和 Mac 的 QoS 的信息</span><span class="sxs-lookup"><span data-stu-id="ce6ab-245">Read these topics for information about implementing QoS for Intune, Surface, iOS, Android, and Mac</span></span>

- [<span data-ttu-id="ce6ab-246">Surface Hub 2 的 QoS</span><span class="sxs-lookup"><span data-stu-id="ce6ab-246">QoS for Surface Hub 2S</span></span>](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)

- [<span data-ttu-id="ce6ab-247">Surface Hub 的 QoS</span><span class="sxs-lookup"><span data-stu-id="ce6ab-247">QoS for Surface Hub</span></span>](https://docs.microsoft.com/surface-hub/surface-hub-qos)

- [<span data-ttu-id="ce6ab-248">IOS、Android 和 Mac 的 QoS</span><span class="sxs-lookup"><span data-stu-id="ce6ab-248">QoS for iOS, Android, and Mac</span></span>](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a><span data-ttu-id="ce6ab-249">相关主题</span><span class="sxs-lookup"><span data-stu-id="ce6ab-249">Related topics</span></span>

- [<span data-ttu-id="ce6ab-250">视频：网络规划</span><span class="sxs-lookup"><span data-stu-id="ce6ab-250">Video: Network Planning</span></span>](https://aka.ms/teams-networking)

- [<span data-ttu-id="ce6ab-251">为 Microsoft Teams 准备组织的网络</span><span class="sxs-lookup"><span data-stu-id="ce6ab-251">Prepare your organization's network for Microsoft Teams</span></span>](prepare-network.md)

- [<span data-ttu-id="ce6ab-252">在团队客户端中实施 QoS</span><span class="sxs-lookup"><span data-stu-id="ce6ab-252">Implement QoS in the Teams client</span></span>](QoS-in-Teams-clients.md)
