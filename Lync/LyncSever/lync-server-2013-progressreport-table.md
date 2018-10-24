---
title: Lync Server 2013：ProgressReport 表
TOCTitle: ProgressReport 表
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425864(v=OCS.15)
ms:contentKeyID: 49312539
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 ProgressReport 表

 

_**上一次修改主题：** 2015-03-09_

进度报告基于呼叫或会话结束后客户端上载到数据库的数据。仅对 Lync Server 2013 确定可能对诊断有帮助的呼叫和会话编写进度报告。

ErrorTime、ErrorReportSeq 和 ProgressReportSeq 字段不一定表示错误，而是表示指示呼叫或消息状态的消息。


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
<td><p>主、外</p></td>
<td><p>包含此进度报告的进度错误报告的日期和时间。有关详细信息，请参阅 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>主、外</p></td>
<td><p>与 ErrorTime 和 ProgressReportSeq 结合使用唯一地标识进度报告的 ID 号。有关详细信息，请参阅 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主、外</p></td>
<td><p>标识错误报告的 ID 号。ErrorReporSeq 与 ErrorTime 结合使用来唯一地标识错误报告。有关详细信息，请参阅 <a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表</a></p>
<p>Microsoft Lync Server 2013 中已引入了此字段。</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>标识进度报告的 ID 号。与 ErrorTime 和 ErrorReportSeq 结合使用可唯一地标识进度报告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>进度报告的诊断 ID。</p>
<p>Microsoft Lync Server 2013 中已引入了此字段。</p></td>
</tr>
<tr class="even">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>发送错误报告的服务器（如果报告是从服务器组件中发送的）。有关详细信息，请参阅 <a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 表</a>。此字段是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>报告涉及的 Lync Server 进程。有关详细信息，请参阅 Application 表。</p></td>
</tr>
<tr class="even">
<td><p><strong>Detail</strong></p></td>
<td><p>图像</p></td>
<td><p></p></td>
<td><p>为节省空间而以二进制格式存储的进度报告详细信息。使用以下语法可将此数据转换为文本格式：</p>
<p>cast(cast(Detail as varbinary(max)) as varchar(max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueIdentifier</p></td>
<td><p></p></td>
<td><p>与会议中所涉及不同组件的加入时间信息关联的唯一标识符。</p>
<p>Microsoft Lync Server 2013 中已引入了此字段。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>特定组件加入会议的时间（以毫秒计）。</p>
<p>Microsoft Lync Server 2013 中已引入了此字段。</p></td>
</tr>
</tbody>
</table>

