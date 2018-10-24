---
title: FocusJoinsAndLeaves 视图
TOCTitle: FocusJoinsAndLeaves 视图
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49888333
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# FocusJoinsAndLeaves 视图

 

_**上一次修改主题：** 2015-03-09_

FocusJoinsAndLeaves 视图存储有关加入和离开某会议的信息。每个会议在此视图中由一条在每次用户加入和离开该会议时编写的记录表示。此视图是在 Microsoft Lync Server 2013 中引入的。


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
<td><p><strong>UserUri</strong></p></td>
<td><p>nvarchar (450)</p></td>
<td><p>已捕获其会议加入/离开信息的用户的 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserUriType</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>已捕获其会议加入/离开信息的用户的 URI 类型。有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserTenant</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>已捕获其会议加入/离开信息的用户的租户。有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的 Tenants 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>已捕获其会议加入/离开信息的用户的唯一标识符。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientVersion</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>由已捕获其会议加入/离开信息的用户使用的客户端版本。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientType</strong></p></td>
<td><p>int</p></td>
<td><p>由已捕获其会议加入/离开信息的用户使用的客户端。有关更多详细信息，请参阅 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserClientCategory</strong></p></td>
<td><p>nvarchar (64)</p></td>
<td><p>由已捕获其会议加入/离开信息的用户使用的客户端的类别名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>FocusUserInstance</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>IsuserInternal</strong></p></td>
<td><p>bit</p></td>
<td><p>表示用户是否为内部用户的位。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogSessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>会话请求的时间。与 SessionIdSeq 结合使用来唯一地标识会话。有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DialogSessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>如果用户同时在多台计算机或设备登录，则使用 UserInstance 来唯一地标识该用户/设备组合。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varchar(775)</p></td>
<td><p>会话的 SIP 对话 ID。格式为：dialog;from-tag;to-tag。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserJoinTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>用户加入会议的时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserLeaveTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>用户离开会议的时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserRole</strong></p></td>
<td><p>nvarchar (256)</p></td>
<td><p>用户在会议中的角色，如演示者或与会者。</p></td>
</tr>
</tbody>
</table>

