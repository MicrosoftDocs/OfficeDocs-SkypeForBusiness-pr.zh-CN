---
title: Lync Server 2013：MonitoredRegionLink 表
TOCTitle: MonitoredRegionLink 表
ms:assetid: cebda194-7be3-42d6-b6f0-c86f8b0f200a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398874(v=OCS.15)
ms:contentKeyID: 49314285
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 MonitoredRegionLink 表

 

_**上一次修改主题：** 2015-03-09_

MonitoredRegionLink 表是一个支持表。每条记录都代表两个国家/地区之间的一个链接。


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
<td><p><strong>Region1Key</strong></p></td>
<td><p>int</p></td>
<td><p>主、外</p></td>
<td><p>引用自 <a href="lync-server-2013-region-table.md">Lync Server 2013 中的 Region 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>Region2Key</strong></p></td>
<td><p>int</p></td>
<td><p>主、外</p></td>
<td><p>引用自 <a href="lync-server-2013-region-table.md">Lync Server 2013 中的 Region 表</a>。</p></td>
</tr>
</tbody>
</table>

