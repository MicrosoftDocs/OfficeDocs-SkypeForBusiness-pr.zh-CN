---
title: Lync Server 2013：扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）
description: Lync Server 2013：扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: c7ca4ca8-c639-4d93-86d7-8891170cacbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398823(v=OCS.15)
ms:contentKeyID: 48185369
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3a1b668902059ef2680525b884d8b2c5e8486260
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577698"
---
# <a name="scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a><span data-ttu-id="8b0ca-103">在 Lync Server 2013 中，扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="8b0ca-103">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b0ca-104">_**上次修改的主题：** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="8b0ca-104">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="8b0ca-p101">在边缘服务器池拓扑中，数据中心的外围网络中部署了两台或更多边缘服务器作为负载平衡池。域名系统 (DNS) 负载平衡用于到外部边缘接口和内部边缘接口的流量。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-p101">In the Edge Server pool topology, two or more Edge Servers are deployed as a load-balanced pool in the perimeter network of the data center. Domain Name System (DNS) load balancing is used for traffic to both the external and internal Edge interfaces.</span></span>

<span data-ttu-id="8b0ca-107">如果您的组织需要支持超过15000个访问边缘服务客户端连接，则1000个活动 Lync Server Web 会议服务客户端连接，或500并发 A/V 边缘会话以及/或边缘服务器的高可用性。此拓扑提供了可伸缩性和故障转移支持的优势。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-107">If your organization requires support for more than 15,000 Access Edge service client connections, 1,000 active Lync Server Web Conferencing service client connections, or 500 concurrent A/V Edge sessions, and/or high availability of the Edge Server is important, this topology offers the advantages of scalability and failover support.</span></span>

<span data-ttu-id="8b0ca-108">该图不显示控制器，即在边缘服务器与前端池或服务器之间部署在内部网络中的可选服务器角色。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-108">The figure does not show Directors, an optional server role deployed in the internal network between the Edge Servers and your Front End pools or server.</span></span> <span data-ttu-id="8b0ca-109">有关控制器拓扑的详细信息，请参阅 [Lync Server 2013 中的控制器所需的组件](lync-server-2013-components-required-for-the-director.md)。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-109">For details about the topology for Directors, see [Components required for the Director in Lync Server 2013](lync-server-2013-components-required-for-the-director.md).</span></span> <span data-ttu-id="8b0ca-110">此图表示一个反向代理。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-110">The figure represents a single reverse proxy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8b0ca-111">所显示的图适用于方向和示例 IP 寻址，但并不旨在代表具有正确传入和传出流量的实际通信流。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-111">The figure shown is for orientation and example IP addressing, but does not intend to represent actual communication flows with the correct incoming and outgoing traffic.</span></span> <span data-ttu-id="8b0ca-112">该图代表可能流量的高级视图。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-112">The figure represents a high level view of possible traffic.</span></span> <span data-ttu-id="8b0ca-113">与传入（至侦听端口）和传出（至目标服务器或客户端）相关的通信流的详细信息显示在每个方案的“端口摘要”图中。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-113">Details for traffic flow as they pertain to incoming (to listening ports) and outgoing (to destination servers or clients) is represented in the Port Summary diagram in each scenario.</span></span> <span data-ttu-id="8b0ca-114">例如，TCP 443 实际上仅限入站（至边缘或反向代理），而且从协议 (TCP) 的角度来看只是一种双向流。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-114">For example, TCP 443 is actually inbound (to the Edge or reverse proxy) only, and is only a two-way flow from a protocol (TCP) perspective.</span></span> <span data-ttu-id="8b0ca-115">此外，该图显示流量的特性，因为在发生 NAT（网络地址转换）时它会发生更改（目标地址在入站上更改，源地址在出站上更改）。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-115">Additionally, the figure shows the nature of traffic as it changes when NAT (network address translation) occurs (destination address is changed on inbound, source address is changed on outbound).</span></span> <span data-ttu-id="8b0ca-116">显示的外部和内部防火墙示例以及服务器界面仅供参考。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-116">Example external and internal firewall, and server interfaces are shown for reference purposes only.</span></span> <span data-ttu-id="8b0ca-117">最后，显示默认网关和路由关系示例（如果适用）。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-117">Finally, example default gateway and route relationships are shown, where applicable.</span></span> <span data-ttu-id="8b0ca-118">另请注意，该图表使用 <EM>.Com</EM> dns 区域表示反向代理服务器和边缘服务器的外部 DNS 区域，而 <EM>.net</EM> DNS 区域引用内部 dns 区域。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-118">Note also that the diagram uses the <EM>.com</EM> DNS zone to represent the external DNS zone for both reverse proxy and Edge Servers, and the <EM>.net</EM> DNS zone refers to the internal DNS zone.</span></span>



</div>

<span data-ttu-id="8b0ca-119">Microsoft Lync Server 2013 的新增支持 IPv6 寻址。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-119">New to Microsoft Lync Server 2013 is support for IPv6 addressing.</span></span> <span data-ttu-id="8b0ca-120">与 IPv4 寻址非常相似，必须以一种适当的方式分配 IPv6 地址，使这些地址属于所分配的 IPv6 地址空间的一部分。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-120">Much like IPv4 addressing, IPv6 addresses must be assigned in such a way that the addresses are part of your assigned IPv6 address space.</span></span> <span data-ttu-id="8b0ca-121">本主题中的地址仅用作示例。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-121">The addresses in this topic are for example only.</span></span> <span data-ttu-id="8b0ca-122">您必须获取将在您的部署中正常运行、提供正确的范围并将与内部和外部寻址进行互操作的 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-122">You must acquire IPv6 addresses that will function in your deployment, provide the correct scope and will interoperate with internal and external addressing.</span></span> <span data-ttu-id="8b0ca-123">Windows Server 提供了一项功能，这一点对将 IPv6 操作和 IPv4 转换为称作 *双重堆栈*的 ipv6 通信非常重要。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-123">Windows Server provides a feature that is important to transitional IPv6 operation and IPv4 to IPv6 communication called the *dual stack*.</span></span> <span data-ttu-id="8b0ca-124">双协议栈是面向 IPv4 和 IPv6 的一种单独且独特的网络堆栈。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-124">The dual stack is a separate and distinct network stack for IPv4 and for IPv6.</span></span> <span data-ttu-id="8b0ca-125">双协议栈可允许您同时为 IPv4 和 IPv6 分配寻址，并允许服务器根据其他主机和客户端的要求与这些主机和客户端进行通信。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-125">The dual stack is what allows you to assign addressing for IPv4 and IPv6 concurrently, and allows the server to communicate with other hosts and clients based on what their requirements are.</span></span>

<span data-ttu-id="8b0ca-126">将用于 IPv6 寻址的典型地址类型将是 IPv6 全局地址 (类似于公用 IPv4 地址) 、IPv6 唯一本地地址 (类似于专用 IPv4 地址范围) 和 IPv6 链路本地地址 (类似于 Windows Server 中 IPv4 的自动专用 IP 地址) </span><span class="sxs-lookup"><span data-stu-id="8b0ca-126">Typical address types that you will use for IPv6 addressing will be the IPv6 global addresses (similar to public IPv4 addresses), IPv6 unique local addresses (similar to the private IPv4 address ranges) and IPv6 link-local addresses (similar to automatic private IP addresses in Windows Server for IPv4)</span></span>

<span data-ttu-id="8b0ca-127">存在 IPv6 的网络地址转换技术 (NAT)，以允许 NAT IPv6 转换为 IPv4（通常称为 NAT64）以及 NAT IPv6 转换为 IPv6（通常称为 NAT66）。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-127">Network address translation technologies (NAT) for IPv6 exist that will allow for NAT IPv6 to IPv4 (commonly referred to as NAT64) and for NAT IPv6 to IPv6 (commonly referred to as NAT66).</span></span> <span data-ttu-id="8b0ca-128">NAT 技术的存在意味着为 Lync Server Edge 服务器提供的五种方案仍然有效。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-128">The existence of NAT technologies means that the five scenarios presented for Lync Server Edge Servers are still valid.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="8b0ca-129">IPv6 是一个复杂的主题，需要仔细规划网络团队和 Internet 提供商，以确保您在 Windows 服务器级别和 Lync Server 2013 级别分配的地址可以按预期工作。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-129">IPv6 is a complex topic and requires careful planning with your networking team and your Internet provider to ensure that the addresses you assign at the Windows server level and at the Lync Server 2013 level will work as expected.</span></span> <span data-ttu-id="8b0ca-130">请参阅本主题结尾处的链接，以了解有关 IPv6 寻址和规划的其他资源。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-130">See the links at the end of this topic for additional resources on IPv6 addressing and planning.</span></span>



</div>

<span data-ttu-id="8b0ca-131">![899546d4-2eef-44d2-8317-51c5f699cd2a](images/Gg398823.899546d4-2eef-44d2-8317-51c5f699cd2a(OCS.15).jpg "899546d4-2eef-44d2-8317-51c5f699cd2a")</span><span class="sxs-lookup"><span data-stu-id="8b0ca-131">![899546d4-2eef-44d2-8317-51c5f699cd2a](images/Gg398823.899546d4-2eef-44d2-8317-51c5f699cd2a(OCS.15).jpg "899546d4-2eef-44d2-8317-51c5f699cd2a")</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8b0ca-132">如果使用呼叫允许控制 (CAC) ，仍必须向边缘服务器的内部接口分配 IPv4 地址。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-132">If you are using Call Admission Control (CAC), you still must assign IPv4 addresses to the Edge Server internal interface.</span></span> <span data-ttu-id="8b0ca-133">CAC 使用 IPv4 地址并且必须使它们可用于操作。</span><span class="sxs-lookup"><span data-stu-id="8b0ca-133">CAC uses IPv4 addresses and must have them available to operate.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="8b0ca-134">本部分内容</span><span class="sxs-lookup"><span data-stu-id="8b0ca-134">In This Section</span></span>

  - [<span data-ttu-id="8b0ca-135">Lync Server 2013 中的证书摘要-扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="8b0ca-135">Certificate summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)

  - [<span data-ttu-id="8b0ca-136">Lync Server 2013 中的端口摘要-扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="8b0ca-136">Port summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="8b0ca-137">Lync Server 2013 中的 DNS 摘要-扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）</span><span class="sxs-lookup"><span data-stu-id="8b0ca-137">DNS summary - Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="8b0ca-138">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8b0ca-138">See Also</span></span>


[<span data-ttu-id="8b0ca-139">IP 版本6寻址体系结构</span><span class="sxs-lookup"><span data-stu-id="8b0ca-139">IP Version 6 Addressing Architecture</span></span>](https://tools.ietf.org/html/rfc4291)  
[<span data-ttu-id="8b0ca-140">IPv6 全局单播地址格式</span><span class="sxs-lookup"><span data-stu-id="8b0ca-140">IPv6 Global Unicast Address Format</span></span>](https://tools.ietf.org/html/rfc3587)  
[<span data-ttu-id="8b0ca-141">唯一的本地 IPv6 单播地址</span><span class="sxs-lookup"><span data-stu-id="8b0ca-141">Unique Local IPv6 Unicast Addresses</span></span>](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

