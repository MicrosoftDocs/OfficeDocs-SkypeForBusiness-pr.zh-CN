---
title: 前端池的 DNS 要求
TOCTitle: 前端池的 DNS 要求
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412910(v=OCS.15)
ms:contentKeyID: 49314045
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 前端池的 DNS 要求

 

_**上一次修改主题：** 2015-03-09_

本节介绍部署前端池所需的域名系统 (DNS) 记录。

## 前端池的 DNS 记录

下表指定 Lync Server 2013 前端池部署的 DNS 要求。

### 前端池的 DNS 要求

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
<td><p>在同时使用 DNS 负载平衡和硬件负载平衡器时，您需要主机 (A) 记录。您需要创建一个可解析前端池的完全限定域名 (FQDN) 的内部 A 记录来实现 DNS 负载平衡。并为指向负载平衡器的虚拟 IP (VIP) 地址的内部 Web 服务创建一个内部主机 (A) 记录。您必须使用拓扑生成器中定义的内部 Web 服务名称。</p>
<p>例如，如果您同时使用 DNS 负载平衡和硬件负载平衡器，则需要为 DNS 负载平衡池中的每个前端服务器创建一个 A 记录，并为指向硬件负载平衡器的虚拟 IP 的内部 Web 服务创建一个 A 记录：</p>
<ul>
<li><p>DNS 负载平衡：   Pool01.contoso.net   池的 IP 地址   10.10.10.5</p>
<div>

> [!WARNING]
> 每个前端服务器也将具有一个单独的 A 记录：

</div>
<ol>
<li><p>FE01.contoso.net    10.10.10.1</p></li>
<li><p>FE02.contoso.net    10.10.10.2</p></li>
<li><p>FE03.contoso.net    10.10.10.3</p></li>
<li><p>FE04.contoso.net    10.10.10.4</p></li>
</ol></li>
<li><p>硬件负载平衡：   WebInternal.contoso.net   HLB VIP 的 IP 地址   192.168.10.5</p></li>
</ul>
<p>除 HTTP/HTTPS 通信之外的所有通信都将使用 Pool01.contoso.net 记录。HTTP/HTTPS 通信将使用定义的内部 Web 服务地址 192.168.10.5</p></td>
</tr>
<tr class="even">
<td><p>部署了 DNS 负载平衡的前端池</p></td>
<td><p>将池的 FQDN 解析为池中每个服务器的 IP 地址的一组内部 A 记录。池中的每个服务器都必须有一个 A 记录。</p></td>
</tr>
<tr class="odd">
<td><p>部署了 DNS 负载平衡的前端池</p></td>
<td><p>将池中每个服务器的 FQDN 解析为该服务器的 IP 地址的一组内部 A 记录。有关详细信息，请参阅规划文档中的 <a href="lync-server-2013-dns-load-balancing.md">Lync Server 2013 中的 DNS 负载平衡</a>。</p></td>
</tr>
<tr class="even">
<td><p>具有一个前端服务器和一个专用后端数据库、但没有负载平衡器的前端池</p></td>
<td><p>将前端池的 FQDN 解析为单个 Enterprise Edition 前端服务器的 IP 地址的内部 A 记录。</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>自动客户端登录</p></td>
<td><p>对于每个受支持的 SIP 域，都有一条针对 _sipinternaltls._tcp.&lt;域&gt; 的 SRV 记录，通过端口 5061 映射到对客户端登录请求进行身份验证和重定向的前端池的 FQDN。有关详细信息，请参阅<a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">自动客户端登录的 DNS 要求</a>。</p></td>
</tr>
<tr class="even">
<td><p>统一通信 (UC) 设备发现设备更新 Web 服务</p></td>
<td><p>有一条名为 ucupdates-r2.&lt;SIP 域&gt; 的内部 A 记录，解析为承载设备更新 Web 服务的前端池的 IP 地址。在打开了 UC 设备但用户从未登录到该设备的情况下，该设备通过此 A 记录可以发现承载设备更新 Web 服务的前端池并获得更新。否则，该设备在用户首次登录时通过带内设置获得此信息。</p>
<div>

> [!IMPORTANT]
> 如果 Lync Server 2010 中已部署设备更新 Web 服务，则已创建名为 ucupdates.<em>&lt;SIP 域&gt;</em> 的内部 A 记录。对于 Microsoft Office Communications Server 2007 R2，必须另外创建一条名为 ucupdates-r2.<em>&lt;SIP 域&gt;</em> 的 DNS A 记录。

</div></td>
</tr>
<tr class="odd">
<td><p>支持 HTTP 流量的反向代理</p></td>
<td><p>将外部 Web 场 FQDN 解析为反向代理的外部 IP 地址的外部 A 记录。客户端和 UC 设备使用此记录连接到反向代理。有关详细信息，请参阅规划文档中的<a href="lync-server-2013-determine-dns-requirements.md">确定 Lync Server 2013 的 DNS 要求</a>。</p></td>
</tr>
</tbody>
</table>


下表显示了内部 Web 场 FQDN 所需的 DNS 记录的示例。

### 内部 Web 场 FQDN 的 DNS 记录示例

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

