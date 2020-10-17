---
title: Lync Server 2013：中介服务器的组件和拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Mediation Server
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398537(v=OCS.15)
ms:contentKeyID: 48184487
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ac46c8aba06bdfedaafa7846142d5a584c703c3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502559"
---
# <a name="components-and-topologies-for-mediation-server-in-lync-server-2013"></a><span data-ttu-id="2a5fe-102">Lync Server 2013 中的中介服务器的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="2a5fe-102">Components and topologies for Mediation Server in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a5fe-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="2a5fe-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="2a5fe-104">本主题介绍了中介服务器依赖的组件以及可在其中部署中介服务器的拓扑</span><span class="sxs-lookup"><span data-stu-id="2a5fe-104">This topic describes the components on which the Mediation Server is dependent and the topologies in which the Mediation Server can be deployed</span></span>

<div>

## <a name="dependencies"></a><span data-ttu-id="2a5fe-105">相关性</span><span class="sxs-lookup"><span data-stu-id="2a5fe-105">Dependencies</span></span>

<span data-ttu-id="2a5fe-106">中介服务器具有以下依存关系：</span><span class="sxs-lookup"><span data-stu-id="2a5fe-106">The Mediation Server has the following dependencies:</span></span>

  - <span data-ttu-id="2a5fe-107">**注册.**</span><span class="sxs-lookup"><span data-stu-id="2a5fe-107">**Registrar.**</span></span> <span data-ttu-id="2a5fe-108">必填。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-108">Required.</span></span> <span data-ttu-id="2a5fe-109">注册器是中介服务器与 Lync Server 2013 网络的交互中的信号的下一个跃点。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-109">The Registrar is the next hop for signaling in the Mediation Server interactions with the Lync Server 2013 network.</span></span> <span data-ttu-id="2a5fe-110">请注意，除了安装在仅包含中介服务器的独立池之外，中介服务器还可以与注册器一起并置在前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-110">Note that Mediation Server can be collocated on a Front End Server along with the Registrar, in addition to being installed in a stand-alone pool consisting only of Mediation Servers.</span></span> <span data-ttu-id="2a5fe-111">注册器与 Survivable 分支设备上的中介服务器和 PSTN 网关并置。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-111">The Registrar is collocated with a Mediation Server and PSTN gateway on a Survivable Branch Appliance.</span></span>

  - <span data-ttu-id="2a5fe-112">**监控服务器。**</span><span class="sxs-lookup"><span data-stu-id="2a5fe-112">**Monitoring Server.**</span></span> <span data-ttu-id="2a5fe-113">可选，但强烈建议。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-113">Optional but highly recommended.</span></span> <span data-ttu-id="2a5fe-114">监控服务器允许中介服务器记录与其媒体会话相关的质量指标。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-114">The Monitoring Server allows the Mediation Server to record quality metrics associated with its media sessions.</span></span>

  - <span data-ttu-id="2a5fe-115">**边缘服务器。**</span><span class="sxs-lookup"><span data-stu-id="2a5fe-115">**Edge Server.**</span></span> <span data-ttu-id="2a5fe-116">外部用户支持的必需项。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-116">Required for external user support.</span></span> <span data-ttu-id="2a5fe-117">通过边缘服务器，中介服务器可以与位于 NAT 或防火墙后面的用户进行交互。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-117">The Edge Server allows the Mediation Server to interact with users who are located behind a NAT or firewall.</span></span>

</div>

<div>

## <a name="topologies"></a><span data-ttu-id="2a5fe-118">拓扑</span><span class="sxs-lookup"><span data-stu-id="2a5fe-118">Topologies</span></span>

<span data-ttu-id="2a5fe-119">Lync Server 2013 （中介服务器）默认情况下并置具有 Standard Edition Server、前端池或 Survivable 分支设备上的注册器实例。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-119">The Lync Server 2013, Mediation Server is by default collocated with an instance of the Registrar on a Standard Edition server, a Front End pool, or Survivable Branch Appliance.</span></span> <span data-ttu-id="2a5fe-120">前端池中的所有中介服务器都必须进行相同的配置。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-120">All Mediation Servers in a Front End pool must be configured identically.</span></span>

<span data-ttu-id="2a5fe-121">在性能问题的情况下，最好在专用独立池中部署一个或多个中介服务器。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-121">Where performance is an issue, it may be preferable to deploy one or more Mediation Servers in a dedicated stand-alone pool.</span></span> <span data-ttu-id="2a5fe-122">或者，如果您正在部署 SIP 中继，我们建议您部署独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-122">Or, if you are deploying SIP trunking, we recommend that you deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="2a5fe-123">如果将直接 SIP 连接部署到支持媒体旁路和 DNS 负载平衡的合格 PSTN 网关，则不需要独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-123">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="2a5fe-124">若要将直接 SIP 连接部署到支持媒体旁路和 DNS 负载平衡的合格的 PSTN 网关，则不需要独立的中介服务器池，因为合格的网关能够将 DNS 负载平衡到中介服务器池，并且可以从池中的任何中介服务器接收通信。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-124">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="2a5fe-125">如果已部署 IP-PBX 或连接到互联网电话服务供应商的会话边界控制器 (SBC)，只要满足以下其中一个条件，我们还建议您将中介服务器并置在前端池上：</span><span class="sxs-lookup"><span data-stu-id="2a5fe-125">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="2a5fe-126">IP-PBX 或 SBC 已配置为接收来自池中的任何中介服务器的通信，并且可将通信统一路由到池中的所有中介服务器。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-126">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="2a5fe-127">Ip-pbx 不支持媒体旁路，但承载中介服务器的前端池可以处理对不应用媒体旁路的呼叫的语音转码。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-127">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="2a5fe-128">您可以使用 Microsoft Lync Server 2013、规划工具来评估您要并置中介服务器的前端池是否可以处理负载。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-128">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="2a5fe-129">如果您的环境不能满足这些要求，则必须部署独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-129">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="2a5fe-130">有关要部署的拓扑的详细信息，请参阅 [Lync server 2013 中的中介服务器部署指南](lync-server-2013-deployment-guidelines-for-mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-130">For details about which topology to deploy, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="2a5fe-131">下图显示了由通过 WAN 链路连接的两个站点组成的简单拓扑。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-131">The following figure shows a simple topology consisting of two sites connected by a WAN link.</span></span> <span data-ttu-id="2a5fe-132">中介服务器与在站点1的前端池上的注册器并置。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-132">Mediation Server is collocated with the Registrar on a Front End pool at Site 1.</span></span> <span data-ttu-id="2a5fe-133">站点1上的中介服务器控制站点1和站点2上的网关的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-133">The Mediation Servers at Site 1 controls both the PSTN gateway at Site 1 and the gateway at Site 2.</span></span> <span data-ttu-id="2a5fe-134">在此拓扑中，已在全局范围内启用媒体旁路以使用站点和区域信息，并且到每个 PSTN 网关（GW1 和 GW2）的中继都已启用旁路。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-134">In this topology, media bypass is enabled globally to use site and region information, and the trunks to each PSTN gateway (GW1 and GW2) have bypass enabled.</span></span>

<span data-ttu-id="2a5fe-135">**通过 WAN 链路与站点 1 的中介服务器和站点 2 的 PSTN 网关相连接的站点示例**</span><span class="sxs-lookup"><span data-stu-id="2a5fe-135">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PSTN gateway at Site 2**</span></span>

<span data-ttu-id="2a5fe-136">![具有中介服务器 WAN 网关的语音拓扑](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "具有中介服务器 WAN 网关的语音拓扑")</span><span class="sxs-lookup"><span data-stu-id="2a5fe-136">![Voice Topology with Mediation Server WAN Gateway](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "Voice Topology with Mediation Server WAN Gateway")</span></span>

<span data-ttu-id="2a5fe-137">下图显示了一个简单的拓扑，其中中介服务器与在站点1上的注册器在前端池上并置，并具有站点1与 IP PBX 的直接 SIP 连接。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-137">The next figure shows a simple topology where the Mediation Server is collocated with the Registrar on Front End pool at Site 1 and has a Direct SIP connection to the IP-PBX at Site 1.</span></span> <span data-ttu-id="2a5fe-138">在此图中，中介服务器还控制站点2的 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-138">In this figure, the Mediation Server also controls a PSTN gateway at Site 2.</span></span> <span data-ttu-id="2a5fe-139">假定 Lync 用户同时存在于站点1和2。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-139">Assume that Lync users exist at both Sites 1 and 2.</span></span> <span data-ttu-id="2a5fe-140">此外，还假定在发送到由 ip-pbx 控制的媒体终结点之前，必须由源自 Lync 终结点的所有媒体遍历的 ip-pbx 的媒体处理器。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-140">Also assume that the IP-PBX has an associated media processor that must be traversed by all media originating from Lync endpoints before being sent to media endpoints controlled by the IP-PBX.</span></span> <span data-ttu-id="2a5fe-141">在此拓扑中，已在全局范围内启用媒体旁路以使用站点和区域信息，并且到 PBX 和 PSTN 网关的中继已启用媒体旁路。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-141">In this topology, media bypass is enabled globally to use site and region information, and the trunks to the PBX and PSTN gateway have media bypass enabled.</span></span>

<span data-ttu-id="2a5fe-142">**通过 WAN 链路与站点 1 的中介服务器和站点 2 的 PBX 相连接的站点的示例**</span><span class="sxs-lookup"><span data-stu-id="2a5fe-142">**Example of sites connected by a WAN link with a Mediation Server at Site 1 and a PBX at Site 2**</span></span>

<span data-ttu-id="2a5fe-143">![语音拓扑中介服务器 WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "语音拓扑中介服务器 WAN PBX")</span><span class="sxs-lookup"><span data-stu-id="2a5fe-143">![Voice Topology Mediation Server WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "Voice Topology Mediation Server WAN PBX")</span></span>

<span data-ttu-id="2a5fe-144">有关规划 PBX 拓扑的详细信息，请参阅 lync server [2013 中的中介服务器部署指南](lync-server-2013-deployment-guidelines-for-mediation-server.md) 和 [lync server 2013 中的直接 SIP 部署选项](lync-server-2013-direct-sip-deployment-options.md)。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-144">For details about planning for PBX topologies, see [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md) and [Direct SIP deployment options in Lync Server 2013](lync-server-2013-direct-sip-deployment-options.md).</span></span>

<span data-ttu-id="2a5fe-145">本主题中的最后一个图显示了中介服务器连接到 Internet 电话服务提供商的 SBC 的拓扑。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-145">The last figure in this topic shows a topology where the Mediation Server is connected to the SBC of an Internet Telephony Service Provider.</span></span> <span data-ttu-id="2a5fe-146">有关 SIP 中继拓扑的详细信息，请参阅 [Lync Server 2013 中的 SIP 中继](lync-server-2013-sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="2a5fe-146">For details about SIP trunk topologies, see [SIP trunking in Lync Server 2013](lync-server-2013-sip-trunking.md).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

