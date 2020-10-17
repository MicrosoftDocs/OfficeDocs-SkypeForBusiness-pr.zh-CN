---
title: Lync Server 2013：设置边缘服务器的网络接口
description: Lync Server 2013：设置边缘服务器的网络接口。
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
ms.openlocfilehash: 576ca8670a34be022e3df0a699edaf0df10f5b70
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550468"
---
# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a><span data-ttu-id="78599-103">在 Lync Server 2013 中设置边缘服务器的网络接口</span><span class="sxs-lookup"><span data-stu-id="78599-103">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="78599-104">_**上次修改的主题：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="78599-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="78599-p101">每台边缘服务器均是具有面向外部和内部的接口的多宿主计算机。适配器域名系统 (DNS) 设置取决于外围网络中是否有 DNS 服务器。如果外围中存在 DNS 服务器，则这些服务器必须有一个包含有关下一个跃点服务器或池（即，控制器或指定的前端池）的一个或多个 DNS A 记录的区域，而对于外部查询，则会对其他公共 DNS 服务器进行名称查找。如果外围中不存在 DNS 服务器，则边缘服务器将使用外部 DNS 服务器解析 Internet 名称查找，并且每个边缘服务器会使用 HOST 将下一个跃点服务器名称解析为 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="78599-p101">Each Edge Server is a multihomed computer with external and internal facing interfaces. The adapter Domain Name System (DNS) settings depend on whether there are DNS servers in the perimeter network. If DNS servers exist in the perimeter, they must have a zone containing one or more DNS A records for the next hop server or pool (that is, either a Director or a designated Front End pool), and for external queries they refer name lookups to other public DNS servers. If no DNS servers exist in the perimeter, the Edge Server(s) use external DNS servers to resolve Internet name lookups, and each Edge Server uses a HOST to resolve the next hop server names to IP addresses.</span></span>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="保护" alt="security" /><span data-ttu-id="78599-110">安全说明：</span><span class="sxs-lookup"><span data-stu-id="78599-110">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="78599-111">为安全起见，建议不要让边缘服务器访问位于内部网络的 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="78599-111">For security reasons, we recommend that you do not have your Edge Servers access a DNS server located in the internal network.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="78599-112">配置接口（外围网络中存在 DNS 服务器）</span><span class="sxs-lookup"><span data-stu-id="78599-112">To configure interfaces with DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="78599-113">为每台边缘服务器安装两个网络适配器，一个用于面向内部的接口，另一个用于面向外部的接口。</span><span class="sxs-lookup"><span data-stu-id="78599-113">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="78599-114">内部子网和外部子网不得相互路由。</span><span class="sxs-lookup"><span data-stu-id="78599-114">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="78599-p102">在外部接口上，在外部外围网络（也称为 DMZ、外围安全区域或屏蔽子网）子网上配置三个静态 IP 地址，并将默认网关指向外部防火墙的内部接口。配置适配器 DNS 设置以指向一对外围 DNS 服务器。</span><span class="sxs-lookup"><span data-stu-id="78599-p102">On the external interface, configure three static IP addresses on the external perimeter network (also known as DMZ, demilitarized zone, and screened subnet) subnet, and point the default gateway to the internal interface of the external firewall. Configure adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="78599-117">可以只为此接口分配一个 IP 地址，但是这样做的话，您需要将端口分配更改为非标准值。</span><span class="sxs-lookup"><span data-stu-id="78599-117">It is possible to use as few as one IP address for this interface, but to do this you need to change the port assignments to non-standard values.</span></span> <span data-ttu-id="78599-118">在拓扑生成器中创建拓扑时，可以确定这一点。</span><span class="sxs-lookup"><span data-stu-id="78599-118">You determine this when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="78599-p104">在内部接口上，在内部外围网络子网上配置一个静态 IP 地址，但不要设置默认网关。配置适配器 DNS 设置，以指向至少一台 DNS 服务器（最好是一对外围 DNS 服务器）。</span><span class="sxs-lookup"><span data-stu-id="78599-p104">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway. Configure adapter DNS settings to point to at least one DNS server, preferably a pair of perimeter DNS servers.</span></span>

4.  <span data-ttu-id="78599-121">在内部接口上创建指向所有内部网络（客户端、Lync Server 2013 和 Exchange 统一消息 (UM) 服务器所驻留的所有内部网络）的永久静态路由。</span><span class="sxs-lookup"><span data-stu-id="78599-121">Create persistent static routes on the internal interface to all internal networks where clients, Lync Server 2013, and Exchange Unified Messaging (UM) servers reside.</span></span>

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="78599-122">配置接口（外围网络中不存在 DNS 服务器）</span><span class="sxs-lookup"><span data-stu-id="78599-122">To configure interfaces without DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="78599-123">为每台边缘服务器安装两个网络适配器，一个用于面向内部的接口，另一个用于面向外部的接口。</span><span class="sxs-lookup"><span data-stu-id="78599-123">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="78599-124">内部子网和外部子网不得相互路由。</span><span class="sxs-lookup"><span data-stu-id="78599-124">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="78599-p105">在外部接口上，在外部外围网络子网上配置三个静态 IP 地址。还可在外部接口上配置默认网关。例如，定义面向 Internet 的路由器或外部防火墙作为默认网关。将 DNS 设置配置为指向一台 DNS 服务器（最好是一对外部 DNS 服务器）。</span><span class="sxs-lookup"><span data-stu-id="78599-p105">On the external interface, configure three static IP addresses on the external perimeter network subnet. You also configure the default gateway on the external interface. For example, define the Internet-facing router or the external firewall as the default gateway. Configure DNS settings to point to a DNS server, preferably to a pair of external DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="78599-129">可以只对外部接口使用一个 IP 地址，但不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="78599-129">It is possible, but not recommended, to use as few as one IP address for the external interface.</span></span> <span data-ttu-id="78599-130">若要达到此目的，您需要将端口分配更改为非标准值，并且这个值不是通常对客户端通信“防火墙友好”的默认端口 443。</span><span class="sxs-lookup"><span data-stu-id="78599-130">To allow this to work, you need to change the port assignments to non-standard values, and away from the default port 443 that is typically “firewall friendly” for client communication.</span></span> <span data-ttu-id="78599-131">在拓扑生成器中创建拓扑时，可以确定 IP 地址设置和端口设置。</span><span class="sxs-lookup"><span data-stu-id="78599-131">You determine the IP address setting and the port settings when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="78599-p107">在内部接口上，在内部外围网络子网上配置一个静态 IP 地址，但不要设置默认网关。将适配器 DNS 设置留空。</span><span class="sxs-lookup"><span data-stu-id="78599-p107">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway. Leave adapter DNS settings empty.</span></span>

4.  <span data-ttu-id="78599-134">在内部接口上为运行 Lync Server 2013 的 Lync 客户端或服务器所驻留的所有内部网络创建永久静态路由。</span><span class="sxs-lookup"><span data-stu-id="78599-134">Create persistent static routes on the internal interface to all internal networks where Lync clients or servers running Lync Server 2013 reside.</span></span>

5.  <span data-ttu-id="78599-135">编辑每台边缘服务器上的主机文件，以包含下一个跃点服务器或虚拟 IP (VIP) 的记录 (该记录将是 Director、Standard Edition Server 或在拓扑生成器) 中配置为边缘服务器下一个跃点地址的前端池。</span><span class="sxs-lookup"><span data-stu-id="78599-135">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP) (the record will be the Director, Standard Edition server, or a Front End pool that was configured as the Edge Server next hop address in Topology Builder).</span></span> <span data-ttu-id="78599-136">如果正在使用 DNS 负载平衡，请包含下一个跃点池中所有成员的行。</span><span class="sxs-lookup"><span data-stu-id="78599-136">If you are using DNS load balancing, include a line for each member of the next hop pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

