---
title: ProgressReport 视图
TOCTitle: ProgressReport 视图
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49888569
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# ProgressReport 视图

 

_**上一次修改主题：** 2015-03-09_

ProgressReport 视图会存储有关已完成的会话的信息。只会针对 Lync Server 2013 判定可能对诊断有用的呼叫和会话编写进度报告。此视图是在 Microsoft Lync Server 2013 中引入的。

> [!NOTE]  
> ErrorTime、ErrorReportSeq 和 ProgressReportSeq 字段不一定表示错误，而是表示指示呼叫或消息状态的消息。




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
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>用于标识进度报告的 ID。用来区分相同错误报告的进度报告。</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>错误报告的诊断 ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Source</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>产生错误的服务器的名称（如果报告是从服务器组件发送的）。</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>产生错误的应用程序的名称（如果报告是从服务器组件发送的）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>uniqueidentifier</p></td>
<td><p>关联会议中所涉及不同组件的加入时间信息的唯一标识符。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p>特定组件加入会议所需的时间（以毫秒为单位）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar(max)</p></td>
<td><p>其他错误信息。</p></td>
</tr>
</tbody>
</table>

