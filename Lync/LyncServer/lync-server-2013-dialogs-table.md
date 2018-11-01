---
title: Lync Server 2013：Dialogs 表
TOCTitle: Dialogs 表
ms:assetid: 487a430b-af66-4ea6-b28e-4e33cfdb7f9e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425954(v=OCS.15)
ms:contentKeyID: 49312733
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 Dialogs 表

 

_**上一次修改主题：** 2015-03-09_

Dialogs 表是一个支持表，用于存储有关点对点会话的 DialogID 的信息。


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
<td><p>主</p></td>
<td><p>会话请求的时间；与 SessionIDSeq 结合使用来唯一地标识会话。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>用于标识会话的 ID 号。与 SessionIDTime 结合使用来唯一地标识会话。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ExternalChecksum</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>ExternalID 的校验和。此字段用于增加数据库搜索的速度。</p></td>
</tr>
<tr class="even">
<td><p><strong>ExternalId</strong></p></td>
<td><p>varbinary(775)</p></td>
<td><p> </p></td>
<td><p>SIP 对话 ID，存储为二进制。二进制的格式为：</p>
<p>dialog;from-tag;to-tag</p>
<p>可以使用以下语法将此数据转换为文本格式：</p>
<p><code>cast(cast(ExternalId as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>

