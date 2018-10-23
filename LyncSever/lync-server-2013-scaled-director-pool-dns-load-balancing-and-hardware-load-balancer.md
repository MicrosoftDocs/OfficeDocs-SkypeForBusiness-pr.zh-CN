---
title: Lync Server 2013：扩展的控制器池 - DNS 负载平衡和硬件负载平衡器
TOCTitle: 扩展的控制器池 - DNS 负载平衡和硬件负载平衡器
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205142(v=OCS.15)
ms:contentKeyID: 49313791
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中扩展的控制器池 - DNS 负载平衡和硬件负载平衡器

 

_**上一次修改主题：** 2012-10-22_

缩放式 控制器池（其中部署了多个 控制器来处理额外的容量和提供高可用性）需要负载平衡来向池的所有成员分发客户端和服务器通信。 控制器用于承载 Web 服务，与 前端池很相似。若要提供负载平衡，可以使用硬件负载平衡或域名系统 (DNS) 负载平衡和硬件负载平衡。Web 服务需要硬件负载平衡，单独的 DNS 负载平衡无法提供 Web 服务所需的功能。

以下主题介绍通过将 DNS 负载平衡与硬件负载平衡一起使用来部署 控制器池的规划注意事项。如果您打算对 控制器池使用硬件负载平衡而不使用 DNS 负载平衡，请参阅主题 [Lync Server 2013 中扩展的控制器池 - 硬件负载平衡器](lync-server-2013-scaled-director-pool-hardware-load-balancer.md)，其中介绍了该拓扑的规划要求。

![扩展的控制器池](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "扩展的控制器池")

## 本部分内容

  - [Lync Server 2013 中的证书摘要 - 已进行 DNS 和 HLB 负载平衡](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Lync Server 2013 中的端口摘要 - 已进行 DNS 和 HLB 负载平衡](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [Lync Server 2013 中的 DNS 摘要 - 已进行 DNS 和 HLB 负载平衡](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

