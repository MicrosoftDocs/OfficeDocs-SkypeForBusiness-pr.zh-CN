---
title: 扩展的控制器池-DNS 负载平衡和硬件负载平衡器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scaled Director pool - DNS load balancing and hardware load balancer
ms:assetid: a1f6ffc0-9e6e-4217-a923-025c9679e154
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205142(v=OCS.15)
ms:contentKeyID: 48185023
ms.date: 03/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d05e579d8c4a2c54342b926b34ff20bbd722524c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510969"
---
# <a name="scaled-director-pool---dns-load-balancing-and-hardware-load-balancer-in-lync-server-2013"></a>Lync Server 2013 中的扩展控制器池-DNS 负载平衡和硬件负载平衡器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-22_

一个扩展的控制器池，在其中部署了多个控制器以处理更多容量并提供高可用性时，需要使用负载平衡将客户端和服务器通信分发到池的所有成员。 控制器承载 web 服务的方式与前端池非常相似。 若要提供负载平衡，可以使用硬件负载平衡或域名系统 (DNS) 负载平衡和硬件负载平衡。 Web 服务需要硬件负载平衡，单独的 DNS 负载平衡无法提供 Web 服务所需的功能。

以下主题介绍了在结合使用 DNS 负载平衡和硬件负载平衡时部署控制器池的规划注意事项。 如果打算使用硬件负载平衡，但不是控制器池的 DNS 负载平衡，请参阅 [Lync Server 2013 中的主题扩展的控制器池-硬件负载平衡器](lync-server-2013-scaled-director-pool-hardware-load-balancer.md) ，用于描述该拓扑的规划要求。

![扩展的控制器池](images/JJ205142.35a78a7a-b781-4c8f-951e-168451ba6a65(OCS.15).jpg "扩展的控制器池")

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 中的证书摘要-DNS 和 HLB 负载平衡](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Lync Server 2013 中的端口摘要-DNS 和 HLB 负载平衡](lync-server-2013-port-summary-dns-and-hlb-load-balanced.md)

  - [Lync Server 2013 中的 DNS 摘要-DNS 和 HLB 负载平衡](lync-server-2013-dns-summary-dns-and-hlb-load-balanced.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

