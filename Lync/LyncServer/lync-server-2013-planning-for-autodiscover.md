---
title: Lync Server 2013：规划自动发现
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6416e2ed817dc3cc03a0ec516175c92623bb31b3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497869"
---
# <a name="planning-for-autodiscover-in-lync-server-2013"></a>在 Lync Server 2013 中规划自动发现

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-16_

在 Lync Server 2010 的累积更新中为 Lync Server 引入了自动发现：11月2011。 此初始的自动发现实现的主要目的是为 Lync Mobile 提供一种方法来查找移动服务 (Mcx) 。 Lync Server 2013 中的自动发现服务现在是所有客户端用来查找服务器和用户服务的一项服务。 Microsoft Lync Server 2013 自动发现服务在控制器和前端服务器上运行。

<div>


> [!TIP]  
> 有关自动发现和向客户端传递内容的技术方面的更多了解，请参阅 <A href="lync-server-2013-understanding-autodiscover.md">了解 Lync Server 2013 中的自动发现</A>。<BR>移动仍然是一个不同的方案，移动服务仍需要进行一些特殊规划。 有关其他详细信息，请参阅 <A href="lync-server-2013-planning-for-mobility.md">在 Lync Server 2013 中规划移动</A>功能。



</div>

如果在 Lync Server 2010 中引入了自动发现，则需要进行一些威胁，以便实施需要对现有服务器部署进行潜在证书更改的服务。 自动发现可用于 HTTPS 的端口 TCP 443 或通过端口 TCP 80 for HTTP。 如果做出了使用 HTTPS 的决定，则需要重新颁发反向代理、控制器和前端服务器上的证书，以便满足所需的 `lyncdiscover.<domain>` 和 `lyncdiscoverinternal.<domain>` DNS 记录。 如果决定使用 HTTP，可以通过使用 DNS CNAME (或别名) 记录来使用证书上的现有名称来避免重新颁发证书。 使用 HTTP 是指未加密初始通信。

由于 Lync Server 2013 使用所有客户端的自动发现，因此主要方案是以独占方式使用 HTTPS，并使用 lyncdiscover. 创建证书。\<domain\> 作为反向代理、控制器和前端服务器的配置的一部分。 如果要将自动发现实现从 Lync Server 2010 的已升级部署，则可能需要使用 HTTP 以避免重新颁发证书。 以下各节提供了这两种方案的指南。

<div>


> [!IMPORTANT]  
> 外部 web 服务发布规则所使用的证书上的 "主题备用名称" 列表必须包含<EM>lyncdiscover.。 &lt;组织 &gt; </EM>中每个 SIP 域的 sipdomain 条目。 有关控制器、前端服务器和反向代理所需的主题替代名称条目的详细信息，请参阅 <A href="lync-server-2013-certificate-summary-autodiscover.md">Lync Server 2013 中的证书摘要-自动发现</A>。



</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [证书摘要-Lync Server 2013 中的自动发现](lync-server-2013-certificate-summary-autodiscover.md)

  - [Lync Server 2013 中的端口摘要-自动发现](lync-server-2013-port-summary-autodiscover.md)

  - [Lync Server 2013 中的 DNS 摘要-自动发现](lync-server-2013-dns-summary-autodiscover.md)

  - [Lync Server 2013 中的混合和拆分域自动发现](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

