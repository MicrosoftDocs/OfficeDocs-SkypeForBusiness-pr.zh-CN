---
title: Lync Server 2013：Roles 表
TOCTitle: Roles 表
ms:assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399043(v=OCS.15)
ms:contentKeyID: 49314593
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Roles 表

 

_**上一次修改主题：** 2015-03-09_

角色表是一个静态表，用于存储可能的会议角色（如与者会和演示者）的列表。


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
<td><p><strong>RoleId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>角色</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>允许的值：</p>
<ul>
<li><p>0 -- 未知</p></li>
<li><p>1 -- 演示者</p></li>
<li><p>2 -- 与会者</p></li>
</ul></td>
</tr>
</tbody>
</table>

