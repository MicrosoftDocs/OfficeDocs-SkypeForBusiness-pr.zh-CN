---
title: Microsoft Teams 通话流程
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 06/08/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sonua
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
description: 介绍团队如何使用各种拓扑中的 Office 365 流。
ms.openlocfilehash: d98f789017c0f5388a0adebd382d947e716d7fc9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36239349"
---
# <a name="microsoft-teams-call-flows"></a><span data-ttu-id="22a51-103">Microsoft Teams 通话流程</span><span class="sxs-lookup"><span data-stu-id="22a51-103">Microsoft Teams call flows</span></span>

> [!Tip]
> <span data-ttu-id="22a51-104">观看以下会话, 了解团队如何利用你的网络以及如何规划最佳网络连接:[团队网络规划](https://aka.ms/teams-networking)</span><span class="sxs-lookup"><span data-stu-id="22a51-104">Watch the following session to learn how Teams leverages your network and how to plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking)</span></span>

## <a name="overview"></a><span data-ttu-id="22a51-105">概述</span><span class="sxs-lookup"><span data-stu-id="22a51-105">Overview</span></span>
<span data-ttu-id="22a51-106">本文介绍团队如何使用各种拓扑中的 Office 365 调用流。</span><span class="sxs-lookup"><span data-stu-id="22a51-106">This article describes how Teams uses Office 365 call flows in various topologies.</span></span> <span data-ttu-id="22a51-107">此外, 它还介绍了用于对等媒体通信的独特团队流。</span><span class="sxs-lookup"><span data-stu-id="22a51-107">In addition, it describes unique Teams flows that are used for peer-to-peer media communication.</span></span> <span data-ttu-id="22a51-108">文档介绍这些流、其用途以及它们在网络上的来源和终止。</span><span class="sxs-lookup"><span data-stu-id="22a51-108">The document describes these flows, their purpose, and their origin and termination on the network.</span></span> <span data-ttu-id="22a51-109">为此, 请考虑以下事项:</span><span class="sxs-lookup"><span data-stu-id="22a51-109">For purposes of this article, assume the following:</span></span>

- <span data-ttu-id="22a51-110">流 X 由本地 Office 365 客户端用于与云中的 Office 365 服务通信。</span><span class="sxs-lookup"><span data-stu-id="22a51-110">Flow X is used by the on-premises Office 365 client to communicate with the Office 365 service in the cloud.</span></span> <span data-ttu-id="22a51-111">它源于客户网络, 它在 Office 365 中作为终结点终止。</span><span class="sxs-lookup"><span data-stu-id="22a51-111">It originates from the customer network, and it terminates as an endpoint in Office 365.</span></span>

- <span data-ttu-id="22a51-112">流 Y 由本地 Office 365 客户端用于与 Office 365 有依赖关系的 Internet 上的服务进行通信。</span><span class="sxs-lookup"><span data-stu-id="22a51-112">Flow Y is used by the on-premises Office 365 client to communicate with a service on the Internet that Office 365 has a dependency on.</span></span> <span data-ttu-id="22a51-113">它源于客户网络, 并作为 Internet 上的终结点终止。</span><span class="sxs-lookup"><span data-stu-id="22a51-113">It originates from the customer network, and it terminates as an endpoint on the Internet.</span></span>

<span data-ttu-id="22a51-114">本文包含以下部分:</span><span class="sxs-lookup"><span data-stu-id="22a51-114">The article contains the following sections:</span></span>

- <span data-ttu-id="22a51-115">**背景**-提供后台信息, 例如 Office 365 流可能遍历的网络、流量的类型、从客户网络到 office 365 服务终结点的连接指南、与第三方组件的互操作性, 以及团队用于选择媒体流的原则。</span><span class="sxs-lookup"><span data-stu-id="22a51-115">**Background** - Provides background information, such as networks that Office 365 flows may traverse, type of traffic, connectivity guidance from the customer network to Office 365 service endpoints, interoperability with third-party components, and principles that are used by Teams to select media flows.</span></span>

- <span data-ttu-id="22a51-116">**各种拓扑中的通话流**-阐释了各种拓扑中的通话流的使用。</span><span class="sxs-lookup"><span data-stu-id="22a51-116">**Call flows in various topologies** - Illustrates the use of call flows in various topologies.</span></span> <span data-ttu-id="22a51-117">对于每个拓扑, 该部分枚举所有受支持的流, 并阐释如何通过多种使用案例使用这些流。</span><span class="sxs-lookup"><span data-stu-id="22a51-117">For each topology, the section enumerates all supported flows and illustrates how these flows are used via several use cases.</span></span> <span data-ttu-id="22a51-118">对于每个用例, 它通过流图描述流的序列和选择。</span><span class="sxs-lookup"><span data-stu-id="22a51-118">For each use case, it describes the sequence and selection of flows via a flow diagram.</span></span> 

- <span data-ttu-id="22a51-119">**具有 Express 路线优化的团队**-介绍在部署快速路由以进行优化时如何使用这些流, 通过简单拓扑阐释。</span><span class="sxs-lookup"><span data-stu-id="22a51-119">**Teams with Express Route optimization** - Describes how these flows are used when Express Route is deployed for optimization, illustrated via a simple topology.</span></span>

## <a name="background"></a><span data-ttu-id="22a51-120">背景</span><span class="sxs-lookup"><span data-stu-id="22a51-120">Background</span></span>
### <a name="network-segments"></a><span data-ttu-id="22a51-121">网络段</span><span class="sxs-lookup"><span data-stu-id="22a51-121">Network segments</span></span>
<span data-ttu-id="22a51-122">**客户网络**: 这是您控制和管理的网络段。</span><span class="sxs-lookup"><span data-stu-id="22a51-122">**Customer network**: This is the network segment that you control and manage.</span></span> <span data-ttu-id="22a51-123">这包括客户办公室中的所有客户连接, 无论是有线还是无线连接的 office 大楼、本地数据中心, 以及 Internet 提供商、快递路线或任何其他私人对等的连接。</span><span class="sxs-lookup"><span data-stu-id="22a51-123">This includes all customer connections within customer offices, whether wired or wireless, between office buildings, to on-premises datacenters, and your connections to Internet providers, Express Route, or any other private peering.</span></span> 

<span data-ttu-id="22a51-124">通常情况下, 客户网络具有多个具有防火墙和/或代理服务器的网络外围, 这些服务器强制实施组织的安全策略, 并且仅允许某些已设置和配置的网络流量。</span><span class="sxs-lookup"><span data-stu-id="22a51-124">Typically, a customer network has several network perimeters with firewalls and/or proxy servers, which enforce your organization's security policies, and that only allow certain network traffic that you have set up and configured.</span></span> <span data-ttu-id="22a51-125">由于你管理此网络, 你可以直接控制网络性能, 因此强烈建议你完成网络评估, 以验证网络中的网站和网络到 Office 365 网络中的性能。</span><span class="sxs-lookup"><span data-stu-id="22a51-125">Because you manage this network, you have direct control over the performance of the network, and it is highly recommended that you complete network assessments to validate performance both within sites in your network and from your network to the Office 365 network.</span></span> 

<span data-ttu-id="22a51-126">**Internet**: 这是整个网络的一部分, 该网段将由从客户网络外部连接到 Office 365 的用户使用。</span><span class="sxs-lookup"><span data-stu-id="22a51-126">**Internet**: This is the network segment that is part of your overall network that will be used by users who are connecting to Office 365 from outside of the customer network.</span></span> <span data-ttu-id="22a51-127">它还可由从客户网络到 Office 365 的某些流量使用。</span><span class="sxs-lookup"><span data-stu-id="22a51-127">It is also used by some traffic from the customer network to Office 365.</span></span> 

<span data-ttu-id="22a51-128">已**访问/来宾专用网络**: 这是客户网络外部的网段, 但不在公共 Internet 中, 您的用户和/或其来宾可能会访问。</span><span class="sxs-lookup"><span data-stu-id="22a51-128">**Visited/Guest private network**: This is the network segment outside your customer network, but not in the public Internet, that your users and/or their guests may visit.</span></span> <span data-ttu-id="22a51-129">例如, 家庭专用网络或企业专用网络, 它不会部署团队, 您的用户和/或其与团队服务交互的客户可能会驻留。</span><span class="sxs-lookup"><span data-stu-id="22a51-129">For example, home private network or an Enterprise private network, that does not deploy Teams, where your users and/or their customers that interact with Teams services may reside.</span></span>

><span data-ttu-id="22a51-130">**注意**: 与 Office 365 的连接也适用于这些网络。</span><span class="sxs-lookup"><span data-stu-id="22a51-130">**Note**: Connectivity to Office 365 is also applicable to these networks.</span></span>

<span data-ttu-id="22a51-131">**Office 365**: 这是支持 Office 365 服务的网络段。</span><span class="sxs-lookup"><span data-stu-id="22a51-131">**Office 365**: This is the network segment that supports Office 365 services.</span></span> <span data-ttu-id="22a51-132">在全球各地, 全球各地都有与客户网络邻近的边缘。</span><span class="sxs-lookup"><span data-stu-id="22a51-132">It is distributed worldwide with edges in proximity to the customer network in most locations.</span></span> <span data-ttu-id="22a51-133">本文档中提及的函数包括传输中继、会议服务器和媒体处理器。</span><span class="sxs-lookup"><span data-stu-id="22a51-133">Functions mentioned in this document include Transport Relay, conferencing server, and Media Processor.</span></span> 

<span data-ttu-id="22a51-134">**快速路线 (可选)**: 这是您的整个网络的一部分, 它将为您提供与 Office 365 网络的专用专用连接。</span><span class="sxs-lookup"><span data-stu-id="22a51-134">**Express Route (optional)**: This is the network segment that is part of your overall network that will give you a dedicated, private connection to the Office 365 network.</span></span>

### <a name="types-of-traffic"></a><span data-ttu-id="22a51-135">流量类型</span><span class="sxs-lookup"><span data-stu-id="22a51-135">Types of traffic</span></span>

<span data-ttu-id="22a51-136">**实时媒体**: 在 RTP (实时传输协议) 内封装的数据, 支持音频、视频和屏幕共享工作负荷。</span><span class="sxs-lookup"><span data-stu-id="22a51-136">**Real-time media**: Data encapsulated within RTP (Real-time Transport Protocol) that supports audio, video and screen sharing workloads.</span></span> <span data-ttu-id="22a51-137">通常情况下, 媒体流量很长很长, 因此你希望此流量能够充分利用最直接的路径, 并将 UDP 与 TCP 用作传输层协议, 这是从质量角度看交互式实时媒体的最佳传输.</span><span class="sxs-lookup"><span data-stu-id="22a51-137">In general, media traffic is highly latency sensitive, so you would want this traffic to take the most direct path possible, and to use UDP versus TCP as the transport layer protocol, which is the best transport for interactive real time media from a quality perspective.</span></span> <span data-ttu-id="22a51-138">(注意: 作为最后的手段, 媒体可以使用 TCP/IP, 也可以在 HTTP 协议中使用隧道, 但不建议由于不良的质量影响。)RTP 流通过 SRTP 进行保护, 其中仅加密负载。</span><span class="sxs-lookup"><span data-stu-id="22a51-138">(Note: As a last resort, media can use TCP/IP and also be tunneled within the HTTP protocol, but it is not recommended due to bad quality implications.) RTP flow is secured via SRTP, in which only the payload is encrypted.</span></span>

<span data-ttu-id="22a51-139">**信号**: 客户端和服务器之间的通信链接, 或用于控制活动的其他客户端 (例如, 启动呼叫时) 和发送即时消息。</span><span class="sxs-lookup"><span data-stu-id="22a51-139">**Signaling**: The communication link between the client and server, or other clients that are used to control activities (for example, when a call is initiated), and deliver instant messages.</span></span> <span data-ttu-id="22a51-140">大多数信号流量使用基于 HTTPS 的 REST 接口, 但在某些情况下 (例如, Office 365 和会话边界控制器之间的连接), 它将使用 SIP 协议。</span><span class="sxs-lookup"><span data-stu-id="22a51-140">Most signaling traffic uses the HTTPS-based REST interfaces, though in some scenarios (for example, connection between Office 365 and a Session Border Controller) it uses SIP protocol.</span></span> <span data-ttu-id="22a51-141">请务必了解此流量对延迟的敏感程度不太大, 但如果终结点之间的延迟超过几秒, 可能会导致服务中断或呼叫超时。</span><span class="sxs-lookup"><span data-stu-id="22a51-141">It's important to understand that this traffic is much less sensitive to latency but may cause service outages or call timeouts if latency between the endpoints exceeds several seconds.</span></span> 

### <a name="connectivity-to-office-365"></a><span data-ttu-id="22a51-142">与 Office 365 的连接</span><span class="sxs-lookup"><span data-stu-id="22a51-142">Connectivity to Office 365</span></span>

<span data-ttu-id="22a51-143">团队需要[连接到 Internet](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10)。</span><span class="sxs-lookup"><span data-stu-id="22a51-143">Teams requires [connectivity to the Internet](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10).</span></span> <span data-ttu-id="22a51-144">团队终结点 Url 和 IP 地址范围在[Office 365 url 和 ip 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)中列出。</span><span class="sxs-lookup"><span data-stu-id="22a51-144">Teams endpoint URLs and IP address ranges are listed in [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> <span data-ttu-id="22a51-145">(注意: 打开到 TCP 端口80和443的连接, 以及 UDP 端口3478到3481的连接。)此外, 团队对 Skype for business Online 有依赖关系, 该功能还必须连接到 Internet。</span><span class="sxs-lookup"><span data-stu-id="22a51-145">(Note: Open connectivity to TCP ports 80 and 443, and to UDP ports 3478 through 3481 is required.) Furthermore, Teams has a dependency on Skype for Business Online, which must also be connected to the Internet.</span></span>

<span data-ttu-id="22a51-146">团队媒体流连接是通过标准的 IETF ICE (交互式连接建立) 过程实现的。</span><span class="sxs-lookup"><span data-stu-id="22a51-146">Teams media flows connectivity is implemented via standard IETF ICE (Interactive Connectivity Establishment) procedures.</span></span>

### <a name="interoperability-restrictions"></a><span data-ttu-id="22a51-147">互操作性限制</span><span class="sxs-lookup"><span data-stu-id="22a51-147">Interoperability restrictions</span></span>
<span data-ttu-id="22a51-148">**第三方媒体中继**: 团队媒体流 (即媒体终结点之一是团队) 可能仅遍历团队或 Skype for business 本机媒体中继。</span><span class="sxs-lookup"><span data-stu-id="22a51-148">**Third party media relays**: A Teams media flow (that is, one of the media endpoints is Teams) may traverse only Teams or Skype for Business native media relays.</span></span> <span data-ttu-id="22a51-149">不支持与第三方媒体中继的互操作。</span><span class="sxs-lookup"><span data-stu-id="22a51-149">Interoperability with a third party media relay is not supported.</span></span> <span data-ttu-id="22a51-150">(注意: PSTN 的第三方 SBC 必须终止 RTP/RTCP 流, 通过 SRTP 进行保护, 而不是将其中继到下一跃点。)</span><span class="sxs-lookup"><span data-stu-id="22a51-150">(Note: A third party SBC on the boundary with PSTN must terminate RTP/RTCP stream, secured via SRTP, and not relay it to the next hop.)</span></span>

<span data-ttu-id="22a51-151">**第三方 SIP 代理服务器**: 带有第三方 SBC 和/或网关的团队发来的 "sip" 对话框可能会遍历团队或 Skype for BUSINESS 本机 SIP 代理。</span><span class="sxs-lookup"><span data-stu-id="22a51-151">**Third party SIP proxy servers**: A Teams signaling SIP dialog with a third party SBC and/or gateway may traverse Teams or Skype for Business native SIP proxies.</span></span> <span data-ttu-id="22a51-152">不支持与第三方 SIP 代理的互操作。</span><span class="sxs-lookup"><span data-stu-id="22a51-152">Interoperability with a third party SIP proxy is not supported.</span></span>

<span data-ttu-id="22a51-153">**第三方 B2BUA (即 SBC)**: 团队媒体流由/到 PSTN 由第三方 SBC 终止。</span><span class="sxs-lookup"><span data-stu-id="22a51-153">**Third party B2BUA (that is, SBC)**: A Teams media flow from/to the PSTN is terminated by a third party SBC.</span></span> <span data-ttu-id="22a51-154">但是, 不支持与团队网络中的第三方 SBC (即第三方 SBC 调节两个团队/Skype for business 终结点) 的互操作性。</span><span class="sxs-lookup"><span data-stu-id="22a51-154">However, interoperability with a third party SBC within the Teams network (that is, a third party SBC mediates two Teams/Skype for Business endpoints) is not supported.</span></span>

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a><span data-ttu-id="22a51-155">Microsoft 团队不推荐的技术</span><span class="sxs-lookup"><span data-stu-id="22a51-155">Technologies that are not recommended with Microsoft Teams</span></span>

<span data-ttu-id="22a51-156">**VPN 网络**: 不建议媒体流量 (即, 流 2 ')。</span><span class="sxs-lookup"><span data-stu-id="22a51-156">**VPN network**: It is not recommended for media traffic (that is, flow 2').</span></span> <span data-ttu-id="22a51-157">VPN 客户端应使用分离的 VPN 和路由媒体流量, 如中https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/所述。</span><span class="sxs-lookup"><span data-stu-id="22a51-157">The VPN client should use split VPN and route media traffic like any external non-VPN user, as specified in https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/.</span></span>

><span data-ttu-id="22a51-158">**注意**: 尽管标题是 Lync, 但它也适用于团队。</span><span class="sxs-lookup"><span data-stu-id="22a51-158">**Note**: Although the title is Lync, it is applicable to Teams as well.</span></span>

<span data-ttu-id="22a51-159">**数据包 shapers**: 不推荐任何类型的数据包 snippers、数据包检查或数据包整形设备, 可能会显著降低质量。</span><span class="sxs-lookup"><span data-stu-id="22a51-159">**Packet shapers**: Any kind of packet snippers, packet inspection, or packet shaper devices are not recommended and may degrade quality significantly.</span></span> 

### <a name="principles"></a><span data-ttu-id="22a51-160">规则</span><span class="sxs-lookup"><span data-stu-id="22a51-160">Principles</span></span>
<span data-ttu-id="22a51-161">有四个一般原则可帮助你理解 Microsoft 团队的通话流:</span><span class="sxs-lookup"><span data-stu-id="22a51-161">There are four general principles that help you understand call flows for Microsoft Teams:</span></span>
 
1.  <span data-ttu-id="22a51-162">Microsoft 团队会议由与第一个参与者联接的同一区域中的 Office 365 托管。</span><span class="sxs-lookup"><span data-stu-id="22a51-162">A Microsoft Teams conference is hosted by Office 365 in the same region where the first participant joined.</span></span> <span data-ttu-id="22a51-163">(注意: 如果在某些拓扑中会出现此规则的例外情况, 将在此文档中介绍这些例外, 并通过相应的通话流进行说明。)</span><span class="sxs-lookup"><span data-stu-id="22a51-163">(Note: If there will be exceptions to this rule in some topologies, then they will be described in this document, and illustrated by an appropriate call flow.)</span></span>

2.  <span data-ttu-id="22a51-164">Office 365 中的团队媒体终结点基于媒体处理需求使用, 而不是基于呼叫类型。</span><span class="sxs-lookup"><span data-stu-id="22a51-164">A Teams media endpoint in Office 365 is used based on media processing needs and not based on call type.</span></span> <span data-ttu-id="22a51-165">(例如, 点到点呼叫可以使用云中的媒体终结点来处理用于脚本和/或录制的媒体, 而两个参与者的会议可能不会使用云中的任何媒体终结点。)但是, 大多数会议会将媒体终结点用于混合和路由用途, 分配了托管会议的位置。</span><span class="sxs-lookup"><span data-stu-id="22a51-165">(For example, a point-to-point call may use a media endpoint in the cloud to process media for transcription and/or recording, while a conference with two participants may not use any media endpoint in the cloud.) However, most conferences will use a media endpoint for mixing and routing purposes, allocated where the conference is hosted.</span></span> <span data-ttu-id="22a51-166">从客户端发送到媒体终结点的媒体流量可能会直接路由, 或者在 Office 365 中使用传输中继 (如果由于客户网络防火墙限制而需要)。</span><span class="sxs-lookup"><span data-stu-id="22a51-166">The media traffic sent from a client to the media endpoint may be routed directly or use a Transport Relay in Office 365 if required due to customer network firewall restrictions.</span></span> 

3.  <span data-ttu-id="22a51-167">对等调用的媒体流量将获得可用的最直接路线, 假设该呼叫不会在云中强制使用媒体终结点 (请参阅上面的 #2)。</span><span class="sxs-lookup"><span data-stu-id="22a51-167">Media traffic for peer-to-peer calls take the most direct route that is available, assuming that the call doesn't mandate a media endpoint in the cloud (see #2 above).</span></span> <span data-ttu-id="22a51-168">首选路由直接发送到远程对等 (客户端), 但如果该路由不可用, 则一个或多个传输中继将中继流量。</span><span class="sxs-lookup"><span data-stu-id="22a51-168">The preferred route is direct to the remote peer (client), but if that route isn't available, then one or more Transport Relays will relay traffic.</span></span> <span data-ttu-id="22a51-169">建议媒体流量不应遍历服务器 (如数据包 shapers、VPN 服务器等), 因为这将影响媒体质量。</span><span class="sxs-lookup"><span data-stu-id="22a51-169">It is recommended that media traffic shall not transverse servers such as packet shapers, VPN servers, and so on, since this will impact the media quality.</span></span>

4.  <span data-ttu-id="22a51-170">信号流量始终转到最接近于用户的服务器。</span><span class="sxs-lookup"><span data-stu-id="22a51-170">Signaling traffic always goes to the closest server to the user.</span></span> 

<span data-ttu-id="22a51-171">若要了解有关所选媒体路径的详细信息, 请参阅https://www.youtube.com/watch?v=1tmHMIlAQdo。</span><span class="sxs-lookup"><span data-stu-id="22a51-171">To learn more about the details on the media path that is chosen, see https://www.youtube.com/watch?v=1tmHMIlAQdo.</span></span>

## <a name="call-flows-in-various-topologies"></a><span data-ttu-id="22a51-172">各种拓扑中的呼叫流</span><span class="sxs-lookup"><span data-stu-id="22a51-172">Call flows in various topologies</span></span>
### <a name="teams-topology"></a><span data-ttu-id="22a51-173">团队拓扑</span><span class="sxs-lookup"><span data-stu-id="22a51-173">Teams topology</span></span>
<span data-ttu-id="22a51-174">此拓扑由客户使用, 它在没有任何本地部署 (如 Skype for Business Server 或手机系统直接路由) 的情况下利用来自云的团队服务。</span><span class="sxs-lookup"><span data-stu-id="22a51-174">This topology is used by customers that leverage Teams services from the cloud without any on-premises deployment, such as Skype for Business Server or Phone System Direct Routing.</span></span> <span data-ttu-id="22a51-175">此外, Office 365 的接口通过不使用 Azure Express 路由的 Internet 完成。</span><span class="sxs-lookup"><span data-stu-id="22a51-175">In addition, the interface to Office 365 is done via the Internet without Azure Express Route.</span></span> 

<span data-ttu-id="22a51-176">[![Microsoft 团队在线通话流程图01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-176">[![Microsoft Teams Online Call Flows Figure 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span></span>

<span data-ttu-id="22a51-177">*图 1-团队拓扑*</span><span class="sxs-lookup"><span data-stu-id="22a51-177">*Figure 1 - Teams topology*</span></span>

<span data-ttu-id="22a51-178">请注意:</span><span class="sxs-lookup"><span data-stu-id="22a51-178">Note that:</span></span>

- <span data-ttu-id="22a51-179">上图中箭头的方向反映了在企业外围环境中影响连接的通信的初始方向。</span><span class="sxs-lookup"><span data-stu-id="22a51-179">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="22a51-180">在 UDP for media 的情况下, 第一个数据包可能沿相反方向流动, 但这些数据包可能会被阻止, 直到其他方向的数据包才会流动。</span><span class="sxs-lookup"><span data-stu-id="22a51-180">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>
- <span data-ttu-id="22a51-181">团队与 Skype for Business Online 并排部署, 因此客户将显示为 "团队/SFB 用户"。</span><span class="sxs-lookup"><span data-stu-id="22a51-181">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user".</span></span>

<span data-ttu-id="22a51-182">有关详细信息, 请查看本文后面的以下可选拓扑:</span><span class="sxs-lookup"><span data-stu-id="22a51-182">You can find more information on the following optional topologies later in the article:</span></span>

- <span data-ttu-id="22a51-183">在**团队混合拓扑**中介绍了 Skype for business 内部部署。</span><span class="sxs-lookup"><span data-stu-id="22a51-183">Skype for Business on-premises deployment is described in **Teams  hybrid topology**.</span></span>
- <span data-ttu-id="22a51-184">手机系统直接路由 (适用于 PSTN 连接) 在**具有直接路由拓扑的团队**中介绍。</span><span class="sxs-lookup"><span data-stu-id="22a51-184">Phone System Direct Routing (for PSTN connectivity) is described in **Teams with Direct Routing topology**.</span></span>
- <span data-ttu-id="22a51-185">快速路线在**具有 Express 路线优化的团队**中介绍。</span><span class="sxs-lookup"><span data-stu-id="22a51-185">Express Route is described in  **Teams with Express Route optimization**.</span></span>

<span data-ttu-id="22a51-186">**流说明**:</span><span class="sxs-lookup"><span data-stu-id="22a51-186">**Flow descriptions**:</span></span>
- <span data-ttu-id="22a51-187">**流 2** -表示用户在客户网络上作为用户团队体验的一部分启动的流程。</span><span class="sxs-lookup"><span data-stu-id="22a51-187">**Flow 2** – Represents a flow initiated by a user on the customer network to the Internet as a part of the user's Teams experience.</span></span> <span data-ttu-id="22a51-188">这些流的示例是 DNS 和对等媒体。</span><span class="sxs-lookup"><span data-stu-id="22a51-188">Examples of these flows are DNS and peer-to-peer media.</span></span>
- <span data-ttu-id="22a51-189">**流 2 "** –表示由远程移动团队用户发起的流, 其中包含指向客户网络的 VPN。</span><span class="sxs-lookup"><span data-stu-id="22a51-189">**Flow 2'** – Represents a flow initiated by a remote mobile Teams user, with VPN to the customer network.</span></span> 
- <span data-ttu-id="22a51-190">**流 3** -表示由远程移动团队用户从 Office 365/团队终结点发起的流。</span><span class="sxs-lookup"><span data-stu-id="22a51-190">**Flow 3** – Represents a flow initiated by a remote mobile Teams user to Office 365/Teams endpoints.</span></span> 
- <span data-ttu-id="22a51-191">**流 4** -表示用户在客户网络上由 Office 365/团队终结点发起的流程。</span><span class="sxs-lookup"><span data-stu-id="22a51-191">**Flow 4** – Represents a flow initiated by a user on the customer network to Office 365/Teams endpoints.</span></span>
- <span data-ttu-id="22a51-192">**流 5** -表示团队用户与其他团队之间的对等媒体流, 或客户网络中的 Skype for business 用户。</span><span class="sxs-lookup"><span data-stu-id="22a51-192">**Flow 5** – Represents a peer-to-peer media flow between a Teams user and another Teams or Skype for Business user within the customer network.</span></span>
- <span data-ttu-id="22a51-193">**流 6** -表示远程移动团队用户与其他远程移动团队或 Internet 上的 Skype for business 用户之间的对等媒体流。</span><span class="sxs-lookup"><span data-stu-id="22a51-193">**Flow 6** – Represents a peer-to-peer media flow between a remote mobile Teams user and another remote mobile Teams or Skype for Business user over the Internet.</span></span>

#### <a name="use-case-one-to-one"></a><span data-ttu-id="22a51-194">使用案例: 一对一</span><span class="sxs-lookup"><span data-stu-id="22a51-194">Use case: One-to-one</span></span>
<span data-ttu-id="22a51-195">一对一呼叫使用一个通用模型, 在该模型中, 呼叫者将获得一组候选项, 其中包含 IP 地址/端口, 包括本地、中继和反身 (客户的公共 IP 地址, 如中继) 候选人。</span><span class="sxs-lookup"><span data-stu-id="22a51-195">One-to-one calls use a common model in which the caller will obtain a set of candidates consisting of IP addresses/ports--including local, relay, and reflexive (public IP address of client as seen by the relay) candidates.</span></span> <span data-ttu-id="22a51-196">呼叫方将这些候选人发送给被呼叫方;被呼叫方还会获取一组类似的候选项, 并将其发送给呼叫方。</span><span class="sxs-lookup"><span data-stu-id="22a51-196">The caller sends these candidates to the called party; the called party also obtains a similar set of candidates and sends them to the caller.</span></span> <span data-ttu-id="22a51-197">STUN 连接检查消息用于查找哪些呼叫方/被叫方媒体路径正常工作, 并且选择了最佳工作路径。</span><span class="sxs-lookup"><span data-stu-id="22a51-197">STUN connectivity check messages are used to find which caller/called party media paths work, and the best working path is selected.</span></span> <span data-ttu-id="22a51-198">然后, 将使用所选候选人对发送媒体 (即, 通过 SRTP 保护的 RTP/RTCP 数据包)。</span><span class="sxs-lookup"><span data-stu-id="22a51-198">Media (that is, RTP/RTCP packets secured via SRTP) are then sent using the selected candidate pair.</span></span> <span data-ttu-id="22a51-199">传输中继作为 Office 365 的一部分进行部署。</span><span class="sxs-lookup"><span data-stu-id="22a51-199">The Transport relay is deployed as part of Office 365.</span></span>

<span data-ttu-id="22a51-200">如果本地 IP 地址/端口候选或反身候选具有连接, 则将为媒体选择客户端 (或通过 NAT) 之间的直接路径。</span><span class="sxs-lookup"><span data-stu-id="22a51-200">If the local IP address/port candidates or the reflexive candidates have connectivity, then the direct path between the clients (or via a NAT) will be selected for media.</span></span> <span data-ttu-id="22a51-201">如果客户端位于客户网络上, 则应选择直接路径。</span><span class="sxs-lookup"><span data-stu-id="22a51-201">If the clients are both on the customer network, then the direct path should be selected.</span></span> <span data-ttu-id="22a51-202">这需要客户网络内的直接 UDP 连接。</span><span class="sxs-lookup"><span data-stu-id="22a51-202">This requires direct UDP connectivity within the customer network.</span></span> <span data-ttu-id="22a51-203">如果客户端都是 nomadic 云用户, 则根据 NAT/防火墙, 媒体可能使用直接连接。</span><span class="sxs-lookup"><span data-stu-id="22a51-203">If the clients are both nomadic cloud users, then depending on the NAT/firewall, media may use direct connectivity.</span></span>

<span data-ttu-id="22a51-204">如果一个客户端是客户网络内部的客户端, 而另一个客户端是外部客户端 (例如, 移动云用户), 则本地或反身候选人之间的直接连接不太可能是正常工作。</span><span class="sxs-lookup"><span data-stu-id="22a51-204">If one client is internal on the customer network and one client is external (for example, a mobile cloud user), then it is unlikely that direct connectivity between the local or reflexive candidates is working.</span></span> <span data-ttu-id="22a51-205">在这种情况下, 选项是使用来自任何客户端的传输中继候选人之一 (例如, 内部客户从 Office 365 中的传输中继获得中继候选人; 外部客户端需要能够将 STUN/RTP/RTCP 数据包发送到传输中继)。</span><span class="sxs-lookup"><span data-stu-id="22a51-205">In this case, an option is to use one of the Transport Relay candidates from either client (for example, the internal client obtained a relay candidate from the Transport relay in Office 365; the external client needs to be able to send STUN/RTP/RTCP packets to the transport relay).</span></span> <span data-ttu-id="22a51-206">另一个选项是内部客户端发送到移动云客户端获取的中继候选人。</span><span class="sxs-lookup"><span data-stu-id="22a51-206">Another option is the internal client sends to the relay candidate obtained by the mobile cloud client.</span></span> <span data-ttu-id="22a51-207">请注意, 虽然强烈建议媒体的 UDP 连接, 但支持 TCP。</span><span class="sxs-lookup"><span data-stu-id="22a51-207">Note that, although UDP connectivity for media is highly recommended, TCP is supported.</span></span>

<span data-ttu-id="22a51-208">**高级别步骤**:</span><span class="sxs-lookup"><span data-stu-id="22a51-208">**High-level steps**:</span></span>
1. <span data-ttu-id="22a51-209">团队用户 A 通过 flow2 解析 URL 域名 (DNS)</span><span class="sxs-lookup"><span data-stu-id="22a51-209">Teams User A resolves URL domain name (DNS) via flow2</span></span>
2. <span data-ttu-id="22a51-210">团队用户 A 通过流量4在团队传输中继上分配媒体中继端口</span><span class="sxs-lookup"><span data-stu-id="22a51-210">Teams User A allocates a media Relay port on Teams Transport Relay via flow 4</span></span>
3. <span data-ttu-id="22a51-211">团队用户 A 通过从候选人候选人发送 "邀请", 从流4到 Office 365</span><span class="sxs-lookup"><span data-stu-id="22a51-211">Teams User A sends "invite" with ICE candidates via flow 4 to Office 365</span></span>
4. <span data-ttu-id="22a51-212">Office 365 通过流量4向团队用户 B 发送通知</span><span class="sxs-lookup"><span data-stu-id="22a51-212">Office 365 sends notification to Teams User B via flow 4</span></span>
5. <span data-ttu-id="22a51-213">团队用户 B 通过流量4在团队传输中继上分配媒体中继端口</span><span class="sxs-lookup"><span data-stu-id="22a51-213">Teams User B allocates a media Relay port on Teams Transport Relay via flow 4</span></span>
6. <span data-ttu-id="22a51-214">团队用户 B 通过流4通过流4发送 "答案", 通过流4向团队用户 A 转发给团队用户 A。</span><span class="sxs-lookup"><span data-stu-id="22a51-214">Teams User B sends "answer" with ICE candidates via flow 4, which is forwarded back to Teams User A via Flow 4</span></span>
7. <span data-ttu-id="22a51-215">团队用户 A 和团队用户 B 调用 ICE 连接测试, 并选择最佳可用媒体路径 (请参阅下面的各种使用案例的图表)</span><span class="sxs-lookup"><span data-stu-id="22a51-215">Teams User A and Teams User B invoke ICE connectivity tests and the best available media path is selected (see diagrams below for various use cases)</span></span>
8. <span data-ttu-id="22a51-216">团队用户通过流量4向 Office 365 发送遥测</span><span class="sxs-lookup"><span data-stu-id="22a51-216">Teams Users send telemetry to Office 365 via flow 4</span></span>

<span data-ttu-id="22a51-217">**在客户网络中:**</span><span class="sxs-lookup"><span data-stu-id="22a51-217">**Within customer network:**</span></span>

<span data-ttu-id="22a51-218">[![Microsoft 团队在线通话流程图02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-218">[![Microsoft Teams Online Call Flows Figure 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span></span>

<span data-ttu-id="22a51-219">*图 2-客户网络内部*</span><span class="sxs-lookup"><span data-stu-id="22a51-219">*Figure 2 - Within customer network*</span></span>
 
<span data-ttu-id="22a51-220">在步骤7中, 选择了 "对等媒体流 5"。</span><span class="sxs-lookup"><span data-stu-id="22a51-220">In step 7, peer-to-peer media flow 5 is selected.</span></span>
 
<span data-ttu-id="22a51-221">媒体为双向媒体。</span><span class="sxs-lookup"><span data-stu-id="22a51-221">Media is bidirectional.</span></span> <span data-ttu-id="22a51-222">流5的方向表示, 一方从连接的角度启动通信, 与本文档中的所有流一致。</span><span class="sxs-lookup"><span data-stu-id="22a51-222">The direction of flow 5 indicates that one side initiates the communication from a connectivity perspective, consistent with all the flows in this document.</span></span> <span data-ttu-id="22a51-223">在这种情况下, 使用哪个方向无关紧要, 因为这两个终结点位于客户网络内。</span><span class="sxs-lookup"><span data-stu-id="22a51-223">In this case, it doesn't matter which direction is used because both endpoints are within the customer network.</span></span>

<span data-ttu-id="22a51-224">**向外部用户的客户网络 (按团队传输中继的媒体中继):**</span><span class="sxs-lookup"><span data-stu-id="22a51-224">**Customer network to external user (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="22a51-225">[![Microsoft 团队在线通话流程图03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-225">[![Microsoft Teams Online Call Flows Figure 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span></span>

<span data-ttu-id="22a51-226">*图 3-向外部用户 (按团队传输中继的媒体中继) 的客户网络*</span><span class="sxs-lookup"><span data-stu-id="22a51-226">*Figure 3 - Customer network to external user (media relayed by Teams Transport Relay)*</span></span>
 
<span data-ttu-id="22a51-227">在步骤 7 (从客户网络到 Office 365) 和流程 3 (从 "远程移动团队用户到 Office 365") 中, 选择 "流程 4"。</span><span class="sxs-lookup"><span data-stu-id="22a51-227">In step 7, flow 4, from customer network to Office 365, and flow 3, from remote mobile Teams user to Office 365, are selected.</span></span> <span data-ttu-id="22a51-228">这些流程由 Office 365 中的团队传输中继进行中继。</span><span class="sxs-lookup"><span data-stu-id="22a51-228">These flows are relayed by Teams Transport Relay within Office 365.</span></span>

<span data-ttu-id="22a51-229">媒体是双向的, 其中, 方向指示哪一侧从连接的角度开始通信。</span><span class="sxs-lookup"><span data-stu-id="22a51-229">Media is bidirectional, where direction indicates which side initiates the communication from a connectivity perspective.</span></span> <span data-ttu-id="22a51-230">在这种情况下, 这些流程通过不同的传输协议和地址用于发送信号和媒体。</span><span class="sxs-lookup"><span data-stu-id="22a51-230">In this case, these flows are used for signaling and media, via different transport protocols and addresses.</span></span>

<span data-ttu-id="22a51-231">**向外部用户 (直接媒体) 的客户网络:**</span><span class="sxs-lookup"><span data-stu-id="22a51-231">**Customer network to external user (direct media):**</span></span>

<span data-ttu-id="22a51-232">[![Microsoft 团队在线通话流程图04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-232">[![Microsoft Teams Online Call Flows Figure 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span></span>

<span data-ttu-id="22a51-233">*图 4-外部用户 (直接媒体) 的客户网络*</span><span class="sxs-lookup"><span data-stu-id="22a51-233">*Figure 4 - Customer network to external user (direct media)*</span></span>
 
<span data-ttu-id="22a51-234">在步骤7中, 选择 "从客户网络到 Internet (客户端对等)" 中的 "流程 2"。</span><span class="sxs-lookup"><span data-stu-id="22a51-234">In step 7, flow 2, from customer network to Internet (client's peer), is selected.</span></span>
- <span data-ttu-id="22a51-235">带有远程移动用户 (即未通过 Office 365 中继) 的直接媒体是可选的。</span><span class="sxs-lookup"><span data-stu-id="22a51-235">Direct media with remote mobile user (that is, not relayed through Office 365) is optional.</span></span> <span data-ttu-id="22a51-236">换句话说, 客户可能会阻止此路径通过 Office 365 中的传输中继强制执行媒体路径。</span><span class="sxs-lookup"><span data-stu-id="22a51-236">In other words, customer may block this path to enforce a media path through Transport Relay in Office 365.</span></span>

- <span data-ttu-id="22a51-237">媒体为双向媒体。</span><span class="sxs-lookup"><span data-stu-id="22a51-237">Media is bidirectional.</span></span> <span data-ttu-id="22a51-238">流2到远程移动用户的方向指示一方从连接的角度启动通信。</span><span class="sxs-lookup"><span data-stu-id="22a51-238">The direction of flow 2 to remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span> 

<span data-ttu-id="22a51-239">**VPN 用户到内部用户 (按团队传输中继的媒体中转)**</span><span class="sxs-lookup"><span data-stu-id="22a51-239">**VPN user to internal user (media relayed by Teams Transport Relay)**</span></span>

<span data-ttu-id="22a51-240">[![Microsoft 团队在线通话流程图05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-240">[![Microsoft Teams Online Call Flows Figure 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span></span>

<span data-ttu-id="22a51-241">*图 5-向内部用户 (按团队传输中继的媒体中继) 的 VPN 用户*</span><span class="sxs-lookup"><span data-stu-id="22a51-241">*Figure 5 - VPN user to internal user (media relayed by Teams Transport Relay)*</span></span>
 
<span data-ttu-id="22a51-242">VPN 与客户网络之间的信号传输是通过流程2。</span><span class="sxs-lookup"><span data-stu-id="22a51-242">Signaling between the VPN to the customer network is via flow 2'.</span></span> <span data-ttu-id="22a51-243">客户网络与 Office 365 之间的信号信号是通过流量4进行的。</span><span class="sxs-lookup"><span data-stu-id="22a51-243">Signaling between the customer network and Office 365 is via flow 4.</span></span> <span data-ttu-id="22a51-244">但是, 媒体绕过 VPN, 并通过流3和4通过 Office 365 中的团队媒体中继进行路由。</span><span class="sxs-lookup"><span data-stu-id="22a51-244">However, media bypasses the VPN and is routed via flows 3 and 4 through Teams media relay in Office 365.</span></span>

<span data-ttu-id="22a51-245">**VPN 用户到内部用户 (直接媒体)**</span><span class="sxs-lookup"><span data-stu-id="22a51-245">**VPN user to internal user (direct media)**</span></span>

<span data-ttu-id="22a51-246">[![Microsoft 团队在线通话流程图06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-246">[![Microsoft Teams Online Call Flows Figure 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span></span>

<span data-ttu-id="22a51-247">*图 6-向内部用户 (直接媒体) 的 VPN 用户*</span><span class="sxs-lookup"><span data-stu-id="22a51-247">*Figure 6 - VPN user to internal user (direct media)*</span></span>

<span data-ttu-id="22a51-248">VPN 与客户网络之间的信号传输是通过流程2。</span><span class="sxs-lookup"><span data-stu-id="22a51-248">Signaling between the VPN to the customer network is via flow 2'.</span></span> <span data-ttu-id="22a51-249">客户网络与 Office 365 之间的信号信号是通过流量4进行的。</span><span class="sxs-lookup"><span data-stu-id="22a51-249">Signaling between the customer network and Office 365 is via flow 4.</span></span> <span data-ttu-id="22a51-250">但是, 媒体绕过 VPN, 并通过从客户网络到 Internet 的流程2路由。</span><span class="sxs-lookup"><span data-stu-id="22a51-250">However, media bypasses the VPN and is routed via flow 2 from the customer network to the Internet.</span></span>

<span data-ttu-id="22a51-251">媒体为双向媒体。</span><span class="sxs-lookup"><span data-stu-id="22a51-251">Media is bidirectional.</span></span> <span data-ttu-id="22a51-252">流2到远程移动用户的方向指示一方从连接的角度启动通信。</span><span class="sxs-lookup"><span data-stu-id="22a51-252">The direction of flow 2 to the remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

<span data-ttu-id="22a51-253">**向外部用户 (直接媒体) 的 VPN 用户**</span><span class="sxs-lookup"><span data-stu-id="22a51-253">**VPN user to external user (direct media)**</span></span>

<span data-ttu-id="22a51-254">[![Microsoft 团队通话流程图07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-254">[![Microsoft Teams call flows Figure 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span></span>

<span data-ttu-id="22a51-255">*图 7-向外部用户 (直接媒体) 的 VPN 用户*</span><span class="sxs-lookup"><span data-stu-id="22a51-255">*Figure 7 - VPN user to external user (direct media)*</span></span>

<span data-ttu-id="22a51-256">VPN 用户与客户网络之间的信号传送方式是通过流 2 "和从流4到 Office 365。</span><span class="sxs-lookup"><span data-stu-id="22a51-256">Signaling between the VPN user to the customer network is via flow 2' and via flow 4 to Office 365.</span></span> <span data-ttu-id="22a51-257">但是, 媒体绕过 VPN 并通过流6路由。</span><span class="sxs-lookup"><span data-stu-id="22a51-257">However, media bypasses VPN and is routed via flow 6.</span></span>

<span data-ttu-id="22a51-258">媒体为双向媒体。</span><span class="sxs-lookup"><span data-stu-id="22a51-258">Media is bidirectional.</span></span> <span data-ttu-id="22a51-259">流6到远程移动用户的方向指示一方从连接的角度启动通信。</span><span class="sxs-lookup"><span data-stu-id="22a51-259">The direction of flow 6 to the remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

#### <a name="use-case-teams-to-pstn-through-office-365-trunk"></a><span data-ttu-id="22a51-260">使用案例: 团队到 PSTN 通过 Office 365 主干</span><span class="sxs-lookup"><span data-stu-id="22a51-260">Use Case: Teams to PSTN through Office 365 Trunk</span></span>
<span data-ttu-id="22a51-261">Office 365 具有一个电话系统, 允许从公共交换电话网络 (PSTN) 拨打和接听电话。</span><span class="sxs-lookup"><span data-stu-id="22a51-261">Office 365 has a Phone System that allows placing and receiving calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="22a51-262">如果 PSTN 主干通过电话系统呼叫计划连接, 则此使用情形没有特殊的连接要求。</span><span class="sxs-lookup"><span data-stu-id="22a51-262">If the PSTN trunk is connected via the Phone System Calling Plan, then there are no special connectivity requirements for this use case.</span></span> <span data-ttu-id="22a51-263">(如果要将自己的本地 PSTN 主干连接到 Office 365, 可以使用 "电话系统直接路由"。)</span><span class="sxs-lookup"><span data-stu-id="22a51-263">(If you want to connect your own on-premises PSTN trunk to Office 365, you can use Phone System Direct Routing.)</span></span>

<span data-ttu-id="22a51-264">[![Microsoft 团队在线通话流程 (见图 08)](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-264">[![Microsoft Teams Online Call Flows Figure 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span></span>

<span data-ttu-id="22a51-265">*图 8-通过 Office 365 主干的团队到 PSTN*</span><span class="sxs-lookup"><span data-stu-id="22a51-265">*Figure 8 - Teams to PSTN through Office 365 Trunk*</span></span>

#### <a name="use-case-teams-meeting"></a><span data-ttu-id="22a51-266">使用案例: 团队会议</span><span class="sxs-lookup"><span data-stu-id="22a51-266">Use Case: Teams Meeting</span></span>

<span data-ttu-id="22a51-267">音频/视频/屏幕共享 (VBSS) 会议服务器是 Office 365 的一部分。</span><span class="sxs-lookup"><span data-stu-id="22a51-267">The audio/video/screen sharing (VBSS) conferencing server is part of Office 365.</span></span> <span data-ttu-id="22a51-268">它具有必须可从客户网络访问且必须可从 Nomadic 云客户端访问的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="22a51-268">It has a public IP address that must be reachable from the customer network and must be reachable from a Nomadic Cloud client.</span></span> <span data-ttu-id="22a51-269">每个客户端/终结点都需要能够连接到会议服务器。</span><span class="sxs-lookup"><span data-stu-id="22a51-269">Each client/endpoint needs to be able to connect to the conferencing server.</span></span>

<span data-ttu-id="22a51-270">内部客户将按照与一对一通话描述的相同方式获取本地、反身和中继候选人。</span><span class="sxs-lookup"><span data-stu-id="22a51-270">Internal clients will obtain local, reflexive, and relay candidates in the same manner as described for one-to-one calls.</span></span> <span data-ttu-id="22a51-271">客户端会将这些候选人发送到邀请中的会议服务器。</span><span class="sxs-lookup"><span data-stu-id="22a51-271">The clients will send these candidates to the conferencing server in an invite.</span></span> <span data-ttu-id="22a51-272">会议服务器不使用中继, 因为它具有可公开访问的 IP 地址, 因此它将通过其本地 IP 地址候选进行响应。</span><span class="sxs-lookup"><span data-stu-id="22a51-272">The conferencing server does not use a relay since it has a publicly reachable IP address, so it responds with its local IP address candidate.</span></span> <span data-ttu-id="22a51-273">客户端和会议服务器将以与一对一呼叫描述的相同方式检查连接。</span><span class="sxs-lookup"><span data-stu-id="22a51-273">The client and conferencing server will check connectivity in the same manner described for one-to-one calls.</span></span> 

<span data-ttu-id="22a51-274">请注意:</span><span class="sxs-lookup"><span data-stu-id="22a51-274">Note that:</span></span>

- <span data-ttu-id="22a51-275">团队客户端无法加入 Skype for Business 会议, 并且 Skype for business 客户端无法加入团队会议。</span><span class="sxs-lookup"><span data-stu-id="22a51-275">Teams clients cannot join Skype for Business meetings, and Skype for Business clients cannot join Teams meetings.</span></span>

- <span data-ttu-id="22a51-276">PSTN 用户可以选择 "拨入" 或 "拨出", 具体取决于会议的组织者 PSTN 呼叫和/或会议设置。</span><span class="sxs-lookup"><span data-stu-id="22a51-276">A PSTN user optionally "Dials IN" or "Dialed OUT", depending on the meeting's organizer PSTN Calling and/or conferencing provisioning.</span></span> 

- <span data-ttu-id="22a51-277">来宾用户或客户用户可以通过具有严格规则的 FW/NAT 保护的来宾专用网络进行联接。</span><span class="sxs-lookup"><span data-stu-id="22a51-277">A guest user or a customer user may join from a guest private network, which is protected via FW/NAT with strict rules.</span></span>

<span data-ttu-id="22a51-278">[![Microsoft 团队在线通话流程图09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-278">[![Microsoft Teams Online Call Flows Figure 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span></span>

<span data-ttu-id="22a51-279">*图 9-团队会议*</span><span class="sxs-lookup"><span data-stu-id="22a51-279">*Figure 9 - Teams Meeting*</span></span>

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a><span data-ttu-id="22a51-280">使用案例: 使用 Skype for business 内部部署联盟</span><span class="sxs-lookup"><span data-stu-id="22a51-280">Use Case: Federation with Skype for Business on premises</span></span>

<span data-ttu-id="22a51-281">**按团队在 Office 365 中传输中继的媒体中继**</span><span class="sxs-lookup"><span data-stu-id="22a51-281">**Media relayed by Teams Transport Relay in Office 365**</span></span>

<span data-ttu-id="22a51-282">[![Microsoft 团队在线通话流程图10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-282">[![Microsoft Teams Online Call Flows Figure 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span></span>

<span data-ttu-id="22a51-283">*图 10-按组在 Office 365 中传输中继的媒体中继*</span><span class="sxs-lookup"><span data-stu-id="22a51-283">*Figure 10 - Media relayed by Teams Transport Relay in Office 365*</span></span>

<span data-ttu-id="22a51-284">请注意:</span><span class="sxs-lookup"><span data-stu-id="22a51-284">Note that:</span></span>

- <span data-ttu-id="22a51-285">根据定义, 联盟是两个租户之间的通信。</span><span class="sxs-lookup"><span data-stu-id="22a51-285">Federation is, by definition, a communication between two tenants.</span></span> <span data-ttu-id="22a51-286">在这种情况下, 租户 A 使用团队, federates 与租户 B 一起使用 Skype for Business 内部部署。</span><span class="sxs-lookup"><span data-stu-id="22a51-286">In this case, tenant A, which uses Teams, federates with tenant B, which uses Skype for Business on premises.</span></span> <span data-ttu-id="22a51-287">如果租户 B 也使用的是 Office 365, 则 Skype for Business 客户端将使用流3与 Office 365 连接。</span><span class="sxs-lookup"><span data-stu-id="22a51-287">If tenant B is also using Office 365, then the Skype for Business client would have used flow 3 to connect with Office 365.</span></span>

- <span data-ttu-id="22a51-288">来自联合 Skype for business 客户端到本地 Skype for Business 服务器的信号和媒体已超出本文档的范围。</span><span class="sxs-lookup"><span data-stu-id="22a51-288">Signaling and media from the federated Skype for Business client to on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="22a51-289">但是, 此处对此进行了明确说明。</span><span class="sxs-lookup"><span data-stu-id="22a51-289">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="22a51-290">团队和 Skype for business 之间的信号由 Office 365 中的网关桥接。</span><span class="sxs-lookup"><span data-stu-id="22a51-290">Signaling between Teams and Skype for Business is bridged by a gateway in Office 365.</span></span>

- <span data-ttu-id="22a51-291">在此情况下, 媒体由团队将 Office 365 中的传输传输到客户网络和通过流4远程 Skype for Business 客户端进行中继。</span><span class="sxs-lookup"><span data-stu-id="22a51-291">Media in this case is relayed by Teams Transport Relay in Office 365 to the customer network and remote Skype for Business client via flow 4.</span></span>

<span data-ttu-id="22a51-292">**联合租户中 Skype for business Media 中继的媒体中继**</span><span class="sxs-lookup"><span data-stu-id="22a51-292">**Media relayed by Skype for Business Media Relay in federated tenant**</span></span>

<span data-ttu-id="22a51-293">[![Microsoft 团队在线通话流程图11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-293">[![Microsoft Teams Online Call Flows Figure 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span></span>

<span data-ttu-id="22a51-294">*图 11-联合租户中 Skype for business Media 中继的媒体中继*</span><span class="sxs-lookup"><span data-stu-id="22a51-294">*Figure 11 - Media relayed by Skype for Business Media Relay in federated tenant*</span></span>

<span data-ttu-id="22a51-295">请注意:</span><span class="sxs-lookup"><span data-stu-id="22a51-295">Note that:</span></span>

- <span data-ttu-id="22a51-296">从联合 Skype for business 客户端到本地 Skype for Business 服务器的信号和媒体已超出本文档的范围。</span><span class="sxs-lookup"><span data-stu-id="22a51-296">Signaling and media from the federated Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="22a51-297">但是, 此处对此进行了明确说明。</span><span class="sxs-lookup"><span data-stu-id="22a51-297">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="22a51-298">团队和 Skype for business 之间的信号由 Office 365 中的网关桥接。</span><span class="sxs-lookup"><span data-stu-id="22a51-298">Signaling between Teams and Skype for Business is bridged by a Gateway in Office 365.</span></span>

- <span data-ttu-id="22a51-299">在这种情况下, 媒体将由 Skype for business 本地媒体中继中继到通过流2的客户网络。</span><span class="sxs-lookup"><span data-stu-id="22a51-299">Media in this case is relayed by Skype for Business on-premises Media Relay to the customer network via flow 2.</span></span> <span data-ttu-id="22a51-300">(请注意, "媒体中继" 中来自团队用户到远程媒体中继的流量最初将由媒体中继阻止, 直到流处于相反方向。</span><span class="sxs-lookup"><span data-stu-id="22a51-300">(Note that traffic from Teams user to the remote Media Relay in the federated customer network will be initially blocked by the Media Relay until traffic in the reverse direction starts to flow.</span></span> <span data-ttu-id="22a51-301">但是, 双向流将以两种方向打开连接。)</span><span class="sxs-lookup"><span data-stu-id="22a51-301">However, the bidirectional flow will open connectivity in both directions.)</span></span>

<span data-ttu-id="22a51-302">**直接 (对等)**</span><span class="sxs-lookup"><span data-stu-id="22a51-302">**Direct (peer-to-peer)**</span></span>

<span data-ttu-id="22a51-303">[![Microsoft 团队在线通话流程图12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-303">[![Microsoft Teams Online Call Flows Figure 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span></span>

<span data-ttu-id="22a51-304">*图 12-直接 (对等)*</span><span class="sxs-lookup"><span data-stu-id="22a51-304">*Figure 12 - Direct (peer-to-peer)*</span></span>

### <a name="teams-hybrid-topology"></a><span data-ttu-id="22a51-305">团队混合拓扑</span><span class="sxs-lookup"><span data-stu-id="22a51-305">Teams hybrid topology</span></span>
<span data-ttu-id="22a51-306">此拓扑包括具有 Skype for Business 内部部署的团队。</span><span class="sxs-lookup"><span data-stu-id="22a51-306">This topology includes Teams with a Skype for Business on-premises deployment.</span></span>

<span data-ttu-id="22a51-307">[![Microsoft 团队在线通话流程图13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-307">[![Microsoft Teams Online Call Flows Figure 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span></span>

<span data-ttu-id="22a51-308">*图 13-团队混合拓扑*</span><span class="sxs-lookup"><span data-stu-id="22a51-308">*Figure 13 - Teams hybrid topology*</span></span>
 
- <span data-ttu-id="22a51-309">上图中箭头的方向反映了在企业外围环境中影响连接的通信的初始方向。</span><span class="sxs-lookup"><span data-stu-id="22a51-309">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="22a51-310">在 UDP for media 的情况下, 第一个数据包可能沿相反方向流动, 但这些数据包可能会被阻止, 直到其他方向的数据包才会流动。</span><span class="sxs-lookup"><span data-stu-id="22a51-310">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>

- <span data-ttu-id="22a51-311">团队与 Skype for Business Online 并排部署, 因此客户将显示为 "团队/SFB 用户"。</span><span class="sxs-lookup"><span data-stu-id="22a51-311">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user".</span></span>

<span data-ttu-id="22a51-312">其他流 (在团队拓扑之上):</span><span class="sxs-lookup"><span data-stu-id="22a51-312">Additional flows (on top of Teams topology):</span></span>
- <span data-ttu-id="22a51-313">**流 5a** –表示客户网络中的团队用户之间的对等媒体流和客户网络边缘的 Skype for business 本地媒体中继。</span><span class="sxs-lookup"><span data-stu-id="22a51-313">**Flow 5A** – Represents a peer-to-peer media flow between a Teams user within the customer network and a Skype for Business on-premises media relay at the customer network edge.</span></span>

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a><span data-ttu-id="22a51-314">使用案例: 团队到 Skype for business 一对一</span><span class="sxs-lookup"><span data-stu-id="22a51-314">Use Case: Teams to Skype for Business one-to-one</span></span>
<span data-ttu-id="22a51-315">**客户网络中的混合**</span><span class="sxs-lookup"><span data-stu-id="22a51-315">**Hybrid within the customer network**</span></span>

<span data-ttu-id="22a51-316">[![Microsoft 团队在线通话流程图14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-316">[![Microsoft Teams Online Call Flows Figure 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span></span>

<span data-ttu-id="22a51-317">*图 14-客户网络中的混合*</span><span class="sxs-lookup"><span data-stu-id="22a51-317">*Figure 14 - Hybrid within customer network*</span></span>
 
<span data-ttu-id="22a51-318">团队和 Skype for business 之间的信号由 Office 365 中的网关桥接。</span><span class="sxs-lookup"><span data-stu-id="22a51-318">Signaling between Teams and Skype for Business is bridged by a gateway in Office 365.</span></span> <span data-ttu-id="22a51-319">但是, 媒体在客户网络中通过流量5直接路由到对等。</span><span class="sxs-lookup"><span data-stu-id="22a51-319">However, media is routed directly peer-to-peer within the customer network via flow 5.</span></span>

<span data-ttu-id="22a51-320">**具有外部 Skype for Business 用户的混合客户网络-由 Office 365 中继**</span><span class="sxs-lookup"><span data-stu-id="22a51-320">**Hybrid customer network with external Skype for Business user – relayed by Office 365**</span></span>

<span data-ttu-id="22a51-321">[![Microsoft 团队在线通话流程图15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-321">[![Microsoft Teams Online Call Flows Figure 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span></span>

<span data-ttu-id="22a51-322">*图 15-使用外部 Skype for Business 用户的混合客户网络-由 Office 365 进行中继*</span><span class="sxs-lookup"><span data-stu-id="22a51-322">*Figure 15 - Hybrid customer network with external Skype for Business user - relayed by Office 365*</span></span>

<span data-ttu-id="22a51-323">请注意:</span><span class="sxs-lookup"><span data-stu-id="22a51-323">Note that:</span></span>

- <span data-ttu-id="22a51-324">从 Skype for business 客户端到本地 Skype for Business 服务器的信号和媒体已超出本文档的范围。</span><span class="sxs-lookup"><span data-stu-id="22a51-324">Signaling and media from the Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="22a51-325">但是, 此处对此进行了明确说明。</span><span class="sxs-lookup"><span data-stu-id="22a51-325">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="22a51-326">团队和 Skype for business 之间的信号由 Office 365 中的网关桥接。</span><span class="sxs-lookup"><span data-stu-id="22a51-326">Signaling between Teams and Skype for Business is bridged by a gateway in Office 365.</span></span>

- <span data-ttu-id="22a51-327">媒体通过团队将 Office 365 中的中继传输到流4中的客户网络来进行中继。</span><span class="sxs-lookup"><span data-stu-id="22a51-327">Media is relayed through Teams Transport Relay in Office 365 to the customer network through flow 4.</span></span>

<span data-ttu-id="22a51-328">**具有外部 Skype for Business 用户的混合客户网络-通过本地边缘进行中继**</span><span class="sxs-lookup"><span data-stu-id="22a51-328">**Hybrid customer network with external Skype for Business user – relayed by on-premises Edge**</span></span>

<span data-ttu-id="22a51-329">[![Microsoft 团队在线通话流程图16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-329">[![Microsoft Teams Online Call Flows Figure 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span></span>

<span data-ttu-id="22a51-330">*图 16-具有外部 Skype for Business 用户的混合客户网络-通过本地边缘进行中继*</span><span class="sxs-lookup"><span data-stu-id="22a51-330">*Figure 16 - Hybrid customer network with external Skype for Business user - relayed by on-premises Edge*</span></span>
 
<span data-ttu-id="22a51-331">请注意:</span><span class="sxs-lookup"><span data-stu-id="22a51-331">Note that:</span></span>

- <span data-ttu-id="22a51-332">从 Skype for business 客户端到本地 Skype for Business 服务器的信号和媒体已超出本文档的范围。</span><span class="sxs-lookup"><span data-stu-id="22a51-332">Signaling and media from Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="22a51-333">但是, 此处对此进行了明确说明。</span><span class="sxs-lookup"><span data-stu-id="22a51-333">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="22a51-334">信号由 Office 365 中的网关桥接。</span><span class="sxs-lookup"><span data-stu-id="22a51-334">Signaling is bridged by a gateway in Office 365.</span></span>

- <span data-ttu-id="22a51-335">Skype for business Media 中继中的 skype for business Media 中继可通过媒体流5A 将媒体转发给客户网络中的团队用户。</span><span class="sxs-lookup"><span data-stu-id="22a51-335">Media is relayed by Skype for Business Media Relay within Skype for Business on-premises Edge to Teams user within the customer network via media flow 5A.</span></span>

### <a name="teams-with-phone-system-direct-routing-topology"></a><span data-ttu-id="22a51-336">具有手机系统直接路由拓扑的团队</span><span class="sxs-lookup"><span data-stu-id="22a51-336">Teams with Phone System Direct Routing topology</span></span>
<span data-ttu-id="22a51-337">此拓扑包括具有手机系统直接路由的团队。</span><span class="sxs-lookup"><span data-stu-id="22a51-337">This topology includes Teams with Phone System Direct Routing.</span></span> 

<span data-ttu-id="22a51-338">直接路由使你能够通过将支持的本地客户拥有的会话边界控制器 (SBC) 硬件设备与 Office 365 配对, 然后将电话服务主干连接到该服务提供商, 从而使用第三方公共交换电话网络 (PSTN) 服务提供商该设备。</span><span class="sxs-lookup"><span data-stu-id="22a51-338">Direct Routing enables you to use a third-party Public Switched Telephone Network (PSTN) service provider by pairing a supported on-premises customer-owned Session Border Controller (SBC) hardware device to Office 365, and then connecting the telephony trunk to that device.</span></span> 

<span data-ttu-id="22a51-339">若要支持此方案, 客户必须部署经认证的 SBC, 以便直接从 Microsoft 认证合作伙伴之一进行路由。</span><span class="sxs-lookup"><span data-stu-id="22a51-339">To support this scenario, the customer must deploy a certified SBC for Direct Routing from one of Microsoft's certified partners.</span></span> <span data-ttu-id="22a51-340">SBC 必须按照供应商的建议进行配置, 并可路由来自 Office 365 的直接 UDP 流量。</span><span class="sxs-lookup"><span data-stu-id="22a51-340">The SBC must be configured as recommended by the vendor, and be routable from Office 365 for direct UDP traffic.</span></span> <span data-ttu-id="22a51-341">媒体可能直接从团队和/或 Skype for business 客户端传递到 SBC (绕过团队网关) 或遍历团队网关。</span><span class="sxs-lookup"><span data-stu-id="22a51-341">The media may flow directly from Teams and/or the Skype for Business client to the SBC (bypassing the Teams gateway) or traverse through the Teams gateway.</span></span> <span data-ttu-id="22a51-342">当主干配置为绕过团队网关时, 与 sbc 的连接是基于 ICE 的, 其中 SBC 支持 ICE, 而团队/Skype for Business media 终结点支持 ICE 完全。</span><span class="sxs-lookup"><span data-stu-id="22a51-342">The connectivity with the SBC, when the trunk is configured to bypass the Teams gateway, is based on ICE, where SBC supports ICE-Lite, while the Teams/Skype for Business media endpoint supports ICE Full.</span></span> 

<span data-ttu-id="22a51-343">[![Microsoft 团队在线通话流程图17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-343">[![Microsoft Teams Online Call Flows Figure 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span></span>

<span data-ttu-id="22a51-344">\* 图 17-具有手机系统直接路由拓扑的团队</span><span class="sxs-lookup"><span data-stu-id="22a51-344">\*Figure 17 - Teams with Phone System Direct Routing topology</span></span>

<span data-ttu-id="22a51-345">请注意:</span><span class="sxs-lookup"><span data-stu-id="22a51-345">Note that:</span></span>

- <span data-ttu-id="22a51-346">上图中箭头的方向反映了在企业外围环境中影响连接的通信的初始方向。</span><span class="sxs-lookup"><span data-stu-id="22a51-346">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="22a51-347">在 UDP for media 的情况下, 第一个数据包可能沿相反方向流动, 但这些数据包可能会被阻止, 直到其他方向的数据包才会流动。</span><span class="sxs-lookup"><span data-stu-id="22a51-347">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>

- <span data-ttu-id="22a51-348">团队与 Skype for Business Online 并排部署, 因此客户将显示为 "团队/SFB 用户"。</span><span class="sxs-lookup"><span data-stu-id="22a51-348">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user".</span></span>

<span data-ttu-id="22a51-349">其他流 (位于团队联机拓扑的顶部):</span><span class="sxs-lookup"><span data-stu-id="22a51-349">Additional flows (on top of Teams online topology):</span></span>
- <span data-ttu-id="22a51-350">**流 4 "** -表示从 Office 365 到客户网络的流, 用于在云中的团队媒体服务器与 SBC 内部部署之间建立连接。</span><span class="sxs-lookup"><span data-stu-id="22a51-350">**Flow 4'** - Represents a flow from Office 365 to the customer network, used to establish a connection between the Teams media server in the cloud with the SBC on premises.</span></span>
- <span data-ttu-id="22a51-351">**流 5b** -表示客户网络中的团队用户之间的媒体流, 在旁路模式下直接路由 SBC。</span><span class="sxs-lookup"><span data-stu-id="22a51-351">**Flow 5B** – Represents a media flow between the Teams user within the customer network with the Direct Routing SBC in bypass mode.</span></span>
- <span data-ttu-id="22a51-352">**流 5c** -表示在 PSTN hairpin 呼叫旁路模式下直接路由 sbc 与另一个直接路由 sbc 之间的媒体流。</span><span class="sxs-lookup"><span data-stu-id="22a51-352">**Flow 5C** – Represents a media flow between the Direct Routing SBC to another Direct Routing SBC in a PSTN hairpin call bypass mode.</span></span>

<span data-ttu-id="22a51-353">**具有直接路由的内部用户 (按团队在 Office 365 中传输中继的媒体中转)**</span><span class="sxs-lookup"><span data-stu-id="22a51-353">**Internal user with Direct Routing (media relayed by Teams Transport Relay in Office 365)**</span></span>

<span data-ttu-id="22a51-354">[![Microsoft 团队在线通话流程图18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-354">[![Microsoft Teams Online Call Flows Figure 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span></span>

<span data-ttu-id="22a51-355">*图 18-直接路由的内部用户 (按团队在 Office 365 中传输中继的媒体中继)*</span><span class="sxs-lookup"><span data-stu-id="22a51-355">*Figure 18 - Internal user with Direct Routing (media relayed by Teams Transport Relay in Office 365)*</span></span>

<span data-ttu-id="22a51-356">请注意:</span><span class="sxs-lookup"><span data-stu-id="22a51-356">Note that:</span></span>
 
- <span data-ttu-id="22a51-357">SBC 必须具有可通过 Office 365 路由的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="22a51-357">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="22a51-358">从 SBC 到 Office 365 的信号和媒体 (反之亦然) 使用流4和/或流4。</span><span class="sxs-lookup"><span data-stu-id="22a51-358">Signaling and media from the SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="22a51-359">从客户网络中的客户端到 Office 365 的信号和媒体使用流4。</span><span class="sxs-lookup"><span data-stu-id="22a51-359">Signaling and media from the client within the customer network to Office 365 use flow 4.</span></span>


<span data-ttu-id="22a51-360">**具有直接路由的远程用户 (通过 Office 365 中的媒体服务器 (MP) 路由媒体)**</span><span class="sxs-lookup"><span data-stu-id="22a51-360">**Remote user with Direct Routing (media is routed through a media server (MP) in Office 365)**</span></span>

<span data-ttu-id="22a51-361">[![Microsoft 团队在线通话流程图19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-361">[![Microsoft Teams Online Call Flows Figure 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span></span>

<span data-ttu-id="22a51-362">*图 19-使用直接路由的远程用户 (通过 Office 365 中的媒体服务器 (MP) 路由媒体)*</span><span class="sxs-lookup"><span data-stu-id="22a51-362">*Figure 19 - Remote user with Direct Routing (media is routed through a media server (MP) in Office 365)*</span></span>
 
<span data-ttu-id="22a51-363">请注意:</span><span class="sxs-lookup"><span data-stu-id="22a51-363">Note that:</span></span>

- <span data-ttu-id="22a51-364">SBC 必须具有可通过 Office 365 路由的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="22a51-364">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="22a51-365">从 SBC 到 Office 365 的信号和媒体 (反之亦然) 使用流4和/或流4。</span><span class="sxs-lookup"><span data-stu-id="22a51-365">Signaling and media from the SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="22a51-366">从 Internet 上的客户端到 Office 365 的信号和媒体使用流程3。</span><span class="sxs-lookup"><span data-stu-id="22a51-366">Signaling and media from the client on the Internet to Office 365 use flow 3.</span></span>

<span data-ttu-id="22a51-367">**内部用户直接路由 (媒体旁路)**</span><span class="sxs-lookup"><span data-stu-id="22a51-367">**Internal user Direct Routing (media bypass)**</span></span>

<span data-ttu-id="22a51-368">[![Microsoft 团队在线通话流程图20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-368">[![Microsoft Teams Online Call Flows Figure 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span></span>

<span data-ttu-id="22a51-369">*图 20-内部用户直接路由 (媒体旁路)*</span><span class="sxs-lookup"><span data-stu-id="22a51-369">*Figure 20 - Internal user Direct Routing (media bypass)*</span></span>
 
<span data-ttu-id="22a51-370">请注意:</span><span class="sxs-lookup"><span data-stu-id="22a51-370">Note that:</span></span>

- <span data-ttu-id="22a51-371">SBC 必须具有可通过 Office 365 路由的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="22a51-371">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="22a51-372">从 SBC 到 Office 365 的信号, 反之亦然, 使用流程4和/或流4。</span><span class="sxs-lookup"><span data-stu-id="22a51-372">Signaling from SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="22a51-373">从客户网络中的客户端发送到 Office 365 的信号使用流4。</span><span class="sxs-lookup"><span data-stu-id="22a51-373">Signaling from client within the customer network to Office 365 use flow 4.</span></span>

- <span data-ttu-id="22a51-374">从客户网络中的客户端到客户网络内的 SBC 的媒体使用流程5B。</span><span class="sxs-lookup"><span data-stu-id="22a51-374">Media from client within the customer network to SBC within the customer network use flow 5B.</span></span>

<span data-ttu-id="22a51-375">**具有直接路由的远程用户 (由团队在 Office 365 中传输中继的媒体绕过中继)**</span><span class="sxs-lookup"><span data-stu-id="22a51-375">**Remote user with Direct Routing (media bypass relayed by Teams Transport Relay in Office 365)**</span></span>

<span data-ttu-id="22a51-376">[![Microsoft 团队在线通话流程图21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-376">[![Microsoft Teams Online Call Flows Figure 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span></span>

<span data-ttu-id="22a51-377">*图 21-使用直接路由的远程用户 (由团队在 Office 365 中传输中继的媒体旁路中继)*</span><span class="sxs-lookup"><span data-stu-id="22a51-377">*Figure 21 - Remote user with Direct Routing (media bypass relayed by Teams Transport Relay in Office 365)*</span></span>

<span data-ttu-id="22a51-378">请注意:</span><span class="sxs-lookup"><span data-stu-id="22a51-378">Note that:</span></span>

- <span data-ttu-id="22a51-379">SBC 必须具有可通过 Office 365 和 Internet 进行路由的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="22a51-379">The SBC must have a public IP address that is routable from Office 365 and Internet.</span></span>

- <span data-ttu-id="22a51-380">从 SBC 到 Office 365 的信号, 反之亦然, 使用流4和/或流4。</span><span class="sxs-lookup"><span data-stu-id="22a51-380">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="22a51-381">从 Internet 上的客户端发送到 Office 365 的信号使用流程3。</span><span class="sxs-lookup"><span data-stu-id="22a51-381">Signaling from the client on the Internet to Office 365 uses flow 3.</span></span>

- <span data-ttu-id="22a51-382">从 Internet 上的客户端到客户网络中 SBC 的媒体使用流3和 4, 并按团队在 Office 365 中传输中继的方式进行中继。</span><span class="sxs-lookup"><span data-stu-id="22a51-382">Media from the client on the Internet to the SBC within the customer network uses flows 3 and 4, relayed by Teams Transport Relay in Office 365.</span></span> 

<span data-ttu-id="22a51-383">**远程用户直接路由 (媒体旁路直接路由)**</span><span class="sxs-lookup"><span data-stu-id="22a51-383">**Remote user Direct Routing (media bypass direct)**</span></span>

<span data-ttu-id="22a51-384">[![Microsoft 团队在线通话流程图22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-384">[![Microsoft Teams Online Call Flows Figure 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span></span>

<span data-ttu-id="22a51-385">*图 22-远程用户直接路由 (媒体旁路直接路由)*</span><span class="sxs-lookup"><span data-stu-id="22a51-385">*Figure 22 - Remote user Direct Routing (media bypass direct)*</span></span>
 
<span data-ttu-id="22a51-386">请注意:</span><span class="sxs-lookup"><span data-stu-id="22a51-386">Note that:</span></span>

- <span data-ttu-id="22a51-387">SBC 必须具有可通过 Office 365 和 Internet 进行路由的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="22a51-387">The SBC must have a public IP address that is routable from Office 365 and the Internet.</span></span>

- <span data-ttu-id="22a51-388">从 SBC 到 Office 365 的信号, 反之亦然, 使用流4和/或流4。</span><span class="sxs-lookup"><span data-stu-id="22a51-388">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="22a51-389">从 Internet 上的客户端发送到 Office 365 的信号使用流程3。</span><span class="sxs-lookup"><span data-stu-id="22a51-389">Signaling from the client on the Internet to Office 365 uses flow 3.</span></span>

- <span data-ttu-id="22a51-390">从 Internet 上的客户端到客户网络中的 SBC 的媒体使用流2。</span><span class="sxs-lookup"><span data-stu-id="22a51-390">Media from the client on the Internet to the SBC within the customer network uses flow 2.</span></span>

<span data-ttu-id="22a51-391">**直接路由 (媒体旁路)-PSTN hairpin 呼叫 (由于呼叫转发/传输)**</span><span class="sxs-lookup"><span data-stu-id="22a51-391">**Direct Routing (media bypass) – PSTN hairpin call (due to call forward/transfer)**</span></span>

<span data-ttu-id="22a51-392">[![Microsoft 团队在线通话流程图23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-392">[![Microsoft Teams Online Call Flows Figure 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span></span>

<span data-ttu-id="22a51-393">*图 23-直接路由 (媒体旁路)-PSTN hairpin 呼叫 (由于呼叫转发/传输)*</span><span class="sxs-lookup"><span data-stu-id="22a51-393">*Figure 23 - Direct Routing (media bypass) - PSTN hairpin call (due to call forward/transfer)*</span></span>
 
<span data-ttu-id="22a51-394">请注意:</span><span class="sxs-lookup"><span data-stu-id="22a51-394">Note that:</span></span>

- <span data-ttu-id="22a51-395">SBC 必须具有可通过 Office 365 路由的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="22a51-395">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="22a51-396">从 SBC 到 Office 365 的信号, 反之亦然, 使用流4和/或流4。</span><span class="sxs-lookup"><span data-stu-id="22a51-396">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="22a51-397">从 PSTN 到 PSTN hairpinned 呼叫后, 客户端不会发出信号和媒体循环。</span><span class="sxs-lookup"><span data-stu-id="22a51-397">The client is out of the signaling and media loop after the call is hairpinned from PSTN to PSTN.</span></span>

- <span data-ttu-id="22a51-398">从客户网络内的 SBC 实例 A 到客户网络 (其中 A 和 B 可以是同一实例) 内的 sbc 实例 B 的媒体使用流程5C。</span><span class="sxs-lookup"><span data-stu-id="22a51-398">Media from SBC instance A within the customer network to SBC instance B within the customer network (where, A and B can be the same instance) uses flow 5C.</span></span>

<span data-ttu-id="22a51-399">**直接路由 (通过 Office 365 的媒体)-跨两个租户的 PSTN hairpin 呼叫**</span><span class="sxs-lookup"><span data-stu-id="22a51-399">**Direct Routing (media through Office 365) – PSTN hairpin call across two tenants**</span></span>

<span data-ttu-id="22a51-400">[![Microsoft 团队在线通话流程图24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-400">[![Microsoft Teams Online Call Flows Figure 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span></span>

<span data-ttu-id="22a51-401">*图 24-直接路由 (通过 Office 365 的媒体)-跨两个租户的 PSTN hairpin 呼叫*</span><span class="sxs-lookup"><span data-stu-id="22a51-401">*Figure 24 - Direct Routing (media through Office 365) – PSTN hairpin call across two tenants*</span></span>
 
<span data-ttu-id="22a51-402">请注意:</span><span class="sxs-lookup"><span data-stu-id="22a51-402">Note that:</span></span>

- <span data-ttu-id="22a51-403">SBC 必须具有可通过 Office 365 路由的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="22a51-403">The SBC must have a public IP address that is routable from Office 365.</span></span>

- <span data-ttu-id="22a51-404">从 SBC 到 Office 365 的信号, 反之亦然, 使用流4和/或流4。</span><span class="sxs-lookup"><span data-stu-id="22a51-404">Signaling from the SBC to Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="22a51-405">从 PSTN 到 PSTN hairpinned 呼叫后, 客户端不会发出信号和媒体循环。</span><span class="sxs-lookup"><span data-stu-id="22a51-405">The client is out of the signaling and media loop after the call is hairpinned from PSTN to PSTN.</span></span>

- <span data-ttu-id="22a51-406">来自 SBC 实例 A (从客户网络 X 到 SBC 实例 B) 内部的媒体必须通过 Office 365 媒体服务器中继, 并且无法使用绕过模式。</span><span class="sxs-lookup"><span data-stu-id="22a51-406">Media from SBC instance A within the customer network X to SBC instance B must be relayed through the Office 365 Media Server and can't use bypass mode.</span></span>

## <a name="teams-with-express-route-optimization"></a><span data-ttu-id="22a51-407">具有快速路线优化的团队</span><span class="sxs-lookup"><span data-stu-id="22a51-407">Teams with Express Route optimization</span></span>

<span data-ttu-id="22a51-408">[![Microsoft 团队在线通话流程图25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-408">[![Microsoft Teams Online Call Flows Figure 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span></span>

<span data-ttu-id="22a51-409">*图 25-具有快速路线优化的团队*</span><span class="sxs-lookup"><span data-stu-id="22a51-409">*Figure 25 - Teams with Express Route optimization*</span></span>
 
<span data-ttu-id="22a51-410">在显示和部署快速路由的情况下, 团队流可以从流4重新路由到流 1, 从流 4 "重新路由到流 1"。</span><span class="sxs-lookup"><span data-stu-id="22a51-410">In the case that Express Route is justified and deployed, then Teams flows could be re-routed from flow 4 to flow 1 and from flow 4' to flow 1'.</span></span> <span data-ttu-id="22a51-411">但是, 团队应用程序对通过 internet 进行的其他 Office 365 流的相关性很难, 因为流4和 4 ';因此, 不能阻止这些流程。</span><span class="sxs-lookup"><span data-stu-id="22a51-411">However, Teams Application has a hard dependency on other Office 365 flows over the internet via flows 4 and 4'; hence these flows must not be blocked.</span></span> 

<span data-ttu-id="22a51-412">请注意, Skype for Business 混合边缘流量将路由到 Internet, 而不是快速路由以与外部用户通信并与其他租户联盟。</span><span class="sxs-lookup"><span data-stu-id="22a51-412">Note that Skype for Business hybrid Edge traffic is routed to the Internet and not to Express Route to communicate with external users and federate with other tenants.</span></span> 

<span data-ttu-id="22a51-413">若要防止非对称流, 重新路由必须在两个方向上。</span><span class="sxs-lookup"><span data-stu-id="22a51-413">To prevent asymmetrical flows, re-routing must be in both directions.</span></span> <span data-ttu-id="22a51-414">换句话说, 客户网络中的地址通过 Internet 或快速路由进行路由, 基于优化, 但不能通过这两者进行路由。</span><span class="sxs-lookup"><span data-stu-id="22a51-414">In other words, an address within the customer network is routable either through Internet or Express Route, based on optimization, but not through both.</span></span>

<span data-ttu-id="22a51-415">例如：</span><span class="sxs-lookup"><span data-stu-id="22a51-415">For example:</span></span>

<span data-ttu-id="22a51-416">**向外部用户的客户网络 (按团队传输中继的媒体中继):**</span><span class="sxs-lookup"><span data-stu-id="22a51-416">**Customer network to external user (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="22a51-417">[![Microsoft 团队在线通话流程图26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span><span class="sxs-lookup"><span data-stu-id="22a51-417">[![Microsoft Teams Online Call Flows Figure 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span></span>

<span data-ttu-id="22a51-418">*图 26-向外部用户 (按团队传输中继的媒体中继) 的客户网络*</span><span class="sxs-lookup"><span data-stu-id="22a51-418">*Figure 26 - Customer network to external user (media relayed by Teams Transport Relay)*</span></span>
 
<span data-ttu-id="22a51-419">**高级别步骤:**</span><span class="sxs-lookup"><span data-stu-id="22a51-419">**High Level Steps:**</span></span>
1. <span data-ttu-id="22a51-420">客户网络中的团队用户通过 flow2 解析 URL 域名 (DNS)</span><span class="sxs-lookup"><span data-stu-id="22a51-420">Teams User within customer network resolves URL domain name (DNS) via flow2</span></span>
2. <span data-ttu-id="22a51-421">客户网络中的团队用户通过流1分配团队传输中继的媒体中继端口</span><span class="sxs-lookup"><span data-stu-id="22a51-421">Teams User within customer network allocates a media Relay port on Teams Transport Relay via flow 1</span></span>
3. <span data-ttu-id="22a51-422">客户网络中的团队用户通过将 "邀请" 通过流1到 Office 365 的冰候选人发送 "邀请"</span><span class="sxs-lookup"><span data-stu-id="22a51-422">Teams User within customer network sends "invite" with ICE candidates via flow 1 to Office 365</span></span>
4. <span data-ttu-id="22a51-423">OFFICE 365 通过流程3向外部团队用户发送通知</span><span class="sxs-lookup"><span data-stu-id="22a51-423">OFFICE 365 sends notification to external Teams user via flow 3</span></span>
5. <span data-ttu-id="22a51-424">团队外部用户通过流3在团队传输中继上分配媒体中继端口</span><span class="sxs-lookup"><span data-stu-id="22a51-424">Teams external user allocates a media Relay port on Teams Transport Relay via flow 3</span></span>
6. <span data-ttu-id="22a51-425">团队外部用户通过流3发送 "解答" 与 ICE 候选人, 通过流3转发给团队用户 A。</span><span class="sxs-lookup"><span data-stu-id="22a51-425">Teams external user sends "answer" with ICE candidates via flow 3, which is forwarded back to Teams user A via Flow 1</span></span>
7. <span data-ttu-id="22a51-426">团队用户 A 和团队用户 B 调用 ICE 连接测试并选择流1和 3 (由 Office 365 中的团队传输中继进行中继)</span><span class="sxs-lookup"><span data-stu-id="22a51-426">Teams User A and Teams User B invoke ICE connectivity tests and selects flows 1 and 3, which are relayed by Teams Transport Relay in Office 365</span></span>
8. <span data-ttu-id="22a51-427">团队用户通过流1和3将遥测发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="22a51-427">Teams Users send telemetry to Office 365 via flows 1 and 3</span></span>

><span data-ttu-id="22a51-428">**注意**: 必须启用流4以支持团队应用程序对流程4的其他微服务的依赖关系。</span><span class="sxs-lookup"><span data-stu-id="22a51-428">**Note**: Flow 4 must be enabled to support dependencies of Teams application on other micro-services that mandates flow 4.</span></span>
