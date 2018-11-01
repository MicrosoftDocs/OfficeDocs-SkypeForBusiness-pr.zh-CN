---
title: Lync Server 2013：ErrorReport 表
TOCTitle: ErrorReport 表
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412826(v=OCS.15)
ms:contentKeyID: 49313915
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 ErrorReport 表

 

_**上一次修改主题：** 2015-06-22_

ErrorReport 表存储有关已发生的错误的信息。每条记录代表发生一次错误。错误由在前端服务器上运行的 CDR 代理捕获或发送自客户端。


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
<td><p><strong>ErrorTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主</p></td>
<td><p>错误发生的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识错误报告的 ID 号。与 <strong>ErrorTime</strong> 结合使用来唯一地标识错误报告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>错误类型的唯一 ID。有关详细信息，请参阅 <a href="lync-server-2013-errordef-table.md">Lync Server 2013 中的 ErrorDef 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>FromUserId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>发起导致出错的请求的用户。有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ToUserId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>导致出错的请求的目标用户。有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConferenceUriId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>与错误相关的会议 URI。有关详细信息，请参阅 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a>。通常，如果 ConferenceUriId 不为 null，则 FromUserId 或 ToUserId 将为 null。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionIdTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>外</p></td>
<td><p>与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionIdSeq</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>用于标识会话的 ID 号。与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会话。有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>发送错误报告的服务器（如果报告是从服务器组件发送的）。有关详细信息，请参阅 <a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 表</a>。</p>
<p>Microsoft Lync Server 2013 中已引入了此字段。</p></td>
</tr>
<tr class="even">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>发送错误报告的服务器（如果报告是从服务器组件发送的）。有关详细信息，请参阅 <a href="lync-server-2013-application-table.md">Lync Server 2013 中的 Application 表</a>。</p>
<p>Microsoft Lync Server 2013 中已引入了此字段。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>图像</p></td>
<td><p> </p></td>
<td><p>有关错误的详细信息。</p>
<p>可以使用以下语法将此数据转换为文本格式：</p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><strong>ClientVersionId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>发送错误报告的终结点的客户端版本。有关详细信息，请参阅 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsCapturedByServer</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>错误报告是由在前端服务器上运行的 CDR 代理捕获的，还是客户端发送的。</p></td>
</tr>
<tr class="even">
<td><p><strong>Flag</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>保留以供将来使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>关联会议中所涉及不同组件的加入时间信息的唯一标识符。</p>
<p>Microsoft Lync Server 2013 中已引入了此字段。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>特定组件加入会议所需的时间（以毫秒为单位）。</p>
<p>Microsoft Lync Server 2013 中已引入了此字段。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ServerId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>代表生成错误报告的服务器的完全限定域名。</p></td>
</tr>
<tr class="even">
<td><p><strong>PoolId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>代表生成错误报告的池的完全限定域名。</p></td>
</tr>
</tbody>
</table>

