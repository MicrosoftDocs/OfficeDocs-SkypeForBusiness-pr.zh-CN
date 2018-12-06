---
title: Lync Server 2013：CallPriorities 表
TOCTitle: CallPriorities 表
ms:assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398093(v=OCS.15)
ms:contentKeyID: 49311848
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 CallPriorities 表

 

_**上一次修改主题：** 2015-03-09_

CallPriorities 表是一个静态表，用于存储可能的呼叫优先级（例如“紧迫”、“紧急”或“普通”）列表。


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
<td><p><strong>PriorityId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Priority</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>允许的值：</p>
<ul>
<li><p>0 – 未知</p></li>
<li><p>1 – 非紧急</p></li>
<li><p>2 – 普通</p></li>
<li><p>3 – 紧急</p></li>
<li><p>4 – 紧迫</p></li>
</ul></td>
</tr>
</tbody>
</table>

