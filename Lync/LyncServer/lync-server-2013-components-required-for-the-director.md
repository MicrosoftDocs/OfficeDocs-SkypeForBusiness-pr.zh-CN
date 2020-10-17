---
title: Lync Server 2013：控制器所需的组件
description: Lync Server 2013：控制器所需的组件。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for the Director
ms:assetid: 15c7c8d4-b93f-4386-b2d1-d76dab8f801e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398228(v=OCS.15)
ms:contentKeyID: 48183502
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 57f717b9ddb9557f212321cdab075713a4b85c2d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549498"
---
# <a name="components-required-for-the-director-in-lync-server-2013"></a><span data-ttu-id="93f5b-103">Lync Server 2013 中的控制器所需的组件</span><span class="sxs-lookup"><span data-stu-id="93f5b-103">Components required for the Director in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93f5b-104">_**上次修改的主题：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="93f5b-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="93f5b-105">创建和配置控制器所需的唯一组件是部署控制器服务器角色。</span><span class="sxs-lookup"><span data-stu-id="93f5b-105">The only component required to create and configure a Director is to deploy the Director server role.</span></span> <span data-ttu-id="93f5b-106">为此，请使用拓扑生成器，并在 "控制器池" 节点中定义单个计算机池或多台计算机池。</span><span class="sxs-lookup"><span data-stu-id="93f5b-106">You do this by using Topology Builder and define either a single computer pool or a multiple computer pool in the Director pool node.</span></span> <span data-ttu-id="93f5b-107">定义控制器池或控制器池之后，在将成为控制器的计算机上运行 Lync Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="93f5b-107">After you have defined the Director or Director pool, run the Lync Server Deployment Wizard on the computer that will be a Director.</span></span> <span data-ttu-id="93f5b-108">对于控制器池，在将成为池成员的每台服务器上运行 Lync Server 部署向导。</span><span class="sxs-lookup"><span data-stu-id="93f5b-108">In the case of a Director pool, you run the Lync Server Deployment Wizard on each server that will be a member of the pool.</span></span>

<div>

## <a name="topologies"></a><span data-ttu-id="93f5b-109">拓扑</span><span class="sxs-lookup"><span data-stu-id="93f5b-109">Topologies</span></span>

<span data-ttu-id="93f5b-110">您可以实现单个控制器服务器或一个控制器池。</span><span class="sxs-lookup"><span data-stu-id="93f5b-110">You can implement a single Director server or a Director pool.</span></span> <span data-ttu-id="93f5b-111">Director 始终是一个单独的服务器或池，而不是并置与 Lync Server 2013 中的任何其他服务器角色。</span><span class="sxs-lookup"><span data-stu-id="93f5b-111">The Director is always a separate server or pool, not collocated with any other server role in Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="93f5b-112">如果不部署控制器，前端服务器或前端池将承担控制器角色。</span><span class="sxs-lookup"><span data-stu-id="93f5b-112">If you do not deploy Directors, the Front End Server or Front End pool will assume the Director role.</span></span>



</div>

<span data-ttu-id="93f5b-113">必须对控制器池进行负载平衡。</span><span class="sxs-lookup"><span data-stu-id="93f5b-113">A pool of Directors must be load balanced.</span></span> <span data-ttu-id="93f5b-114">可选择下列方法之一：</span><span class="sxs-lookup"><span data-stu-id="93f5b-114">You can do one of the following:</span></span>

  - <span data-ttu-id="93f5b-115">创建一个拓扑，以便使用硬件负载平衡器对其他流量类型实现 Web 服务和域名系统 (DNS) 负载平衡。</span><span class="sxs-lookup"><span data-stu-id="93f5b-115">Create a topology that uses a hardware load balancer for web services and Domain Name System (DNS) load balancing for the other traffic types.</span></span>
    
    [<span data-ttu-id="93f5b-116">Lync Server 2013 中的扩展控制器池-DNS 负载平衡和硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="93f5b-116">Scaled Director pool - DNS load balancing and hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)

  - <span data-ttu-id="93f5b-117">创建使用硬件负载平衡器进行控制器池所需的负载平衡的拓扑。</span><span class="sxs-lookup"><span data-stu-id="93f5b-117">Create a topology that uses a hardware load balancer for load balancing needed for the Director pool.</span></span>
    
    [<span data-ttu-id="93f5b-118">Lync Server 2013 中的扩展控制器池-硬件负载平衡器</span><span class="sxs-lookup"><span data-stu-id="93f5b-118">Scaled Director pool - hardware load balancer in Lync Server 2013</span></span>](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

