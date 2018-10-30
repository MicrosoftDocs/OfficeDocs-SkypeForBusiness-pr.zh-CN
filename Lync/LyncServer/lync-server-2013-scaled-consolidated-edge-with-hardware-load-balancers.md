---
title: Lync Server 2013：使用硬件负载平衡器的扩展的合并边缘
TOCTitle: 使用硬件负载平衡器的扩展的合并边缘
ms:assetid: 6783e225-9677-415a-8731-0bf2e2c4cf8b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398478(v=OCS.15)
ms:contentKeyID: 49313109
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中使用硬件负载平衡器的扩展的合并边缘

 

_**上一次修改主题：** 2016-12-08_

在 边缘池拓扑中，数据中心的外围网络中部署了两台或更多 边缘服务器作为负载平衡池。硬件负载平衡用于到外部和内部 边缘服务器接口的流量。

如果组织需要支持超过 15,000 个 访问边缘服务客户端连接、1,000 个活动的 Web 会议边缘服务客户端连接、或 500 次并发 A/V 边缘服务会话，且 边缘服务器的高可用性非常重要，则该拓扑具有可伸缩性和故障转移支持优势。

下图未显示 控制器，其是在 边缘服务器和您的 前端池或服务器之间的内部网络中部署的一个可选服务器角色。有关 控制器拓扑的详细信息，请参阅 [Lync Server 2013 中控制器所需的组件](lync-server-2013-components-required-for-the-director.md)。

> [!NOTE]  
> 所显示的图涉及 IP 寻址的方向和示例，但并不表示正确传入和传出流量的实际通信流。该图显示了可能的流量的高级视图。通信流的详细信息在通信流与传入（至侦听端口）和传出（至目标服务器或客户端）有关时显示在每种方案的“端口摘要”图中。例如，TCP 443 只是实际入站（至边缘服务器或服务器代理），并且只是来自协议 (TCP) 的双向流。此外，该图显示随 NAT（网络地址转换）的出现而发生更改的流量的性质（入站更改目标地址，出站更改源地址）。显示的示例外部和内部防火墙以及服务器接口仅作参考之用。最终，将显示示例默认网关和路由关系（如果适用）。还要注意，该图使用 <em>.com</em> DNS 区域表示反向代理和边缘服务器的外部 DNS 区域，并且 <em>.net</em> DNS 区域表示内部 DNS 区域。



Microsoft Lync Server 2013 的新增功能是对 IPv6 寻址的支持。与 IPv4 寻址非常相似，必须以一种适当的方式分配 IPv6 地址，使这些地址属于所分配的 IPv6 地址空间的一部分。本主题中的地址仅用作示例。您必须获取将在您的部署中正常运行、提供正确的范围并将与内部和外部寻址进行互操作的 IPv6 地址。 Windows Server 提供了一种对转换 IPv6 操作和 IPv4 至 IPv6 通信（称为 *双协议栈* ）而言都非常重要的功能。双协议栈是面向 IPv4 和 IPv6 的一种单独且独特的网络堆栈。双协议栈可允许您同时为 IPv4 和 IPv6 分配寻址，并允许服务器根据其他主机和客户端的要求与这些主机和客户端进行通信。

您将用于 IPv6 寻址的典型地址类型为 IPv6 全局地址（与公共 IPv4 地址类似）、IPv6 唯一本地地址（与专用 IPv4 地址范围类似）和 IPv6 链接本地地址（与 Windows Server for IPv4 中的自动专用 IP 地址类似）

存在 IPv6 的网络地址转换技术 (NAT)，以允许 NAT IPv6 转换为 IPv4（通常称为 NAT64）以及 NAT IPv6 转换为 IPv6（通常称为 NAT66）。NAT 技术的存在意味着针对 Lync Server边缘服务器 存在的五种方案仍有效。

> [!WARNING]
> IPv6 是一个复杂的主题，需要您的网络团队和 Internet 提供商进行仔细地规划，以确保您在 Windows 服务器级别和 Lync Server 2013 级别分配的地址按预期工作。请参阅本主题结尾处的链接，以了解有关 IPv6 寻址和规划的其他资源。


**硬件负载平衡器配置**

有关详细信息，请参阅[Lync Server 2013 中外部用户访问所需的组件](lync-server-2013-components-required-for-external-user-access.md)中的“A/V 边缘的硬件负载平衡器要求”部分。

**扩展的合并边缘拓扑（硬件负载已平衡）**

![扩展合并边缘拓扑](images/Gg398478.3a57cd0d-8de4-4ecc-a783-4dff5b3456a2(OCS.15).jpg "扩展合并边缘拓扑")

> [!IMPORTANT]
> 如果您使用的是呼叫允许控制 (CAC)，那么仍必须将 IPv4 地址分配给 边缘服务器内部接口。CAC 使用 IPv4 地址并且必须使它们可用于操作。


## 本部分内容

  - [Lync Server 2013 中的证书摘要 - 使用硬件负载平衡器的扩展的合并边缘](lync-server-2013-certificate-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Lync Server 2013 中的端口摘要 - 使用硬件负载平衡器的扩展的合并边缘](lync-server-2013-port-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

  - [Lync Server 2013 中的 DNS 摘要 - 使用硬件负载平衡器的扩展的合并边缘](lync-server-2013-dns-summary-scaled-consolidated-edge-with-hardware-load-balancers.md)

## 另请参阅

#### 其他资源

[IPv6 寻址体系结构](http://tools.ietf.org/html/rfc4291)  
[IPv6 全局单播地址格式](http://tools.ietf.org/html/rfc3587)  
[唯一本地 IPv6 单播地址](http://tools.ietf.org/html/rfc4193)

