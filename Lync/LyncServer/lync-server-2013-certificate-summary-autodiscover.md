---
title: Lync Server 2013：证书摘要-自动发现
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Autodiscover
ms:assetid: 16ac96bb-882a-4141-b75c-9530637548d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945616(v=OCS.15)
ms:contentKeyID: 51541451
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 196b3dacec792097a4760ef134ead91f267a53d1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499309"
---
# <a name="certificate-summary---autodiscover-in-lync-server-2013"></a>证书摘要-Lync Server 2013 中的自动发现

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-14_

Lync Server 2013 自动发现服务在控制器和前端池服务器上运行，并且在 DNS 中发布时可供 Lync 客户端用来查找服务器和用户服务。 如果要从 Lync Server 2010 升级且未部署移动性，则在客户端可以使用自动发现之前，必须在运行自动发现服务的任何控制器和前端服务器上修改证书使用者备用名称列表。 此外，可能还必须修改证书上的供反向代理上的外部 Web 服务发布规则使用的使用者替代名称列表。

有关是否在反向代理上使用主题备用名称列表的决策取决于您是在端口80上还是在端口443上发布自动发现服务：

  - **已在端口 80**     上发布如果对自动发现服务的初始查询在端口80上发生，则不需要进行证书更改。 这是因为运行 Lync 的移动设备将在外部端口80上访问反向代理，然后在内部桥接到端口8080上的控制器或前端服务器。 有关详细信息，请参阅 [Lync Server 2013 中的移动性技术要求](lync-server-2013-technical-requirements-for-mobility.md)一节中的 "使用端口80初始自动发现过程" 一节。

  - **已在端口 443**     上发布外部 web 服务发布规则所使用的证书上的 "主题备用名称" 列表必须包含*lyncdiscover. \<sipdomain\> 。* 组织中每个 SIP 域的条目。
    
    <div>
    

    > [!IMPORTANT]  
    > 强烈建议使用 HTTPS over HTTP。 HTTPS 使用证书对流量进行加密。 HTTP 不提供加密功能，发送的任何数据将为纯文本。

    
    </div>

使用内部证书颁发机构重新发起证书通常是一个简单的过程。 但对于 web 服务发布规则上使用的公共证书，添加多个使用者可选名称条目可能会变得昂贵。 若要解决此问题，我们支持通过端口80的初始自动发现连接，该连接随后将被重定向到控制器或前端服务器上的端口8080。

<div>


> [!NOTE]  
> 如果你的 Lync Server 2013 基础结构使用从内部证书颁发机构颁发的内部证书 (CA) ，并且计划支持通过无线方式连接的移动设备，则必须在移动设备上安装内部 CA 的根证书链，或者必须将其更改为 Lync Server 2013 基础结构上的公共证书。



</div>

本主题介绍了控制器、前端服务器和反向代理所需的已添加主题替代名称。 仅引用添加的主题替代名称 (SAN) 。 有关证书的其他条目的指导，请参阅规划部分。 有关详细信息，请参阅 lync server [2013 中的 Director 方案](lync-server-2013-scenarios-for-the-director.md)、 [lync server 2013 中的外部用户访问](lync-server-2013-scenarios-for-external-user-access.md)方案和 [lync server 2013 中的反向代理](lync-server-2013-scenarios-for-reverse-proxy.md)方案。

下表定义了控制器池、前端池和反向代理的自动发现 SAN 条目：

### <a name="director-pool-certificate-requirements"></a>控制器池证书要求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>说明</th>
<th>使用者替代名称条目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部自动发现服务 URL</p></td>
<td><p>SAN = lyncdiscoverinternal.。 &lt;内部域名&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自动发现服务 URL</p></td>
<td><p>SAN = lyncdiscover.。 &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 将新更新的证书和新的 SAN 条目分配给默认证书。 或者，也可以使用 SAN = *。 &lt;sipdomain &gt; 。



</div>

### <a name="front-end-pool-certificate-requirements"></a>前端池证书要求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>说明</th>
<th>使用者替代名称条目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>内部自动发现服务 URL</p></td>
<td><p>SAN = lyncdiscoverinternal.。 &lt;内部域名&gt;</p></td>
</tr>
<tr class="even">
<td><p>外部自动发现服务 URL</p></td>
<td><p>SAN = lyncdiscover.。 &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 将新更新的证书和新的 SAN 条目分配给默认证书。 或者，也可以使用 SAN = *。 &lt;sipdomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>反向代理（公共 CA）证书要求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>说明</th>
<th>使用者替代名称条目</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>外部自动发现服务 URL</p></td>
<td><p>SAN = lyncdiscover.。 &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> 将新更新的证书和新的 SAN 条目分配给反向代理上的 SSL 侦听器。



</div>

</div>

<span> </span>

</div>

</div>

</div>

