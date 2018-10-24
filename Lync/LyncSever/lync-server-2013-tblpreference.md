---
title: Lync Server 2013：tblPreference
TOCTitle: tblPreference
ms:assetid: f94eb128-f782-42ff-a568-ed3529573bc8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615052(v=OCS.15)
ms:contentKeyID: 49314805
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblPreference

 

_**上一次修改主题：** 2015-03-09_

tblPreference 包含用户的客户端首选项。这通常由 Lync 2013 版本之前的客户端使用。

### 列

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>类型</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>prefLabel</p></td>
<td><p>nvarchar (255)，不为 null</p></td>
<td><p>使用如下格式标记：&lt;user sip uri&gt;|username.&lt;preference set&gt;。</p></td>
</tr>
<tr class="even">
<td><p>prefSeqID</p></td>
<td><p>int，不为 null</p></td>
<td><p>用于版本控制的序号（每标签）。</p></td>
</tr>
<tr class="odd">
<td><p>prefContent</p></td>
<td><p>nvarchar (max)</p></td>
<td><p>编码内容。</p></td>
</tr>
<tr class="even">
<td><p>lastModifiedBy</p></td>
<td><p>int，不为 null</p></td>
<td><p>更新首选项的主体的 ID。</p></td>
</tr>
</tbody>
</table>


### 键

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;prefLabel, prefSeqID&gt;</p></td>
<td><p>主键。</p></td>
</tr>
</tbody>
</table>

