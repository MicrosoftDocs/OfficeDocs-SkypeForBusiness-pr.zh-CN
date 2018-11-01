---
title: Lync Server 2013：Pool 表
TOCTitle: Pool 表
ms:assetid: 92ded8fd-d0ad-4f8a-9e6f-2e8a690fda3a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398746(v=OCS.15)
ms:contentKeyID: 49313623
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Pool 表

 

_**上一次修改主题：** 2015-03-09_

Pool 表是存储有关各种前端池的信息的支持表。表中的每条记录分别表示一个池。


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
<td><p><strong>PoolKey</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识此池的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolName</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>唯一</p></td>
<td><p>池 FQDN。</p></td>
</tr>
</tbody>
</table>

