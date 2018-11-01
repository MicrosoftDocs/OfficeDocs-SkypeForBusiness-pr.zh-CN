---
title: Lync Server 2013：SessionCorrelation 表
TOCTitle: SessionCorrelation 表
ms:assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398091(v=OCS.15)
ms:contentKeyID: 49311843
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 SessionCorrelation 表

 

_**上一次修改主题：** 2015-03-09_

SessionCorrelation 表是一个支持表。每条记录代表一个用于关联多个会话的 CorrelationID。


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
<td><p><strong>Checksum</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>CorrelationKey</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识该 A/V 会议服务器的唯一编号。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CorrelationID</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>唯一</p></td>
<td><p>关联的会话将具有同一关联 ID。</p></td>
</tr>
<tr class="even">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>仅供内部使用。</p></td>
</tr>
</tbody>
</table>

