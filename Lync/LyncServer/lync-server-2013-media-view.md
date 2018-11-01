---
title: 媒体视图
TOCTitle: 媒体视图
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49888319
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 媒体视图

 

_**上一次修改主题：** 2015-03-09_

“媒体”视图存储有关在对等会话中使用的一种媒体类型的信息。如果使用多个媒体类型，则一个会话由表中的多条记录表示。此视图是在 Microsoft Lync Server 2013 中引入的。

> [!NOTE]  
> “媒体”视图不应用来计算会话的媒体持续时间。此视图包含会话中的媒体交换信号详情。媒体交换通过 INVITE 请求实现，StartTime 指示发出 INVITE 的时间。邀请时间不一定表示媒体的启动时间，因为仅在会话被接受后，媒体才启动。



除了下面列出的内容外，“媒体”视图还包含 [SessionDetails 视图](lync-server-2013-sessiondetails-view.md)中的所有列。


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
<td><p><strong>Media</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>媒体类型。有关详细信息，请参阅 <a href="lync-server-2013-medialist-table.md">Lync Server 2013 中的 MediaList 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>MediaStartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>发出媒体请求的时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>会话的结束时间。</p></td>
</tr>
</tbody>
</table>

