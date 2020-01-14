---
title: Lync Server 2013：扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled consolidated edge, DNS load balancing with private IP addresses using NAT
ms:assetid: c7ca4ca8-c639-4d93-86d7-8891170cacbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398823(v=OCS.15)
ms:contentKeyID: 48185369
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d0650e156dca03ac5024dfe4f3045a0d8f155643
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat-in-lync-server-2013"></a>Lync Server 2013 中的扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-08_

在边缘服务器池拓扑中，在数据中心的外围网络中，将两个或更多边缘服务器部署为负载平衡的池。 域名系统（DNS）负载平衡用于外部和内部边缘接口的流量。

如果你的组织需要支持超过15000个 Access Edge 服务客户端连接，1000个 active Lync Server Web 会议服务客户端连接或500并发的 A/V 边缘会话以及/或边缘服务器的高可用性很重要，此拓扑提供可伸缩性和故障转移支持的优势。

该图不显示 Director、在边缘服务器与前端池或服务器之间部署的可选服务器角色。 有关董事拓扑的详细信息，请参阅[Lync Server 2013 中的 Director 所需的组件](lync-server-2013-components-required-for-the-director.md)。 该图表示单个反向代理。

<div>


> [!NOTE]  
> 所示的图针对方向和示例 IP 寻址，但不打算表示具有正确的传入和传出流量的实际通信流。 该图表示可能流量的高级视图。 在每个方案的端口摘要图中表示通信流与传入（对侦听端口）和传出（目标服务器或客户端）的通信流的详细信息。 例如，TCP 443 实际上是入站的（到边缘或反向代理），并且只是从协议（TCP）角度进行的双向流。 此外，该图显示了当发生 NAT （网络地址转换）时通信的性质（在入站上更改了目标地址时，在出站上更改了源地址）。 示例外部和内部防火墙以及服务器接口的显示仅供参考之用。 最后，显示默认网关和路由关系的示例（如果适用）。 另请注意，图表使用<EM>.Com</EM> dns 区域表示反向代理服务器和边缘服务器的外部 DNS 区域，而<EM>.net</EM> DNS 区域则指内部 DNS 区域。



</div>

Microsoft Lync Server 2013 的新增功能支持 IPv6 寻址。 与 IPv4 寻址非常相似，必须以一种方式分配 IPv6 地址，这些地址是分配的 IPv6 地址空间的一部分。 本主题中的地址仅适用于示例。 你必须获取将在你的部署中运行的 IPv6 地址，提供正确的范围，并将与内部和外部寻址进行互操作。 Windows Server 提供对过渡的 IPv6 操作和 IPv4 到称为*双重堆栈*的 ipv6 通信非常重要的功能。 双重堆栈是 IPv4 和 IPv6 的单独且独特的网络堆栈。 双重堆栈使你可以同时为 IPv4 和 IPv6 分配寻址，并允许服务器根据其要求与其他主机和客户端进行通信。

将用于 IPv6 寻址的典型地址类型将是 IPv6 全局地址（类似于公用 IPv4 地址）、IPv6 唯一本地地址（类似于专用 IPv4 地址范围）和 IPv6 链接本地地址（类似于自动专用 IP）Windows Server for IPv4 中的地址）

IPv6 的网络地址转换技术（NAT）将允许 NAT IPv6 至 IPv4 （通常称为 NAT64）和 NAT IPv6 到 IPv6 （通常称为 NAT66）。 NAT 技术的存在意味着为 Lync Server Edge 服务器提供的五种方案仍然有效。

<div>


> [!WARNING]  
> IPv6 是一个复杂的主题，需要仔细规划网络团队和 Internet 提供商，以确保您在 Windows 服务器级别和 Lync Server 2013 级别分配的地址将按预期工作。 请参阅本主题结尾处的链接，以了解有关 IPv6 寻址和规划的其他资源。



</div>

![899546d4-2eef-44d2-8317-51c5f699cd2a](images/Gg398823.899546d4-2eef-44d2-8317-51c5f699cd2a(OCS.15).jpg "899546d4-2eef-44d2-8317-51c5f699cd2a")

<div>


> [!IMPORTANT]  
> 如果您使用的是 "呼叫许可控制" （CAC），仍然必须将 IPv4 地址分配给 Edge 服务器内部接口。 CAC 使用 IPv4 地址，并且必须具有它们才能运行。



</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [Lync Server 2013 中的证书摘要 - 扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-private-ip.md)

  - [Lync Server 2013 中的端口摘要 - 扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [Lync Server 2013 中的 DNS 摘要 - 扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[IP 版本6寻址体系结构](http://tools.ietf.org/html/rfc4291)  
[IPv6 全局单播地址格式](http://tools.ietf.org/html/rfc3587)  
[唯一本地 IPv6 单播地址](http://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

