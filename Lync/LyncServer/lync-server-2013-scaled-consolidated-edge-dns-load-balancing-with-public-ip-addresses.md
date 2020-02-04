---
title: 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge, DNS load balancing with public IP addresses
ms:assetid: 2b854f6d-3d3f-4961-a5f8-a03f47740df0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204761(v=OCS.15)
ms:contentKeyID: 48183698
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 11da1e2b514c200ec82f1c6cb07c5c5b6cc79857
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses-in-lync-server-2013"></a><span data-ttu-id="026b3-102">Lync Server 2013 中的扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="026b3-102">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="026b3-103">_**主题上次修改时间：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="026b3-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="026b3-104">在边缘服务器池拓扑中，在数据中心的外围网络中，将两个或更多边缘服务器部署为负载平衡的池。</span><span class="sxs-lookup"><span data-stu-id="026b3-104">In the Edge Server pool topology, two or more Edge Servers are deployed as a load-balanced pool in the perimeter network of the data center.</span></span> <span data-ttu-id="026b3-105">域名系统（DNS）负载平衡用于外部和内部边缘接口的流量。</span><span class="sxs-lookup"><span data-stu-id="026b3-105">Domain Name System (DNS) load balancing is used for traffic to both the external and internal Edge interfaces.</span></span>

<span data-ttu-id="026b3-106">如果你的组织需要支持超过15000个 Access Edge 服务客户端连接，1000个 active Lync Server Web 会议服务客户端连接或500并发的 A/V 边缘会话以及/或边缘服务器的高可用性很重要，此拓扑提供可伸缩性和故障转移支持的优势。</span><span class="sxs-lookup"><span data-stu-id="026b3-106">If your organization requires support for more than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, or 500 concurrent A/V Edge sessions, and/or high availability of the Edge Server is important, this topology offers the advantages of scalability and failover support.</span></span>

<span data-ttu-id="026b3-107">该图不显示 Director、在边缘服务器与前端池或服务器之间部署的可选服务器角色。</span><span class="sxs-lookup"><span data-stu-id="026b3-107">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="026b3-108">有关董事拓扑的详细信息，请参阅[Lync Server 2013 中的 Director 所需的组件](lync-server-2013-components-required-for-the-director.md)。</span><span class="sxs-lookup"><span data-stu-id="026b3-108">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="026b3-109">该图表示单个反向代理。</span><span class="sxs-lookup"><span data-stu-id="026b3-109">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="026b3-110">所示的图针对方向和示例 IP 寻址，但不打算表示具有正确的传入和传出流量的实际通信流。</span><span class="sxs-lookup"><span data-stu-id="026b3-110">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="026b3-111">该图表示可能流量的高级视图。</span><span class="sxs-lookup"><span data-stu-id="026b3-111">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="026b3-112">在每个方案的端口摘要图中表示通信流与传入（对侦听端口）和传出（目标服务器或客户端）的通信流的详细信息。</span><span class="sxs-lookup"><span data-stu-id="026b3-112">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="026b3-113">例如，TCP 443 实际上是入站的（到边缘或反向代理），并且只是从协议（TCP）角度进行的双向流。</span><span class="sxs-lookup"><span data-stu-id="026b3-113">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="026b3-114">此外，该图显示了当发生 NAT （网络地址转换）时通信的性质（在入站上更改了目标地址时，在出站上更改了源地址）。</span><span class="sxs-lookup"><span data-stu-id="026b3-114">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="026b3-115">示例外部和内部防火墙以及服务器接口的显示仅供参考之用。</span><span class="sxs-lookup"><span data-stu-id="026b3-115">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="026b3-116">最后，显示默认网关和路由关系的示例（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="026b3-116">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="026b3-117">另请注意，图表使用<EM>.Com</EM> dns 区域表示反向代理服务器和边缘服务器的外部 DNS 区域，而<EM>.net</EM> DNS 区域则指内部 DNS 区域。</span><span class="sxs-lookup"><span data-stu-id="026b3-117">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="026b3-118">Microsoft Lync Server 2013 的新增功能支持 IPv6 寻址。</span><span class="sxs-lookup"><span data-stu-id="026b3-118">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="026b3-119">与 IPv4 寻址非常相似，必须以一种方式分配 IPv6 地址，这些地址是分配的 IPv6 地址空间的一部分。</span><span class="sxs-lookup"><span data-stu-id="026b3-119">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="026b3-120">本主题中的地址仅适用于示例。</span><span class="sxs-lookup"><span data-stu-id="026b3-120">The addresses in this topic are for example only.</span></span> <span data-ttu-id="026b3-121">你必须获取将在你的部署中运行的 IPv6 地址，提供正确的范围，并将与内部和外部寻址进行互操作。</span><span class="sxs-lookup"><span data-stu-id="026b3-121">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="026b3-122">Windows Server 提供对过渡的 IPv6 操作和 IPv4 到称为*双重堆栈*的 ipv6 通信非常重要的功能。</span><span class="sxs-lookup"><span data-stu-id="026b3-122">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="026b3-123">双重堆栈是 IPv4 和 IPv6 的单独且独特的网络堆栈。</span><span class="sxs-lookup"><span data-stu-id="026b3-123">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="026b3-124">双重堆栈使你可以同时为 IPv4 和 IPv6 分配寻址，并允许服务器根据其要求与其他主机和客户端进行通信。</span><span class="sxs-lookup"><span data-stu-id="026b3-124">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="026b3-125">将用于 IPv6 寻址的典型地址类型将是 IPv6 全局地址（类似于公用 IPv4 地址）、IPv6 唯一本地地址（类似于专用 IPv4 地址范围）和 IPv6 链接本地地址（类似于自动专用 IP）Windows Server for IPv4 中的地址）</span><span class="sxs-lookup"><span data-stu-id="026b3-125">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="026b3-126">IPv6 的网络地址转换技术（NAT）将允许 NAT IPv6 至 IPv4 （通常称为 NAT64）和 NAT IPv6 到 IPv6 （通常称为 NAT66）。</span><span class="sxs-lookup"><span data-stu-id="026b3-126">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="026b3-127">NAT 技术的存在意味着为 Lync Server Edge 服务器提供的五种方案仍然有效。</span><span class="sxs-lookup"><span data-stu-id="026b3-127">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]
> <span data-ttu-id="026b3-128">IPv6 是一个复杂的主题，需要仔细规划网络团队和 Internet 提供商，以确保您在 Windows 服务器级别和 Lync Server 2013 级别分配的地址将按预期工作。</span><span class="sxs-lookup"><span data-stu-id="026b3-128">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="026b3-129">请参阅本主题结尾处的链接，以了解有关 IPv6 寻址和规划的其他资源。</span><span class="sxs-lookup"><span data-stu-id="026b3-129">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="026b3-130">![7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537](images/JJ204761.7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537(OCS.15).jpg "7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537")</span><span class="sxs-lookup"><span data-stu-id="026b3-130">![7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537](images/JJ204761.7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537(OCS.15).jpg "7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537")</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="026b3-131">如果您使用的是 "呼叫许可控制" （CAC），仍然必须将 IPv4 地址分配给 Edge 服务器内部接口。</span><span class="sxs-lookup"><span data-stu-id="026b3-131">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="026b3-132">CAC 使用 IPv4 地址，并且必须具有它们才能运行。</span><span class="sxs-lookup"><span data-stu-id="026b3-132">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="026b3-133">本节内容</span><span class="sxs-lookup"><span data-stu-id="026b3-133">In This Section</span></span>

  - [<span data-ttu-id="026b3-134">Lync Server 2013 中的证书摘要 - 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="026b3-134">Certificate summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="026b3-135">Lync Server 2013 中的端口摘要 - 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="026b3-135">Port summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="026b3-136">Lync Server 2013 中的 DNS 摘要 - 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="026b3-136">DNS summary - Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="026b3-137">另请参阅</span><span class="sxs-lookup"><span data-stu-id="026b3-137">See Also</span></span>


[<span data-ttu-id="026b3-138">IP 版本6寻址体系结构</span><span class="sxs-lookup"><span data-stu-id="026b3-138">IP Version 6 Addressing Architecture</span></span>](http://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="026b3-139">IPv6 全局单播地址格式</span><span class="sxs-lookup"><span data-stu-id="026b3-139">IPv6 Global Unicast Address Format</span></span>](http://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="026b3-140">唯一本地 IPv6 单播地址</span><span class="sxs-lookup"><span data-stu-id="026b3-140">Unique Local IPv6 Unicast Addresses</span></span>](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

