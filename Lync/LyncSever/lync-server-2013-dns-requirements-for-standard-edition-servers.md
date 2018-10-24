---
title: Standard Edition Server 的 DNS 要求
TOCTitle: Standard Edition Server 的 DNS 要求
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425900(v=OCS.15)
ms:contentKeyID: 49312577
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Standard Edition Server 的 DNS 要求

 

_**上一次修改主题：** 2015-03-09_

本节介绍部署 Standard Edition Server 所需的域名系统 (DNS) 记录。

## Standard Edition Server 的 DNS 记录

下表指定了 Lync Server 2013 Standard Edition Server 部署的 DNS 要求。

### Standard Edition Server 的 DNS 要求

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
<td><p>Standard Edition Server</p></td>
<td><p>将服务器的完全限定域名 (FQDN) 解析为其 IP 地址的内部 A 记录。</p></td>
</tr>
<tr class="even">
<td><p>自动客户端登录</p></td>
<td><p>对于每个受支持的 SIP 域，都有一条 _sipinternaltls._tcp.<em>&lt;域&gt;</em> 的 SRV 记录，通过端口 5061 映射到对客户端登录请求进行身份验证和重定向的 Standard Edition Server 的 FQDN。有关详细信息，请参阅<a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">自动客户端登录的 DNS 要求</a>。</p></td>
</tr>
<tr class="odd">
<td><p>统一通信 (UC) 设备发现设备更新 Web 服务</p></td>
<td><p>有一条名为 ucupdates-r2.<em>&lt;SIP 域&gt;</em> 的内部 A 记录，解析为承载设备更新 Web 服务的 Standard Edition Server 的 IP 地址。在打开了 UC 设备，但用户从未登录到设备的情况下，设备通过该 A 记录可以发现承载设备更新 Web 服务的服务器并获得更新。否则，设备在用户首次登录时通过带内设置获得服务器信息。</p></td>
</tr>
<tr class="even">
<td><p>支持 HTTP 流量的反向代理</p></td>
<td><p>将外部 Web 场 FQDN 解析为反向代理的外部 IP 地址的外部 A 记录。客户端和 UC 设备使用此记录连接到反向代理。有关详细信息，请参阅规划文档中的<a href="lync-server-2013-determine-dns-requirements.md">确定 Lync Server 2013 的 DNS 要求</a>。</p></td>
</tr>
</tbody>
</table>

