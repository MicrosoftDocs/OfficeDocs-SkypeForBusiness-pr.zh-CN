---
title: 扩展的控制器池 - DNS 负载平衡和硬件负载平衡器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1cd92304ca3a1147737958ad9d9fc94a49b2e5e2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822179"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a>Lync Server 2013 中扩展的控制器池 - DNS 负载平衡和硬件负载平衡器

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-22_

一个缩放的控制器池, 为处理更多容量和提供高可用性而部署了多个控制器, 需要负载平衡才能将客户端和服务器通信分配给该池的所有成员。 控制器承载 web 服务的方式非常类似于前端池。 若要提供负载平衡, 可以使用硬件负载平衡或域名系统 (DNS) 负载平衡和硬件负载平衡。 对于 web 服务, 硬件负载平衡是必需的, 并且 DNS 负载平衡本身不提供 web 服务所需的功能。

以下主题介绍了使用 DNS 负载平衡结合硬件负载平衡来部署控制器池的规划注意事项。 如果你打算使用硬件负载平衡, 而不是控制器池的 DNS 负载平衡, 请参阅[Lync Server 2013 中的主题缩放的控制器池-硬件负载平衡器](lync-server-2013-scaled-director-pool-hardware-load-balancer.md), 描述该拓扑的规划要求。

![缩放的控制器池](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "缩放的控制器池")

<div>

## <a name="in-this-section"></a>本节内容

  - [Lync Server 2013 中的证书摘要 - 已进行 DNS 和 HLB 负载平衡](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Lync Server 2013 中的端口摘要 - 已进行 DNS 和 HLB 负载平衡](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [Lync Server 2013 中的 DNS 摘要 - 已进行 DNS 和 HLB 负载平衡](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

