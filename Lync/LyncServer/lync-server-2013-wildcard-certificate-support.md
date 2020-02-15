---
title: Lync Server 2013 通配符证书支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 18b1313432cac09f03cd414b90d9a068f271edef
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041201"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a>Lync Server 2013 中的通配符证书支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-03-21_

Lync Server 2013 使用证书提供通信加密和服务器身份身份验证。 在某些情况下，如通过反向代理的 Web 发布，不需要使用与提供服务的服务器的完全限定域名 (FQDN) 匹配的强主题备用名称 (SAN) 项。 在这些情况下，可以使用具有通配符 SAN 项（通常称为“通配符证书”）的证书来减少从公共证书颁发机构请求证书的成本，并降低证书规划流程的复杂性。

<div>


> [!WARNING]  
> 若要保留统一通信 (UC) 设备（例如，桌面电话）的功能，您应该小心测试已部署的证书，确保设备在实施通配符证书后可以正常运行。



</div>

不支持使用通配符项作为任何角色的主题名称（也称为公用名或 CN）。使用 SAN 中的通配符项时支持以下服务器角色：

  - <span></span>  
    **反向代理。**   通配符 SAN 条目受简单 URL （"满足" 和 "拨入"）发布证书支持。

  - <span></span>  
    **反向代理。**   对于发布证书上的 LYNCDISCOVER. 的 san 条目，支持通配符 san 条目。

  - <span></span>  
    **导演。**   通配符 san 条目支持简单 url （"满足" 和 "拨入"），以及用于 Lyncdiscover. 和 lyncdiscoverinternal. web 组件的 SAN 条目。

  - <span></span>  
    **前端服务器（Standard Edition）和前端池（Enterprise Edition）。** 对于简单 Url （"满足" 和 "拨入"）以及 Lyncdiscover. 和 Lyncdiscoverinternal. 的 SAN 条目，在前端 web 组件中支持通配符 SAN 条目。

  - <span></span>  
    **Exchange 统一消息（UM）。**   在作为独立服务器部署时，服务器不使用 SAN 条目。

  - <span></span>  
    **Microsoft Exchange Server 客户端访问服务器。**   SAN 中的通配符条目支持内部和外部客户端。

  - <span></span>  
    **Exchange 统一消息（UM）和同一台服务器上的 Microsoft Exchange Server 客户端访问服务器。**   支持通配符 SAN 条目。

该主题中未提到的服务器角色：

  - 内部服务器角色（包括但不限于中介服务器、存档和监控服务器、Survivable 分支设备或 Survivable 分支服务器）

  - 外部边缘服务器接口

  - 内部边缘服务器
    
    <div>
    

    > [!NOTE]  
    > 对于内部边缘服务器接口，可以将通配符项分配给 SAN 并支持它。 不会查询内部边缘服务器上的 SAN，并且通配符 SAN 条目的值有限。

    
    </div>

有关证书配置的详细信息（包括证书中的通配符使用），请参阅下列主题：

  - [Lync Server 2013 中的内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Lync Server 2013 中的外部用户访问的证书要求](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Lync Server 2013 中的证书摘要-DNS 和 HLB 负载平衡](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [证书摘要-Lync Server 2013 中的单个控制器](lync-server-2013-certificate-summary-single-director.md)

  - [Lync Server 2013 中的证书摘要-扩展的控制器池、硬件负载平衡器](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Lync Server 2013 中的证书摘要-反向代理](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [集成本地统一消息和 Lync Server 2013 的准则](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

有关为 Exchange 配置证书的详细信息，包括通配符的使用，请参阅 Exchange 2013 产品文档。

</div>

<span> </span>

</div>

</div>

</div>

