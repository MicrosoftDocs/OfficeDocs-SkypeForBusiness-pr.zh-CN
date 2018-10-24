---
title: Lync Server 2013：ContentTypes 表
TOCTitle: ContentTypes 表
ms:assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg399007(v=OCS.15)
ms:contentKeyID: 49314544
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 ContentTypes 表

 

_**上一次修改主题：** 2015-03-09_

ContentTypes 表是一个支持表，存储点对点对话和会议会话中使用的内容类型的列表。该表中的每条记录表示一个内容类型。


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
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识内容类型的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td> </td>
<td><p>内容类型名称。</p></td>
</tr>
</tbody>
</table>

