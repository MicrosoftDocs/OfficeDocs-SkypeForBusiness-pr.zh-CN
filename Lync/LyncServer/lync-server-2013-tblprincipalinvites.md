---
title: Lync Server 2013：tblPrincipalInvites
TOCTitle: tblPrincipalInvites
ms:assetid: 548ec156-4d1a-469d-a804-62cff226e5c2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558650(v=OCS.15)
ms:contentKeyID: 49312871
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblPrincipalInvites

 

_**上一次修改主题：** 2015-03-09_

tblPrincipalInvites 包含打开自动邀请的所有节点的所有已设置用户的邀请。

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
<td><p>prinID</p></td>
<td><p>int，不为 null</p></td>
<td><p>主体 ID。</p></td>
</tr>
<tr class="even">
<td><p>invID</p></td>
<td><p>int，不为 null</p></td>
<td><p>从 tblLastInviteId 表中生成的唯一连续数字（每个主体 ID）。</p></td>
</tr>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>int，不为 null</p></td>
<td><p>节点 ID（仅聊天室）。</p></td>
</tr>
<tr class="even">
<td><p>createdOn</p></td>
<td><p>datetime，不为 null</p></td>
<td><p>创建的时间。</p></td>
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
<td><p>&lt;prinID, nodeID&gt;</p></td>
<td><p>主键。</p></td>
</tr>
<tr class="even">
<td><p>prinID</p></td>
<td><p>在 tblPrincipal.prinID 表中查找的外键。</p></td>
</tr>
<tr class="odd">
<td><p>nodeID</p></td>
<td><p>在 tblNode.nodeID 表中查找的外键。</p></td>
</tr>
</tbody>
</table>

