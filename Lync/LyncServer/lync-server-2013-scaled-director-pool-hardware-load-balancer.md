---
title: Lync Server 2013：扩展的控制器池 - 硬件负载平衡器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled Director pool - hardware load balancer
ms:assetid: cf34759a-b384-479c-855f-ea5e80a234b6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205316(v=OCS.15)
ms:contentKeyID: 48185585
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0faf0983830466b44c91532f4fd80d72abb37fd7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="afe52-102">Lync Server 2013 中扩展的控制器池 - 硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="afe52-102">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afe52-103">_**主题上次修改时间:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="afe52-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="afe52-104">一个缩放的控制器池, 部署了多个控制器以处理更多容量并提供高可用性, 需要负载平衡才能将客户端和服务器通信分配给该池的所有成员。</span><span class="sxs-lookup"><span data-stu-id="afe52-104">A scaled Director pool, where there are more than one Director is deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="afe52-105">控制器承载 web 服务的方式非常类似于前端池。</span><span class="sxs-lookup"><span data-stu-id="afe52-105">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="afe52-106">Web 服务需要硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="afe52-106">Hardware load balancing is required for the web services.</span></span>

<span data-ttu-id="afe52-107">以下主题介绍了使用硬件负载平衡部署控制器池的规划注意事项。</span><span class="sxs-lookup"><span data-stu-id="afe52-107">The following topics describe the planning considerations for deploying a Director pool using hardware load balancing.</span></span> <span data-ttu-id="afe52-108">如果你打算为控制器池使用硬件负载平衡和 DNS 负载平衡, 请参阅[Lync Server 2013 中的主题 "扩展的控制器池"-"DNS 负载平衡" 和 "硬件负载平衡器](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)", 描述该拓扑的规划要求。</span><span class="sxs-lookup"><span data-stu-id="afe52-108">If you intend to use hardware load balancing and DNS load balancing for the Director pool, see the topic [Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="afe52-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span><span class="sxs-lookup"><span data-stu-id="afe52-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="afe52-110">本节内容</span><span class="sxs-lookup"><span data-stu-id="afe52-110">In This Section</span></span>

  - [<span data-ttu-id="afe52-111">Lync Server 2013 中的证书摘要 - 扩展的控制器池、硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="afe52-111">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="afe52-112">Lync Server 2013 中的端口摘要 - 扩展的控制器池、硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="afe52-112">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="afe52-113">Lync Server 2013 中的 DNS 摘要 - 扩展的控制器池、硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="afe52-113">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

