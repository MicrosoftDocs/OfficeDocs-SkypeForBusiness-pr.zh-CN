---
title: Lync Server 2013：Servers 表
TOCTitle: Servers 表
ms:assetid: 1535e676-a647-4606-bc56-e8bfde5ca823
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398223(v=OCS.15)
ms:contentKeyID: 49312096
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Servers 表

 

_**上一次修改主题：** 2015-03-09_

服务器表是一个支持表，用于存储有关各种服务器的信息。表中的每条记录表示一台服务器。


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
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识此服务器的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerFQDN</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p> </p></td>
<td><p>服务器 FQDN。</p></td>
</tr>
</tbody>
</table>

