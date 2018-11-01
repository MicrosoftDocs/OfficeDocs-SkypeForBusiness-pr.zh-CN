---
title: IPv6 的 Lync Server 2013 技术要求
TOCTitle: IPv6 的技术要求
ms:assetid: caff0123-ce41-4a62-87a0-00b1d118b72b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205278(v=OCS.15)
ms:contentKeyID: 49314247
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中 IPv6 的技术要求

 

_**上一次修改主题：** 2016-12-08_

如果计划将 Lync Server 2013 配置为使用 IPv6，请谨记以下要求：

  - 要对 Lync Server 使用 IPv6 地址，需要为必须发现和解析为 IPv6 地址的记录创建域名系统 (DNS) 记录。IPv6 DNS 使用主机 AAAA (4A) 记录。如果在部署中同时使用 IPv4 和 IPv6，最好同时配置和维护 IPv4 的主机 A 记录和 IPv6 的主机 AAAA 记录。即使将部署完全转换到 IPv6 后，仍可能需要 IPv4 DNS 主机记录以满足仍使用 IPv4 的用户。
    
    您可以在开始使用 IPv6 前部署 IPv6 DNS 主机记录。如果客户端或服务器不使用 IPv6，该记录不会被引用。切换技术将根据切换技术配置和策略决定使用哪条记录。

  - 每个 IPv6 地址都有一个作用域。可用于 IPv6 寻址的三个作用域是 IPv6 全局地址（与公共 IPv4 地址类似）、IPv6 唯一本地地址（与专用 IPv4 地址范围类似）和 IPv6 链接本地地址（与 Windows Server for IPv4 中的自动专用 IP 地址类似）。池内所有服务器都应该具有作用域相同的 IPv6 地址。

> [!IMPORTANT]
> IPv6 是一个复杂的主题，需要您的网络团队和 Internet 提供商进行仔细地规划，以确保您在 Windows Server 级别和 Lync Server 2013 级别分配的地址按预期工作。请参阅本主题结尾处的链接，以了解有关 IPv6 寻址和规划的其他资源。


## 另请参阅

#### 其他资源

[IPv6 寻址体系结构](http://tools.ietf.org/html/rfc4291)  
[IPv6 全局单播地址格式](http://tools.ietf.org/html/rfc3587)  
[唯一本地 IPv6 单播地址](http://tools.ietf.org/html/rfc4193)

