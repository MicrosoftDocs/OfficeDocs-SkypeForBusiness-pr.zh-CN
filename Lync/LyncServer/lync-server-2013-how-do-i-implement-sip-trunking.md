---
title: Lync Server 2013：如何实现 SIP 中继？
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: How do I implement SIP trunking?
ms:assetid: 273a22b1-8a4c-4187-acf8-c57d5c6598ce
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425743(v=OCS.15)
ms:contentKeyID: 48183666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ecd89ce28f1565e44c92ba543ccf992bb2a3c811
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504139"
---
# <a name="how-do-i-implement-sip-trunking-in-lync-server-2013"></a><span data-ttu-id="2b2db-102">如何在 Lync Server 2013 中实现 SIP 中继？</span><span class="sxs-lookup"><span data-stu-id="2b2db-102">How do I implement SIP trunking in Lync Server 2013?</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b2db-103">_**上次修改的主题：** 2013-03-18_</span><span class="sxs-lookup"><span data-stu-id="2b2db-103">_**Topic Last Modified:** 2013-03-18_</span></span>

<span data-ttu-id="2b2db-104">若要实现 SIP 中继，您必须通过中介服务器路由连接，该服务器充当 Lync Server 2013 客户端与服务提供商和 transcodes 媒体之间的通信会话的代理（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="2b2db-104">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Lync Server 2013 clients and the service provider and transcodes media, when necessary.</span></span>

<span data-ttu-id="2b2db-105">每个中介服务器都有一个内部网络接口和一个外部网络接口。</span><span class="sxs-lookup"><span data-stu-id="2b2db-105">Each Mediation Server has an internal network interface and an external network interface.</span></span> <span data-ttu-id="2b2db-106">内部接口连接到前端服务器。</span><span class="sxs-lookup"><span data-stu-id="2b2db-106">The internal interface connects to the Front End Servers.</span></span> <span data-ttu-id="2b2db-107">外部接口通常称为网关接口，因为它通常用于将中介服务器连接到公开交换的电话网络， (PSTN) 网关或 ip-pbx。</span><span class="sxs-lookup"><span data-stu-id="2b2db-107">The external interface is commonly called the gateway interface because it has traditionally been used to connect the Mediation Server to a public switched telephone network (PSTN) gateway or an IP-PBX.</span></span> <span data-ttu-id="2b2db-108">若要实现 SIP 中继，请将中介服务器的外部接口连接到 ITSP 的外部边缘组件。</span><span class="sxs-lookup"><span data-stu-id="2b2db-108">To implement a SIP trunk, you connect the external interface of the Mediation Server to the external edge component of the ITSP.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b2db-109">ITSP 的外部边缘组件可以是会话边界控制器 (SBC)、路由器或网关。</span><span class="sxs-lookup"><span data-stu-id="2b2db-109">The external edge component of the ITSP could be a Session Border Controller (SBC), a router, or a gateway.</span></span>



</div>

<span data-ttu-id="2b2db-110">有关中介服务器的详细信息，请参阅 [Lync server 2013 中的中介服务器组件](lync-server-2013-mediation-server-component.md)。</span><span class="sxs-lookup"><span data-stu-id="2b2db-110">For details about Mediation Servers, see [Mediation Server component in Lync Server 2013](lync-server-2013-mediation-server-component.md).</span></span>

<div>

## <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="2b2db-111">集中 SIP 中继和分布式 SIP 中继</span><span class="sxs-lookup"><span data-stu-id="2b2db-111">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="2b2db-112">*集中* SIP 中继通过您的中心站点路由所有 Internet 协议 (VoIP) 流量，包括分支站点流量。</span><span class="sxs-lookup"><span data-stu-id="2b2db-112">*Centralized* SIP trunking routes all Voice over Internet Protocol (VoIP) traffic, including branch site traffic, through your central site.</span></span> <span data-ttu-id="2b2db-113">集中部署模型简单、经济高效，通常是使用 Lync Server 2013 实现 SIP 中继的推荐方法。</span><span class="sxs-lookup"><span data-stu-id="2b2db-113">The centralized deployment model is simple, cost-effective, and is generally the recommended approach for implementing SIP trunks with Lync Server 2013.</span></span>

<span data-ttu-id="2b2db-114">*分布式* SIP 中继是一种部署模型，可在其中实现一个或多个分支站点的本地 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="2b2db-114">*Distributed* SIP trunking is a deployment model in which you implement a local SIP trunk at one or more branch sites.</span></span> <span data-ttu-id="2b2db-115">然后，将 VoIP 流量从分支站点直接路由到服务提供商，而无需通过中央站点。</span><span class="sxs-lookup"><span data-stu-id="2b2db-115">VoIP traffic is then routed from the branch site directly to a service provider without going through the central site.</span></span>

<span data-ttu-id="2b2db-116">仅在出现以下情况时才需要使用分布式 SIP 中继：</span><span class="sxs-lookup"><span data-stu-id="2b2db-116">Distributed SIP trunking is required only in the following cases:</span></span>

  - <span data-ttu-id="2b2db-117">分支站点需要 survivable 电话连接 (例如，如果 WAN 向下) 。</span><span class="sxs-lookup"><span data-stu-id="2b2db-117">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="2b2db-118">应为每个分支站点分析此要求;某些分支可能需要冗余和故障转移，而其他分支可能不需要。</span><span class="sxs-lookup"><span data-stu-id="2b2db-118">This requirement should be analyzed for each branch site; some of your branches may require redundancy and failover, whereas others may not.</span></span>

  - <span data-ttu-id="2b2db-119">两个中央站点之间需要弹性。</span><span class="sxs-lookup"><span data-stu-id="2b2db-119">Resiliency is required between two central sites.</span></span> <span data-ttu-id="2b2db-120">您需要确保 SIP 中继在每个中央站点终止。</span><span class="sxs-lookup"><span data-stu-id="2b2db-120">You need to make sure that a SIP trunk terminates at each central site.</span></span> <span data-ttu-id="2b2db-121">例如，如果您有都柏林和 Tukwila 中心站点，并且两者都仅使用一个站点的 SIP 中继，则其他站点的用户不能发出 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="2b2db-121">For example, if you have Dublin and Tukwila central sites and both use only one site’s SIP trunk, if the trunk goes down, the other site’s users cannot make PSTN calls.</span></span>

  - <span data-ttu-id="2b2db-122">分支站点和中央站点位于不同的国家/地区。</span><span class="sxs-lookup"><span data-stu-id="2b2db-122">The branch site and central site are in different countries/regions.</span></span> <span data-ttu-id="2b2db-123">出于兼容性和合法性考虑，每个国家/地区至少需要一个 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="2b2db-123">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span> <span data-ttu-id="2b2db-124">例如，在欧盟，如果某个国家/地区的通信没有本地终止于中央点，则无法离开该国家/地区。</span><span class="sxs-lookup"><span data-stu-id="2b2db-124">For example, in the European Union, communications cannot leave a country/region without terminating locally at a centralized point.</span></span>

<span data-ttu-id="2b2db-125">根据网站的地理位置和您在企业中预期的流量，您可能不希望通过中心 SIP 中继路由所有用户，也可以选择通过分支站点的 SIP 中继路由某些用户。</span><span class="sxs-lookup"><span data-stu-id="2b2db-125">Depending on the geographical location of sites and how much traffic you anticipate within your enterprise, you may not want to route all users through the central SIP trunk, or you may opt to route some users through a SIP trunk at their branch site.</span></span> <span data-ttu-id="2b2db-126">为分析您的需求，请回答以下问题：</span><span class="sxs-lookup"><span data-stu-id="2b2db-126">To analyze your needs, answer the following questions:</span></span>

  - <span data-ttu-id="2b2db-127">每个网站的大小是多少 (也就是说，为企业语音) 启用了多少个用户？</span><span class="sxs-lookup"><span data-stu-id="2b2db-127">How big is each site (that is, how many users are enabled for Enterprise Voice)?</span></span>

  - <span data-ttu-id="2b2db-128">每个站点中哪个外线直拨分机 (DID) 号码收到的电话呼叫最多？</span><span class="sxs-lookup"><span data-stu-id="2b2db-128">Which direct inward dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="2b2db-129">确定部署集中 SIP 中继还是分布式 SIP 中继之前需要进行成本效益分析。</span><span class="sxs-lookup"><span data-stu-id="2b2db-129">The decision whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="2b2db-130">某些情况下，虽然并不是必需的，但选择分布式部署模型可能会比较有益。</span><span class="sxs-lookup"><span data-stu-id="2b2db-130">In some cases, it may be advantageous to opt for the distributed deployment model even if it is not required.</span></span> <span data-ttu-id="2b2db-131">在完全集中的部署中，所有分支站点流量都通过 WAN 链路进行路由。</span><span class="sxs-lookup"><span data-stu-id="2b2db-131">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="2b2db-132">如果您不想支付 WAN 链路所需的带宽费用，则可能需要使用分布式 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="2b2db-132">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span> <span data-ttu-id="2b2db-133">例如，您可能希望在与中心站点具有联合的分支站点上部署 Standard Edition 服务器，或者您可能想要使用小型网关部署 Survivable 分支设备或 Survivable 分支服务器。</span><span class="sxs-lookup"><span data-stu-id="2b2db-133">For example, you may want to deploy a Standard Edition server at a branch site with federation to the central site, or you may want to deploy a Survivable Branch Appliance or a Survivable Branch Server with a small gateway.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b2db-134">有关分布式 SIP 中继的详细信息，请参阅 <A href="lync-server-2013-branch-site-sip-trunking.md">Lync Server 2013 中的分支站点 SIP 中继</A>。</span><span class="sxs-lookup"><span data-stu-id="2b2db-134">For details about distributed SIP trunking, see <A href="lync-server-2013-branch-site-sip-trunking.md">Branch site SIP trunking in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="2b2db-135">支持的 SIP 中继连接类型</span><span class="sxs-lookup"><span data-stu-id="2b2db-135">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="2b2db-136">Lync Server 支持 SIP 中继的以下连接类型：</span><span class="sxs-lookup"><span data-stu-id="2b2db-136">Lync Server supports the following connection types for SIP trunking:</span></span>

  - <span data-ttu-id="2b2db-p109">多协议标签交换 (MPLS) 是一种专用网络，用于定向数据并将其从一个网络节点传送到下一个网络节点。MPLS 网络中的带宽可与其他订阅者共享，并为每个数据包分配一个标签以便区别每个订阅者的数据。这种连接类型无需使用虚拟专用网 (VPN)。潜在的缺点是过多的 IP 流量会干扰 VoIP 操作，除非为 VoIP 流量指定优先级。</span><span class="sxs-lookup"><span data-stu-id="2b2db-p109">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next. The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber’s data from another’s. This connection type does not require a virtual private network (VPN). A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

  - <span data-ttu-id="2b2db-p110">没有其他流量的专用连接（例如，租用的光纤连接或 T1 线路）通常是最安全可靠的连接类型。此连接类型提供最大的呼叫传送容量，但通常也是最昂贵的。无需使用 VPN。专用连接适用于具有大量呼叫或严格的安全和可用性要求的组织。</span><span class="sxs-lookup"><span data-stu-id="2b2db-p110">A private connection with no other traffic—for example, a leased fiber-optic connection or T1 line—is typically the most reliable and secure connection type. This connection type provides the highest call-carrying capacity, but it is typically the most expensive. VPN is not required. Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

  - <span data-ttu-id="2b2db-145">Internet 是成本最低的连接类型，但也是最不可靠的。</span><span class="sxs-lookup"><span data-stu-id="2b2db-145">The Internet is the least expensive connection type, but it is also the least reliable.</span></span> <span data-ttu-id="2b2db-146">Internet 连接是唯一需要 VPN 的 Lync Server SIP 中继连接类型。</span><span class="sxs-lookup"><span data-stu-id="2b2db-146">Internet connection is the only Lync Server SIP trunking connection type that requires VPN.</span></span>

<div>

## <a name="selecting-a-connection-type"></a><span data-ttu-id="2b2db-147">选择连接类型</span><span class="sxs-lookup"><span data-stu-id="2b2db-147">Selecting a Connection Type</span></span>

<span data-ttu-id="2b2db-148">最适用于企业的 SIP 中继连接类型取决于企业的需求和预算。</span><span class="sxs-lookup"><span data-stu-id="2b2db-148">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

  - <span data-ttu-id="2b2db-p112">对于大中型企业，MPLS 网络通常是最佳选择。它能提供必需的带宽，且费率比专用网络更低。</span><span class="sxs-lookup"><span data-stu-id="2b2db-p112">For a mid-size or larger enterprise, an MPLS network usually provides the greatest value. It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

  - <span data-ttu-id="2b2db-151">大型企业可能需要专用的光纤、T1、T3 或更高连接（在欧盟为 E1、E3 或更高）。</span><span class="sxs-lookup"><span data-stu-id="2b2db-151">Large enterprises may require a private fiber-optic, T1, T3 or higher connection (E1, E3 or higher in the European Union).</span></span>

  - <span data-ttu-id="2b2db-152">对于呼叫量较低的小型企业或分支站点，通过 Internet 的 SIP 中继可能是最佳选择。</span><span class="sxs-lookup"><span data-stu-id="2b2db-152">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="2b2db-153">建议大中型站点不要使用此连接类型。</span><span class="sxs-lookup"><span data-stu-id="2b2db-153">This connection type is not recommended for mid-size or larger sites.</span></span>

</div>

</div>

<div>

## <a name="bandwidth-requirements"></a><span data-ttu-id="2b2db-154">带宽要求</span><span class="sxs-lookup"><span data-stu-id="2b2db-154">Bandwidth Requirements</span></span>

<span data-ttu-id="2b2db-p114">实现所要求的带宽量取决于呼叫容量（必须能够支持的并发呼叫数）。需考虑到带宽可用性，以便能够充分利用购买的峰值容量。使用以下公式计算 SIP 中继峰值带宽的要求：</span><span class="sxs-lookup"><span data-stu-id="2b2db-p114">The amount of bandwidth your implementation requires depends on call capacity (the number of concurrent calls you must be able to support). You need to consider bandwidth availability, so that you can take full advantage of the peak capacity that you have paid for. Use the following formula to calculate SIP trunk peak bandwidth requirement:</span></span>

<span data-ttu-id="2b2db-158">SIP 中继峰值带宽 = 最大并发呼叫数 x（64 kbps + 标头大小）</span><span class="sxs-lookup"><span data-stu-id="2b2db-158">SIP Trunk Peak Bandwidth = Max Simultaneous Calls x (64 kbps + header size)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b2db-159">标头最大大小为 20 字节。</span><span class="sxs-lookup"><span data-stu-id="2b2db-159">Header size is 20 bytes maximum.</span></span>



</div>

</div>

<div>

## <a name="codec-support"></a><span data-ttu-id="2b2db-160">编解码器支持</span><span class="sxs-lookup"><span data-stu-id="2b2db-160">Codec Support</span></span>

<span data-ttu-id="2b2db-161">Lync Server 2013 仅支持以下编解码器：</span><span class="sxs-lookup"><span data-stu-id="2b2db-161">Lync Server 2013 supports only the following codecs:</span></span>

  - <span data-ttu-id="2b2db-162">G.711 a-law（主要在北美以外的国家/地区使用）</span><span class="sxs-lookup"><span data-stu-id="2b2db-162">G.711 a-law (used primarily outside North America)</span></span>

  - <span data-ttu-id="2b2db-163">G.711 µ-law（在北美使用）</span><span class="sxs-lookup"><span data-stu-id="2b2db-163">G.711 µ-law (used in North America)</span></span>

</div>

<div>

## <a name="internet-telephony-service-provider"></a><span data-ttu-id="2b2db-164">Internet 电话服务提供商</span><span class="sxs-lookup"><span data-stu-id="2b2db-164">Internet Telephony Service Provider</span></span>

<span data-ttu-id="2b2db-165">SIP 中继连接的服务提供商端的实现方式因 ITSP 而异。</span><span class="sxs-lookup"><span data-stu-id="2b2db-165">How you implement the service provider side of a SIP trunk connection varies from one ITSP to another.</span></span> <span data-ttu-id="2b2db-166">有关部署信息，请与服务提供商联系。</span><span class="sxs-lookup"><span data-stu-id="2b2db-166">For deployment information, contact your service provider.</span></span> <span data-ttu-id="2b2db-167">有关认证的 SIP 中继服务提供商的列表，请参阅 [Microsoft 统一通信开放式互操作性计划网站](https://go.microsoft.com/fwlink/?linkid=287029)。</span><span class="sxs-lookup"><span data-stu-id="2b2db-167">For a list of certified SIP trunking service providers, see [Microsoft Unified Communications Open Interoperability Program website](https://go.microsoft.com/fwlink/?linkid=287029).</span></span>

<span data-ttu-id="2b2db-168">有关 Microsoft 认证的 SIP 中继提供商的详细信息，请与 Microsoft 代表联系。</span><span class="sxs-lookup"><span data-stu-id="2b2db-168">For details about Microsoft certified SIP trunking providers, contact your Microsoft representative.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2b2db-p116">您必须使用 Microsoft 认证的服务提供商，才能确保 ITSP 支持遍历 SIP 中继的所有功能（例如，设置和管理会话以及支持所有扩展 VoIP 服务）。Microsoft 技术支持没有扩展到使用非认证提供商的配置。如果当前使用的是未认证 SIP 中继的 Internet 服务提供商，您可以选择继续使用该提供商作为您的 ISP，同时使用 Microsoft 认证的 SIP 中继提供商。</span><span class="sxs-lookup"><span data-stu-id="2b2db-p116">You must use a Microsoft certified service provider to ensure that your ITSP supports all of the functionality that traverses the SIP trunk (for example, setting up and managing sessions and supporting all of the extended VoIP services). Microsoft technical support does not extend to configurations that use noncertified providers. If you currently use an Internet service provider that is not certified for SIP trunking, you can opt to continue using that provider as your ISP and use a provider certified by Microsoft for SIP trunking.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

