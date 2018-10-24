---
title: Lync Server 2013：Conference 表
TOCTitle: Conference 表
ms:assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425762(v=OCS.15)
ms:contentKeyID: 49312326
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Conference 表

 

_**上一次修改主题：** 2015-03-09_

会议表是一个支持表。每条记录代表一个会议或点对点会话。


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
<td><p><strong>ConferenceKey</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识该会议记录的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfURI</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>唯一</p></td>
<td><p>如果是会议，则是会议 URI；如果是点对点会话，则是 DialogID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Checksum</strong></p></td>
<td><p>int</p></td>
<td><p>索引</p></td>
<td><p>会议 URI 的校验和。该项仅供内部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
</tbody>
</table>

