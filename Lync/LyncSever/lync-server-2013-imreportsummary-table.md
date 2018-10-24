---
title: Lync Server 2013 中的 IMReportSummary 表
TOCTitle: Lync Server 2013 中的 IMReportSummary 表
ms:assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204753(v=OCS.15)
ms:contentKeyID: 49312309
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 IMReportSummary 表

 

_**上一次修改主题：** 2015-03-09_

IMReportSummaryTable 提供有关组织中进行的即时消息会话的总体报告。此表是在 Microsoft Lync Server 2013 中引入的。


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
<td><p><strong>StartTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主</p></td>
<td><p>即时消息会话开始的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>TimePeriod</strong></p></td>
<td><p>char(1)</p></td>
<td><p>主</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>PoolFQDN</strong></p></td>
<td><p>nvarchar (257)</p></td>
<td><p>主</p></td>
<td><p>承载会话的池的完全限定域名。</p></td>
</tr>
<tr class="even">
<td><p><strong>AuthType</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>呼叫的优先级（例如，紧急或非紧急）。优先级信息存储在 <a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 中的 CallPriorities 表</a>中。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SessionCount</strong></p></td>
<td><p>bigint</p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>MsgCount</strong></p></td>
<td><p>bigint</p></td>
<td><p></p></td>
<td><p>会话期间交换的即时消息总数。</p></td>
</tr>
</tbody>
</table>

