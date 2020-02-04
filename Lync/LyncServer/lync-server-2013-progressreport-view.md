---
title: Lync Server 2013： ProgressReport 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fa8d73981490503b26b77b79be6f42aab77703e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a>Lync Server 2013 中的 ProgressReport 视图

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-01_

ProgressReport 视图存储有关已完成会话的信息。 将仅写入 Lync Server 2013 确定可能对诊断目的有用的通话和会话的进度报告。 此视图已在 Microsoft Lync Server 2013 中引入。

<div>


> [!NOTE]  
> "ErrorTime"、"ErrorReportSeq" 和 "ProgressReportSeq" 字段不一定是指错误，而是指示调用状态或消息的消息。



</div>


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
<td><p>出现错误的时间。 与 ErrorReportSeq 结合使用以唯一标识错误。</p></td>
</tr>
<tr class="even">
<td><p><strong>ErrorReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>标识错误的 ID 号。 与 ErrorTime 结合使用以唯一标识错误。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ProgressReportSeq</strong></p></td>
<td><p>int</p></td>
<td><p>标识进度报表的 ID。 用于区分同一错误报告的进度报告。</p></td>
</tr>
<tr class="even">
<td><p><strong>MsDiagId</strong></p></td>
<td><p>int</p></td>
<td><p>错误报告的诊断 ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>来源</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>产生错误的服务器的名称（如果报表是从服务器组件发送的）。</p></td>
</tr>
<tr class="even">
<td><p><strong>Application</strong></p></td>
<td><p>nvarchar(256)</p></td>
<td><p>发出错误的应用程序的名称（如果报表是从服务器组件发送的）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>TelemetryId</strong></p></td>
<td><p>标识符</p></td>
<td><p>关联会议中涉及的不同组件的加入时间信息的唯一标识符。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSetupTime</strong></p></td>
<td><p>int</p></td>
<td><p>特定组件加入会议所需的时间（以毫秒为单位）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagHeader</strong></p></td>
<td><p>varchar （max）</p></td>
<td><p>其他错误信息。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

