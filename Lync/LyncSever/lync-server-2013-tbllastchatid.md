---
title: Lync Server 2013：tblLastChatId
TOCTitle: tblLastChatId
ms:assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558616(v=OCS.15)
ms:contentKeyID: 49312135
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblLastChatId

 

_**上一次修改主题：** 2015-03-09_

LastChatId 包含上次为每个用户生成的并且在 tblChat 表中使用的聊天 ID。

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
<td><p>nodeID</p></td>
<td><p>int，不为 null</p></td>
<td><p>节点 ID（仅限聊天室类型）。</p></td>
</tr>
<tr class="even">
<td><p>lastChatID</p></td>
<td><p>bigint，不为 null</p></td>
<td><p>上次使用的聊天 ID。</p></td>
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
<td><p>&lt;nodeID、lastChatID&gt;</p></td>
<td><p>主键（只有 nodeID 足以进行处理）。</p></td>
</tr>
<tr class="even">
<td><p>nodeID</p></td>
<td><p>在 tblNode.nodeID 表中查找的外键。</p></td>
</tr>
</tbody>
</table>


## 另请参阅

#### 概念

[Lync Server 2013 中的 tblChat](lync-server-2013-tblchat.md)

