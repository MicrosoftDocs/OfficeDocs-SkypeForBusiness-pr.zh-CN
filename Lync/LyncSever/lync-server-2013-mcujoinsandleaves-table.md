---
title: Lync Server 2013：McuJoinsAndLeaves 表
TOCTitle: McuJoinsAndLeaves 表
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398316(v=OCS.15)
ms:contentKeyID: 49312803
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 McuJoinsAndLeaves 表

 

_**上一次修改主题：** 2015-03-09_

此表中的每条记录都包含有关用户加入或离开与会议服务器的组合的呼叫详细信息。例如，如果用户加入包括 Web 会议和音频/视频元素的会议，则会为该用户的 Web 会议加入创建一条记录，并为该用户的音频/视频会议加入创建另一条记录。


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
<td><p>主、外</p></td>
<td><p>用于标识此用户的唯一编号。有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>如果用户同时在多个计算机或设备中登录，McuUserInstance 会唯一地标识用户/设备组合。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsFromPstn</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>用户是否从 PSTN 中加入。</p></td>
</tr>
<tr class="even">
<td><p><strong>McuId</strong></p></td>
<td><p>int</p></td>
<td><p>主、外</p></td>
<td><p>用于标识此会议服务器的唯一编号。有关详细信息，请参阅 <a href="lync-server-2013-mcus-table.md">Lync Server 2013 中的 Mcus 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>外</p></td>
<td><p>会话请求的时间。与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>用于标识会话的 ID 号。与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会话。有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>此用户加入此会议服务器的时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p> </p></td>
<td><p>此用户离开此会议服务器的时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVerId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>指定在会议中使用的客户端软件的版本号的标识符。有关详细信息，请参阅 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a>。</p>
<p>Microsoft Lync Server 2013 中已引入了此字段。</p></td>
</tr>
</tbody>
</table>

