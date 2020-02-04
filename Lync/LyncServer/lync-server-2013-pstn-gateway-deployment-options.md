---
title: Lync Server 2013：PSTN 网关部署选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5b2f3cd153a6dc8d101f44a3f087f0ccedfa9bf7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a><span data-ttu-id="cbc0f-102">Lync Server 2013 中的 PSTN 网关部署选项</span><span class="sxs-lookup"><span data-stu-id="cbc0f-102">PSTN gateway deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cbc0f-103">_**主题上次修改时间：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="cbc0f-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>

## <a name="pstn-gateways"></a><span data-ttu-id="cbc0f-104">PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="cbc0f-104">PSTN Gateways</span></span>

<span data-ttu-id="cbc0f-105">公共交换式电话网络（PSTN）网关是第三方硬件组件，可直接或通过连接到 SIP 中继在企业语音基础结构和 PSTN 之间转换信号和媒体。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-105">Public switched telephone network (PSTN) gateways are third-party hardware components that translate signaling and media between the Enterprise Voice infrastructure and the PSTN, either directly or through connection to SIP trunks.</span></span> <span data-ttu-id="cbc0f-106">在任一拓扑中，网关将终止 PSTN。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-106">In either topology, the gateway terminates the PSTN.</span></span> <span data-ttu-id="cbc0f-107">网关被隔离在其自己的子网中，并通过中介服务器连接到企业网络。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-107">The gateway is isolated in its own subnet and is connected to the enterprise network through the Mediation Server.</span></span>

<span data-ttu-id="cbc0f-108">具有多个网站的企业通常会在每个网站上部署一个或多个网关。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-108">An enterprise with multiple sites would typically deploy one or more gateways at each site.</span></span> <span data-ttu-id="cbc0f-109">分支站点可以通过网关或通过 Survivable 分支设备连接到 PSTN，该设备将网关和服务器结合到一个框中。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-109">Branch sites can connect to the PSTN either through a gateway, or through a Survivable Branch Appliance, which combines gateway and servers in a single box.</span></span> <span data-ttu-id="cbc0f-110">如果分支站点使用网关，则在网站上需要注册机构和中介服务器，除非 WAN 链接是复原的。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-110">If branch sites use a gateway, both a Registrar and Mediation Server are required on site, unless the WAN link is resilient.</span></span> <span data-ttu-id="cbc0f-111">一个或多个中介服务器（在前端服务器上 collocated）可路由每个站点上的一个或多个网关的呼叫。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-111">One or more Mediation Servers, which are collocated on Front End Servers, can route calls for the one or more gateways at each site.</span></span> <span data-ttu-id="cbc0f-112">我们建议将网站上所需的注册机构、中介服务器和网关部署为 Survivable 分支装置。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-112">We recommend that the Registrar, Mediation Server, and gateway required on site are deployed as a Survivable Branch Appliance.</span></span>

<span data-ttu-id="cbc0f-113">确定 PSTN 网关的数量、大小和位置可能是规划企业语音基础结构时必须做出的最重要且昂贵的决策。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-113">Determining the number, size, and location of PSTN gateways is perhaps the most important and expensive decision you must make when planning your Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="cbc0f-114">下面是要考虑的主要问题。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-114">Here are the main questions to consider.</span></span> <span data-ttu-id="cbc0f-115">请记住，这些问题的答案都是相互依赖的</span><span class="sxs-lookup"><span data-stu-id="cbc0f-115">Keep in mind that the answers to these questions are all interdependent</span></span>

  - <span data-ttu-id="cbc0f-116">需要多少个 PSTN 网关？</span><span class="sxs-lookup"><span data-stu-id="cbc0f-116">How many PSTN gateways are needed?</span></span> <span data-ttu-id="cbc0f-117">答案取决于用户数、预计的同时通话数（流量负载）和网站数（每个网站需要一个）。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-117">The answer depends on the number of users, the anticipated number of simultaneous calls (traffic load), and the number of sites (each site needs one).</span></span>

  - <span data-ttu-id="cbc0f-118">网关应具有的大小是多少？</span><span class="sxs-lookup"><span data-stu-id="cbc0f-118">What size should the gateways be?</span></span> <span data-ttu-id="cbc0f-119">答案取决于网站上的用户数以及流量负载。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-119">The answer depends on the number of users at the site and on the traffic load.</span></span>

  - <span data-ttu-id="cbc0f-120">网关应位于何处？</span><span class="sxs-lookup"><span data-stu-id="cbc0f-120">Where should the gateways be located?</span></span> <span data-ttu-id="cbc0f-121">答案部分取决于拓扑和组织地理位置分布的部分。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-121">The answer depends in part on the topology and in part on the geographic distribution of your organization.</span></span>

<span data-ttu-id="cbc0f-122">你还应考虑网关拓扑选项（有关详细信息，请参阅本主题后面的网关拓扑）。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-122">You should also consider your gateway topology options (for details, see Gateway Topologies later in this topic).</span></span>

<div>

## <a name="mn-trunk-support"></a><span data-ttu-id="cbc0f-123">M:N 中继支持</span><span class="sxs-lookup"><span data-stu-id="cbc0f-123">M:N Trunk Support</span></span>

<span data-ttu-id="cbc0f-124">中介服务器可通过多个网关、由 Internet 电话服务提供商提供的会话边界控制器（SBCs）或这两者的组合来路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-124">The Mediation Servers can route calls through multiple gateways, Session Border Controllers (SBCs) provided by Internet telephony service providers, or a combination of the two.</span></span> <span data-ttu-id="cbc0f-125">此外，池中的多个中介服务器可以与多个网关交互。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-125">Additionally, multiple Mediation Servers in the pool can interact with multiple gateways.</span></span> <span data-ttu-id="cbc0f-126">在中介服务器和网关之间定义的逻辑路由称为*主干*。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-126">The logical route defined between a Mediation Server and gateway is called a *trunk*.</span></span> <span data-ttu-id="cbc0f-127">当内部用户置入 PSTN 呼叫时，前端池上的出站路由逻辑将选择哪些干线路由到可能可用于路由特定呼叫的所有可能的组合。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-127">When an internal user places a PSTN call, outbound routing logic on the Front End pool chooses which trunk to route over out of all possible combinations that may be available for routing that particular call.</span></span> <span data-ttu-id="cbc0f-128">使用 DNS 负载平衡，如果由于池中的特定中介服务器出现问题而导致呼叫无法到达网关，则会将该呼叫重试到池中的备用中介服务器。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-128">With DNS load balancing, if a call fails to reach a gateway due to an issue with a particular Mediation Server in the pool, the call will be retried to an alternate Mediation Server in the pool.</span></span>

<span data-ttu-id="cbc0f-129">有关规划多个网关的详细信息，请参阅[Lync Server 2013 中的 M:N 主干](lync-server-2013-m-n-trunk.md)。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-129">For details about planning for multiple gateways, see [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).</span></span>

<span data-ttu-id="cbc0f-130">有关其他出站路由增强的详细信息，请参阅[Lync Server 2013 中的语音路由](lync-server-2013-voice-routes.md)。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-130">For details about other outbound routing enhancements, see [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).</span></span>

</div>

<div>

## <a name="gateway-topologies"></a><span data-ttu-id="cbc0f-131">网关拓扑</span><span class="sxs-lookup"><span data-stu-id="cbc0f-131">Gateway Topologies</span></span>

<span data-ttu-id="cbc0f-132">考虑网关部署的基本问题时，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="cbc0f-132">When you consider the fundamental questions of gateway deployment, follow these steps:</span></span>

1.  <span data-ttu-id="cbc0f-133">使用企业语音对要提供 PSTN 连接的站点进行计数。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-133">Count the sites at which you want to provide PSTN connectivity by using Enterprise Voice.</span></span>

2.  <span data-ttu-id="cbc0f-134">估计每个网站上的流量（用户数和每个用户每小时平均通话数）。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-134">Estimate the traffic at each site (number of users and average number of calls per hour per user).</span></span>

3.  <span data-ttu-id="cbc0f-135">在每个站点部署一个或多个网关以处理预期的流量。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-135">Deploy one or more gateways at each site to handle the anticipated traffic.</span></span>

<span data-ttu-id="cbc0f-136">生成的分布式网关拓扑如下图所示。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-136">The resulting distributed gateway topology is shown in the following figure.</span></span>

<span data-ttu-id="cbc0f-137">**分布式网关拓扑**</span><span class="sxs-lookup"><span data-stu-id="cbc0f-137">**Distributed gateway topology**</span></span>

<span data-ttu-id="cbc0f-138">![分布式网关拓扑图](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "分布式网关拓扑图")</span><span class="sxs-lookup"><span data-stu-id="cbc0f-138">![Distributed Gateway Topology diagram](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Distributed Gateway Topology diagram")</span></span>

<span data-ttu-id="cbc0f-139">在此拓扑中，每个站点和站点之间的工作人员之间的通话均通过 intranet 进行路由。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-139">With this topology, calls among workers at each site and between sites are all routed over your intranet.</span></span> <span data-ttu-id="cbc0f-140">对 PSTN 的调用通过企业 IP 网络路由到最接近目标号码位置的网关。但是，如果您的组织支持数十个或成百上千个站点分布在一个或多个洲内，那么许多金融机构和其他大型企业都有这些功能？</span><span class="sxs-lookup"><span data-stu-id="cbc0f-140">Calls to the PSTN are routed over the enterprise IP network to the gateways that are closest to the location of the destination numbers.But what if your organization supports dozens or hundreds or even thousands of sites spread across one or more continents, as many financial institutions and other large enterprises do?</span></span> <span data-ttu-id="cbc0f-141">在这种情况下，在每个网站上部署单独的网关是不切实际的。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-141">In such cases, deploying a separate gateway at each site is not practical.</span></span>

<span data-ttu-id="cbc0f-142">为了解决此问题，许多大型公司更喜欢部署一个或几个大型电话中心网站，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-142">To address this issue, many large companies prefer to deploy one or a few large telephony central sites, as shown in the following figure.</span></span>

<span data-ttu-id="cbc0f-143">**电话中心站点拓扑**</span><span class="sxs-lookup"><span data-stu-id="cbc0f-143">**Telephony central site topology**</span></span>

<span data-ttu-id="cbc0f-144">![数据中心网关拓扑](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "数据中心网关拓扑")</span><span class="sxs-lookup"><span data-stu-id="cbc0f-144">![Data center gateway topology](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Data center gateway topology")</span></span>

<span data-ttu-id="cbc0f-145">在此拓扑中，将在每个中心站点上部署几个大型网关，足以容纳预期的用户负载。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-145">In this topology, several large gateways sufficient to accommodate the anticipated user load are deployed at each central site.</span></span> <span data-ttu-id="cbc0f-146">对企业中的用户的所有呼叫均由公司的电话服务提供商转发到中央站点。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-146">All calls to users in the enterprise are forwarded by the company's telephone service provider to a central site.</span></span> <span data-ttu-id="cbc0f-147">中心网站上的路由逻辑确定是否应通过 intranet 或 PSTN 路由呼叫。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-147">Routing logic at the central site determines whether the call should be routed over the intranet or to the PSTN.</span></span>

</div>

<div>

## <a name="gateway-location"></a><span data-ttu-id="cbc0f-148">网关位置</span><span class="sxs-lookup"><span data-stu-id="cbc0f-148">Gateway Location</span></span>

<span data-ttu-id="cbc0f-149">网关位置还可以确定你选择的网关类型以及它们的配置方式。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-149">Gateway location may also determine the types of gateways that you choose and how they are configured.</span></span> <span data-ttu-id="cbc0f-150">有许多 PSTN 协议，它们都不是全球标准。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-150">There are dozens of PSTN protocols, none of which is a worldwide standard.</span></span> <span data-ttu-id="cbc0f-151">如果你的所有网关均位于单个国家/地区，则不会出现问题，但如果你在多个国家/地区中找到网关，则每个国家/地区都必须根据该国家/地区的 PSTN 标准进行配置。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-151">If all your gateways are located in a single country/region, this is not an issue, but if you locate gateways in several countries/regions, each must be configured according to the PSTN standards of that country/region.</span></span> <span data-ttu-id="cbc0f-152">此外，为在加拿大（例如加拿大）内操作认证的网关可能未在印度、巴西或欧盟进行认证。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-152">Moreover, gateways that are certified for operation in, for example, Canada, may not be certified in India, Brazil, or the European Union.</span></span>

</div>

<div>

## <a name="gateway-size-and-number"></a><span data-ttu-id="cbc0f-153">网关大小和号码</span><span class="sxs-lookup"><span data-stu-id="cbc0f-153">Gateway Size and Number</span></span>

<span data-ttu-id="cbc0f-154">大多数组织都将考虑从2到多达960端口部署范围内的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-154">The PSTN gateways that most organizations will consider deploying range in size from 2 to as many as 960 ports.</span></span> <span data-ttu-id="cbc0f-155">（甚至更大的网关，但主要由电话服务提供商使用。）估计你的组织所需的端口数时，请使用以下指南：</span><span class="sxs-lookup"><span data-stu-id="cbc0f-155">(There are even larger gateways, but these are used mainly by telephone service providers.) When estimating the number of ports your organization requires, use the following guidelines:</span></span>

  - <span data-ttu-id="cbc0f-156">具有轻型电话使用的组织（每个用户每小时一个 PSTN 呼叫）应该为每15个用户分配一个端口。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-156">Organizations with light telephony usage (one PSTN call per user per hour) should allocate one port for every 15 users.</span></span> <span data-ttu-id="cbc0f-157">例如，如果您有20个用户，将需要一个具有两个端口的网关。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-157">For example, if you have 20 users, you will require a gateway with two ports.</span></span>

  - <span data-ttu-id="cbc0f-158">具有中等电话服务使用率（每个用户每小时两个 PSTN 呼叫）的组织应为每10个用户分配一个端口。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-158">Organizations with moderate telephony usage (two PSTN calls per user per hour) should allocate one port for every 10 users.</span></span> <span data-ttu-id="cbc0f-159">例如，如果您有100用户，那么您将需要在一个或多个网关之间分配10个端口。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-159">For example, if you have 100 users, you will require a total of 10 ports allocated among one or more gateways.</span></span>

  - <span data-ttu-id="cbc0f-160">使用大量电话服务的组织（每个用户每小时的三个或更多 PSTN 呼叫）应为每五个用户分配一个端口。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-160">Organizations with heavy telephony usage (three or more PSTN calls per user per hour) should allocate one port for every five users.</span></span> <span data-ttu-id="cbc0f-161">例如，如果您有47000用户，则需要在至少10个大型网关之间分配的9400端口总数。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-161">For example, if you have 47,000 users, you will require a total of 9,400 ports allocated among at least 10 large gateways.</span></span>

  - <span data-ttu-id="cbc0f-162">在您的组织中增加的用户数或您的组织中的流量量增加时，可以获得其他端口。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-162">Additional ports can be acquired as the number of users or amount of traffic in your organization increases.</span></span>

<span data-ttu-id="cbc0f-163">对于任何必须支持的用户数，您可以选择部署较少、更大的网关或较小的网关。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-163">For any given number of users you must support, you have the choice of deploying fewer, larger gateways, or smaller ones.</span></span> <span data-ttu-id="cbc0f-164">通常，建议组织至少两个网关，以便在一个网关出现故障时保持可用性。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-164">As a rule, a minimum of two gateways for an organization is recommended to maintain availability if one gateway fails.</span></span>

<span data-ttu-id="cbc0f-165">你部署的每个 PSTN 网关都必须至少有一个对应的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="cbc0f-165">Each PSTN gateway that you deploy must have at least one corresponding Mediation Server.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

