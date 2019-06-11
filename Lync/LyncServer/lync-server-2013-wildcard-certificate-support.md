---
title: Lync Server 2013 通配符证书支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Wildcard certificate support
ms:assetid: 0bae2aa8-b6dc-46f5-a3be-3fe7581809d4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202161(v=OCS.15)
ms:contentKeyID: 48183382
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9422c3bebbb5fb32be88cfe5c41968207bbed2ec
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="wildcard-certificate-support-in-lync-server-2013"></a>Lync Server 2013 中的通配符证书支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-03-21_

Lync Server 2013 使用证书提供通信加密和服务器身份身份验证。 在某些情况下 (例如, 通过反向代理的 web 发布), 与提供该服务的服务器的完全限定的域名 (FQDN) 匹配的强主题备用名称 (SAN) 条目不是必需的。 在这些情况下, 你可以将证书用于通配符 SAN 条目 (通常称为 "通配证书") 以减少从公共证书颁发机构请求的证书的费用, 并降低证书的规划过程的复杂性.

<div>


> [!WARNING]  
> 若要保留统一通信 (UC) 设备 (如桌面电话) 的功能, 应仔细测试部署的证书, 以确保设备在你实现通配符证书后正常工作。



</div>

不支持通配符条目作为任何角色的主题名称 (也称为公用名称或 CN)。 在 SAN 中使用通配符条目时, 支持以下服务器角色:

  - <span></span>  
    **反向代理。**   对于简单 URL ("满足" 和 "拨入") 发布证书, 支持通配符 SAN 条目。

  - <span></span>  
    **反向代理。**   LyncDiscover 发布证书上的 san 条目支持通配符 san 条目。

  - <span></span>  
    **导演。**   对于简单的 url ("满足" 和 "拨入") 以及用于 LyncDiscover 和 LyncDiscoverInternal web 组件的 SAN 条目, 均支持通配符 san 条目。

  - <span></span>  
    **前端服务器 (标准版) 和前端池 (企业版)。** 对于简单 Url ("满足" 和 "拨入") 以及 LyncDiscover 和 LyncDiscoverInternal (前端 web 组件) 的 SAN 条目, 均支持通配符 SAN 条目。

  - <span></span>  
    **Exchange 统一消息 (UM)。**   在作为独立服务器部署时, 服务器不使用 SAN 条目。

  - <span></span>  
    **Microsoft Exchange Server 客户端访问服务器。**   SAN 中的通配符条目支持内部和外部客户端。

  - <span></span>  
    **Exchange 统一消息 (UM) 和同一台服务器上的 Microsoft Exchange Server 客户端访问服务器。**   支持通配符 SAN 条目。

本主题中未解决的服务器角色:

  - 内部服务器角色 (包括但不限于中介服务器、存档和监视服务器、Survivable 分支装置或 Survivable 分支服务器)

  - 外部边缘服务器接口

  - 内部边缘服务器
    
    <div>
    

    > [!NOTE]  
    > 对于内部边缘服务器接口, 可以将通配符条目分配给 SAN, 并且受支持。 不会查询内部边缘服务器上的 SAN, 并且通配符 SAN 条目的价值有限。

    
    </div>

有关证书配置的详细信息 (包括在证书中使用通配符), 请参阅以下主题:

  - [Lync Server 2013 中内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Lync Server 2013 中外部用户访问的证书要求](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Lync Server 2013 中的证书摘要 - 已进行 DNS 和 HLB 负载平衡](lync-server-2013-certificate-summary-dns-and-hlb-load-balanced.md)

  - [Lync Server 2013 中的证书摘要 - 单一控制器](lync-server-2013-certificate-summary-single-director.md)

  - [Lync Server 2013 中的证书摘要 - 扩展的控制器池、硬件负载平衡器](lync-server-2013-certificate-summary-scaled-director-pool-hardware-load-balancer.md)

  - [Lync Server 2013 中的证书摘要 - 反向代理](lync-server-2013-certificate-summary-reverse-proxy.md)

  - [集成本地统一消息与 Lync Server 2013 的指南](lync-server-2013-guidelines-for-integrating-on-premises-unified-messaging.md)

有关配置 Exchange 证书的详细信息 (包括通配符使用), 请参阅 Exchange 2013 产品文档。

</div>

<span> </span>

</div>

</div>

</div>

