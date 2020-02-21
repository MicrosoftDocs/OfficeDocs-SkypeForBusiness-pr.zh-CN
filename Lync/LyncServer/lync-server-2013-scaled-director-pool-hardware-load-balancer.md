---
title: Lync Server 2013：扩展的控制器池-硬件负载平衡器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - hardware load balancer
ms:assetid: cf34759a-b384-479c-855f-ea5e80a234b6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205316(v=OCS.15)
ms:contentKeyID: 48185585
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 178408e29e794fe39241920d715e271fc84f1c17
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200948"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---hardware-load-balancer-in-lync-server-2013"></a><span data-ttu-id="42c5a-102">Lync Server 2013 中的扩展控制器池-硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="42c5a-102">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42c5a-103">_**上次修改的主题：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="42c5a-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="42c5a-104">一个扩展的控制器池，在其中部署了多个控制器以处理更多容量并提供高可用性时，需要使用负载平衡将客户端和服务器通信分发到池的所有成员。</span><span class="sxs-lookup"><span data-stu-id="42c5a-104">A scaled Director pool, where there are more than one Director is deployed to handle additional capacity and to provide high availability, requires load balancing to distribute client and server communication to all members of the pool.</span></span> <span data-ttu-id="42c5a-105">控制器承载 web 服务的方式与前端池非常相似。</span><span class="sxs-lookup"><span data-stu-id="42c5a-105">A Director hosts web services much like a Front End pool.</span></span> <span data-ttu-id="42c5a-106">Web 服务需要实现硬件负载平衡。</span><span class="sxs-lookup"><span data-stu-id="42c5a-106">Hardware load balancing is required for the web services.</span></span>

<span data-ttu-id="42c5a-107">下列主题介绍了使用硬件负载平衡部署控制器池时的规划注意事项。</span><span class="sxs-lookup"><span data-stu-id="42c5a-107">The following topics describe the planning considerations for deploying a Director pool using hardware load balancing.</span></span> <span data-ttu-id="42c5a-108">如果打算使用控制器池的硬件负载平衡和 DNS 负载平衡，请参阅[Lync Server 2013 中的主题扩展的控制器池池-DNS 负载平衡和硬件负载平衡器](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)，它描述了该拓扑的规划要求。</span><span class="sxs-lookup"><span data-stu-id="42c5a-108">If you intend to use hardware load balancing and DNS load balancing for the Director pool, see the topic [Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md) that describes the planning requirements for that topology.</span></span>

<span data-ttu-id="42c5a-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span><span class="sxs-lookup"><span data-stu-id="42c5a-109">![cfa892b9-5b24-4245-b5bd-c5da21984eeb](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "cfa892b9-5b24-4245-b5bd-c5da21984eeb")</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="42c5a-110">本部分内容</span><span class="sxs-lookup"><span data-stu-id="42c5a-110">In This Section</span></span>

  - [<span data-ttu-id="42c5a-111">Lync Server 2013 中的证书摘要-扩展的控制器池、硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="42c5a-111">Certificate summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="42c5a-112">Lync Server 2013 中的端口摘要-扩展的控制器池、硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="42c5a-112">Port summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-director-pool-hardware-load-balancer.md)

  - [<span data-ttu-id="42c5a-113">Lync Server 2013 中的 DNS 摘要-扩展的控制器池、硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="42c5a-113">DNS summary - Scaled Director pool, hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

