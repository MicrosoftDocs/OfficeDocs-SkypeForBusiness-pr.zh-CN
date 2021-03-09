---
title: 在 Microsoft Teams 中实施服务质量
author: SerdarSoysal
ms.author: serdars
manager: Serdars
ms.topic: article
ms.service: msteams
ms.reviewer: vkorlep, siunies
audience: admin
description: 了解如何在 Microsoft Teams 中准备组织的服务质量网络 (QoS) 服务。
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
ms.openlocfilehash: c07e3e71d391123d34ae64ebf5806c090c29a29d
ms.sourcegitcommit: e29e38bf00536400e5826fc55bc86dfd6ed761f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2021
ms.locfileid: "50558201"
---
# <a name="implement-quality-of-service-qos-in-microsoft-teams"></a><span data-ttu-id="c1eac-103">在 Microsoft Teams 中 (QoS) 服务质量</span><span class="sxs-lookup"><span data-stu-id="c1eac-103">Implement Quality of Service (QoS) in Microsoft Teams</span></span>

<span data-ttu-id="c1eac-104">Microsoft Teams 中的服务质量 (QoS) 允许对网络延迟敏感的实时网络流量 (例如，语音或视频流) 在不太敏感的 (例如下载新应用（其中额外下载秒数不是大交易) ）前"排成一线"。</span><span class="sxs-lookup"><span data-stu-id="c1eac-104">Quality of Service (QoS) in Microsoft Teams allows real-time network traffic that's sensitive to network delays (for example, voice or video streams) to "cut in line" in front of traffic that's less sensitive (like downloading a new app, where an extra second to download isn't a large deal).</span></span> <span data-ttu-id="c1eac-105">QoS 使用 Windows 组策略对象和基于端口的访问控制列表来识别并标记实时流中的所有数据包。</span><span class="sxs-lookup"><span data-stu-id="c1eac-105">QoS uses Windows Group Policy Objects and Port-based Access Control Lists to identify and mark all packets in real-time streams.</span></span> <span data-ttu-id="c1eac-106">这有助于网络为语音、视频和屏幕共享流提供专用网络带宽部分。</span><span class="sxs-lookup"><span data-stu-id="c1eac-106">This helps your network to give voice, video, and screen share streams a dedicated portion of network bandwidth.</span></span>

<span data-ttu-id="c1eac-107">如果你支持大量遇到本文所述任何问题的用户，则你可能需要实现 QoS。</span><span class="sxs-lookup"><span data-stu-id="c1eac-107">If you support a large group of users who are experiencing any of the problems described in this article, then you probably need to implement QoS.</span></span> <span data-ttu-id="c1eac-108">用户数很少的小型企业可能不需要 QoS，但即使存在，它也应该很有用。</span><span class="sxs-lookup"><span data-stu-id="c1eac-108">A small business with few users might not need QoS, but even there it should be helpful.</span></span>

<span data-ttu-id="c1eac-109">如果没有某种形式的 QoS，你可能会在语音和视频中看到以下质量问题：</span><span class="sxs-lookup"><span data-stu-id="c1eac-109">Without some form of QoS, you might see the following quality issues in voice and video:</span></span>

- <span data-ttu-id="c1eac-110">抖动 - 以不同速率到达的媒体数据包，这可能会导致通话中缺少字词或音节</span><span class="sxs-lookup"><span data-stu-id="c1eac-110">Jitter – media packets arriving at different rates, which can result in missing words or syllables in calls</span></span>
- <span data-ttu-id="c1eac-111">数据包丢失 - 数据包被丢弃，这还可能导致语音质量降低且难以理解语音</span><span class="sxs-lookup"><span data-stu-id="c1eac-111">Packet loss – packets dropped, which can also result in lower voice quality and hard to understand speech</span></span>
- <span data-ttu-id="c1eac-112">RTT (延迟的往返) – 媒体数据包到达其目的地需要很长时间，导致对话中双方之间的明显延迟，导致人们相互交谈</span><span class="sxs-lookup"><span data-stu-id="c1eac-112">Delayed round-trip time (RTT) – media packets taking a long time to reach their destinations, which result in noticeable delays between two parties in a conversation and causes people to talk over each other</span></span>

<span data-ttu-id="c1eac-113">解决这些问题最不复杂的方法就是增加内部和外部到 Internet 的数据连接的大小。</span><span class="sxs-lookup"><span data-stu-id="c1eac-113">The least complex way to address these issues is to increase the size of the data connections, both internally and out to the internet.</span></span> <span data-ttu-id="c1eac-114">由于这通常成本过高，QoS 提供了一种更有效地管理资源的方法，而不是添加带宽。</span><span class="sxs-lookup"><span data-stu-id="c1eac-114">Since that is often cost-prohibitive, QoS provides a way to more effectively manage the resources you have instead of adding bandwidth.</span></span> <span data-ttu-id="c1eac-115">若要解决质量问题，建议首先使用 QoS，然后仅在必要时添加带宽。</span><span class="sxs-lookup"><span data-stu-id="c1eac-115">To address quality issues, we recommend that you first use QoS, then add bandwidth only where necessary.</span></span>

<span data-ttu-id="c1eac-116">若要使 QoS 有效，必须在整个组织中应用一致的 QoS 设置。</span><span class="sxs-lookup"><span data-stu-id="c1eac-116">For QoS to be effective, you must apply consistent QoS settings throughout your organization.</span></span> <span data-ttu-id="c1eac-117">无法支持 QoS 优先级的路径的任何部分都可能会降低通话、视频和屏幕共享的质量。</span><span class="sxs-lookup"><span data-stu-id="c1eac-117">Any part of the path that fails to support your QoS priorities can degrade the quality of calls, video, and screen sharing.</span></span> <span data-ttu-id="c1eac-118">这包括将设置应用到每个用户电脑或设备、网络交换机、路由器到 Internet 和 Teams 服务。</span><span class="sxs-lookup"><span data-stu-id="c1eac-118">This includes applying settings to all user PCs or devices, network switches, routers to the internet, and the Teams service.</span></span>

<span data-ttu-id="c1eac-119">_图 1.组织网络与 Microsoft 365 或 Office 365 服务之间的关系_</span><span class="sxs-lookup"><span data-stu-id="c1eac-119">_Figure 1. The relationship between an organization's networks and Microsoft 365 or Office 365 services_</span></span>

<span data-ttu-id="c1eac-120">![网络与服务之间的关系图示](media/Qos-in-Teams-Image1.png "组织网络与 Microsoft 365 或 Office 365 服务之间的关系：本地网络和设备通过互连网络进行连接，而互连网络又连接到 Microsoft 365 或 Office 365 云语音和音频会议服务。")</span><span class="sxs-lookup"><span data-stu-id="c1eac-120">![Illustration of the relationship between networks and services](media/Qos-in-Teams-Image1.png "The relationship between an organization's networks and Microsoft 365 or Office 365 services: on-premises network and devices connect with an interconnect network, which in turn connects with Microsoft 365 or Office 365 Cloud Voice and Audio Conferencing services.")</span></span>

## <a name="qos-implementation-checklist"></a><span data-ttu-id="c1eac-121">QoS 实现清单</span><span class="sxs-lookup"><span data-stu-id="c1eac-121">QoS implementation checklist</span></span>

<span data-ttu-id="c1eac-122">在高级别上，执行下列操作来实现 QoS：</span><span class="sxs-lookup"><span data-stu-id="c1eac-122">At a high level, do the following to implement QoS:</span></span>

1. <span data-ttu-id="c1eac-123">[请确保网络已准备就绪](#make-sure-your-network-is-ready)。</span><span class="sxs-lookup"><span data-stu-id="c1eac-123">[Make sure your network is ready](#make-sure-your-network-is-ready).</span></span>

1. <span data-ttu-id="c1eac-124">[选择 QoS 实现方法](#select-a-qos-implementation-method)。</span><span class="sxs-lookup"><span data-stu-id="c1eac-124">[Select a QoS implementation method](#select-a-qos-implementation-method).</span></span>

1. <span data-ttu-id="c1eac-125">[选择每种媒体类型的初始端口范围](#choose-initial-port-ranges-for-each-media-type)。</span><span class="sxs-lookup"><span data-stu-id="c1eac-125">[Choose initial port ranges for each media type](#choose-initial-port-ranges-for-each-media-type).</span></span>

1. <span data-ttu-id="c1eac-126">实现 QoS 设置：</span><span class="sxs-lookup"><span data-stu-id="c1eac-126">Implement QoS settings:</span></span>
   1. <span data-ttu-id="c1eac-127">在使用组策略对象的客户端上 (GPO) [设置客户端设备端口范围和标记](QoS-in-Teams-clients.md)。</span><span class="sxs-lookup"><span data-stu-id="c1eac-127">On clients using a Group Policy Object (GPO) to [set client device port ranges and markings](QoS-in-Teams-clients.md).</span></span>
   2. <span data-ttu-id="c1eac-128">在路由器 (请参阅制造商文档) 或其他网络设备。</span><span class="sxs-lookup"><span data-stu-id="c1eac-128">On routers (see the manufacturer documentation) or other network devices.</span></span> <span data-ttu-id="c1eac-129">这可能包括基于端口的访问控制列表 (ACL) 定义 QoS 队列和 DSCP 标记，或者所有这些。</span><span class="sxs-lookup"><span data-stu-id="c1eac-129">This might include port-based Access Control Lists (ACLs) or simply defining the QoS queues and DSCP markings, or all of these.</span></span>

      > [!IMPORTANT]
      > <span data-ttu-id="c1eac-130">我们建议使用客户端源端口以及"任何"的源和目标 IP 地址实现这些 QoS 策略。</span><span class="sxs-lookup"><span data-stu-id="c1eac-130">We recommend implementing these QoS policies using the client source ports and a source and destination IP address of “any.”</span></span> <span data-ttu-id="c1eac-131">这将捕获内部网络上传入和传出的媒体流量。</span><span class="sxs-lookup"><span data-stu-id="c1eac-131">This will catch both incoming and outgoing media traffic on the internal network.</span></span>  

   3. <span data-ttu-id="c1eac-132">[设置如何处理 Teams 会议的媒体流量](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)。</span><span class="sxs-lookup"><span data-stu-id="c1eac-132">[Set how you want to handle media traffic for Teams meetings](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings).</span></span>

5. <span data-ttu-id="c1eac-133">[通过分析网络上 Teams](#validate-your-qos-implementation) 流量来验证 QoS 实现。</span><span class="sxs-lookup"><span data-stu-id="c1eac-133">[Validate your QoS implementation](#validate-your-qos-implementation) by analyzing Teams traffic on the network.</span></span>

<span data-ttu-id="c1eac-134">准备实施 QoS 时，请记住以下准则：</span><span class="sxs-lookup"><span data-stu-id="c1eac-134">As you prepare to implement QoS, keep the following guidelines in mind:</span></span>

- <span data-ttu-id="c1eac-135">Microsoft 365 的最短路径最佳。</span><span class="sxs-lookup"><span data-stu-id="c1eac-135">The shortest path to Microsoft 365 is best.</span></span>
- <span data-ttu-id="c1eac-136">关闭端口只会导致质量下降。</span><span class="sxs-lookup"><span data-stu-id="c1eac-136">Closing ports will only lead to quality degradation.</span></span>
- <span data-ttu-id="c1eac-137">不建议在两者之间设置任何障碍，例如代理。</span><span class="sxs-lookup"><span data-stu-id="c1eac-137">Any obstacles in between, such as proxies, aren't recommended.</span></span>
- <span data-ttu-id="c1eac-138">限制跃点数：</span><span class="sxs-lookup"><span data-stu-id="c1eac-138">Limit the number of hops:</span></span>
  - <span data-ttu-id="c1eac-139">客户端到网络边缘 – 3 到 5 个跃点</span><span class="sxs-lookup"><span data-stu-id="c1eac-139">Client to network edge – 3 to 5 hops</span></span>
  - <span data-ttu-id="c1eac-140">ISP 到 Microsoft 网络边缘 - 3 个跃点</span><span class="sxs-lookup"><span data-stu-id="c1eac-140">ISP to Microsoft network edge – 3 hops</span></span>
  - <span data-ttu-id="c1eac-141">Microsoft 网络边缘到最终目标 – 不相关</span><span class="sxs-lookup"><span data-stu-id="c1eac-141">Microsoft network edge to final destination – irrelevant</span></span>

<span data-ttu-id="c1eac-142">有关配置防火墙端口的信息，请转到 Office [365 URL 和 IP 范围](office-365-urls-ip-address-ranges.md)。</span><span class="sxs-lookup"><span data-stu-id="c1eac-142">For information about configuring firewall ports, go to [Office 365 URLs and IP ranges](office-365-urls-ip-address-ranges.md).</span></span>

## <a name="make-sure-your-network-is-ready"></a><span data-ttu-id="c1eac-143">确保网络已准备就绪</span><span class="sxs-lookup"><span data-stu-id="c1eac-143">Make sure your network is ready</span></span>

<span data-ttu-id="c1eac-144">如果你正在考虑 QoS 实现，你应该已经确定了你的带宽要求和其他 [网络要求](prepare-network.md)。</span><span class="sxs-lookup"><span data-stu-id="c1eac-144">If you're considering a QoS implementation, you should already have determined your bandwidth requirements and other [network requirements](prepare-network.md).</span></span>
  
<span data-ttu-id="c1eac-145">整个网络的流量拥塞将极大地影响媒体质量。</span><span class="sxs-lookup"><span data-stu-id="c1eac-145">Traffic congestion across a network will greatly impact media quality.</span></span> <span data-ttu-id="c1eac-146">缺少带宽会导致性能下降和用户体验不佳。</span><span class="sxs-lookup"><span data-stu-id="c1eac-146">A lack of bandwidth leads to performance degradation and a poor user experience.</span></span> <span data-ttu-id="c1eac-147">随着 Teams 采用和使用量的增长，使用报告[](use-call-analytics-to-troubleshoot-poor-call-quality.md)、每用户呼叫分析和呼叫质量仪表板[ (CQD) ](turning-on-and-using-call-quality-dashboard.md)来识别问题，然后使用 QoS 和选择性带宽添加进行调整。</span><span class="sxs-lookup"><span data-stu-id="c1eac-147">As Teams adoption and usage grows, use reporting, [per-user call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md), and [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) to identify problems and then make adjustments using QoS and selective bandwidth additions.</span></span>

### <a name="vpn-considerations"></a><span data-ttu-id="c1eac-148">VPN 注意事项</span><span class="sxs-lookup"><span data-stu-id="c1eac-148">VPN considerations</span></span>

<span data-ttu-id="c1eac-149">QoS 仅在调用方之间的所有链接上实现时，才正常工作。</span><span class="sxs-lookup"><span data-stu-id="c1eac-149">QoS only works as expected when implemented on all links between callers.</span></span> <span data-ttu-id="c1eac-150">如果在内部网络上使用 QoS，并且用户从远程位置登录，则只能在内部托管网络中设置优先级。</span><span class="sxs-lookup"><span data-stu-id="c1eac-150">If you use QoS on an internal network and a user signs in from a remote location, you can only prioritize within your internal, managed network.</span></span> <span data-ttu-id="c1eac-151">尽管远程位置可以通过实现虚拟专用网络 (VPN) 来接收托管连接，但 VPN 本质上会增加数据包开销，并造成实时流量的延迟。</span><span class="sxs-lookup"><span data-stu-id="c1eac-151">Although remote locations can receive a managed connection by implementing a virtual private network (VPN),  a VPN inherently adds packet overhead and creates delays in real-time traffic.</span></span> <span data-ttu-id="c1eac-152">建议避免通过 VPN 运行实时通信流量。</span><span class="sxs-lookup"><span data-stu-id="c1eac-152">We  recommend that you avoid running real-time communications traffic over a VPN.</span></span>

<span data-ttu-id="c1eac-153">在具有跨大洲的托管链接的全球组织中，我们强烈建议使用 QoS，因为这些链接的带宽与 LAN 相比有限制。</span><span class="sxs-lookup"><span data-stu-id="c1eac-153">In a global organization with managed links that span continents, we strongly recommend QoS because bandwidth for those links is limited in comparison to the LAN.</span></span>

## <a name="introduction-to-qos-queues"></a><span data-ttu-id="c1eac-154">QoS 队列简介</span><span class="sxs-lookup"><span data-stu-id="c1eac-154">Introduction to QoS queues</span></span>

<span data-ttu-id="c1eac-155">若要提供 QoS，网络设备必须具有对流量进行分类的方法，并且必须能够区分语音或视频与其他网络流量。</span><span class="sxs-lookup"><span data-stu-id="c1eac-155">To provide QoS, network devices must have a way to classify traffic and must be able to distinguish voice or video from other network traffic.</span></span>

<span data-ttu-id="c1eac-156">当网络流量进入路由器时，流量将放入队列。</span><span class="sxs-lookup"><span data-stu-id="c1eac-156">When network traffic enters a router, the traffic is placed into a queue.</span></span> <span data-ttu-id="c1eac-157">如果未配置 QoS 策略，则只有一个队列，所有数据都被视为优先级相同的先入先出。</span><span class="sxs-lookup"><span data-stu-id="c1eac-157">If a QoS policy isn't configured, there is only one queue, and all data is treated as first-in, first-out with the same priority.</span></span> <span data-ttu-id="c1eac-158">这意味着语音流量 (对延迟非常敏感) 可能会卡在流量后面，如果延迟额外几毫秒不会是问题。</span><span class="sxs-lookup"><span data-stu-id="c1eac-158">That means voice traffic (which is very sensitive to delays) might get stuck behind traffic where a delay of a few extra milliseconds wouldn't be a problem.</span></span>

<span data-ttu-id="c1eac-159">实现 QoS 时，使用多种拥塞管理功能之一定义多个队列，例如 Cisco 的优先级队列和基于类的加权公平队列[ (CBWFQ) ](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641)和拥塞规避功能，例如加权随机早期检测[ (WRED) 。 ](https://en.wikipedia.org/wiki/Weighted_random_early_detection)</span><span class="sxs-lookup"><span data-stu-id="c1eac-159">When you implement QoS, you define multiple queues using one of several congestion management features, such as Cisco’s priority queuing and [Class-Based Weighted Fair Queueing (CBWFQ)](https://www.cisco.com/en/US/docs/ios/12_0t/12_0t5/feature/guide/cbwfq.html#wp17641) and congestion avoidance features, such as [weighted random early detection (WRED)](https://en.wikipedia.org/wiki/Weighted_random_early_detection).</span></span>

<span data-ttu-id="c1eac-160">_图 2.QoS 队列的示例_</span><span class="sxs-lookup"><span data-stu-id="c1eac-160">_Figure 2. Examples of QoS queues_</span></span>

<span data-ttu-id="c1eac-161">![QoS 队列和带宽划分图示](media/Qos-in-Teams-Image2.png "总可用带宽在分配了不同优先级的多个队列（音频、视频和其他流量）之间划分。")</span><span class="sxs-lookup"><span data-stu-id="c1eac-161">![Illustration of QoS queues and bandwidth division](media/Qos-in-Teams-Image2.png "Total available bandwidth is divided among multiple queues—audio, video, and other traffic—that have been assigned different priorities.")</span></span>

<span data-ttu-id="c1eac-162">一个简单的类比是 QoS 在数据网络中创建虚拟"拼车通道"，以便某些类型的数据永远不会或很少遇到延迟。</span><span class="sxs-lookup"><span data-stu-id="c1eac-162">A simple analogy is that QoS creates virtual "carpool lanes" in your data network so some types of data never or rarely encounter a delay.</span></span> <span data-ttu-id="c1eac-163">创建这些通道后，可以调整其相对大小并更有效地管理你拥有的连接带宽，同时仍为组织的用户提供企业级体验。</span><span class="sxs-lookup"><span data-stu-id="c1eac-163">Once you create those lanes, you can adjust their relative size and much more effectively manage the connection bandwidth you have, while still delivering business-grade experiences for your organization's users.</span></span>

## <a name="select-a-qos-implementation-method"></a><span data-ttu-id="c1eac-164">选择 QoS 实现方法</span><span class="sxs-lookup"><span data-stu-id="c1eac-164">Select a QoS implementation method</span></span>

<span data-ttu-id="c1eac-165">可以通过基于端口的标记实现 QoS，使用访问控制列表 (网络) 上的 ACL。</span><span class="sxs-lookup"><span data-stu-id="c1eac-165">You could implement QoS via port-based tagging, using Access Control Lists (ACLs) on your network's routers.</span></span> <span data-ttu-id="c1eac-166">基于端口的标记是最可靠的方法，因为它适用于 Windows、Mac 和 Linux 混合环境，并且最容易实现。</span><span class="sxs-lookup"><span data-stu-id="c1eac-166">Port-based tagging is the most reliable method because it works in mixed Windows, Mac, and Linux environments and is the easiest to implement.</span></span> <span data-ttu-id="c1eac-167">移动客户端不提供使用 DSCP 值标记流量的机制，因此需要此方法。</span><span class="sxs-lookup"><span data-stu-id="c1eac-167">Mobile clients don't provide a mechanism to mark traffic by using DSCP values, so they'll require this method.</span></span>  

<span data-ttu-id="c1eac-168">使用基于端口的标记，网络的路由器会检查传入数据包，如果数据包是使用特定端口或端口范围到达的，它会将其标识为特定媒体类型，并置于该类型的队列中，向 IP 数据包标头添加预先确定的 [DSCP](https://tools.ietf.org/html/rfc2474) 标记，以便其他设备可以识别其流量类型，并在其队列中赋予其优先级。</span><span class="sxs-lookup"><span data-stu-id="c1eac-168">Using port-based tagging, your network's router examines an incoming packet, and if the packet arrived using a certain port or range of ports, it identifies it as a certain media type and puts it in the queue for that type, adding a predetermined [DSCP](https://tools.ietf.org/html/rfc2474) mark to the IP Packet header so other devices can recognize its traffic type and give it priority in their queue.</span></span>

<span data-ttu-id="c1eac-169">尽管基于端口的标记可以跨平台工作，但它只会标记 WAN 边缘 (到客户端计算机的流量，) 产生管理开销。</span><span class="sxs-lookup"><span data-stu-id="c1eac-169">Although port-based tagging works across platforms, it only marks traffic at the WAN edge (not all the way to the client machine) and creates management overhead.</span></span> <span data-ttu-id="c1eac-170">有关实现此方法的说明，请参阅路由器制造商提供的文档。</span><span class="sxs-lookup"><span data-stu-id="c1eac-170">Refer to the documentation provided by the router manufacturer for instructions on implementing this method.</span></span>

### <a name="insert-dscp-markers"></a><span data-ttu-id="c1eac-171">插入 DSCP 标记</span><span class="sxs-lookup"><span data-stu-id="c1eac-171">Insert DSCP markers</span></span>

<span data-ttu-id="c1eac-172">您也可以通过使用组策略对象 (GPO) 来指示客户端设备在 IP 数据包标头中插入 DSCP 标记，以将其标识为特定的流量类型 (例如语音) 。</span><span class="sxs-lookup"><span data-stu-id="c1eac-172">You could also implement QoS by using a Group Policy Object (GPO) to direct client devices to insert a DSCP marker in IP packet headers identifying it as particular type of traffic (for example, voice).</span></span> <span data-ttu-id="c1eac-173">可以将路由器和其他网络设备配置为识别这一点，将流量放在一个单独的更高优先级的队列中。</span><span class="sxs-lookup"><span data-stu-id="c1eac-173">Routers and other network devices can be configured to recognize this and put the traffic in a separate, higher-priority queue.</span></span>

<span data-ttu-id="c1eac-174">尽管此方案完全有效，但它仅适用于已加入域的 Windows 客户端。</span><span class="sxs-lookup"><span data-stu-id="c1eac-174">Although this scenario is entirely valid, it will only work for domain-joined Windows clients.</span></span> <span data-ttu-id="c1eac-175">任何未加入域的 Windows 客户端的设备将不会启用 DSCP 标记。</span><span class="sxs-lookup"><span data-stu-id="c1eac-175">Any device that isn't a domain-joined Windows client won't be enabled for DSCP tagging.</span></span> <span data-ttu-id="c1eac-176">其他客户端（例如运行 macOS 的客户端）具有硬编码的标记，并且始终标记流量。</span><span class="sxs-lookup"><span data-stu-id="c1eac-176">Other clients, such as those running macOS, have hard-coded tags and will always tag traffic.</span></span>

<span data-ttu-id="c1eac-177">另外，通过 GPO 控制 DSCP 标记可确保所有已加入域的计算机接收相同的设置，并且只有管理员可以管理这些设置。</span><span class="sxs-lookup"><span data-stu-id="c1eac-177">On the plus side, controlling the DSCP marking via GPO ensures that all domain-joined computers receive the same settings and that only an administrator can manage them.</span></span> <span data-ttu-id="c1eac-178">可以使用 GPO 的客户端将在发起设备上进行标记，然后配置的网络设备可以通过 DSCP 代码识别实时流，并赋予其适当的优先级。</span><span class="sxs-lookup"><span data-stu-id="c1eac-178">Clients that can use GPO will be tagged on the originating device, and then configured network devices can recognize the real-time stream by the DSCP code and give it an appropriate priority.</span></span>

### <a name="best-practice"></a><span data-ttu-id="c1eac-179">最佳做法</span><span class="sxs-lookup"><span data-stu-id="c1eac-179">Best practice</span></span>

<span data-ttu-id="c1eac-180">如果可能，建议将终结点上的 DSCP 标记与路由器上基于端口的 ACL 组合使用。</span><span class="sxs-lookup"><span data-stu-id="c1eac-180">We recommend a combination of DSCP markings at the endpoint and port-based ACLs on routers, if possible.</span></span> <span data-ttu-id="c1eac-181">使用 GPO 捕获大部分客户端，同时使用基于端口的 DSCP 标记将确保移动、Mac 和其他客户端仍将获得 QoS 处理 (至少部分) 。</span><span class="sxs-lookup"><span data-stu-id="c1eac-181">Using a GPO to catch the majority of clients, and also using port-based DSCP tagging will ensure that mobile, Mac, and other clients will still get QoS treatment (at least partially).</span></span>

<span data-ttu-id="c1eac-182">DSCP 标记可以比作邮政戳记，向邮政工作者指示送达的紧急度以及如何以最佳方式对邮件进行排序以加快交付速度。</span><span class="sxs-lookup"><span data-stu-id="c1eac-182">DSCP markings can be likened to postage stamps that indicate to postal workers how urgent the delivery is and how best to sort it for speedy delivery.</span></span> <span data-ttu-id="c1eac-183">将网络配置为优先处理实时媒体流后，丢失的数据包和延迟的数据包会大大减少。</span><span class="sxs-lookup"><span data-stu-id="c1eac-183">Once you've configured your network to give priority to real-time media streams, lost packets and late packets should diminish greatly.</span></span>

<span data-ttu-id="c1eac-184">一旦网络内的所有设备都使用相同的分类、标记和优先级，则通过更改分配给每个流量类型的队列的端口范围的大小，可以减少或消除延迟、丢弃的数据包和抖动。</span><span class="sxs-lookup"><span data-stu-id="c1eac-184">Once all devices in the network are using the same classifications, markings, and priorities, it's possible to reduce or eliminate delays, dropped packets, and jitter by changing the size of the port ranges assigned to the queues used for each traffic type.</span></span> <span data-ttu-id="c1eac-185">从 Teams 的角度来看，最重要的配置步骤是数据包的分类和标记。</span><span class="sxs-lookup"><span data-stu-id="c1eac-185">From the Teams perspective, the most important configuration step is the classification and marking of packets.</span></span> <span data-ttu-id="c1eac-186">但是，若要使端到端 QoS 成功，还需要仔细将应用程序的配置与基础网络配置保持一致。</span><span class="sxs-lookup"><span data-stu-id="c1eac-186">However, for end-to-end QoS to be successful, you also need to carefully align the application's configuration with the underlying network configuration.</span></span> <span data-ttu-id="c1eac-187">完全实现 QoS 后，持续管理就是根据组织的需求和实际使用情况调整分配给每种流量类型的端口范围的问题。</span><span class="sxs-lookup"><span data-stu-id="c1eac-187">Once QoS is fully implemented, ongoing management is a question of adjusting the port ranges assigned to each traffic type based on your organization's needs and actual usage.</span></span>

## <a name="choose-initial-port-ranges-for-each-media-type"></a><span data-ttu-id="c1eac-188">选择每种媒体类型的初始端口范围</span><span class="sxs-lookup"><span data-stu-id="c1eac-188">Choose initial port ranges for each media type</span></span>

<span data-ttu-id="c1eac-189">DSCP 值告知相应配置的网络提供数据包或流的优先级，无论 DSCP 标记是由客户端分配还是网络本身基于 ACL 设置分配。</span><span class="sxs-lookup"><span data-stu-id="c1eac-189">The DSCP value tells a correspondingly configured network what priority to give a packet or stream, whether the DSCP mark is assigned by clients or the network itself based on ACL settings.</span></span> <span data-ttu-id="c1eac-190">每个媒体工作负荷获取自己的唯一 DSCP 值 (其他服务可能允许工作负荷共享 DSCP 标记，Teams 不会) 以及用于每种媒体类型的已定义和单独端口范围。</span><span class="sxs-lookup"><span data-stu-id="c1eac-190">Each media workload gets its own unique DSCP value (other services might allow workloads to share a DSCP marking, Teams doesn't) and a defined and separate port range used for each media type.</span></span> <span data-ttu-id="c1eac-191">其他环境可能有现有的 QoS 策略，可帮助确定网络工作负荷的优先级。</span><span class="sxs-lookup"><span data-stu-id="c1eac-191">Other environments might have an existing QoS strategy in place, which will help you determine the priority of network workloads.</span></span>

<span data-ttu-id="c1eac-192">不同实时流式处理工作负荷的端口范围的相对大小设置专用于该工作负荷的总可用带宽的比例。</span><span class="sxs-lookup"><span data-stu-id="c1eac-192">The relative size of the port ranges for different real-time streaming workloads sets the proportion of the total available bandwidth dedicated to that workload.</span></span> <span data-ttu-id="c1eac-193">要返回到我们早期的邮政类比：带"Air Mail"戳记的信函可能在一小时内到达最近的机场，而标有"批量邮件"标记的小包裹可以等待一天，然后再在一系列卡车上行驶。</span><span class="sxs-lookup"><span data-stu-id="c1eac-193">To return to our earlier postal analogy: a letter with an "Air Mail" stamp might get taken within an hour to the nearest airport, while a small package marked "Bulk Mail" mark can wait for a day before traveling over land on a series of trucks.</span></span>

<span data-ttu-id="c1eac-194">_建议的初始端口范围_</span><span class="sxs-lookup"><span data-stu-id="c1eac-194">_Recommended initial port ranges_</span></span>

|<span data-ttu-id="c1eac-195">媒体流量类型</span><span class="sxs-lookup"><span data-stu-id="c1eac-195">Media traffic type</span></span>| <span data-ttu-id="c1eac-196">客户端源端口范围</span><span class="sxs-lookup"><span data-stu-id="c1eac-196">Client source port range</span></span> |<span data-ttu-id="c1eac-197">协议</span><span class="sxs-lookup"><span data-stu-id="c1eac-197">Protocol</span></span>|<span data-ttu-id="c1eac-198">DSCP 值</span><span class="sxs-lookup"><span data-stu-id="c1eac-198">DSCP value</span></span>|<span data-ttu-id="c1eac-199">DSCP 类</span><span class="sxs-lookup"><span data-stu-id="c1eac-199">DSCP class</span></span>|
|:--- |:--- |:--- |:--- |:--- |
|<span data-ttu-id="c1eac-200">音频</span><span class="sxs-lookup"><span data-stu-id="c1eac-200">Audio</span></span>| <span data-ttu-id="c1eac-201">50,000–50,019</span><span class="sxs-lookup"><span data-stu-id="c1eac-201">50,000–50,019</span></span>|<span data-ttu-id="c1eac-202">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="c1eac-202">TCP/UDP</span></span>|<span data-ttu-id="c1eac-203">46</span><span class="sxs-lookup"><span data-stu-id="c1eac-203">46</span></span>|<span data-ttu-id="c1eac-204">加速转发 (EF)</span><span class="sxs-lookup"><span data-stu-id="c1eac-204">Expedited Forwarding (EF)</span></span>|
|<span data-ttu-id="c1eac-205">视频</span><span class="sxs-lookup"><span data-stu-id="c1eac-205">Video</span></span>| <span data-ttu-id="c1eac-206">50,020–50,039</span><span class="sxs-lookup"><span data-stu-id="c1eac-206">50,020–50,039</span></span>|<span data-ttu-id="c1eac-207">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="c1eac-207">TCP/UDP</span></span>|<span data-ttu-id="c1eac-208">34</span><span class="sxs-lookup"><span data-stu-id="c1eac-208">34</span></span>|<span data-ttu-id="c1eac-209">保证转发 (AF41)</span><span class="sxs-lookup"><span data-stu-id="c1eac-209">Assured Forwarding (AF41)</span></span>|
|<span data-ttu-id="c1eac-210">应用程序/屏幕共享</span><span class="sxs-lookup"><span data-stu-id="c1eac-210">Application/Screen Sharing</span></span>| <span data-ttu-id="c1eac-211">50,040–50,059</span><span class="sxs-lookup"><span data-stu-id="c1eac-211">50,040–50,059</span></span>|<span data-ttu-id="c1eac-212">TCP/UDP</span><span class="sxs-lookup"><span data-stu-id="c1eac-212">TCP/UDP</span></span>|<span data-ttu-id="c1eac-213">18</span><span class="sxs-lookup"><span data-stu-id="c1eac-213">18</span></span>|<span data-ttu-id="c1eac-214">保证转发 (AF21)</span><span class="sxs-lookup"><span data-stu-id="c1eac-214">Assured Forwarding (AF21)</span></span>|
||||||

<span data-ttu-id="c1eac-215">使用这些设置时请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="c1eac-215">Be aware of the following when you use these settings:</span></span>

- <span data-ttu-id="c1eac-216">如果计划在将来实现 ExpressRoute 但尚未实现 QoS，我们建议遵循指南，以便从发送方到接收方的 DSCP 值相同。</span><span class="sxs-lookup"><span data-stu-id="c1eac-216">If you plan to implement ExpressRoute in the future and haven't yet implemented QoS, we recommend that you follow the guidance so that DSCP values are the same from sender to receiver.</span></span>

- <span data-ttu-id="c1eac-217">所有客户端（包括移动客户端和 Teams 设备）都将使用这些端口范围，并且将受你实施的任何使用这些源端口范围的 DSCP 策略的影响。</span><span class="sxs-lookup"><span data-stu-id="c1eac-217">All clients, including mobile clients and Teams devices, will use these port ranges and will be affected by any DSCP policy you implement that uses these source port ranges.</span></span> <span data-ttu-id="c1eac-218">将继续使用动态端口的唯一客户端是基于浏览器的客户端 (允许参与者使用其浏览器和) 。</span><span class="sxs-lookup"><span data-stu-id="c1eac-218">The only clients that will continue to use dynamic ports are the browser-based clients (clients that let participants join meetings by using their browsers).</span></span>

- <span data-ttu-id="c1eac-219">虽然 Mac 客户端使用相同的端口范围，但它也使用 EF (和视频) AF41 (硬编码) 。</span><span class="sxs-lookup"><span data-stu-id="c1eac-219">Although the Mac client uses the same port ranges, it also uses hard-coded values for audio (EF) and video (AF41).</span></span> <span data-ttu-id="c1eac-220">这些值不可配置。</span><span class="sxs-lookup"><span data-stu-id="c1eac-220">These values aren't configurable.</span></span>

- <span data-ttu-id="c1eac-221">如果以后需要调整端口范围以改进用户体验，则端口范围不能重叠，并且应该彼此相邻。</span><span class="sxs-lookup"><span data-stu-id="c1eac-221">If you later need to adjust the port ranges to improve user experience, the port ranges can't overlap and should be adjacent to each other.</span></span>

## <a name="migrate-qos-to-teams"></a><span data-ttu-id="c1eac-222">将 QoS 迁移到 Teams</span><span class="sxs-lookup"><span data-stu-id="c1eac-222">Migrate QoS to Teams</span></span>

<span data-ttu-id="c1eac-223">如果你之前部署了 Skype for Business Online，包括 QoS 标记和端口范围，并且现在正在部署。</span><span class="sxs-lookup"><span data-stu-id="c1eac-223">If you've previously deployed Skype for Business Online, including QoS tagging and port ranges, and are now deploying.</span></span> <span data-ttu-id="c1eac-224">Teams、Teams 将尊重现有配置，并使用与 Skype for Business 客户端相同的端口范围和标记。</span><span class="sxs-lookup"><span data-stu-id="c1eac-224">Teams, Teams will respect the existing configuration and will use the same port ranges and tagging as the Skype for Business client.</span></span> <span data-ttu-id="c1eac-225">在大多数情况下，不需要其他配置。</span><span class="sxs-lookup"><span data-stu-id="c1eac-225">In most cases, no additional configuration will be needed.</span></span>

> [!NOTE]
> <span data-ttu-id="c1eac-226">如果通过组策略使用应用程序名称 QoS 标记，则必须Teams.exe应用程序名称。</span><span class="sxs-lookup"><span data-stu-id="c1eac-226">If you're using Application Name QoS tagging via Group Policy, you must add Teams.exe as the application name.</span></span>

### <a name="implement-qos-in-teams-on-windows-using-powershell"></a><span data-ttu-id="c1eac-227">使用 PowerShell 在 Windows 上的 Teams 中实现 QoS</span><span class="sxs-lookup"><span data-stu-id="c1eac-227">Implement QoS in Teams on Windows using PowerShell</span></span>

<span data-ttu-id="c1eac-228">**为音频设置 QoS**</span><span class="sxs-lookup"><span data-stu-id="c1eac-228">**Set QoS for audio**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Audio" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50000 -IPSrcPortEndMatchCondition 50019 -DSCPAction 46 -NetworkProfile All
```

<span data-ttu-id="c1eac-229">**为视频设置 QoS**</span><span class="sxs-lookup"><span data-stu-id="c1eac-229">**Set QoS for video**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Video" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50020 -IPSrcPortEndMatchCondition 50039 -DSCPAction 34 -NetworkProfile All
```

<span data-ttu-id="c1eac-230">**设置 QoS 进行共享**</span><span class="sxs-lookup"><span data-stu-id="c1eac-230">**Set QoS for sharing**</span></span>

```powershell
new-NetQosPolicy -Name "Teams Sharing" -AppPathNameMatchCondition "Teams.exe" -IPProtocolMatchCondition Both -IPSrcPortStartMatchCondition 50040 -IPSrcPortEndMatchCondition 50059 -DSCPAction 18 -NetworkProfile All
```

## <a name="managing-source-ports-in-the-teams-admin-center"></a><span data-ttu-id="c1eac-231">在 Teams 管理中心管理源端口</span><span class="sxs-lookup"><span data-stu-id="c1eac-231">Managing source ports in the Teams admin center</span></span>

<span data-ttu-id="c1eac-232">在 Teams 中，应主动管理不同工作负荷使用的 QoS 源端口，并根据需要进行调整。</span><span class="sxs-lookup"><span data-stu-id="c1eac-232">In Teams, QoS source ports used by the different workloads should be actively managed, and adjusted as necessary.</span></span> <span data-ttu-id="c1eac-233">引用"选择每种媒体类型[](#choose-initial-port-ranges-for-each-media-type)的初始端口范围"中的表，端口范围是可调整的，但 DSCP 标记不可配置。</span><span class="sxs-lookup"><span data-stu-id="c1eac-233">Referring to the table in [Choose initial port ranges for each media type](#choose-initial-port-ranges-for-each-media-type), the port ranges are adjustable, but the DSCP markings aren't configurable.</span></span> <span data-ttu-id="c1eac-234">实现这些设置后，你可能会发现给定媒体类型需要更多或更少的端口。</span><span class="sxs-lookup"><span data-stu-id="c1eac-234">Once you have implemented these settings, you might find that more or fewer ports are needed for a given media type.</span></span> <span data-ttu-id="c1eac-235">[应该使用](use-call-analytics-to-troubleshoot-poor-call-quality.md) [CQD ](turning-on-and-using-call-quality-dashboard.md) (基于用户的呼叫分析和呼叫质量仪表板) 在 Teams 实施后做出调整端口范围的决策，并定期根据需求变化进行调整。</span><span class="sxs-lookup"><span data-stu-id="c1eac-235">[Per-user call analytics](use-call-analytics-to-troubleshoot-poor-call-quality.md) and [Call Quality Dashboard (CQD)](turning-on-and-using-call-quality-dashboard.md) should be used in making a decision to adjust port ranges after Teams has been implemented, and periodically as needs change.</span></span>

> [!NOTE]
> <span data-ttu-id="c1eac-236">如果已基于 Skype for Business Online 的源端口范围和 DSCP 标记配置 QoS，则相同的配置将应用于 Teams，并且无需对映射进行进一步的客户端或网络更改，不过，您可能需要设置 [Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) 中使用的范围，以匹配为 Skype for Business Online 配置的范围。</span><span class="sxs-lookup"><span data-stu-id="c1eac-236">If you've already configured QoS based on source port ranges and DSCP markings for Skype for Business Online, the same configuration will apply to Teams and no further client or network changes to the mapping will be required, though you may have to [set the ranges used in Teams](meeting-settings-in-teams.md#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings) to match what was configured for Skype for Business Online.</span></span>

<span data-ttu-id="c1eac-237">如果你之前在本地部署了 Skype for Business Server，你可能需要重新检查 QoS 策略。</span><span class="sxs-lookup"><span data-stu-id="c1eac-237">If you’ve previously deployed Skype for Business Server on-premises, you might need to re-examine your QoS policies.</span></span> <span data-ttu-id="c1eac-238">调整策略以匹配已验证的端口范围设置，为 Teams 提供高质量的用户体验。</span><span class="sxs-lookup"><span data-stu-id="c1eac-238">Adjust the policies to match port range settings you've verified provide a quality user experience for Teams.</span></span>

## <a name="validate-your-qos-implementation"></a><span data-ttu-id="c1eac-239">验证 QoS 实现</span><span class="sxs-lookup"><span data-stu-id="c1eac-239">Validate your QoS implementation</span></span>

<span data-ttu-id="c1eac-240">若要使 QoS 生效，GPO 设置的 DSCP 值需要在调用的两端存在。</span><span class="sxs-lookup"><span data-stu-id="c1eac-240">For QoS to be effective, the DSCP value set by the GPO needs to be present at both ends of a call.</span></span> <span data-ttu-id="c1eac-241">通过分析 Teams 客户端生成的流量，可以验证在 Teams 工作负荷流量在网络中移动时是否更改或去除 DSCP 值。</span><span class="sxs-lookup"><span data-stu-id="c1eac-241">By analyzing the traffic generated by the Teams client, you can verify that the DSCP value isn’t changed or stripped out when the Teams workload traffic moves through the network.</span></span>

<span data-ttu-id="c1eac-242">最好是在网络出口点捕获流量。</span><span class="sxs-lookup"><span data-stu-id="c1eac-242">Preferably, you capture traffic at the network egress point.</span></span> <span data-ttu-id="c1eac-243">可以使用交换机或路由器上的端口镜像来帮助实现此要求。</span><span class="sxs-lookup"><span data-stu-id="c1eac-243">You can use port mirroring on a switch or router to help with this.</span></span>

## <a name="implement-qos-for-other-devices"></a><span data-ttu-id="c1eac-244">为其他设备实现 QoS</span><span class="sxs-lookup"><span data-stu-id="c1eac-244">Implement QoS for other devices</span></span>

<span data-ttu-id="c1eac-245">阅读以下主题，了解为 Intune、Surface、iOS、Android 和 Mac 实现 QoS 的信息</span><span class="sxs-lookup"><span data-stu-id="c1eac-245">Read these topics for information about implementing QoS for Intune, Surface, iOS, Android, and Mac</span></span>

- [<span data-ttu-id="c1eac-246">Surface Hub 2S 的 QoS</span><span class="sxs-lookup"><span data-stu-id="c1eac-246">QoS for Surface Hub 2S</span></span>](https://docs.microsoft.com/surface-hub/surface-hub-2s-manage-intune)

- [<span data-ttu-id="c1eac-247">Surface Hub 的 QoS</span><span class="sxs-lookup"><span data-stu-id="c1eac-247">QoS for Surface Hub</span></span>](https://docs.microsoft.com/surface-hub/surface-hub-qos)

- [<span data-ttu-id="c1eac-248">适用于 iOS、Android 和 Mac 的 QoS</span><span class="sxs-lookup"><span data-stu-id="c1eac-248">QoS for iOS, Android, and Mac</span></span>](https://docs.microsoft.com/microsoftteams/meeting-settings-in-teams?WT.mc_id=TeamsAdminCenterCSH#set-how-you-want-to-handle-real-time-media-traffic-for-teams-meetings)

## <a name="related-topics"></a><span data-ttu-id="c1eac-249">相关主题</span><span class="sxs-lookup"><span data-stu-id="c1eac-249">Related topics</span></span>

- [<span data-ttu-id="c1eac-250">视频：网络规划</span><span class="sxs-lookup"><span data-stu-id="c1eac-250">Video: Network Planning</span></span>](https://aka.ms/teams-networking)

- [<span data-ttu-id="c1eac-251">为 Microsoft Teams 准备组织的网络</span><span class="sxs-lookup"><span data-stu-id="c1eac-251">Prepare your organization's network for Microsoft Teams</span></span>](prepare-network.md)

- [<span data-ttu-id="c1eac-252">在 Teams 客户端中实现 QoS</span><span class="sxs-lookup"><span data-stu-id="c1eac-252">Implement QoS in the Teams client</span></span>](QoS-in-Teams-clients.md)
