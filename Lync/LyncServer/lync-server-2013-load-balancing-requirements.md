---
title: Lync Server 2013 的负载平衡要求
TOCTitle: Lync Server 2013 的负载平衡要求
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615011(v=OCS.15)
ms:contentKeyID: 49313450
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的负载平衡要求

 

_**上一次修改主题：** 2012-10-05_

如果您具有前端池、控制器池或边缘服务器池，则需要为这些池部署负载平衡。负载平衡会将流量分配到池中的各台服务器上。

Lync Server 2013 支持两种类型的客户端到服务器流量负载平衡解决方案：域名系统 (DNS) 负载平衡和硬件负载平衡。DNS 负载平衡具有几大优势，包括更简单的管理、更高效的故障排除以及使大多数 Lync Server 流量避免出现任何潜在的硬件负载平衡器问题的功能。

在决定哪种负载平衡解决方案适合您部署中的每个池时，请记住以下限制：

  - 内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。您不能在一个接口上使用 DNS 负载平衡的同时，在另一个接口上使用硬件负载平衡。

  - 某些类型的流量需要硬件负载平衡器。例如，HTTP 流量需要硬件平衡负载器而非 DNS 负载平衡。DNS 负载平衡对客户端到服务器的 Web 流量不起作用。

有关选择硬件负载平衡器解决方案的更多详细信息，请参阅[Lync Server 2013 的硬件负载平衡器要求](lync-server-2013-hardware-load-balancer-requirements.md)。

如果选择对某个池使用 DNS 负载平衡，但仍需对流量（如 HTTP 流量）实现硬件负载平衡器，则会大大简化硬件负载平衡器的管理。例如，配置硬件负载平衡器将更简单，因为它仅管理 HTTP 和 HTTPS 流量，而所有其他协议将由 DNS 负载平衡管理。有关详细信息，请参阅 [Lync Server 2013 中的 DNS 负载平衡](lync-server-2013-dns-load-balancing.md)。

对于服务器到服务器流量，Lync Server 2013 使用可识别拓扑的负载平衡。服务器读取中央管理存储中已发布的拓扑以在拓扑中获取服务器的 FQDN，并且在各服务器之间自动分发流量。管理员不必设置或管理此类型的负载平衡。

如果使用 DNS 负载平衡并且需要阻止至特定计算机的流量，则仅仅删除池 FQDN 中的 IP 地址条目是不够的。您还必须删除计算机的 DNS 条目。

