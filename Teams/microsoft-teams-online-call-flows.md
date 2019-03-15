---
title: Microsoft Teams 联机通话流程
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 06/08/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sonua
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
appliesto:
- Microsoft Teams
description: 介绍如何团队工作负荷利用不同拓扑中的 Office 365 流。
ms.openlocfilehash: 49393337fd8e4f5c0bbfdf8b3cea0edf383fbd57
ms.sourcegitcommit: 3014331fff89a0842c4db0b9adf0ef32f9728ade
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/15/2019
ms.locfileid: "30641086"
---
# <a name="microsoft-teams-online-call-flows"></a><span data-ttu-id="f1316-103">Microsoft Teams 联机通话流程</span><span class="sxs-lookup"><span data-stu-id="f1316-103">Microsoft Teams Online Call Flows</span></span>

> [!Tip]
> <span data-ttu-id="f1316-104">观看下面的会话，若要了解如何团队利用您的网络和如何最好地规划最佳的网络连接：[团队网络规划](https://aka.ms/teams-networking)</span><span class="sxs-lookup"><span data-stu-id="f1316-104">Watch the following session to learn how to Teams leverages your network and how to best plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking)</span></span>

## <a name="overview"></a><span data-ttu-id="f1316-105">概述</span><span class="sxs-lookup"><span data-stu-id="f1316-105">Overview</span></span>
<span data-ttu-id="f1316-106">本文档介绍团队工作负荷如何利用不同拓扑中的 Office 365 流。</span><span class="sxs-lookup"><span data-stu-id="f1316-106">This document describes how Teams workload utilizes Office 365 flows in various topologies.</span></span> <span data-ttu-id="f1316-107">此外，它指定用于对等媒体通信的唯一团队流。</span><span class="sxs-lookup"><span data-stu-id="f1316-107">In addition, it specifies unique Teams flows that are used for peer to peer media communication.</span></span> <span data-ttu-id="f1316-108">文档枚举这些流程，并介绍其用途和其原点/终止网络。</span><span class="sxs-lookup"><span data-stu-id="f1316-108">The document enumerates these flows and describes their purpose and their origin/termination networks.</span></span> <span data-ttu-id="f1316-109">例如，流 X 用于 Office 365 客户端在本地与云中，来自客户网络和 Office 365 云终结点终止的 Office 365 服务进行通信和流 Y 由本地的 Office 365 客户端与进行通信Internet，Office 365 具有依赖项，从客户网络，发起和终止 Internet 上的终结点上的服务。</span><span class="sxs-lookup"><span data-stu-id="f1316-109">For example, flow X is used by Office 365 client on premises to communicate with Office 365 service in the cloud, originated from the Customer Network and terminated by an endpoint in Office 365 cloud, and flow Y is used by Office 365 client on premises to communicate with a service on the Internet, that Office 365 has dependency on, originated from the Customer Network, and is terminated by an endpoint on the Internet.</span></span>

<span data-ttu-id="f1316-110">文档有三个主要部分。</span><span class="sxs-lookup"><span data-stu-id="f1316-110">The document has three main sections.</span></span> <span data-ttu-id="f1316-111">第一个提供背景信息，如网络 （即 Office 365 流可能遍历）、 类型的通信、 客户网络连接指南 to Office 365 服务终结点、 第三方组件和主体互操作性的使用团队选择媒体流。</span><span class="sxs-lookup"><span data-stu-id="f1316-111">The first provides a background information, such as networks (that Office 365 flows may traverse), type of traffic, connectivity guidance from Customer Network to Office 365 service endpoints, interoperability with third party components and principals that are used by Teams to select media flows.</span></span> <span data-ttu-id="f1316-112">第二个说明了在各种拓扑中的这些流程的使用情况。</span><span class="sxs-lookup"><span data-stu-id="f1316-112">The second illustrates the usage of these flows in various topologies.</span></span> <span data-ttu-id="f1316-113">为每个拓扑，它枚举所有支持的流，并说明了如何使用这些流程通过多个用例。</span><span class="sxs-lookup"><span data-stu-id="f1316-113">For each topology, it enumerates all supported flows and illustrates how these flows are used via several use cases.</span></span> <span data-ttu-id="f1316-114">对于每个用例，它介绍顺序以及选择通过流程图的流。</span><span class="sxs-lookup"><span data-stu-id="f1316-114">For each use case, it describes the sequence and selection of flows via a flow diagram.</span></span> <span data-ttu-id="f1316-115">第三个介绍用于优化，通过简单拓扑中说明了部署 Express 路由时如何使用这些流程。</span><span class="sxs-lookup"><span data-stu-id="f1316-115">The third describes how these flows are utilized when Express Route is deployed for optimization, illustrated via a simple topology.</span></span>

## <a name="background"></a><span data-ttu-id="f1316-116">背景</span><span class="sxs-lookup"><span data-stu-id="f1316-116">Background</span></span>
### <a name="network-segments"></a><span data-ttu-id="f1316-117">网络段</span><span class="sxs-lookup"><span data-stu-id="f1316-117">Network Segments</span></span>
<span data-ttu-id="f1316-118">**客户网络**： 这是控制并管理总体网络一部分的网络段。</span><span class="sxs-lookup"><span data-stu-id="f1316-118">**Customer Network**: This is the network segment that is part of your overall network that you control and manage.</span></span> <span data-ttu-id="f1316-119">这包括客户办公室内的所有客户连接是否有线或无线，办公楼到本地数据中心之间 Internet 提供商、 Express 路由或任何其他专用对等连接。</span><span class="sxs-lookup"><span data-stu-id="f1316-119">This includes all customer connections within customer offices, whether wired or wireless, between office buildings, to on-premises datacenters, and your connections to Internet providers, Express Route or any other private peering.</span></span> 

<span data-ttu-id="f1316-120">通常情况下，客户网络具有多个网络外围防火墙和/或代理服务器，其强制实施组织的安全策略和的仅允许您设置并配置某些网络流量。</span><span class="sxs-lookup"><span data-stu-id="f1316-120">Typically, a customer network has several network perimeters with firewalls and/or proxy servers, which enforce an organization's security policies and that only allow certain network traffic that you have set up and configured.</span></span> <span data-ttu-id="f1316-121">由于客户管理此网络，客户可以直接控制的网络，性能，强烈建议完成客户网络评估，以验证性能这两个网络中以及从网站内的您到 Office 365 网络的网络。</span><span class="sxs-lookup"><span data-stu-id="f1316-121">Because the customer manages this network, the customer has direct control over the performance of the network, and it is highly recommended that the customer complete network assessments to validate performance both within sites in your network and from your network to Office 365 network.</span></span> <span data-ttu-id="f1316-122">在本地部署的业务和 PSTN 会话边界控制器与 PSTN 连接到网络 （即，直接路由） 的 Skype 是可选的。</span><span class="sxs-lookup"><span data-stu-id="f1316-122">Skype for Business on premises deployment and PSTN Session Border Controller to connect with PSTN through your network (i.e., Direct Routing) are optional.</span></span>

<span data-ttu-id="f1316-123">**Internet**： 这是您要连接到 Office 365 云从客户网络之外的用户将使用的整个网络一部分的网络段。</span><span class="sxs-lookup"><span data-stu-id="f1316-123">**Internet**: This is the network segment that is part of your overall network that will be used by users who are connecting to Office 365 Cloud from outside of the Customer Network.</span></span> <span data-ttu-id="f1316-124">它还使用到 Office 365 云客户网络一些流量。</span><span class="sxs-lookup"><span data-stu-id="f1316-124">It is also used by some traffic from the Customer Network to Office 365 Cloud.</span></span> 

<span data-ttu-id="f1316-125">**已访问/来宾专用网络**： 这是外部客户网络，但不能在公用 Internet，也可以访问您的用户和/或其来宾的网络段。</span><span class="sxs-lookup"><span data-stu-id="f1316-125">**Visited/Guest private Network**: This is the network segment outside your Customer Network, but not in the public Internet, that your users and/or their guests may visit.</span></span> <span data-ttu-id="f1316-126">例如，主专用网络或企业版专用网络的不部署团队，可能位于您的用户和/或其与团队服务进行交互的客户。</span><span class="sxs-lookup"><span data-stu-id="f1316-126">For example, home private network or an Enterprise private Network, that does not deploy Teams, where your users and/or their customers that interact with Teams services, may reside.</span></span>

><span data-ttu-id="f1316-127">**注意**： 连接到 Office 365b 也是适用于这些网络。</span><span class="sxs-lookup"><span data-stu-id="f1316-127">**Note**: Connectivity to Office 365b is also applicable to these networks.</span></span>

<span data-ttu-id="f1316-128">**Office 365 云**： 这是支持 Office 365 服务的网络段。</span><span class="sxs-lookup"><span data-stu-id="f1316-128">**Office 365 Cloud**: This is the network segment that supports Office 365 services.</span></span> <span data-ttu-id="f1316-129">它与接近大多数位置中的客户网络中的边缘世界各地分布。</span><span class="sxs-lookup"><span data-stu-id="f1316-129">It is distributed worldwide with edges in proximity to Customer Network in most locations.</span></span> <span data-ttu-id="f1316-130">本文档中提到的功能包括传输中继、 会议服务器和媒体处理器。</span><span class="sxs-lookup"><span data-stu-id="f1316-130">Functions mentioned in this document include Transport Relay, conferencing server and Media Processor.</span></span> 

<span data-ttu-id="f1316-131">**Express 路由 （可选）**： 这是您将为您提供专用的专用连接到 Office 365 网络的总体网络一部分的网络段。</span><span class="sxs-lookup"><span data-stu-id="f1316-131">**Express Route (Optional)**: This is the network segment that is part of your overall network that will give you a dedicated, private connection to the Office 365 network.</span></span>

### <a name="types-of-traffic"></a><span data-ttu-id="f1316-132">类型的通信</span><span class="sxs-lookup"><span data-stu-id="f1316-132">Types of traffic</span></span>

<span data-ttu-id="f1316-133">**实时媒体**： 封装 RTP （实时传输协议） 和支持音频、 视频和共享工作负荷的屏幕中的数据。</span><span class="sxs-lookup"><span data-stu-id="f1316-133">**Real-time media**: Data encapsulated within RTP (Real-time Transport Protocol) and supports audio, video and screen sharing workloads.</span></span> <span data-ttu-id="f1316-134">一般情况下，媒体流量高度是延迟敏感，因此您希望采用的最直接路径可能，并使用 UDP 和 TCP 作为传输层协议，它是最佳传输质量角度从交互式实时媒体此通信。</span><span class="sxs-lookup"><span data-stu-id="f1316-134">In general, media traffic is highly latency sensitive, so you would want this traffic to take the most direct path possible, and to use UDP versus TCP as the transport layer protocol, which is the best transport for interactive real time media from quality perspective.</span></span> <span data-ttu-id="f1316-135">(注意： 媒体作为最后的手段，可以使用 TCP/IP 和还隧道 HTTP 协议内，但不是建议由于错误质量影响。)通过 SRTP，只对负载用于加密被安全 RTP 流。</span><span class="sxs-lookup"><span data-stu-id="f1316-135">(Note: As a last resort, media can use TCP/IP and also be tunneled within HTTP protocol, but it is not recommended due to bad quality implications.) RTP flow is secured via SRTP, in which only the payload is encrypted.</span></span>

<span data-ttu-id="f1316-136">**信号**： 客户端和服务器或用于控制活动 （例如，当发起呼叫），其他客户端之间的通信链接和提供即时消息。</span><span class="sxs-lookup"><span data-stu-id="f1316-136">**Signaling**: The communication link between the client and server, or other clients that are used to control activities (for example, when a call is initiated), and deliver instant messages.</span></span> <span data-ttu-id="f1316-137">最信号流量使用基于 HTTPS 的 REST 界面，但在某些情况下 （例如，Office 365 云和会话边界控制器之间的连接） 使用 SIP 协议。</span><span class="sxs-lookup"><span data-stu-id="f1316-137">Most signaling traffic uses the HTTPS-based REST interfaces, though in some scenarios (for example, connection between Office 365 Cloud and a Session Border Controller) uses SIP Protocol.</span></span> <span data-ttu-id="f1316-138">务必要了解此通信是这么对延迟敏感，但可能会导致服务中断或呼叫超时，如果终结点之间的延迟超过几秒钟的时间。</span><span class="sxs-lookup"><span data-stu-id="f1316-138">It's important to understand that this traffic is much less sensitive to latency but may cause service outages or call timeouts if latency between the endpoints exceed several seconds.</span></span> 

### <a name="connectivity-to-office-365"></a><span data-ttu-id="f1316-139">连接到 Office 365</span><span class="sxs-lookup"><span data-stu-id="f1316-139">Connectivity to Office 365</span></span>

<span data-ttu-id="f1316-140">团队服务需要[连接到 Internet](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10)。</span><span class="sxs-lookup"><span data-stu-id="f1316-140">Teams service requires [connectivity to the Internet](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10).</span></span> <span data-ttu-id="f1316-141">[Office 365 Url 和 IP 地址范围](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges)中列出了工作组终结点 Url 和 IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="f1316-141">Teams endpoints URLs and IP address ranges are listed in [Office 365 URLs and IP address ranges](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges).</span></span> <span data-ttu-id="f1316-142">(注意： 需要打开连接到 TCP 端口 80 和 443 和 UDP 端口 3478 到 3481。)此外，团队服务具有对 Skype 业务联机服务的依赖项，因此它需要连接到 Internet 的还此服务。</span><span class="sxs-lookup"><span data-stu-id="f1316-142">(Note: It requires to open connectivity to TCP ports 80 and 443 and UDP ports 3478 through 3481.) Furthermore, Teams service has dependency on Skype for business online service, hence it is required to connect also this service to the Internet.</span></span>

<span data-ttu-id="f1316-143">通过标准 IETF ICE （互动式连接建立） 过程中实现团队媒体流连接。</span><span class="sxs-lookup"><span data-stu-id="f1316-143">Teams media flows connectivity is implemented via standard IETF ICE (Interactive Connectivity Establishment) procedures.</span></span>

### <a name="interoperability-restrictions"></a><span data-ttu-id="f1316-144">互操作性限制</span><span class="sxs-lookup"><span data-stu-id="f1316-144">Interoperability Restrictions</span></span>
<span data-ttu-id="f1316-145">**第三方媒体中继**： 团队媒体流 （即，其中一个媒体端点是团队） 可能遍历仅团队或 Skype 的业务本机媒体中继。</span><span class="sxs-lookup"><span data-stu-id="f1316-145">**Third party media relays**: A Teams media flow (i.e., one of the media endpoints is Teams) may traverse only Teams or Skype for Business native media relays.</span></span> <span data-ttu-id="f1316-146">不支持与第三方媒体中继互操作性。</span><span class="sxs-lookup"><span data-stu-id="f1316-146">Interoperability with a third party media relay is not supported.</span></span> <span data-ttu-id="f1316-147">(注意： 与 PSTN 边界上的第三方 SBC 必须终止 RTP/RTCP 流，通过 SRTP 保护并不将其中继到下一个跃点。)</span><span class="sxs-lookup"><span data-stu-id="f1316-147">(Note: A third party SBC on the boundary with PSTN MUST terminate RTP/RTCP stream, secured via SRTP, and not relay it to the next hop.)</span></span>

<span data-ttu-id="f1316-148">**第三方 SIP 代理服务器**： 团队信号 SIP 对话与第三方 SBC 和/或网关可能的业务本机 SIP 代理遍历团队或 Skype。</span><span class="sxs-lookup"><span data-stu-id="f1316-148">**Third party SIP Proxy Servers**: A Teams signaling SIP dialog with a third party SBC and/or Gateway may traverse Teams or Skype for Business native SIP proxies.</span></span> <span data-ttu-id="f1316-149">不支持与第三方 SIP 代理服务器互操作性。</span><span class="sxs-lookup"><span data-stu-id="f1316-149">Interoperability with a third party SIP Proxy is not supported.</span></span>

<span data-ttu-id="f1316-150">**第三方 B2BUA (即，SBC)**： 由第三方 SBC 终止团队从/pstn 的媒体流。</span><span class="sxs-lookup"><span data-stu-id="f1316-150">**Third party B2BUA (i.e., SBC)**: A Teams media flow from/to PSTN is terminated by a third party SBC.</span></span> <span data-ttu-id="f1316-151">但是，与互操作性第三方 SBC 团队网络内 （即，第三方 SBC 作为两个团队/Skype 的业务终结点） 不受支持。</span><span class="sxs-lookup"><span data-stu-id="f1316-151">However, interoperability with a third party SBC within Teams network (i.e., third party SBC mediates two Teams/Skype For Business endpoints) is not supported.</span></span>

### <a name="technologies-that-are-strongly-not-recommended-with-microsoft-teams"></a><span data-ttu-id="f1316-152">与 Microsoft 团队中不强烈建议使用的技术</span><span class="sxs-lookup"><span data-stu-id="f1316-152">Technologies that are strongly not recommended with Microsoft Teams</span></span>

<span data-ttu-id="f1316-153">**VPN 网络**： 强烈建议不要的媒体流量 （即，流 2）。</span><span class="sxs-lookup"><span data-stu-id="f1316-153">**VPN Network**: It is strongly not recommended for media traffic (i.e., flow 2').</span></span> <span data-ttu-id="f1316-154">VPN 客户端应该使用中指定的任何外部的非 VPN 用户，如拆分 VPN 和路由媒体流量https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/</span><span class="sxs-lookup"><span data-stu-id="f1316-154">VPN client SHOULD use split VPN and route media traffic like any external non-VPN user, as specified in https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/</span></span> 

><span data-ttu-id="f1316-155">**注意**： 虽然标题为 Lync，它也适用于团队。</span><span class="sxs-lookup"><span data-stu-id="f1316-155">**Note**: Although the title is Lync, it is applicable to Teams as well.</span></span>

<span data-ttu-id="f1316-156">**数据包 Shapers**： 任何类型的数据包 snippers、 数据包检查或数据包整形程序设备强不建议使用，并且会显著可能会降低的质量。</span><span class="sxs-lookup"><span data-stu-id="f1316-156">**Packet Shapers**: Any kind of packet snippers, packet inspection, or packet shaper devices are strongly not recommended and may degrade quality significantly.</span></span> 

### <a name="principles"></a><span data-ttu-id="f1316-157">原则</span><span class="sxs-lookup"><span data-stu-id="f1316-157">Principles</span></span>
<span data-ttu-id="f1316-158">有四个一般原则，帮助您了解 Microsoft 团队的呼叫流。</span><span class="sxs-lookup"><span data-stu-id="f1316-158">There are four general principles that help you understand call flows for Microsoft Teams.</span></span> 
1.  <span data-ttu-id="f1316-159">由其中第一个参与者加入同一区域中的 Office 365 云承载的 Microsoft 团队会议。</span><span class="sxs-lookup"><span data-stu-id="f1316-159">A Microsoft Teams conference is hosted by Office 365 cloud in the same region where the first participant joined.</span></span> <span data-ttu-id="f1316-160">(注意： 如果将在某些拓扑中，此规则的例外，则它们将由相应的呼叫流量所示的本文档中所述。)</span><span class="sxs-lookup"><span data-stu-id="f1316-160">(Note: If there will be exceptions to this rule in some topologies, then they will be described in this document, illustrated by an appropriate call flow.)</span></span>
2.  <span data-ttu-id="f1316-161">使用云的 Office 365 中的团队媒体端点 (MP) 基于媒体处理需求，并不基于呼叫类型。</span><span class="sxs-lookup"><span data-stu-id="f1316-161">A Teams media endpoint (MP) in Office 365 cloud is used based on media processing needs and not based on call type.</span></span> <span data-ttu-id="f1316-162">（例如，点到点呼叫可能用于媒体终结点到过程介质云中转录和/或时具有两个参与者的会议中不能使用任何媒体终结点云录制。）但是，大多数会议将使用 MP 混合和路由目的，分配承载会议。</span><span class="sxs-lookup"><span data-stu-id="f1316-162">(For example, a point to point call may use a media endpoint in the cloud to process media for transcription and/or recording, while a conference with two participants may not use any media endpoint in the cloud.) However, most conferences will use an MP for mixing and routing purposes, allocated where the conference is hosted.</span></span> <span data-ttu-id="f1316-163">从客户端发送到 MP 的媒体流量可能会直接路由或 Office 365 云使用传输中继，如果需要由于客户网络防火墙限制。</span><span class="sxs-lookup"><span data-stu-id="f1316-163">The media traffic sent from a client to the MP may be routed directly or use a Transport Relay, in Office 365 Cloud, if required due to Customer Network firewall restrictions.</span></span> 
3.  <span data-ttu-id="f1316-164">媒体流量的对等呼叫发生不可用，假定呼叫不要求在云中 MP 最直接路由 （请参阅上面的 #2）。</span><span class="sxs-lookup"><span data-stu-id="f1316-164">Media traffic for peer-to-peer calls take the most direct route that is available, assuming that the call doesn't mandate an MP in the cloud (see #2 above).</span></span> <span data-ttu-id="f1316-165">首选的路由是直接连接到远程对等方 （客户端），但如果该路由不可用，然后一个或多个传输中继将通信中继。</span><span class="sxs-lookup"><span data-stu-id="f1316-165">The preferred route is direct to the remote peer (client), but if that route isn't available, then one or more Transport Relays will relay traffic.</span></span> <span data-ttu-id="f1316-166">建议媒体流量应如数据包 shapers、 VPN 服务器等，不遍历服务器，因为这将影响的媒体质量。</span><span class="sxs-lookup"><span data-stu-id="f1316-166">It is recommended that media traffic shall not transverse servers such as packet shapers, VPN servers, etc., since this will impact the media quality.</span></span>
4.  <span data-ttu-id="f1316-167">始终信号流量转到最近服务器向用户。</span><span class="sxs-lookup"><span data-stu-id="f1316-167">Signaling traffic always goes to the closest server to the user.</span></span> 

<span data-ttu-id="f1316-168">若要了解有关上选择的媒体路径的详细信息，请参阅https://www.youtube.com/watch?v=aD5mUg2ZzLQ。</span><span class="sxs-lookup"><span data-stu-id="f1316-168">To learn more about the details on the media path that is chosen, see https://www.youtube.com/watch?v=aD5mUg2ZzLQ.</span></span>

## <a name="call-flows-in-various-topologies"></a><span data-ttu-id="f1316-169">在不同拓扑中的呼叫流</span><span class="sxs-lookup"><span data-stu-id="f1316-169">Call Flows in Various Topologies</span></span>
### <a name="teams-online-pure-topology"></a><span data-ttu-id="f1316-170">团队联机 （"纯"） 拓扑</span><span class="sxs-lookup"><span data-stu-id="f1316-170">Teams Online ("pure") Topology</span></span>
<span data-ttu-id="f1316-171">未部署任何服务器，以进行直接路由内部部署的 SBC 业务的 Skype 等情况下利用团队云服务的客户使用这种拓扑。</span><span class="sxs-lookup"><span data-stu-id="f1316-171">This topology is used by customers that leverage Teams services from the cloud without deploying any server, such as Skype for business and SBC for Direct Routing, on premises.</span></span> <span data-ttu-id="f1316-172">此外，通过不 Azure Express 路由 Internet 完成到 Office 365 的接口。</span><span class="sxs-lookup"><span data-stu-id="f1316-172">In addition, the interface to Office 365 is done via the Internet without Azure Express Route.</span></span> 

<span data-ttu-id="f1316-173">[![Microsoft 团队联机呼叫流图 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-173">[![Microsoft Teams Online Call Flows Figure 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span></span>

<span data-ttu-id="f1316-174">*图 1-团队联机 （纯'） 拓扑*</span><span class="sxs-lookup"><span data-stu-id="f1316-174">*Figure 1 - Teams Online ('pure') Topology*</span></span>

><span data-ttu-id="f1316-175">**说明**：</span><span class="sxs-lookup"><span data-stu-id="f1316-175">**Notes**:</span></span>
>- <span data-ttu-id="f1316-176">在上图上箭头的方向反映影响连接功能的企业外围环境的通信的初始方向。</span><span class="sxs-lookup"><span data-stu-id="f1316-176">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="f1316-177">对于媒体 UDP，第一个数据包可能流的反向方向，但可能被阻止这些数据包，直到在其他方向的数据包将流。</span><span class="sxs-lookup"><span data-stu-id="f1316-177">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>
>- <span data-ttu-id="f1316-178">团队 Online 业务 online 部署并排 Skype，因此客户端显示为"团队/SFB 用户"。</span><span class="sxs-lookup"><span data-stu-id="f1316-178">Teams Online is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user".</span></span>

- <span data-ttu-id="f1316-179">本文档中的部分**团队 Online 的混合拓扑**中所述为内部部署中的业务的可选 Skype</span><span class="sxs-lookup"><span data-stu-id="f1316-179">Optional Skype for Business on premises deployment is described in this document in the section **Teams Online Hybrid Topology**</span></span>
- <span data-ttu-id="f1316-180">对于 PSTN 的可选直接路由本文档的**团队 Online 与直接路由拓扑**部分中所述</span><span class="sxs-lookup"><span data-stu-id="f1316-180">Optional Direct Routing for PSTN is described in this document in the section **Teams Online with Direct Routing Topology**</span></span>
- <span data-ttu-id="f1316-181">本文档中**小组具有 Express 路由优化**部分中所述可选 Express 路由</span><span class="sxs-lookup"><span data-stu-id="f1316-181">Optional Express Route is described in this document in the section **Teams w/ Express Route optimization**</span></span>

<span data-ttu-id="f1316-182">**流说明**：</span><span class="sxs-lookup"><span data-stu-id="f1316-182">**Flows Descriptions**:</span></span>
- <span data-ttu-id="f1316-183">**流 2** – 表示作为其团队体验一部分启动客户网络到 Internet 上的用户的流量。</span><span class="sxs-lookup"><span data-stu-id="f1316-183">**Flow 2** – Represents a flow initiated by a user on Customer Network to the Internet as a part of his Teams experience.</span></span> <span data-ttu-id="f1316-184">这些流程的示例是 DNS 和对等媒体。</span><span class="sxs-lookup"><span data-stu-id="f1316-184">Examples of these flows are DNS and peer to peer media.</span></span>
- <span data-ttu-id="f1316-185">**流 2** – 表示启动远程移动团队用户，向客户网络的 VPN 流。</span><span class="sxs-lookup"><span data-stu-id="f1316-185">**Flow 2'** – Represents a flow initiated by a remote mobile Teams user, which VPN to Customer Network.</span></span> 
- <span data-ttu-id="f1316-186">**流 3** – 表示启动远程移动团队用户对 Office 365/Teams 终结点的流。</span><span class="sxs-lookup"><span data-stu-id="f1316-186">**Flow 3** – Represents a flow initiated by a remote mobile Teams user to Office 365/Teams endpoints.</span></span> 
- <span data-ttu-id="f1316-187">**流 4** – 表示启动客户网络到 Office 365/Teams 终结点上的用户的流量。</span><span class="sxs-lookup"><span data-stu-id="f1316-187">**Flow 4** – Represents a flow initiated by a user on the Customer Network to Office 365/Teams endpoints.</span></span>
- <span data-ttu-id="f1316-188">**流 5** – 表示客户网络内的业务用户，团队用户与其他工作组或 Skype 之间的对等媒体流。</span><span class="sxs-lookup"><span data-stu-id="f1316-188">**Flow 5** – Represents a peer to peer media flow between Teams user and another Teams or Skype for Business user, within Customer Network.</span></span>
- <span data-ttu-id="f1316-189">**流 6** – 表示对等媒体 internet 的远程移动团队用户和业务用户的另一个远程移动的团队或 Skype 之间流动。</span><span class="sxs-lookup"><span data-stu-id="f1316-189">**Flow 6** – Represents a peer to peer media flow between a remote mobile Teams user and another remote mobile Teams or Skype for Business user, over the Internet.</span></span>

#### <a name="use-case-one-to-one"></a><span data-ttu-id="f1316-190">用例： 一对一</span><span class="sxs-lookup"><span data-stu-id="f1316-190">Use Case: One-to-one</span></span>
<span data-ttu-id="f1316-191">一对一呼叫使用通用模型呼叫者将获取一组候选个 IP 地址/端口;本地中继以及身 （公共 IP 地址的客户端可看见的中继）。</span><span class="sxs-lookup"><span data-stu-id="f1316-191">One-to-one calls use a common model the caller will obtain a set of candidates consisting of IP addresses/ports; local, relay, and reflexive (public IP address of client as seen by the relay).</span></span> <span data-ttu-id="f1316-192">呼叫者发送这些候选人向呼叫方邀请中，调用的方还获取一组类似的候选人，并将其发送到呼叫者。</span><span class="sxs-lookup"><span data-stu-id="f1316-192">The caller sends these candidates to the called party in the invite, the called party also obtains a similar set of candidates and sends them to the caller.</span></span> <span data-ttu-id="f1316-193">邮件用来查找的调用方/调用方媒体路径起作用，STUN 连接检查和最佳工作路径处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="f1316-193">STUN connectivity check messages are used to find which caller/called party media paths work, and the best working path is selected.</span></span> <span data-ttu-id="f1316-194">然后，使用选定的候选对发送介质 （即，通过 SRTP 保护的 RTP/RTCP 数据包）。</span><span class="sxs-lookup"><span data-stu-id="f1316-194">Media (i.e., RTP/RTCP packets secured via SRTP) are then sent using the selected candidate pair.</span></span> <span data-ttu-id="f1316-195">传输中继部署作为 Office 365 云的一部分。</span><span class="sxs-lookup"><span data-stu-id="f1316-195">The Transport relay is deployed as part of the Office 365 Cloud.</span></span>

<span data-ttu-id="f1316-196">如果本地 IP 地址/端口候选人或身候选人具有连接，然后将媒体选择直接路径客户端之间 （或通过 NAT）。</span><span class="sxs-lookup"><span data-stu-id="f1316-196">If the local IP address/port candidates or the reflexive candidates have connectivity, then the direct path between the clients (or via a NAT) will be selected for media.</span></span> <span data-ttu-id="f1316-197">如果客户端都客户网络上，则应选择直接路径。</span><span class="sxs-lookup"><span data-stu-id="f1316-197">If the clients are both on the Customer network, then the direct path should be selected.</span></span> <span data-ttu-id="f1316-198">这需要客户网络内的直接 UDP 连接。</span><span class="sxs-lookup"><span data-stu-id="f1316-198">This requires direct UDP connectivity within the Customer Network.</span></span> <span data-ttu-id="f1316-199">如果客户端这两个游牧云用户，然后根据 NAT/防火墙，媒体可能会使用直接连接。</span><span class="sxs-lookup"><span data-stu-id="f1316-199">If the clients are both nomadic cloud users, then depending on the NAT/firewall, media may use direct connectivity.</span></span>

<span data-ttu-id="f1316-200">如果一个客户端是内部客户网络上，一个客户端是外部 （例如，移动云用户），然后它不太之间的本地或身候选的直接连接是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="f1316-200">If one client is internal on the Customer Network and one client is external (e.g., mobile cloud user), then it is unlikely that direct connectivity between the local or reflexive candidates is working.</span></span> <span data-ttu-id="f1316-201">在这种情况下，选择是使用从任一客户端的传输中继候选之一 (例如，内部客户端从 Office 365 云中传输中继获取中继候选、 外部客户端需要能够发送到的 STUN/RTP/RTCP 数据包传输中继）。</span><span class="sxs-lookup"><span data-stu-id="f1316-201">In this case, an option is to use one of the Transport Relay candidates from either client (e.g., the internal client obtained a relay candidate from the Transport relay in Office 365 Cloud, the external client needs to be able to send STUN/RTP/RTCP packets to the transport relay).</span></span> <span data-ttu-id="f1316-202">另一个选项是内部客户端将发送到移动云客户端获取中继候选。</span><span class="sxs-lookup"><span data-stu-id="f1316-202">Another option is the internal client sends to the relay candidate obtained by the mobile cloud client.</span></span> <span data-ttu-id="f1316-203">请注意，但强烈建议 UDP 连接的媒体，支持 TCP。</span><span class="sxs-lookup"><span data-stu-id="f1316-203">Note that although UDP connectivity for media is highly recommended, TCP is supported.</span></span>

<span data-ttu-id="f1316-204">**简要步骤**：</span><span class="sxs-lookup"><span data-stu-id="f1316-204">**High Level Steps**:</span></span>
1. <span data-ttu-id="f1316-205">团队需要用户 A 解析 URL 域 (DNS) 通过名 flow2</span><span class="sxs-lookup"><span data-stu-id="f1316-205">Teams User A resolves URL domain name (DNS) via flow2</span></span>
2. <span data-ttu-id="f1316-206">团队用户 A 分配媒体中继端口团队传输中继上的通过流 4</span><span class="sxs-lookup"><span data-stu-id="f1316-206">Teams User A allocates a media Relay port on Teams Transport Relay via flow 4</span></span>
3. <span data-ttu-id="f1316-207">团队需要用户 A 发送与通过流 4 到 Office 365 的 ICE 候选人"邀请"</span><span class="sxs-lookup"><span data-stu-id="f1316-207">Teams User A sends "invite" with ICE candidates via flow 4 to Office 365</span></span>
4. <span data-ttu-id="f1316-208">OFFICE 365 将通知发送给团队用户 B，通过流 4</span><span class="sxs-lookup"><span data-stu-id="f1316-208">OFFICE 365 sends notification to Teams User B via flow 4</span></span>
5. <span data-ttu-id="f1316-209">团队用户 B 分配媒体中继端口团队传输中继上的通过流 4</span><span class="sxs-lookup"><span data-stu-id="f1316-209">Teams User B allocates a media Relay port on Teams Transport Relay via flow 4</span></span>
6. <span data-ttu-id="f1316-210">团队用户 B 发送而被转接回通过流 4 的团队用户 A 的流 4，通过 ICE 候选人"应答"</span><span class="sxs-lookup"><span data-stu-id="f1316-210">Teams User B sends "answer" with ICE candidates via flow 4, which is forwarded back to Teams User A via Flow 4</span></span>
7. <span data-ttu-id="f1316-211">团队用户 A 和团队用户 B 调用 ICE 连接测试和选择最佳可用的媒体路径 （的各种使用情况下，请参阅下面的图表）</span><span class="sxs-lookup"><span data-stu-id="f1316-211">Teams User A and Teams User B invoke ICE connectivity tests and the best available media path is selected (see diagrams below for various use cases)</span></span>
8. <span data-ttu-id="f1316-212">团队用户发送到 Office 365 通过流 4 的遥测</span><span class="sxs-lookup"><span data-stu-id="f1316-212">Teams Users send telemetry to Office 365 via flow 4</span></span>

<span data-ttu-id="f1316-213">**客户网络： 中**</span><span class="sxs-lookup"><span data-stu-id="f1316-213">**Within Customer Network:**</span></span>

<span data-ttu-id="f1316-214">[![Microsoft 团队联机呼叫流图 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-214">[![Microsoft Teams Online Call Flows Figure 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span></span>

<span data-ttu-id="f1316-215">*图 2-客户的网络内*</span><span class="sxs-lookup"><span data-stu-id="f1316-215">*Figure 2 - Within Customer Network*</span></span>
 
<span data-ttu-id="f1316-216">在步骤 7 中，选择"对等"媒体流 5</span><span class="sxs-lookup"><span data-stu-id="f1316-216">In step 7, "peer to peer" media flow 5 is selected</span></span> 
><span data-ttu-id="f1316-217">**注意**： 媒体为双向。</span><span class="sxs-lookup"><span data-stu-id="f1316-217">**Note**: Media is bidirectional.</span></span> <span data-ttu-id="f1316-218">流 5 的方向指示一方启动从连接角度来看，将其与本文档中的所有流一致的通信。</span><span class="sxs-lookup"><span data-stu-id="f1316-218">The direction of flow 5 indicates that one side initiates the communication from connectivity perspective, consistent with all the flows in this document.</span></span> <span data-ttu-id="f1316-219">在这种情况下，无论使用哪个方向，因为这两个终结点客户网络内部。</span><span class="sxs-lookup"><span data-stu-id="f1316-219">In this case, it doesn't matter which direction is used because both endpoints are within the Customer Network.</span></span>

<span data-ttu-id="f1316-220">**客户网络向外部用户 （媒体中继的团队传输中继）：**</span><span class="sxs-lookup"><span data-stu-id="f1316-220">**Customer Network to External User (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="f1316-221">[![Microsoft 团队联机呼叫流图 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-221">[![Microsoft Teams Online Call Flows Figure 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span></span>

<span data-ttu-id="f1316-222">*图 3-客户网络向外部用户 （媒体中继的团队传输中继）*</span><span class="sxs-lookup"><span data-stu-id="f1316-222">*Figure 3 - Customer Network to External User (media relayed by Teams Transport Relay)*</span></span>
 
<span data-ttu-id="f1316-223">在步骤 7 中，选择 4，从到 Office 365 客户网络和流 3，来自远程移动到 Office 365 的团队用户。</span><span class="sxs-lookup"><span data-stu-id="f1316-223">In step 7, flow 4, from Customer Network to Office 365, and flow 3, from remote mobile Teams user to Office 365, are selected.</span></span> <span data-ttu-id="f1316-224">通过 Office 365 中的团队传输中继中继这些流程。</span><span class="sxs-lookup"><span data-stu-id="f1316-224">These flows are relayed by Teams Transport Relay within Office 365.</span></span>

><span data-ttu-id="f1316-225">**注意**： 媒体是双向，其中方向表示哪一侧启动从连接角度通信。</span><span class="sxs-lookup"><span data-stu-id="f1316-225">**Note**: Media is bidirectional, where direction indicates which side initiates the communication from connectivity perspective.</span></span> <span data-ttu-id="f1316-226">在这种情况下，这些流程用于信号和媒体，通过不同的传输协议和地址。</span><span class="sxs-lookup"><span data-stu-id="f1316-226">In this case, these flows are used for signaling and media, via different transport protocols and addresses.</span></span>

<span data-ttu-id="f1316-227">**客户网络向外部用户 （直接媒体）：**</span><span class="sxs-lookup"><span data-stu-id="f1316-227">**Customer Network to External User (direct media):**</span></span>

<span data-ttu-id="f1316-228">[![Microsoft 团队联机呼叫流图 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-228">[![Microsoft Teams Online Call Flows Figure 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span></span>

<span data-ttu-id="f1316-229">*图 4-客户网络向外部用户 （直接媒体）*</span><span class="sxs-lookup"><span data-stu-id="f1316-229">*Figure 4 - Customer Network to External User (direct media)*</span></span>
 
<span data-ttu-id="f1316-230">在步骤 7 中，从 internet （客户端的对等） 的客户网络的流 2 中，处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="f1316-230">In step 7, flow 2, from Customer Network to Internet (client's peer), is selected.</span></span>
><span data-ttu-id="f1316-231">**说明**：</span><span class="sxs-lookup"><span data-stu-id="f1316-231">**Notes**:</span></span> 
>- <span data-ttu-id="f1316-232">媒体直接与远程移动用户 （即不中继通过 Office 365 云） 是可选的。</span><span class="sxs-lookup"><span data-stu-id="f1316-232">Direct media with remote mobile user (i.e., not relayed through Office 365 cloud) is optional.</span></span> <span data-ttu-id="f1316-233">换句话说，客户可以阻止此路径并这样，强制实施通过 Office 365 云中传输中继的媒体路径。</span><span class="sxs-lookup"><span data-stu-id="f1316-233">In other words, customer may block this path and by doing so, enforce a media path through Transport Relay in Office 365 cloud.</span></span>
>- <span data-ttu-id="f1316-234">媒体为双向。</span><span class="sxs-lookup"><span data-stu-id="f1316-234">Media is bidirectional.</span></span> <span data-ttu-id="f1316-235">到远程移动用户的流 2 的方向指示一方启动从连接角度的通信。</span><span class="sxs-lookup"><span data-stu-id="f1316-235">The direction of flow 2 to remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span> 

<span data-ttu-id="f1316-236">**VPN 用户与内部用户 （媒体中继的团队传输中继）**</span><span class="sxs-lookup"><span data-stu-id="f1316-236">**VPN User to Internal User (media relayed by Teams Transport Relay)**</span></span>

<span data-ttu-id="f1316-237">[![Microsoft 团队联机呼叫流图 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-237">[![Microsoft Teams Online Call Flows Figure 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span></span>

<span data-ttu-id="f1316-238">*图 5-VPN 用户与内部用户 （媒体中继的团队传输中继）*</span><span class="sxs-lookup"><span data-stu-id="f1316-238">*Figure 5 - VPN User to Internal User (media relayed by Teams Transport Relay)*</span></span>
 
<span data-ttu-id="f1316-239">信号客户通过流 2，并与网络流 4 到 Office 365 的 VPN。</span><span class="sxs-lookup"><span data-stu-id="f1316-239">Signaling VPN to Customer Network via flow 2' and flow 4 to Office 365.</span></span> <span data-ttu-id="f1316-240">但是，媒体"绕过"VPN 和通过流 3 和 4 到 Office 365 云团队媒体中继路由。</span><span class="sxs-lookup"><span data-stu-id="f1316-240">However, media "bypass" VPN and routed via flows 3 and 4 through Teams media relay in Office 365 cloud.</span></span>

<span data-ttu-id="f1316-241">**VPN 用户与内部用户 （直接媒体）**</span><span class="sxs-lookup"><span data-stu-id="f1316-241">**VPN User to Internal User (direct media)**</span></span>

<span data-ttu-id="f1316-242">[![Microsoft 团队联机呼叫流图 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-242">[![Microsoft Teams Online Call Flows Figure 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span></span>

<span data-ttu-id="f1316-243">*图 6-VPN 用户与内部用户 （直接媒体）*</span><span class="sxs-lookup"><span data-stu-id="f1316-243">*Figure 6 - VPN User to Internal User (direct media)*</span></span>

<span data-ttu-id="f1316-244">通过 2 向客户网络和流 4 到 Office 365 信号到客户网络的 VPN。</span><span class="sxs-lookup"><span data-stu-id="f1316-244">Signaling VPN to Customer Network via flow 2' to Customer Network and flow 4 to Office 365.</span></span> <span data-ttu-id="f1316-245">但是，媒体"绕过"VPN 和路由通过流 2 从客户的网络到 internet。</span><span class="sxs-lookup"><span data-stu-id="f1316-245">However, media "bypass" VPN and routed via flow 2 from Customer Network to the internet.</span></span>

><span data-ttu-id="f1316-246">**注意**： 媒体为双向。</span><span class="sxs-lookup"><span data-stu-id="f1316-246">**Note**: Media is bidirectional.</span></span> <span data-ttu-id="f1316-247">到远程移动用户的流 2 的方向指示一方启动从连接角度的通信。</span><span class="sxs-lookup"><span data-stu-id="f1316-247">The direction of flow 2 to remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

<span data-ttu-id="f1316-248">**VPN 用户与外部用户 （直接媒体）**</span><span class="sxs-lookup"><span data-stu-id="f1316-248">**VPN User to External User (direct media)**</span></span>

<span data-ttu-id="f1316-249">[![Microsoft 团队联机呼叫流图 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-249">[![Microsoft Teams Online Call Flows Figure 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span></span>

<span data-ttu-id="f1316-250">*图 7-VPN 用户与外部用户 （直接媒体）*</span><span class="sxs-lookup"><span data-stu-id="f1316-250">*Figure 7 - VPN User to External User (direct media)*</span></span>

<span data-ttu-id="f1316-251">通过 2 向客户网络和流 4 到 Office 365 信号到客户网络的 VPN。</span><span class="sxs-lookup"><span data-stu-id="f1316-251">Signaling VPN to Customer Network via flow 2' to Customer Network and flow 4 to Office 365.</span></span> <span data-ttu-id="f1316-252">但是，媒体"绕过"VPN 和通过流 6 路由。</span><span class="sxs-lookup"><span data-stu-id="f1316-252">However, media "bypass" VPN and routed via flow 6.</span></span>

><span data-ttu-id="f1316-253">**注意**： 媒体为双向。</span><span class="sxs-lookup"><span data-stu-id="f1316-253">**Note**: Media is bidirectional.</span></span> <span data-ttu-id="f1316-254">到远程移动用户的流 6 的方向指示一方启动从连接角度的通信。</span><span class="sxs-lookup"><span data-stu-id="f1316-254">The direction of flow 6 to remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

#### <a name="use-case-teams-to-pstn-through-office-365-trunk"></a><span data-ttu-id="f1316-255">通过 Office 365 中继的 pstn 的使用案例： 团队</span><span class="sxs-lookup"><span data-stu-id="f1316-255">Use Case: Teams to PSTN through Office 365 Trunk</span></span>
<span data-ttu-id="f1316-256">Office 365 云具有允许发出和接收来自公用电话交换网的呼叫的电话系统。</span><span class="sxs-lookup"><span data-stu-id="f1316-256">Office 365 Cloud has a Phone System that allows placing and receiving the calls from Public Switched Telephone Network.</span></span> <span data-ttu-id="f1316-257">如果 PSTN 中继已通过 Office 365 云连接，则使用本例没有特殊连接要求。</span><span class="sxs-lookup"><span data-stu-id="f1316-257">If the PSTN Trunk is connected via Office 365 cloud, then there are no special connectivity requirements for this use case.</span></span> <span data-ttu-id="f1316-258">否则为 （直接路由已部署） 然后参阅**TBD**。</span><span class="sxs-lookup"><span data-stu-id="f1316-258">Otherwise, (Direct Routing is deployed) then see section **TBD**.</span></span>

<span data-ttu-id="f1316-259">[![Microsoft 团队联机呼叫流图 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-259">[![Microsoft Teams Online Call Flows Figure 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span></span>

<span data-ttu-id="f1316-260">*图 8-通过 Office 365 中继的 PSTN 团队*</span><span class="sxs-lookup"><span data-stu-id="f1316-260">*Figure 8 - Teams to PSTN through Office 365 Trunk*</span></span>

#### <a name="use-case-teams-meeting"></a><span data-ttu-id="f1316-261">使用案例： 团队会议</span><span class="sxs-lookup"><span data-stu-id="f1316-261">Use Case: Teams Meeting</span></span>

<span data-ttu-id="f1316-262">音频/视频/屏幕共享 (VBSS) 会议服务器是 Office 365 云的一部分。</span><span class="sxs-lookup"><span data-stu-id="f1316-262">The audio/video/screen sharing (VBSS) conferencing server is part of the Office 365 cloud.</span></span> <span data-ttu-id="f1316-263">具有公共 IP 地址必须从客户网络上可以访问，必须将其从游牧云客户端访问。</span><span class="sxs-lookup"><span data-stu-id="f1316-263">It has a public IP address that must be reachable from the Customer network and must be reachable from a Nomadic Cloud client.</span></span> <span data-ttu-id="f1316-264">每个客户端/终结点需要能够连接到会议服务器。</span><span class="sxs-lookup"><span data-stu-id="f1316-264">Each client/endpoint needs to be able to connect to the conferencing server.</span></span>

<span data-ttu-id="f1316-265">内部客户端将获取本地、 身，和中继候选相同的方式，一对一呼叫所述。</span><span class="sxs-lookup"><span data-stu-id="f1316-265">Internal clients will obtain local, reflexive, and relay candidates in the same manner as described for one-to-one calls.</span></span> <span data-ttu-id="f1316-266">客户端将邀请中的会议服务器发送这些候选人。</span><span class="sxs-lookup"><span data-stu-id="f1316-266">The clients will send these candidates to the conference server in an invite.</span></span> <span data-ttu-id="f1316-267">会议服务器不使用中继，因为它具有一个公共可访问的 IP 地址，以便它与刚其本地的 IP 地址候选的响应。</span><span class="sxs-lookup"><span data-stu-id="f1316-267">The conferencing server does not use a relay since it has a publicly reachable IP address, so it responds with just its local IP address candidate.</span></span> <span data-ttu-id="f1316-268">客户端和会议服务器将检查连接一对一呼叫所述的方式相同。</span><span class="sxs-lookup"><span data-stu-id="f1316-268">The client and conferencing server will check connectivity in the same manner described for one-to-one calls.</span></span> 

><span data-ttu-id="f1316-269">**说明**：</span><span class="sxs-lookup"><span data-stu-id="f1316-269">**Notes**:</span></span>
>- <span data-ttu-id="f1316-270">团队客户端无法加入 Skype 业务会议和 Skype 业务客户端无法加入团队会议。</span><span class="sxs-lookup"><span data-stu-id="f1316-270">Teams clients cannot join Skype for business meetings, and Skype for Business clients cannot join Teams meetings.</span></span>
>- <span data-ttu-id="f1316-271">PSTN 用户 （可选）"拨打中"或"拨出"，取决于会议的 PSTN 呼叫的组织者和/或会议设置。</span><span class="sxs-lookup"><span data-stu-id="f1316-271">PSTN user optionally "Dials IN" or "Dialed OUT", depends on meeting's organizer PSTN Calling and/or conferencing provisioning.</span></span> 
>- <span data-ttu-id="f1316-272">来宾用户或客户的用户可以加入从来宾专用网络，其通过 FW/NAT 术 シ モ メ 严格的规则。</span><span class="sxs-lookup"><span data-stu-id="f1316-272">A guest user or a customer user may join from a guest private network, which is protected via FW/NAT with strict rules.</span></span>

<span data-ttu-id="f1316-273">[![Microsoft 团队联机呼叫流图 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-273">[![Microsoft Teams Online Call Flows Figure 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span></span>

<span data-ttu-id="f1316-274">*图 9-团队会议*</span><span class="sxs-lookup"><span data-stu-id="f1316-274">*Figure 9 - Teams Meeting*</span></span>

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a><span data-ttu-id="f1316-275">与 Skype 的本地业务的使用案例： 联盟</span><span class="sxs-lookup"><span data-stu-id="f1316-275">Use Case: Federation with Skype for Business on premises</span></span>

<span data-ttu-id="f1316-276">**媒体中继的 Office 365 云团队传输中继**</span><span class="sxs-lookup"><span data-stu-id="f1316-276">**Media relayed by Teams Transport Relay in Office 365 Cloud**</span></span>

<span data-ttu-id="f1316-277">[![Microsoft 团队联机呼叫流图 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-277">[![Microsoft Teams Online Call Flows Figure 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span></span>

<span data-ttu-id="f1316-278">*图 10-媒体中继的 Office 365 云团队传输中继*</span><span class="sxs-lookup"><span data-stu-id="f1316-278">*Figure 10 - Media relayed by Teams Transport Relay in Office 365 Cloud*</span></span>

><span data-ttu-id="f1316-279">**说明**：</span><span class="sxs-lookup"><span data-stu-id="f1316-279">**Notes**:</span></span> 
>- <span data-ttu-id="f1316-280">"联盟"根据定义，是两个租户之间的通信。</span><span class="sxs-lookup"><span data-stu-id="f1316-280">"Federation" is, by definition, a communication between two Tenants.</span></span> <span data-ttu-id="f1316-281">在这种情况下，租户 A，使用联机团队，与租户 B，使用本地业务 Skype 建立联盟。</span><span class="sxs-lookup"><span data-stu-id="f1316-281">In this case, tenant A, which uses Teams Online, federates with tenant B, which uses Skype for business on premises.</span></span> <span data-ttu-id="f1316-282">如果租户 B 也使用的 Office 365，然后 Skype 的业务客户端将已使用流 3 与 Office 365 连接。</span><span class="sxs-lookup"><span data-stu-id="f1316-282">If tenant B is also using Office 365, then Skype For Business client would have used flow 3 to connect with Office 365.</span></span>
>- <span data-ttu-id="f1316-283">本文档的范围超出信号和媒体从联合 Skype 的业务客户端到业务其 Skype 部署服务器上。</span><span class="sxs-lookup"><span data-stu-id="f1316-283">Signaling and media from federated Skype For Business client to its Skype for Business on premises server is out of scope of this document.</span></span> <span data-ttu-id="f1316-284">但是，它所示为清楚起见。</span><span class="sxs-lookup"><span data-stu-id="f1316-284">However, it is illustrated here for clarity.</span></span>

<span data-ttu-id="f1316-285">工作组和 for Business 的 Skype 之间信号是"桥接"通过 Office 365 云的网关。</span><span class="sxs-lookup"><span data-stu-id="f1316-285">Signaling between Teams and Skype for Business is "bridged" by a Gateway in Office 365 cloud.</span></span>

<span data-ttu-id="f1316-286">在这种情况下媒体通过团队传输中继到客户网络和远程 Skype 业务客户端通过流 4 的 Office 365 云中继。</span><span class="sxs-lookup"><span data-stu-id="f1316-286">Media in this case is relayed by Teams Transport Relay in Office 365 cloud to Customer Network and Remote Skype for Business client via flows 4.</span></span>

<span data-ttu-id="f1316-287">**Skype 通过中继进行业务媒体中继联盟租户中的媒体**</span><span class="sxs-lookup"><span data-stu-id="f1316-287">**Media relayed by Skype for Business Media Relay in federated tenant**</span></span>

<span data-ttu-id="f1316-288">[![Microsoft 团队联机呼叫流图 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-288">[![Microsoft Teams Online Call Flows Figure 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span></span>

<span data-ttu-id="f1316-289">*图 11-Skype 通过中继进行业务媒体中继联盟租户中的媒体*</span><span class="sxs-lookup"><span data-stu-id="f1316-289">*Figure 11 - Media relayed by Skype for Business Media Relay in federated tenant*</span></span>

><span data-ttu-id="f1316-290">**注意**： 信号和媒体从联合 Skype 的业务客户端到业务其 Skype 部署服务器上已超出本文档的范围。</span><span class="sxs-lookup"><span data-stu-id="f1316-290">**Note**: Signaling and media from federated Skype For Business client to its Skype for Business on premises server is out of scope of this document.</span></span> <span data-ttu-id="f1316-291">但是，它所示为清楚起见。</span><span class="sxs-lookup"><span data-stu-id="f1316-291">However, it is illustrated here for clarity.</span></span>

<span data-ttu-id="f1316-292">工作组和 for Business 的 Skype 之间信号是"桥接"通过 Office 365 云的网关。</span><span class="sxs-lookup"><span data-stu-id="f1316-292">Signaling between Teams and Skype for Business is "bridged" by a Gateway in Office 365 cloud.</span></span>

<span data-ttu-id="f1316-293">在这种情况下媒体通过内部部署到客户网络媒体中继通过流 2 的业务的 Skype 中继。</span><span class="sxs-lookup"><span data-stu-id="f1316-293">Media in this case is relayed by Skype for Business on premises Media Relay to Customer Network via flow 2.</span></span> <span data-ttu-id="f1316-294">（请注意，流量团队用户与联盟的客户网络中远程媒体中继之前将被最初阻止媒体中继反向流量开始流动。</span><span class="sxs-lookup"><span data-stu-id="f1316-294">(Note that traffic from Teams user to the remote Media Relay in federated customer network will be initially blocked by the Media Relay until traffic in the reverse direction starts to flow.</span></span> <span data-ttu-id="f1316-295">但是，双向流中会打开连接两个方向。）</span><span class="sxs-lookup"><span data-stu-id="f1316-295">However, the bidirectional flow will open connectivity in both directions.)</span></span>

<span data-ttu-id="f1316-296">**直接 （对等）**</span><span class="sxs-lookup"><span data-stu-id="f1316-296">**Direct (peer to peer)**</span></span>

<span data-ttu-id="f1316-297">[![Microsoft 团队联机呼叫流图 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-297">[![Microsoft Teams Online Call Flows Figure 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span></span>

<span data-ttu-id="f1316-298">*图 12-直接 （对等）*</span><span class="sxs-lookup"><span data-stu-id="f1316-298">*Figure 12 - Direct (peer to peer)*</span></span>

### <a name="teams-online-hybrid-topology"></a><span data-ttu-id="f1316-299">团队 Online 的混合拓扑</span><span class="sxs-lookup"><span data-stu-id="f1316-299">Teams Online Hybrid Topology</span></span>
<span data-ttu-id="f1316-300">这种拓扑适用类似于工作组联机默认 （"纯"），但"上添加"的本地业务 Skype。</span><span class="sxs-lookup"><span data-stu-id="f1316-300">This topology is similar to Teams Online default ("pure") but "adds on" Skype for business on premises.</span></span>

<span data-ttu-id="f1316-301">[![Microsoft 团队联机呼叫流图 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-301">[![Microsoft Teams Online Call Flows Figure 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span></span>

<span data-ttu-id="f1316-302">*图 13-团队 Online 的混合拓扑*</span><span class="sxs-lookup"><span data-stu-id="f1316-302">*Figure 13 - Teams Online Hybrid Topology*</span></span>
 
><span data-ttu-id="f1316-303">**说明**：</span><span class="sxs-lookup"><span data-stu-id="f1316-303">**Notes**:</span></span>
>- <span data-ttu-id="f1316-304">在上图上箭头的方向反映影响连接功能的企业外围环境的通信的初始方向。</span><span class="sxs-lookup"><span data-stu-id="f1316-304">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="f1316-305">对于媒体 UDP，第一个数据包可能流的反向方向，但可能被阻止这些数据包，直到在其他方向的数据包将流。</span><span class="sxs-lookup"><span data-stu-id="f1316-305">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>
>- <span data-ttu-id="f1316-306">团队 Online 业务 online 部署并排 Skype，因此客户端显示为"团队/SFB 用户"。</span><span class="sxs-lookup"><span data-stu-id="f1316-306">Teams Online is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user".</span></span>

<span data-ttu-id="f1316-307">（在工作组联机"纯"拓扑结构） 的其他流：</span><span class="sxs-lookup"><span data-stu-id="f1316-307">Additional Flows (on top of Teams Online "pure" topology):</span></span>
- <span data-ttu-id="f1316-308">**流 5A** – 表示与业务 Skype 客户网络中部署在客户网络边缘媒体中继上的团队用户之间的对等媒体流。</span><span class="sxs-lookup"><span data-stu-id="f1316-308">**Flow 5A** – Represents a peer to peer media flow between Teams user within Customer Network with a Skype for Business on premises media relay at the Customer Network edge.</span></span>

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a><span data-ttu-id="f1316-309">使用案例： 业务一对一的 Skype 团队</span><span class="sxs-lookup"><span data-stu-id="f1316-309">Use Case: Teams to Skype for Business One-to-one</span></span>
<span data-ttu-id="f1316-310">**客户网络中的混合**</span><span class="sxs-lookup"><span data-stu-id="f1316-310">**Hybrid within Customer Network**</span></span>

<span data-ttu-id="f1316-311">[![Microsoft 团队联机呼叫流图 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-311">[![Microsoft Teams Online Call Flows Figure 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span></span>

<span data-ttu-id="f1316-312">*图 14-客户网络中的混合*</span><span class="sxs-lookup"><span data-stu-id="f1316-312">*Figure 14 - Hybrid within Customer Network*</span></span>
 
<span data-ttu-id="f1316-313">工作组和 Skype 之间信号 for business 是"桥接"通过 Office 365 云的网关。</span><span class="sxs-lookup"><span data-stu-id="f1316-313">Signaling between Teams and Skype for business is "bridged" by a Gateway in Office 365 cloud.</span></span> <span data-ttu-id="f1316-314">但是，媒体直接"对等"客户的网络内通过传送流 5。</span><span class="sxs-lookup"><span data-stu-id="f1316-314">However, media is routed directly "peer to peer" within Customer Network via flow 5.</span></span>

<span data-ttu-id="f1316-315">**与外部业务用户 – Office 365 中继 Skype 混合客户网络**</span><span class="sxs-lookup"><span data-stu-id="f1316-315">**Hybrid Customer Network with External Skype for Business user – relayed by Office 365**</span></span>

<span data-ttu-id="f1316-316">[![Microsoft 团队联机呼叫流图 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-316">[![Microsoft Teams Online Call Flows Figure 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span></span>

<span data-ttu-id="f1316-317">*图 15-与外部业务用户的 Skype 混合客户网络-Office 365 中继*</span><span class="sxs-lookup"><span data-stu-id="f1316-317">*Figure 15 - Hybrid Customer Network with External Skype for Business user - relayed by Office 365*</span></span>
 
><span data-ttu-id="f1316-318">**注意**： 信号和媒体从 Skype 业务客户端 for Business 的 Skype 到内部部署服务器上已超出本文档的范围。</span><span class="sxs-lookup"><span data-stu-id="f1316-318">**Note**: Signaling and media from Skype for Business client to Skype for Business on premises server is out of scope of this document.</span></span> <span data-ttu-id="f1316-319">但是，它所示为清楚起见。</span><span class="sxs-lookup"><span data-stu-id="f1316-319">However, it is illustrated here for clarity.</span></span>

<span data-ttu-id="f1316-320">工作组和 for Business 的 Skype 之间信号是"桥接"通过 Office 365 云的网关。</span><span class="sxs-lookup"><span data-stu-id="f1316-320">Signaling between Teams and Skype for Business is "bridged" by a Gateway in Office 365 cloud.</span></span>

<span data-ttu-id="f1316-321">媒体流 4 通过中继通过团队传输到客户网络的 Office 365 中的中继。</span><span class="sxs-lookup"><span data-stu-id="f1316-321">Media is relayed through Teams Transport Relay in Office 365 to Customer Network through flows 4.</span></span>

<span data-ttu-id="f1316-322">**与外部业务用户 – 通过中继上部署边缘 Skype 混合客户网络**</span><span class="sxs-lookup"><span data-stu-id="f1316-322">**Hybrid Customer Network with External Skype for Business user – relayed by on premises edge**</span></span>

<span data-ttu-id="f1316-323">[![Microsoft 团队联机呼叫流图 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-323">[![Microsoft Teams Online Call Flows Figure 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span></span>

<span data-ttu-id="f1316-324">*图 16-混合客户网络与外部业务用户的 Skype-由中继上部署边缘*</span><span class="sxs-lookup"><span data-stu-id="f1316-324">*Figure 16 - Hybrid Customer Network with External Skype for Business user - relayed by on premises edge*</span></span>
 
><span data-ttu-id="f1316-325">**注意**： 信号和媒体从 Skype 业务客户端到 Skype 的内部部署服务器上的业务已超出本文档的范围。</span><span class="sxs-lookup"><span data-stu-id="f1316-325">**Note**: Signaling and media from Skype for Business client to Skype for business on premises server is out of scope of this document.</span></span> <span data-ttu-id="f1316-326">但是，它所示为清楚起见。</span><span class="sxs-lookup"><span data-stu-id="f1316-326">However, it is illustrated here for clarity.</span></span>

<span data-ttu-id="f1316-327">信号是"桥接"通过 Office 365 云的网关。</span><span class="sxs-lookup"><span data-stu-id="f1316-327">Signaling is "bridged" by a Gateway in Office 365 cloud.</span></span>

<span data-ttu-id="f1316-328">在本地边缘到媒体流 5A 客户网络内部用户团队业务的 Skype 中的业务媒体中继的情况下，媒体中继的 Skype。</span><span class="sxs-lookup"><span data-stu-id="f1316-328">Media is relayed by Skype for Business Media Relay within Skype for Business on premises Edge to Teams user within Customer Network via media flow 5A.</span></span>

### <a name="teams-online-with-direct-routing-topology"></a><span data-ttu-id="f1316-329">团队 Online 与"直接路由"的拓扑</span><span class="sxs-lookup"><span data-stu-id="f1316-329">Teams Online with "Direct Routing" Topology</span></span>
<span data-ttu-id="f1316-330">这种拓扑适用类似于工作组联机 （"纯"），但"上添加"直接路由。</span><span class="sxs-lookup"><span data-stu-id="f1316-330">This topology is similar to Teams Online ("pure") but "adds on" Direct Routing.</span></span> 

<span data-ttu-id="f1316-331">直接路由，以前称为 BYOT （使您自己中继），与第三方公共交换电话服务提供商。</span><span class="sxs-lookup"><span data-stu-id="f1316-331">Direct Routing, previously known as BYOT (Bring Your Own Trunk), with a third party Public Switched Telephone Service provider.</span></span> <span data-ttu-id="f1316-332">此方法是通过配对的受支持的本地客户拥有会话边界控制器硬件设备到 Office 365 云，并连接到该设备的电话中继可能。</span><span class="sxs-lookup"><span data-stu-id="f1316-332">This method is possible by pairing a supported on-premises customer-owned Session Border Controller hardware device to Office 365 Cloud, and connecting the telephony trunk to that device.</span></span> 

<span data-ttu-id="f1316-333">若要支持这种情况下，客户必须直接路由从 Microsoft 认证合作伙伴的部署认证的 SBC(s)。</span><span class="sxs-lookup"><span data-stu-id="f1316-333">To support this scenario, the customer must deploy certified SBC(s) for Direct Routing from one of Microsoft's certified partners.</span></span> <span data-ttu-id="f1316-334">SBC 必须按照供应商，建议正确配置，并为可路由从 Office 365 云中的直接 UDP 流量。</span><span class="sxs-lookup"><span data-stu-id="f1316-334">The SBC must be configured properly, as recommended by the vendor, and be routable from Office 365 Cloud for direct UDP traffic.</span></span> <span data-ttu-id="f1316-335">媒体可能直接从流向团队/Skype 业务客户端的 SBC （旁路团队网关 (即，MP)） 或遍历通过团队网关。</span><span class="sxs-lookup"><span data-stu-id="f1316-335">The media may flow directly from Teams/Skype for Business client to the SBC (bypass Teams Gateway (i.e., MP)) or traverse through Teams Gateway.</span></span> <span data-ttu-id="f1316-336">与 SBC，连接时中继配置为绕过团队网关，基于的 ICE，其中 SBC 支持 ICE Lite，而对业务媒体端点的团队/Skype 支持 ICE 完全。</span><span class="sxs-lookup"><span data-stu-id="f1316-336">The connectivity with the SBC, when trunk is configured to bypass Teams Gateway, is based on ICE, where SBC supports ICE-Lite, while Teams/Skype for Business media endpoint supports ICE Full.</span></span> 

<span data-ttu-id="f1316-337">[![Microsoft 团队联机呼叫流图 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-337">[![Microsoft Teams Online Call Flows Figure 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span></span>

<span data-ttu-id="f1316-338">*图 17-团队 Onine 与直接路由的拓扑*</span><span class="sxs-lookup"><span data-stu-id="f1316-338">*Figure 17 - Teams Onine with 'Direct Routing' Topology*</span></span>

><span data-ttu-id="f1316-339">**说明**：</span><span class="sxs-lookup"><span data-stu-id="f1316-339">**Notes**:</span></span>
>- <span data-ttu-id="f1316-340">在上图上箭头的方向反映影响连接功能的企业外围环境的通信的初始方向。</span><span class="sxs-lookup"><span data-stu-id="f1316-340">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="f1316-341">对于媒体 UDP，第一个数据包可能流的反向方向，但可能被阻止这些数据包，直到在其他方向的数据包将流。</span><span class="sxs-lookup"><span data-stu-id="f1316-341">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>
>- <span data-ttu-id="f1316-342">团队 Online 业务 online 部署并排 Skype，因此客户端显示为"团队/SFB 用户"。</span><span class="sxs-lookup"><span data-stu-id="f1316-342">Teams Online is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user".</span></span>

<span data-ttu-id="f1316-343">（在工作组联机"纯"拓扑结构） 的其他流：</span><span class="sxs-lookup"><span data-stu-id="f1316-343">Additional Flows (on top of Teams Online "pure" topology):</span></span>
- <span data-ttu-id="f1316-344">**流 4** -表示一个从 Office 365 云流向客户网络用于建立与本地 SBC 云中团队媒体服务器之间的连接。</span><span class="sxs-lookup"><span data-stu-id="f1316-344">**Flow 4'** - Represents a flow from Office 365 cloud to Customer Network, used to establish a connection between Teams media server in the cloud with the SBC on premises.</span></span>
- <span data-ttu-id="f1316-345">**流 5B** – 表示与直接路由 SBC 客户网络内"绕过"模式中的团队用户之间的媒体流。</span><span class="sxs-lookup"><span data-stu-id="f1316-345">**Flow 5B** – Represents a media flow between Teams user within Customer Network with Direct Routing SBC in "bypass" mode.</span></span>
- <span data-ttu-id="f1316-346">**流 5c** – 表示之间直接路由 SBC 到另一个直接路由 SBC PSTN 发夹呼叫"绕过"模式中的媒体流。</span><span class="sxs-lookup"><span data-stu-id="f1316-346">**Flow 5C** – Represents a media flow between Direct Routing SBC to another Direct Routing SBC in PSTN hairpin call "bypass" mode.</span></span>

<span data-ttu-id="f1316-347">**内部用户直接路由 （媒体中继的 Office 365 中的团队传输中继）**</span><span class="sxs-lookup"><span data-stu-id="f1316-347">**Internal User Direct Routing (media relayed by Teams Transport Relay in Office 365)**</span></span>

<span data-ttu-id="f1316-348">[![Microsoft 团队联机呼叫流图 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-348">[![Microsoft Teams Online Call Flows Figure 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span></span>

<span data-ttu-id="f1316-349">*图 18-内部用户直接路由 （媒体中继的 Office 365 中的团队传输中继）*</span><span class="sxs-lookup"><span data-stu-id="f1316-349">*Figure 18 - Internal User Direct Routing (media relayed by Teams Transport Relay in Office 365)*</span></span>
 
><span data-ttu-id="f1316-350">**注意**： SBC 必须是从 Office 365 可穿绕的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="f1316-350">**Note**: SBC MUST have a public IP address that is routable from Office 365.</span></span>

<span data-ttu-id="f1316-351">信号和媒体从 SBC 到 Office 365，反之亦然使用流 4，和/或流 4。</span><span class="sxs-lookup"><span data-stu-id="f1316-351">Signaling and Media from SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

<span data-ttu-id="f1316-352">信号和媒体从客户的网络内的客户端与 Office 365 云使用流 4。</span><span class="sxs-lookup"><span data-stu-id="f1316-352">Signaling and Media from client within Customer Network to Office 365 cloud use flow 4.</span></span>


<span data-ttu-id="f1316-353">**远程用户直接路由 （媒体路由至 Office 365 中的媒体服务器 (MP)）**</span><span class="sxs-lookup"><span data-stu-id="f1316-353">**Remote User Direct Routing (media is routed through a media server (MP) in Office 365)**</span></span>

<span data-ttu-id="f1316-354">[![Microsoft 团队联机呼叫流图 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-354">[![Microsoft Teams Online Call Flows Figure 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span></span>

<span data-ttu-id="f1316-355">*图 19-远程用户直接路由 （媒体路由至 Office 365 中的媒体服务器 (MP)）*</span><span class="sxs-lookup"><span data-stu-id="f1316-355">*Figure 19 - Remote User Direct Routing (media is routed through a media server (MP) in Office 365)*</span></span>
 
><span data-ttu-id="f1316-356">**注意**： SBC 必须是从 Office 365 可穿绕的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="f1316-356">**Note**: SBC MUST have a public IP address that is routable from Office 365.</span></span>

<span data-ttu-id="f1316-357">信号和媒体从 SBC 到 Office 365，反之亦然使用流 4，和/或流 4。</span><span class="sxs-lookup"><span data-stu-id="f1316-357">Signaling and Media from SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

<span data-ttu-id="f1316-358">信号和媒体从 Internet 上的客户端与 Office 365 云使用流 3。</span><span class="sxs-lookup"><span data-stu-id="f1316-358">Signaling and Media from client on the Internet to Office 365 cloud use flow 3.</span></span>

<span data-ttu-id="f1316-359">**内部用户直接路由 （媒体绕过）**</span><span class="sxs-lookup"><span data-stu-id="f1316-359">**Internal user Direct Routing (media bypass)**</span></span>

<span data-ttu-id="f1316-360">[![Microsoft 团队联机呼叫流图 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-360">[![Microsoft Teams Online Call Flows Figure 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span></span>

<span data-ttu-id="f1316-361">*图 20-直接路由 （媒体绕过） 的内部用户*</span><span class="sxs-lookup"><span data-stu-id="f1316-361">*Figure 20 - Internal user Direct Routing (media bypass)*</span></span>
 
><span data-ttu-id="f1316-362">**注意**： SBC 必须是从 Office 365 可穿绕的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="f1316-362">**Note**: SBC MUST have a public IP address that is routable from Office 365.</span></span>

<span data-ttu-id="f1316-363">使用从 SBC 到 Office 365，反之亦然信号流 4 和/或流 4。</span><span class="sxs-lookup"><span data-stu-id="f1316-363">Signaling from SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

<span data-ttu-id="f1316-364">从客户的网络内的客户端到 Office 365 云使用流 4 的信号。</span><span class="sxs-lookup"><span data-stu-id="f1316-364">Signaling from client within Customer Network to Office 365 cloud use flow 4.</span></span>

<span data-ttu-id="f1316-365">媒体从客户的网络内的客户端到客户的网络内的 SBC 使用流 5B。</span><span class="sxs-lookup"><span data-stu-id="f1316-365">Media from client within Customer Network to SBC within Customer Network use flow 5B.</span></span>

<span data-ttu-id="f1316-366">**远程用户直接路由 （由 Office 365 中的团队传输中继中继的媒体绕过）**</span><span class="sxs-lookup"><span data-stu-id="f1316-366">**Remote user Direct Routing (media bypass relayed by Teams Transport Relay in Office 365)**</span></span>

<span data-ttu-id="f1316-367">[![Microsoft 团队联机呼叫流图 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-367">[![Microsoft Teams Online Call Flows Figure 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span></span>

<span data-ttu-id="f1316-368">*图 21-远程用户直接路由 （由 Office 365 中的团队传输中继中继的媒体绕过）*</span><span class="sxs-lookup"><span data-stu-id="f1316-368">*Figure 21 - Remote user Direct Routing (media bypass relayed by Teams Transport Relay in Office 365)*</span></span>
 
><span data-ttu-id="f1316-369">**注意**： SBC 必须是从 Office 365 和 Internet 可路由的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="f1316-369">**Note**: SBC MUST have a public IP address that is routable from Office 365 and Internet.</span></span>

<span data-ttu-id="f1316-370">使用从 SBC 到 Office 365，反之亦然信号流 4 和/或流 4。</span><span class="sxs-lookup"><span data-stu-id="f1316-370">Signaling from SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

<span data-ttu-id="f1316-371">从 Internet 上的客户端到 Office 365 云使用流 3 信号。</span><span class="sxs-lookup"><span data-stu-id="f1316-371">Signaling from client on the Internet to Office 365 cloud use flow 3.</span></span>

<span data-ttu-id="f1316-372">媒体从 Internet 上的客户端到客户的网络内的 SBC 使用流 3 和 4 时，由 Office 365 云团队传输中继中继。</span><span class="sxs-lookup"><span data-stu-id="f1316-372">Media from client on the Internet to SBC within Customer Network use flows 3 and 4, relayed by Teams Transport Relay in Office 365 cloud.</span></span> 

<span data-ttu-id="f1316-373">**远程用户直接路由 （媒体绕过直接）**</span><span class="sxs-lookup"><span data-stu-id="f1316-373">**Remote user Direct Routing (media bypass direct)**</span></span>

<span data-ttu-id="f1316-374">[![Microsoft 团队联机呼叫流图 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-374">[![Microsoft Teams Online Call Flows Figure 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span></span>

<span data-ttu-id="f1316-375">*图 22-远程用户直接路由 （媒体绕过直接）*</span><span class="sxs-lookup"><span data-stu-id="f1316-375">*Figure 22 - Remote user Direct Routing (media bypass direct)*</span></span>
 
><span data-ttu-id="f1316-376">**注意**： SBC 必须是从 Office 365 和 Internet 可路由的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="f1316-376">**Note**: SBC MUST have a public IP address that is routable from Office 365 and Internet.</span></span>

<span data-ttu-id="f1316-377">使用从 SBC 到 Office 365，反之亦然信号流 4 和/或流 4。</span><span class="sxs-lookup"><span data-stu-id="f1316-377">Signaling from SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

<span data-ttu-id="f1316-378">从 Internet 上的客户端到 Office 365 云使用流 3 信号。</span><span class="sxs-lookup"><span data-stu-id="f1316-378">Signaling from client on the Internet to Office 365 cloud use flow 3.</span></span>

<span data-ttu-id="f1316-379">媒体从 Internet 上的客户端到客户的网络内的 SBC 使用流 2。</span><span class="sxs-lookup"><span data-stu-id="f1316-379">Media from client on the Internet to SBC within Customer Network use flow 2.</span></span>

<span data-ttu-id="f1316-380">**直接路由 （媒体绕过） – （由于呼叫转接/传输） 的 PSTN 发夹呼叫**</span><span class="sxs-lookup"><span data-stu-id="f1316-380">**Direct Routing (media bypass) – PSTN hairpin call (due to call forward/transfer)**</span></span>

<span data-ttu-id="f1316-381">[![Microsoft 团队联机呼叫流图 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-381">[![Microsoft Teams Online Call Flows Figure 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span></span>

<span data-ttu-id="f1316-382">*图 23-直接路由 （媒体绕过）-PSTN 发夹呼叫 （由于呼叫转接/传输）*</span><span class="sxs-lookup"><span data-stu-id="f1316-382">*Figure 23 - Direct Routing (media bypass) - PSTN hairpin call (due to call forward/transfer)*</span></span>
 
><span data-ttu-id="f1316-383">**注意**： SBC 必须是从 Office 365 可穿绕的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="f1316-383">**Note**: SBC MUST have a public IP address that is routable from Office 365.</span></span>

<span data-ttu-id="f1316-384">使用从 SBC 到 Office 365，反之亦然信号流 4 和/或流 4。</span><span class="sxs-lookup"><span data-stu-id="f1316-384">Signaling from SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

<span data-ttu-id="f1316-385">客户端是不足的信号和媒体循环发夹从 PSTN 向 PSTN 呼叫后。</span><span class="sxs-lookup"><span data-stu-id="f1316-385">Client is out of the signaling and media loop after the call is hairpin from PSTN to PSTN.</span></span>

<span data-ttu-id="f1316-386">从客户的网络内的 SBC 实例 A 到 SBC 实例 B （其中，A 和 B 可以是同一个实例） 的客户网络内的媒体使用流 5 c。</span><span class="sxs-lookup"><span data-stu-id="f1316-386">Media from SBC instance A within Customer Network to SBC instance B within Customer Network (where, A and B can be the same instance) use flow 5C.</span></span>

<span data-ttu-id="f1316-387">**跨两个租户 PSTN 发夹呼叫直接路由 （通过 Office 365 的媒体 –）**</span><span class="sxs-lookup"><span data-stu-id="f1316-387">**Direct Routing (media through Office 365) – PSTN hairpin call across two tenants**</span></span>

<span data-ttu-id="f1316-388">[![Microsoft 团队联机呼叫流图 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-388">[![Microsoft Teams Online Call Flows Figure 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span></span>

<span data-ttu-id="f1316-389">*跨两个租户的图 24-直接路由 （媒体通过 Office 365） – PSTN 发夹呼叫*</span><span class="sxs-lookup"><span data-stu-id="f1316-389">*Figure 24 - Direct Routing (media through Office 365) – PSTN hairpin call across two tenants*</span></span>
 
><span data-ttu-id="f1316-390">**注意**： SBC 必须是从 Office 365 可穿绕的公共 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="f1316-390">**Note**: SBC MUST have a public IP address that is routable from Office 365.</span></span>

<span data-ttu-id="f1316-391">使用从 SBC 到 Office 365，反之亦然信号流 4 和/或流 4。</span><span class="sxs-lookup"><span data-stu-id="f1316-391">Signaling from SBC to Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

<span data-ttu-id="f1316-392">客户端是不足的信号和媒体循环发夹从 PSTN 向 PSTN 呼叫后。</span><span class="sxs-lookup"><span data-stu-id="f1316-392">Client is out of the signaling and media loop after the call is hairpin from PSTN to PSTN.</span></span>

<span data-ttu-id="f1316-393">从内客户网络 X 的 SBC 实例 A 到 SBC 实例 B 必须通过 O365 媒体服务器中继和不能使用媒体绕过模式。</span><span class="sxs-lookup"><span data-stu-id="f1316-393">Media from SBC instance A within Customer Network X to SBC instance B must be relayed through O365 Media Server and can't use bypass mode.</span></span>

## <a name="teams-w-express-route-optimization"></a><span data-ttu-id="f1316-394">具有 Express 路由优化的团队</span><span class="sxs-lookup"><span data-stu-id="f1316-394">Teams w/ Express Route optimization</span></span>

<span data-ttu-id="f1316-395">[![Microsoft 团队联机呼叫流图 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-395">[![Microsoft Teams Online Call Flows Figure 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span></span>

<span data-ttu-id="f1316-396">*图 25-与 Express 路由优化的团队*</span><span class="sxs-lookup"><span data-stu-id="f1316-396">*Figure 25 - Teams with Express Route optimization*</span></span>
 
<span data-ttu-id="f1316-397">在这种情况的两端对齐 Express 路由并将其部署，然后团队流无法重新路由从流流 1 并从流 4 1 的排列的 4。</span><span class="sxs-lookup"><span data-stu-id="f1316-397">In the case that Express Route is justified and deployed, then Teams flows could be re-routed from flow 4 to flow 1 and from flow 4' to flow 1'.</span></span> <span data-ttu-id="f1316-398">但是，团队应用程序具有硬依赖项其他 OFFICE 365 流通过流 4 通过 internet 和 4;因此必须不阻止这些流程。</span><span class="sxs-lookup"><span data-stu-id="f1316-398">However, Teams Application has hard dependency on other OFFICE 365 flows over the internet via flows 4 and 4'; hence these flows must not be blocked.</span></span> 

<span data-ttu-id="f1316-399">请注意业务混合边缘流量的 Skype 被路由到 Internet，而不适用于 Express 路由与外部用户和与其他租户的"联盟"进行通信。</span><span class="sxs-lookup"><span data-stu-id="f1316-399">Note that Skype for Business Hybrid Edge traffic is routed to the Internet and not to Express Route to communicate with external users and "federation" with other tenants.</span></span> 

<span data-ttu-id="f1316-400">若要阻止非对称流，请重新路由而必须在两个方向。</span><span class="sxs-lookup"><span data-stu-id="f1316-400">To prevent asymmetrical flows, re-routing must be in both directions.</span></span> <span data-ttu-id="f1316-401">换句话说，客户网络内的地址是通过 Internet 或 Express 路由，基于优化，而不是通过同时，可穿绕的。</span><span class="sxs-lookup"><span data-stu-id="f1316-401">In other words, an address within Customer Network is routable either through Internet or Express Route, based on optimization, but not through both.</span></span>

<span data-ttu-id="f1316-402">例如：</span><span class="sxs-lookup"><span data-stu-id="f1316-402">For example:</span></span>

<span data-ttu-id="f1316-403">**客户网络向外部用户 （媒体中继的团队传输中继）：**</span><span class="sxs-lookup"><span data-stu-id="f1316-403">**Customer Network to External User (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="f1316-404">[![Microsoft 团队联机呼叫流图 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span><span class="sxs-lookup"><span data-stu-id="f1316-404">[![Microsoft Teams Online Call Flows Figure 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span></span>

<span data-ttu-id="f1316-405">*图 26-客户网络向外部用户 （媒体中继的团队传输中继）*</span><span class="sxs-lookup"><span data-stu-id="f1316-405">*Figure 26 - Customer Network to External User (media relayed by Teams Transport Relay)*</span></span>
 
<span data-ttu-id="f1316-406">**简要步骤：**</span><span class="sxs-lookup"><span data-stu-id="f1316-406">**High Level Steps:**</span></span>
1. <span data-ttu-id="f1316-407">客户网络中的团队用户解析 URL 域名 (DNS) 通过 flow2</span><span class="sxs-lookup"><span data-stu-id="f1316-407">Teams User within Customer Network resolves URL domain name (DNS) via flow2</span></span>
2. <span data-ttu-id="f1316-408">客户网络中的团队用户分配媒体中继端口团队传输中继上的通过流 1</span><span class="sxs-lookup"><span data-stu-id="f1316-408">Teams User within Customer Network allocates a media Relay port on Teams Transport Relay via flow 1</span></span>
3. <span data-ttu-id="f1316-409">客户网络中的团队用户发送与通过流 1 到 Office 365 的 ICE 候选人"邀请"</span><span class="sxs-lookup"><span data-stu-id="f1316-409">Teams User within Customer Network sends "invite" with ICE candidates via flow 1 to Office 365</span></span>
4. <span data-ttu-id="f1316-410">OFFICE 365 将通知发送给外部团队用户通过流 3</span><span class="sxs-lookup"><span data-stu-id="f1316-410">OFFICE 365 sends notification to external Teams User via flow 3</span></span>
5. <span data-ttu-id="f1316-411">团队外部用户分配媒体中继端口团队传输中继上的通过流 3</span><span class="sxs-lookup"><span data-stu-id="f1316-411">Teams external User allocates a media Relay port on Teams Transport Relay via flow 3</span></span>
6. <span data-ttu-id="f1316-412">团队外部用户发送与通过流 3，转发回到通过流 1 的团队用户 A 的 ICE 候选人"应答"</span><span class="sxs-lookup"><span data-stu-id="f1316-412">Teams external User sends "answer" with ICE candidates via flow 3, which is forwarded back to Teams User A via Flow 1</span></span>
7. <span data-ttu-id="f1316-413">团队用户 A 和团队用户 B 调用 ICE 连接测试，并选择流 1 和 3，由 Office 365 云团队传输中继中继。</span><span class="sxs-lookup"><span data-stu-id="f1316-413">Teams User A and Teams User B invoke ICE connectivity tests and selects flows 1 and 3, which are relayed by Teams Transport Relay in Office 365 cloud.</span></span>
8. <span data-ttu-id="f1316-414">团队用户通过流 1 和 3 将遥测发送到 Office 365</span><span class="sxs-lookup"><span data-stu-id="f1316-414">Teams Users send telemetry to Office 365 via flows 1 and 3</span></span>

><span data-ttu-id="f1316-415">**注意**： 必须启用流 4 以对其他微服务要求流 4 支持团队应用程序依赖项。</span><span class="sxs-lookup"><span data-stu-id="f1316-415">**Note**: Flow 4 must be enabled to support dependencies of Teams application on other micro-services that mandates flow 4.</span></span>
