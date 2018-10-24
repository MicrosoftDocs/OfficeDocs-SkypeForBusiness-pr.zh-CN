---
title: Lync Server 2013 中的 IPAddress 表
TOCTitle: Lync Server 2013 中的 IPAddress 表
ms:assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205077(v=OCS.15)
ms:contentKeyID: 49313560
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 IPAddress 表

 

_**上一次修改主题：** 2015-03-09_

IPAddress 表将 IP 地址映射到可在用户体验质量数据库中的任何其他位置使用的唯一 IP 地址标识符。此表是在 Microsoft Lync Server 2013 中引入的。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>列</strong></th>
<th><strong>数据类型</strong></th>
<th><strong>键/索引</strong></th>
<th><strong>详细信息</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>IPAddressKey</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>指定的 IP 地址的唯一标识符。</p></td>
</tr>
<tr class="even">
<td><p><strong>IPAddress</strong></p></td>
<td><p>varchar(50)</p></td>
<td><p>唯一</p></td>
<td><p>映射到 IpAddressKey 的唯一 IP 地址（例如，189.168.1.1）。这可能是 IPv4 地址或 IPv6 地址。</p></td>
</tr>
</tbody>
</table>

