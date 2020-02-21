---
title: Lync Server 2013 SIP 中继支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SIP trunking support
ms:assetid: e3042831-e8d8-4ea2-baa2-1a697401ffa0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399005(v=OCS.15)
ms:contentKeyID: 48185714
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f31159a2d14facbdfed2f74f3567081699a7bde9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42181835"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sip-trunking-support-in-lync-server-2013"></a><span data-ttu-id="e7652-102">Lync Server 2013 中的 SIP 中继支持</span><span class="sxs-lookup"><span data-stu-id="e7652-102">SIP trunking support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7652-103">_**上次修改的主题：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e7652-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e7652-104">如果计划将企业语音与 SIP 中继结合使用，则必须部署中介服务器，并确保其他基础结构和组件满足部署模型的相应支持要求。</span><span class="sxs-lookup"><span data-stu-id="e7652-104">If you plan to use Enterprise Voice with SIP trunking, you must deploy a Mediation Server and make sure that other infrastructure and components meet the support requirements appropriate to your deployment model.</span></span> <span data-ttu-id="e7652-105">有关确定是否实现 SIP 中继的详细信息，请参阅规划文档中的[Lync Server 2013 中的 SIP 中继概述](lync-server-2013-overview-of-sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="e7652-105">For details about determining whether to implement SIP trunking, see [Overview of SIP trunking in Lync Server 2013](lync-server-2013-overview-of-sip-trunking.md) in the Planning documentation.</span></span>

<span data-ttu-id="e7652-106">您可以使用 Microsoft 统一通信开放式互操作性计划进行企业电话基础结构，以查找限定的公共交换电话网络（PSTN）网关、IP Pbx 和 SIP 中继服务，包括符合条件的 IP 电话服务提供商。</span><span class="sxs-lookup"><span data-stu-id="e7652-106">You can use the Microsoft Unified Communications Open Interoperability Program for enterprise telephony infrastructure to find qualified public switched telephone network (PSTN) gateways, IP-PBXs, and SIP trunking services, including qualified IP telephony service providers.</span></span> <span data-ttu-id="e7652-107">有关详细信息，请参阅 Microsoft 统一通信开放式互操作性[https://go.microsoft.com/fwlink/p/?LinkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309)计划网站，网址为。</span><span class="sxs-lookup"><span data-stu-id="e7652-107">For details, see the Microsoft Unified Communications Open Interoperability Program website at [https://go.microsoft.com/fwlink/p/?LinkId=203309](https://go.microsoft.com/fwlink/p/?linkid=203309).</span></span>

<div>

## <a name="mediation-server-support"></a><span data-ttu-id="e7652-108">中介服务器支持</span><span class="sxs-lookup"><span data-stu-id="e7652-108">Mediation Server Support</span></span>

<span data-ttu-id="e7652-109">若要实现 SIP 中继，必须通过中介服务器路由连接，该服务器充当 Lync Server 2013 客户端和服务提供商之间的通信会话的代理。</span><span class="sxs-lookup"><span data-stu-id="e7652-109">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider.</span></span> <span data-ttu-id="e7652-110">中介服务器对来自客户端和服务器的媒体流量进行解码，并在将其发送到服务提供程序之前对其进行重新编码。</span><span class="sxs-lookup"><span data-stu-id="e7652-110">The Mediation Server decodes the media traffic from clients and servers and re-encodes it before sending it to the service provider.</span></span> <span data-ttu-id="e7652-111">重新编码是必需的，因为 SIP 中继不支持用于防火墙遍历的一些编解码器，如实时音频（RTA）或交互连接建立（ICE）协议协商。</span><span class="sxs-lookup"><span data-stu-id="e7652-111">The re-encoding is needed because SIP trunks do not support some codecs used, such as Real Time Audio (RTA) or Interactive Connectivity Establishment (ICE) protocol negotiation for firewall traversal.</span></span>

<span data-ttu-id="e7652-112">每个中介服务器都可以有两个网络适配器，它们提供了内部和外部网络接口。</span><span class="sxs-lookup"><span data-stu-id="e7652-112">Each Mediation Server can have two network adapters, which provide an internal and an external network interface.</span></span> <span data-ttu-id="e7652-113">外部接口通常称为网关接口，因为传统情况下它用于连接到 PSTN 网关或 ip-pbx。</span><span class="sxs-lookup"><span data-stu-id="e7652-113">The external interface is commonly called the gateway interface because, traditionally, it has been used to connect to a PSTN gateway or an IP-PBX.</span></span> <span data-ttu-id="e7652-114">若要实现 SIP 中继，请将外部接口连接到服务提供商的会话边界控制器（SBC）。</span><span class="sxs-lookup"><span data-stu-id="e7652-114">To implement a SIP trunk, you connect the external interface to a Session Border Controller (SBC) at a service provider.</span></span>

</div>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="e7652-115">集中 SIP 中继和分布式 SIP 中继</span><span class="sxs-lookup"><span data-stu-id="e7652-115">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="e7652-116">*集中*SIP 中继通过数据中心路由所有 Internet 协议（VoIP）通信，包括分支站点流量。</span><span class="sxs-lookup"><span data-stu-id="e7652-116">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your data center.</span></span> <span data-ttu-id="e7652-117">集中部署模型简单、经济高效，通常是使用 Lync Server 2013 实现 SIP 中继的首选方法。</span><span class="sxs-lookup"><span data-stu-id="e7652-117">The centralized deployment model is simple, cost-effective, and is generally the preferred approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="e7652-118">根据企业中的使用模式，您可能不希望通过集中 SIP 中继路由所有用户。</span><span class="sxs-lookup"><span data-stu-id="e7652-118">Depending on usage patterns within your enterprise, you may not want to route all users through the centralized SIP trunk.</span></span> <span data-ttu-id="e7652-119">为分析您的需求，请回答以下问题：</span><span class="sxs-lookup"><span data-stu-id="e7652-119">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="e7652-120">每个站点有多大？</span><span class="sxs-lookup"><span data-stu-id="e7652-120">How big is each site?</span></span> <span data-ttu-id="e7652-121">有多少用户？</span><span class="sxs-lookup"><span data-stu-id="e7652-121">How many users?</span></span>

  - <span data-ttu-id="e7652-122">每个站点上的哪些直接向内拨号（已）号码可以获得最多的电话呼叫？</span><span class="sxs-lookup"><span data-stu-id="e7652-122">Which Direct Inward Dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="e7652-123">*分布式*SIP 中继是一种部署模型，可在其中实现一个或多个分支站点的本地 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="e7652-123">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="e7652-124">然后，将 VoIP 流量从分支站点直接路由到其服务提供商，而无需遍历您的数据中心。</span><span class="sxs-lookup"><span data-stu-id="e7652-124">VoIP traffic is then routed from the branch site directly to their service provider, without going through your data center.</span></span>

<span data-ttu-id="e7652-125">仅在出现以下情况时才需要使用分布式 SIP 中继：</span><span class="sxs-lookup"><span data-stu-id="e7652-125">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="e7652-126">分支站点需要 survivable 电话连接（例如，如果 WAN 故障）。</span><span class="sxs-lookup"><span data-stu-id="e7652-126">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="e7652-127">如果分支确实需要冗余和故障转移，则服务提供商将会花费更多费用，配置将需要更长时间。</span><span class="sxs-lookup"><span data-stu-id="e7652-127">If the branch does need redundancy and failover, the service provider will charge more and the configuration will take longer.</span></span> <span data-ttu-id="e7652-128">应针对每个分支站点对此进行分析。</span><span class="sxs-lookup"><span data-stu-id="e7652-128">This should be analyzed for each branch site.</span></span> <span data-ttu-id="e7652-129">某些分支可能需要冗余和故障转移，而其他分支可能不需要。</span><span class="sxs-lookup"><span data-stu-id="e7652-129">Some of your branches may require redundancy and failover, while others may not.</span></span>

  - <span data-ttu-id="e7652-130">分支站点和数据中心位于不同的国家/地区。</span><span class="sxs-lookup"><span data-stu-id="e7652-130">The branch site and data center are in different countries/regions.</span></span> <span data-ttu-id="e7652-131">出于兼容性和合法性考虑，每个国家/地区至少需要一个 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="e7652-131">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span>

<span data-ttu-id="e7652-132">决定是部署集中式 SIP 中继还是分布式 SIP 中继需要进行成本效益分析。</span><span class="sxs-lookup"><span data-stu-id="e7652-132">Deciding whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="e7652-133">在某些情况下，选择分布式部署模式可能会有好处，即使不是必需的也是如此。</span><span class="sxs-lookup"><span data-stu-id="e7652-133">In some cases, it may be advantageous to opt for the distributed deployment mode, even if it is not required.</span></span> <span data-ttu-id="e7652-134">在完全集中的部署中，所有分支站点流量都通过 WAN 链路进行路由。</span><span class="sxs-lookup"><span data-stu-id="e7652-134">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="e7652-135">如果您不想支付 WAN 链路所需的带宽费用，则可能需要使用分布式 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="e7652-135">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e7652-136">有关您可能使用分布式 SIP 中继的原因和方式的详细信息，请参阅规划文档中的<A href="lync-server-2013-branch-site-sip-trunking.md">Lync Server 2013 中的分支站点 SIP 中继</A>。</span><span class="sxs-lookup"><span data-stu-id="e7652-136">For details about why and how you might use distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A> in the Planning documentation.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="e7652-137">支持的 SIP 中继连接类型</span><span class="sxs-lookup"><span data-stu-id="e7652-137">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="e7652-138">Lync Server 2013 支持 SIP 中继的以下连接类型：</span><span class="sxs-lookup"><span data-stu-id="e7652-138">Lync Server 2013 supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="e7652-139">多协议标签交换 (MPLS) 是一种专用网络，用于定向数据并将其从一个网络节点传送到下一个网络节点。</span><span class="sxs-lookup"><span data-stu-id="e7652-139">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next.</span></span> <span data-ttu-id="e7652-140">MPLS 网络中的带宽可与其他订阅者共享，并为每个数据包分配一个标签以便区别每个订阅者的数据。</span><span class="sxs-lookup"><span data-stu-id="e7652-140">The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s.</span></span> <span data-ttu-id="e7652-141">此连接类型不需要 VPN。</span><span class="sxs-lookup"><span data-stu-id="e7652-141">This connection type does not require VPN.</span></span> <span data-ttu-id="e7652-142">潜在的缺点是过多的 IP 流量会干扰 VoIP 操作，除非为 VoIP 流量指定优先级。</span><span class="sxs-lookup"><span data-stu-id="e7652-142">A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="e7652-143">没有其他通信的专用连接通常是最可靠和安全的连接类型（例如，租用光纤连接或 T1 线路）。</span><span class="sxs-lookup"><span data-stu-id="e7652-143">A private connection with no other traffic is typically the most reliable and secure connection type (for example, a leased fiber-optic connection or T1 line).</span></span> <span data-ttu-id="e7652-144">此连接类型提供了最高的呼叫存储容量，但通常成本最高。</span><span class="sxs-lookup"><span data-stu-id="e7652-144">This connection type provides the highest call-carrying capacity, but is typically the most expensive.</span></span> <span data-ttu-id="e7652-145">无需使用 VPN。</span><span class="sxs-lookup"><span data-stu-id="e7652-145">VPN is not required.</span></span> <span data-ttu-id="e7652-146">专用连接适用于具有大量呼叫或严格的安全和可用性要求的组织。</span><span class="sxs-lookup"><span data-stu-id="e7652-146">Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="e7652-147">公用 Internet 是开销最低的连接类型，但也是最不可靠的，并且具有最低的呼叫存储容量。</span><span class="sxs-lookup"><span data-stu-id="e7652-147">The public Internet is the least expensive connection type, but also the least reliable, and the one with the lowest call-carrying capacity.</span></span> <span data-ttu-id="e7652-148">如果 Internet 电话服务提供商（ITSP）支持传输层安全性（TLS）和安全实时传输协议（SRTP）来加密信号和媒体流量，则您的 Internet 电话服务提供商（）可以帮助保护这种 SIP 中继连接类型。</span><span class="sxs-lookup"><span data-stu-id="e7652-148">Your Internet Telephony Service Provider (ITSP) can help secure this SIP trunk connection type if it supports Transport Layer Security (TLS) and Secure Real-Time Transport Protocol (SRTP) to encrypt signaling and media traffic.</span></span> <span data-ttu-id="e7652-149">如果无法通过 Internet 配置 SIP 中继连接以使用 TLS 和 SRTP，强烈建议您使用 VPN 隧道提供更安全的连接。</span><span class="sxs-lookup"><span data-stu-id="e7652-149">If you cannot configure a SIP trunk connection through the Internet to use TLS and SRTP, we strongly recommend that you use a VPN tunnel to provide a more secure connection.</span></span> <span data-ttu-id="e7652-150">请联系你的 ITSP 以确定它是否提供对 TLS 的 SRTP 支持。</span><span class="sxs-lookup"><span data-stu-id="e7652-150">Contact your ITSP to determine whether it provides support for TLS with SRTP.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="e7652-151">选择连接类型</span><span class="sxs-lookup"><span data-stu-id="e7652-151">Selecting a Connection Type</span></span>

<span data-ttu-id="e7652-152">最适用于企业的 SIP 中继连接类型取决于企业的需求和预算。</span><span class="sxs-lookup"><span data-stu-id="e7652-152">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="e7652-153">对于中等规模或更大的企业，MPLS 网络通常可提供最大价值。</span><span class="sxs-lookup"><span data-stu-id="e7652-153">For a mid-size or larger enterprise, an MPLS network generally provides the most value.</span></span> <span data-ttu-id="e7652-154">它能提供必需的带宽，且费率比专用网络更低。</span><span class="sxs-lookup"><span data-stu-id="e7652-154">It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="e7652-155">大型企业可能需要专用光纤或 T1 连接。</span><span class="sxs-lookup"><span data-stu-id="e7652-155">Large enterprises may require a private fiber-optic or T1 connection.</span></span>

  - <span data-ttu-id="e7652-156">对于呼叫量较低的小型企业或分支站点，通过 Internet 的 SIP 中继可能是最佳选择。</span><span class="sxs-lookup"><span data-stu-id="e7652-156">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="e7652-157">但是，不建议将此连接类型用于中等规模或更大的网站。</span><span class="sxs-lookup"><span data-stu-id="e7652-157">However, this connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="e7652-158">编解码器支持</span><span class="sxs-lookup"><span data-stu-id="e7652-158">Codec Support</span></span>

<span data-ttu-id="e7652-159">服务提供程序代理必须支持以下编解码器：</span><span class="sxs-lookup"><span data-stu-id="e7652-159">The service provider proxy must support the following codecs:</span></span>

  - <span data-ttu-id="e7652-160">G.711 a-law（主要在北美以外的国家/地区使用）</span><span class="sxs-lookup"><span data-stu-id="e7652-160">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="e7652-161">G.711 µ-law（在北美使用）</span><span class="sxs-lookup"><span data-stu-id="e7652-161">G.711 µ-law (used in North America)</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

