---
title: Lync Server 2013：使用硬件负载平衡器的扩展的合并边缘
description: Lync Server 2013：使用硬件负载平衡器的扩展的合并边缘。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled consolidated edge with hardware load balancers
ms:assetid: 6783e225-9677-415a-8731-0bf2e2c4cf8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398478(v=OCS.15)
ms:contentKeyID: 48184353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 808c03e0d6f2836719599c6cad9ec83e1c96b207
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48547648"
---
# <a name="scaled-consolidated-edge-with-hardware-load-balancers-in-lync-server-2013"></a>Lync Server 2013 中具有硬件负载平衡器的扩展的合并边缘

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-21_

在边缘池拓扑中，在数据中心的外围网络中，将两台或多台边缘服务器部署为负载平衡池。 硬件负载平衡用于与外部和内部边缘服务器接口的通信。

如果您的组织需要支持15000个以上的 Access Edge 服务客户端连接、1000个活动的 Web 会议边缘服务客户端连接，或者500并发 A/V 边缘服务会话，并且边缘服务器的高可用性很重要，则此拓扑提供了可伸缩性和故障转移支持的优势。

该图不显示控制器，即在边缘服务器与前端池或服务器之间部署在内部网络中的可选服务器角色。 . 有关控制器拓扑的详细信息，请参阅 [Lync Server 2013 中的控制器所需的组件](lync-server-2013-components-required-for-the-director.md)。

<div>


> [!NOTE]  
> 所显示的图适用于方向和示例 IP 寻址，但并不旨在代表具有正确传入和传出流量的实际通信流。 该图代表可能流量的高级视图。 与传入（至侦听端口）和传出（至目标服务器或客户端）相关的通信流的详细信息显示在每个方案的“端口摘要”图中。 例如，TCP 443 实际上是到边缘服务器或反向代理) 的入站 (，只是来自 TCP) 角度的 (协议的双向流。 此外，该图显示流量的特性，因为在发生 NAT（网络地址转换）时它会发生更改（目标地址在入站上更改，源地址在出站上更改）。 显示的外部和内部防火墙示例以及服务器界面仅供参考。 最后，显示默认网关和路由关系示例（如果适用）。 另请注意，该图表使用 <EM>.Com</EM> dns 区域表示反向代理服务器和边缘服务器的外部 DNS 区域，而 <EM>.net</EM> DNS 区域引用内部 dns 区域。



</div>

Microsoft Lync Server 2013 的新增支持 IPv6 寻址。 与 IPv4 寻址非常相似，必须以一种适当的方式分配 IPv6 地址，使这些地址属于所分配的 IPv6 地址空间的一部分。 本主题中的地址仅用作示例。 您必须获取将在您的部署中正常运行、提供正确的范围并将与内部和外部寻址进行互操作的 IPv6 地址。 Windows Server 提供了一项功能，这一点对将 IPv6 操作和 IPv4 转换为称作 *双重堆栈*的 ipv6 通信非常重要。 双协议栈是面向 IPv4 和 IPv6 的一种单独且独特的网络堆栈。 双协议栈可允许您同时为 IPv4 和 IPv6 分配寻址，并允许服务器根据其他主机和客户端的要求与这些主机和客户端进行通信。

将用于 IPv6 寻址的典型地址类型将是 IPv6 全局地址 (类似于公用 IPv4 地址) 、IPv6 唯一本地地址 (类似于专用 IPv4 地址范围) 和 IPv6 链路本地地址 (类似于 Windows Server 中 IPv4 的自动专用 IP 地址) 

存在 IPv6 的网络地址转换技术 (NAT)，以允许 NAT IPv6 转换为 IPv4（通常称为 NAT64）以及 NAT IPv6 转换为 IPv6（通常称为 NAT66）。 NAT 技术的存在意味着为 Lync Server Edge 服务器提供的五种方案仍然有效。

<div>


> [!WARNING]  
> IPv6 是一个复杂的主题，需要仔细规划网络团队和 Internet 提供商，以确保您在 Windows 服务器级别和 Lync Server 2013 级别分配的地址可以按预期工作。 有关 IPv6 寻址和规划的其他资源，请参阅本主题末尾的链接。



</div>

**硬件负载平衡器配置**

有关详细信息，请参阅 [Lync Server 2013 中的外部用户访问所需的组件](lync-server-2013-components-required-for-external-user-access.md)中的 "A/V 边缘的硬件负载平衡器要求" 部分。

**扩展的合并边缘拓扑（硬件负载已平衡）**

![3a57cd0d-8de4-4ecc-a783-4dff5b3456a2](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "3a57cd0d-8de4-4ecc-a783-4dff5b3456a2")

<div>


> [!IMPORTANT]  
> 如果使用呼叫允许控制 (CAC) ，仍必须向边缘服务器的内部接口分配 IPv4 地址。 CAC 使用 IPv4 地址并且必须使它们可用于操作。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 中的证书摘要-使用硬件负载平衡器的扩展的合并边缘](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Lync Server 2013 中的端口摘要-使用硬件负载平衡器的扩展的合并边缘](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Lync Server 2013 中的 DNS 摘要-使用硬件负载平衡器的扩展的合并边缘](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

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

