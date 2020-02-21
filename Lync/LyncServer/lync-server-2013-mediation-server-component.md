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
ms.openlocfilehash: 2c068e284e871caf5848ba9616f8bf7afa380b49
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185176"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mediation-server-component-in-lync-server-2013"></a><span data-ttu-id="52414-102">Lync Server 2013 中的中介服务器组件</span><span class="sxs-lookup"><span data-stu-id="52414-102">Mediation Server component in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52414-103">_**上次修改的主题：** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="52414-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="52414-104">如果部署企业语音工作负载，则必须部署 Lync Server 2013 （中介服务器）。</span><span class="sxs-lookup"><span data-stu-id="52414-104">You must deploy Lync Server 2013, Mediation Server if you deploy the Enterprise Voice workload.</span></span> <span data-ttu-id="52414-105">本节描述了基本功能、依赖关系、基本拓扑和规划指南。</span><span class="sxs-lookup"><span data-stu-id="52414-105">This section describes basic functionality, dependencies, basic topologies, and planning guidelines.</span></span>

<span data-ttu-id="52414-106">中介服务器转换信号，在某些配置中，在内部 Lync Server 2013、企业语音基础结构和公共交换电话网络（PSTN）网关或会话初始协议（SIP）中继之间的媒体。</span><span class="sxs-lookup"><span data-stu-id="52414-106">The Mediation Server translates signaling and, in some configurations, media between your internal Lync Server 2013, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="52414-107">在 Lync Server 2013 端，中介服务器侦听单一相互 TLS （MTLS）传输地址。</span><span class="sxs-lookup"><span data-stu-id="52414-107">On the Lync Server 2013 side, Mediation Server listens on a single mutual TLS (MTLS) transport address.</span></span> <span data-ttu-id="52414-108">在网关这一端，中介服务器侦听与拓扑文档中定义的中继关联的所有相关侦听端口。</span><span class="sxs-lookup"><span data-stu-id="52414-108">On the gateway side, Mediation Server listens on all associated listening ports associated with trunks defined in the Topology document.</span></span> <span data-ttu-id="52414-109">所有合格网关必须支持 TLS，但也可以启用 TCP。</span><span class="sxs-lookup"><span data-stu-id="52414-109">All qualified gateways must support TLS, but can enable TCP as well.</span></span> <span data-ttu-id="52414-110">不支持 TLS 的网关将支持 TCP。</span><span class="sxs-lookup"><span data-stu-id="52414-110">TCP is supported for gateways that do not support TLS.</span></span>

<span data-ttu-id="52414-111">如果你的环境中还有现有的公共分支 Exchange （PBX），中介服务器将处理企业语音用户和 PBX 之间的呼叫。</span><span class="sxs-lookup"><span data-stu-id="52414-111">If you also have an existing Public Branch Exchange (PBX) in your environment, Mediation Server handles calls between Enterprise Voice users and the PBX.</span></span> <span data-ttu-id="52414-112">如果你的 PBX 是 ip-pbx，则可以在 PBX 和中介服务器之间创建直接 SIP 连接。</span><span class="sxs-lookup"><span data-stu-id="52414-112">If your PBX is an IP-PBX, you can create a direct SIP connection between the PBX and Mediation Server.</span></span> <span data-ttu-id="52414-113">如果你的 PBX 是时间段多路复用（TDM） PBX，则还必须在中介服务器和 PBX 之间部署 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="52414-113">If your PBX is a Time Division Multiplex (TDM) PBX, you must also deploy a PSTN gateway between Mediation Server and the PBX.</span></span>

<span data-ttu-id="52414-114">默认情况下，中介服务器与前端服务器并置。</span><span class="sxs-lookup"><span data-stu-id="52414-114">The Mediation Server is collocated with the Front End Server by default.</span></span> <span data-ttu-id="52414-115">由于性能原因，中介服务器也可以部署在独立的池中，如果您部署 SIP 中继，则强烈建议使用独立池。</span><span class="sxs-lookup"><span data-stu-id="52414-115">The Mediation Server can also be deployed in a stand-alone pool for performance reasons, or if you deploy SIP trunking, in which case the stand-alone pool is strongly recommended.</span></span>

<span data-ttu-id="52414-116">如果将直接 SIP 连接部署到支持媒体旁路和 DNS 负载平衡的合格 PSTN 网关，则不需要独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="52414-116">If you deploy Direct SIP connections to a qualified PSTN gateway that supports media bypass and DNS load balancing, a stand-alone Mediation Server pool is not necessary.</span></span> <span data-ttu-id="52414-117">若要将直接 SIP 连接部署到支持媒体旁路和 DNS 负载平衡的合格的 PSTN 网关，则不需要独立的中介服务器池，因为合格的网关能够将 DNS 负载平衡到中介服务器池，并且可以从池中的任何中介服务器接收通信。</span><span class="sxs-lookup"><span data-stu-id="52414-117">A stand-alone Mediation Server pool is not necessary because qualified gateways are capable of DNS load balancing to a pool of Mediation Servers and they can receive traffic from any Mediation Server in a pool.</span></span>

<span data-ttu-id="52414-118">如果已部署 IP-PBX 或连接到互联网电话服务供应商的会话边界控制器 (SBC)，只要满足以下其中一个条件，我们还建议您将中介服务器并置在前端池上：</span><span class="sxs-lookup"><span data-stu-id="52414-118">We also recommend that you collocate the Mediation Server on a Front End pool when you have deployed IP-PBXs or connect to an Internet Telephony Server Provider’s Session Border Controller (SBC), as long as any of the following conditions are met:</span></span>

  - <span data-ttu-id="52414-119">IP-PBX 或 SBC 已配置为接收来自池中的任何中介服务器的通信，并且可将通信统一路由到池中的所有中介服务器。</span><span class="sxs-lookup"><span data-stu-id="52414-119">The IP-PBX or SBC is configured to receive traffic from any Mediation Server in the pool and can route traffic uniformly to all Mediation Servers in the pool.</span></span>

  - <span data-ttu-id="52414-120">Ip-pbx 不支持媒体旁路，但承载中介服务器的前端池可以处理对不应用媒体旁路的呼叫的语音转码。</span><span class="sxs-lookup"><span data-stu-id="52414-120">The IP-PBX does not support media bypass, but the Front End pool that is hosting the Mediation Server can handle voice transcoding for calls to which media bypass does not apply.</span></span>

<span data-ttu-id="52414-121">您可以使用 Microsoft Lync Server 2013、规划工具来评估您要并置中介服务器的前端池是否可以处理负载。</span><span class="sxs-lookup"><span data-stu-id="52414-121">You can use the Microsoft Lync Server 2013, Planning Tool to evaluate whether the Front End pool where you want to collocate the Mediation Server can handle the load.</span></span> <span data-ttu-id="52414-122">如果您的环境不能满足这些要求，则必须部署独立的中介服务器池。</span><span class="sxs-lookup"><span data-stu-id="52414-122">If your environment cannot meet these requirements, then you must deploy a stand-alone Mediation Server pool.</span></span>

<span data-ttu-id="52414-123">中介服务器的主要功能如下所示：</span><span class="sxs-lookup"><span data-stu-id="52414-123">The main functions of the Mediation Server are as follows:</span></span>

  - <span data-ttu-id="52414-124">在 Lync Server 端对 SRTP 进行加密和解密</span><span class="sxs-lookup"><span data-stu-id="52414-124">Encrypting and decrypting SRTP on the Lync Server side</span></span>

  - <span data-ttu-id="52414-125">将 TCP 上的 SIP（针对不支持 TLS 的网关）转换为相互 TLS 上的 SIP</span><span class="sxs-lookup"><span data-stu-id="52414-125">Translating SIP over TCP (for gateways that do not support TLS) to SIP over mutual TLS</span></span>

  - <span data-ttu-id="52414-126">在 Lync Server 和中介服务器的网关对等之间转换媒体流</span><span class="sxs-lookup"><span data-stu-id="52414-126">Translating media streams between Lync Server and the gateway peer of the Mediation Server</span></span>

  - <span data-ttu-id="52414-127">将网络外部的客户端连接到内部 ICE 组件，使媒体可以遍历 NAT 和防火墙</span><span class="sxs-lookup"><span data-stu-id="52414-127">Connecting clients that are outside the network to internal ICE components, which enable media traversal of NAT and firewalls</span></span>

  - <span data-ttu-id="52414-128">充当网关不支持的呼叫流媒介，例如来自企业语音客户端的远程工作人员的呼叫</span><span class="sxs-lookup"><span data-stu-id="52414-128">Acting as an intermediary for call flows that a gateway does not support, such as calls from remote workers on an Enterprise Voice client</span></span>

  - <span data-ttu-id="52414-129">在包含 SIP 中继的部署中，配合 SIP 中继服务提供商提供 PSTN 支持，从而不再需要 PSTN 网关</span><span class="sxs-lookup"><span data-stu-id="52414-129">In deployments that include SIP trunking, working with the SIP trunking service provider to provide PSTN support, which eliminates the need for a PSTN gateway</span></span>

<span data-ttu-id="52414-130">下图显示了在与基本 PSTN 网关和企业语音基础结构通信时，中介服务器使用的信号和媒体协议。</span><span class="sxs-lookup"><span data-stu-id="52414-130">The following figure shows the signaling and media protocols that are used by the Mediation Server when communicating with a basic PSTN gateway and the Enterprise Voice infrastructure.</span></span>

<span data-ttu-id="52414-131">**中介服务器使用的信号和媒体协议**</span><span class="sxs-lookup"><span data-stu-id="52414-131">**Signaling and media protocols used by the Mediation Server**</span></span>

<span data-ttu-id="52414-132">![中介服务器协议图](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "中介服务器协议图")</span><span class="sxs-lookup"><span data-stu-id="52414-132">![Mediation Server Protocols diagram](images/Gg398399.c3d39ba0-e323-4a58-8f07-4e80d3278af2(OCS.15).jpg "Mediation Server Protocols diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="52414-133">如果在 PSTN 网关和中介服务器之间的网络上使用 TCP 或 RTP/RTCP （而不是 SRTP 或 SRTCP），我们建议采取措施来帮助确保网络的安全和隐私。</span><span class="sxs-lookup"><span data-stu-id="52414-133">If you are using TCP or RTP/RTCP (instead of SRTP or SRTCP) on the network between the PSTN gateway and the Mediation Server, we recommend that you take measures to help ensure the security and privacy of the network.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="52414-134">本部分内容</span><span class="sxs-lookup"><span data-stu-id="52414-134">In This Section</span></span>

  - [<span data-ttu-id="52414-135">Lync Server 2013 中的 M:N 中继</span><span class="sxs-lookup"><span data-stu-id="52414-135">M:N trunk in Lync Server 2013</span></span>](lync-server-2013-m-n-trunk.md)

  - [<span data-ttu-id="52414-136">Lync Server 2013 中的呼叫允许控制和中介服务器</span><span class="sxs-lookup"><span data-stu-id="52414-136">Call admission control and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-and-mediation-server.md)

  - [<span data-ttu-id="52414-137">Lync Server 2013 中的增强型9-1-1 （E9-1-1）和中介服务器</span><span class="sxs-lookup"><span data-stu-id="52414-137">Enhanced 9-1-1 (E9-1-1) and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md)

  - [<span data-ttu-id="52414-138">Lync Server 2013 中的媒体旁路和中介服务器</span><span class="sxs-lookup"><span data-stu-id="52414-138">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)

  - [<span data-ttu-id="52414-139">Lync Server 2013 中的中介服务器的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="52414-139">Components and topologies for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-mediation-server.md)

  - [<span data-ttu-id="52414-140">Lync Server 2013 中的中介服务器的部署指南</span><span class="sxs-lookup"><span data-stu-id="52414-140">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

