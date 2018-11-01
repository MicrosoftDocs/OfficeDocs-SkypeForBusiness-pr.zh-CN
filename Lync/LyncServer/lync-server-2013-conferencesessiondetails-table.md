---
title: Lync Server 2013：ConferenceSessionDetails 表
TOCTitle: ConferenceSessionDetails 表
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412741(v=OCS.15)
ms:contentKeyID: 49313761
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 ConferenceSessionDetails 表

 

_**上一次修改主题：** 2015-03-09_

每个记录表示一个会议会话，它可以是具有会议状态中心的会话，也可以是具有特定会议服务器的会话。


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
<td><p>Datetime</p></td>
<td><p>主、外</p></td>
<td><p>会话请求的时间；与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会议会话。有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主、外</p></td>
<td><p>用于标识会话的 ID 号。与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会议会话。有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表</a>。*</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>与此会话相关的会议状态中心会议 URI。有关详细信息，请参阅 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a>。此 URI 是基于会议状态中心的会议 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConfInstance</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>区分各个定期会议实例的标识符。每个定期会议实例的 ConferenceURI 都相同，但具有不同的 ConfInstance 值。</p>
<p>Microsoft Lync Server 2013 中已引入了此字段。</p></td>
</tr>
<tr class="odd">
<td><p><strong>McuConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>与此会话相关的会议服务器会议 URI。有关详细信息，请参阅 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a>。此 URI 是基于会议服务器的会议 URI。对于会议状态中心会议会话，此列将为 null。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>会议会话中的一个用户的 ID。有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserEndpointId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p></p></td>
<td><p>用于标识终结点的实例的 GUID。例如，如果一个用户使用相同帐户登录到不同的计算机上，则每台计算机将具有不同的终结点 ID。</p></td>
</tr>
<tr class="even">
<td><p><strong>OnBehalfOfId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>指示呼叫者所代表的用户的 ID。有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReferredById</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>引用呼叫的用户的 ID。有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>会议用户使用的客户端版本。有关详细信息，请参阅 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConfClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>会议服务器使用的客户端版本。有关详细信息，请参阅 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>ReplaceDialogIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>外</p></td>
<td><p>用于标识由当前会话取代的对话的 ID 号。有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ReplaceDialogIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>用于标识会话的 ID 号。与 <strong>ReplacesDialogIdTime</strong> 结合使用来唯一地标识由此会话取代的会话。有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsStartedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>指示会话是否是由会议服务器启动的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsEndedByConfServer</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>指示会话是否是由会议服务器终止的。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsUserInternal</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>用户是否从内部登录。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>会话邀请的会话初始协议 (SIP) 响应代码。此字段通常用从会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</p></td>
</tr>
<tr class="even">
<td><p><strong>DiagnosticId</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>从 SIP 标头捕获的诊断 ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>用于此会话的前端服务器的 ID。有关详细信息，请参阅 <a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>在其中捕获会话的池的 ID。有关详细信息，请参阅 <a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 Pools 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediationServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫使用的中介服务器。有关详细信息，请参阅 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>GatewayId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫使用的网关。有关详细信息，请参阅 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的 Gateways 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EdgeServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫使用的边缘服务器。有关详细信息，请参阅 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentTypeId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>会话中使用的内容类型。有关详细信息，请参阅 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>InviteTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>第一个 INVITE 请求的时间。此字段通常用从会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>第一个 SIP 响应的时间。此字段通常用从会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionEndTime</strong></p></td>
<td><p>datetime</p></td>
<td><p></p></td>
<td><p>会话结束的时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>UriTypeId</strong></p></td>
<td><p>tinyint</p></td>
<td><p>外</p></td>
<td><p>包含 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 中的 MCU URI 类型值。此字段用于改进查询性能。</p>
<p>Microsoft Lync Server 2013 中已引入了此字段。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UserFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>指示用户属性的位集。列出了以下属性定义：</p>
<ul>
<li><p>与桌面电话集成 - 1</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>CallFlag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>指示呼叫属性的位集。列出了以下属性定义：</p>
<ul>
<li><p>重试会话 - 1</p></li>
</ul></td>
</tr>
</tbody>
</table>


\* 对于大多数会话，SessionIdSeq 值都为 1。如果多个会话完全同时启动，则一个会话的 SessionIdSeq 将为 1，另一个会话的 SessionIdSeq 将为 2，依此类推。

