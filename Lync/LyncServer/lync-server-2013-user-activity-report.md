---
title: Lync Server 2013：用户活动报告
description: Lync Server 2013：用户活动报告。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Activity Report
ms:assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558638(v=OCS.15)
ms:contentKeyID: 48183862
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0e959020e6ace6c72ecd570039d30a9ecc174c82
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569828"
---
# <a name="user-activity-report-in-lync-server-2013"></a>Lync Server 2013 中的用户活动报告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2015-02-27_

用户活动报告提供了由用户在给定时间段内执行的点对点会话和会议会话的详细列表。与很多监控报告不同，用户活动报告会将每个呼叫与单个用户绑定。例如，点对点会话指定发起呼叫（源用户）的人员以及被呼叫（目标用户）的人员的 SIP URI。如果展开会议的信息，则会看到所有会议参与者及其在该会议中担任的角色的列表。

用户活动报告有时候称为“技术支持”报告。这是因为该报告通常由技术支持人员用于检索特定用户的会话信息。您可以筛选来自或发往单个用户的呼叫，只需在“用户 URI”前缀框中键入该用户的 SIP URI 即可。

如果执行此操作，则用户活动报告将返回其 SIP URI 以指定字符串开头的任何用户的信息。 例如，如果在 "URI" 框中键入 **ken** ，则用户活动报告将找到 **ken**。Myer@litwareinc.com。 但是，它还会找到以下用户：

  - **ken**azi@litwareinc.com

  - **ken**burg@litwareinc.com

  - **Ken**。Sanchez@litwareinc.com

  - **Ken**nedy@litwareinc.com

若要确保仅返回 Ken Myer 的信息，请在 "搜索" 框中键入他的完整 URI (Ken.Myer@litwareinc.com) 或至少足够的 Ken URI 类型，以唯一地区分他与组织中的其他用户。 例如：

Ken.my

<div>

## <a name="to-access-the-user-activity-report"></a>访问用户活动报告

用户活动报告是从“监控报告”主页访问的。 您还可以通过单击 [Lync Server 2013 中的 "IP 电话清单报告](lync-server-2013-ip-phone-inventory-report.md)" 上的 "用户 URI" 指标来访问用户活动报告。 在用户活动报告中，单击“会议 URI”（针对会议）会将您转到会议详细信息报告。 同样，单击对等呼叫的详细信息指标将转到 [Lync Server 2013 中的对等会话详细信息报告](lync-server-2013-peer-to-peer-session-detail-report.md)。

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a>充分利用用户活动报告

尽管用户活动报告中有很多有用的信息，但这些信息有时候可能很难找到。 例如，在指定时间段内组织中发生的所有用户活动都包含在用户活动报告中;这意味着，在报告中，隐藏了在某些方面实际使用 Microsoft Lync Server 2013 的用户的相关信息。

<div>


> [!WARNING]  
> 从技术上讲，某些用户活动可能会执行 unrecorded：尽管 Lync Server 努力保留有关所有电话呼叫的信息，但在未将有关该调用的信息写入数据库的情况下，可能会进行呼叫。 Lync Server 旨在提供非常准确但不一定完全了解 Lync Server 2013 的使用方式。  (不能保证所有呼叫的100% 不会被记录，说明为什么不应将 Lync Server 监控用作帐单系统。 ) <BR>其次，“监控报告”报告最多只能显示 1,000 个记录。根据您具有的用户活动的数量以及您工作的时间段，这意味着您的查询可能无法返回数据库中实际存储的所有数据。



</div>

  - 哪些用户在此时间段内实际上使用了系统？

  - 我的哪些用户在此时间段内最活跃？

  - 发出电话呼叫最多的用户是否也是参与即时消息会话最多的用户？

如果您需要回答这样的问题，则可以将监控报告检索到的数据导出到 Excel 电子表格。 然后，使用该电子表格和/或逗号分隔值文件以用户活动报告的方式分析数据。 例如，假设您已将报告数据导出到 Excel，然后导出为逗号分隔值文件。 此时，您可以从导入数据。CSV 文件到 Windows PowerShell，方法是使用类似如下的命令：

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

导入数据后，您可以使用简单的 Windows PowerShell 命令来帮助回答您的问题。 例如，以下命令将返回至少在一个会话中充当“源用户”的唯一用户的列表：

    $x | Group-Object "From user" | Select Name | Sort-Object Name

换一种形式就是：

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

以下命令将根据唯一用户参与的会话的总数列出这些用户：

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

这将返回类似于下面的数据：

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

以下命令会将报告的会话限制为将音频作为一种形式包含的会话：

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

如果将鼠标悬停在报告上显示的任何诊断 ID 上，则会出现一个描述该 ID 的工具提示。

</div>

<div>

## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，用户活动报告允许您基于活动类型（即点对点会话还是会议会话）或用户的 SIP 地址（允许您查看一个用户的活动）筛选返回的数据。您还可以选择数据的分组方式。在此示例中，将按小时、日、周或月对使用情况进行分组。

下表列出了可用于用户活动报告的筛选器。

### <a name="user-activity-report-filters"></a>用户活动报告筛选器

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>From</strong></p></td>
<td><p>时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</p>
<p>7/17/12012 1:00 PM</p>
<p>如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</p>
<p>7/17/12012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/13/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</p>
<p>7/17/12012 1:00 PM</p>
<p>如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</p>
<p>7/17/12012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/13/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>活动类型</strong></p></td>
<td><p>活动的类型。选择下列选项之一：</p>
<ul>
<li><p>各种</p></li>
<li><p>对等</p></li>
<li><p>Conference</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>模态</strong></p></td>
<td><p>可供您使用的模态根据选择活动类型的不同而有所不同。 如果活动类型是对等的，则可以选择 IM;文件传输;应用程序共享;音量或视频作为模态。</p>
<p>如果活动类型为 "会议"，则可以选择 "IM 电话会议";Web 会议;应用程序共享;语音/视频会议;或电话会议。</p></td>
</tr>
<tr class="odd">
<td><p><strong>会话类别</strong></p></td>
<td><p>指示相应活动已成功还是失败。选择下列选项之一：</p>
<ul>
<li><p>各种</p></li>
<li><p>成功</p></li>
<li><p>预期失败</p></li>
<li><p>意外失败</p></li>
</ul>
<p>&quot;预期故障 &quot; 是预期发生的故障; 例如，如果用户已将其状态设置为 "请勿打扰"，则可能会对该用户的任何调用失败。 &quot;意外故障 &quot; 是指看起来好像是以其他正常运行的系统出现的故障。 例如，如果呼叫者处于呼叫等待状态，则不应该终止呼叫。 如果终止，则会被标记为意外失败。</p></td>
</tr>
<tr class="even">
<td><p><strong>用户 URI 前缀</strong></p></td>
<td><p>用户的 SIP 地址。要仅查看用户 Ken Myer 的记录，您需要输入 Ken Myer 的 SIP 地址。例如：</p>
<p>sip:kenmyer@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>点对点会话的指标

下表列出了点对点会话（即，只涉及两个参与者的会话）的用户活动报告中提供的信息。

### <a name="metrics-for-peer-to-peer-sessions"></a>点对点会话的指标

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>是否可按此项排序？</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>详细信息</strong></p></td>
<td><p>否</p></td>
<td><p>单击此项时，报告将显示所选会话的点对点会话详细信息报告。</p></td>
</tr>
<tr class="even">
<td><p><strong>来源用户</strong></p></td>
<td><p>是</p></td>
<td><p>发起点对点会话的用户的 SIP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>目标用户</strong></p></td>
<td><p>是</p></td>
<td><p>加入点对点会话的用户的 SIP 地址。</p></td>
</tr>
<tr class="even">
<td><p><strong>形式</strong></p></td>
<td><p>是</p></td>
<td><p>会话中使用的通信类型。例如，IM、音频或文件传输。</p></td>
</tr>
<tr class="odd">
<td><p><strong>邀请时间</strong></p></td>
<td><p>是</p></td>
<td><p>发送加入点对点会话的初始邀请的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>响应时间</strong></p></td>
<td><p>是</p></td>
<td><p>&quot;到 &quot; 用户接受会话邀请的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>结束时间</strong></p></td>
<td><p>是</p></td>
<td><p>点对点会话结束的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>诊断 ID</strong></p></td>
<td><p>是</p></td>
<td><p>附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。诊断标头是可选的（SIP 会话可以不包含这些标头），并且只对遇到此类问题的会话报告诊断 ID。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>会议会话的指标

下表列出了会议会话（即，涉及三个或更多参与者的会话）的用户活动报告中提供的信息。

### <a name="metrics-for-conferencing-sessions"></a>会议会话的指标

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>是否可按此项排序？</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>会议 URI</strong></p></td>
<td><p>是</p></td>
<td><p>唯一会议标识符。 单击此项时，报告将显示所选会话的会议详细信息报告。 展开此项时，报告将显示有关会议参与者的信息。 有关详细信息，请参阅 &quot; 本主题后面的 "会议参与者的指标" &quot; 一节。</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizer</strong></p></td>
<td><p>是</p></td>
<td><p>组织会议的用户的 SIP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>是</p></td>
<td><p>会议中使用的边缘服务器（如果有）的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>开始时间</strong></p></td>
<td><p>是</p></td>
<td><p>会议开始的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>结束时间</strong></p></td>
<td><p>是</p></td>
<td><p>会议结束的日期和时间。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a>会议参与者的指标

下表列出了会议的每个参与者的用户活动报告中提供的信息。

### <a name="metrics-for-conference-participants"></a>会议参与者的指标

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>是否可按此项排序？</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>角色</strong></p></td>
<td><p>否</p></td>
<td><p>用户的会议角色（例如，演示者）。</p></td>
</tr>
<tr class="even">
<td><p><strong>参与者</strong></p></td>
<td><p>否</p></td>
<td><p>用户的 SIP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>连接</strong></p></td>
<td><p>否</p></td>
<td><p>网络连接类型。 例如，用于 &quot; &quot; 内部连接的内部或 &quot; 来自 PSTN &quot; 的电话拨入用户。</p></td>
</tr>
<tr class="even">
<td><p><strong>加入时间</strong></p></td>
<td><p>否</p></td>
<td><p>用户加入会议的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>离开时间</strong></p></td>
<td><p>否</p></td>
<td><p>用户离开会议的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>诊断 ID</strong></p></td>
<td><p>否</p></td>
<td><p>附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。诊断标头是可选的（SIP 会话可以不包含这些标头），并且只对遇到此类问题的会话报告诊断 ID。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

