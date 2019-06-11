---
title: Lync Server 2013：中介服务器的组件和拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f9c353dc65f5e943e082df9321a934ea8f14be1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837525"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="12b48-102">Lync Server 2013 中中介服务器的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="12b48-102">Components and topologies for Mediation Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12b48-103">_**主题上次修改时间:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="12b48-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="12b48-104">本主题介绍了中介服务器依赖的组件以及可以在其中部署中介服务器的拓扑</span><span class="sxs-lookup"><span data-stu-id="12b48-104">This topic describes the components on which the Mediation Server is dependent and the topologies in which the Mediation Server can be deployed</span></span>

<div>

## <a name="dependencies"></a><span data-ttu-id="12b48-105">依赖项</span><span class="sxs-lookup"><span data-stu-id="12b48-105">Dependencies</span></span>

<span data-ttu-id="12b48-106">中介服务器具有以下依赖关系:</span><span class="sxs-lookup"><span data-stu-id="12b48-106">The Mediation Server has the following dependencies:</span></span>

  - <span data-ttu-id="12b48-107">**注册.**</span><span class="sxs-lookup"><span data-stu-id="12b48-107">**Registrar.**</span></span> <span data-ttu-id="12b48-108">必需。</span><span class="sxs-lookup"><span data-stu-id="12b48-108">Required.</span></span> <span data-ttu-id="12b48-109">注册机构是中介服务器与 Lync Server 2013 网络交互中的信号的下一跃点。</span><span class="sxs-lookup"><span data-stu-id="12b48-109">The Registrar is the next hop for signaling in the Mediation Server interactions with the Lync Server 2013 network.</span></span> <span data-ttu-id="12b48-110">请注意, 除了在包含中介服务器的独立池中安装外, 还可以在前端服务器上与注册机构一起 collocated。</span><span class="sxs-lookup"><span data-stu-id="12b48-110">Note that Mediation Server can be collocated on a Front End Server along with the Registrar, in addition to being installed in a stand-alone pool consisting only of Mediation Servers.</span></span> <span data-ttu-id="12b48-111">注册机构在 Survivable 分支装置上使用中介服务器和 PSTN 网关 collocated。</span><span class="sxs-lookup"><span data-stu-id="12b48-111">The Registrar is collocated with a Mediation Server and PSTN gateway on a Survivable Branch Appliance.</span></span>

  - <span data-ttu-id="12b48-112">**监视服务器。**</span><span class="sxs-lookup"><span data-stu-id="12b48-112">**Monitoring Server.**</span></span> <span data-ttu-id="12b48-113">可选, 但强烈建议使用。</span><span class="sxs-lookup"><span data-stu-id="12b48-113">Optional but highly recommended.</span></span> <span data-ttu-id="12b48-114">监视服务器允许中介服务器记录与其媒体会话关联的质量指标。</span><span class="sxs-lookup"><span data-stu-id="12b48-114">The Monitoring Server allows the Mediation Server to record quality metrics associated with its media sessions.</span></span>

  - <span data-ttu-id="12b48-115">**边缘服务器。**</span><span class="sxs-lookup"><span data-stu-id="12b48-115">**Edge Server.**</span></span> <span data-ttu-id="12b48-116">外部用户支持所必需。</span><span class="sxs-lookup"><span data-stu-id="12b48-116">Required for external user support.</span></span> <span data-ttu-id="12b48-117">Edge 服务器允许中介服务器与位于 NAT 或防火墙后面的用户进行交互。</span><span class="sxs-lookup"><span data-stu-id="12b48-117">The Edge Server allows the Mediation Server to interact with users who are located behind a NAT or firewall.</span></span>

</div>

<div>

## <a name="topologies"></a><span data-ttu-id="12b48-118">朴</span><span class="sxs-lookup"><span data-stu-id="12b48-118">Topologies</span></span>

<span data-ttu-id="12b48-119">Lync Server 2013 (中介服务器) 默认情况下 collocated 在标准版服务器、前端池或 Survivable 分支装置上使用注册机构的实例。</span><span class="sxs-lookup"><span data-stu-id="12b48-119">The Lync Server 2013, Mediation Server is by default collocated with an instance of the Registrar on a Standard Edition server, a Front End pool, or Survivable Branch Appliance.</span></span> <span data-ttu-id="12b48-120">前端池中的所有中介服务器的配置都必须相同。</span><span class="sxs-lookup"><span data-stu-id="12b48-120">All Mediation Servers in a Front End pool must be configured identically.</span></span>

<span data-ttu-id="12b48-121">在性能有问题的情况下, 最好是在专用独立池中部署一个或多个中介服务器。</span><span class="sxs-lookup"><span data-stu-id="12b48-121">Where performance is an issue, it may be preferable to deploy one or more Mediation Servers in a dedicated stand-alone pool.</span></span> <span data-ttu-id="12b48-122">或者, 如果你要部署 SIP 中继, 我们建议你部署独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="12b48-122">Or, if you are deploying SIP trunking, we recommend that you deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="12b48-123">如果你将直接 SIP 连接部署到支持媒体绕过和 DNS 负载平衡的合格 PSTN 网关, 则不需要独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="12b48-123">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="12b48-124">不需要独立的中介服务器池, 因为合格的网关能够将 DNS 负载平衡到中介服务器池, 并且它们可以接收来自池中的任何中介服务器的流量。</span><span class="sxs-lookup"><span data-stu-id="12b48-124">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="12b48-125">我们还建议你在部署 IP-Pbx 或连接到 Internet 电话服务器提供商的会话边界控制器 (SBC) 时, 在前端池中 collocate 中介服务器, 前提是满足以下任何条件:</span><span class="sxs-lookup"><span data-stu-id="12b48-125">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="12b48-126">将 IP PBX 或 SBC 配置为接收来自池中的任何中介服务器的流量, 并且可以将流量统一路由到池中的所有中介服务器。</span><span class="sxs-lookup"><span data-stu-id="12b48-126">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="12b48-127">IP-PBX 不支持媒体绕过, 但托管中介服务器的前端池可以处理语音转换, 以便不应用绕过媒体的呼叫。</span><span class="sxs-lookup"><span data-stu-id="12b48-127">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="12b48-128">你可以使用 Microsoft Lync Server 2013、计划工具评估你想要 collocate 中介服务器的前端池是否可以处理负载。</span><span class="sxs-lookup"><span data-stu-id="12b48-128">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="12b48-129">如果你的环境无法满足这些要求, 则必须部署独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="12b48-129">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="12b48-130">有关要部署的拓扑的详细信息, 请参阅[Lync server 2013 中的中介服务器部署指南](lync-server-2013-deployment-guidelines-for-mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="12b48-130">For details about which topology to deploy, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="12b48-131">下图显示了由通过 WAN 链路连接的两个站点组成的简单拓扑。</span><span class="sxs-lookup"><span data-stu-id="12b48-131">The following figure shows a simple topology consisting of two sites connected by a WAN link.</span></span> <span data-ttu-id="12b48-132">在站点1的前端池中的注册机构 collocated 的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="12b48-132">Mediation Server is collocated with the Registrar on a Front End pool at Site 1.</span></span> <span data-ttu-id="12b48-133">站点1处的中介服务器控制站点1和站点2上的网关的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="12b48-133">The Mediation Servers at Site 1 controls both the PSTN gateway at Site 1 and the gateway at Site 2.</span></span> <span data-ttu-id="12b48-134">在此拓扑中，已在全局范围内启用媒体旁路以使用站点和区域信息，并且到每个 PSTN 网关（GW1 和 GW2）的中继都已启用旁路。</span><span class="sxs-lookup"><span data-stu-id="12b48-134">In this topology, media bypass is enabled globally to use site and region information, and the trunks to each PSTN gateway (GW1 and GW2) have bypass enabled.</span></span>

<span data-ttu-id="12b48-135">**通过 WAN 链路与站点 1 的中介服务器和站点 2 的 PSTN 网关相连接的站点示例**</span><span class="sxs-lookup"><span data-stu-id="12b48-135">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PSTN gateway at Site 2**</span></span>

<span data-ttu-id="12b48-136">![具有中介服务器 WAN 网关的语音拓扑](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "具有中介服务器 WAN 网关的语音拓扑")</span><span class="sxs-lookup"><span data-stu-id="12b48-136">![Voice Topology with Mediation Server WAN Gateway](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Voice Topology with Mediation Server WAN Gateway")</span></span>

<span data-ttu-id="12b48-137">下图显示了一个简单的拓扑, 其中中介服务器在站点1上与 collocated 前端池的注册机构进行了连接, 并与站点1上的 IP PBX 具有直接 SIP 连接。</span><span class="sxs-lookup"><span data-stu-id="12b48-137">The next figure shows a simple topology where the Mediation Server is collocated with the Registrar on Front End pool at Site 1 and has a Direct SIP connection to the IP-PBX at Site 1.</span></span> <span data-ttu-id="12b48-138">在此图中, 中介服务器还控制站点2上的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="12b48-138">In this figure, the Mediation Server also controls a PSTN gateway at Site 2.</span></span> <span data-ttu-id="12b48-139">假设 Lync 用户同时存在于站点1和2。</span><span class="sxs-lookup"><span data-stu-id="12b48-139">Assume that Lync users exist at both Sites 1 and 2.</span></span> <span data-ttu-id="12b48-140">此外, 假设在发送到由 IP PBX 控制的媒体终结点之前, 必须由所有源自 Lync 终结点的媒体遍历到 IP PBX 的媒体处理器。</span><span class="sxs-lookup"><span data-stu-id="12b48-140">Also assume that the IP-PBX has an associated media processor that must be traversed by all media originating from Lync endpoints before being sent to media endpoints controlled by the IP-PBX.</span></span> <span data-ttu-id="12b48-141">在此拓扑中，已在全局范围内启用媒体旁路以使用站点和区域信息，并且到 PBX 和 PSTN 网关的中继已启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="12b48-141">In this topology, media bypass is enabled globally to use site and region information, and the trunks to the PBX and PSTN gateway have media bypass enabled.</span></span>

<span data-ttu-id="12b48-142">**通过 WAN 链路与站点 1 的中介服务器和站点 2 的 PBX 相连接的站点的示例**</span><span class="sxs-lookup"><span data-stu-id="12b48-142">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PBX at Site 2**</span></span>

<span data-ttu-id="12b48-143">![语音拓扑中介服务器 WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "语音拓扑中介服务器 WAN PBX")</span><span class="sxs-lookup"><span data-stu-id="12b48-143">![Voice Topology Mediation Server WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Voice Topology Mediation Server WAN PBX")</span></span>

<span data-ttu-id="12b48-144">有关规划 PBX 拓扑的详细信息, 请参阅[lync server 2013 中的中介服务器部署指南](lync-server-2013-deployment-guidelines-for-mediation-server.md)和[lync server 2013 中的直接 SIP 部署选项](lync-server-2013-direct-sip-deployment-options.md)。</span><span class="sxs-lookup"><span data-stu-id="12b48-144">For details about planning for PBX topologies, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) and [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span></span>

<span data-ttu-id="12b48-145">本主题中的最后一个图显示了一个拓扑, 其中中介服务器连接到 Internet 电话服务提供商的 SBC。</span><span class="sxs-lookup"><span data-stu-id="12b48-145">The last figure in this topic shows a topology where the Mediation Server is connected to the SBC of an Internet Telephony Service Provider.</span></span> <span data-ttu-id="12b48-146">有关 SIP 中继拓扑的详细信息, 请参阅[Lync Server 2013 中的 SIP 中继](lync-server-2013-sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="12b48-146">For details about SIP trunk topologies, see [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

