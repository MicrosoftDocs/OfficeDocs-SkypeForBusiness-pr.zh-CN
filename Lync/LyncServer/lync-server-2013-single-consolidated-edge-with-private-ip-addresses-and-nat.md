---
title: Lync Server 2013：使用专用 IP 地址和 NAT 的单一合并边缘
description: Lync Server 2013：使用专用 IP 地址和 NAT 的单一合并边缘。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Single consolidated edge with private IP addresses and NAT
ms:assetid: e1e5189e-f17d-45e9-b177-e0e6f97f8951
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399001(v=OCS.15)
ms:contentKeyID: 48185691
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e716cd7cd07fdb4e4557cab83db7d8f3aecada2
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555668"
---
# <a name="single-consolidated-edge-with-private-ip-addresses-and-nat-in-lync-server-2013"></a>Lync Server 2013 中具有专用 IP 地址和 NAT 的单一合并边缘

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-08_

如果您的组织需要支持低于15000的访问边缘服务客户端连接、1000主动 Lync Server Web 会议服务客户端连接和500并发 A/V 边缘会话，并且边缘服务器的高可用性并不重要，则此拓扑可提供降低硬件成本和简化部署的优势。 如果需要更大的容量或需要高可用性，则需要部署一个扩展的合并边缘服务器拓扑。 有关详细信息，请参阅以下内容：

  - <span></span>  
    [在 Lync Server 2013 中，扩展的合并边缘（使用 NAT 通过专用 IP 地址进行 DNS 负载平衡）](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - <span></span>  
    [在 Lync Server 2013 中，扩展的合并边缘（使用公用 IP 地址进行 DNS 负载平衡）](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - <span></span>  
    [Lync Server 2013 中具有硬件负载平衡器的扩展的合并边缘](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

该图不显示控制器，即在边缘服务器与前端池或服务器之间部署在内部网络中的可选服务器角色。 有关控制器拓扑的详细信息，请参阅 [Lync Server 2013 中的控制器所需的组件](lync-server-2013-components-required-for-the-director.md)。 此图表示一个反向代理。

<div>


> [!NOTE]  
> 所显示的图适用于方向和示例 IP 寻址，但并不旨在代表具有正确传入和传出流量的实际通信流。 该图代表可能流量的高级视图。 与传入（至侦听端口）和传出（至目标服务器或客户端）相关的通信流的详细信息显示在每个方案的“端口摘要”图中。 例如，TCP 443 实际上仅限入站（至边缘或反向代理），而且从协议 (TCP) 的角度来看只是一种双向流。 此外，该图显示流量的特性，因为在发生 NAT（网络地址转换）时它会发生更改（目标地址在入站上更改，源地址在出站上更改）。 显示的外部和内部防火墙示例以及服务器界面仅供参考。 最后，显示默认网关和路由关系示例（如果适用）。 另请注意，该图表使用 <EM>.Com</EM> dns 区域表示反向代理服务器和边缘服务器的外部 DNS 区域，而 <EM>.net</EM> DNS 区域引用内部 dns 区域。



</div>

Microsoft Lync Server 2013 的新增支持 IPv6 寻址。 与 IPv4 寻址非常相似，必须以一种适当的方式分配 IPv6 地址，使这些地址属于所分配的 IPv6 地址空间的一部分。 本主题中的地址仅用作示例。 您必须获取将在您的部署中正常运行、提供正确的范围并将与内部和外部寻址进行互操作的 IPv6 地址。 Windows Server 提供了一项功能，这一点对将 IPv6 操作和 IPv4 转换为称作 *双重堆栈*的 ipv6 通信非常重要。 双协议栈是面向 IPv4 和 IPv6 的一种单独且独特的网络堆栈。 双协议栈可允许您同时为 IPv4 和 IPv6 分配寻址，并允许服务器根据其他主机和客户端的要求与这些主机和客户端进行通信。

将用于 IPv6 寻址的典型地址类型将是 IPv6 全局地址 (类似于公用 IPv4 地址) 、IPv6 唯一本地地址 (类似于专用 IPv4 地址范围) 和 IPv6 链路本地地址 (类似于 Windows Server 中 IPv4 的自动专用 IP 地址) 

存在 IPv6 的网络地址转换技术 (NAT)，以允许 NAT IPv6 转换为 IPv4（通常称为 NAT64）以及 NAT IPv6 转换为 IPv6（通常称为 NAT66）。 NAT 技术的存在意味着为 Lync Server Edge 服务器提供的五种方案仍然有效。

<div>


> [!WARNING]  
> IPv6 是一个复杂的主题，需要仔细规划网络团队和 Internet 提供商，以确保您在 Windows 服务器级别和 Lync Server 2013 级别分配的地址可以按预期工作。 请参阅本主题结尾处的链接，以了解有关 IPv6 寻址和规划的其他资源。



</div>

**单一合并边缘拓扑**

![d9b889c1-587c-4732-9b68-841186ccff78](images/Gg399001.d9b889c1-587c-4732-9b68-841186ccff78(OCS.15).jpg "d9b889c1-587c-4732-9b68-841186ccff78")

<div>


> [!IMPORTANT]  
> 如果使用呼叫允许控制 (CAC) ，仍必须向边缘服务器的内部接口分配 IPv4 地址。 CAC 使用 IPv4 地址并且必须使它们可用于操作。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 中的证书摘要-使用 NAT 的专用 IP 地址的单一合并边缘](lync-server-2013-certificate-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [Lync Server 2013 中的端口摘要-使用 NAT 的具有专用 IP 地址的单一合并边缘](lync-server-2013-port-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

  - [Lync Server 2013 中的 DNS 摘要-使用 NAT 的专用 IP 地址的单一合并边缘](lync-server-2013-dns-summary-single-consolidated-edge-with-private-ip-addresses-using-nat.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[IP 版本6寻址体系结构](https://tools.ietf.org/html/rfc4291)  
[IPv6 全局单播地址格式](https://tools.ietf.org/html/rfc3587)  
[唯一的本地 IPv6 单播地址](https://tools.ietf.org/html/rfc4193)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

