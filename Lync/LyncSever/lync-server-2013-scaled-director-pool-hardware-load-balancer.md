---
title: Lync Server 2013：扩展的控制器池 - 硬件负载平衡器
TOCTitle: 扩展的控制器池 - 硬件负载平衡器
ms:assetid: cf34759a-b384-479c-855f-ea5e80a234b6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205316(v=OCS.15)
ms:contentKeyID: 49314297
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中扩展的控制器池 - 硬件负载平衡器

 

_**上一次修改主题：** 2012-09-08_

部署一个扩展的 控制器池（其中包含多个 控制器）以处理额外容量并提供高可用性，这要求实现负载平衡以将客户端和服务器分发给池中的所有成员。 控制器用于承载 Web 服务，与 前端池很相似。Web 服务需要实现硬件负载平衡。

以下主题介绍了使用硬件负载平衡部署 控制器池的规划注意事项。如果您打算对 控制器池使用硬件负载平衡和 DNS 负载平衡，请参阅以下介绍关于该拓扑的规划要求的主题： [Lync Server 2013 中扩展的控制器池 - DNS 负载平衡和硬件负载平衡器](lync-server-2013-scaled-director-pool-dns-load-balancing-and-hardware-load-balancer.md)。

![扩展的控制器池](images/JJ205316.cfa892b9-5b24-4245-b5bd-c5da21984eeb(OCS.15).jpg "扩展的控制器池")

## 本部分内容

  - [Lync Server 2013 中的证书摘要 - 扩展的控制器池、硬件负载平衡器](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Lync Server 2013 中的端口摘要 - 扩展的控制器池、硬件负载平衡器](lync-server-2013-port-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Lync Server 2013 中的 DNS 摘要 - 扩展的控制器池、硬件负载平衡器](lync-server-2013-dns-summary-scaled-director-pool-hardware-load-balancer.md)

