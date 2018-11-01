---
title: Lync Server 2013：tblScopePrincipal
TOCTitle: tblScopePrincipal
ms:assetid: 422d6c7f-7ba7-4dd4-bacc-95ace47959ff
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558639(v=OCS.15)
ms:contentKeyID: 49312659
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblScopePrincipal

 

_**上一次修改主题：** 2015-03-09_

tblScopePrincipal 包含分配至节点的作用域。

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
<td><p>scopeNodeID</p></td>
<td><p>int，不为 null</p></td>
<td><p>作用域适用的节点 ID。</p></td>
</tr>
<tr class="even">
<td><p>scopePrinID</p></td>
<td><p>int，不为 null</p></td>
<td><p>主体 ID。</p></td>
</tr>
<tr class="odd">
<td><p>scopeIsDenied</p></td>
<td><p>bit，不为 null</p></td>
<td><p>如果作用域的类型为 Deny，则为 True；如果作用域的类型为 Allow，则为 False。</p></td>
</tr>
<tr class="even">
<td><p>scopeUpdatedBy</p></td>
<td><p>int，不为 null</p></td>
<td><p>上次更新此项的主体的 ID。</p></td>
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
<td><p>&lt;scopeNodeID, scopePrinID&gt;</p></td>
<td><p>主键。</p></td>
</tr>
<tr class="even">
<td><p>scopeNodeID</p></td>
<td><p>在 tblNode.nodeID 表中查找的外键。</p></td>
</tr>
<tr class="odd">
<td><p>scopePrinID</p></td>
<td><p>在 tblPrincipal.prinID 表中查找的外键。</p></td>
</tr>
</tbody>
</table>

