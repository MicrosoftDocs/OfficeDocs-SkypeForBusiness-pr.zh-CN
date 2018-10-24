---
title: ErrorReport 视图
TOCTitle: ErrorReport 视图
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49888609
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ErrorReport 视图

 

_**上一次修改主题：** 2015-03-09_

ErrorReport 视图存储有关已报告的错误的信息。每条记录代表发生一次错误。错误由在前端服务器上运行的 CDR 代理捕获或发送自客户端。此视图在 Microsoft Lync Server 2013 中引入。


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
<td><p><strong>ErrorTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>发生错误的时间。与 ErrorReportSeq 结合使用来唯一地标识错误。</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>用于标识错误的 ID 号。与 ErrorTime 结合使用来唯一地标识错误。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>错误报告的诊断 ID。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>导致出错的用户的 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FromUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>导致出错的用户的 URI 的类型。有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>导致出错的用户的租户。有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的 Tenants 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>成为错误报告目标的用户的 URI。</p></td>
</tr>
<tr class="even">
<td><p><strong>ToUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>成为错误报告目标的用户的 URI 类型。有关详细信息，请参阅 UriTypes 表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToTenant</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>成为错误报告目标的用户的租户。有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的 Tenants 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUri</strong></p></td>
<td><p>nvarchar(450)</p></td>
<td><p>成为错误报告目标的会议的 URI。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConferenceUriType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>成为错误报告目标的会议的 URI 类型。有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>导致发出错误报告的会话请求的时间。与 SessionIdSeq 结合使用来唯一地标识会话。有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>用于标识导致发出错误报告的会话请求的 ID 编号。与 SessionIdTime 结合使用来唯一地标识会话。有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>DialogId</strong></p></td>
<td><p>varstring(775)</p></td>
<td><p>导致出错的会话的 SIP 对话 ID。格式为：</p>
<p>dialog;from-tag;to-tag</p>
<p>可以使用以下语法将此数据转换为文本格式：</p>
<p>cast(cast(ExternalId as varbinary(max)) as varchar(max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientVersion</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>导致出错的用户所使用的客户端版本。</p></td>
</tr>
<tr class="even">
<td><p><strong>ClientType</strong></p></td>
<td><p>int</p></td>
<td><p>导致出错的用户所使用的客户端。有关详细信息，请参阅 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClientCategory</strong></p></td>
<td><p>nvarchar(64)</p></td>
<td><p>导致出错的用户所使用的客户端的类别名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>Source</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>导致出错的服务器的名称（如果报告发送自服务器组件）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Application</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>导致出错的应用程序的名称（如果报告发送自服务器组件）。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResponseCode</strong></p></td>
<td><p>int</p></td>
<td><p>包含错误报告的 SIP 消息对话的 SIP 响应代码。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RequestType</strong></p></td>
<td><p>varchar(max)</p></td>
<td><p>失败的请求的类型。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentType</strong></p></td>
<td><p>varchar(max)</p></td>
<td><p>失败的请求的内容类型。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>会话类型。有关详细信息，请参阅 <a href="lync-server-2013-calltype-table.md">Lync Server 2013 中的 CallType 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>关联会议中所涉及不同组件的加入时间信息的唯一标识符。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p>特定组件加入会议所需的时间（以毫秒为单位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>bit</p></td>
<td><p>指示错误报告是由在前端服务器上运行的 CDR 代理捕获的，还是客户端发送的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p>保留以供将来使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar(max)</p></td>
<td><p>有关错误的其他信息。</p></td>
</tr>
</tbody>
</table>

