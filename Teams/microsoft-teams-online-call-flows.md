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
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: 了解如何Teams拓扑Office 365流，以及用于对等媒体通信的唯一团队流。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 27a2c68483c3d54cb3f3572bbed3a06a53ccc67e
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059206"
---
# <a name="microsoft-teams-call-flows"></a><span data-ttu-id="579df-103">Microsoft Teams 通话流程</span><span class="sxs-lookup"><span data-stu-id="579df-103">Microsoft Teams call flows</span></span>

> [!TIP]
> <span data-ttu-id="579df-104">观看此会话，了解如何Teams网络以及如何规划最佳网络连接：Teams[规划](https://aka.ms/teams-networking)。</span><span class="sxs-lookup"><span data-stu-id="579df-104">Watch this session to learn how Teams leverages your network and how to plan for optimal network connectivity: [Teams Network Planning](https://aka.ms/teams-networking).</span></span>

## <a name="overview"></a><span data-ttu-id="579df-105">概述</span><span class="sxs-lookup"><span data-stu-id="579df-105">Overview</span></span>

<span data-ttu-id="579df-106">本文介绍如何Teams拓扑Microsoft 365 Office 365调用流。</span><span class="sxs-lookup"><span data-stu-id="579df-106">This article describes how Teams uses Microsoft 365 or Office 365 call flows in various topologies.</span></span> <span data-ttu-id="579df-107">此外，还介绍了Teams媒体通信的唯一流。</span><span class="sxs-lookup"><span data-stu-id="579df-107">In addition, it describes unique Teams flows that are used for peer-to-peer media communication.</span></span> <span data-ttu-id="579df-108">本文档介绍这些流及其用途，以及网络上流的来源和终止。</span><span class="sxs-lookup"><span data-stu-id="579df-108">The document describes these flows, their purpose, and their origin and termination on the network.</span></span> <span data-ttu-id="579df-109">出于本文的目的，假设以下各项：</span><span class="sxs-lookup"><span data-stu-id="579df-109">For purposes of this article, assume the following:</span></span>

- <span data-ttu-id="579df-110">Flow本地客户端使用 X 与云中的Microsoft 365 Office 365服务通信。</span><span class="sxs-lookup"><span data-stu-id="579df-110">Flow X is used by the on-premises client to communicate with the Microsoft 365 or Office 365 service in the cloud.</span></span> <span data-ttu-id="579df-111">它源自客户网络，以终结点或终结点Microsoft 365 Office 365。</span><span class="sxs-lookup"><span data-stu-id="579df-111">It originates from the customer network, and it terminates as an endpoint in Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="579df-112">Flow本地客户端使用 Y 与 Internet 上具有依赖关系的Microsoft 365 Office 365通信。</span><span class="sxs-lookup"><span data-stu-id="579df-112">Flow Y is used by the on-premises client to communicate with a service on the Internet that Microsoft 365 or Office 365 has a dependency on.</span></span> <span data-ttu-id="579df-113">它源自客户网络，在 Internet 上终止为终结点。</span><span class="sxs-lookup"><span data-stu-id="579df-113">It originates from the customer network, and it terminates as an endpoint on the Internet.</span></span>

<span data-ttu-id="579df-114">本文介绍以下信息：</span><span class="sxs-lookup"><span data-stu-id="579df-114">This article covers the following information:</span></span>

- <span data-ttu-id="579df-115">**背景**。</span><span class="sxs-lookup"><span data-stu-id="579df-115">**Background**.</span></span> <span data-ttu-id="579df-116">提供背景信息，例如流可能遍历的网络、流量类型、从客户网络到 Microsoft 365 或 Office 365 服务终结点的连接指南、第三方组件的互操作性，以及 Teams 用于选择媒体流的原则。</span><span class="sxs-lookup"><span data-stu-id="579df-116">Provides background information such as networks that the flows may traverse, types of traffic, connectivity guidance from the customer network to Microsoft 365 or Office 365 service endpoints, interoperability with third-party components, and principles that are used by Teams to select media flows.</span></span>

- <span data-ttu-id="579df-117">**调用各种拓扑中的流**。</span><span class="sxs-lookup"><span data-stu-id="579df-117">**Call flows in various topologies**.</span></span> <span data-ttu-id="579df-118">演示如何在各种拓扑中使用调用流。</span><span class="sxs-lookup"><span data-stu-id="579df-118">Illustrates the use of call flows in various topologies.</span></span> <span data-ttu-id="579df-119">对于每个拓扑，该部分枚举所有受支持的流，并说明如何在多种用例中使用这些流。</span><span class="sxs-lookup"><span data-stu-id="579df-119">For each topology, the section enumerates all supported flows and illustrates how these flows are used in several use cases.</span></span> <span data-ttu-id="579df-120">对于每个用例，它使用流程图描述流的序列和选择。</span><span class="sxs-lookup"><span data-stu-id="579df-120">For each use case, it describes the sequence and selection of flows using a flow diagram.</span></span>

- <span data-ttu-id="579df-121">**Teams Express Route 优化。**</span><span class="sxs-lookup"><span data-stu-id="579df-121">**Teams with Express Route optimization**.</span></span> <span data-ttu-id="579df-122">介绍部署 Express Route 进行优化时如何使用这些流，使用简单的拓扑进行演示。</span><span class="sxs-lookup"><span data-stu-id="579df-122">Describes how these flows are used when Express Route is deployed for optimization, illustrated using a simple topology.</span></span>

## <a name="background"></a><span data-ttu-id="579df-123">背景</span><span class="sxs-lookup"><span data-stu-id="579df-123">Background</span></span>

### <a name="network-segments"></a><span data-ttu-id="579df-124">网段</span><span class="sxs-lookup"><span data-stu-id="579df-124">Network segments</span></span>

<span data-ttu-id="579df-125">**客户网络**。</span><span class="sxs-lookup"><span data-stu-id="579df-125">**Customer network**.</span></span> <span data-ttu-id="579df-126">这是您控制和管理的网络段。</span><span class="sxs-lookup"><span data-stu-id="579df-126">This is the network segment that you control and manage.</span></span> <span data-ttu-id="579df-127">这包括客户办公室内的所有客户连接，无论是有线连接还是无线连接、办公大楼间的连接、与本地数据中心的连接，以及 Internet 提供商、Express Route 或其他任何专用对等互连的连接。</span><span class="sxs-lookup"><span data-stu-id="579df-127">This includes all customer connections within customer offices, whether wired or wireless, connections between office buildings, connections to on-premises datacenters, and your connections to Internet providers, Express Route, or any other private peering.</span></span>

<span data-ttu-id="579df-128">通常，客户网络具有多个网络外围，防火墙和/或代理服务器强制实施组织的安全策略，并且仅允许已设置和配置的某些网络流量。</span><span class="sxs-lookup"><span data-stu-id="579df-128">Typically, a customer network has several network perimeters with firewalls and/or proxy servers, which enforce your organization's security policies, and that only allow certain network traffic that you have set up and configured.</span></span> <span data-ttu-id="579df-129">由于你管理此网络，因此你可以直接控制网络的性能，我们建议你完成网络评估，以验证网络站点内部的性能，以及从网络到 Microsoft 365 或 Office 365 网络的性能。</span><span class="sxs-lookup"><span data-stu-id="579df-129">Because you manage this network, you have direct control over the performance of the network, and we recommend that you complete network assessments to validate performance both within sites in your network and from your network to the Microsoft 365 or Office 365 network.</span></span>

<span data-ttu-id="579df-130">**Internet。**</span><span class="sxs-lookup"><span data-stu-id="579df-130">**Internet**.</span></span> <span data-ttu-id="579df-131">这是属于整个网络的一部分的网络段，由从客户网络外部连接到 Microsoft 365 或 Office 365 的用户使用。</span><span class="sxs-lookup"><span data-stu-id="579df-131">This is the network segment that is part of your overall network that will be used by users who are connecting to Microsoft 365 or Office 365 from outside of the customer network.</span></span> <span data-ttu-id="579df-132">它还会由客户网络发来的流量用于Microsoft 365 Office 365。</span><span class="sxs-lookup"><span data-stu-id="579df-132">It is also used by some traffic from the customer network to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="579df-133">**访问的或来宾专用网络**。</span><span class="sxs-lookup"><span data-stu-id="579df-133">**Visited or guest private network**.</span></span> <span data-ttu-id="579df-134">这是用户及其来宾可能访问 (（例如，家庭专用网络或不部署 Teams 的企业专用网络）（用户及其与 Teams 服务交互的客户可能驻留在) ）外部（而不是公共 Internet）中的网络段。</span><span class="sxs-lookup"><span data-stu-id="579df-134">This is the network segment outside your customer network, but not in the public Internet, that your users and their guests may visit (for example, a home private network or an enterprise private network, that does not deploy Teams, where your users and their customers that interact with Teams services may reside).</span></span>

> [!NOTE]
> <span data-ttu-id="579df-135">与 Microsoft 365 或 Office 365 的连接也适用于这些网络。</span><span class="sxs-lookup"><span data-stu-id="579df-135">Connectivity to Microsoft 365 or Office 365 is also applicable to these networks.</span></span>

<span data-ttu-id="579df-136">**Microsoft 365 或 Office 365。**</span><span class="sxs-lookup"><span data-stu-id="579df-136">**Microsoft 365 or Office 365**.</span></span> <span data-ttu-id="579df-137">这是支持服务或Microsoft 365 Office 365网段。</span><span class="sxs-lookup"><span data-stu-id="579df-137">This is the network segment that supports Microsoft 365 or Office 365 services.</span></span> <span data-ttu-id="579df-138">它分布在世界各地，在大多数位置具有靠近客户网络的边缘。</span><span class="sxs-lookup"><span data-stu-id="579df-138">It is distributed worldwide with edges in proximity to the customer network in most locations.</span></span> <span data-ttu-id="579df-139">函数包括传输中继、会议服务器和媒体处理器。</span><span class="sxs-lookup"><span data-stu-id="579df-139">Functions include Transport Relay, conferencing server, and Media Processor.</span></span>

<span data-ttu-id="579df-140">**Express Route (可选) 。**</span><span class="sxs-lookup"><span data-stu-id="579df-140">**Express Route (optional)**.</span></span> <span data-ttu-id="579df-141">这是整个网络的一部分网络段，可让你与虚拟网络或Microsoft 365专用Office 365连接。</span><span class="sxs-lookup"><span data-stu-id="579df-141">This is the network segment that is part of your overall network that will give you a dedicated, private connection to the Microsoft 365 or Office 365 network.</span></span>

### <a name="types-of-traffic"></a><span data-ttu-id="579df-142">流量类型</span><span class="sxs-lookup"><span data-stu-id="579df-142">Types of traffic</span></span>

<span data-ttu-id="579df-143">**实时媒体**。</span><span class="sxs-lookup"><span data-stu-id="579df-143">**Real-time media**.</span></span> <span data-ttu-id="579df-144">支持音频、视频和屏幕共享工作负荷 (RTP) 实时传输协议内封装的数据。</span><span class="sxs-lookup"><span data-stu-id="579df-144">Data encapsulated within Real-time Transport Protocol (RTP) that supports audio, video, and screen sharing workloads.</span></span> <span data-ttu-id="579df-145">通常，媒体流量对延迟高度敏感，因此，你可能希望此流量采用尽可能最直接的路径，并使用 UDP 与 TCP 作为传输层协议，这是从质量角度对交互式实时媒体的最佳传输。</span><span class="sxs-lookup"><span data-stu-id="579df-145">In general, media traffic is highly latency sensitive, so you would want this traffic to take the most direct path possible, and to use UDP versus TCP as the transport layer protocol, which is the best transport for interactive real-time media from a quality perspective.</span></span> <span data-ttu-id="579df-146"> (请注意，作为最后手段，媒体可以使用 TCP/IP，也可在 HTTP 协议内进行隧道传输，但由于质量影响不佳，不建议这样做。) RTP 流使用 SRTP 进行保护，其中只加密有效负载。</span><span class="sxs-lookup"><span data-stu-id="579df-146">(Note that as a last resort, media can use TCP/IP and also be tunneled within the HTTP protocol, but it is not recommended due to bad quality implications.) RTP flow is secured using SRTP, in which only the payload is encrypted.</span></span>

<span data-ttu-id="579df-147">**发出信号**。</span><span class="sxs-lookup"><span data-stu-id="579df-147">**Signaling**.</span></span> <span data-ttu-id="579df-148">客户端与服务器或其他客户端之间的通信链接，用于控制活动 (例如，当发起呼叫时) 发送即时消息。</span><span class="sxs-lookup"><span data-stu-id="579df-148">The communication link between the client and server, or other clients that are used to control activities (for example, when a call is initiated), and deliver instant messages.</span></span> <span data-ttu-id="579df-149">大多数信令流量使用基于 HTTPS 的 REST 接口，但在某些情况下 (例如，Microsoft 365 或 Office 365 与会话边界控制器之间的连接) 它使用 SIP 协议。</span><span class="sxs-lookup"><span data-stu-id="579df-149">Most signaling traffic uses the HTTPS-based REST interfaces, though in some scenarios (for example, connection between Microsoft 365 or Office 365 and a Session Border Controller) it uses SIP protocol.</span></span> <span data-ttu-id="579df-150">必须了解，此流量对延迟不太敏感，但如果终结点之间的延迟超过几秒，则可能会导致服务中断或调用超时。</span><span class="sxs-lookup"><span data-stu-id="579df-150">It's important to understand that this traffic is much less sensitive to latency but may cause service outages or call timeouts if latency between the endpoints exceeds several seconds.</span></span>

### <a name="connectivity-to-microsoft-365-or-office-365"></a><span data-ttu-id="579df-151">连接到 Microsoft 365 或 Office 365</span><span class="sxs-lookup"><span data-stu-id="579df-151">Connectivity to Microsoft 365 or Office 365</span></span>

<span data-ttu-id="579df-152">Teams[需要连接到 Internet。](/office365/enterprise/assessing-network-connectivity)</span><span class="sxs-lookup"><span data-stu-id="579df-152">Teams requires [connectivity to the Internet](/office365/enterprise/assessing-network-connectivity).</span></span> <span data-ttu-id="579df-153">Teams URL 和 IP 地址范围中列出了Office 365 [URL 和 IP 地址范围](/office365/enterprise/urls-and-ip-address-ranges)。</span><span class="sxs-lookup"><span data-stu-id="579df-153">Teams endpoint URLs and IP address ranges are listed in [Office 365 URLs and IP address ranges](/office365/enterprise/urls-and-ip-address-ranges).</span></span> <span data-ttu-id="579df-154"> (请注意，需要打开到 TCP 端口 80 和 443 以及到 UDP 端口 3478 到 3481 的连接。) 此外，Teams 依赖于 Skype for Business Online，这还必须连接到 Internet。</span><span class="sxs-lookup"><span data-stu-id="579df-154">(Note that open connectivity to TCP ports 80 and 443, and to UDP ports 3478 through 3481, is required.) Furthermore, Teams has a dependency on Skype for Business Online, which must also be connected to the Internet.</span></span>

<span data-ttu-id="579df-155">Teams媒体流连接是使用标准 IETF 交互式连接建立 (ICE) 过程实现的。</span><span class="sxs-lookup"><span data-stu-id="579df-155">Teams media flows connectivity is implemented using standard IETF Interactive Connectivity Establishment (ICE) procedures.</span></span>

### <a name="interoperability-restrictions"></a><span data-ttu-id="579df-156">互操作性限制</span><span class="sxs-lookup"><span data-stu-id="579df-156">Interoperability restrictions</span></span>

<span data-ttu-id="579df-157">**第三方媒体中继**。</span><span class="sxs-lookup"><span data-stu-id="579df-157">**Third-party media relays**.</span></span> <span data-ttu-id="579df-158">一Teams媒体 (，即其中一个媒体终结点Teams) 只能遍历Teams或Skype for Business媒体中继。</span><span class="sxs-lookup"><span data-stu-id="579df-158">A Teams media flow (that is, where one of the media endpoints is Teams) may traverse only Teams or Skype for Business native media relays.</span></span> <span data-ttu-id="579df-159">不支持第三方媒体中继的互操作性。</span><span class="sxs-lookup"><span data-stu-id="579df-159">Interoperability with a third-party media relay is not supported.</span></span> <span data-ttu-id="579df-160"> (PSTN 边界上的第三方 SBC 必须终止使用 SRTP 保护的 RTP/RTCP 流，而不是中继到下一跃点.) </span><span class="sxs-lookup"><span data-stu-id="579df-160">(Note that a third-party SBC on the boundary with PSTN must terminate RTP/RTCP stream, secured using SRTP, and not relay it to the next hop.)</span></span>

<span data-ttu-id="579df-161">**第三方 SIP 代理服务器**。</span><span class="sxs-lookup"><span data-stu-id="579df-161">**Third-party SIP proxy servers**.</span></span> <span data-ttu-id="579df-162">使用Teams SBC 和/或网关发送 SIP 信号的网关可能会遍历Teams或Skype for Business SIP 代理。</span><span class="sxs-lookup"><span data-stu-id="579df-162">A Teams signaling SIP dialog with a third-party SBC and/or gateway may traverse Teams or Skype for Business native SIP proxies.</span></span> <span data-ttu-id="579df-163">不支持第三方 SIP 代理的互操作性。</span><span class="sxs-lookup"><span data-stu-id="579df-163">Interoperability with a third-party SIP proxy is not supported.</span></span>

<span data-ttu-id="579df-164">**第三方 B2BUA (或 SBC) 。**</span><span class="sxs-lookup"><span data-stu-id="579df-164">**Third-party B2BUA (or SBC)**.</span></span> <span data-ttu-id="579df-165">与Teams PSTN 之间的媒体流由第三方 SBC 终止。</span><span class="sxs-lookup"><span data-stu-id="579df-165">A Teams media flow to and from the PSTN is terminated by a third-party SBC.</span></span> <span data-ttu-id="579df-166">但是，不支持在 Teams 网络 (中与第三方 SBC 的互操作性Teams或 Skype for Business 终结点) 。</span><span class="sxs-lookup"><span data-stu-id="579df-166">However, interoperability with a third-party SBC within the Teams network (where a third-party SBC mediates two Teams or Skype for Business endpoints) is not supported.</span></span>

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a><span data-ttu-id="579df-167">不建议使用 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="579df-167">Technologies that are not recommended with Microsoft Teams</span></span>

<span data-ttu-id="579df-168">**VPN 网络**。</span><span class="sxs-lookup"><span data-stu-id="579df-168">**VPN network**.</span></span> <span data-ttu-id="579df-169">不建议将媒体流量 (流 2') 。</span><span class="sxs-lookup"><span data-stu-id="579df-169">It is not recommended for media traffic (or flow 2').</span></span> <span data-ttu-id="579df-170">VPN 客户端应该使用拆分隧道，Teams外部非 VPN 用户一样路由媒体流量，如启用 Lync 媒体绕过 VPN 隧道[中指定](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210)。</span><span class="sxs-lookup"><span data-stu-id="579df-170">The VPN client should use split tunneling and route Teams media traffic like any external non-VPN user, as specified in [Enabling Lync media to bypass a VPN tunnel](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210).</span></span>

> [!NOTE]
> <span data-ttu-id="579df-171">尽管游戏指示 Lync，但它也适用于Teams Lync。</span><span class="sxs-lookup"><span data-stu-id="579df-171">Although the title indicates Lync, it is applicable to Teams as well.</span></span>

<span data-ttu-id="579df-172">**数据包形状。**</span><span class="sxs-lookup"><span data-stu-id="579df-172">**Packet shapers**.</span></span> <span data-ttu-id="579df-173">对于媒体流量，不建议使用任何类型的数据包捕获器、数据包检查或数据包Teams设备，并且可能会显著降低质量。</span><span class="sxs-lookup"><span data-stu-id="579df-173">Any kind of packet snipper, packet inspection, or packet shaper devices are not recommended for Teams media traffic and may degrade quality significantly.</span></span>

### <a name="principles"></a><span data-ttu-id="579df-174">原则</span><span class="sxs-lookup"><span data-stu-id="579df-174">Principles</span></span>

<span data-ttu-id="579df-175">有四条一般性原则可帮助你了解以下Microsoft Teams：</span><span class="sxs-lookup"><span data-stu-id="579df-175">There are four general principles that help you understand call flows for Microsoft Teams:</span></span>

- <span data-ttu-id="579df-176">Microsoft Teams会议由第一Microsoft 365 Office 365参与者加入的同一区域中的用户或参与者主持。</span><span class="sxs-lookup"><span data-stu-id="579df-176">A Microsoft Teams conference is hosted by Microsoft 365 or Office 365 in the same region where the first participant joined.</span></span> <span data-ttu-id="579df-177"> (请注意，如果某些拓扑中存在此规则例外，本文档中将介绍这些异常，并按相应的调用流.) </span><span class="sxs-lookup"><span data-stu-id="579df-177">(Note that if there are exceptions to this rule in some topologies, they will be described in this document and illustrated by an appropriate call flow.)</span></span>

- <span data-ttu-id="579df-178">Teams或Microsoft 365媒体Office 365基于媒体处理需求使用，而不是基于呼叫类型。</span><span class="sxs-lookup"><span data-stu-id="579df-178">A Teams media endpoint in Microsoft 365 or Office 365 is used based on media processing needs and not based on call type.</span></span> <span data-ttu-id="579df-179"> (例如，点到点呼叫可以使用云中的媒体终结点处理媒体听录或录制，而包含两个参与者的会议可能不会使用云中任何媒体终结点。) 但是，大多数会议将使用媒体终结点进行混合和路由，而该终结点是在托管会议时分配的。</span><span class="sxs-lookup"><span data-stu-id="579df-179">(For example, a point-to-point call may use a media endpoint in the cloud to process media for transcription or recording, while a conference with two participants may not use any media endpoint in the cloud.) However, most conferences will use a media endpoint for mixing and routing purposes, allocated where the conference is hosted.</span></span> <span data-ttu-id="579df-180">由于客户网络防火墙限制，从客户端发送到媒体终结点的媒体流量可以直接路由或使用 Microsoft 365 或 Office 365 中的传输中继。</span><span class="sxs-lookup"><span data-stu-id="579df-180">The media traffic sent from a client to the media endpoint may be routed directly or use a Transport Relay in Microsoft 365 or Office 365 if required due to customer network firewall restrictions.</span></span>

- <span data-ttu-id="579df-181">点对点呼叫的媒体流量采用最直接的可用路由，假设该调用不强制云中的媒体终结点 (请参阅前面的原则) 。</span><span class="sxs-lookup"><span data-stu-id="579df-181">Media traffic for peer-to-peer calls takes the most direct route that is available, assuming that the call doesn't mandate a media endpoint in the cloud (see previous principle).</span></span> <span data-ttu-id="579df-182">首选路由将直接路由到远程对等 (客户端) ，但如果该路由不可用，则一个或多个传输中继将中继流量。</span><span class="sxs-lookup"><span data-stu-id="579df-182">The preferred route is direct to the remote peer (client), but if that route isn't available, then one or more Transport Relays will relay traffic.</span></span> <span data-ttu-id="579df-183">建议媒体流量不要转置数据包形状器、VPN 服务器等服务器，因为这会影响媒体质量。</span><span class="sxs-lookup"><span data-stu-id="579df-183">It is recommended that media traffic shall not transverse servers such as packet shapers, VPN servers, and so on, since this will impact the media quality.</span></span>

- <span data-ttu-id="579df-184">信令流量始终会转到离用户最近的服务器。</span><span class="sxs-lookup"><span data-stu-id="579df-184">Signaling traffic always goes to the closest server to the user.</span></span>

<span data-ttu-id="579df-185">若要了解有关所选媒体路径的详细信息，请参阅了解媒体流中的Microsoft Teams [- BRK4016。](https://www.youtube.com/watch?v=1tmHMIlAQdo)</span><span class="sxs-lookup"><span data-stu-id="579df-185">To learn more about the details on the media path that is chosen, see [Understanding Media Flows in Microsoft Teams - BRK4016](https://www.youtube.com/watch?v=1tmHMIlAQdo).</span></span>

## <a name="call-flows-in-various-topologies"></a><span data-ttu-id="579df-186">各种拓扑中的调用流</span><span class="sxs-lookup"><span data-stu-id="579df-186">Call flows in various topologies</span></span>

### <a name="teams-topology"></a><span data-ttu-id="579df-187">Teams拓扑</span><span class="sxs-lookup"><span data-stu-id="579df-187">Teams topology</span></span>

<span data-ttu-id="579df-188">此拓扑由利用云Teams服务的客户使用，无需任何本地部署，例如Skype for Business Server或电话系统路由。</span><span class="sxs-lookup"><span data-stu-id="579df-188">This topology is used by customers that leverage Teams services from the cloud without any on-premises deployment, such as Skype for Business Server or Phone System Direct Routing.</span></span> <span data-ttu-id="579df-189">此外，无需 Azure express Route Microsoft 365 Office 365 Internet 即可完成用于连接或路由的接口。</span><span class="sxs-lookup"><span data-stu-id="579df-189">In addition, the interface to Microsoft 365 or Office 365 is done over the Internet without Azure Express Route.</span></span>

<span data-ttu-id="579df-190">[![Microsoft Teams在线呼叫流图 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span><span class="sxs-lookup"><span data-stu-id="579df-190">[![Microsoft Teams Online Call Flows Figure 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)</span></span>

<span data-ttu-id="579df-191">*图 1 - Teams拓扑*</span><span class="sxs-lookup"><span data-stu-id="579df-191">*Figure 1 - Teams topology*</span></span>

<span data-ttu-id="579df-192">请注意：</span><span class="sxs-lookup"><span data-stu-id="579df-192">Note that:</span></span>

- <span data-ttu-id="579df-193">上图中箭头的方向反映影响企业外围连接的通信的启动方向。</span><span class="sxs-lookup"><span data-stu-id="579df-193">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="579df-194">对于媒体的 UDP，第一 (数据包) 反向流动，但可能会阻止这些数据包，直到其他方向的数据包流动。</span><span class="sxs-lookup"><span data-stu-id="579df-194">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>
- <span data-ttu-id="579df-195">Teams与 Skype for Business Online 并排部署，因此客户端显示为"Teams/SFB 用户"。</span><span class="sxs-lookup"><span data-stu-id="579df-195">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user."</span></span>

<span data-ttu-id="579df-196">可以在本文的稍后部分找到有关以下可选拓扑详细信息：</span><span class="sxs-lookup"><span data-stu-id="579df-196">You can find more information on the following optional topologies later in the article:</span></span>

- <span data-ttu-id="579df-197">Skype for Business混合拓扑 中介绍了Teams **部署**。</span><span class="sxs-lookup"><span data-stu-id="579df-197">Skype for Business on-premises deployment is described in **Teams hybrid topology**.</span></span>
- <span data-ttu-id="579df-198">电话系统PSTN 连接 (直接路由) 使用直接Teams **拓扑 中所述**。</span><span class="sxs-lookup"><span data-stu-id="579df-198">Phone System Direct Routing (for PSTN connectivity) is described in **Teams with Direct Routing topology**.</span></span>
- <span data-ttu-id="579df-199">Express Route 在快速Teams **中进行了介绍**。</span><span class="sxs-lookup"><span data-stu-id="579df-199">Express Route is described in **Teams with Express Route optimization**.</span></span>

<span data-ttu-id="579df-200">**Flow说明**：</span><span class="sxs-lookup"><span data-stu-id="579df-200">**Flow descriptions**:</span></span>

- <span data-ttu-id="579df-201">**Flow 2** – 表示客户网络上用户启动的到 Internet 的流，作为用户体验的一Teams部分。</span><span class="sxs-lookup"><span data-stu-id="579df-201">**Flow 2** – Represents a flow initiated by a user on the customer network to the Internet as a part of the user's Teams experience.</span></span> <span data-ttu-id="579df-202">这些流的示例包括 DNS 和对等媒体。</span><span class="sxs-lookup"><span data-stu-id="579df-202">Examples of these flows are DNS and peer-to-peer media.</span></span>
- <span data-ttu-id="579df-203">**Flow 2'** – 表示由远程移动用户启动Teams，使用 VPN 到客户网络的流。</span><span class="sxs-lookup"><span data-stu-id="579df-203">**Flow 2'** – Represents a flow initiated by a remote mobile Teams user, with VPN to the customer network.</span></span>
- <span data-ttu-id="579df-204">**Flow 3** – 表示由远程移动启动Teams用户Microsoft 365终结点Office 365/Teams流。</span><span class="sxs-lookup"><span data-stu-id="579df-204">**Flow 3** – Represents a flow initiated by a remote mobile Teams user to Microsoft 365 or Office 365/Teams endpoints.</span></span>
- <span data-ttu-id="579df-205">**Flow 4** – 表示客户网络上用户启动的流，Microsoft 365或Office 365/Teams终结点。</span><span class="sxs-lookup"><span data-stu-id="579df-205">**Flow 4** – Represents a flow initiated by a user on the customer network to Microsoft 365 or Office 365/Teams endpoints.</span></span>
- <span data-ttu-id="579df-206">**Flow 5** – 表示客户网络中 Teams 用户与另一个Teams或Skype for Business之间的对等媒体流。</span><span class="sxs-lookup"><span data-stu-id="579df-206">**Flow 5** – Represents a peer-to-peer media flow between a Teams user and another Teams or Skype for Business user within the customer network.</span></span>
- <span data-ttu-id="579df-207">**Flow 6** – 表示远程移动 Teams 用户与通过 Internet 的另一个远程移动Teams或 Skype for Business 用户之间的对等媒体流。</span><span class="sxs-lookup"><span data-stu-id="579df-207">**Flow 6** – Represents a peer-to-peer media flow between a remote mobile Teams user and another remote mobile Teams or Skype for Business user over the Internet.</span></span>

#### <a name="use-case-one-to-one"></a><span data-ttu-id="579df-208">用例：一对一</span><span class="sxs-lookup"><span data-stu-id="579df-208">Use case: One-to-one</span></span>

<span data-ttu-id="579df-209">一对一调用使用通用模型，调用方将获取一组候选项，其中包括 IP 地址/端口，包括客户端的本地、中继和反身 (公共 IP 地址，如中继候选) 所看到的。</span><span class="sxs-lookup"><span data-stu-id="579df-209">One-to-one calls use a common model in which the caller will obtain a set of candidates consisting of IP addresses/ports, including local, relay, and reflexive (public IP address of client as seen by the relay) candidates.</span></span> <span data-ttu-id="579df-210">调用方将这些候选者发送到被调用方;被调用方还会获取一组类似的候选项，并将其发送给调用方。</span><span class="sxs-lookup"><span data-stu-id="579df-210">The caller sends these candidates to the called party; the called party also obtains a similar set of candidates and sends them to the caller.</span></span> <span data-ttu-id="579df-211">STUN 连接性检查消息用于查找哪些调用方/被呼叫方媒体路径工作，并且选择了最佳工作路径。</span><span class="sxs-lookup"><span data-stu-id="579df-211">STUN connectivity check messages are used to find which caller/called party media paths work, and the best working path is selected.</span></span> <span data-ttu-id="579df-212">媒体 (，即使用 SRTP 保护的 RTP/RTCP 数据包) 所选候选对发送。</span><span class="sxs-lookup"><span data-stu-id="579df-212">Media (that is, RTP/RTCP packets secured using SRTP) are then sent using the selected candidate pair.</span></span> <span data-ttu-id="579df-213">传输中继部署为 Microsoft 365 和 Office 365。</span><span class="sxs-lookup"><span data-stu-id="579df-213">The Transport relay is deployed as part of Microsoft 365 and Office 365.</span></span>

<span data-ttu-id="579df-214">如果本地 IP 地址/候选端口或反身候选项具有连接性，则客户端之间的直接路径 (或者使用 NAT) 媒体。</span><span class="sxs-lookup"><span data-stu-id="579df-214">If the local IP address/port candidates or the reflexive candidates have connectivity, then the direct path between the clients (or using a NAT) will be selected for media.</span></span> <span data-ttu-id="579df-215">如果客户端都位于客户网络上，应选择直接路径。</span><span class="sxs-lookup"><span data-stu-id="579df-215">If the clients are both on the customer network, then the direct path should be selected.</span></span> <span data-ttu-id="579df-216">这需要在客户网络中建立直接 UDP 连接。</span><span class="sxs-lookup"><span data-stu-id="579df-216">This requires direct UDP connectivity within the customer network.</span></span> <span data-ttu-id="579df-217">如果客户端都是云用户，则根据 NAT/防火墙，媒体可能会使用直接连接。</span><span class="sxs-lookup"><span data-stu-id="579df-217">If the clients are both nomadic cloud users, then depending on the NAT/firewall, media may use direct connectivity.</span></span>

<span data-ttu-id="579df-218">如果一个客户端位于客户网络内部，一个客户端是外部客户端 (例如移动云用户) ，则本地候选者或反身候选者之间的直接连接不太可能正常。</span><span class="sxs-lookup"><span data-stu-id="579df-218">If one client is internal on the customer network and one client is external (for example, a mobile cloud user), then it is unlikely that direct connectivity between the local or reflexive candidates is working.</span></span> <span data-ttu-id="579df-219">在这种情况下，一个选项是使用来自任一客户端的一个传输中继候选项 (例如，内部客户端从 Microsoft 365 或 Office 365 中的传输中继获取中继候选项;外部客户端需要能够将 STUN/RTP/RTCP 数据包发送到传输中继) 。</span><span class="sxs-lookup"><span data-stu-id="579df-219">In this case, an option is to use one of the Transport Relay candidates from either client (for example, the internal client obtained a relay candidate from the Transport relay in Microsoft 365 or Office 365; the external client needs to be able to send STUN/RTP/RTCP packets to the transport relay).</span></span> <span data-ttu-id="579df-220">另一个选项是内部客户端发送到移动云客户端获取的中继候选项。</span><span class="sxs-lookup"><span data-stu-id="579df-220">Another option is the internal client sends to the relay candidate obtained by the mobile cloud client.</span></span> <span data-ttu-id="579df-221">请注意，尽管强烈建议建立媒体的 UDP 连接，但支持 TCP。</span><span class="sxs-lookup"><span data-stu-id="579df-221">Note that, although UDP connectivity for media is highly recommended, TCP is supported.</span></span>

<span data-ttu-id="579df-222">**高级步骤**：</span><span class="sxs-lookup"><span data-stu-id="579df-222">**High-level steps**:</span></span>

1. <span data-ttu-id="579df-223">Teams用户 A 使用流 2 (DNS) 解析 URL 域名。</span><span class="sxs-lookup"><span data-stu-id="579df-223">Teams User A resolves URL domain name (DNS) using flow 2.</span></span>
1. <span data-ttu-id="579df-224">Teams用户 A 使用流 4 在Teams中继上分配媒体中继端口。</span><span class="sxs-lookup"><span data-stu-id="579df-224">Teams User A allocates a media Relay port on Teams Transport Relay using flow 4.</span></span>
1. <span data-ttu-id="579df-225">Teams用户 A 使用流 4 向 ICE 候选者发送"邀请"Microsoft 365或Office 365。</span><span class="sxs-lookup"><span data-stu-id="579df-225">Teams User A sends "invite" with ICE candidates using flow 4 to Microsoft 365 or Office 365.</span></span>
1. <span data-ttu-id="579df-226">Microsoft 365或Office 365使用流 4 Teams向用户 B 发送通知。</span><span class="sxs-lookup"><span data-stu-id="579df-226">Microsoft 365 or Office 365 sends notification to Teams User B using flow 4.</span></span>
1. <span data-ttu-id="579df-227">Teams用户 B 使用流 4 在Teams中继上分配媒体中继端口。</span><span class="sxs-lookup"><span data-stu-id="579df-227">Teams User B allocates a media Relay port on Teams Transport Relay using flow 4.</span></span>
1. <span data-ttu-id="579df-228">Teams用户 B 使用流 4 向 ICE 候选项发送"答案"，流 4 使用 Teams 4 转发Flow A。</span><span class="sxs-lookup"><span data-stu-id="579df-228">Teams User B sends "answer" with ICE candidates using flow 4, which is forwarded back to Teams User A using Flow 4.</span></span>
1. <span data-ttu-id="579df-229">Teams用户 A Teams用户 B 调用 ICE 连接测试，并且选择了最佳可用媒体路径 (请参阅下图了解各种用例) 。</span><span class="sxs-lookup"><span data-stu-id="579df-229">Teams User A and Teams User B invoke ICE connectivity tests and the best available media path is selected (see diagrams below for various use cases).</span></span>
1. <span data-ttu-id="579df-230">Teams用户使用流 4 Microsoft 365或Office 365遥测数据。</span><span class="sxs-lookup"><span data-stu-id="579df-230">Teams Users send telemetry to Microsoft 365 or Office 365 using flow 4.</span></span>

<span data-ttu-id="579df-231">**在客户网络中：**</span><span class="sxs-lookup"><span data-stu-id="579df-231">**Within customer network:**</span></span>

<span data-ttu-id="579df-232">[![Microsoft Teams联机呼叫流图 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span><span class="sxs-lookup"><span data-stu-id="579df-232">[![Microsoft Teams Online Call Flows Figure 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)</span></span>

<span data-ttu-id="579df-233">*图 2 - 在客户网络中*</span><span class="sxs-lookup"><span data-stu-id="579df-233">*Figure 2 - Within customer network*</span></span>

<span data-ttu-id="579df-234">在步骤 7 中，选择"对等媒体流 5"。</span><span class="sxs-lookup"><span data-stu-id="579df-234">In step 7, peer-to-peer media flow 5 is selected.</span></span>

<span data-ttu-id="579df-235">媒体是双向的。</span><span class="sxs-lookup"><span data-stu-id="579df-235">Media is bidirectional.</span></span> <span data-ttu-id="579df-236">流 5 的方向指示一端从连接角度启动通信，与本文档中所有流一致。</span><span class="sxs-lookup"><span data-stu-id="579df-236">The direction of flow 5 indicates that one side initiates the communication from a connectivity perspective, consistent with all the flows in this document.</span></span> <span data-ttu-id="579df-237">在这种情况下，使用哪个方向并不重要，因为两个终结点都位于客户网络中。</span><span class="sxs-lookup"><span data-stu-id="579df-237">In this case, it doesn't matter which direction is used because both endpoints are within the customer network.</span></span>

<span data-ttu-id="579df-238">**客户网络与外部用户 (传输中继Teams媒体) ：**</span><span class="sxs-lookup"><span data-stu-id="579df-238">**Customer network to external user (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="579df-239">[![Microsoft Teams在线呼叫流图 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span><span class="sxs-lookup"><span data-stu-id="579df-239">[![Microsoft Teams Online Call Flows Figure 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)</span></span>

<span data-ttu-id="579df-240">*图 3 - 客户网络到外部用户 (中继中继Teams媒体)*</span><span class="sxs-lookup"><span data-stu-id="579df-240">*Figure 3 - Customer network to external user (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="579df-241">在步骤 7 中，选择从客户网络到 Microsoft 365 或 Office 365 的流 4，以及流 3（从远程移动 Teams 用户到 Microsoft 365 或 Office 365）。</span><span class="sxs-lookup"><span data-stu-id="579df-241">In step 7, flow 4, from customer network to Microsoft 365 or Office 365, and flow 3, from remote mobile Teams user to Microsoft 365 or Office 365, are selected.</span></span> <span data-ttu-id="579df-242">这些流由 Teams 或 Microsoft 365 内的传输中继Office 365。</span><span class="sxs-lookup"><span data-stu-id="579df-242">These flows are relayed by Teams Transport Relay within Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="579df-243">媒体是双向的，其中方向指示哪个端从连接角度启动通信。</span><span class="sxs-lookup"><span data-stu-id="579df-243">Media is bidirectional, where direction indicates which side initiates the communication from a connectivity perspective.</span></span> <span data-ttu-id="579df-244">在这种情况下，这些流用于信令和媒体，使用不同的传输协议和地址。</span><span class="sxs-lookup"><span data-stu-id="579df-244">In this case, these flows are used for signaling and media, using different transport protocols and addresses.</span></span>

<span data-ttu-id="579df-245">**客户网络与外部用户 (媒体) ：**</span><span class="sxs-lookup"><span data-stu-id="579df-245">**Customer network to external user (direct media):**</span></span>

<span data-ttu-id="579df-246">[![Microsoft Teams联机呼叫流图 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span><span class="sxs-lookup"><span data-stu-id="579df-246">[![Microsoft Teams Online Call Flows Figure 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)</span></span>

<span data-ttu-id="579df-247">*图 4 - 客户网络与外部用户 (媒体)*</span><span class="sxs-lookup"><span data-stu-id="579df-247">*Figure 4 - Customer network to external user (direct media)*</span></span>

<span data-ttu-id="579df-248">在步骤 7 中，选择"流 2"，即从客户网络 (客户端对等) Internet。</span><span class="sxs-lookup"><span data-stu-id="579df-248">In step 7, flow 2, from customer network to the Internet (client's peer), is selected.</span></span>

- <span data-ttu-id="579df-249">不通过远程移动用户 (直接媒体Microsoft 365 Office 365) 可选。</span><span class="sxs-lookup"><span data-stu-id="579df-249">Direct media with remote mobile user (not relayed through Microsoft 365 or Office 365) is optional.</span></span> <span data-ttu-id="579df-250">换言之，客户可能会阻止此路径，以强制媒体路径通过 Microsoft 365 或 Office 365 中的传输中继。</span><span class="sxs-lookup"><span data-stu-id="579df-250">In other words, customer may block this path to enforce a media path through Transport Relay in Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="579df-251">媒体是双向的。</span><span class="sxs-lookup"><span data-stu-id="579df-251">Media is bidirectional.</span></span> <span data-ttu-id="579df-252">流 2 到远程移动用户的方向指示一端从连接角度启动通信。</span><span class="sxs-lookup"><span data-stu-id="579df-252">The direction of flow 2 to remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

<span data-ttu-id="579df-253">**VPN 用户到内部用户 (中继中继Teams媒体)**</span><span class="sxs-lookup"><span data-stu-id="579df-253">**VPN user to internal user (media relayed by Teams Transport Relay)**</span></span>

<span data-ttu-id="579df-254">[![Microsoft Teams在线呼叫流图 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span><span class="sxs-lookup"><span data-stu-id="579df-254">[![Microsoft Teams Online Call Flows Figure 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)</span></span>

<span data-ttu-id="579df-255">*图 5 - VPN 用户到内部用户 (中继中继Teams媒体)*</span><span class="sxs-lookup"><span data-stu-id="579df-255">*Figure 5 - VPN user to internal user (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="579df-256">VPN 与客户网络之间的信号发送使用的是流 2'。</span><span class="sxs-lookup"><span data-stu-id="579df-256">Signaling between the VPN to the customer network is using flow 2'.</span></span> <span data-ttu-id="579df-257">客户网络与客户或Microsoft 365之间的Office 365使用流 4。</span><span class="sxs-lookup"><span data-stu-id="579df-257">Signaling between the customer network and Microsoft 365 or Office 365 is using flow 4.</span></span> <span data-ttu-id="579df-258">但是，媒体绕过 VPN，使用流 3 和流 4 通过Teams或媒体中继Microsoft 365 Office 365。</span><span class="sxs-lookup"><span data-stu-id="579df-258">However, media bypasses the VPN and is routed using flows 3 and 4 through Teams media relay in Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="579df-259">**VPN 用户到内部用户 (媒体)**</span><span class="sxs-lookup"><span data-stu-id="579df-259">**VPN user to internal user (direct media)**</span></span>

<span data-ttu-id="579df-260">[![Microsoft Teams在线呼叫流图 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span><span class="sxs-lookup"><span data-stu-id="579df-260">[![Microsoft Teams Online Call Flows Figure 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)</span></span>

<span data-ttu-id="579df-261">*图 6 - VPN 用户到内部用户 (媒体)*</span><span class="sxs-lookup"><span data-stu-id="579df-261">*Figure 6 - VPN user to internal user (direct media)*</span></span>

<span data-ttu-id="579df-262">VPN 与客户网络之间的信号发送使用的是流 2'。</span><span class="sxs-lookup"><span data-stu-id="579df-262">Signaling between the VPN to the customer network is using flow 2'.</span></span> <span data-ttu-id="579df-263">客户网络与客户或Microsoft 365之间的Office 365使用流 4。</span><span class="sxs-lookup"><span data-stu-id="579df-263">Signaling between the customer network and Microsoft 365 or Office 365 is using flow 4.</span></span> <span data-ttu-id="579df-264">但是，媒体绕过 VPN，使用流 2 从客户网络路由到 Internet。</span><span class="sxs-lookup"><span data-stu-id="579df-264">However, media bypasses the VPN and is routed using flow 2 from the customer network to the Internet.</span></span>

<span data-ttu-id="579df-265">媒体是双向的。</span><span class="sxs-lookup"><span data-stu-id="579df-265">Media is bidirectional.</span></span> <span data-ttu-id="579df-266">流 2 到远程移动用户的方向指示一端从连接角度启动通信。</span><span class="sxs-lookup"><span data-stu-id="579df-266">The direction of flow 2 to the remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

<span data-ttu-id="579df-267">**VPN 用户到外部用户 (媒体)**</span><span class="sxs-lookup"><span data-stu-id="579df-267">**VPN user to external user (direct media)**</span></span>

<span data-ttu-id="579df-268">[![Microsoft Teams调用流图 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span><span class="sxs-lookup"><span data-stu-id="579df-268">[![Microsoft Teams call flows Figure 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)</span></span>

<span data-ttu-id="579df-269">*图 7 - VPN 用户到外部用户 (媒体)*</span><span class="sxs-lookup"><span data-stu-id="579df-269">*Figure 7 - VPN user to external user (direct media)*</span></span>

<span data-ttu-id="579df-270">VPN 用户与客户网络之间的信号发送是使用流 2'，使用流 4 Microsoft 365或Office 365。</span><span class="sxs-lookup"><span data-stu-id="579df-270">Signaling between the VPN user to the customer network is using flow 2' and using flow 4 to Microsoft 365 or Office 365.</span></span> <span data-ttu-id="579df-271">但是，媒体绕过 VPN，并且使用流 6 进行路由。</span><span class="sxs-lookup"><span data-stu-id="579df-271">However, media bypasses VPN and is routed using flow 6.</span></span>

<span data-ttu-id="579df-272">媒体是双向的。</span><span class="sxs-lookup"><span data-stu-id="579df-272">Media is bidirectional.</span></span> <span data-ttu-id="579df-273">流 6 到远程移动用户的方向指示一端从连接角度启动通信。</span><span class="sxs-lookup"><span data-stu-id="579df-273">The direction of flow 6 to the remote mobile user indicates that one side initiates the communication from a connectivity perspective.</span></span>

#### <a name="use-case-teams-to-pstn-through-microsoft-365-or-office-365-trunk"></a><span data-ttu-id="579df-274">用例：Teams中继Microsoft 365 PSTN Office 365 PSTN</span><span class="sxs-lookup"><span data-stu-id="579df-274">Use Case: Teams to PSTN through Microsoft 365 or Office 365 Trunk</span></span>

<span data-ttu-id="579df-275">Microsoft 365 和 Office 365 具有一个电话系统，允许从 PSTN 公用电话交换网和 PSTN (接听) 。</span><span class="sxs-lookup"><span data-stu-id="579df-275">Microsoft 365 and Office 365 have a Phone System that allows placing and receiving calls from the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="579df-276">如果 PSTN 中继使用呼叫电话系统连接，则此用例没有特殊的连接要求。</span><span class="sxs-lookup"><span data-stu-id="579df-276">If the PSTN trunk is connected using the Phone System Calling Plan, then there are no special connectivity requirements for this use case.</span></span> <span data-ttu-id="579df-277"> (如果要将自己的本地 PSTN 中继连接到 Microsoft 365 或 Office 365，可以使用 电话系统 直接路由.) </span><span class="sxs-lookup"><span data-stu-id="579df-277">(If you want to connect your own on-premises PSTN trunk to Microsoft 365 or Office 365, you can use Phone System Direct Routing.)</span></span>

<span data-ttu-id="579df-278">[![Microsoft Teams在线呼叫流图 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span><span class="sxs-lookup"><span data-stu-id="579df-278">[![Microsoft Teams Online Call Flows Figure 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)</span></span>

<span data-ttu-id="579df-279">*图 8 - Teams通过中继Office 365 PSTN*</span><span class="sxs-lookup"><span data-stu-id="579df-279">*Figure 8 - Teams to PSTN through Office 365 Trunk*</span></span>

#### <a name="use-case-teams-meeting"></a><span data-ttu-id="579df-280">用例：Teams会议</span><span class="sxs-lookup"><span data-stu-id="579df-280">Use case: Teams meeting</span></span>

<span data-ttu-id="579df-281">VBSS (会议) 的音频/视频/屏幕共享是Microsoft 365 Office 365。</span><span class="sxs-lookup"><span data-stu-id="579df-281">The audio/video/screen sharing (VBSS) conferencing server is part of Microsoft 365 and Office 365.</span></span> <span data-ttu-id="579df-282">它拥有一个公共 IP 地址，该地址必须从客户网络访问，并且必须从 Nomadic 云客户端访问。</span><span class="sxs-lookup"><span data-stu-id="579df-282">It has a public IP address that must be reachable from the customer network and must be reachable from a Nomadic Cloud client.</span></span> <span data-ttu-id="579df-283">每个客户端/终结点都需要能够连接到会议服务器。</span><span class="sxs-lookup"><span data-stu-id="579df-283">Each client/endpoint needs to be able to connect to the conferencing server.</span></span>

<span data-ttu-id="579df-284">内部客户端将像一对一调用所述一样获取本地、反身和中继候选项。</span><span class="sxs-lookup"><span data-stu-id="579df-284">Internal clients will obtain local, reflexive, and relay candidates in the same manner as described for one-to-one calls.</span></span> <span data-ttu-id="579df-285">客户将在邀请中将这些候选者发送到会议服务器。</span><span class="sxs-lookup"><span data-stu-id="579df-285">The clients will send these candidates to the conferencing server in an invite.</span></span> <span data-ttu-id="579df-286">会议服务器不使用中继，因为它具有可公开访问的 IP 地址，因此它使用其本地 IP 地址候选项进行响应。</span><span class="sxs-lookup"><span data-stu-id="579df-286">The conferencing server does not use a relay since it has a publicly reachable IP address, so it responds with its local IP address candidate.</span></span> <span data-ttu-id="579df-287">客户端和会议服务器以一对一呼叫中所述的相同方式检查连接。</span><span class="sxs-lookup"><span data-stu-id="579df-287">The client and conferencing server will check connectivity in the same manner described for one-to-one calls.</span></span>

<span data-ttu-id="579df-288">请注意：</span><span class="sxs-lookup"><span data-stu-id="579df-288">Note that:</span></span>

- <span data-ttu-id="579df-289">Teams无法加入Skype for Business会议，Skype for Business无法加入Teams会议。</span><span class="sxs-lookup"><span data-stu-id="579df-289">Teams clients cannot join Skype for Business meetings, and Skype for Business clients cannot join Teams meetings.</span></span>

- <span data-ttu-id="579df-290">PSTN 用户可选择"拨入"或"拨出"，具体取决于会议的组织者 PSTN 呼叫和/或会议预配。</span><span class="sxs-lookup"><span data-stu-id="579df-290">A PSTN user optionally "Dials IN" or is "Dialed OUT", depending on the meeting's organizer PSTN Calling and/or conferencing provisioning.</span></span>

- <span data-ttu-id="579df-291">来宾用户或客户用户可以从来宾专用网络加入，该网络通过严格的规则使用 FW/NAT 进行保护。</span><span class="sxs-lookup"><span data-stu-id="579df-291">A guest user or a customer user may join from a guest private network, which is protected using FW/NAT with strict rules.</span></span>

<span data-ttu-id="579df-292">[![Microsoft Teams联机呼叫流图 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span><span class="sxs-lookup"><span data-stu-id="579df-292">[![Microsoft Teams Online Call Flows Figure 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)</span></span>

<span data-ttu-id="579df-293">*图 9 - Teams 会议*</span><span class="sxs-lookup"><span data-stu-id="579df-293">*Figure 9 - Teams Meeting*</span></span>

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a><span data-ttu-id="579df-294">用例：与本地Skype for Business联合</span><span class="sxs-lookup"><span data-stu-id="579df-294">Use case: Federation with Skype for Business on premises</span></span>

<span data-ttu-id="579df-295">**由媒体传输中继Teams中继在 Microsoft 365 或 Office 365**</span><span class="sxs-lookup"><span data-stu-id="579df-295">**Media relayed by Teams Transport Relay in Microsoft 365 or Office 365**</span></span>

<span data-ttu-id="579df-296">[![Microsoft Teams在线呼叫流图 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span><span class="sxs-lookup"><span data-stu-id="579df-296">[![Microsoft Teams Online Call Flows Figure 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)</span></span>

<span data-ttu-id="579df-297">*图 10 - 由 Teams 传输中继在 Office 365*</span><span class="sxs-lookup"><span data-stu-id="579df-297">*Figure 10 - Media relayed by Teams Transport Relay in Office 365*</span></span>

<span data-ttu-id="579df-298">请注意：</span><span class="sxs-lookup"><span data-stu-id="579df-298">Note that:</span></span>

- <span data-ttu-id="579df-299">根据定义，联合身份验证是两个租户之间的通信。</span><span class="sxs-lookup"><span data-stu-id="579df-299">Federation is, by definition, a communication between two tenants.</span></span> <span data-ttu-id="579df-300">在这种情况下，使用 Teams 的租户 A Skype for Business租户 B 联合。</span><span class="sxs-lookup"><span data-stu-id="579df-300">In this case, tenant A, which uses Teams, federates with tenant B, which uses Skype for Business on premises.</span></span> <span data-ttu-id="579df-301">如果租户 B 也使用 Microsoft 365 或 Office 365，则 Skype for Business 客户端会使用流 3 与 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="579df-301">If tenant B is also using Microsoft 365 or Office 365, then the Skype for Business client would have used flow 3 to connect with Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="579df-302">从联合客户端Skype for Business到本地Skype for Business Server信号和媒体超出了本文档的范围。</span><span class="sxs-lookup"><span data-stu-id="579df-302">Signaling and media from the federated Skype for Business client to on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="579df-303">但是，为了清楚起见，此处说明了这一点。</span><span class="sxs-lookup"><span data-stu-id="579df-303">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="579df-304">网关Teams Skype for Business之间的信令。</span><span class="sxs-lookup"><span data-stu-id="579df-304">Signaling between Teams and Skype for Business is bridged by a gateway.</span></span>

- <span data-ttu-id="579df-305">在这种情况下，媒体使用流 4 Teams传输中继中继到客户网络和Skype for Business客户端。</span><span class="sxs-lookup"><span data-stu-id="579df-305">Media in this case is relayed by Teams Transport Relay to the customer network and remote Skype for Business client using flow 4.</span></span>

<span data-ttu-id="579df-306">**联合租户中Skype for Business媒体中继的媒体**</span><span class="sxs-lookup"><span data-stu-id="579df-306">**Media relayed by Skype for Business Media Relay in federated tenant**</span></span>

<span data-ttu-id="579df-307">[![Microsoft Teams在线呼叫流图 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span><span class="sxs-lookup"><span data-stu-id="579df-307">[![Microsoft Teams Online Call Flows Figure 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)</span></span>

<span data-ttu-id="579df-308">*图 11 - 联合租户Skype for Business媒体中继的媒体*</span><span class="sxs-lookup"><span data-stu-id="579df-308">*Figure 11 - Media relayed by Skype for Business Media Relay in federated tenant*</span></span>

<span data-ttu-id="579df-309">请注意：</span><span class="sxs-lookup"><span data-stu-id="579df-309">Note that:</span></span>

- <span data-ttu-id="579df-310">从联合客户端Skype for Business到本地客户端Skype for Business Server信号和媒体超出了本文档的范围。</span><span class="sxs-lookup"><span data-stu-id="579df-310">Signaling and media from the federated Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="579df-311">但是，为了清楚起见，此处说明了这一点。</span><span class="sxs-lookup"><span data-stu-id="579df-311">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="579df-312">网关Teams Skype for Business网关之间的信令。</span><span class="sxs-lookup"><span data-stu-id="579df-312">Signaling between Teams and Skype for Business is bridged by a Gateway.</span></span>

- <span data-ttu-id="579df-313">在这种情况下，媒体使用流 2 Skype for Business本地媒体中继中继到客户网络。</span><span class="sxs-lookup"><span data-stu-id="579df-313">Media in this case is relayed by Skype for Business on-premises Media Relay to the customer network using flow 2.</span></span> <span data-ttu-id="579df-314"> (请注意，从 Teams 用户发到联合客户网络中远程媒体中继的流量最初将被媒体中继阻止，直到反向的流量开始流动。</span><span class="sxs-lookup"><span data-stu-id="579df-314">(Note that traffic from Teams user to the remote Media Relay in the federated customer network will be initially blocked by the Media Relay until traffic in the reverse direction starts to flow.</span></span> <span data-ttu-id="579df-315">但是，双向流将在两个方向打开连接。) </span><span class="sxs-lookup"><span data-stu-id="579df-315">However, the bidirectional flow will open connectivity in both directions.)</span></span>

<span data-ttu-id="579df-316">**直接 (对等)**</span><span class="sxs-lookup"><span data-stu-id="579df-316">**Direct (peer-to-peer)**</span></span>

<span data-ttu-id="579df-317">[![Microsoft Teams在线呼叫流图 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span><span class="sxs-lookup"><span data-stu-id="579df-317">[![Microsoft Teams Online Call Flows Figure 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)</span></span>

<span data-ttu-id="579df-318">*图 12 - (直接对等)*</span><span class="sxs-lookup"><span data-stu-id="579df-318">*Figure 12 - Direct (peer-to-peer)*</span></span>

### <a name="teams-hybrid-topology"></a><span data-ttu-id="579df-319">Teams混合拓扑</span><span class="sxs-lookup"><span data-stu-id="579df-319">Teams hybrid topology</span></span>

<span data-ttu-id="579df-320">此拓扑包含Teams本地Skype for Business的拓扑。</span><span class="sxs-lookup"><span data-stu-id="579df-320">This topology includes Teams with a Skype for Business on-premises deployment.</span></span>

<span data-ttu-id="579df-321">[![Microsoft Teams在线呼叫流图 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span><span class="sxs-lookup"><span data-stu-id="579df-321">[![Microsoft Teams Online Call Flows Figure 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)</span></span>

<span data-ttu-id="579df-322">*图 13 - Teams混合拓扑*</span><span class="sxs-lookup"><span data-stu-id="579df-322">*Figure 13 - Teams hybrid topology*</span></span>

- <span data-ttu-id="579df-323">上图中箭头的方向反映影响企业外围连接的通信的启动方向。</span><span class="sxs-lookup"><span data-stu-id="579df-323">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="579df-324">对于媒体的 UDP，第一 (数据包) 反向流动，但可能会阻止这些数据包，直到其他方向的数据包流动。</span><span class="sxs-lookup"><span data-stu-id="579df-324">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>

- <span data-ttu-id="579df-325">Teams与 Skype for Business Online 并排部署，因此客户端显示为"Teams/SFB 用户"。</span><span class="sxs-lookup"><span data-stu-id="579df-325">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user."</span></span>

<span data-ttu-id="579df-326">基于 (拓扑的其他Teams流) ：</span><span class="sxs-lookup"><span data-stu-id="579df-326">Additional flow (on top of Teams topology):</span></span>

- <span data-ttu-id="579df-327">**Flow 5A** – 表示客户网络中 Teams 用户与客户网络边缘的 Skype for Business 本地媒体中继之间的对等媒体流。</span><span class="sxs-lookup"><span data-stu-id="579df-327">**Flow 5A** – Represents a peer-to-peer media flow between a Teams user within the customer network and a Skype for Business on-premises media relay at the customer network edge.</span></span>

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a><span data-ttu-id="579df-328">用例：Teams Skype for Business一对一</span><span class="sxs-lookup"><span data-stu-id="579df-328">Use case: Teams to Skype for Business one-to-one</span></span>

<span data-ttu-id="579df-329">**客户网络内的混合**</span><span class="sxs-lookup"><span data-stu-id="579df-329">**Hybrid within the customer network**</span></span>

<span data-ttu-id="579df-330">[![Microsoft Teams在线呼叫流图 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span><span class="sxs-lookup"><span data-stu-id="579df-330">[![Microsoft Teams Online Call Flows Figure 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)</span></span>

<span data-ttu-id="579df-331">*图 14 - 客户网络内部的混合*</span><span class="sxs-lookup"><span data-stu-id="579df-331">*Figure 14 - Hybrid within customer network*</span></span>

<span data-ttu-id="579df-332">网关Teams Skype for Business之间的信令。</span><span class="sxs-lookup"><span data-stu-id="579df-332">Signaling between Teams and Skype for Business is bridged by a gateway.</span></span> <span data-ttu-id="579df-333">但是，媒体使用流 5 直接在客户网络中点对点路由。</span><span class="sxs-lookup"><span data-stu-id="579df-333">However, media is routed directly peer-to-peer within the customer network using flow 5.</span></span>

<span data-ttu-id="579df-334">**具有外部外部用户Skype for Business混合客户网络 – 由 Microsoft 365 或 Office 365**</span><span class="sxs-lookup"><span data-stu-id="579df-334">**Hybrid customer network with external Skype for Business user – relayed by Microsoft 365 or Office 365**</span></span>

<span data-ttu-id="579df-335">[![Microsoft Teams在线呼叫流图 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span><span class="sxs-lookup"><span data-stu-id="579df-335">[![Microsoft Teams Online Call Flows Figure 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)</span></span>

<span data-ttu-id="579df-336">*图 15 - 具有外部用户Skype for Business混合客户网络 - 由 Office 365*</span><span class="sxs-lookup"><span data-stu-id="579df-336">*Figure 15 - Hybrid customer network with external Skype for Business user - relayed by Office 365*</span></span>

<span data-ttu-id="579df-337">请注意：</span><span class="sxs-lookup"><span data-stu-id="579df-337">Note that:</span></span>

- <span data-ttu-id="579df-338">从客户端Skype for Business到本地客户端Skype for Business Server信号和媒体超出了本文档的范围。</span><span class="sxs-lookup"><span data-stu-id="579df-338">Signaling and media from the Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="579df-339">但是，为了清楚起见，此处说明了这一点。</span><span class="sxs-lookup"><span data-stu-id="579df-339">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="579df-340">网关Teams Skype for Business之间的信令。</span><span class="sxs-lookup"><span data-stu-id="579df-340">Signaling between Teams and Skype for Business is bridged by a gateway.</span></span>

- <span data-ttu-id="579df-341">媒体通过流 4 Teams传输中继中继到客户网络。</span><span class="sxs-lookup"><span data-stu-id="579df-341">Media is relayed through Teams Transport Relay to the customer network through flow 4.</span></span>

<span data-ttu-id="579df-342">**与外部用户Skype for Business混合客户网络 – 由本地 Edge 中继**</span><span class="sxs-lookup"><span data-stu-id="579df-342">**Hybrid customer network with external Skype for Business user – relayed by on-premises Edge**</span></span>

<span data-ttu-id="579df-343">[![Microsoft Teams在线呼叫流图 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span><span class="sxs-lookup"><span data-stu-id="579df-343">[![Microsoft Teams Online Call Flows Figure 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)</span></span>

<span data-ttu-id="579df-344">*图 16 - 具有外部用户Skype for Business混合客户网络 - 由本地 Edge 中继*</span><span class="sxs-lookup"><span data-stu-id="579df-344">*Figure 16 - Hybrid customer network with external Skype for Business user - relayed by on-premises Edge*</span></span>

<span data-ttu-id="579df-345">请注意：</span><span class="sxs-lookup"><span data-stu-id="579df-345">Note that:</span></span>

- <span data-ttu-id="579df-346">从客户端Skype for Business到本地客户端Skype for Business Server信号和媒体超出了本文档的范围。</span><span class="sxs-lookup"><span data-stu-id="579df-346">Signaling and media from Skype for Business client to an on-premises Skype for Business Server is out of scope of this document.</span></span> <span data-ttu-id="579df-347">但是，为了清楚起见，此处说明了这一点。</span><span class="sxs-lookup"><span data-stu-id="579df-347">However, it is illustrated here for clarity.</span></span>

- <span data-ttu-id="579df-348">信号由网关桥接。</span><span class="sxs-lookup"><span data-stu-id="579df-348">Signaling is bridged by a gateway.</span></span>

- <span data-ttu-id="579df-349">媒体通过本地 Edge Skype for Business媒体中继Skype for Business中继，以Teams 5A 在客户网络中与用户通信。</span><span class="sxs-lookup"><span data-stu-id="579df-349">Media is relayed by Skype for Business Media Relay within Skype for Business on-premises Edge to Teams user within the customer network using media flow 5A.</span></span>

### <a name="teams-with-phone-system-direct-routing-topology"></a><span data-ttu-id="579df-350">Teams直接电话系统拓扑</span><span class="sxs-lookup"><span data-stu-id="579df-350">Teams with Phone System Direct Routing topology</span></span>

<span data-ttu-id="579df-351">此拓扑包含Teams直接电话系统的拓扑。</span><span class="sxs-lookup"><span data-stu-id="579df-351">This topology includes Teams with Phone System Direct Routing.</span></span>

<span data-ttu-id="579df-352">直接路由使你能够使用第三方公用电话交换网 (PSTN) 服务提供商，通过将受支持的本地客户拥有的会话边界控制器 (SBC) 硬件设备与 Microsoft 365 或 Office 365 配对，然后将电话中继连接到该设备。</span><span class="sxs-lookup"><span data-stu-id="579df-352">Direct Routing enables you to use a third-party Public Switched Telephone Network (PSTN) service provider by pairing a supported on-premises customer-owned Session Border Controller (SBC) hardware device to Microsoft 365 or Office 365, and then connecting the telephony trunk to that device.</span></span>

<span data-ttu-id="579df-353">若要支持此方案，客户必须部署 Microsoft 的认证合作伙伴之一的经认证的 SBC 进行直接路由。</span><span class="sxs-lookup"><span data-stu-id="579df-353">To support this scenario, the customer must deploy a certified SBC for Direct Routing from one of Microsoft's certified partners.</span></span> <span data-ttu-id="579df-354">SBC 必须按照供应商的建议进行配置，并且对于直接 UDP 流量，Microsoft 365或Office 365路由。</span><span class="sxs-lookup"><span data-stu-id="579df-354">The SBC must be configured as recommended by the vendor, and be routable from Microsoft 365 or Office 365 for direct UDP traffic.</span></span> <span data-ttu-id="579df-355">媒体可以直接从 Teams 和/或 Skype for Business 客户端流向 SBC (绕过 Teams 网关) 或遍历 Teams 网关。</span><span class="sxs-lookup"><span data-stu-id="579df-355">The media may flow directly from Teams and/or the Skype for Business client to the SBC (bypassing the Teams gateway) or traverse through the Teams gateway.</span></span> <span data-ttu-id="579df-356">当中继配置为绕过 Teams 网关时，与 SBC 的连接基于 ICE，其中 SBC 支持 ICE-Lite，而 Teams/Skype for Business 媒体终结点支持 ICE 完整形式。</span><span class="sxs-lookup"><span data-stu-id="579df-356">The connectivity with the SBC, when the trunk is configured to bypass the Teams gateway, is based on ICE, where SBC supports ICE-Lite, while the Teams/Skype for Business media endpoint supports ICE Full Form.</span></span>

<span data-ttu-id="579df-357">[![Microsoft Teams在线呼叫流图 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span><span class="sxs-lookup"><span data-stu-id="579df-357">[![Microsoft Teams Online Call Flows Figure 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)</span></span>

<span data-ttu-id="579df-358">\*图 17 - Teams直接电话系统拓扑</span><span class="sxs-lookup"><span data-stu-id="579df-358">\*Figure 17 - Teams with Phone System Direct Routing topology</span></span>

<span data-ttu-id="579df-359">请注意：</span><span class="sxs-lookup"><span data-stu-id="579df-359">Note that:</span></span>

- <span data-ttu-id="579df-360">上图中箭头的方向反映影响企业外围连接的通信的启动方向。</span><span class="sxs-lookup"><span data-stu-id="579df-360">The direction of the arrows on the diagram above reflect the initiation direction of the communication that affects connectivity at the enterprise perimeters.</span></span> <span data-ttu-id="579df-361">对于媒体的 UDP，第一 (数据包) 反向流动，但可能会阻止这些数据包，直到其他方向的数据包流动。</span><span class="sxs-lookup"><span data-stu-id="579df-361">In the case of UDP for media, the first packet(s) may flow in the reverse direction, but these packets may be blocked until packets in the other direction will flow.</span></span>

- <span data-ttu-id="579df-362">Teams与 Skype for Business Online 并排部署，因此客户端显示为"Teams/SFB 用户"。</span><span class="sxs-lookup"><span data-stu-id="579df-362">Teams is deployed side by side with Skype for Business Online, hence clients are displayed as "Teams/SFB user."</span></span>

<span data-ttu-id="579df-363">其他 (流Teams联机拓扑) ：</span><span class="sxs-lookup"><span data-stu-id="579df-363">Additional flows (on top of Teams online topology):</span></span>

- <span data-ttu-id="579df-364">**Flow 4'** - 表示从 Microsoft 365 或 Office 365 到客户网络的流，用于在云中的 Teams 媒体服务器与本地 SBC 建立连接。</span><span class="sxs-lookup"><span data-stu-id="579df-364">**Flow 4'** - Represents a flow from Microsoft 365 or Office 365 to the customer network, used to establish a connection between the Teams media server in the cloud with the SBC on premises.</span></span>
- <span data-ttu-id="579df-365">**Flow 5B** – 表示客户网络中直接路由 SBC Teams直接路由 SBC 的用户之间的媒体流。</span><span class="sxs-lookup"><span data-stu-id="579df-365">**Flow 5B** – Represents a media flow between the Teams user within the customer network with the Direct Routing SBC in bypass mode.</span></span>
- <span data-ttu-id="579df-366">**Flow 5C** - 表示 PSTN hairpin 呼叫绕过模式下直接路由 SBC 到另一个直接路由 SBC 之间的媒体流。</span><span class="sxs-lookup"><span data-stu-id="579df-366">**Flow 5C** – Represents a media flow between the Direct Routing SBC to another Direct Routing SBC in a PSTN hairpin call bypass mode.</span></span>

<span data-ttu-id="579df-367">**具有直接路由的内部用户 (传输中继Teams中继中继)**</span><span class="sxs-lookup"><span data-stu-id="579df-367">**Internal user with Direct Routing (media relayed by Teams Transport Relay)**</span></span>

<span data-ttu-id="579df-368">[![Microsoft Teams在线呼叫流图 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span><span class="sxs-lookup"><span data-stu-id="579df-368">[![Microsoft Teams Online Call Flows Figure 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)</span></span>

<span data-ttu-id="579df-369">*图 18 - 具有直接路由 (由传输中继Teams中继)*</span><span class="sxs-lookup"><span data-stu-id="579df-369">*Figure 18 - Internal user with Direct Routing (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="579df-370">请注意：</span><span class="sxs-lookup"><span data-stu-id="579df-370">Note that:</span></span>

- <span data-ttu-id="579df-371">SBC 必须具有一个公共 IP 地址，该地址从 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="579df-371">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="579df-372">从 SBC 发信号和媒体Microsoft 365或Office 365反之亦然，使用流 4 和/或流 4'。</span><span class="sxs-lookup"><span data-stu-id="579df-372">Signaling and media from the SBC to Microsoft 365 or Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="579df-373">从客户网络内的客户端发出信号和媒体以Microsoft 365或Office 365流 4。</span><span class="sxs-lookup"><span data-stu-id="579df-373">Signaling and media from the client within the customer network to Microsoft 365 or Office 365 use flow 4.</span></span>

<span data-ttu-id="579df-374">**使用直接路由的远程 (媒体通过媒体服务器和 MP (路由) )**</span><span class="sxs-lookup"><span data-stu-id="579df-374">**Remote user with Direct Routing (media is routed through a media server (MP))**</span></span>

<span data-ttu-id="579df-375">[![Microsoft Teams在线呼叫流图 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span><span class="sxs-lookup"><span data-stu-id="579df-375">[![Microsoft Teams Online Call Flows Figure 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)</span></span>

<span data-ttu-id="579df-376">*图 19 - 使用直接路由 (媒体的远程用户通过媒体服务器 (MP) )*</span><span class="sxs-lookup"><span data-stu-id="579df-376">*Figure 19 - Remote user with Direct Routing (media is routed through a media server (MP))*</span></span>

<span data-ttu-id="579df-377">请注意：</span><span class="sxs-lookup"><span data-stu-id="579df-377">Note that:</span></span>

- <span data-ttu-id="579df-378">SBC 必须具有一个公共 IP 地址，该地址从 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="579df-378">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="579df-379">从 SBC 发信号和媒体Microsoft 365或Office 365反之亦然，使用流 4 和/或流 4'。</span><span class="sxs-lookup"><span data-stu-id="579df-379">Signaling and media from the SBC to Microsoft 365 or Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="579df-380">从 Internet 上的客户端发出信号和媒体以Microsoft 365或Office 365流 3。</span><span class="sxs-lookup"><span data-stu-id="579df-380">Signaling and media from the client on the Internet to Microsoft 365 or Office 365 use flow 3.</span></span>

<span data-ttu-id="579df-381">**内部用户直接路由 (绕过媒体)**</span><span class="sxs-lookup"><span data-stu-id="579df-381">**Internal user Direct Routing (media bypass)**</span></span>

<span data-ttu-id="579df-382">[![Microsoft Teams在线呼叫流图 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span><span class="sxs-lookup"><span data-stu-id="579df-382">[![Microsoft Teams Online Call Flows Figure 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)</span></span>

<span data-ttu-id="579df-383">*图 20 - 内部用户直接路由 (绕过媒体)*</span><span class="sxs-lookup"><span data-stu-id="579df-383">*Figure 20 - Internal user Direct Routing (media bypass)*</span></span>

<span data-ttu-id="579df-384">请注意：</span><span class="sxs-lookup"><span data-stu-id="579df-384">Note that:</span></span>

- <span data-ttu-id="579df-385">SBC 必须具有一个公共 IP 地址，该地址从 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="579df-385">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="579df-386">从 SBC 发Microsoft 365或Office 365，反之亦然，使用流 4 和/或流 4'。</span><span class="sxs-lookup"><span data-stu-id="579df-386">Signaling from SBC to Microsoft 365 or Office 365 and vice versa use flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="579df-387">从客户网络内的客户端发出信号，Microsoft 365或Office 365流 4。</span><span class="sxs-lookup"><span data-stu-id="579df-387">Signaling from client within the customer network to Microsoft 365 or Office 365 use flow 4.</span></span>

- <span data-ttu-id="579df-388">从客户网络内的客户端到客户网络内的 SBC 的媒体使用流 5B。</span><span class="sxs-lookup"><span data-stu-id="579df-388">Media from client within the customer network to SBC within the customer network use flow 5B.</span></span>

<span data-ttu-id="579df-389">**使用直接路由的远程用户 (传输中继Teams媒体旁路)**</span><span class="sxs-lookup"><span data-stu-id="579df-389">**Remote user with Direct Routing (media bypass relayed by Teams Transport Relay)**</span></span>

<span data-ttu-id="579df-390">[![Microsoft Teams在线呼叫流图 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span><span class="sxs-lookup"><span data-stu-id="579df-390">[![Microsoft Teams Online Call Flows Figure 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)</span></span>

<span data-ttu-id="579df-391">*图 21 - 使用直接路由的远程用户 (传输中继中继Teams媒体旁路)*</span><span class="sxs-lookup"><span data-stu-id="579df-391">*Figure 21 - Remote user with Direct Routing (media bypass relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="579df-392">请注意：</span><span class="sxs-lookup"><span data-stu-id="579df-392">Note that:</span></span>

- <span data-ttu-id="579df-393">SBC 必须具有一个公共 IP 地址，该地址从 Microsoft 365 或 Office 365 Internet 进行路由。</span><span class="sxs-lookup"><span data-stu-id="579df-393">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365 and Internet.</span></span>

- <span data-ttu-id="579df-394">从 SBC 到 Microsoft 365 或 Office 365（反之亦然）使用流 4 和/或流 4'。</span><span class="sxs-lookup"><span data-stu-id="579df-394">Signaling from the SBC to Microsoft 365 or Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="579df-395">从 Internet 上的客户端发出信号以Microsoft 365或Office 365流 3。</span><span class="sxs-lookup"><span data-stu-id="579df-395">Signaling from the client on the Internet to Microsoft 365 or Office 365 uses flow 3.</span></span>

- <span data-ttu-id="579df-396">从 Internet 上的客户端到客户网络中 SBC 的媒体使用流 3 和流 4，由 Teams中继。</span><span class="sxs-lookup"><span data-stu-id="579df-396">Media from the client on the Internet to the SBC within the customer network uses flows 3 and 4, relayed by Teams Transport Relay.</span></span>

<span data-ttu-id="579df-397">**远程用户直接路由 (绕过媒体直接)**</span><span class="sxs-lookup"><span data-stu-id="579df-397">**Remote user Direct Routing (media bypass direct)**</span></span>

<span data-ttu-id="579df-398">[![Microsoft Teams在线呼叫流图 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span><span class="sxs-lookup"><span data-stu-id="579df-398">[![Microsoft Teams Online Call Flows Figure 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)</span></span>

<span data-ttu-id="579df-399">*图 22 - 远程用户直接路由 (绕过媒体直接)*</span><span class="sxs-lookup"><span data-stu-id="579df-399">*Figure 22 - Remote user Direct Routing (media bypass direct)*</span></span>

<span data-ttu-id="579df-400">请注意：</span><span class="sxs-lookup"><span data-stu-id="579df-400">Note that:</span></span>

- <span data-ttu-id="579df-401">SBC 必须具有一个公共 IP 地址，该地址从 Microsoft 365 或 Office 365 Internet 进行路由。</span><span class="sxs-lookup"><span data-stu-id="579df-401">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365 and the Internet.</span></span>

- <span data-ttu-id="579df-402">从 SBC 到 Microsoft 365 或 Office 365（反之亦然）使用流 4 和/或流 4'。</span><span class="sxs-lookup"><span data-stu-id="579df-402">Signaling from the SBC to Microsoft 365 or Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="579df-403">从 Internet 上的客户端发出信号以Microsoft 365或Office 365流 3。</span><span class="sxs-lookup"><span data-stu-id="579df-403">Signaling from the client on the Internet to Microsoft 365 or Office 365 uses flow 3.</span></span>

- <span data-ttu-id="579df-404">从 Internet 上的客户端到客户网络中 SBC 的媒体使用流 2。</span><span class="sxs-lookup"><span data-stu-id="579df-404">Media from the client on the Internet to the SBC within the customer network uses flow 2.</span></span>

<span data-ttu-id="579df-405">**直接路由 (媒体旁路) – 由于呼叫转接/转接 (PSTN)**</span><span class="sxs-lookup"><span data-stu-id="579df-405">**Direct Routing (media bypass) – PSTN hairpin call (due to call forward/transfer)**</span></span>

<span data-ttu-id="579df-406">[![Microsoft Teams在线呼叫流图 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span><span class="sxs-lookup"><span data-stu-id="579df-406">[![Microsoft Teams Online Call Flows Figure 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)</span></span>

<span data-ttu-id="579df-407">*图 23 - 直接路由 (媒体旁路) - 由于呼叫转接/转接 (PSTN hairpin 呼叫)*</span><span class="sxs-lookup"><span data-stu-id="579df-407">*Figure 23 - Direct Routing (media bypass) - PSTN hairpin call (due to call forward/transfer)*</span></span>

<span data-ttu-id="579df-408">请注意：</span><span class="sxs-lookup"><span data-stu-id="579df-408">Note that:</span></span>

- <span data-ttu-id="579df-409">SBC 必须具有一个公共 IP 地址，该地址从 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="579df-409">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="579df-410">从 SBC 到 Microsoft 365 或 Office 365（反之亦然）使用流 4 和/或流 4'。</span><span class="sxs-lookup"><span data-stu-id="579df-410">Signaling from the SBC to Microsoft 365 or Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="579df-411">将呼叫从 PSTN 固定到 PSTN 后，客户端将退出信号和媒体循环。</span><span class="sxs-lookup"><span data-stu-id="579df-411">The client is out of the signaling and media loop after the call is hairpinned from PSTN to PSTN.</span></span>

- <span data-ttu-id="579df-412">从客户网络内的 SBC 实例 A 到客户网络内的 SBC 实例 B 的媒体 (其中，A 和 B 可以是使用流 5C 的) 实例。</span><span class="sxs-lookup"><span data-stu-id="579df-412">Media from SBC instance A within the customer network to SBC instance B within the customer network (where, A and B can be the same instance) uses flow 5C.</span></span>

<span data-ttu-id="579df-413">**直接路由 (通过 Microsoft 365 或 Office 365) - 跨两个租户的 PSTN hairpin 呼叫**</span><span class="sxs-lookup"><span data-stu-id="579df-413">**Direct Routing (media through Microsoft 365 or Office 365) – PSTN hairpin call across two tenants**</span></span>

<span data-ttu-id="579df-414">[![Microsoft Teams在线呼叫流图 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span><span class="sxs-lookup"><span data-stu-id="579df-414">[![Microsoft Teams Online Call Flows Figure 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)</span></span>

<span data-ttu-id="579df-415">*图 24 - 通过 (或 Microsoft 365 Office 365) 直接路由媒体 - 跨两个租户的 PSTN hairpin 呼叫*</span><span class="sxs-lookup"><span data-stu-id="579df-415">*Figure 24 - Direct Routing (media through Microsoft 365 or Office 365) – PSTN hairpin call across two tenants*</span></span>

<span data-ttu-id="579df-416">请注意：</span><span class="sxs-lookup"><span data-stu-id="579df-416">Note that:</span></span>

- <span data-ttu-id="579df-417">SBC 必须具有一个公共 IP 地址，该地址从 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="579df-417">The SBC must have a public IP address that is routable from Microsoft 365 or Office 365.</span></span>

- <span data-ttu-id="579df-418">从 SBC 到 Microsoft 365 或 Office 365（反之亦然）使用流 4 和/或流 4'。</span><span class="sxs-lookup"><span data-stu-id="579df-418">Signaling from the SBC to Microsoft 365 or Office 365 and vice versa uses flow 4 and/or flow 4'.</span></span>

- <span data-ttu-id="579df-419">将呼叫从 PSTN 固定到 PSTN 后，客户端将退出信号和媒体循环。</span><span class="sxs-lookup"><span data-stu-id="579df-419">The client is out of the signaling and media loop after the call is hairpinned from PSTN to PSTN.</span></span>

- <span data-ttu-id="579df-420">客户网络 X 中的 SBC 实例 A 到 SBC 实例 B 的媒体必须通过 Microsoft 365 或 Office 365 媒体服务器中继，并且不能使用绕过模式。</span><span class="sxs-lookup"><span data-stu-id="579df-420">Media from SBC instance A within the customer network X to SBC instance B must be relayed through the Microsoft 365 or Office 365 Media Server and can't use bypass mode.</span></span>

## <a name="teams-with-express-route-optimization"></a><span data-ttu-id="579df-421">Teams快速路由优化</span><span class="sxs-lookup"><span data-stu-id="579df-421">Teams with Express Route optimization</span></span>

<span data-ttu-id="579df-422">[![Microsoft Teams在线呼叫流图 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span><span class="sxs-lookup"><span data-stu-id="579df-422">[![Microsoft Teams Online Call Flows Figure 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)</span></span>

<span data-ttu-id="579df-423">*图 25 - Teams快速路由优化*</span><span class="sxs-lookup"><span data-stu-id="579df-423">*Figure 25 - Teams with Express Route optimization*</span></span>

<span data-ttu-id="579df-424">在两端对齐并部署 Express Route 的情况下，Teams流从流 4 重新路由到流 1，从流 4'重新路由到流 1'。</span><span class="sxs-lookup"><span data-stu-id="579df-424">In the case that Express Route is justified and deployed, then Teams flows could be re-routed from flow 4 to flow 1 and from flow 4' to flow 1'.</span></span> <span data-ttu-id="579df-425">但是，Teams应用程序依赖于使用流 4 和Microsoft 365 Office 365 4' 通过 Internet 流的其他流或流;因此，不得阻止这些流。</span><span class="sxs-lookup"><span data-stu-id="579df-425">However, the Teams application has a hard dependency on other Microsoft 365 or Office 365 flows over the Internet using flows 4 and 4'; hence these flows must not be blocked.</span></span>

<span data-ttu-id="579df-426">请注意，Skype for Business混合边缘流量路由到 Internet，而不是路由到 Express Route，以便与外部用户通信并与其他租户联合。</span><span class="sxs-lookup"><span data-stu-id="579df-426">Note that Skype for Business hybrid Edge traffic is routed to the Internet and not to Express Route to communicate with external users and federate with other tenants.</span></span>

<span data-ttu-id="579df-427">为了防止非对称流，重新路由必须同时朝两个方向进行。</span><span class="sxs-lookup"><span data-stu-id="579df-427">To prevent asymmetrical flows, re-routing must be in both directions.</span></span> <span data-ttu-id="579df-428">换言之，客户网络内的地址可以基于优化通过 Internet 或 Express Route 进行路由，但不能同时通过两者。</span><span class="sxs-lookup"><span data-stu-id="579df-428">In other words, an address within the customer network is routable either through Internet or Express Route, based on optimization, but not through both.</span></span>


<span data-ttu-id="579df-429">**客户网络与外部用户 (传输中继Teams媒体) ：**</span><span class="sxs-lookup"><span data-stu-id="579df-429">**Customer network to external user (media relayed by Teams Transport Relay):**</span></span>

<span data-ttu-id="579df-430">[![Microsoft Teams在线呼叫流图 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span><span class="sxs-lookup"><span data-stu-id="579df-430">[![Microsoft Teams Online Call Flows Figure 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)</span></span>

<span data-ttu-id="579df-431">*图 26 - 客户网络与外部用户 (中继中继Teams媒体)*</span><span class="sxs-lookup"><span data-stu-id="579df-431">*Figure 26 - Customer network to external user (media relayed by Teams Transport Relay)*</span></span>

<span data-ttu-id="579df-432">**高级步骤：**</span><span class="sxs-lookup"><span data-stu-id="579df-432">**High-Level Steps:**</span></span>

1. <span data-ttu-id="579df-433">Teams客户网络内的用户使用 flow2 (DNS) URL 域名。</span><span class="sxs-lookup"><span data-stu-id="579df-433">Teams User within customer network resolves URL domain name (DNS) using flow2.</span></span>
1. <span data-ttu-id="579df-434">Teams客户网络内的用户使用流 1 在 Teams 传输中继上分配媒体中继端口。</span><span class="sxs-lookup"><span data-stu-id="579df-434">Teams User within customer network allocates a media Relay port on Teams Transport Relay using flow 1.</span></span>
1. <span data-ttu-id="579df-435">Teams客户网络内的用户使用流 1 将"邀请"与 ICE 候选项一起发送到Microsoft 365或Office 365。</span><span class="sxs-lookup"><span data-stu-id="579df-435">Teams User within customer network sends "invite" with ICE candidates using flow 1 to Microsoft 365 or Office 365.</span></span>
1. <span data-ttu-id="579df-436">Microsoft 365或Office 365使用流 3 Teams向外部用户发送通知。</span><span class="sxs-lookup"><span data-stu-id="579df-436">Microsoft 365 or Office 365 sends notification to external Teams user using flow 3.</span></span>
1. <span data-ttu-id="579df-437">Teams使用流 3 在 Teams 传输中继上分配媒体中继端口。</span><span class="sxs-lookup"><span data-stu-id="579df-437">Teams external user allocates a media Relay port on Teams Transport Relay using flow 3.</span></span>
1. <span data-ttu-id="579df-438">Teams使用流 3 向 ICE 候选项发送"答案"，使用流 1 将Teams转发Flow A。</span><span class="sxs-lookup"><span data-stu-id="579df-438">Teams external user sends "answer" with ICE candidates using flow 3, which is forwarded back to Teams user A using Flow 1.</span></span>
1. <span data-ttu-id="579df-439">Teams用户 A Teams用户 B 调用 ICE 连接测试，并选择流 1 和流 3，它们由 Teams中继。</span><span class="sxs-lookup"><span data-stu-id="579df-439">Teams User A and Teams User B invoke ICE connectivity tests and selects flows 1 and 3, which are relayed by Teams Transport Relay.</span></span>
1. <span data-ttu-id="579df-440">Teams用户使用流 1 和Microsoft 365 3 Office 365遥测数据。</span><span class="sxs-lookup"><span data-stu-id="579df-440">Teams Users send telemetry to Microsoft 365 or Office 365 using flows 1 and 3.</span></span>

> [!NOTE]
> <span data-ttu-id="579df-441">Flow 4 必须启用 ，以支持应用程序Teams依赖于要求流 4 的其他微服务。</span><span class="sxs-lookup"><span data-stu-id="579df-441">Flow 4 must be enabled to support dependencies of Teams application on other micro-services that mandates flow 4.</span></span>
