---
title: 在 Microsoft Teams 中实施服务质量
author: LolaJacobsen
ms.author: lolaj
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: 了解如何为 Microsoft 团队中的服务质量（QoS）准备组织的网络。
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
ms.openlocfilehash: ef2fca810a7125c4150ff4de2c3eea8fd7970d2e
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085278"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a><span data-ttu-id="0033f-103">在 Microsoft 团队中实施服务质量（QoS）</span><span class="sxs-lookup"><span data-stu-id="0033f-103">Implement Quality of Service (QoS) in Microsoft Teams</span></span>

<span data-ttu-id="0033f-104">Microsoft 团队中的服务质量（QoS）是一种使实时网络流量对网络延迟（例如，语音或视频流）敏感的方式，以便在不太敏感的通信（如下载新应用，要下载的额外第二秒）之前 "在行中剪切"。</span><span class="sxs-lookup"><span data-stu-id="0033f-104">Quality of Service (QoS) in Microsoft Teams is a way to allow real-time network traffic that is sensitive to network delays (for example, voice or video streams) to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal).</span></span> <span data-ttu-id="0033f-105">QoS 在实时流中标识和标记所有数据包（使用 Windows 组策略对象和名为基于端口的访问控制列表的路由功能，有关这些列表的详细信息），然后可帮助你的网络提供语音、视频和屏幕共享流，以流出专用的网络带宽部分。</span><span class="sxs-lookup"><span data-stu-id="0033f-105">QoS identifies and marks all packets in real-time streams (using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, more about those is below) which then helps your network to give voice, video, and screen share streams a dedicated portion of network bandwidth.</span></span>

<span data-ttu-id="0033f-106">如果你支持一组大型用户，并且遇到下面所述的任何问题，则可能需要实现 QoS。</span><span class="sxs-lookup"><span data-stu-id="0033f-106">If you're supporting a large group of users and they're experiencing any of the problems described below, you probably need to implement QoS.</span></span> <span data-ttu-id="0033f-107">用户数较少的小型企业可能不需要 QoS，但甚至应该有帮助。</span><span class="sxs-lookup"><span data-stu-id="0033f-107">A small business with few users may not need QoS, but even there it should be helpful.</span></span>

<span data-ttu-id="0033f-108">如果没有某种形式的 QoS，您可能会在语音和视频中看到以下质量问题：</span><span class="sxs-lookup"><span data-stu-id="0033f-108">Without some form of QoS, you might see the following quality issues in voice and video:</span></span>

- <span data-ttu-id="0033f-109">抖动-媒体数据包以不同的费率收取，这可能会导致通话中缺少单词或音节</span><span class="sxs-lookup"><span data-stu-id="0033f-109">Jitter – media packets arriving at different rates, which can result in missing words or syllables in calls</span></span>
- <span data-ttu-id="0033f-110">数据包丢失-丢弃的数据包，还可能导致更低的语音质量，并且难以理解语音</span><span class="sxs-lookup"><span data-stu-id="0033f-110">Packet loss – packets dropped, which can also result in lower voice quality and hard to understand speech</span></span>
- <span data-ttu-id="0033f-111">延迟的往返时间（RTT）-媒体数据包在到达其目标时花费很长时间，从而导致对话中两方之间出现明显延迟，从而导致用户相互通话</span><span class="sxs-lookup"><span data-stu-id="0033f-111">Delayed round trip time (RTT) – media packets taking a long time to reach their destinations, which results in noticeable delays between two parties in a conversation, causing people to talk over each other</span></span>

<span data-ttu-id="0033f-112">解决这些问题的最简单的方法是在内部和 internet 上增加数据连接的大小。</span><span class="sxs-lookup"><span data-stu-id="0033f-112">The least complex way to address these issues is to increase the size of the data connections, both internally and out to the internet.</span></span> <span data-ttu-id="0033f-113">由于这通常是成本不受影响的，因此 QoS 提供了一种更高效地管理您所拥有的资源（而不是增加带宽）的方法。</span><span class="sxs-lookup"><span data-stu-id="0033f-113">Since that is often cost-prohibitive, QoS provides a way to more effectively manage the resources you have instead of adding bandwidth.</span></span> <span data-ttu-id="0033f-114">若要解决质量问题，我们建议你首先使用 QoS，然后仅在必要时才添加带宽。</span><span class="sxs-lookup"><span data-stu-id="0033f-114">To address quality issues, we recommend that you first use QoS, then add bandwidth only where necessary.</span></span>

<span data-ttu-id="0033f-115">为了使 QoS 有效，你将在整个组织中应用一致的 QoS 设置，因为无法支持 QoS 优先级的路径的任何部分可能会降低呼叫、视频和屏幕共享的质量。</span><span class="sxs-lookup"><span data-stu-id="0033f-115">For QoS to be effective, you'll apply consistent QoS settings throughout your organization, because any part of the path that fails to support your QoS priorities can degrade the quality of calls, video, and screen sharing.</span></span> <span data-ttu-id="0033f-116">这包括将设置应用到所有用户电脑或设备、网络交换机、互联网路由器以及团队服务。</span><span class="sxs-lookup"><span data-stu-id="0033f-116">This includes applying settings to all user PCs or devices, network switches, routers to the internet, and the Teams service.</span></span>

<span data-ttu-id="0033f-117">_图1。组织的网络与 Microsoft 365 或 Office 365 服务之间的关系_</span><span class="sxs-lookup"><span data-stu-id="0033f-117">_Figure 1. The relationship between an organization's networks and Microsoft 365 or Office 365 services_</span></span>

<span data-ttu-id="0033f-118">![网络和服务之间的关系的插图](media/Qos-in-Teams-Image1.png "组织的网络和 Microsoft 365 或 Office 365 服务之间的关系：本地网络和设备与互连网络连接，后者又与 Microsoft 365 或 Office 365 云语音和音频会议服务连接。")</span><span class="sxs-lookup"><span data-stu-id="0033f-118">![Illustration of the relationship between networks and services](media/Qos-in-Teams-Image1.png "The relationship between an organization's networks and Microsoft 365 or Office 365 services: on-premises network and devices connect with an interconnect network, which in turn connects with Microsoft 365 or Office 365 Cloud Voice and Audio Conferencing services.")</span></span>

## <a name="qos-implementation-checklist"></a><span data-ttu-id="0033f-119">QoS 实施清单</span><span class="sxs-lookup"><span data-stu-id="0033f-119">QoS implementation checklist</span></span>

<span data-ttu-id="0033f-120">在高级别上，执行以下操作来实现 QoS：</span><span class="sxs-lookup"><span data-stu-id="0033f-120">At a high level, do the following to implement QoS:</span></span>

1. [<span data-ttu-id="0033f-121">请确保您的网络已准备就绪</span><span class="sxs-lookup"><span data-stu-id="0033f-121">Make sure your network is ready</span></span>](#make-sure-your-network-is-ready)

1. [<span data-ttu-id="0033f-122">选择 QoS 实现方法</span><span class="sxs-lookup"><span data-stu-id="0033f-122">Select a QoS implementation method</span></span>](#select-a-qos-implementation-method)

1. [<span data-ttu-id="0033f-123">为每种媒体类型选择初始端口范围</span><span class="sxs-lookup"><span data-stu-id="0033f-123">Choose initial port ranges for each media type</span></span>](#choose-initial-port-ranges-for-each-media-type)

1. <span data-ttu-id="0033f-124">实施 QoS 设置：</span><span class="sxs-lookup"><span data-stu-id="0033f-124">Implement QoS settings:</span></span>
   1. <span data-ttu-id="0033f-125">在使用 GPO[设置客户端设备端口范围和标记](QoS-in-Teams-clients.md)的客户端上</span><span class="sxs-lookup"><span data-stu-id="0033f-125">On clients using a GPO to [set client device port ranges and markings](QoS-in-Teams-clients.md)</span></span>
   2. <span data-ttu-id="0033f-126">在路由器上（请参阅制造商文档）或其他网络设备。</span><span class="sxs-lookup"><span data-stu-id="0033f-126">On routers (see the manufacturer documentation) or other network devices.</span></span> <span data-ttu-id="0033f-127">这可能包括基于端口的 Acl，或者仅定义 QoS 队列和 DSCP 标记，或者所有这些操作。</span><span class="sxs-lookup"><span data-stu-id="0033f-127">This may include port-based ACLs or simply defining the QoS queues and DSCP markings, or all of these.</span></span>

      > [!IMPORTANT]
      > <span data-ttu-id="0033f-128">我们建议使用客户端源端口和来源和目标 IP 地址 "any" 实现这些 QoS 策略。</span><span class="sxs-lookup"><span data-stu-id="0033f-128">We recommend implementing these QoS policies using the client source ports and a source and destination IP address of “any.”</span></span> <span data-ttu-id="0033f-129">这将在内部网络上捕获传入和传出媒体流量。</span><span class="sxs-lookup"><span data-stu-id="0033f-129">This will catch both incoming and outgoing media traffic on the internal network.</span></span>  

   3. [<span data-ttu-id="0033f-130">设置你希望如何处理团队会议的媒体流量</span><span class="sxs-lookup"><span data-stu-id="0033f-130">Set how you want to handle media traffic for Teams meetings</span></span>](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

5. <span data-ttu-id="0033f-131">通过分析网络上的团队通信来[验证你的 QoS 实施](#validate-your-qos-implementation)情况。</span><span class="sxs-lookup"><span data-stu-id="0033f-131">[Validate your QoS implementation](#validate-your-qos-implementation) by analyzing Teams traffic on the network.</span></span>

<span data-ttu-id="0033f-132">准备实施 QoS 时，请牢记以下准则：</span><span class="sxs-lookup"><span data-stu-id="0033f-132">As you prepare to implement QoS, keep the following guidelines in mind:</span></span>

- <span data-ttu-id="0033f-133">最短的 Microsoft 365 路径最短</span><span class="sxs-lookup"><span data-stu-id="0033f-133">The shortest path to Microsoft 365 is best</span></span>
- <span data-ttu-id="0033f-134">关闭端口仅会导致质量下降</span><span class="sxs-lookup"><span data-stu-id="0033f-134">Closing ports will only lead to quality degradation</span></span>
- <span data-ttu-id="0033f-135">不建议在任何情况下（如代理）中的任何障碍</span><span class="sxs-lookup"><span data-stu-id="0033f-135">Any obstacles in between, such as proxies, aren't recommended</span></span>
- <span data-ttu-id="0033f-136">限制跃点的数量：</span><span class="sxs-lookup"><span data-stu-id="0033f-136">Limit the number of hops:</span></span>
  - <span data-ttu-id="0033f-137">客户端到网络边缘-3 到5个跃点</span><span class="sxs-lookup"><span data-stu-id="0033f-137">Client to network edge – 3 to 5 hops</span></span>
  - <span data-ttu-id="0033f-138">ISP 到 Microsoft network edge –3个跃点</span><span class="sxs-lookup"><span data-stu-id="0033f-138">ISP to Microsoft network edge – 3 hops</span></span>
  - <span data-ttu-id="0033f-139">Microsoft 网络边缘到最终目标-不相关</span><span class="sxs-lookup"><span data-stu-id="0033f-139">Microsoft network edge to final destination – irrelevant</span></span>

<span data-ttu-id="0033f-140">有关配置防火墙端口的信息，请转到[Office 365 url 和 IP 范围](office-365-urls-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="0033f-140">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>


## <a name="make-sure-your-network-is-ready"></a><span data-ttu-id="0033f-141">请确保您的网络已准备就绪</span><span class="sxs-lookup"><span data-stu-id="0033f-141">Make sure your network is ready</span></span>

<span data-ttu-id="0033f-142">如果你正在考虑 QoS 实施，你应该已确定带宽要求和其他[网络要求](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="0033f-142">If you're considering a QoS implementation, you should already have determined your bandwidth requirements and other [network requirements](prepare-network.md).</span></span> 
  
<span data-ttu-id="0033f-143">网络上的流量拥塞将显著影响媒体质量。</span><span class="sxs-lookup"><span data-stu-id="0033f-143">Traffic congestion across a network will greatly impact media quality.</span></span> <span data-ttu-id="0033f-144">缺少带宽会导致性能下降和用户体验较差。</span><span class="sxs-lookup"><span data-stu-id="0033f-144">A lack of bandwidth leads to performance degradation and a poor user experience.</span></span> <span data-ttu-id="0033f-145">当团队采纳和使用增加时，请使用 "报告"、"[每用户呼叫分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)" 和 "[呼叫质量" 仪表板（CQD）](turning-on-and-using-call-quality-dashboard.md)来识别问题，然后使用 QoS 和选择性带宽增加进行调整。</span><span class="sxs-lookup"><span data-stu-id="0033f-145">As Teams adoption and usage grows, use reporting, [per-user call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md), and [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to identify problems and then make adjustments using QoS and selective bandwidth additions.</span></span>

### <a name="vpn-considerations"></a><span data-ttu-id="0033f-146">VPN 注意事项</span><span class="sxs-lookup"><span data-stu-id="0033f-146">VPN considerations</span></span>

<span data-ttu-id="0033f-147">仅当在调用方之间的所有链接上实现时，QoS 才按预期工作。</span><span class="sxs-lookup"><span data-stu-id="0033f-147">QoS only works as expected when implemented on all links between callers.</span></span> <span data-ttu-id="0033f-148">如果在内部网络上使用 QoS，并且用户从远程位置登录，则只能在内部托管网络中设置优先级。</span><span class="sxs-lookup"><span data-stu-id="0033f-148">If you use QoS on an internal network and a user signs in from a remote location, you can only prioritize within your internal, managed network.</span></span> <span data-ttu-id="0033f-149">虽然远程位置可以通过实施虚拟专用网络（VPN）接收托管连接，但 VPN 本身会增加数据包开销并在实时流量中产生延迟。</span><span class="sxs-lookup"><span data-stu-id="0033f-149">Although remote locations can receive a managed connection by implementing a virtual private network (VPN),  a VPN inherently adds packet overhead and creates delays in real-time traffic.</span></span> <span data-ttu-id="0033f-150">我们建议你避免通过 VPN 运行实时通信流量。</span><span class="sxs-lookup"><span data-stu-id="0033f-150">We  recommend that you avoid running real-time communications traffic over a VPN.</span></span>

<span data-ttu-id="0033f-151">在具有跨大洲的托管链接的全球组织中，我们强烈建议使用 QoS，因为与 LAN 相比，这些链接的带宽受到限制。</span><span class="sxs-lookup"><span data-stu-id="0033f-151">In a global organization with managed links that span continents, we strongly recommend QoS because bandwidth for those links is limited in comparison to the LAN.</span></span>

## <a name="introduction-to-qos-queues"></a><span data-ttu-id="0033f-152">QoS 队列简介</span><span class="sxs-lookup"><span data-stu-id="0033f-152">Introduction to QoS queues</span></span>

<span data-ttu-id="0033f-153">为了提供 QoS，网络设备必须能够对流量进行分类，并且必须能够将语音或视频与其他网络流量区分开。</span><span class="sxs-lookup"><span data-stu-id="0033f-153">To provide QoS, network devices must have a way to classify traffic and must be able to distinguish voice or video from other network traffic.</span></span>

<span data-ttu-id="0033f-154">当网络流量进入路由器时，流量将放入队列中。</span><span class="sxs-lookup"><span data-stu-id="0033f-154">When network traffic enters a router, the traffic is placed into a queue.</span></span> <span data-ttu-id="0033f-155">如果未配置 QoS 策略，则仅有一个队列，所有数据将按具有相同优先级的第一项处理。</span><span class="sxs-lookup"><span data-stu-id="0033f-155">If a QoS policy isn't configured, there is only one queue, and all data is treated as first-in, first-out with the same priority.</span></span> <span data-ttu-id="0033f-156">这意味着语音流量（对延迟非常敏感）可能会陷入通信量不足的情况下，延迟几个额外的毫秒不会出现问题。</span><span class="sxs-lookup"><span data-stu-id="0033f-156">That means voice traffic (which is very sensitive to delays) might get stuck behind traffic where a delay of a few extra milliseconds wouldn't be a problem.</span></span>

<span data-ttu-id="0033f-157">当你实现 QoS 时，你可以使用以下几个拥塞管理功能之一定义多个队列（如 Cisco 的优先级队列和[基于类的加权公平队列（CBWFQ）](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641)）和拥塞避免功能（如[加权随机检测（WRED）](https://en.wikipedia.org/wiki/Weighted_random_early_detection)）。</span><span class="sxs-lookup"><span data-stu-id="0033f-157">When you implement QoS, you define multiple queues using one of several congestion management features (such as Cisco’s priority queuing and [Class-Based Weighted Fair Queueing (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641)) and congestion avoidance features (such as [weighted random early detection (WRED)](https://en.wikipedia.org/wiki/Weighted_random_early_detection)).</span></span>

<span data-ttu-id="0033f-158">_图2。QoS 队列的示例_</span><span class="sxs-lookup"><span data-stu-id="0033f-158">_Figure 2. Examples of QoS queues_</span></span>

<span data-ttu-id="0033f-159">![QoS 队列和带宽划分的插图](media/Qos-in-Teams-Image2.png "可用带宽的总可用带宽分为多个队列：音频、视频和其他流量，这些队列已被分配不同的优先级。")</span><span class="sxs-lookup"><span data-stu-id="0033f-159">![Illustration of QoS queues and bandwidth division](media/Qos-in-Teams-Image2.png "Total available bandwidth is divided among multiple queues—audio, video, and other traffic—that have been assigned different priorities.")</span></span>

<span data-ttu-id="0033f-160">简单的类比是 QoS 在数据网络中创建虚拟的 "carpool 车道"，因此某些类型的数据从不或几乎不会遇到延迟。</span><span class="sxs-lookup"><span data-stu-id="0033f-160">A simple analogy is that QoS creates virtual "carpool lanes" in your data network so some types of data never or rarely encounter a delay.</span></span> <span data-ttu-id="0033f-161">创建这些泳道后，您可以调整其相对大小，并更有效地管理您拥有的连接带宽，同时还可以为您的组织的用户提供业务级体验。</span><span class="sxs-lookup"><span data-stu-id="0033f-161">Once you create those lanes, you can adjust their relative size and much more effectively manage the connection bandwidth you have, while still delivering business-grade experiences for your organization's users.</span></span>

## <a name="select-a-qos-implementation-method"></a><span data-ttu-id="0033f-162">选择 QoS 实现方法</span><span class="sxs-lookup"><span data-stu-id="0033f-162">Select a QoS implementation method</span></span>

<span data-ttu-id="0033f-163">你可以使用网络路由器上的访问控制列表（Acl），通过基于端口的标记实现 QoS。</span><span class="sxs-lookup"><span data-stu-id="0033f-163">You could implement QoS via port-based tagging, using Access Control Lists (ACLs) on your network's routers.</span></span> <span data-ttu-id="0033f-164">基于端口的标记是最可靠的方法，因为它在混合的 Windows、Mac 和 Linux 环境中工作，并且最容易实现。</span><span class="sxs-lookup"><span data-stu-id="0033f-164">Port-based tagging is the most reliable method because it works in mixed Windows, Mac, and Linux environments and is the easiest to implement.</span></span> <span data-ttu-id="0033f-165">移动客户端不提供使用 DSCP 值标记流量的机制，因此它们将需要此方法。</span><span class="sxs-lookup"><span data-stu-id="0033f-165">Mobile clients don't provide a mechanism to mark traffic by using DSCP values, so they will require this method.</span></span>  

<span data-ttu-id="0033f-166">使用基于端口的标记，你的网络路由器将检查传入的数据包，如果该数据包使用特定的端口或端口范围接收，则它将其标识为特定媒体类型，并将其放入该类型的队列中，将预定义的[DSCP](https://tools.ietf.org/html/rfc2474)标记添加到 IP 数据包标头，以便其他设备可以识别其流量类型，并在其队列中授予其优先级</span><span class="sxs-lookup"><span data-stu-id="0033f-166">Using port-based tagging, your network's router examines an incoming packet, and if the packet arrived using a certain port or range of ports, it identifies it as a certain media type and puts it in the queue for that type, adding a predetermined [DSCP](https://tools.ietf.org/html/rfc2474) mark to the IP Packet header so other devices can recognize its traffic type and give it priority in their queue.</span></span>

<span data-ttu-id="0033f-167">尽管这在多个平台上有效，但它仅将流量标记为 WAN edge （而不是客户端计算机的任何方式），并创建管理开销。</span><span class="sxs-lookup"><span data-stu-id="0033f-167">Although this works across platforms, it only marks traffic at the WAN edge (not all the way to the client machine) and creates management overhead.</span></span> <span data-ttu-id="0033f-168">您应该参考路由器制造商提供的文档，获取有关实施此方法的说明。</span><span class="sxs-lookup"><span data-stu-id="0033f-168">You should refer to the documentation provided by the router manufacturer for instructions on implementing this method.</span></span>

### <a name="insert-dscp-markers"></a><span data-ttu-id="0033f-169">插入 DSCP 标记</span><span class="sxs-lookup"><span data-stu-id="0033f-169">Insert DSCP markers</span></span>

<span data-ttu-id="0033f-170">你还可以通过使用组策略对象（GPO）直接在 IP 数据包标题中插入 DSCP 标记以将 DSCP 标记插入标识为特定类型的流量（例如，语音）来实现 QoS。</span><span class="sxs-lookup"><span data-stu-id="0033f-170">You could also implement QoS by using a Group Policy Object (GPO) to direct client devices to insert a DSCP marker in IP packet headers identifying it as particular type of traffic (for example, voice).</span></span> <span data-ttu-id="0033f-171">路由器和其他网络设备可以配置为识别此项，并将流量放在一个单独的、优先级较高的队列中。</span><span class="sxs-lookup"><span data-stu-id="0033f-171">Routers and other network devices can be configured to recognize this and put the traffic in a separate, higher-priority queue.</span></span>

<span data-ttu-id="0033f-172">虽然此方案完全有效，但它仅适用于加入域的 Windows 客户端。</span><span class="sxs-lookup"><span data-stu-id="0033f-172">Although this scenario is entirely valid, it will only work for domain-joined Windows clients.</span></span> <span data-ttu-id="0033f-173">任何不是加入域的 Windows 客户端的设备都不会启用 DSCP 标记。</span><span class="sxs-lookup"><span data-stu-id="0033f-173">Any device that isn't a domain-joined Windows client won't be enabled for DSCP tagging.</span></span> <span data-ttu-id="0033f-174">客户端（如 Mac OS）具有硬编码的标记，并且将始终标记流量。</span><span class="sxs-lookup"><span data-stu-id="0033f-174">Clients such as Mac OS have hard-coded tags and will always tag traffic.</span></span>

<span data-ttu-id="0033f-175">在加号，通过 GPO 控制 DSCP 标记可确保所有加入域的计算机接收相同的设置，并且只有管理员可以管理它们。</span><span class="sxs-lookup"><span data-stu-id="0033f-175">On the plus side, controlling the DSCP marking via GPO ensures that all domain-joined computers receive the same settings and that only an administrator can manage them.</span></span> <span data-ttu-id="0033f-176">可以使用 GPO 的客户端将在原始设备上进行标记，然后配置的网络设备可以通过 DSCP 代码识别实时流并为其提供相应优先级。</span><span class="sxs-lookup"><span data-stu-id="0033f-176">Clients that can use GPO will be tagged on the originating device, and then configured network devices can recognize the real-time stream by the DSCP code and give it an appropriate priority.</span></span>

### <a name="best-practice"></a><span data-ttu-id="0033f-177">最佳做法</span><span class="sxs-lookup"><span data-stu-id="0033f-177">Best practice</span></span>

<span data-ttu-id="0033f-178">我们建议在路由器上的终结点和基于端口的 Acl 中使用 DSCP 标记组合（如有可能）。</span><span class="sxs-lookup"><span data-stu-id="0033f-178">We recommend a combination of DSCP markings at the endpoint and port-based ACLs on routers, if possible.</span></span> <span data-ttu-id="0033f-179">使用组策略对象捕获大多数客户端，同时使用基于端口的 DSCP 标记，可确保移动、Mac 和其他客户端仍会获得 QoS 处理（至少部分）。</span><span class="sxs-lookup"><span data-stu-id="0033f-179">Using a Group Policy object to catch the majority of clients, and also using port-based DSCP tagging will ensure that mobile, Mac, and other clients will still get QoS treatment (at least partially).</span></span>

<span data-ttu-id="0033f-180">DSCP 标记可以是 likened 到邮票，用于向邮政标志指明邮政的重要程度，以及如何对其进行排序以实现快速交付。</span><span class="sxs-lookup"><span data-stu-id="0033f-180">DSCP markings can be likened to postage stamps that indicate to postal workers how urgent the delivery is and how best to sort it for speedy delivery.</span></span> <span data-ttu-id="0033f-181">将您的网络配置为为实时媒体流提供优先级后，丢失数据包和后期数据包应该会显著降低。</span><span class="sxs-lookup"><span data-stu-id="0033f-181">Once you've configured your network to give priority to real-time media streams, lost packets and late packets should diminish greatly.</span></span>

<span data-ttu-id="0033f-182">一旦网络中的所有设备使用相同的分类、标记和优先级，就可以通过更改分配给每个流量类型使用的队列的端口范围的大小来减少或消除延迟、丢弃的数据包和抖动。</span><span class="sxs-lookup"><span data-stu-id="0033f-182">Once all devices in the network are using the same classifications, markings, and priorities, it's possible to reduce or eliminate delays, dropped packets, and jitter by changing the size of the port ranges assigned to the queues used for each traffic type.</span></span> <span data-ttu-id="0033f-183">从 "团队" 角度来看，最重要的配置步骤是对数据包进行分类和标记，但要使端到端 QoS 成功，还需要将应用程序的配置与基础网络配置仔细对齐。</span><span class="sxs-lookup"><span data-stu-id="0033f-183">From the Teams perspective, the most important configuration step is the classification and marking of packets, but for end-to-end QoS to be successful you also need to carefully align the application's configuration with the underlying network configuration.</span></span> <span data-ttu-id="0033f-184">当 QoS 完全实施后，持续管理是根据组织的需求和实际使用情况调整分配给每个流量类型的端口范围的问题。</span><span class="sxs-lookup"><span data-stu-id="0033f-184">Once QoS is fully implemented, ongoing management is a question of adjusting the port ranges assigned to each traffic type based on your organization's needs and actual usage.</span></span>

## <a name="choose-initial-port-ranges-for-each-media-type"></a><span data-ttu-id="0033f-185">为每种媒体类型选择初始端口范围</span><span class="sxs-lookup"><span data-stu-id="0033f-185">Choose initial port ranges for each media type</span></span>

<span data-ttu-id="0033f-186">DSCP 值会将相应的配置的网络通知到相应配置的网络，提供数据包或流的优先级，无论是由客户还是基于 ACL 设置为网络本身分配了 DSCP 标记。</span><span class="sxs-lookup"><span data-stu-id="0033f-186">The DSCP value tells a correspondingly configured network what priority to give a packet or stream, whether the DSCP mark is assigned by clients or the network itself based on ACL settings.</span></span> <span data-ttu-id="0033f-187">每个媒体工作负荷获取自己的唯一 DSCP 值（其他服务可能允许工作负荷共享 DSCP 标记、团队不支持）以及用于每种媒体类型的定义的和单独的端口范围。</span><span class="sxs-lookup"><span data-stu-id="0033f-187">Each media workload gets its own unique DSCP value (other services might allow workloads to share a DSCP marking, Teams does not) and a defined and separate port range used for each media type.</span></span> <span data-ttu-id="0033f-188">其他环境可能具有现有的 QoS 策略，这将帮助你确定网络工作负荷的优先级。</span><span class="sxs-lookup"><span data-stu-id="0033f-188">Other environments might have an existing QoS strategy in place, which will help you determine the priority of network workloads.</span></span>

<span data-ttu-id="0033f-189">不同实时流工作负荷的端口范围的相对大小设置专用于该工作负荷的总可用带宽的比例。</span><span class="sxs-lookup"><span data-stu-id="0033f-189">The relative size of the port ranges for different real-time streaming workloads sets the proportion of the total available bandwidth dedicated to that workload.</span></span> <span data-ttu-id="0033f-190">若要返回到我们以前的邮政编码，请执行以下操作：带有 "Air Mail" 图章的信函可能会在一个小时内进入最接近的机场，而标记为 "大宗邮件" 的小程序包可以在一天前等待一天。</span><span class="sxs-lookup"><span data-stu-id="0033f-190">To return to our earlier postal analogy: a letter with an "Air Mail" stamp might get taken within an hour to the nearest airport, while a small package marked "Bulk Mail" mark can wait for a day before traveling over land on a series of trucks.</span></span>

<span data-ttu-id="0033f-191">_推荐的初始端口范围_</span><span class="sxs-lookup"><span data-stu-id="0033f-191">_Recommended initial port ranges_</span></span>

|<span data-ttu-id="0033f-192">媒体流量类型</span><span class="sxs-lookup"><span data-stu-id="0033f-192">Media traffic type</span></span>| <span data-ttu-id="0033f-193">客户端源端口范围</span><span class="sxs-lookup"><span data-stu-id="0033f-193">Client source port range</span></span> |<span data-ttu-id="0033f-194">协议</span><span class="sxs-lookup"><span data-stu-id="0033f-194">Protocol</span></span>|<span data-ttu-id="0033f-195">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="0033f-195">DSCP value</span></span>|<span data-ttu-id="0033f-196">DSCP 类</span><span class="sxs-lookup"><span data-stu-id="0033f-196">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="0033f-197">音频</span><span class="sxs-lookup"><span data-stu-id="0033f-197">Audio</span></span>| <span data-ttu-id="0033f-198">50,000–50,019</span><span class="sxs-lookup"><span data-stu-id="0033f-198">50,000–50,019</span></span>|<span data-ttu-id="0033f-199">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="0033f-199">TCP/UDP</span></span>|<span data-ttu-id="0033f-200">46</span><span class="sxs-lookup"><span data-stu-id="0033f-200">46</span></span>|<span data-ttu-id="0033f-201">加速转发 (EF)</span><span class="sxs-lookup"><span data-stu-id="0033f-201">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="0033f-202">视频</span><span class="sxs-lookup"><span data-stu-id="0033f-202">Video</span></span>| <span data-ttu-id="0033f-203">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="0033f-203">50,020–50,039</span></span>|<span data-ttu-id="0033f-204">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="0033f-204">TCP/UDP</span></span>|<span data-ttu-id="0033f-205">34</span><span class="sxs-lookup"><span data-stu-id="0033f-205">34</span></span>|<span data-ttu-id="0033f-206">保证转发 (AF41)</span><span class="sxs-lookup"><span data-stu-id="0033f-206">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="0033f-207">应用程序/屏幕共享</span><span class="sxs-lookup"><span data-stu-id="0033f-207">Application/Screen Sharing</span></span>| <span data-ttu-id="0033f-208">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="0033f-208">50,040–50,059</span></span>|<span data-ttu-id="0033f-209">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="0033f-209">TCP/UDP</span></span>|<span data-ttu-id="0033f-210">18</span><span class="sxs-lookup"><span data-stu-id="0033f-210">18</span></span>|<span data-ttu-id="0033f-211">保证转发 (AF21)</span><span class="sxs-lookup"><span data-stu-id="0033f-211">Assured Forwarding (AF21)</span></span>|
||||||

<span data-ttu-id="0033f-212">使用这些设置时，请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="0033f-212">Be aware of the following when you use these settings:</span></span>

- <span data-ttu-id="0033f-213">如果你计划在将来实施 ExpressRoute，但尚未实现 QoS，我们建议你按照指南进行操作，以便从发送方到接收方的 DSCP 值相同。</span><span class="sxs-lookup"><span data-stu-id="0033f-213">If you plan to implement ExpressRoute in the future and haven't yet implemented QoS, we recommend that you follow the guidance so that DSCP values are the same from sender to receiver.</span></span>
- <span data-ttu-id="0033f-214">所有客户（包括移动客户端和团队设备）将使用这些端口范围，并且将受到你使用这些源端口范围实现的任何 DSCP 策略的影响。</span><span class="sxs-lookup"><span data-stu-id="0033f-214">All clients, including mobile clients and Teams devices, will use these port ranges and will be affected by any DSCP policy you implement that uses these source port ranges.</span></span> <span data-ttu-id="0033f-215">只有基于浏览器的客户端（即允许参与者使用其浏览器加入会议的客户端）才会继续使用动态端口。</span><span class="sxs-lookup"><span data-stu-id="0033f-215">The only clients that will continue to use dynamic ports are the browser-based clients (that is, those clients that let participants join meetings by using their browsers).</span></span>
- <span data-ttu-id="0033f-216">虽然 Mac 客户端使用相同的端口范围，但它还会将硬编码的值用于音频（EF）和视频（AF41）。</span><span class="sxs-lookup"><span data-stu-id="0033f-216">Although the Mac client uses the same port ranges, it also uses hard-coded values for audio (EF) and video (AF41).</span></span> <span data-ttu-id="0033f-217">这些值不可配置。</span><span class="sxs-lookup"><span data-stu-id="0033f-217">These values are not configurable.</span></span>
- <span data-ttu-id="0033f-218">如果稍后需要调整端口范围以提高用户体验，则端口范围不会重叠，并且应彼此相邻。</span><span class="sxs-lookup"><span data-stu-id="0033f-218">If you later need to adjust the port ranges to improve user experience, the port ranges can not overlap and should be adjacent to each other.</span></span>

## <a name="migrate-qos-to-teams"></a><span data-ttu-id="0033f-219">将 QoS 迁移到团队</span><span class="sxs-lookup"><span data-stu-id="0033f-219">Migrate QoS to Teams</span></span>

<span data-ttu-id="0033f-220">如果你以前已部署 Skype for business Online，包括 QoS 标记和端口范围，并且现在部署团队，团队将考虑现有配置，并将使用相同的端口范围和标记作为 Skype for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="0033f-220">If you've previously deployed Skype for Business Online, including QoS tagging and port ranges, and are now deploying Teams, Teams will respect the existing configuration and will use the same port ranges and tagging as the Skype for Business client.</span></span> <span data-ttu-id="0033f-221">在大多数情况下，不需要额外的配置。</span><span class="sxs-lookup"><span data-stu-id="0033f-221">In most cases, no additional configuration will be needed.</span></span>

> [!NOTE]
> <span data-ttu-id="0033f-222">如果你通过组策略使用应用程序名称 QoS 标记，则必须添加 Teams.exe 作为应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="0033f-222">If you're using Application Name QoS tagging via Group Policy, you must add Teams.exe as the application name.</span></span>


## <a name="managing-source-ports-in-the-teams-admin-center"></a><span data-ttu-id="0033f-223">管理团队管理中心中的源端口</span><span class="sxs-lookup"><span data-stu-id="0033f-223">Managing source ports in the Teams admin center</span></span>

<span data-ttu-id="0033f-224">在团队中，不同工作负荷使用的 QoS 源端口应处于主动管理状态，并根据需要进行调整。</span><span class="sxs-lookup"><span data-stu-id="0033f-224">In Teams, QoS source ports used by the different workloads should be actively managed, and adjusted as necessary.</span></span> <span data-ttu-id="0033f-225">在[选择每个媒体类型的初始端口范围](#choose-initial-port-ranges-for-each-media-type)中引用表，可调整端口范围，但无法配置 DSCP 标记。</span><span class="sxs-lookup"><span data-stu-id="0033f-225">Referring to the table in [Choose initial port ranges for each media type](#choose-initial-port-ranges-for-each-media-type), the port ranges are adjustable, but the DSCP markings are not configurable.</span></span> <span data-ttu-id="0033f-226">实现这些设置后，你可能会发现给定媒体类型需要更多或更少的端口。</span><span class="sxs-lookup"><span data-stu-id="0033f-226">Once you have implemented these settings, you may find that more or fewer ports are needed for a given media type.</span></span> <span data-ttu-id="0033f-227">[每用户呼叫分析](use-call-analytics-to-troubleshoot-poor-call-quality.md)和[通话质量仪表板（CQD）](turning-on-and-using-call-quality-dashboard.md)应该用于决定在团队实施后调整端口范围，以及根据需要定期进行更改。</span><span class="sxs-lookup"><span data-stu-id="0033f-227">[Per-user call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md) and [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) should be used in making a decision to adjust port ranges after Teams has been implemented, and periodically as needs change.</span></span>

> [!NOTE]
> <span data-ttu-id="0033f-228">如果你已基于 Skype for business Online 的源端口范围和 DSCP 标记配置了 QoS，则同一配置将应用到团队，并且不需要进一步的客户端或网络更改，但你可能需要[将团队中使用的区域](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)与 skype For business Online 配置相匹配。</span><span class="sxs-lookup"><span data-stu-id="0033f-228">If you've already configured QoS based on source port ranges and DSCP markings for Skype for Business Online, the same configuration will apply to Teams and no further client or network changes to the mapping will be required, though you may have to [set the ranges used in Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) to match what was configured for Skype for Business Online.</span></span>

<span data-ttu-id="0033f-229">如果以前已部署了本地 Skype for business 服务器，你可能需要重新检查 QoS 策略并对其进行调整，以匹配已验证的端口范围设置为团队提供了高质量的用户体验。</span><span class="sxs-lookup"><span data-stu-id="0033f-229">If you’ve previously deployed Skype for Business Server on-premises, you may need to re-examine your QoS policies and adjust them to match port range settings you've verified provide a quality user experience for Teams.</span></span>

## <a name="validate-your-qos-implementation"></a><span data-ttu-id="0033f-230">验证你的 QoS 实施</span><span class="sxs-lookup"><span data-stu-id="0033f-230">Validate your QoS implementation</span></span>

<span data-ttu-id="0033f-231">为了使 QoS 有效，组策略对象设置的 DSCP 值需要存在于调用的两端。</span><span class="sxs-lookup"><span data-stu-id="0033f-231">For QoS to be effective, the DSCP value set by the Group Policy object needs to be present at both ends of a call.</span></span> <span data-ttu-id="0033f-232">通过分析由团队客户端生成的流量，可以验证当团队工作负载流量通过网络移动时，DSCP 值不会更改或去除。</span><span class="sxs-lookup"><span data-stu-id="0033f-232">By analyzing the traffic generated by the Teams client, you can verify that the DSCP value isn’t changed or stripped out when the Teams workload traffic moves through the network.</span></span>

<span data-ttu-id="0033f-233">最好是在网络出口点处捕获流量。</span><span class="sxs-lookup"><span data-stu-id="0033f-233">Preferably, you capture traffic at the network egress point.</span></span> <span data-ttu-id="0033f-234">可以在交换机或路由器上使用端口镜像来帮助解决此情况。</span><span class="sxs-lookup"><span data-stu-id="0033f-234">You can use port mirroring on a switch or router to help with this.</span></span>


## <a name="related-topics"></a><span data-ttu-id="0033f-235">相关主题</span><span class="sxs-lookup"><span data-stu-id="0033f-235">Related topics</span></span>

[<span data-ttu-id="0033f-236">视频：网络规划</span><span class="sxs-lookup"><span data-stu-id="0033f-236">Video: Network Planning</span></span>](https://aka.ms/teams-networking)

[<span data-ttu-id="0033f-237">为 Microsoft Teams 准备组织的网络</span><span class="sxs-lookup"><span data-stu-id="0033f-237">Prepare your organization's network for Microsoft Teams</span></span>](prepare-network.md)

[<span data-ttu-id="0033f-238">在团队客户端中实施 QoS</span><span class="sxs-lookup"><span data-stu-id="0033f-238">Implement QoS in the Teams client</span></span>](QoS-in-Teams-clients.md)
