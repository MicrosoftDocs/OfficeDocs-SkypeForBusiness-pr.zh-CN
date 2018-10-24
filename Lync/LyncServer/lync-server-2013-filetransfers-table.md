---
title: Lync Server 2013：FileTransfers 表
TOCTitle: FileTransfers 表
ms:assetid: 5368e67c-d8a9-43a1-9472-a839950dedb3
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398353(v=OCS.15)
ms:contentKeyID: 49312860
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 FileTransfers 表

 

_**上一次修改主题：** 2015-03-09_

每条记录代表一个文件传输会话。


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主、外</p></td>
<td><p>会话请求的时间。与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主、外</p></td>
<td><p>用于标识会话的 ID 号。与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会话。有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>File Name</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p></p></td>
<td><p>文件的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>FileIdentity</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p></p></td>
<td><p>涉及相同文件名的文件传输之间标识的唯一标识符。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Cookie</strong></p></td>
<td><p>nvarchar (128)</p></td>
<td><p>主</p></td>
<td><p>用于标识与此关联时的每条后续消息。</p></td>
</tr>
<tr class="even">
<td><p><strong>接受</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>可以是 TRUE 或 NULL。如果是 TRUE，则拒绝和取消将为 NULL。</p></td>
</tr>
<tr class="odd">
<td><p><strong>拒绝</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>可以是 TRUE 或 NULL。如果是 TRUE，则接受和取消将为 NULL。</p></td>
</tr>
<tr class="even">
<td><p><strong>取消</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>可以是 TRUE 或 NULL。如果是 TRUE，则接受和拒绝将为 NULL。</p></td>
</tr>
</tbody>
</table>

