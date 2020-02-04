---
title: Lync Server 2013：设置边缘服务器的网络接口
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfbae47a5f5e99e603e3f095a2e07dbb9b49515f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764638"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a><span data-ttu-id="0719f-102">在 Lync Server 2013 中设置边缘服务器的网络接口</span><span class="sxs-lookup"><span data-stu-id="0719f-102">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0719f-103">_**主题上次修改时间：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="0719f-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="0719f-104">每个边缘服务器都是具有外部接口和内部接口的多宿主计算机。</span><span class="sxs-lookup"><span data-stu-id="0719f-104">Each Edge Server is a multihomed computer with external and internal facing interfaces.</span></span> <span data-ttu-id="0719f-105">适配器域名系统（DNS）设置取决于外围网络中是否存在 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="0719f-105">The adapter Domain Name System (DNS) settings depend on whether there are DNS servers in the perimeter network.</span></span> <span data-ttu-id="0719f-106">如果外围设备存在 DNS 服务器，则它们必须具有一个区域，其中包含下一跃点服务器或池（即 Director 或指定的前端池）的一个或多个 DNS A 记录，并且对于外部查询，它们引用其他公共 DNS 服务器的名称查找。</span><span class="sxs-lookup"><span data-stu-id="0719f-106">If DNS servers exist in the perimeter, they must have a zone containing one or more DNS A records for the next hop server or pool (that is, either a Director or a designated Front End pool), and for external queries they refer name lookups to other public DNS servers.</span></span> <span data-ttu-id="0719f-107">如果外围设备中不存在任何 DNS 服务器，则边缘服务器使用外部 DNS 服务器解析 Internet 名称查找，并且每台边缘服务器使用主机将下一个跃点服务器名称解析为 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="0719f-107">If no DNS servers exist in the perimeter, the Edge Server(s) use external DNS servers to resolve Internet name lookups, and each Edge Server uses a HOST to resolve the next hop server names to IP addresses.</span></span>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全" alt="security" /><span data-ttu-id="0719f-109">安全说明：</span><span class="sxs-lookup"><span data-stu-id="0719f-109">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="0719f-110">出于安全考虑，我们建议你不要让 Edge 服务器访问位于内部网络中的 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="0719f-110">For security reasons, we recommend that you do not have your Edge Servers access a DNS server located in the internal network.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="0719f-111">在外围网络中配置具有 DNS 服务器的接口</span><span class="sxs-lookup"><span data-stu-id="0719f-111">To configure interfaces with DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="0719f-112">为每台边缘服务器安装两个网络适配器，一个用于面向内部的接口，另一个用于面向外部的接口。</span><span class="sxs-lookup"><span data-stu-id="0719f-112">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0719f-113">内部子网和外部子网不得相互路由。</span><span class="sxs-lookup"><span data-stu-id="0719f-113">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="0719f-114">在外部接口上，在外部外围网络（也称为 DMZ、隔离区和屏蔽子网）子网中配置三个静态 IP 地址，并将默认网关指向外部防火墙的内部接口。</span><span class="sxs-lookup"><span data-stu-id="0719f-114">On the external interface, configure three static IP addresses on the external perimeter network (also known as DMZ, demilitarized zone, and screened subnet) subnet, and point the default gateway to the internal interface of the external firewall.</span></span> <span data-ttu-id="0719f-115">将适配器 DNS 设置配置为指向一对外围 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="0719f-115">Configure adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0719f-116">可以为此接口使用最少的一个 IP 地址，但要执行此操作，您需要将端口分配更改为非标准值。</span><span class="sxs-lookup"><span data-stu-id="0719f-116">It is possible to use as few as one IP address for this interface, but to do this you need to change the port assignments to non-standard values.</span></span> <span data-ttu-id="0719f-117">在拓扑生成器中创建拓扑时，可以确定此情况。</span><span class="sxs-lookup"><span data-stu-id="0719f-117">You determine this when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="0719f-118">在内部接口上，在内部外围网络子网中配置一个静态 IP 地址，不要设置默认网关。</span><span class="sxs-lookup"><span data-stu-id="0719f-118">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="0719f-119">将适配器 DNS 设置配置为指向至少一个 DNS 服务器，最好是一对外围 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="0719f-119">Configure adapter DNS settings to point to at least one DNS server, preferably a pair of perimeter DNS servers.</span></span>

4.  <span data-ttu-id="0719f-120">在内部接口上为客户端、Lync Server 2013 和 Exchange 统一消息（UM）服务器所驻留的所有内部网络创建永久静态路由。</span><span class="sxs-lookup"><span data-stu-id="0719f-120">Create persistent static routes on the internal interface to all internal networks where clients, Lync Server 2013, and Exchange Unified Messaging (UM) servers reside.</span></span>

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="0719f-121">在外围网络中配置没有 DNS 服务器的接口</span><span class="sxs-lookup"><span data-stu-id="0719f-121">To configure interfaces without DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="0719f-122">为每台边缘服务器安装两个网络适配器，一个用于面向内部的接口，另一个用于面向外部的接口。</span><span class="sxs-lookup"><span data-stu-id="0719f-122">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="0719f-123">内部子网和外部子网不得相互路由。</span><span class="sxs-lookup"><span data-stu-id="0719f-123">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="0719f-124">在外部接口上，在外部外围网络子网中配置三个静态 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="0719f-124">On the external interface, configure three static IP addresses on the external perimeter network subnet.</span></span> <span data-ttu-id="0719f-125">您还可以在外部接口上配置默认网关。</span><span class="sxs-lookup"><span data-stu-id="0719f-125">You also configure the default gateway on the external interface.</span></span> <span data-ttu-id="0719f-126">例如，将面向 Internet 的路由器或外部防火墙定义为默认网关。</span><span class="sxs-lookup"><span data-stu-id="0719f-126">For example, define the Internet-facing router or the external firewall as the default gateway.</span></span> <span data-ttu-id="0719f-127">将 DNS 设置配置为指向 DNS 服务器，最好使用一对外部 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="0719f-127">Configure DNS settings to point to a DNS server, preferably to a pair of external DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="0719f-128">可以使用，但不推荐使用一个 IP 地址作为外部接口。</span><span class="sxs-lookup"><span data-stu-id="0719f-128">It is possible, but not recommended, to use as few as one IP address for the external interface.</span></span> <span data-ttu-id="0719f-129">若要允许此操作，你需要将端口分配更改为非标准值，并离开默认端口443（通常为客户端通信 "防火墙友好"）。</span><span class="sxs-lookup"><span data-stu-id="0719f-129">To allow this to work, you need to change the port assignments to non-standard values, and away from the default port 443 that is typically “firewall friendly” for client communication.</span></span> <span data-ttu-id="0719f-130">在拓扑生成器中创建拓扑时，确定 IP 地址设置和端口设置。</span><span class="sxs-lookup"><span data-stu-id="0719f-130">You determine the IP address setting and the port settings when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="0719f-131">在内部接口上，在内部外围网络子网中配置一个静态 IP 地址，不要设置默认网关。</span><span class="sxs-lookup"><span data-stu-id="0719f-131">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="0719f-132">将适配器 DNS 设置保留为空。</span><span class="sxs-lookup"><span data-stu-id="0719f-132">Leave adapter DNS settings empty.</span></span>

4.  <span data-ttu-id="0719f-133">在内部接口上为运行 Lync Server 2013 的 Lync 客户端或服务器所驻留的所有内部网络创建永久静态路由。</span><span class="sxs-lookup"><span data-stu-id="0719f-133">Create persistent static routes on the internal interface to all internal networks where Lync clients or servers running Lync Server 2013 reside.</span></span>

5.  <span data-ttu-id="0719f-134">编辑每台边缘服务器上的主机文件，以包含下一个跃点服务器或虚拟 IP （VIP）的记录（该记录将是 Director、标准版服务器，或在拓扑结构生成器中配置为边缘服务器下一跃点服务器的前端池）。</span><span class="sxs-lookup"><span data-stu-id="0719f-134">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP) (the record will be the Director, Standard Edition server, or a Front End pool that was configured as the Edge Server next hop address in Topology Builder).</span></span> <span data-ttu-id="0719f-135">如果你使用的是 DNS 负载平衡，请为下一个跃点池的每个成员包含一行。</span><span class="sxs-lookup"><span data-stu-id="0719f-135">If you are using DNS load balancing, include a line for each member of the next hop pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

