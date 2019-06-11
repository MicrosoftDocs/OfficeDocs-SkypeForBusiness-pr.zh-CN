---
title: 'Lync Server 2013: SIP 中继'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SIP trunking
ms:assetid: 7c586401-d0e5-4017-b3e1-fe5e7f8fc6db
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398619(v=OCS.15)
ms:contentKeyID: 48184615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9b7103b965c08df66d86eec99722ad03b937e407
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845852"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sip-trunking-in-lync-server-2013"></a><span data-ttu-id="f1071-102">Lync Server 2013 中的 SIP 中继</span><span class="sxs-lookup"><span data-stu-id="f1071-102">SIP trunking in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1071-103">_**主题上次修改时间:** 2012-08-13_</span><span class="sxs-lookup"><span data-stu-id="f1071-103">_**Topic Last Modified:** 2012-08-13_</span></span>

<span data-ttu-id="f1071-p101">会话初始协议 (SIP) 用于启动和管理基本电话服务和其他实时通信服务（例如即时消息、会议、状态检测和多媒体）的 IP 语音 (VoIP) 通信会话。本节提供实现 *SIP 中继*（一种 SIP 连接，可以扩展到本地网络以外）的规划信息。</span><span class="sxs-lookup"><span data-stu-id="f1071-p101">Session Initiation Protocol (SIP) is used to initiate and manage Voice over IP (VoIP) communications sessions for basic telephone service and for additional real-time communication services, such as instant messaging, conferencing, presence detection, and multimedia. This section provides planning information for implementing *SIP trunks*, a type of SIP connection that extends beyond the boundary of your local network.</span></span>

<div>

## <a name="what-is-sip-trunking"></a><span data-ttu-id="f1071-106">什么是 SIP 中继？</span><span class="sxs-lookup"><span data-stu-id="f1071-106">What is SIP Trunking?</span></span>

<span data-ttu-id="f1071-p102">SIP 中继是一种 IP 连接，在您的组织与防火墙以外的 Internet 电话服务提供商 (ITSP) 之间建立 SIP 通信链路。通常情况下，SIP 中继用于将组织的中央站点连接到 ITSP。在某些情况中，您也可以选择使用 SIP 中继将分支站点连接到 ITSP。</span><span class="sxs-lookup"><span data-stu-id="f1071-p102">A SIP trunk is an IP connection that establishes a SIP communications link between your organization and an Internet telephony service provider (ITSP) beyond your firewall. Typically, a SIP trunk is used to connect your organization’s central site to an ITSP. In some cases, you may also opt to use SIP trunking to connect your branch site to an ITSP.</span></span>

<div>

## <a name="sip-trunks-vs-direct-sip-connections"></a><span data-ttu-id="f1071-110">SIP 中继与直接 SIP 连接</span><span class="sxs-lookup"><span data-stu-id="f1071-110">SIP Trunks vs. Direct SIP Connections</span></span>

<span data-ttu-id="f1071-111">术语*中继*源自电路交换技术。</span><span class="sxs-lookup"><span data-stu-id="f1071-111">The term *trunk* is derived from circuit-switched technology.</span></span> <span data-ttu-id="f1071-112">它指的是连接电话交换设备的专用物理线路。</span><span class="sxs-lookup"><span data-stu-id="f1071-112">It refers to a dedicated physical line that connects telephone switching equipment.</span></span> <span data-ttu-id="f1071-113">与它们的前身一样, 时间段复用 (TDM) 中继, SIP 中继是两个独立 SIP 网络之间的连接, 即 Lync Server 2013 企业版和 ITSP。</span><span class="sxs-lookup"><span data-stu-id="f1071-113">Like their predecessor, time division multiplexing (TDM) trunks, SIP trunks are connections between two separate SIP networks—the Lync Server 2013 enterprise and the ITSP.</span></span> <span data-ttu-id="f1071-114">SIP 中继是可以通过任何支持的 SIP 中继连接类型建立的虚拟连接，这一点与电路交换中继不同。</span><span class="sxs-lookup"><span data-stu-id="f1071-114">Unlike circuit-switched trunks, SIP trunks are virtual connections that can be established over any of the supported SIP trunking connection types.</span></span> <span data-ttu-id="f1071-115">有关支持的连接类型的详细信息, 请参阅[如何在 Lync Server 2013 中实现 SIP 中继？](lync-server-2013-how-do-i-implement-sip-trunking.md)。</span><span class="sxs-lookup"><span data-stu-id="f1071-115">For details about the supported connection types, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span>

<span data-ttu-id="f1071-116">而直接 SIP 连接指的是不能跨越本地网络边界的 SIP 连接（也就是说，它们连接到内部网络内的公用电话交换网 (PSTN) 网关或专用交换机 (PBX)）。</span><span class="sxs-lookup"><span data-stu-id="f1071-116">Direct SIP connections, on the other hand, are SIP connections that do not cross the local network boundary (that is, they connect to a public switched telephone network (PSTN) gateway or private branch exchange (PBX) within your internal network).</span></span> <span data-ttu-id="f1071-117">有关如何将直接 SIP 连接与 Lync Server 2013 配合使用的详细信息, 请参阅[Lync server 2013 中的直接 sip 连接](lync-server-2013-direct-sip-connections.md)。</span><span class="sxs-lookup"><span data-stu-id="f1071-117">For details about how you can use direct SIP connections with Lync Server 2013, see [Direct SIP connections in Lync Server 2013](lync-server-2013-direct-sip-connections.md).</span></span>

</div>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f1071-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="f1071-118">In This Section</span></span>

  - [<span data-ttu-id="f1071-119">Lync Server 2013 中的 SIP 中继概述</span><span class="sxs-lookup"><span data-stu-id="f1071-119">Overview of SIP trunking in Lync Server 2013</span></span>](lync-server-2013-overview-of-sip-trunking.md)

  - [<span data-ttu-id="f1071-120">如何在 Lync Server 2013 中实施 SIP 中继？</span><span class="sxs-lookup"><span data-stu-id="f1071-120">How do I implement SIP trunking in Lync Server 2013?</span></span>](lync-server-2013-how-do-i-implement-sip-trunking.md)

  - [<span data-ttu-id="f1071-121">Lync Server 2013 中用于 SIP 中继的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="f1071-121">Components and topologies for SIP trunking in Lync Server 2013</span></span>](lync-server-2013-components-and-topologies-for-sip-trunking.md)

  - [<span data-ttu-id="f1071-122">Branch site SIP trunking in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f1071-122">Branch site SIP trunking in Lync Server 2013</span></span>](lync-server-2013-branch-site-sip-trunking.md)

  - [<span data-ttu-id="f1071-123">Lync Server 2013 的 SIP 中继部署清单</span><span class="sxs-lookup"><span data-stu-id="f1071-123">SIP trunk deployment checklist for Lync Server 2013</span></span>](lync-server-2013-sip-trunk-deployment-checklist.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

