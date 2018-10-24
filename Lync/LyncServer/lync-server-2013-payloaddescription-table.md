---
title: Lync Server 2013：PayloadDescription 表
TOCTitle: PayloadDescription 表
ms:assetid: c49d61c0-305a-4770-a5d2-5d9f05decc6d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412971(v=OCS.15)
ms:contentKeyID: 49314189
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 PayloadDescription 表

 

_**上一次修改主题：** 2015-03-09_

PayloadDescription 表是一个支持表。每条记录都代表一个音频或视频会话使用的编解码器。


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
<td><p><strong>PayloadDescriptionKey</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>用于标识该编解码器的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>PayloadDescription</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>唯一</p></td>
<td><p>编解码器的名称。</p></td>
</tr>
</tbody>
</table>

