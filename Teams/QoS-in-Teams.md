---
title: 在 Microsoft Teams 中实施服务质量
author: lanachin
ms.author: v-lanac
manager: Serdars
ms.date: 12/17/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
audience: admin
description: 了解如何为 Microsoft 团队中的服务质量（QoS）准备组织网络。
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.meetingsettings.qos
- ms.teamsadmincenter.meetingsettings.network.qosmarkers
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 545cbc1d170f6b511de5e8d21a237bc893ee0702
ms.sourcegitcommit: cddaacf1e8dbcdfd3f94deee7057c89cee0e5699
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2020
ms.locfileid: "43138032"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a><span data-ttu-id="df414-103">在 Microsoft 团队中实施服务质量（QoS）</span><span class="sxs-lookup"><span data-stu-id="df414-103">Implement Quality of Service (QoS) in Microsoft Teams</span></span>

<span data-ttu-id="df414-104">本文将帮助你为 Microsoft 团队中的服务质量（QoS）准备组织的网络。</span><span class="sxs-lookup"><span data-stu-id="df414-104">This article will help you prepare your organization's network for Quality of Service (QoS) in Microsoft Teams.</span></span> <span data-ttu-id="df414-105">如果你支持一组大型用户，并且遇到下面所述的任何问题，则可能需要实现 QoS。</span><span class="sxs-lookup"><span data-stu-id="df414-105">If you are supporting a large group of users and they are experiencing any of the problems mentioned below, you probably need to implement QoS.</span></span> <span data-ttu-id="df414-106">用户数较少的小型企业可能不需要 QoS，但甚至应该有帮助。</span><span class="sxs-lookup"><span data-stu-id="df414-106">A small business with few users may not need QoS, but even there it should be helpful.</span></span>

<span data-ttu-id="df414-107">QoS 是一种允许实时网络流量（如语音或视频流）对网络延迟（如下载新应用，要下载不太重要的应用）的网络延迟的敏感网络流量（如下载新应用程序）。</span><span class="sxs-lookup"><span data-stu-id="df414-107">QoS is a way to allow real-time network traffic (like voice or video streams) that is sensitive to network delays to "cut in line" in front of traffic that is less sensitive (like downloading a new app, where an extra second to download isn't a big deal).</span></span> <span data-ttu-id="df414-108">QoS 在实时流中标识和标记所有数据包（使用 Windows 组策略对象和名为基于端口的访问控制列表的路由功能，有关这些列表的详细信息），然后可帮助你的网络提供语音、视频和屏幕共享流，以流出专用的网络带宽部分。</span><span class="sxs-lookup"><span data-stu-id="df414-108">QoS identifies and marks all packets in real-time streams (using Windows Group Policy Objects and a routing feature called Port-based Access Control Lists, more about those is below) which then helps your network to give voice, video, and screen share streams a dedicated portion of network bandwidth.</span></span>

<span data-ttu-id="df414-109">如果没有某种形式的 QoS，您可能会在语音和视频中看到以下质量问题：</span><span class="sxs-lookup"><span data-stu-id="df414-109">Without some form of QoS, you might see the following quality issues in voice and video:</span></span>

- <span data-ttu-id="df414-110">抖动-媒体数据包以不同的费率收取，这可能会导致通话中缺少单词或音节。</span><span class="sxs-lookup"><span data-stu-id="df414-110">Jitter – media packets arriving at different rates, which can result in missing words or syllables in calls.</span></span>
- <span data-ttu-id="df414-111">数据包丢失-丢弃的数据包，也可能导致更低的语音质量，并且难以理解语音。</span><span class="sxs-lookup"><span data-stu-id="df414-111">Packet loss – packets dropped, which can also result in lower voice quality and hard to understand speech.</span></span>
- <span data-ttu-id="df414-112">延迟的往返时间（RTT）-媒体数据包在到达其目标时花费很长时间，从而导致对话中两方之间出现明显延迟，从而导致用户相互通话。</span><span class="sxs-lookup"><span data-stu-id="df414-112">Delayed round trip time (RTT) – media packets taking a long time to reach their destinations, which results in noticeable delays between two parties in a conversation, causing people to talk over each other.</span></span>

<span data-ttu-id="df414-113">解决这些问题的最简单的方法是在内部和 internet 上增加数据连接的大小。</span><span class="sxs-lookup"><span data-stu-id="df414-113">The least complex way to address these issues is to increase the size of the data connections, both internally and out to the internet.</span></span> <span data-ttu-id="df414-114">由于这通常是成本不受影响的，因此 QoS 提供了一种更高效地管理您所拥有的资源（而不是添加新资源）的方法。</span><span class="sxs-lookup"><span data-stu-id="df414-114">Since that is often cost-prohibitive, QoS provides a way to more effectively manage the resources you have instead of adding new resources.</span></span> <span data-ttu-id="df414-115">若要完全解决质量问题，请在实现中使用 QoS，然后仅在绝对必要的位置添加连接。</span><span class="sxs-lookup"><span data-stu-id="df414-115">To fully address quality issues you would use QoS across the implementation, then add connectivity only where absolutely necessary.</span></span>

<span data-ttu-id="df414-116">为了使 QoS 生效，你的组织中的一致 QoS 设置将在你的组织中最终应用，因为无法支持 QoS 优先级的路径的任何部分可能会降低呼叫、视频和屏幕共享的质量。</span><span class="sxs-lookup"><span data-stu-id="df414-116">For QoS to be effective, you will have have consistent QoS settings applied end to end in your organization, because any part of the path that fails to support your QoS priorities can degrade the quality of calls, video, and screen shares.</span></span> <span data-ttu-id="df414-117">这包括将设置应用到所有用户电脑或设备、网络交换机、互联网路由器以及团队联机服务。</span><span class="sxs-lookup"><span data-stu-id="df414-117">This includes applying settings to all user PCs or devices, network switches, routers to the internet, and the Teams online service.</span></span>

<span data-ttu-id="df414-118">_图1。组织的网络和 Office 365 服务之间的关系_</span><span class="sxs-lookup"><span data-stu-id="df414-118">_Figure 1. The relationship between an organization's networks and Office 365 services_</span></span>

<span data-ttu-id="df414-119">![网络和服务之间的关系的插图](media/Qos-in-Teams-Image1.png "组织的网络和 Office 365 服务之间的关系：本地网络和设备与互连网络连接，后者又与 Office 365 云语音和音频会议服务连接。")</span><span class="sxs-lookup"><span data-stu-id="df414-119">![Illustration of the relationship between networks and services](media/Qos-in-Teams-Image1.png "The relationship between an organization's networks and Office 365 services: on-premises network and devices connect with an interconnect network, which in turn connects with Office 365 Cloud Voice and Audio Conferencing services.")</span></span>

<span data-ttu-id="df414-120">在大多数情况下，将你的企业连接到云的网络将是无法可靠地设置 QoS 选项的非托管网络。</span><span class="sxs-lookup"><span data-stu-id="df414-120">In most cases, the network connecting your enterprise to the cloud will be an unmanaged network where you won't be able to reliably set QoS options.</span></span> <span data-ttu-id="df414-121">用于解决端到端 QoS 的一个选择是[Azure ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/)，但我们仍建议你在本地网络上为入站和出站流量实现 QoS。</span><span class="sxs-lookup"><span data-stu-id="df414-121">One choice available to address end-to-end QoS is [Azure ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-introduction/), but we still recommend that you implement QoS on your on-premises network for both inbound and outbound traffic.</span></span> <span data-ttu-id="df414-122">这将提高整个部署中实时通信工作负荷的质量并减少 chokepoints。</span><span class="sxs-lookup"><span data-stu-id="df414-122">This will increase the quality of real-time communication workloads throughout your deployment and alleviate chokepoints.</span></span>

## <a name="verify-your-network-is-ready"></a><span data-ttu-id="df414-123">验证网络是否已准备好</span><span class="sxs-lookup"><span data-stu-id="df414-123">Verify your network is ready</span></span>

<span data-ttu-id="df414-124">如果你正在考虑 QoS 实施，你应该已确定带宽要求和其他[网络要求](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="df414-124">If you are considering a QoS implementation, you should already have determined your bandwidth requirements and other [network requirements](prepare-network.md).</span></span> 
  
  <span data-ttu-id="df414-125">网络上的流量拥塞将显著影响媒体质量。</span><span class="sxs-lookup"><span data-stu-id="df414-125">Traffic congestion across a network will greatly impact media quality.</span></span> <span data-ttu-id="df414-126">缺少带宽会导致性能下降和用户体验较差。</span><span class="sxs-lookup"><span data-stu-id="df414-126">A lack of bandwidth leads to performance degradation and a poor user experience.</span></span> <span data-ttu-id="df414-127">当团队采纳和使用增加时，请使用 "报告"、"[呼叫分析" 和 "呼叫质量" 仪表板](difference-between-call-analytics-and-call-quality-dashboard.md)来识别问题，然后使用 QoS 和选择性带宽增加进行调整。</span><span class="sxs-lookup"><span data-stu-id="df414-127">As Teams adoption and usage grows, use reporting,  [Call Analytics, and Call Quality Dashboard](difference-between-call-analytics-and-call-quality-dashboard.md) to identify problems and then make adjustments using QoS and selective bandwidth additions.</span></span>

### <a name="vpn-considerations"></a><span data-ttu-id="df414-128">VPN 注意事项</span><span class="sxs-lookup"><span data-stu-id="df414-128">VPN considerations</span></span>

<span data-ttu-id="df414-129">仅当在调用方之间的所有链接上实现时，QoS 才按预期工作。</span><span class="sxs-lookup"><span data-stu-id="df414-129">QoS only works as expected when implemented on all links between callers.</span></span> <span data-ttu-id="df414-130">如果在内部网络上使用 QoS，并且用户从远程位置登录，则只能在内部托管网络中设置优先级。</span><span class="sxs-lookup"><span data-stu-id="df414-130">If you use QoS on an internal network and a user signs in from a remote location, you can only prioritize within your internal, managed network.</span></span> <span data-ttu-id="df414-131">虽然远程位置可以通过实施虚拟专用网络（VPN）接收托管连接，但 VPN 本身会增加数据包开销并在实时流量中产生延迟。</span><span class="sxs-lookup"><span data-stu-id="df414-131">Although remote locations can receive a managed connection by implementing a virtual private network (VPN),  a VPN inherently adds packet overhead and creates delays in real-time traffic.</span></span> <span data-ttu-id="df414-132">我们建议你避免通过 VPN 运行实时通信流量。</span><span class="sxs-lookup"><span data-stu-id="df414-132">We  recommend that you avoid running real-time communications traffic over a VPN.</span></span>

<span data-ttu-id="df414-133">在具有跨大洲的托管链接的全球组织中，我们强烈建议使用 QoS，因为与 LAN 相比，这些链接的带宽受到限制。</span><span class="sxs-lookup"><span data-stu-id="df414-133">In a global organization with managed links that span continents, we strongly recommend QoS because bandwidth for those links is limited in comparison to the LAN.</span></span>

## <a name="introduction-to-qos-queues"></a><span data-ttu-id="df414-134">QoS 队列简介</span><span class="sxs-lookup"><span data-stu-id="df414-134">Introduction to QoS queues</span></span>

<span data-ttu-id="df414-135">为了提供 QoS，网络设备必须能够对流量进行分类，并且必须能够将语音或视频与其他网络流量区分开。</span><span class="sxs-lookup"><span data-stu-id="df414-135">To provide QoS, network devices must have a way to classify traffic and must be able to distinguish voice or video from other network traffic.</span></span>

<span data-ttu-id="df414-136">当网络流量进入路由器时，流量将放入队列中。</span><span class="sxs-lookup"><span data-stu-id="df414-136">When network traffic enters a router, the traffic is placed into a queue.</span></span> <span data-ttu-id="df414-137">如果未配置 QoS 策略，则仅有一个队列，所有数据将按具有相同优先级的第一项处理。</span><span class="sxs-lookup"><span data-stu-id="df414-137">If a QoS policy isn't configured, there is only one queue, and all data is treated as first-in, first-out with the same priority.</span></span> <span data-ttu-id="df414-138">这意味着语音流量（对延迟非常敏感）可能会陷入通信量不足的情况下，延迟几个额外的毫秒不会出现问题。</span><span class="sxs-lookup"><span data-stu-id="df414-138">That means voice traffic (which is very sensitive to delays) might get stuck behind traffic where a delay of a few extra milliseconds wouldn't be a problem.</span></span>

<span data-ttu-id="df414-139">当你实现 QoS 时，你可以使用以下几个拥塞管理功能之一（如 Cisco 的优先级队列和基于类的加权公平队列[CBWFQ](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641)）和拥塞回避功能（如加权随机检测[WRED](https://en.wikipedia.org/wiki/Weighted_random_early_detection)）定义多个队列。</span><span class="sxs-lookup"><span data-stu-id="df414-139">When you implement QoS, you define multiple queues using one of several congestion management features (such as Cisco's priority queuing and Class-Based Weighted Fair Queueing [CBWFQ](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641)) and congestion avoidance features (such as weighted random early detection [WRED](https://en.wikipedia.org/wiki/Weighted_random_early_detection)).</span></span>

<span data-ttu-id="df414-140">_图2。QoS 队列的示例_</span><span class="sxs-lookup"><span data-stu-id="df414-140">_Figure 2. Examples of QoS queues_</span></span>

<span data-ttu-id="df414-141">![QoS 队列和带宽划分的插图](media/Qos-in-Teams-Image2.png "可用带宽的总可用带宽分为多个队列：音频、视频和其他流量，这些队列已被分配不同的优先级。")</span><span class="sxs-lookup"><span data-stu-id="df414-141">![Illustration of QoS queues and bandwidth division](media/Qos-in-Teams-Image2.png "Total available bandwidth is divided among multiple queues—audio, video, and other traffic—that have been assigned different priorities.")</span></span>

<span data-ttu-id="df414-142">简单的类比是 QoS 在数据网络中创建虚拟的 "carpool 车道"，因此某些类型的数据从不或几乎不会遇到延迟。</span><span class="sxs-lookup"><span data-stu-id="df414-142">A simple analogy is that QoS creates virtual "carpool lanes" in your data network so some types of data never or rarely encounter a delay.</span></span> <span data-ttu-id="df414-143">创建这些泳道后，您可以调整其相对大小，并更有效地管理您拥有的连接带宽，同时还可以为您的组织的用户提供业务级体验。</span><span class="sxs-lookup"><span data-stu-id="df414-143">Once you create those lanes, you can adjust their relative size and much more effectively manage the connection bandwidth you have, while still delivering business-grade experiences for your organization's users.</span></span>

## <a name="select-a-qos-implementation-method"></a><span data-ttu-id="df414-144">选择 QoS 实现方法</span><span class="sxs-lookup"><span data-stu-id="df414-144">Select a QoS implementation method</span></span>

<span data-ttu-id="df414-145">你可以使用网络路由器上的访问控制列表（Acl），通过基于端口的标记实现 QoS。</span><span class="sxs-lookup"><span data-stu-id="df414-145">You could implement QoS via port-based tagging, using Access Control Lists (ACLs) on your network's routers.</span></span> <span data-ttu-id="df414-146">基于端口的标记是最可靠的方法，因为它可以在混合 Windows 和 Mac 环境中使用，并且最容易实现。</span><span class="sxs-lookup"><span data-stu-id="df414-146">Port-based tagging is the most reliable method because it works in mixed Windows and Mac environments and is the easiest to implement.</span></span> <span data-ttu-id="df414-147">移动客户端不提供使用 DSCP 值标记流量的机制，因此它们将需要此方法。</span><span class="sxs-lookup"><span data-stu-id="df414-147">Mobile clients don't provide a mechanism to mark traffic by using DSCP values, so they will require this method.</span></span>  

<span data-ttu-id="df414-148">使用此方法，你的网络路由器会检查传入的数据包，如果该数据包使用特定端口或端口范围接收，则它将其标识为特定媒体类型，并将其放入该类型的队列中，将预定义的[DSCP](https://tools.ietf.org/html/rfc2474)标记添加到 IP 数据包标头，以便其他设备可以识别其流量类型，并在其队列中授予其优先级。</span><span class="sxs-lookup"><span data-stu-id="df414-148">Using this method, your network's router examines an incoming packet, and if the packet arrived using a certain port or range of ports, it identifies it as a certain media type and puts it in the queue for that type, adding a predetermined [DSCP](https://tools.ietf.org/html/rfc2474) mark to the IP Packet header so other devices can recognize its traffic type and give it priority in their queue.</span></span>

<span data-ttu-id="df414-149">尽管这在多个平台上有效，但它仅将流量标记为 WAN edge （而不是客户端计算机的任何方式），并创建管理开销。</span><span class="sxs-lookup"><span data-stu-id="df414-149">Although this works across platforms, it only marks traffic at the WAN edge (not all the way to the client machine) and creates management overhead.</span></span> <span data-ttu-id="df414-150">您应该参考路由器制造商提供的文档，获取有关实施此方法的说明。</span><span class="sxs-lookup"><span data-stu-id="df414-150">You should refer to the documentation provided by the router manufacturer for instructions on implementing this method.</span></span>

* * *

<span data-ttu-id="df414-151">你还可以通过使用组策略对象（GPO）来实现 QoS，以直接在 IP 数据包标题中插入 DSCP 标记，将其识别为特定类型的流量（例如，语音）。</span><span class="sxs-lookup"><span data-stu-id="df414-151">You could also implement QoS implemented by using a Group Policy Object (GPO) to direct client devices to insert a DSCP marker in IP packet headers identifying it as particular type of traffic(for example, voice).</span></span> <span data-ttu-id="df414-152">路由器和其他网络设备可以配置为识别此项，并将流量放在一个单独的、优先级较高的队列中。</span><span class="sxs-lookup"><span data-stu-id="df414-152">Routers and other network devices can be configured to recognize this and put the traffic in a separate, higher-priority queue.</span></span>

<span data-ttu-id="df414-153">虽然此方案完全有效，但它仅适用于加入域的 Windows 客户端。</span><span class="sxs-lookup"><span data-stu-id="df414-153">Although this scenario is entirely valid, it will only work for domain-joined Windows clients.</span></span> <span data-ttu-id="df414-154">任何不是加入域的 Windows 客户端的设备都不会启用 DSCP 标记。</span><span class="sxs-lookup"><span data-stu-id="df414-154">Any device that isn't a domain-joined Windows client won't be enabled for DSCP tagging.</span></span> <span data-ttu-id="df414-155">客户端（如 Mac OS）具有硬编码的标记，并且将始终标记流量。</span><span class="sxs-lookup"><span data-stu-id="df414-155">Clients such as Mac OS have hard-coded tags and will always tag traffic.</span></span>

<span data-ttu-id="df414-156">在加号，通过 GPO 控制 DSCP 标记可确保所有加入域的计算机接收相同的设置，并且只有管理员可以管理它们。</span><span class="sxs-lookup"><span data-stu-id="df414-156">On the plus side, controlling the DSCP marking via GPO ensures that all domain-joined computers receive the same settings and that only an administrator can manage them.</span></span> <span data-ttu-id="df414-157">可以使用 GPO 的客户端将在原始设备上进行标记，然后配置的网络设备可以通过 DSCP 代码识别实时流并为其提供相应优先级。</span><span class="sxs-lookup"><span data-stu-id="df414-157">Clients that can use GPO will be tagged on the originating device, and then configured network devices can recognize the real-time stream by the DSCP code and give it an appropriate priority.</span></span>

* * *

<span data-ttu-id="df414-158">我们建议在路由器上的终结点和基于端口的 Acl 中使用 DSCP 标记组合（如有可能）。</span><span class="sxs-lookup"><span data-stu-id="df414-158">We recommend a combination of DSCP markings at the endpoint and port-based ACLs on routers, if possible.</span></span> <span data-ttu-id="df414-159">使用组策略对象捕获大多数客户端，同时使用基于端口的 DSCP 标记，可确保移动、Mac 和其他客户端仍会获得 QoS 处理（至少部分）。</span><span class="sxs-lookup"><span data-stu-id="df414-159">Using a Group Policy object to catch the majority of clients, and also using port-based DSCP tagging will ensure that mobile, Mac, and other clients will still get QoS treatment (at least partially).</span></span>

<span data-ttu-id="df414-160">DSCP 标记可以是 likened 到邮票，用于向邮政标志指明邮政的重要程度，以及如何对其进行排序以实现快速交付。</span><span class="sxs-lookup"><span data-stu-id="df414-160">DSCP markings can be likened to postage stamps that indicate to postal workers how urgent the delivery is and how best to sort it for speedy delivery.</span></span> <span data-ttu-id="df414-161">将您的网络配置为为实时媒体流提供优先级后，丢失数据包和后期数据包应该会显著降低。</span><span class="sxs-lookup"><span data-stu-id="df414-161">Once you've configured your network to give priority to real-time media streams, lost packets and late packets should diminish greatly.</span></span>

<span data-ttu-id="df414-162">一旦网络中的所有设备使用相同的分类、标记和优先级，就可以通过更改分配给每个流量类型使用的队列的端口范围的大小来减少或消除延迟、丢弃的数据包和抖动。</span><span class="sxs-lookup"><span data-stu-id="df414-162">Once all devices in the network are using the same classifications, markings, and priorities, it's possible to reduce or eliminate delays, dropped packets, and jitter by changing the size of the port ranges assigned to the queues used for each traffic type.</span></span> <span data-ttu-id="df414-163">从 "团队" 角度来看，最重要的配置步骤是对数据包进行分类和标记，但要使端到端 QoS 成功，还需要将应用程序的配置与基础网络配置仔细对齐。</span><span class="sxs-lookup"><span data-stu-id="df414-163">From the Teams perspective, the most important configuration step is the classification and marking of packets, but for end-to-end QoS to be successful you also need to carefully align the application's configuration with the underlying network configuration.</span></span> <span data-ttu-id="df414-164">当 QoS 完全实施后，持续管理是根据组织的需求和实际使用情况调整分配给每个流量类型的端口范围的问题。</span><span class="sxs-lookup"><span data-stu-id="df414-164">Once QoS is fully implemented, ongoing management is a question of adjusting the port ranges assigned to each traffic type based on your organization's needs and actual usage.</span></span>

## <a name="choose-initial-port-ranges-for-each-media-type"></a><span data-ttu-id="df414-165">为每种媒体类型选择初始端口范围</span><span class="sxs-lookup"><span data-stu-id="df414-165">Choose initial port ranges for each media type</span></span>

<span data-ttu-id="df414-166">DSCP 值会将相应的配置的网络通知到相应配置的网络，提供数据包或流的优先级，无论是由客户还是基于 ACL 设置为网络本身分配了 DSCP 标记。</span><span class="sxs-lookup"><span data-stu-id="df414-166">The DSCP value tells a correspondingly configured network what priority to give a packet or stream, whether the DSCP mark is assigned by clients or the network itself based on ACL settings.</span></span> <span data-ttu-id="df414-167">每个媒体工作负荷获取自己的唯一 DSCP 值（其他服务可能允许工作负荷共享 DSCP 标记、团队不支持）以及用于每种媒体类型的定义的和单独的端口范围。</span><span class="sxs-lookup"><span data-stu-id="df414-167">Each media workload gets its own unique DSCP value (other services might allow workloads to share a DSCP marking, Teams does not) and a defined and separate port range used for each media type.</span></span> <span data-ttu-id="df414-168">其他环境可能具有现有的 QoS 策略，这将帮助你确定网络工作负荷的优先级。</span><span class="sxs-lookup"><span data-stu-id="df414-168">Other environments might have an existing QoS strategy in place, which will help you determine the priority of network workloads.</span></span>

<span data-ttu-id="df414-169">不同实时流工作负荷的端口范围的相对大小设置专用于该工作负荷的总可用带宽的比例。</span><span class="sxs-lookup"><span data-stu-id="df414-169">The relative size of the port ranges for different real-time streaming workloads sets the proportion of the total available bandwidth dedicated to that workload.</span></span> <span data-ttu-id="df414-170">若要返回到我们以前的邮政编码，请执行以下操作：带有 "Air Mail" 图章的信函可能会在一个小时内进入最接近的机场，而标记为 "大宗邮件" 的小程序包可以在一天前等待一天。</span><span class="sxs-lookup"><span data-stu-id="df414-170">To return to our earlier postal analogy: a letter with an "Air Mail" stamp might get taken within an hour to the nearest airport, while a small package marked "Bulk Mail" mark can wait for a day before traveling over land on a series of trucks.</span></span>

<span data-ttu-id="df414-171">下表显示了所需的 DSCP 标记以及团队和 ExpressRoute 使用的建议的相应媒体端口范围。</span><span class="sxs-lookup"><span data-stu-id="df414-171">The following table shows the required DSCP markings and the suggested corresponding media port ranges used by both Teams and ExpressRoute.</span></span> <span data-ttu-id="df414-172">对于不确定在其自己的环境中使用哪些内容的客户，这些范围可能是一个良好的起点。</span><span class="sxs-lookup"><span data-stu-id="df414-172">These ranges might serve as a good starting point for customers who are unsure what to use in their own environments.</span></span> <span data-ttu-id="df414-173">要了解详细信息，请阅读 [ExpressRoute QoS 要求](https://docs.microsoft.com/azure/expressroute/expressroute-qos)。</span><span class="sxs-lookup"><span data-stu-id="df414-173">To learn more, read [ExpressRoute QoS requirements](https://docs.microsoft.com/azure/expressroute/expressroute-qos).</span></span>

<span data-ttu-id="df414-174">_推荐的初始端口范围_</span><span class="sxs-lookup"><span data-stu-id="df414-174">_Recommended initial port ranges_</span></span>

|<span data-ttu-id="df414-175">媒体流量类型</span><span class="sxs-lookup"><span data-stu-id="df414-175">Media traffic type</span></span>| <span data-ttu-id="df414-176">客户端源端口范围</span><span class="sxs-lookup"><span data-stu-id="df414-176">Client source port range</span></span> |<span data-ttu-id="df414-177">协议</span><span class="sxs-lookup"><span data-stu-id="df414-177">Protocol</span></span>|<span data-ttu-id="df414-178">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="df414-178">DSCP value</span></span>|<span data-ttu-id="df414-179">DSCP 类</span><span class="sxs-lookup"><span data-stu-id="df414-179">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="df414-180">音频</span><span class="sxs-lookup"><span data-stu-id="df414-180">Audio</span></span>| <span data-ttu-id="df414-181">50,000–50,019</span><span class="sxs-lookup"><span data-stu-id="df414-181">50,000–50,019</span></span>|<span data-ttu-id="df414-182">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="df414-182">TCP/UDP</span></span>|<span data-ttu-id="df414-183">46</span><span class="sxs-lookup"><span data-stu-id="df414-183">46</span></span>|<span data-ttu-id="df414-184">加速转发 (EF)</span><span class="sxs-lookup"><span data-stu-id="df414-184">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="df414-185">视频</span><span class="sxs-lookup"><span data-stu-id="df414-185">Video</span></span>| <span data-ttu-id="df414-186">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="df414-186">50,020–50,039</span></span>|<span data-ttu-id="df414-187">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="df414-187">TCP/UDP</span></span>|<span data-ttu-id="df414-188">34</span><span class="sxs-lookup"><span data-stu-id="df414-188">34</span></span>|<span data-ttu-id="df414-189">保证转发 (AF41)</span><span class="sxs-lookup"><span data-stu-id="df414-189">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="df414-190">应用程序/屏幕共享</span><span class="sxs-lookup"><span data-stu-id="df414-190">Application/Screen Sharing</span></span>| <span data-ttu-id="df414-191">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="df414-191">50,040–50,059</span></span>|<span data-ttu-id="df414-192">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="df414-192">TCP/UDP</span></span>|<span data-ttu-id="df414-193">18</span><span class="sxs-lookup"><span data-stu-id="df414-193">18</span></span>|<span data-ttu-id="df414-194">保证转发 (AF21)</span><span class="sxs-lookup"><span data-stu-id="df414-194">Assured Forwarding (AF21)</span></span>|
||||||

<span data-ttu-id="df414-195">使用这些设置时，请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="df414-195">Be aware of the following when you use these settings:</span></span>

- <span data-ttu-id="df414-196">如果你计划在将来实施 ExpressRoute，但尚未实现 QoS，我们建议你按照指南进行操作，以便从发送方到接收方的 DSCP 值相同。</span><span class="sxs-lookup"><span data-stu-id="df414-196">If you plan to implement ExpressRoute in the future and haven't yet implemented QoS, we recommend that you follow the guidance so that DSCP values are the same from sender to receiver.</span></span>
- <span data-ttu-id="df414-197">所有客户（包括移动客户端和团队设备）将使用这些端口范围，并且将受到你使用这些源端口范围实现的任何 DSCP 策略的影响。</span><span class="sxs-lookup"><span data-stu-id="df414-197">All clients, including mobile clients and Teams devices, will use these port ranges and will be affected by any DSCP policy you implement that uses these source port ranges.</span></span> <span data-ttu-id="df414-198">只有基于浏览器的客户端（即允许参与者使用其浏览器加入会议的客户端）才会继续使用动态端口。</span><span class="sxs-lookup"><span data-stu-id="df414-198">The only clients that will continue to use dynamic ports are the browser-based clients (that is, those clients that let participants join meetings by using their browsers).</span></span>
- <span data-ttu-id="df414-199">虽然 Mac 客户端使用相同的端口范围，但它还会将硬编码的值用于音频（EF）和视频（AF41）。</span><span class="sxs-lookup"><span data-stu-id="df414-199">Although the Mac client uses the same port ranges, it also uses hard-coded values for audio (EF) and video (AF41).</span></span> <span data-ttu-id="df414-200">这些值不可配置。</span><span class="sxs-lookup"><span data-stu-id="df414-200">These values are not configurable.</span></span>
- <span data-ttu-id="df414-201">如果稍后需要调整端口范围以提高用户体验，则端口范围不会重叠，并且应彼此相邻。</span><span class="sxs-lookup"><span data-stu-id="df414-201">If you later need to adjust the port ranges to improve user experience, the port ranges can not overlap and should be adjacent to each other.</span></span>

## <a name="migrate-qos-to-teams"></a><span data-ttu-id="df414-202">将 QoS 迁移到团队</span><span class="sxs-lookup"><span data-stu-id="df414-202">Migrate QoS to Teams</span></span>

<span data-ttu-id="df414-203">如果你以前已部署 Skype for business Online，包括 QoS 标记和端口范围，并且现在部署团队，团队将考虑现有配置，并将使用相同的端口范围和标记作为 Skype for Business 客户端。</span><span class="sxs-lookup"><span data-stu-id="df414-203">If you've previously deployed Skype for Business Online, including QoS tagging and port ranges, and are now deploying Teams, Teams will respect the existing configuration and will use the same port ranges and tagging as the Skype for Business client.</span></span> <span data-ttu-id="df414-204">在大多数情况下，不需要额外的配置。</span><span class="sxs-lookup"><span data-stu-id="df414-204">In most cases, no additional configuration will be needed.</span></span>

> [!NOTE]
> <span data-ttu-id="df414-205">如果你通过组策略使用应用程序名称 QoS 标记，则必须添加作为应用程序名称的团队 .exe。</span><span class="sxs-lookup"><span data-stu-id="df414-205">If you're using Application Name QoS tagging via Group Policy, you must add Teams.exe as the application name.</span></span>

## <a name="qos-implementation-steps"></a><span data-ttu-id="df414-206">QoS 实施步骤</span><span class="sxs-lookup"><span data-stu-id="df414-206">QoS implementation steps</span></span>

<span data-ttu-id="df414-207">在非常高的级别上，实现 QoS 需要执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="df414-207">At a very high level, implementing QoS requires these steps:</span></span>

1. [<span data-ttu-id="df414-208">验证网络是否已准备好</span><span class="sxs-lookup"><span data-stu-id="df414-208">Verify your network is ready</span></span>](#verify-your-network-is-ready)
2. [<span data-ttu-id="df414-209">选择 QoS 实现方法</span><span class="sxs-lookup"><span data-stu-id="df414-209">Select a QoS implementation method</span></span>](#select-a-qos-implementation-method)
3. [<span data-ttu-id="df414-210">为每种媒体类型选择初始端口范围</span><span class="sxs-lookup"><span data-stu-id="df414-210">Choose initial port ranges for each media type</span></span>](#choose-initial-port-ranges-for-each-media-type)
4. <span data-ttu-id="df414-211">实施 QoS 设置：</span><span class="sxs-lookup"><span data-stu-id="df414-211">Implement QoS settings:</span></span>
   1. <span data-ttu-id="df414-212">在使用 GPO[设置客户端设备端口范围和标记](QoS-in-Teams-clients.md)的客户端上</span><span class="sxs-lookup"><span data-stu-id="df414-212">On Clients using a GPO to [set client device port ranges and markings](QoS-in-Teams-clients.md)</span></span>
   2. <span data-ttu-id="df414-213">在路由器上（请参阅制造商文档）或其他网络设备。</span><span class="sxs-lookup"><span data-stu-id="df414-213">On routers (see the manufacturer documentation) or other network devices.</span></span> <span data-ttu-id="df414-214">这可能包括基于端口的 Acl，或者仅定义 QoS 队列和 DSCP 标记，或者所有这些操作。</span><span class="sxs-lookup"><span data-stu-id="df414-214">This may include port-based ACLs or simply defining the QoS queues and DSCP markings, or all of these.</span></span>

      > [!IMPORTANT]
      > <span data-ttu-id="df414-215">我们建议使用客户端源端口和来源和目标 IP 地址 "any" 实现这些 QoS 策略。</span><span class="sxs-lookup"><span data-stu-id="df414-215">We recommend implementing these QoS policies using the client source ports and a source and destination IP address of "any."</span></span> <span data-ttu-id="df414-216">这将在内部网络上捕获传入和传出媒体流量。</span><span class="sxs-lookup"><span data-stu-id="df414-216">This will catch both incoming and outgoing media traffic on the internal network.</span></span>  

   3. <span data-ttu-id="df414-217">在[团队管理中心](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)</span><span class="sxs-lookup"><span data-stu-id="df414-217">On [Teams Admin Center](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)</span></span>
5. <span data-ttu-id="df414-218">通过分析网络上的团队通信来[验证 QoS 实施](#validate-the-qos-implementation)。</span><span class="sxs-lookup"><span data-stu-id="df414-218">[Validate the QoS implementation](#validate-the-qos-implementation) by analyzing Teams traffic on the network.</span></span>

<span data-ttu-id="df414-219">准备实施 QoS 时，请牢记以下准则：</span><span class="sxs-lookup"><span data-stu-id="df414-219">As you prepare to implement QoS, keep the following guidelines in mind:</span></span>

- <span data-ttu-id="df414-220">最短的 Office 365 路径是最佳途径。</span><span class="sxs-lookup"><span data-stu-id="df414-220">The shortest path to Office 365 is best.</span></span>
- <span data-ttu-id="df414-221">关闭端口仅会导致质量下降。</span><span class="sxs-lookup"><span data-stu-id="df414-221">Closing ports will only lead to quality degradation.</span></span>
- <span data-ttu-id="df414-222">不建议在任何情况下（如代理）中的任何障碍物。</span><span class="sxs-lookup"><span data-stu-id="df414-222">Any obstacles in-between, such as proxies, are not recommended.</span></span>
- <span data-ttu-id="df414-223">限制跃点的数量：</span><span class="sxs-lookup"><span data-stu-id="df414-223">Limit the number of hops:</span></span>
  - <span data-ttu-id="df414-224">客户端到网络边缘-3 到5个跃点。</span><span class="sxs-lookup"><span data-stu-id="df414-224">Client to network edge – 3 to 5 hops.</span></span>
  - <span data-ttu-id="df414-225">ISP 到 Microsoft network edge –3个跃点</span><span class="sxs-lookup"><span data-stu-id="df414-225">ISP to Microsoft network edge – 3 hops</span></span>
  - <span data-ttu-id="df414-226">Microsoft 网络边缘到最终目标-不相关</span><span class="sxs-lookup"><span data-stu-id="df414-226">Microsoft network edge to final destination – irrelevant</span></span>

<span data-ttu-id="df414-227">有关配置防火墙端口的信息，请转到[Office 365 url 和 IP 范围](office-365-urls-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="df414-227">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

## <a name="managing-source-ports-in-the-teams-admin-center"></a><span data-ttu-id="df414-228">管理团队管理中心中的源端口</span><span class="sxs-lookup"><span data-stu-id="df414-228">Managing source ports in the Teams admin center</span></span>

<span data-ttu-id="df414-229">在团队中，不同工作负荷使用的 QoS 源端口应处于主动管理状态，并根据需要进行调整。</span><span class="sxs-lookup"><span data-stu-id="df414-229">In Teams, QoS source ports used by the different workloads should be actively managed, and adjusted as necessary.</span></span> <span data-ttu-id="df414-230">在[选择每个媒体类型的初始端口范围](#choose-initial-port-ranges-for-each-media-type)中引用表，可调整端口范围，但无法配置 DSCP 标记。</span><span class="sxs-lookup"><span data-stu-id="df414-230">Referring to the table in [Choose initial port ranges for each media type](#choose-initial-port-ranges-for-each-media-type), the port ranges are adjustable, but the DSCP markings are not configurable.</span></span> <span data-ttu-id="df414-231">实现这些设置后，你可能会发现给定媒体类型需要更多或更少的端口。</span><span class="sxs-lookup"><span data-stu-id="df414-231">Once you have implemented these settings, you may find that more or fewer ports are needed for a given media type.</span></span> <span data-ttu-id="df414-232">应使用 "[呼叫分析" 和 "呼叫质量" 仪表板](difference-between-call-analytics-and-call-quality-dashboard.md)决定在团队实施后调整端口范围，并根据需要定期进行更改。</span><span class="sxs-lookup"><span data-stu-id="df414-232">[Call Analytics and Call Quality Dashboard](difference-between-call-analytics-and-call-quality-dashboard.md) should be used in making a decision to adjust port ranges after Teams has been implemented, and periodically as needs change.</span></span>

> [!NOTE]
> <span data-ttu-id="df414-233">如果你已基于 Skype for business Online 的源端口范围和 DSCP 标记配置了 QoS，则同一配置将应用到团队，并且不需要进一步的客户端或网络更改，但你可能需要[设置团队管理中心中使用的范围](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)，以匹配为 Skype For business Online 配置的内容。</span><span class="sxs-lookup"><span data-stu-id="df414-233">If you've already configured QoS based on source port ranges and DSCP markings for Skype for Business Online, the same configuration will apply to Teams and no further client or network changes to the mapping will be required, though you may have to [set the ranges used in Teams Admin Center](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) to match what was configured for Skype for Business Online.</span></span>

<span data-ttu-id="df414-234">如果你以前已部署了本地 Skype for business 服务器，你可能需要重新检查 QoS 策略并根据需要进行调整，以便与你已验证的端口范围设置相匹配，从而为团队提供了高质量的用户体验。</span><span class="sxs-lookup"><span data-stu-id="df414-234">If you've previously deployed Skype for Business Server on-premises, you may need to re-examine your QoS policies and adjust them as needed to match port range settings you've verified provide a quality user experience for Teams.</span></span>

## <a name="validate-the-qos-implementation"></a><span data-ttu-id="df414-235">验证 QoS 实施</span><span class="sxs-lookup"><span data-stu-id="df414-235">Validate the QoS implementation</span></span>

<span data-ttu-id="df414-236">为了使 QoS 有效，组策略对象设置的 DSCP 值需要存在于调用的两端。</span><span class="sxs-lookup"><span data-stu-id="df414-236">For QoS to be effective, the DSCP value set by the Group Policy object needs to be present at both ends of a call.</span></span> <span data-ttu-id="df414-237">通过分析由团队客户端生成的流量，你可以验证当团队工作负载流量遍历网络时，DSCP 值不会更改或去除。</span><span class="sxs-lookup"><span data-stu-id="df414-237">By analyzing the traffic generated by the Teams client, you can verify that the DSCP value isn't changed or stripped out when the Teams workload traffic traverses moves through the network.</span></span>

<span data-ttu-id="df414-238">最好是在网络出口点处捕获流量。</span><span class="sxs-lookup"><span data-stu-id="df414-238">Preferably, you capture traffic at the network egress point.</span></span> <span data-ttu-id="df414-239">可以在交换机或路由器上使用端口镜像来帮助解决此情况。</span><span class="sxs-lookup"><span data-stu-id="df414-239">You can use port mirroring on a switch or router to help with this.</span></span>

### <a name="use-network-monitor-to-verify-dscp-values"></a><span data-ttu-id="df414-240">使用网络监视器验证 DSCP 值</span><span class="sxs-lookup"><span data-stu-id="df414-240">Use Network Monitor to verify DSCP values</span></span>

<span data-ttu-id="df414-241">网络监视器是可以[从 Microsoft 下载](https://www.microsoft.com/download/4865)以分析网络流量的工具。</span><span class="sxs-lookup"><span data-stu-id="df414-241">Network Monitor is a tool you can [download from Microsoft](https://www.microsoft.com/download/4865) to analyze network traffic.</span></span>

1. <span data-ttu-id="df414-242">在运行网络监视器的电脑上，连接到已为端口镜像配置的端口并开始捕获数据包。</span><span class="sxs-lookup"><span data-stu-id="df414-242">On the PC running Network Monitor, connect to the port that has been configured for port mirroring and start capturing packets.</span></span>

2. <span data-ttu-id="df414-243">使用团队客户端进行呼叫。</span><span class="sxs-lookup"><span data-stu-id="df414-243">Make a call by using the Teams client.</span></span> <span data-ttu-id="df414-244">在挂断呼叫之前，请确保已建立媒体。</span><span class="sxs-lookup"><span data-stu-id="df414-244">Make sure media has been established before hanging up the call.</span></span>

3. <span data-ttu-id="df414-245">停止捕获。</span><span class="sxs-lookup"><span data-stu-id="df414-245">Stop the capture.</span></span>

4. <span data-ttu-id="df414-246">在 "**显示筛选器**" 字段中，使用发出呼叫的 PC 的源 IP 地址，并通过将 DSCP 值46（十六进制0x2E）定义为搜索条件来优化筛选器，如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="df414-246">In the **Display Filter** field, use the source IP address of the PC that made the call, and refine the filter by defining DSCP value 46 (hex 0x2E) as search criteria, as shown in the following example:</span></span>

    <span data-ttu-id="df414-247">Source = = "192.168.137.201" 和 DifferentiatedServicesField = = 0x2E</span><span class="sxs-lookup"><span data-stu-id="df414-247">Source == "192.168.137.201" AND IPv4.DifferentiatedServicesField == 0x2E</span></span>

    <span data-ttu-id="df414-248">!["显示筛选器" 对话框中的屏幕截图筛选器。](media/Qos-in-Teams-Image4.png "网络监视器中的 "显示筛选" 对话框，显示要应用的筛选器。")</span><span class="sxs-lookup"><span data-stu-id="df414-248">![Screenshot filters in the Display Filter dialog box.](media/Qos-in-Teams-Image4.png "The Display Filter dialog box in Network Monitor, showing the filters to apply.")</span></span>

5. <span data-ttu-id="df414-249">选择 "**应用**" 以激活筛选器。</span><span class="sxs-lookup"><span data-stu-id="df414-249">Select **Apply** to activate the filter.</span></span>

6. <span data-ttu-id="df414-250">在 "**帧摘要**" 窗口中，选择第一个 UDP 数据包。</span><span class="sxs-lookup"><span data-stu-id="df414-250">In the **Frame Summary** window, select the first UDP packet.</span></span>

7. <span data-ttu-id="df414-251">在 "**帧详细信息**" 窗口中，展开 "IPv4 列表" 项，并记下以**DSCP**开头的行末尾的值。</span><span class="sxs-lookup"><span data-stu-id="df414-251">In the **Frame Details** window, expand the IPv4 list item and note the value at the end of the line that begins with **DSCP**.</span></span>

    <span data-ttu-id="df414-252">![显示 "帧详细信息" 对话框中的 DSCP 设置的屏幕截图。](media/Qos-in-Teams-Image5.png "网络监视器中的 "帧详细信息" 对话框，突出显示 "DSCP 设置"。")</span><span class="sxs-lookup"><span data-stu-id="df414-252">![Screenshot showing DSCP settings in the Frame Details dialog box.](media/Qos-in-Teams-Image5.png "The Frame Details dialog box in Network Monitor, highlighting DSCP settings.")</span></span>

<span data-ttu-id="df414-253">在此示例中，DSCP 值设置为46。</span><span class="sxs-lookup"><span data-stu-id="df414-253">In this example, the DSCP value is set to 46.</span></span> <span data-ttu-id="df414-254">这是正确的，因为使用的源端口是50019，表示这是一个语音工作负荷。</span><span class="sxs-lookup"><span data-stu-id="df414-254">This is correct, because the source port used is 50019, which indicates that this is a voice workload.</span></span>

<span data-ttu-id="df414-255">为 GPO 标记的每个工作负荷重复执行验证。</span><span class="sxs-lookup"><span data-stu-id="df414-255">Repeat the verification for each workload that has been marked by the GPO.</span></span>

## <a name="more-information"></a><span data-ttu-id="df414-256">更多信息</span><span class="sxs-lookup"><span data-stu-id="df414-256">More information</span></span>

[<span data-ttu-id="df414-257">视频：网络规划</span><span class="sxs-lookup"><span data-stu-id="df414-257">Video: Network Planning</span></span>](https://aka.ms/teams-networking)

[<span data-ttu-id="df414-258">为 Microsoft Teams 准备组织的网络</span><span class="sxs-lookup"><span data-stu-id="df414-258">Prepare your organization's network for Microsoft Teams</span></span>](prepare-network.md)

[<span data-ttu-id="df414-259">ExpressRoute QoS 要求</span><span class="sxs-lookup"><span data-stu-id="df414-259">ExpressRoute QoS requirements</span></span>](https://docs.microsoft.com/azure/expressroute/expressroute-qos)
