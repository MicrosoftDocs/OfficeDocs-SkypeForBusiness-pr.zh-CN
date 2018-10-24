---
title: FileTransfers 视图
TOCTitle: FileTransfers 视图
ms:assetid: e52c3ad0-152e-4a18-af1c-1aff0d205151
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721914(v=OCS.15)
ms:contentKeyID: 49888648
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# FileTransfers 视图

 

_**上一次修改主题：** 2015-03-09_

FileTranfer 视图存储有关点对点文件传输会话的信息。Microsoft Lync Server 2013 中已引入了此视图。

> [!NOTE]  
> 除以下列出的列外，FileTransfers 视图还包含 <a href="lync-server-2013-sessiondetails-view.md">SessionDetails 视图</a> 中的所有列。




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
<td><p><strong>FileName</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>文件传输的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>Cookie</strong></p></td>
<td><p>nvarchar(128)</p></td>
<td><p>用于标识与此关联时的每条后续消息。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>涉及相同文件名的文件传输之间标识的唯一标识符。</p></td>
</tr>
<tr class="even">
<td><p><strong>接受</strong></p></td>
<td><p>位</p></td>
<td><p>可以是 TRUE 或 NULL。如果是 TRUE，则拒绝和取消将为 NULL。</p></td>
</tr>
<tr class="odd">
<td><p><strong>拒绝</strong></p></td>
<td><p>位</p></td>
<td><p>可以是 TRUE 或 NULL。如果是 TRUE，则接受和取消将为 NULL。</p></td>
</tr>
<tr class="even">
<td><p><strong>取消</strong></p></td>
<td><p>位</p></td>
<td><p>可以是 TRUE 或 NULL。如果是 TRUE，则接受和拒绝将为 NULL。</p></td>
</tr>
</tbody>
</table>

