---
title: Lync Server 2013：AppliedBandwidthSource 表
TOCTitle: AppliedBandwidthSource 表
ms:assetid: 24fb3caf-19b3-4c0a-90d7-ca5d53de32ad
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425725(v=OCS.15)
ms:contentKeyID: 49312269
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 AppliedBandwidthSource 表

 

_**上一次修改主题：** 2015-03-09_

AppliedBandwidthSource 表是一个支持表。每条记录分别表示一个来源。


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
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识来源的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthSource</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>唯一</p></td>
<td><p>这是所设定的带宽限制的来源。它描述带宽限制源自的位置（例如，“策略服务器”、“TURN 服务器”或“形式”）。</p></td>
</tr>
</tbody>
</table>

