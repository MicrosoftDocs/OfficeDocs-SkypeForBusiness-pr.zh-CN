---
title: Lync Server 2013：tblPrincipalRole
TOCTitle: tblPrincipalRole
ms:assetid: dcd16dc1-a66c-4720-a48f-ec8b28337383
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615039(v=OCS.15)
ms:contentKeyID: 49314475
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblPrincipalRole

 

_**上一次修改主题：** 2015-03-09_

tblPrincipalRole 包含分配给节点的显式角色。

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
<td><p>prinRoleNodeID</p></td>
<td><p>int，不为 null</p></td>
<td><p>角色适用的节点 ID。</p></td>
</tr>
<tr class="even">
<td><p>prinRolePfrinID</p></td>
<td><p>int，不为 null</p></td>
<td><p>主体 ID。</p></td>
</tr>
<tr class="odd">
<td><p>prinRoleTypeID</p></td>
<td><p>int，不为 null</p></td>
<td><p>角色类型 ID（来自 tblRoleType）。</p></td>
</tr>
<tr class="even">
<td><p>prinRoleUpdatedBy</p></td>
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
<td><p>&lt;prinRoleNodeID、prinRolePrinID、prinRoleTypeID&gt;</p></td>
<td><p>主键。</p></td>
</tr>
<tr class="even">
<td><p>prinRoleNodeID</p></td>
<td><p>在 tblNode.nodeID 表中查找的外键。</p></td>
</tr>
<tr class="odd">
<td><p>prinRolePfrinID</p></td>
<td><p>在 tblPrincipal.prinID 表中查找的外键。</p></td>
</tr>
<tr class="even">
<td><p>prinRoleTypeID</p></td>
<td><p>在 tblRoleType.rtypeID 表中查找的外键。</p></td>
</tr>
</tbody>
</table>

