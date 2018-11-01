---
title: ClientVersions 视图
TOCTitle: ClientVersions 视图
ms:assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721891(v=OCS.15)
ms:contentKeyID: 49888610
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ClientVersions 视图

 

_**上一次修改主题：** 2015-03-09_

ClientVersions 视图存储已参与数据库中记录的会话的各种客户端类型和版本的相关信息。视图中的每条记录都代表一个客户端版本。此视图在 Microsoft Lync Server 2013 中引入。

> [!NOTE]  
> 某些列可能有多条记录。




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
<td><p><strong>VersionId</strong></p></td>
<td><p>int</p></td>
<td><p>标识此客户端类型和版本的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>Version</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>代表用户代理。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>客户端类型。</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar(64)</p></td>
<td><p>客户端所属的类别。例如，客户端 Conferencing_Attendant_1.0 属于 ClientCategory CAA。</p></td>
</tr>
</tbody>
</table>

