---
title: Lync Server 2013：Pools 表
TOCTitle: Pools 表
ms:assetid: e0632b8d-e23a-4365-8a7a-6ca0957a46a9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398991(v=OCS.15)
ms:contentKeyID: 49314498
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Pools 表

 

_**上一次修改主题：** 2015-03-09_

Pools 表是存储有关各个池的信息的支持表。表中的每条记录分别表示一个池。


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
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识此池的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolFQDN</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p> </p></td>
<td><p>池 FQDN。</p></td>
</tr>
</tbody>
</table>

