---
title: ConferenceUris 视图
TOCTitle: ConferenceUris 视图
ms:assetid: 9a3cdcea-426e-4b6b-9876-ba746a8de706
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688148(v=OCS.15)
ms:contentKeyID: 49888528
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ConferenceUris 视图

 

_**上一次修改主题：** 2015-03-09_

ConfernceUris 视图存储有关已参与会议会话的 URI 的信息。此视图是在 Microsoft Lync Server 2013 中引入的。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>数据类型</th>
<th>详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ConferenceUriId</p></td>
<td><p>int</p></td>
<td><p>标识此会议 URI 的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p>ConferenceUri</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>会议的 URI。</p></td>
</tr>
<tr class="odd">
<td><p>ConferenceUriType</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>会议 URI 的类型。有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</p></td>
</tr>
</tbody>
</table>

