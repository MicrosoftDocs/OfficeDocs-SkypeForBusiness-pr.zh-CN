---
title: Lync Server 2013：前端池的 DNS 要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a1808e4b65e900b5a38de1d76e7da17fe055d270
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48526829"
---
# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a>Lync Server 2013 中前端池的 DNS 要求

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-07_

本节介绍部署前端池所需的域名系统 (DNS) 记录。

<div>

## <a name="dns-records-for-front-end-pools"></a>前端池的 DNS 记录

下表指定了 Lync Server 2013 前端池部署的 DNS 要求。

### <a name="dns-requirements-for-a-front-end-pool"></a>前端池的 DNS 要求

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>部署方案</th>
<th>DNS 要求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>带有多个前端服务器和一个硬件负载平衡器的前端池（该池上是否也部署了 DNS 负载平衡）</p></td>
<td><p>在同时使用 DNS 负载平衡和硬件负载平衡器时，您需要主机 (A) 记录。 为 DNS 负载平衡创建将解析前端池的完全限定域名 (FQDN) 的内部 A 记录。 为内部 Web 服务创建针对负载平衡器的虚拟 IP (VIP) 地址的内部主机 (A) 记录。 您必须使用拓扑生成器中定义的内部 Web 服务名称。</p>
<p>例如，如果同时使用 DNS 负载平衡和硬件负载平衡，则会为池内的每个前端服务器提供一个记录，以实现 DNS 负载平衡，将内部 Web 服务的 A 记录用于指向硬件负载平衡器的虚拟 IP：</p>
<ul>
<li><p>DNS 负载平衡：   Pool01.contoso.net   池的 IP 地址   10.10.10.5</p>
<div>

> [!WARNING]  
> 每个前端服务器也将具有不同的 A 记录：


</div>
<ol>
<li><p>FE01.contoso.net 10.10.10。1</p></li>
<li><p>FE02.contoso.net 10.10.10。2</p></li>
<li><p>FE03.contoso.net 10.10.10。3</p></li>
<li><p>FE04.contoso.net 10.10.10。4</p></li>
</ol></li>
<li><p>硬件负载平衡：   WebInternal.contoso.net    HLB VIP 的 IP 地址   192.168.10.5</p></li>
</ul>
<p>除 HTTP/HTTPS 流量之外的所有流量都将使用 Pool01.contoso.net 记录。HTTP/HTTPS 流量将使用定义的内部 Web 服务地址 192.168.10.5</p></td>
</tr>
<tr class="even">
<td><p>部署了 DNS 负载平衡的前端池</p></td>
<td><p>将池的 FQDN 解析为池中每个服务器的 IP 地址的一组内部 A 记录。池中的每个服务器都必须有一个 A 记录。</p></td>
</tr>
<tr class="odd">
<td><p>部署了 DNS 负载平衡的前端池</p></td>
<td><p>将池中每个服务器的 FQDN 解析为该服务器的 IP 地址的一组内部 A 记录。 有关详细信息，请参阅规划文档中的 <a href="lync-server-2013-dns-load-balancing.md">Lync Server 2013 中的 DNS 负载平衡</a> 。</p></td>
</tr>
<tr class="even">
<td><p>具有一个前端服务器和一个专用后端数据库、但没有负载平衡器的前端池</p></td>
<td><p>将前端池的 FQDN 解析为单个 Enterprise Edition 前端服务器的 IP 地址的内部 A 记录。</p></td>
</tr>
<tr class="odd">
<td><p>自动客户端登录</p></td>
<td><p>对于每个受支持的 SIP 域，_sipinternaltls 的 SRV 记录。 _tcp c0/>&gt;通过端口5061的域映射到前端池的 FQDN，该前端池会对登录的客户端请求进行身份验证和重定向。 有关详细信息，请参阅 <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013 中的自动客户端登录的 DNS 要求</a>。</p></td>
</tr>
<tr class="even">
<td><p>统一通信 (UC) 设备发现设备更新 Web 服务</p></td>
<td><p>一个名为为 ucupdates-r2.-r2 的内部 A 记录。 &lt;&gt;解析为承载设备更新 Web 服务的前端池的 IP 地址的 SIP 域。 在打开了 UC 设备但用户从未登录到该设备的情况下，该设备通过此 A 记录可以发现承载设备更新 Web 服务的前端池并获得更新。 否则，该设备在用户首次登录时通过带内设置获得此信息。</p>
<div>

> [!IMPORTANT]  
> 如果您已在 Lync Server 2010 中部署了设备更新 Web 服务，则您已使用名称为 ucupdates-r2. 创建了一个内部 A 记录。 &lt;SIP 域 &gt; 。 对于 Microsoft Office 通信服务器 2007 R2，必须创建一个名为为 ucupdates-r2.-R2 的附加 DNS A 记录。 &lt;SIP 域 &gt; 。


</div></td>
</tr>
<tr class="odd">
<td><p>支持 HTTP 流量的反向代理</p></td>
<td><p>将外部 Web 场 FQDN 解析为反向代理的外部 IP 地址的外部 A 记录。 客户端和 UC 设备使用此记录连接到反向代理。 有关详细信息，请参阅规划文档中的 <a href="lync-server-2013-determine-dns-requirements.md">确定 Lync Server 2013 的 DNS 要求</a> 。</p></td>
</tr>
</tbody>
</table>


下表显示了内部 Web 场 FQDN 所需的 DNS 记录的示例。

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a>内部 Web 场 FQDN 的 DNS 记录示例

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>内部 Web 场 FQDN</th>
<th>池 FQDN</th>
<th>DNS A 记录</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>webcon.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>ee-pool.contoso.com 的 DNS A 记录，将解析为前端服务器使用的负载平衡器的 VIP 地址。</p>
<p>webcon.contoso.com 的 DNS A 记录，将解析为前端服务器使用的负载平衡器的 VIP 地址。</p></td>
</tr>
<tr class="even">
<td><p>ee-pool.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>ee-pool.contoso.com 的 DNS A 记录，将解析为前端池中 Enterprise Edition 前端服务器所使用的负载平衡器的虚拟 IP (VIP) 地址。</p>
<p>请注意，如果您正对该池使用 DNS 负载平衡，则前端池和内部 Web 场不会有相同的 FQDN。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

