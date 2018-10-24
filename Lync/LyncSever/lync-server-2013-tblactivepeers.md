---
title: Lync Server 2013：tblActivePeers
TOCTitle: tblActivePeers
ms:assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615030(v=OCS.15)
ms:contentKeyID: 49313996
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblActivePeers

 

_**上一次修改主题：** 2015-03-09_

tblActivePeers 包含聊天服务之间当前对等连接。

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
<td><p>aplServerID</p></td>
<td><p>int，不为 null</p></td>
<td><p>发布条目的服务器的 ID。</p></td>
</tr>
<tr class="even">
<td><p>aplPeerID</p></td>
<td><p>int，不为 null</p></td>
<td><p>发布服务器连接到的对等方的 ID。</p></td>
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
<td><p>&lt;aplServerID, aplPeerID&gt;</p></td>
<td><p>主键。</p></td>
</tr>
<tr class="even">
<td><p>aplServerID</p></td>
<td><p>其查找包含在 tblServerIdentity.serverID 表中的外键。</p></td>
</tr>
<tr class="odd">
<td><p>aplPeerID</p></td>
<td><p>其查找包含在 tblServerIdentity.serverID 表中的外键。</p></td>
</tr>
</tbody>
</table>

