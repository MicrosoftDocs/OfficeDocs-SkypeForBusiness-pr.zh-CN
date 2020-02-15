---
title: Lync Server 2013 负载平衡要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Load balancing requirements
ms:assetid: 84489328-64a4-486c-9384-a3e5c8ed9c8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615011(v=OCS.15)
ms:contentKeyID: 48184697
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bb74e5a6272f752da7cf31be3379d217447f3397
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="load-balancing-requirements-for-lync-server-2013"></a>Lync Server 2013 的负载平衡要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-05_

如果有前端池、控制器池或边缘服务器池，则需要为这些池部署负载平衡。 负载平衡会将流量分配到池中的各台服务器上。

Lync Server 2013 支持两种类型的客户端到服务器通信的负载平衡解决方案：域名系统（DNS）负载平衡和硬件负载平衡。 DNS 负载平衡提供了多项优势，包括更简单的管理、更高效的故障排除以及从任何潜在的硬件负载平衡器问题中隔离大部分 Lync Server 流量的功能。

在决定哪种负载平衡解决方案适合您部署中的每个池时，请记住以下限制：

  - 内部边缘接口和外部边缘接口必须使用同一类型的负载平衡。您不能在一个接口上使用 DNS 负载平衡的同时，在另一个接口上使用硬件负载平衡。

  - 某些类型的流量需要硬件负载平衡器。例如，HTTP 流量需要硬件平衡负载器而非 DNS 负载平衡。DNS 负载平衡对客户端到服务器的 Web 流量不起作用。

有关选择硬件负载平衡器解决方案的更多详细信息，请参阅[Lync Server 2013 的硬件负载平衡器要求](lync-server-2013-hardware-load-balancer-requirements.md)。

如果选择对某个池使用 DNS 负载平衡，但仍需对流量（如 HTTP 流量）使用硬件负载平衡器，则会大大简化硬件负载平衡器的管理。 例如，配置硬件负载平衡器会更简单，因为它将只管理 HTTP 和 HTTPS 流量，而所有其他协议都将通过 DNS 负载平衡进行管理。 有关详细信息，请参阅[Lync Server 2013 中的 DNS 负载平衡](lync-server-2013-dns-load-balancing.md)。

对于服务器到服务器的流量，Lync Server 2013 使用拓扑感知负载平衡。 服务器在中央管理存储中读取已发布的拓扑，以获取拓扑中的服务器的 Fqdn，并自动在服务器之间分布流量。 管理员无需设置或管理此类型的负载平衡。

如果使用 DNS 负载平衡，并且需要阻止到特定计算机的流量，则只需从池 FQDN 中删除 IP 地址条目是不够的。 您还必须删除计算机的 DNS 条目。

</div>

<span> </span>

</div>

</div>

</div>

