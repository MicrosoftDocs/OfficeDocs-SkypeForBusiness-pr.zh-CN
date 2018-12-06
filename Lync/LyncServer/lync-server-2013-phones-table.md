---
title: Lync Server 2013：Phones 表
TOCTitle: Phones 表
ms:assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425923(v=OCS.15)
ms:contentKeyID: 49312657
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Phones 表

 

_**上一次修改主题：** 2015-03-09_

Phones 表是一个支持表。表中的每条记录存储有关一个电话号码（在数据库中具有记录的 VoIP 呼叫涉及该号码）的信息。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>数据类型</th>
<th>键/索引</th>
<th>详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>PhoneId</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识此电话的唯一号码。</p></td>
</tr>
<tr class="even">
<td><p><strong>PhoneUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p> </p></td>
<td><p>电话号码。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NextUpdateTS</strong></p></td>
<td><p>dateTime</p></td>
<td><p></p></td>
<td><p>时间戳（仅供内部使用）。</p>
<p>Microsoft Lync Server 2013 中已引入了此字段。</p></td>
</tr>
</tbody>
</table>

