---
title: Lync Server 2013：扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）
TOCTitle: 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）
ms:assetid: 2b854f6d-3d3f-4961-a5f8-a03f47740df0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204761(v=OCS.15)
ms:contentKeyID: 49312350
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）

 

_**上一次修改主题：** 2016-12-08_

在边缘服务器池拓扑中，数据中心的外围网络中部署了两台或更多边缘服务器作为负载平衡池。域名系统 (DNS) 负载平衡用于到外部边缘接口和内部边缘接口的流量。

如果组织需要支持 15,000 个以上的访问边缘服务客户端连接，1,000 个以上的活动 Lync Server Web 会议服务客户端连接或 500 个以上的并发 A/V 边缘会话，和/或边缘服务器的高可用性非常重要，则该拓扑具有可伸缩性和故障转移支持方面的优势。

此图未显示 控制器，它是一个在 边缘服务器与您的 前端池或服务器之间的内部网络中部署的可选服务器角色。有关控制器拓扑的详细信息，请参阅 [Lync Server 2013 中控制器所需的组件](lync-server-2013-components-required-for-the-director.md)。此图表示一个反向代理。

> [!NOTE]  
> 所显示的图适用于方向和示例 IP 寻址，但并不旨在代表具有正确传入和传出流量的实际通信流。该图代表可能流量的高级视图。与传入（至侦听端口）和传出（至目标服务器或客户端）相关的通信流的详细信息显示在每个方案的“端口摘要”图中。例如，TCP 443 实际上仅限入站（至边缘或反向代理），而且从协议 (TCP) 的角度来看只是一种双向流。此外，该图显示流量的特性，因为在发生 NAT（网络地址转换）时它会发生更改（目标地址在入站上更改，源地址在出站上更改）。显示的外部和内部防火墙示例以及服务器界面仅供参考。最后，显示默认网关和路由关系示例（如果适用）。另请注意，该图使用 <em>.net</em> DNS 区域代表反向代理和边缘服务器的外部 DNS 区域，而 <em>.net</em> DNS 区域参考内部 DNS 区域。



Microsoft Lync Server 2013 的新增功能是对 IPv6 寻址的支持。与 IPv4 寻址非常相似，必须以一种适当的方式分配 IPv6 地址，使这些地址属于所分配的 IPv6 地址空间的一部分。本主题中的地址仅用作示例。您必须获取将在您的部署中正常运行、提供正确的范围并将与内部和外部寻址进行互操作的 IPv6 地址。 Windows Server 提供了一种对转换 IPv6 操作和 IPv4 至 IPv6 通信（称为 *双协议栈* ）而言都非常重要的功能。双协议栈是面向 IPv4 和 IPv6 的一种单独且独特的网络堆栈。双协议栈可允许您同时为 IPv4 和 IPv6 分配寻址，并允许服务器根据其他主机和客户端的要求与这些主机和客户端进行通信。

您将用于 IPv6 寻址的典型地址类型为 IPv6 全局地址（与公共 IPv4 地址类似）、IPv6 唯一本地地址（与专用 IPv4 地址范围类似）和 IPv6 链接本地地址（与 Windows Server for IPv4 中的自动专用 IP 地址类似）

存在 IPv6 的网络地址转换技术 (NAT)，以允许 NAT IPv6 转换为 IPv4（通常称为 NAT64）以及 NAT IPv6 转换为 IPv6（通常称为 NAT66）。NAT 技术的存在意味着针对 Lync Server边缘服务器 存在的五种方案仍有效。

> [!WARNING]
> IPv6 是一个复杂的主题，需要您的网络团队和 Internet 提供商进行仔细地规划，以确保您在 Windows 服务器级别和 Lync Server 2013 级别分配的地址按预期工作。请参阅本主题结尾处的链接，以了解有关 IPv6 寻址和规划的其他资源。


![扩展合并边缘拓扑](images/JJ204761.7c1e3e6b-9b1b-4ac6-b0e7-9c256dbc2537(OCS.15).jpg "扩展合并边缘拓扑")

> [!IMPORTANT]
> 如果您使用的是呼叫允许控制 (CAC)，那么仍必须将 IPv4 地址分配给 边缘服务器内部接口。CAC 使用 IPv4 地址并且必须使它们可用于操作。


## 本部分内容

  - [Lync Server 2013 中的证书摘要 - 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）](lync-server-2013-certificate-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Lync Server 2013 中的端口摘要 - 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）](lync-server-2013-port-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [Lync Server 2013 中的 DNS 摘要 - 扩展的合并边缘（通过公用 IP 地址进行 DNS 负载平衡）](lync-server-2013-dns-summary-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

## 另请参阅

#### 其他资源

[IPv6 寻址体系结构](http://tools.ietf.org/html/rfc4291)  
[IPv6 全局单播地址格式](http://tools.ietf.org/html/rfc3587)  
[唯一本地 IPv6 单播地址](http://tools.ietf.org/html/rfc4193)

