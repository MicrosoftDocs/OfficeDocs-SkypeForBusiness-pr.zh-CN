---
title: ConferenceMessageCount 视图
TOCTitle: ConferenceMessageCount 视图
ms:assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688129(v=OCS.15)
ms:contentKeyID: 49888507
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ConferenceMessageCount 视图

 

_**上一次修改主题：** 2015-03-09_

ConferenceMessageCount 视图存储有关用户已向会议中发送的消息数的信息。此视图是在 Microsoft Lync Server 2013 中引入的。

> [!NOTE]  
> ConferenceMessageCount 视图包含 <a href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails 视图</a>中的所有列以及下面列出的列。




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
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>发送消息的用户的 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>发送消息的用户的 URI 类型。有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>发送消息的用户的租户。有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的 Tenants 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserMessageCount</strong></p></td>
<td><p>smallint</p></td>
<td><p>用户在会议会话期间发送的消息数。</p></td>
</tr>
</tbody>
</table>

