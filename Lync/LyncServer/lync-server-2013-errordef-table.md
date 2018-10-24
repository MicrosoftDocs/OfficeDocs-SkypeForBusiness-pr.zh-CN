---
title: Lync Server 2013：ErrorDef 表
TOCTitle: ErrorDef 表
ms:assetid: 6acf3b86-da61-4923-9812-300db6f66dec
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398503(v=OCS.15)
ms:contentKeyID: 49313144
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 ErrorDef 表

 

_**上一次修改主题：** 2015-03-09_

ErrorDef 表存储有关可能发生的每种错误类型的信息。每条记录是一种错误类型。


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
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识此错误类型的唯一 ID 号。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>与此错误关联的标准 SIP 响应代码。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>Microsoft 诊断 ID。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫的类型。有关详细信息，请参阅 <a href="lync-server-2013-calltype-table.md">Lync Server 2013 中的 CallType 表</a></p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varbinary(33)</p></td>
<td><p> </p></td>
<td><p>失败的请求的类型。</p>
<p>可以使用以下语法将此数据转换为文本格式：</p>
<p><code>cast(cast(RequestType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>varbinary(257)</p></td>
<td><p> </p></td>
<td><p>失败的请求的内容类型。</p>
<p>使用以下语法可将此类数据转换为文本格式：</p>
<p><code>cast(cast(ContentType as varbinary(max)) as varchar(max))</code></p></td>
</tr>
</tbody>
</table>

