---
title: Lync Server 2013：中介服务器组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mediation Server component
ms:assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398399(v=OCS.15)
ms:contentKeyID: 48184239
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 363b277003d7ca1581475ec7c1197bb0f60ccfaa
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41766073"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a><span data-ttu-id="15a2f-102">Lync Server 2013 中的中介服务器组件</span><span class="sxs-lookup"><span data-stu-id="15a2f-102">Mediation Server component in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="15a2f-103">_**主题上次修改时间：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="15a2f-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="15a2f-104">如果你部署了企业语音工作负荷，则必须部署 Lync Server 2013、中介服务器。</span><span class="sxs-lookup"><span data-stu-id="15a2f-104">You must deploy Lync Server 2013, Mediation Server if you deploy the Enterprise Voice workload.</span></span> <span data-ttu-id="15a2f-105">本部分介绍基本功能、依赖关系、基本拓扑和规划指南。</span><span class="sxs-lookup"><span data-stu-id="15a2f-105">This section describes basic functionality, dependencies, basic topologies, and planning guidelines.</span></span>

<span data-ttu-id="15a2f-106">中介服务器转换信号，在某些配置中，你的内部 Lync Server 2013、企业语音基础结构和公共交换电话网络（PSTN）网关或会话初始协议（SIP）干线之间的媒体。</span><span class="sxs-lookup"><span data-stu-id="15a2f-106">The Mediation Server translates signaling and, in some configurations, media between your internal Lync Server 2013, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="15a2f-107">在 Lync Server 2013 端，中介服务器侦听单个相互 TLS （MTLS）传输地址。</span><span class="sxs-lookup"><span data-stu-id="15a2f-107">On the Lync Server 2013 side, Mediation Server listens on a single mutual TLS (MTLS) transport address.</span></span> <span data-ttu-id="15a2f-108">在网关端，中介服务器侦听与拓扑文档中定义的中继相关联的所有关联的侦听端口。</span><span class="sxs-lookup"><span data-stu-id="15a2f-108">On the gateway side, Mediation Server listens on all associated listening ports associated with trunks defined in the Topology document.</span></span> <span data-ttu-id="15a2f-109">所有合格网关必须支持 TLS，但也可以启用 TCP。</span><span class="sxs-lookup"><span data-stu-id="15a2f-109">All qualified gateways must support TLS, but can enable TCP as well.</span></span> <span data-ttu-id="15a2f-110">不支持 TLS 的网关将支持 TCP。</span><span class="sxs-lookup"><span data-stu-id="15a2f-110">TCP is supported for gateways that do not support TLS.</span></span>

<span data-ttu-id="15a2f-111">如果你的环境中还有现有的公共分支 Exchange （PBX），则中介服务器处理企业语音用户和 PBX 之间的通话。</span><span class="sxs-lookup"><span data-stu-id="15a2f-111">If you also have an existing Public Branch Exchange (PBX) in your environment, Mediation Server handles calls between Enterprise Voice users and the PBX.</span></span> <span data-ttu-id="15a2f-112">如果你的 PBX 是 IP PBX，则可以在 PBX 和中介服务器之间创建直接 SIP 连接。</span><span class="sxs-lookup"><span data-stu-id="15a2f-112">If your PBX is an IP-PBX, you can create a direct SIP connection between the PBX and Mediation Server.</span></span> <span data-ttu-id="15a2f-113">如果你的 PBX 是时间段多路传输（TDM） PBX，则还必须在中介服务器和 PBX 之间部署 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="15a2f-113">If your PBX is a Time Division Multiplex (TDM) PBX, you must also deploy a PSTN gateway between Mediation Server and the PBX.</span></span>

<span data-ttu-id="15a2f-114">默认情况下，中介服务器与前端服务器 collocated。</span><span class="sxs-lookup"><span data-stu-id="15a2f-114">The Mediation Server is collocated with the Front End Server by default.</span></span> <span data-ttu-id="15a2f-115">由于性能原因，中介服务器也可以部署在独立的池中，或者，如果你部署 SIP 中继，强烈建议使用独立池。</span><span class="sxs-lookup"><span data-stu-id="15a2f-115">The Mediation Server can also be deployed in a stand-alone pool for performance reasons, or if you deploy SIP trunking, in which case the stand-alone pool is strongly recommended.</span></span>

<span data-ttu-id="15a2f-116">如果你将直接 SIP 连接部署到支持媒体绕过和 DNS 负载平衡的合格 PSTN 网关，则不需要独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="15a2f-116">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="15a2f-117">不需要独立的中介服务器池，因为合格的网关能够将 DNS 负载平衡到中介服务器池，并且它们可以接收来自池中的任何中介服务器的流量。</span><span class="sxs-lookup"><span data-stu-id="15a2f-117">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="15a2f-118">我们还建议你在部署 IP-Pbx 或连接到 Internet 电话服务器提供商的会话边界控制器（SBC）时，在前端池中 collocate 中介服务器，前提是满足以下任何条件：</span><span class="sxs-lookup"><span data-stu-id="15a2f-118">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="15a2f-119">将 IP PBX 或 SBC 配置为接收来自池中的任何中介服务器的流量，并且可以将流量统一路由到池中的所有中介服务器。</span><span class="sxs-lookup"><span data-stu-id="15a2f-119">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="15a2f-120">IP-PBX 不支持媒体绕过，但托管中介服务器的前端池可以处理语音转换，以便不应用绕过媒体的呼叫。</span><span class="sxs-lookup"><span data-stu-id="15a2f-120">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="15a2f-121">你可以使用 Microsoft Lync Server 2013、计划工具评估你想要 collocate 中介服务器的前端池是否可以处理负载。</span><span class="sxs-lookup"><span data-stu-id="15a2f-121">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="15a2f-122">如果你的环境无法满足这些要求，则必须部署独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="15a2f-122">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="15a2f-123">中介服务器的主要功能如下所示：</span><span class="sxs-lookup"><span data-stu-id="15a2f-123">The main functions of the Mediation Server are as follows:</span></span>

  - <span data-ttu-id="15a2f-124">在 Lync Server 端对 SRTP 进行加密和解密</span><span class="sxs-lookup"><span data-stu-id="15a2f-124">Encrypting and decrypting SRTP on the Lync Server side</span></span>

  - <span data-ttu-id="15a2f-125">通过 TCP （对于不支持 TLS 的网关）将 SIP 转换为通过相互 TLS 的 SIP</span><span class="sxs-lookup"><span data-stu-id="15a2f-125">Translating SIP over TCP (for gateways that do not support TLS) to SIP over mutual TLS</span></span>

  - <span data-ttu-id="15a2f-126">在 Lync 服务器和中介服务器的网关对等之间转换媒体流</span><span class="sxs-lookup"><span data-stu-id="15a2f-126">Translating media streams between Lync Server and the gateway peer of the Mediation Server</span></span>

  - <span data-ttu-id="15a2f-127">将网络外部的客户端连接到内部 ICE 组件，从而支持 NAT 和防火墙的媒体遍历</span><span class="sxs-lookup"><span data-stu-id="15a2f-127">Connecting clients that are outside the network to internal ICE components, which enable media traversal of NAT and firewalls</span></span>

  - <span data-ttu-id="15a2f-128">充当网关不支持的呼叫流的媒介，例如来自企业语音客户端的远程工作人员的呼叫</span><span class="sxs-lookup"><span data-stu-id="15a2f-128">Acting as an intermediary for call flows that a gateway does not support, such as calls from remote workers on an Enterprise Voice client</span></span>

  - <span data-ttu-id="15a2f-129">在包含 SIP 中继的部署中，使用 SIP 中继服务提供商提供 PSTN 支持，从而无需 PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="15a2f-129">In deployments that include SIP trunking, working with the SIP trunking service provider to provide PSTN support, which eliminates the need for a PSTN gateway</span></span>

<span data-ttu-id="15a2f-130">下图显示了在与基本 PSTN 网关和企业语音基础结构通信时，中介服务器使用的信号和媒体协议。</span><span class="sxs-lookup"><span data-stu-id="15a2f-130">The following figure shows the signaling and media protocols that are used by the Mediation Server when communicating with a basic PSTN gateway and the Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="15a2f-131">**中介服务器使用的信号和媒体协议**</span><span class="sxs-lookup"><span data-stu-id="15a2f-131">**Signaling and media protocols used by the Mediation Server**</span></span>

<span data-ttu-id="15a2f-132">![中介服务器协议图](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "中介服务器协议图")</span><span class="sxs-lookup"><span data-stu-id="15a2f-132">![Mediation Server Protocols diagram](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Mediation Server Protocols diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="15a2f-133">如果在 PSTN 网关和中介服务器之间的网络上使用 TCP 或 RTP/RTCP （而不是 SRTP 或 SRTCP），我们建议你采取措施来帮助确保网络的安全和隐私。</span><span class="sxs-lookup"><span data-stu-id="15a2f-133">If you are using TCP or RTP/RTCP (instead of SRTP or SRTCP) on the network between the PSTN gateway and the Mediation Server, we recommend that you take measures to help ensure the security and privacy of the network.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="15a2f-134">本节内容</span><span class="sxs-lookup"><span data-stu-id="15a2f-134">In This Section</span></span>

  - [<span data-ttu-id="15a2f-135">Lync Server 2013 中的 M:N 主干</span><span class="sxs-lookup"><span data-stu-id="15a2f-135">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="15a2f-136">Lync Server 2013 中的呼叫允许控制和中介服务器</span><span class="sxs-lookup"><span data-stu-id="15a2f-136">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [<span data-ttu-id="15a2f-137">Lync Server 2013 中的增强型 9-1-1 (E9-1-1) 和中介服务器</span><span class="sxs-lookup"><span data-stu-id="15a2f-137">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [<span data-ttu-id="15a2f-138">Lync Server 2013 中的媒体绕过和中介服务器</span><span class="sxs-lookup"><span data-stu-id="15a2f-138">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)

  - [<span data-ttu-id="15a2f-139">Lync Server 2013 中中介服务器的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="15a2f-139">Components and topologies for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [<span data-ttu-id="15a2f-140">Lync Server 2013 中的中介服务器部署指南</span><span class="sxs-lookup"><span data-stu-id="15a2f-140">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

