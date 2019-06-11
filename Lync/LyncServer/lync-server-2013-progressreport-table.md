---
title: Lync Server 2013：ProgressReport 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa8ca0341cd5b85418ef5f71234870ae4171af27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a>Lync Server 2013 中的 ProgressReport 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-28_

进度报告基于客户端在通话或会话完成后上载到数据库的数据。 将仅写入 Lync Server 2013 确定可能对诊断目的有用的通话和会话的进度报告。

"ErrorTime"、"ErrorReportSeq" 和 "ProgressReportSeq" 字段不一定是指错误, 而是指示调用状态或消息的消息。


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
<td><p>主、外部</p></td>
<td><p>包含此进度报表的 "进度错误" 报表的日期和时间。 有关详细信息, 请参阅<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorId</strong></p></td>
<td><p>int</p></td>
<td><p>主、外部</p></td>
<td><p>与 ErrorTime 和 ProgressReportSeq 结合使用的 ID 号, 用于唯一标识进度报告。 有关详细信息, 请参阅<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主、外部</p></td>
<td><p>标识错误报告的 ID 号。 ErrorReporSeq 与 ErrorTime 结合使用, 以唯一标识错误报告。 有关详细信息, 请参阅<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表</a>。</p>
<p>此字段是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>标识进度报表的 ID 号。 与 ErrorTime 和 ErrorReportSeq 结合使用, 以唯一标识进度报表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>进度报表的诊断 ID。</p>
<p>此字段是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>SourceId</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>发送错误报告的服务器 (如果报表是从服务器组件发送的)。 有关详细信息, 请参阅<a href="lync-server-2013-servers-table.md">Lync Server 2013 中</a>的 "服务器" 表。此字段是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationId</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>报表所针对的 Lync Server 进程。 有关详细信息, 请参阅应用程序表。</p></td>
</tr>
<tr class="even">
<td><p><strong>详情</strong></p></td>
<td><p>图像</p></td>
<td></td>
<td><p>进度报告详细信息, 以二进制格式存储以节省空间。此数据可以使用以下语法转换为文本格式:</p>
<p>转换 (cast (作为 varbinary (max) 的详细信息) 作为 varchar (max))</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>标识符</p></td>
<td></td>
<td><p>关联会议中涉及的不同组件的联接时间信息的唯一标识符。</p>
<p>此字段是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>特定组件加入会议的时间 (以毫秒为单位)。</p>
<p>此字段是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

