---
title: 'Lync Server 2013: 前端池的 DNS 要求'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 03759267ea10a4eaf7046fd25390b45265e479f6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a>Lync Server 2013 中前端池的 DNS 要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-07_

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
<td><p>具有多个前端服务器和硬件负载平衡器 (无论是否还在该池中部署了 DNS 负载平衡) 的前端池</p></td>
<td><p>同时使用 DNS 负载平衡和硬件负载平衡器时, 你需要托管 (A) 条记录。 创建一个内部 A 记录, 用于解析用于 DNS 负载平衡的前端池的完全限定的域名 (FQDN)。 为内部 Web 服务创建内部主机 (A) 记录以使用负载平衡器的虚拟 IP (VIP) 地址。 你必须使用拓扑生成器中定义的内部 Web 服务名称。</p>
<p>例如, 如果你同时使用 DNS 负载平衡和硬件负载平衡, 你将在一个池中为 DNS 负载平衡的池中的每个前端服务器提供一个记录, 并提供指向硬件负载平衡器的虚拟 IP 的内部 Web 服务的 A 记录:</p>
<ul>
<li><p>DNS 负载平衡: Pool01.contoso.net 的 IP 地址池10.10.10。5</p>
<div>

> [!WARNING]  
> 每个前端服务器还将具有不同的 A 记录:


</div>
<ol>
<li><p>FE01.contoso.net 10.10.10。1</p></li>
<li><p>FE02.contoso.net 10.10.10。2</p></li>
<li><p>FE03.contoso.net 10.10.10。3</p></li>
<li><p>FE04.contoso.net 10.10.10。4</p></li>
</ol></li>
<li><p>硬件负载平衡: WebInternal.contoso.net HLB VIP 192.168.10.5 的 IP 地址</p></li>
</ul>
<p>除 HTTP/HTTPS 流量之外的所有通信都将使用 Pool01.contoso.net 记录。 HTTP/HTTPS 流量将使用已定义的内部 Web 服务地址192.168.10。5</p></td>
</tr>
<tr class="even">
<td><p>部署了 DNS 负载平衡的前端池</p></td>
<td><p>一组内部 A 记录, 用于将池的 FQDN 解析为池中每台服务器的 IP 地址。 池中每台服务器必须有一条记录。</p></td>
</tr>
<tr class="odd">
<td><p>部署了 DNS 负载平衡的前端池</p></td>
<td><p>一组内部 A 记录, 用于将池中的每个服务器的 FQDN 解析为该服务器的 IP 地址。 有关详细信息, 请参阅规划文档中<a href="lync-server-2013-dns-load-balancing.md">Lync Server 2013 中的 "DNS 负载平衡</a>"。</p></td>
</tr>
<tr class="even">
<td><p>带有单个前端服务器和专用后端数据库但没有负载平衡器的前端池</p></td>
<td><p>一个内部 A 记录, 可将前端池的 FQDN 解析为单个企业版前端服务器的 IP 地址。</p></td>
</tr>
<tr class="odd">
<td><p>自动客户端登录</p></td>
<td><p>对于每个受支持的 SIP 域, _sipinternaltls _tcp 的 SRV 记录。&lt;通过&gt;端口5061的域映射到用于对登录的客户端请求进行身份验证和重定向的前端池的 FQDN。 有关详细信息, 请参阅<a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">Lync Server 2013 中的自动客户端登录 DNS 要求</a>。</p></td>
</tr>
<tr class="even">
<td><p>通过统一通信 (UC) 设备进行的设备更新 Web 服务发现</p></td>
<td><p>名为 ucupdates-r2 的内部 A 记录。&lt;SIP 域&gt; , 可解析为托管设备更新 Web 服务的前端池的 IP 地址。 在 UC 设备处于打开状态但用户从未登录到设备的情况下, A 记录允许设备发现前端池托管设备更新 Web 服务并获取更新。 否则, 设备会在用户第一次登录时通过带内预配获取此信息。</p>
<div>

> [!IMPORTANT]  
> 如果您在 Lync Server 2010 中已有设备更新 Web 服务的现有部署, 则您已使用名称 ucupdates 创建了一个内部 A 记录。&lt;SIP 域&gt;。 对于 Microsoft Office 通信服务器 2007 R2, 必须创建一个名为 ucupdates-R2 的附加 DNS A 记录。&lt;SIP 域&gt;。


</div></td>
</tr>
<tr class="odd">
<td><p>支持 HTTP 流量的反向代理</p></td>
<td><p>将外部 web 场 FQDN 解析为反向代理的外部 IP 地址的外部 A 记录。 客户端和 UC 设备使用此记录连接到反向代理。 有关详细信息, 请参阅在规划文档中<a href="lync-server-2013-determine-dns-requirements.md">确定 Lync Server 2013 的 DNS 要求</a>。</p></td>
</tr>
</tbody>
</table>


下表显示内部 web 场 FQDN 所需的 DNS 记录的示例。

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a>内部 Web 场 FQDN 的 DNS 记录示例

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>内部 web 场 FQDN</th>
<th>池 FQDN</th>
<th>DNS A 记录</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>webcon.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>Ee-pool.contoso.com 的 DNS A 记录, 它解析为前端服务器使用的负载平衡器的 VIP 地址。</p>
<p>用于解析为前端服务器使用的负载平衡器的 VIP 地址的 webcon.contoso.com 的 DNS A 记录。</p></td>
</tr>
<tr class="even">
<td><p>ee-pool.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>Ee-pool.contoso.com 的 DNS A 记录, 用于解析为前端池中的企业版前端服务器使用的负载平衡器的虚拟 IP (VIP) 地址。</p>
<p>请注意, 如果在此池中使用 DNS 负载平衡, 则您的前端池和内部 web 场不能具有相同的 FQDN。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

