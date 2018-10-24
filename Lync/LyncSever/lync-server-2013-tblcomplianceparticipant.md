---
title: Lync Server 2013：tblComplianceParticipant
TOCTitle: tblComplianceParticipant
ms:assetid: 5d7e0dea-74f7-46d1-badf-b94abc8f066d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558655(v=OCS.15)
ms:contentKeyID: 49312984
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 tblComplianceParticipant

 

_**上一次修改主题：** 2015-03-09_

tblComplianceParticipant 包含每个通道和每台服务器的当前参与者。

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
<td><p>channelUri</p></td>
<td><p>nvarchar (255)，不为 null</p></td>
<td><p>通道统一资源标识符 (URI)。</p></td>
</tr>
<tr class="even">
<td><p>userId</p></td>
<td><p>int，不为 null</p></td>
<td><p>参与者的主体 ID（与 tblPrincipal.prinID 表对应）。</p></td>
</tr>
<tr class="odd">
<td><p>joinedAt</p></td>
<td><p>bigint，不为 null</p></td>
<td><p>加入事件的时间戳。</p></td>
</tr>
<tr class="even">
<td><p>partedAt</p></td>
<td><p>bigint</p></td>
<td><p>如果仍加入参与者，则为 null。如果不为 null，则为通道离开事件的时间戳。</p>
<p>当所有转换器处理该事件时，将最终删除这些项。</p></td>
</tr>
<tr class="odd">
<td><p>UserUri</p></td>
<td><p>nvarchar (255)，不为 null</p></td>
<td><p>用户 URI。</p></td>
</tr>
<tr class="even">
<td><p>serverID</p></td>
<td><p>int</p></td>
<td><p>服务器标识（如 tblServerIdentity.serverID 表中所示）。</p></td>
</tr>
<tr class="odd">
<td><p>sessionId</p></td>
<td><p>bigint</p></td>
<td><p>服务器会话。它是每次聊天服务启动时生成的随机数字。它用于区分会话以便标识孤立参与者。</p></td>
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
<td><p>&lt;channelUri, userId, joinedAt&gt;</p></td>
<td><p>主键。</p></td>
</tr>
</tbody>
</table>

