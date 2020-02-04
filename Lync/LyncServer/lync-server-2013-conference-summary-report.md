---
title: Lync Server 2013：会议摘要报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Summary Report
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558656(v=OCS.15)
ms:contentKeyID: 48184299
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68858d56c47953a99928a59e5f83485ba9d305cb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-summary-report-in-lync-server-2013"></a>Lync Server 2013 中的 "会议摘要" 报表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-09-03_

会议摘要报告提供了联机会议会话的整体视图。 会议通常涉及超过2个用户，并且需要使用 Microsoft Lync Server 2013 会议服务。 通过比较，对等会话通常只涉及2个用户，不需要使用 Lync 服务器的会议服务。 对等活动报告在[Lync Server 2013 中的对等活动摘要报表](lync-server-2013-peer-to-peer-activity-summary-report.md)上。

"会议摘要" 报表不仅告诉你在给定时间段内（每小时、每天、每周、每月）举行的会议数，还会告诉你参与这些会议的人员总数以及唯一会议的总数组织.

“唯一”组织者是计划了至少一场会议的任何人。 例如，如果 Pilar Ackerman 计划了一场会议，则她将算为一个唯一组织者。 如果 Ken Myer 计划了 148 场会议，则他也将算为一个唯一组织者。 例如，下表显示计划的8个会议，但仅有三个唯一的组织者（Ken Myer、Pilar Ackerman 和 David Ahs）。


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>会议组织者</th>
<th>会议日期</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 1:00 PM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 2:00 PM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
</tbody>
</table>


会议摘要报告还指示了包含音频和/或视频的会议数量。

<div>

## <a name="accessing-the-conference-summary-report"></a>访问会议摘要报告

会议摘要报告是通过“监控报告”主页进行访问的。您可通过单击下列任一指标向下钻取至会议活动报告：

  - 会议总数

  - 参与者总数

</div>

<div>

## <a name="making-the-best-use-of-the-conference-summary-report"></a>充分利用会议摘要报告

会议摘要报告上使用的大部分指标的合计值都可在此报告的底部找到；向下滚动可看到指定时间段内举行的会议总数以及参与这些会议的总人数等值。 此报告底部未进行合计的一个指标是唯一会议组织者的总数。 为什么不进行合计？ 以下是一个理由。 假如您正查看一个月的数据。 第 1 天，您有 34 个唯一会议组织者；第 2 天，您有 27 个唯一会议组织者。 这是否意味着您在这两天有 61 个唯一会议组织者？ 不一定。 毕竟第 2 天组织了会议的所有 27 个人可能就在第 1 天组织了会议的 34 个人中。 例如，在此简单报表中，注意 Ken Myer 和 Pilar Ackerman 在7/7/2012 和7/2/2012 上安排的会议：


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>会议组织者</th>
<th>会议日期</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>David Ahs</p></td>
<td><p>7/7/2012 10:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 11:00 AM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/7/2012 1:00 PM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/7/2012 2:00 PM</p></td>
</tr>
<tr class="odd">
<td><p>Ken Myer</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
<tr class="even">
<td><p>Pilar Ackerman</p></td>
<td><p>7/2/2012 10:00 AM</p></td>
</tr>
</tbody>
</table>


若要更好地了解组织了会议的唯一用户的总数，请更改您的时间间隔；例如，按月而不是按天查看数据。

</div>

<div>

## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，会议摘要报告允许您选择数据的分组方式。在此示例中，将按小时、日、周或月对会议进行分组。

下表列出了可用于会议摘要报告的筛选器。

### <a name="conference-summary-report-filters"></a>会议摘要报告筛选器

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
<td><p><strong>从</strong></p></td>
<td><p>时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="even">
<td><p><strong>到</strong></p></td>
<td><p>时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>间隔</strong></p></td>
<td><p>时间间隔。选择下列选项之一：</p>
<ul>
<li><p>每小时（最多可显示 25 个小时）</p></li>
<li><p>每天（最多可显示 31 天）</p></li>
<li><p>每周（最多可显示 12 周）</p></li>
<li><p>每月（最多可显示 12 个月）</p></li>
</ul>
<p>如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。 例如，如果选择 "开始日期 7/7/2012" 和 "结束日期 2/28/2012" 的 "每日间隔"，则会显示 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 的数据（即，总共31天的数据）。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指标

下表列出了由会议摘要报告提供的信息。

### <a name="conference-summary-report-metrics"></a>会议摘要报告指标

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
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>每小时</strong></p>
<p><strong>每天</strong></p>
<p><strong>每周</strong></p>
<p><strong>每月</strong></p></td>
<td><p>否</p></td>
<td><p>指示在筛选器工具栏上选择的时间间隔。 如果适用，可单击某一给定的时间间隔以查看该间隔的详细信息。 例如，如果你使用的是每日间隔，并且单击 "7/7/2012"，你将看到该日期的用户注册活动的每小时细目。</p></td>
</tr>
<tr class="even">
<td><p><strong>会议总数</strong></p></td>
<td><p>否</p></td>
<td><p>举行的会议总数（不考虑会议类型）。单击此项时，报告将显示所选时间段的会议活动报告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>参与者总数</strong></p></td>
<td><p>否</p></td>
<td><p>参与会议的总人数。单击此项时，报告将显示所选时间段的会议活动报告。</p></td>
</tr>
<tr class="even">
<td><p><strong>每个会议的平均参与者数</strong></p></td>
<td><p>否</p></td>
<td><p>参与给定会议的平均人数。计算方法是参与者总数除以会议总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>A/V 会议总数</strong></p></td>
<td><p>否</p></td>
<td><p>使用了音频或视频的会议总数。</p></td>
</tr>
<tr class="even">
<td><p><strong>A/V 会议总分钟数</strong></p></td>
<td><p>否</p></td>
<td><p>音频/视频会议的总分钟数。</p>
<p>Total A/V 会议分钟跃点数汇总了所有音频/视频会议类型，包括： A/V 会议;IM 会议;应用程序共享会议;数据会议;和 PSTN 会议。</p></td>
</tr>
<tr class="odd">
<td><p><strong>A/V 会议参与者总分钟数</strong></p></td>
<td><p>否</p></td>
<td><p>音频/视频会议的参与者总分钟数。例如，假定一个用户在音频/视频会议中花费了 5 分钟时间，另一个用户在同一会议中花费了 3 分钟时间，则参与者总分钟数为 8：5 分钟加上 3 分钟。</p></td>
</tr>
<tr class="even">
<td><p><strong>A/V 会议平均分钟数</strong></p></td>
<td><p>否</p></td>
<td><p>每个音频/视频会议的平均分钟数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>唯一会议组织者总数</strong></p></td>
<td><p>否</p></td>
<td><p>至少组织过一次会议的用户总数。与仅组织过一次会议的用户一样，组织过多次会议的用户算作一个唯一组织者。</p></td>
</tr>
<tr class="even">
<td><p><strong>会议消息总数</strong></p></td>
<td><p>否</p></td>
<td><p>会议期间发送的即时消息总数。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

