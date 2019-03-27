---
title: Skype 业务服务器中的 SIP 中继
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
description: 了解有关在 Skype 的 SIP 中继的业务 Server 企业语音
ms.openlocfilehash: 98b107d02d223ea8bad555c5aa0802f8f7581807
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30892954"
---
# <a name="sip-trunking-in-skype-for-business-server"></a><span data-ttu-id="d939b-103">Skype 业务服务器中的 SIP 中继</span><span class="sxs-lookup"><span data-stu-id="d939b-103">SIP trunking in Skype for Business Server</span></span>

<span data-ttu-id="d939b-104">了解有关在 Skype 的 SIP 中继的业务 Server 企业语音</span><span class="sxs-lookup"><span data-stu-id="d939b-104">Learn about SIP trunking in Skype for Business Server Enterprise Voice</span></span>

<span data-ttu-id="d939b-105">会话初始协议 (SIP) 用于启动和管理基本电话服务和其他实时通信服务（例如即时消息、会议、状态检测和多媒体）的 IP 语音 (VoIP) 通信会话。</span><span class="sxs-lookup"><span data-stu-id="d939b-105">Session Initiation Protocol (SIP) is used to initiate and manage Voice over IP (VoIP) communications sessions for basic telephone service and for additional real-time communication services, such as instant messaging, conferencing, presence detection, and multimedia.</span></span> <span data-ttu-id="d939b-106">本节提供实现 SIP 中继（一种 SIP 连接，可以扩展到本地网络以外）的规划信息。</span><span class="sxs-lookup"><span data-stu-id="d939b-106">This section provides planning information for implementing SIP trunks, a type of SIP connection that extends beyond the boundary of your local network.</span></span>

## <a name="what-is-sip-trunking"></a><span data-ttu-id="d939b-107">什么是 SIP 中继？</span><span class="sxs-lookup"><span data-stu-id="d939b-107">What is SIP Trunking?</span></span>

<span data-ttu-id="d939b-108">SIP 中继是一种 IP 连接，在您的组织与防火墙以外的 Internet 电话服务提供商 (ITSP) 之间建立 SIP 通信链路。</span><span class="sxs-lookup"><span data-stu-id="d939b-108">A SIP trunk is an IP connection that establishes a SIP communications link between your organization and an Internet telephony service provider (ITSP) beyond your firewall.</span></span> <span data-ttu-id="d939b-109">通常，SIP 中继用于连接到 ITSP 的组织的中央站点。</span><span class="sxs-lookup"><span data-stu-id="d939b-109">Typically, a SIP trunk is used to connect your organization's central site to an ITSP.</span></span> <span data-ttu-id="d939b-110">在某些情况中，您也可以选择使用 SIP 中继将分支站点连接到 ITSP。</span><span class="sxs-lookup"><span data-stu-id="d939b-110">In some cases, you may also opt to use SIP trunking to connect your branch site to an ITSP.</span></span>

<span data-ttu-id="d939b-111">部署 SIP 中继可以 big 步简化您的组织的电信和准备实时通信的最新增强功能。</span><span class="sxs-lookup"><span data-stu-id="d939b-111">Deploying SIP trunking can be a big step toward simplifying your organization's telecommunications and preparing for up-to-date enhancements to real-time communications.</span></span> <span data-ttu-id="d939b-112">SIP 中继的主要优势之一是您可以整合贵组织的连接到公用电话交换网 (PSTN) 在中央站点，而不是其前置任务，时间部门多路复用 (TDM) 中继，这通常需要从每个分支站点的单独中继。</span><span class="sxs-lookup"><span data-stu-id="d939b-112">One of the primary advantages of SIP trunking is that you can consolidate your organization's connections to the public switched telephone network (PSTN) at a central site, as opposed to its predecessor, time division multiplexing (TDM) trunking, which typically requires a separate trunk from each branch site.</span></span>

### <a name="cost-savings"></a><span data-ttu-id="d939b-113">节省成本</span><span class="sxs-lookup"><span data-stu-id="d939b-113">Cost Savings</span></span>

<span data-ttu-id="d939b-114">可以大大节省与 SIP 中继有关的成本：</span><span class="sxs-lookup"><span data-stu-id="d939b-114">The cost savings associated with SIP trunking can be substantial:</span></span>

- <span data-ttu-id="d939b-115">通过 SIP 中继拨打长途电话通常可以大幅降低成本。</span><span class="sxs-lookup"><span data-stu-id="d939b-115">Long distance calls typically cost much less through a SIP trunk.</span></span>

- <span data-ttu-id="d939b-116">可以节省可管理性成本并降低部署的复杂性。</span><span class="sxs-lookup"><span data-stu-id="d939b-116">You can cut manageability costs and reduce the complexity of deployment.</span></span>

- <span data-ttu-id="d939b-p104">如果可以以极低的成本将 SIP 中继直接连接到 ITSP，则可以消除基本速率接口 (BRI) 和主速率接口 (PRI) 的费用。在 TDM 中继中，服务提供商按分钟对呼叫计费。SIP 中继的成本可能基于带宽使用，能够以更小、更经济的增量购买带宽。（实际成本取决于选择的 ITSP 的服务模型。）</span><span class="sxs-lookup"><span data-stu-id="d939b-p104">Basic rate interface (BRI) and primary rate interface (PRI) fees can be eliminated if you connect a SIP trunk directly to your ITSP at significantly lower cost. In TDM trunking, service providers charge for calls by the minute. The cost of SIP trunking may be based on bandwidth usage, which you can buy in smaller, more economical increments. (The actual cost depends on the service model of the ITSP you choose.)</span></span>

#### <a name="sip-trunking-vs-hosting-a-pstn-gateway-or-ip-pbx"></a><span data-ttu-id="d939b-121">SIP 中继与承载 PSTN 网关或 IP-PBX</span><span class="sxs-lookup"><span data-stu-id="d939b-121">SIP Trunking vs. Hosting a PSTN Gateway or IP-PBX</span></span>

<span data-ttu-id="d939b-p105">由于 SIP 中继直接连接到服务提供商，因此可以消除 PSTN 网关及其管理成本和复杂性。使用 SIP 中继可以减少维护和管理工作，从而大幅节省成本。</span><span class="sxs-lookup"><span data-stu-id="d939b-p105">Because SIP trunks connect directly to your service provider, you can eliminate your PSTN gateways and their management cost and complexity. Using a SIP trunk can lead to substantial cost savings through reduced maintenance and administration.</span></span>

### <a name="expanded-voip-services"></a><span data-ttu-id="d939b-124">扩展的 VoIP 服务</span><span class="sxs-lookup"><span data-stu-id="d939b-124">Expanded VoIP Services</span></span>

<span data-ttu-id="d939b-125">语音功能通常是部署 SIP 中继的主要动机，但是语音支持只是第一步。</span><span class="sxs-lookup"><span data-stu-id="d939b-125">Voice features are often the primary motivation for deploying SIP trunking, but voice support is just the first step.</span></span> <span data-ttu-id="d939b-126">与 SIP 中继，您可以扩展的 VoIP 功能，并启用 Skype 业务服务器提供丰富的服务。</span><span class="sxs-lookup"><span data-stu-id="d939b-126">With SIP trunking, you can extend VoIP capabilities and enable Skype for Business Server to deliver a richer set of services.</span></span> <span data-ttu-id="d939b-127">例如：</span><span class="sxs-lookup"><span data-stu-id="d939b-127">For example:</span></span>

- <span data-ttu-id="d939b-128">业务服务器未运行 Skype 的设备的增强的状态检测可以更好地与移动电话，您可以查看用户移动电话通话时启用集成。</span><span class="sxs-lookup"><span data-stu-id="d939b-128">Enhanced presence detection for devices that are not running Skype for Business Server can provide better integration with mobile phones, enabling you to see when a user is on a mobile phone call.</span></span>

- <span data-ttu-id="d939b-129">E9-1-1 紧急呼叫，应答 911 呼叫，以确定从他/她的电话号码的呼叫者的位置的机构。</span><span class="sxs-lookup"><span data-stu-id="d939b-129">E9-1-1 emergency calling enables the authorities who answer 911 calls to determine the caller's location from his or her telephone number.</span></span>

> [!NOTE]
> <span data-ttu-id="d939b-130">与 ITSP 联系以获取他们支持并且可以为贵组织启用的服务列表。</span><span class="sxs-lookup"><span data-stu-id="d939b-130">Contact your ITSP for a list of services that they support and can enable for your organization.</span></span>

### <a name="sip-trunks-vs-direct-sip-connections"></a><span data-ttu-id="d939b-131">SIP 中继与直接 SIP 连接</span><span class="sxs-lookup"><span data-stu-id="d939b-131">SIP Trunks vs. Direct SIP Connections</span></span>

<span data-ttu-id="d939b-132">术语中继源自电路交换技术。</span><span class="sxs-lookup"><span data-stu-id="d939b-132">The term trunk is derived from circuit-switched technology.</span></span> <span data-ttu-id="d939b-133">它指的是连接电话交换设备的专用物理线路。</span><span class="sxs-lookup"><span data-stu-id="d939b-133">It refers to a dedicated physical line that connects telephone switching equipment.</span></span> <span data-ttu-id="d939b-134">其前置任务，时分多路复用 (TDM) 中继，如 SIP 中继的两个单独的 SIP 网络之间的连接 — Business Server enterprise Skype 和 ITSP。</span><span class="sxs-lookup"><span data-stu-id="d939b-134">Like their predecessor, time division multiplexing (TDM) trunks, SIP trunks are connections between two separate SIP networks—the Skype for Business Server enterprise and the ITSP.</span></span> <span data-ttu-id="d939b-135">SIP 中继是可以通过任何支持的 SIP 中继连接类型建立的虚拟连接，这一点与电路交换中继不同。</span><span class="sxs-lookup"><span data-stu-id="d939b-135">Unlike circuit-switched trunks, SIP trunks are virtual connections that can be established over any of the supported SIP trunking connection types.</span></span>

<span data-ttu-id="d939b-136">而直接 SIP 连接指的是不能跨越本地网络边界的 SIP 连接（也就是说，它们连接到内部网络内的公用电话交换网 (PSTN) 网关或专用交换机 (PBX)）。</span><span class="sxs-lookup"><span data-stu-id="d939b-136">Direct SIP connections, on the other hand, are SIP connections that do not cross the local network boundary (that is, they connect to a public switched telephone network (PSTN) gateway or private branch exchange (PBX) within your internal network).</span></span> <span data-ttu-id="d939b-137">有关如何使用直接 SIP 连接使用 Skype 业务服务器的详细信息，请参阅[中的业务服务器 Skype 的直接 SIP 连接](direct-sip.md)。</span><span class="sxs-lookup"><span data-stu-id="d939b-137">For details about how you can use direct SIP connections with Skype for Business Server, see [Direct SIP connections in Skype for Business Server](direct-sip.md).</span></span>

## <a name="how-do-i-implement-sip-trunking"></a><span data-ttu-id="d939b-138">如何实施 SIP 中继？</span><span class="sxs-lookup"><span data-stu-id="d939b-138">How do I implement SIP Trunking?</span></span>

<span data-ttu-id="d939b-139">若要实现 SIP 中继，您必须路由通过中介服务器，充当业务 Server 客户端的 Skype 的服务提供商和必要媒体，必要时之间的通信会话代理服务器的连接。</span><span class="sxs-lookup"><span data-stu-id="d939b-139">To implement SIP trunking, you must route the connection through a Mediation Server, which acts as a proxy for communications sessions between Skype for Business Server clients and the service provider and transcodes media, when necessary.</span></span>

<span data-ttu-id="d939b-140">每台中介服务器具有一个内部网络接口和外部网络接口。</span><span class="sxs-lookup"><span data-stu-id="d939b-140">Each Mediation Server has an internal network interface and an external network interface.</span></span> <span data-ttu-id="d939b-141">内部接口连接到前端服务器。</span><span class="sxs-lookup"><span data-stu-id="d939b-141">The internal interface connects to the Front End Servers.</span></span> <span data-ttu-id="d939b-142">因为它通常用于连接到公用电话交换网 (pstn) 网关或 IP PBX 的中介服务器的外部接口通常称为网关接口。</span><span class="sxs-lookup"><span data-stu-id="d939b-142">The external interface is commonly called the gateway interface because it has traditionally been used to connect the Mediation Server to a public switched telephone network (PSTN) gateway or an IP-PBX.</span></span> <span data-ttu-id="d939b-143">若要实现 SIP 中继，则中介服务器的外部接口连接到 ITSP 的外部边缘组件。</span><span class="sxs-lookup"><span data-stu-id="d939b-143">To implement a SIP trunk, you connect the external interface of the Mediation Server to the external edge component of the ITSP.</span></span> <span data-ttu-id="d939b-144">ITSP 的外部边缘组件可以是会话边界控制器 (SBC)、路由器或网关。</span><span class="sxs-lookup"><span data-stu-id="d939b-144">The external edge component of the ITSP could be a Session Border Controller (SBC), a router, or a gateway.</span></span>

<span data-ttu-id="d939b-145">有关中介服务器的详细信息，请参阅[Skype 业务服务器中的中介服务器组件](mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="d939b-145">For details about Mediation Servers, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>

### <a name="centralized-vs-distributed-sip-trunking"></a><span data-ttu-id="d939b-146">集中 SIP 中继和分布式 SIP 中继</span><span class="sxs-lookup"><span data-stu-id="d939b-146">Centralized vs. Distributed SIP Trunking</span></span>

<span data-ttu-id="d939b-147">集中的 SIP 中继路由所有 VoIP 流量，包括分支站点流量，通过在中央站点。</span><span class="sxs-lookup"><span data-stu-id="d939b-147">Centralized SIP trunking routes all VoIP traffic, including branch site traffic, through your central site.</span></span> <span data-ttu-id="d939b-148">集中的部署模型简单、 经济高效，并且通常是推荐用于实现业务服务器的 SIP 中继与 Skype 的方法。</span><span class="sxs-lookup"><span data-stu-id="d939b-148">The centralized deployment model is simple, cost-effective, and is generally the recommended approach for implementing SIP trunks with Skype for Business Server.</span></span>

<span data-ttu-id="d939b-149">分布式的 SIP 中继是您在其中实现在一个或多个分支站点的本地 SIP 中继的部署模型。</span><span class="sxs-lookup"><span data-stu-id="d939b-149">Distributed SIP trunking is a deployment model in which you implement local SIP trunks at one or more branch sites.</span></span> <span data-ttu-id="d939b-150">VoIP 流量是然后从分支站点直接路由到的服务提供商而不经由中央站点。</span><span class="sxs-lookup"><span data-stu-id="d939b-150">VoIP traffic is then routed from the branch site directly to a service provider without going through the central site.</span></span>

<span data-ttu-id="d939b-151">仅在出现以下情况时才需要使用分布式 SIP 中继：</span><span class="sxs-lookup"><span data-stu-id="d939b-151">Distributed SIP trunking is required only in the following cases:</span></span>

- <span data-ttu-id="d939b-152">分支站点需要 survivable 电话连接 （例如，如果 WAN 不可用）。</span><span class="sxs-lookup"><span data-stu-id="d939b-152">The branch site requires survivable phone connectivity (for example, if the WAN goes down).</span></span> <span data-ttu-id="d939b-153">应为每个分支站点; 分析这一要求分支的一些可能需要冗余和故障转移，而其他用户可能不。</span><span class="sxs-lookup"><span data-stu-id="d939b-153">This requirement should be analyzed for each branch site; some of your branches may require redundancy and failover, whereas others may not.</span></span>

- <span data-ttu-id="d939b-154">恢复能力，则需要两个中央站点之间。</span><span class="sxs-lookup"><span data-stu-id="d939b-154">Resiliency is required between two central sites.</span></span> <span data-ttu-id="d939b-155">您需要确保 SIP 中继终止每个中央站点上。</span><span class="sxs-lookup"><span data-stu-id="d939b-155">You need to make sure that a SIP trunk terminates at each central site.</span></span> <span data-ttu-id="d939b-156">例如，如果您具有都柏林和 Tukwila 中央站点，并同时使用只有一个站点 SIP 中继，如果中继不可用，其他站点的用户无法进行 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="d939b-156">For example, if you have Dublin and Tukwila central sites and both use only one site's SIP trunk, if the trunk goes down, the other site's users cannot make PSTN calls.</span></span>

- <span data-ttu-id="d939b-157">分支站点和中央站点是在不同的国家/地区。</span><span class="sxs-lookup"><span data-stu-id="d939b-157">The branch site and central site are in different countries/regions.</span></span> <span data-ttu-id="d939b-158">出于兼容性和合法性考虑，每个国家/地区至少需要一个 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="d939b-158">For compatibility and legal reasons, you need at least one SIP trunk per country/region.</span></span> <span data-ttu-id="d939b-159">例如，在欧盟，如果某个国家/地区的通信没有本地终止于中央点，则无法离开该国家/地区。</span><span class="sxs-lookup"><span data-stu-id="d939b-159">For example, in the European Union, communications cannot leave a country/region without terminating locally at a centralized point.</span></span>

<span data-ttu-id="d939b-160">根据地理位置的网站和在企业内预计多少通信您可能不希望路由所有用户通过管理中心的 SIP 中继，或您可以选择将一些用户通过 SIP 中继都路由其分支站点。</span><span class="sxs-lookup"><span data-stu-id="d939b-160">Depending on the geographical location of sites and how much traffic you anticipate within your enterprise, you may not want to route all users through the central SIP trunk, or you may opt to route some users through a SIP trunk at their branch site.</span></span> <span data-ttu-id="d939b-161">为分析您的需求，请回答以下问题：</span><span class="sxs-lookup"><span data-stu-id="d939b-161">To analyze your needs, answer the following questions:</span></span>

- <span data-ttu-id="d939b-162">（即，多少用户启用企业语音） 每个站点有多大？</span><span class="sxs-lookup"><span data-stu-id="d939b-162">How big is each site (that is, how many users are enabled for Enterprise Voice)?</span></span>

- <span data-ttu-id="d939b-163">每个站点中哪个外线直拨分机 (DID) 号码收到的电话呼叫最多？</span><span class="sxs-lookup"><span data-stu-id="d939b-163">Which direct inward dialing (DID) numbers at each site get the most phone calls?</span></span>

<span data-ttu-id="d939b-164">确定部署集中 SIP 中继还是分布式 SIP 中继之前需要进行成本效益分析。</span><span class="sxs-lookup"><span data-stu-id="d939b-164">The decision whether to deploy centralized or distributed SIP trunking requires a cost-benefit analysis.</span></span> <span data-ttu-id="d939b-165">某些情况下，虽然并不是必需的，但选择分布式部署模型可能会比较有益。</span><span class="sxs-lookup"><span data-stu-id="d939b-165">In some cases, it may be advantageous to opt for the distributed deployment model even if it is not required.</span></span> <span data-ttu-id="d939b-166">在完全集中部署中，通过 WAN 链接路由所有分支站点流量。</span><span class="sxs-lookup"><span data-stu-id="d939b-166">In a completely centralized deployment, all branch site traffic is routed over WAN links.</span></span> <span data-ttu-id="d939b-167">如果您不想支付 WAN 链路所需的带宽费用，则可能需要使用分布式 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="d939b-167">Instead of paying for the bandwidth required for WAN linking, you may want to use distributed SIP trunking.</span></span> <span data-ttu-id="d939b-168">例如，您可能想要将在分支站点使用联盟 Standard Edition server 部署到中心网站，或要部署 Survivable Branch Appliance 或 Survivable Branch Server 的小型网关。</span><span class="sxs-lookup"><span data-stu-id="d939b-168">For example, you may want to deploy a Standard Edition server at a branch site with federation to the central site, or you may want to deploy a Survivable Branch Appliance or a Survivable Branch Server with a small gateway.</span></span>

> [!NOTE]
> <span data-ttu-id="d939b-169">有关分布式 SIP 中继的详细信息，请参阅[Skype 业务服务器中的分支站点 SIP 中继](branch-site.md)。</span><span class="sxs-lookup"><span data-stu-id="d939b-169">For details about distributed SIP trunking, see [Branch site SIP trunking in Skype for Business Server](branch-site.md).</span></span>

### <a name="supported-sip-trunking-connection-types"></a><span data-ttu-id="d939b-170">支持的 SIP 中继连接类型</span><span class="sxs-lookup"><span data-stu-id="d939b-170">Supported SIP Trunking Connection Types</span></span>

<span data-ttu-id="d939b-171">Skype 业务服务器的 SIP 中继支持以下连接类型：</span><span class="sxs-lookup"><span data-stu-id="d939b-171">Skype for Business Server supports the following connection types for SIP trunking:</span></span>

- <span data-ttu-id="d939b-172">多协议标签交换 (MPLS) 是一种专用网络，用于定向数据并将其从一个网络节点传送到下一个网络节点。</span><span class="sxs-lookup"><span data-stu-id="d939b-172">Multiprotocol Label Switching (MPLS) is a private network that directs and carries data from one network node to the next.</span></span> <span data-ttu-id="d939b-173">MPLS 网络中的带宽为共享其他订阅者，并且每个数据包分配一个订阅者的数据分开其他人的标签。</span><span class="sxs-lookup"><span data-stu-id="d939b-173">The bandwidth in an MPLS network is shared with other subscribers, and each data packet is assigned a label to distinguish one subscriber's data from another's.</span></span> <span data-ttu-id="d939b-174">这种连接类型无需使用虚拟专用网 (VPN)。</span><span class="sxs-lookup"><span data-stu-id="d939b-174">This connection type does not require a virtual private network (VPN).</span></span> <span data-ttu-id="d939b-175">潜在的缺点是过多的 IP 流量会干扰 VoIP 操作，除非为 VoIP 流量指定优先级。</span><span class="sxs-lookup"><span data-stu-id="d939b-175">A potential drawback is that excessive IP traffic can interfere with VoIP operation unless VoIP traffic is given priority.</span></span>

- <span data-ttu-id="d939b-p118">没有其他流量的专用连接（例如，租用的光纤连接或 T1 线路）通常是最安全可靠的连接类型。此连接类型提供最大的呼叫传送容量，但通常也是最昂贵的。无需使用 VPN。专用连接适用于具有大量呼叫或严格的安全和可用性要求的组织。</span><span class="sxs-lookup"><span data-stu-id="d939b-p118">A private connection with no other traffic—for example, a leased fiber-optic connection or T1 line—is typically the most reliable and secure connection type. This connection type provides the highest call-carrying capacity, but it is typically the most expensive. VPN is not required. Private connections are appropriate for organizations with high call volumes or stringent security and availability requirements.</span></span>

- <span data-ttu-id="d939b-180">Internet 是成本最低的连接类型，但也是最不可靠的。</span><span class="sxs-lookup"><span data-stu-id="d939b-180">The Internet is the least expensive connection type, but it is also the least reliable.</span></span> <span data-ttu-id="d939b-181">Internet 连接的唯一 Skype 业务服务器 SIP 中继连接类型所需 VPN。</span><span class="sxs-lookup"><span data-stu-id="d939b-181">Internet connection is the only Skype for Business Server SIP trunking connection type that requires VPN.</span></span>

#### <a name="selecting-a-connection-type"></a><span data-ttu-id="d939b-182">选择连接类型</span><span class="sxs-lookup"><span data-stu-id="d939b-182">Selecting a Connection Type</span></span>

<span data-ttu-id="d939b-183">最适用于企业的 SIP 中继连接类型取决于企业的需求和预算。</span><span class="sxs-lookup"><span data-stu-id="d939b-183">The most appropriate SIP trunking connection type for your enterprise depends on your needs and your budget.</span></span>

- <span data-ttu-id="d939b-p120">对于大中型企业，MPLS 网络通常是最佳选择。它能提供必需的带宽，且费率比专用网络更低。</span><span class="sxs-lookup"><span data-stu-id="d939b-p120">For a mid-size or larger enterprise, an MPLS network usually provides the greatest value. It can provide the necessary bandwidth at a cheaper rate than a specialized private network.</span></span>

- <span data-ttu-id="d939b-186">大型企业可能需要专用的光纤、T1、T3 或更高连接（在欧盟为 E1、E3 或更高）。</span><span class="sxs-lookup"><span data-stu-id="d939b-186">Large enterprises may require a private fiber-optic, T1, T3 or higher connection (E1, E3 or higher in the European Union).</span></span>

- <span data-ttu-id="d939b-187">对于小型企业或使用较低的呼叫量的分支站点，通过 Internet 的 SIP 中继可能是最佳选择。</span><span class="sxs-lookup"><span data-stu-id="d939b-187">For a small enterprise or branch site with low call volume, SIP trunking through the Internet may be the best choice.</span></span> <span data-ttu-id="d939b-188">建议大中型站点不要使用此连接类型。</span><span class="sxs-lookup"><span data-stu-id="d939b-188">This connection type is not recommended for mid-size or larger sites.</span></span>

### <a name="bandwidth-requirements"></a><span data-ttu-id="d939b-189">带宽要求</span><span class="sxs-lookup"><span data-stu-id="d939b-189">Bandwidth Requirements</span></span>

<span data-ttu-id="d939b-p122">实现所要求的带宽量取决于呼叫容量（必须能够支持的并发呼叫数）。需考虑到带宽可用性，以便能够充分利用购买的峰值容量。使用以下公式计算 SIP 中继峰值带宽的要求：</span><span class="sxs-lookup"><span data-stu-id="d939b-p122">The amount of bandwidth your implementation requires depends on call capacity (the number of concurrent calls you must be able to support). You need to consider bandwidth availability, so that you can take full advantage of the peak capacity that you have paid for. Use the following formula to calculate SIP trunk peak bandwidth requirement:</span></span>

<span data-ttu-id="d939b-193">SIP 中继峰值带宽 = 最大并发呼叫数 x（64 kbps + 标头大小）</span><span class="sxs-lookup"><span data-stu-id="d939b-193">SIP Trunk Peak Bandwidth = Max Simultaneous Calls x (64 kbps + header size)</span></span>

> [!NOTE]
> <span data-ttu-id="d939b-194">标头最大大小为 20 字节。</span><span class="sxs-lookup"><span data-stu-id="d939b-194">Header size is 20 bytes maximum.</span></span>

### <a name="codec-support"></a><span data-ttu-id="d939b-195">编解码器支持</span><span class="sxs-lookup"><span data-stu-id="d939b-195">Codec Support</span></span>

<span data-ttu-id="d939b-196">Skype 业务服务器仅支持以下编解码器：</span><span class="sxs-lookup"><span data-stu-id="d939b-196">Skype for Business Server supports only the following codecs:</span></span>

- <span data-ttu-id="d939b-197">G.711 a-law（主要在北美以外的国家/地区使用）</span><span class="sxs-lookup"><span data-stu-id="d939b-197">G.711 a-law (used primarily outside North America)</span></span>

- <span data-ttu-id="d939b-198">G.711 μ-law（在北美使用）</span><span class="sxs-lookup"><span data-stu-id="d939b-198">G.711 µ-law (used in North America)</span></span>

### <a name="internet-telephony-service-provider"></a><span data-ttu-id="d939b-199">Internet 电话服务提供商</span><span class="sxs-lookup"><span data-stu-id="d939b-199">Internet Telephony Service Provider</span></span>

<span data-ttu-id="d939b-200">SIP 中继连接的服务提供商端的实现方式因 ITSP 而异。</span><span class="sxs-lookup"><span data-stu-id="d939b-200">How you implement the service provider side of a SIP trunk connection varies from one ITSP to another.</span></span> <span data-ttu-id="d939b-201">有关部署信息，请与服务提供商联系。</span><span class="sxs-lookup"><span data-stu-id="d939b-201">For deployment information, contact your service provider.</span></span> <span data-ttu-id="d939b-202">有关认证的 SIP 中继服务提供商的列表，请参阅[Microsoft 统一通信开放互操作性计划网站](https://go.microsoft.com/fwlink/p/?LinkId=287029)。</span><span class="sxs-lookup"><span data-stu-id="d939b-202">For a list of certified SIP trunking service providers, see [Microsoft Unified Communications Open Interoperability Program website](https://go.microsoft.com/fwlink/p/?LinkId=287029).</span></span>

<span data-ttu-id="d939b-203">有关 Microsoft 认证的 SIP 中继提供商的详细信息，请与 Microsoft 代表联系。</span><span class="sxs-lookup"><span data-stu-id="d939b-203">For details about Microsoft certified SIP trunking providers, contact your Microsoft representative.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d939b-p124">您必须使用 Microsoft 认证的服务提供商，才能确保 ITSP 支持遍历 SIP 中继的所有功能（例如，设置和管理会话以及支持所有扩展 VoIP 服务）。Microsoft 技术支持没有扩展到使用非认证提供商的配置。如果当前使用的是未认证 SIP 中继的 Internet 服务提供商，您可以选择继续使用该提供商作为您的 ISP，同时使用 Microsoft 认证的 SIP 中继提供商。</span><span class="sxs-lookup"><span data-stu-id="d939b-p124">You must use a Microsoft certified service provider to ensure that your ITSP supports all of the functionality that traverses the SIP trunk (for example, setting up and managing sessions and supporting all of the extended VoIP services). Microsoft technical support does not extend to configurations that use noncertified providers. If you currently use an Internet service provider that is not certified for SIP trunking, you can opt to continue using that provider as your ISP and use a provider certified by Microsoft for SIP trunking.</span></span>

### <a name="topologies-and-components-for-sip-trunking"></a><span data-ttu-id="d939b-207">用于 SIP 中继的拓扑和组件</span><span class="sxs-lookup"><span data-stu-id="d939b-207">Topologies and Components for SIP Trunking</span></span>

<span data-ttu-id="d939b-208">下图描绘业务服务器中 Skype 的 SIP 中继拓扑。</span><span class="sxs-lookup"><span data-stu-id="d939b-208">The following figure depicts the SIP trunking topology in Skype for Business Server.</span></span>

<span data-ttu-id="d939b-209">**SIP 中继拓扑**</span><span class="sxs-lookup"><span data-stu-id="d939b-209">**SIP trunking topology**</span></span>

![SIP 中继拓扑](../../media/669fb55d-7c81-4e21-9421-fabc43d6e064.jpg)

<span data-ttu-id="d939b-p125">如图所示，企业网络与公用电话交换网 (PSTN) 服务提供商之间的连接使用 IP 虚拟专用网络 (VPN)。这个专用网络旨在提供 IP 连接、增强安全性和（可选的）获取服务质量 (QoS) 保证。由于 VPN 的特性，您无需为 SIP 信号流量使用传输层安全性 (TLS)，也无需为媒体流量使用安全实时传输协议 (SRTP)。因此，企业与服务提供商之间的连接由用于 SIP 的普通 TCP 连接以及用于通过 IP VPN 进行隧道传输的媒体的普通实时传输协议 (RTP)（通过 UDP）构成。确保 VPN 路由器之间的所有防火墙打开端口以允许 VPN 路由器进行通信，并且 VPN 路由器外部边缘上的 IP 地址公共可路由。</span><span class="sxs-lookup"><span data-stu-id="d939b-p125">As shown in the diagram, an IP virtual private network (VPN) is used for connectivity between the enterprise network and the public switched telephone network (PSTN) service provider. The purpose of this private network is to provide IP connectivity, enhance security, and (optionally) obtain Quality of Service (QoS) guarantees. Because of the nature of a VPN, you do not need to use Transport Layer Security (TLS) for SIP signaling traffic or secure real-time transport protocol (SRTP) for the media traffic. Connections between the enterprise and the service provider therefore consist of plain TCP connections for SIP and plain real-time transport protocol (RTP) (over UDP) for media tunneled through an IP VPN. Ensure that all firewalls between the VPN routers have ports open to allow the VPN routers to communicate, and that the IP addresses on the external edges of the VPN routers are publicly routable.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="d939b-216">请与服务提供商联系，以确定是否提供包括故障转移在内的高可用性支持。</span><span class="sxs-lookup"><span data-stu-id="d939b-216">Contact your service provider to determine whether it provides support for high availability, including failover.</span></span> <span data-ttu-id="d939b-217">如果提供，则需要确定设置过程。</span><span class="sxs-lookup"><span data-stu-id="d939b-217">If so, you will need to determine the procedures for setting it up.</span></span> <span data-ttu-id="d939b-218">例如，您需要在每个中介服务器上，配置只有一个 IP 地址和一个 SIP 中继或是否需要在每台中介服务器上配置多个 SIP 中继？</span><span class="sxs-lookup"><span data-stu-id="d939b-218">For example, do you need to configure only one IP address and one SIP trunk on each Mediation Server, or do you need to configure multiple SIP trunks on each Mediation Server?</span></span> <span data-ttu-id="d939b-219">如果您有多个中央站点，> 还可以询问服务提供商是否有能力启用与另一个中央站点的连接。</span><span class="sxs-lookup"><span data-stu-id="d939b-219">> If you have multiple central sites, also ask whether the service provider has the ability to enable connections to and from another central site.</span></span>

> [!NOTE]
> <span data-ttu-id="d939b-220">SIP 中继，我们强烈建议您部署独立的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="d939b-220">For SIP trunking, we strongly recommend that you deploy stand-alone Mediation Servers.</span></span> <span data-ttu-id="d939b-221">有关详细信息，请参阅部署文档中的 [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d939b-221">For details, see [Deploying Mediation Servers and Defining Peers](https://technet.microsoft.com/library/a684f1da-6671-4011-adf6-2db49e2528e2.aspx) in the Deployment documentation.</span></span>

### <a name="securing-the-mediation-server-for-sip-trunking"></a><span data-ttu-id="d939b-222">为 SIP 中继保护中介服务器的安全</span><span class="sxs-lookup"><span data-stu-id="d939b-222">Securing the Mediation Server for SIP Trunking</span></span>

<span data-ttu-id="d939b-p128">为安全起见，应为两个 VPN 路由器之间的每个连接设置一个虚拟 LAN (VLAN)。设置 VLAN 的实际过程因路由器制造商而异。请与路由器供应商联系以获取详细信息。</span><span class="sxs-lookup"><span data-stu-id="d939b-p128">For security purposes, you should set up a virtual LAN (VLAN) for each connection between the two VPN routers. The actual process for setting up a VLAN varies from one router manufacturer to another. For details, contact your router vendor.</span></span>

<span data-ttu-id="d939b-226">建议您遵循下列准则：</span><span class="sxs-lookup"><span data-stu-id="d939b-226">We recommend that you follow these guidelines:</span></span>

- <span data-ttu-id="d939b-227">设置 up 虚拟 LAN (VLAN) 之间中介服务器和 VPN 路由器外围网络 （也称为 DMZ、 非军事区和屏蔽子网） 中。</span><span class="sxs-lookup"><span data-stu-id="d939b-227">Set up a virtual LAN (VLAN) between the Mediation Server and the VPN router in the perimeter network (also known as DMZ, demilitarized zone, and screened subnet).</span></span>

- <span data-ttu-id="d939b-228">不允许将广播数据包或多播数据包从路由器传输到 VLAN。</span><span class="sxs-lookup"><span data-stu-id="d939b-228">Do not allow broadcast or multicast packets to be transferred from the router to the VLAN.</span></span>

- <span data-ttu-id="d939b-229">阻止所有将流量从路由器到 anywhere 路由的路由规则但中介服务器。</span><span class="sxs-lookup"><span data-stu-id="d939b-229">Block any routing rules that route traffic from the router to anywhere but the Mediation Server.</span></span>

<span data-ttu-id="d939b-230">如果使用 VPN 服务器，建议您遵循下列准则：</span><span class="sxs-lookup"><span data-stu-id="d939b-230">If you use a VPN server, we recommend that you follow these guidelines:</span></span>

- <span data-ttu-id="d939b-231">设置 VPN 服务器和中介服务器之间的 VLAN。</span><span class="sxs-lookup"><span data-stu-id="d939b-231">Set up a VLAN between the VPN server and the Mediation Server.</span></span>

- <span data-ttu-id="d939b-232">不允许将广播数据包或多播数据包从 VPN 服务器传输到 VLAN。</span><span class="sxs-lookup"><span data-stu-id="d939b-232">Do not allow broadcast or multicast packets to be transmitted from the VPN server to the VLAN.</span></span>

- <span data-ttu-id="d939b-233">阻止所有将 VPN 服务器流量路由到任何位置的路由规则但中介服务器。</span><span class="sxs-lookup"><span data-stu-id="d939b-233">Block any routing rule that routes VPN server traffic to anywhere but the Mediation Server.</span></span>

- <span data-ttu-id="d939b-234">使用基本路由封装 (GRE) 加密 VPN 上的数据。</span><span class="sxs-lookup"><span data-stu-id="d939b-234">Encrypt data on the VPN by using generic routing encapsulation (GRE).</span></span>

## <a name="see-also"></a><span data-ttu-id="d939b-235">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d939b-235">See also</span></span>

[<span data-ttu-id="d939b-236">Skype 业务服务器中的分支站点 SIP 中继</span><span class="sxs-lookup"><span data-stu-id="d939b-236">Branch site SIP trunking in Skype for Business Server</span></span>](branch-site.md)

