---
title: Lync Server 2013：ConferenceMessageCount 表
TOCTitle: ConferenceMessageCount 表
ms:assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398590(v=OCS.15)
ms:contentKeyID: 49313310
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 ConferenceMessageCount 表

 

_**上一次修改主题：** 2015-03-09_

此表中的每条记录分别表示一个 IM 会议中的一个用户，并包括该用户发送的消息数。每个会议由此表中的多条记录表示；每个用户一条记录。


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
<td><p>主、外</p></td>
<td><p>会议实例的时间。与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会议实例。有关详细信息，请参阅 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中的 Conferences 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主、外</p></td>
<td><p>用于标识会议实例的 ID 号。与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会议实例。有关详细信息，请参阅 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中的 Conferences 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>从 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>引用的用于用于标识此用户的唯一编号。</p></td>
</tr>
<tr class="even">
<td><p><strong>MessageCount</strong></p></td>
<td><p>smallint</p></td>
<td><p> </p></td>
<td><p>此用户在此会议期间发送的消息数。</p></td>
</tr>
</tbody>
</table>

