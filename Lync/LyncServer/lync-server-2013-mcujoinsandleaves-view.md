---
title: McuJoinsAndLeaves 视图
TOCTitle: McuJoinsAndLeaves 视图
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49888458
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# McuJoinsAndLeaves 视图

 

_**上一次修改主题：** 2015-03-09_

McuJoinsAndLeaves 视图存储有关用户加入和离开某个会议服务器的信息。此视图中的每条记录都包含有关用户加入或离开与会议服务器的组合的呼叫详细信息。此视图是在 Microsoft Lync Server 2013 中引入的。


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
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>会议实例的时间。与 SessionIdSeq 结合使用来唯一地标识会议实例。有关详细信息，请参阅 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中的 Conferences 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>用于标识会议实例的 ID 号。与 SessionIdTime 结合使用来唯一地标识会议实例。有关详细信息，请参阅 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中的 Conferences 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuUri</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>用户连接到的会议服务器的 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>McuUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>用户连接到的会议服务器的 URI。有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>已捕获其会议服务器加入/离开信息的用户的 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>已捕获其会议服务器加入/离开信息的用户的 URI 类型。有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>已捕获其会议服务器加入/离开信息的用户的租户。有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的 Tenants 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>已捕获其会议服务器加入/离开信息的用户所使用的客户端版本。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>已捕获其会议服务器加入/离开信息的用户所使用的客户端。有关详细信息，请参阅 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar(64)</p></td>
<td><p>已捕获其会议服务器加入/离开信息的用户所使用的客户端类别的名称。</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p>唯一标识同时登录到多台设备的用户的用户/设备组合。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserFromPstn</strong></p></td>
<td><p>bit</p></td>
<td><p>表示用户是否为内部用户的位。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>会话请求的时间。与 SessionIdSeq 结合使用来唯一地标识会话。有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>用于标识会话的 ID 号。与 SessionIdTime 结合使用来唯一地标识会话。有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar(775)</p></td>
<td><p>会话的 SIP 对话 ID。格式为：dialog;from-tag;to-tag。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>用户加入会议服务器的时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>用户离开会议服务器的时间。</p></td>
</tr>
</tbody>
</table>

