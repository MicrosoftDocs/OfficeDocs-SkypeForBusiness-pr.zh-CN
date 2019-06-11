---
title: Lync Server 2013：控制器所需的组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components required for the Director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48183502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c80002d0c91853be1523f6ce1bedfdccef72a68
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837510"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-the-director-in-lync-server-2013"></a><span data-ttu-id="9448c-102">Lync Server 2013 中控制器所需的组件</span><span class="sxs-lookup"><span data-stu-id="9448c-102">Components required for the Director in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9448c-103">_**主题上次修改时间:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="9448c-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="9448c-104">创建和配置 Director 所需的唯一组件是部署 Director 服务器角色。</span><span class="sxs-lookup"><span data-stu-id="9448c-104">The only component required to create and configure a Director is to deploy the Director server role.</span></span> <span data-ttu-id="9448c-105">可通过使用拓扑生成器并在 "控制器池" 节点中定义单个计算机池或多台计算机池来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="9448c-105">You do this by using Topology Builder and define either a single computer pool or a multiple computer pool in the Director pool node.</span></span> <span data-ttu-id="9448c-106">定义 Director 或控制器池后, 请在将成为 Director 的计算机上运行 Lync Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="9448c-106">After you have defined the Director or Director pool, run the Lync Server Deployment Wizard on the computer that will be a Director.</span></span> <span data-ttu-id="9448c-107">在控制器池的情况下, 你在将成为池成员的每台服务器上运行 Lync Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="9448c-107">In the case of a Director pool, you run the Lync Server Deployment Wizard on each server that will be a member of the pool.</span></span>

<div>

## <a name="topologies"></a><span data-ttu-id="9448c-108">朴</span><span class="sxs-lookup"><span data-stu-id="9448c-108">Topologies</span></span>

<span data-ttu-id="9448c-109">你可以实现单个控制器服务器或控制器池。</span><span class="sxs-lookup"><span data-stu-id="9448c-109">You can implement a single Director server or a Director pool.</span></span> <span data-ttu-id="9448c-110">Director 始终是单独的服务器或池, 而不是在 Lync Server 2013 中与任何其他服务器角色 collocated。</span><span class="sxs-lookup"><span data-stu-id="9448c-110">The Director is always a separate server or pool, not collocated with any other server role in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="9448c-111">如果不部署控制器, 前端服务器或前端池将承担 Director 角色。</span><span class="sxs-lookup"><span data-stu-id="9448c-111">If you do not deploy Directors, the Front End Server or Front End pool will assume the Director role.</span></span>



</div>

<span data-ttu-id="9448c-112">控制器池必须进行负载平衡。</span><span class="sxs-lookup"><span data-stu-id="9448c-112">A pool of Directors must be load balanced.</span></span> <span data-ttu-id="9448c-113">您可以执行下列操作之一:</span><span class="sxs-lookup"><span data-stu-id="9448c-113">You can do one of the following:</span></span>

  - <span data-ttu-id="9448c-114">创建一个拓扑, 该拓扑使用针对其他流量类型的 web 服务和域名系统 (DNS) 负载平衡的硬件负载平衡器。</span><span class="sxs-lookup"><span data-stu-id="9448c-114">Create a topology that uses a hardware load balancer for web services and Domain Name System (DNS) load balancing for the other traffic types.</span></span>
    
    [<span data-ttu-id="9448c-115">Lync Server 2013 中扩展的控制器池 - DNS 负载平衡和硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="9448c-115">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - <span data-ttu-id="9448c-116">创建一个拓扑, 该拓扑使用硬件负载平衡器实现控制器池所需的负载平衡。</span><span class="sxs-lookup"><span data-stu-id="9448c-116">Create a topology that uses a hardware load balancer for load balancing needed for the Director pool.</span></span>
    
    [<span data-ttu-id="9448c-117">Lync Server 2013 中扩展的控制器池 - 硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="9448c-117">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

