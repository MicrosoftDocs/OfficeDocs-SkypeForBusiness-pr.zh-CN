---
title: Lync Server 2013：会议摘要报告
TOCTitle: 会议摘要报告
ms:assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558656(v=OCS.15)
ms:contentKeyID: 49313046
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的会议摘要报告

 

_**上一次修改主题：** 2015-03-09_

会议摘要报告提供了联机会议会话的整体视图。会议一般涉及两个以上的用户并且需要使用 Microsoft Lync Server 2013 会议服务。相比之下，对等会话一般仅涉及 2 个用户并且不需要使用 Lync Server 的会议服务。点对点活动将在 [Lync Server 2013 中的点对点活动摘要报告](lync-server-2013-peer-to-peer-activity-summary-report.md)上报告。

会议摘要报告不仅告知您给定时间段（每小时、每日、每周、每月）举行的会议数量，还告知您参与这些会议的总人数，以及唯一会议组织者的总数量。

“唯一”组织者是计划了至少一场会议的任何人。例如，如果 Pilar Ackerman 计划了一场会议，则她将算为一个唯一组织者。如果 Ken Myer 计划了 148 场会议，则他也将算为一个唯一组织者。例如，下表显示了计划的 8 场会议，但仅 3 个唯一组织者（Ken Myer、Pilar Ackerman 和 David Ahs）。


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

## 访问会议摘要报告

会议摘要报告是通过“监控报告”主页进行访问的。您可通过单击下列任一指标向下钻取至会议活动报告：

  - 会议总数

  - 参与者总数

## 充分利用会议摘要报告

会议摘要报告上使用的大部分指标的合计值都可在此报告的底部找到；向下滚动可看到指定时间段内举行的会议总数以及参与这些会议的总人数等值。此报告底部未进行合计的一个指标是唯一会议组织者的总数。为什么不进行合计？以下是一个理由。假如您正查看一个月的数据。第 1 天，您有 34 个唯一会议组织者；第 2 天，您有 27 个唯一会议组织者。这是否意味着您在这两天有 61 个唯一会议组织者？不一定。毕竟第 2 天组织了会议的所有 27 个人可能就在第 1 天组织了会议的 34 个人中。例如，在以下简单的报告中，请注意，Ken Myer 和 Pilar Ackerman 在 7/7/2012 和 7/2/2012 这两天均组织了会议：


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

## 筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，会议摘要报告允许您选择数据的分组方式。在此示例中，将按小时、日、周或月对会议进行分组。

下表列出了可用于会议摘要报告的筛选器。

### 会议摘要报告筛选器

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
<td><p><strong>开始日期</strong></p></td>
<td><p>时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 AM 作为开始时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="even">
<td><p><strong>结束日期</strong></p></td>
<td><p>时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 AM 作为结束时间。若要按日查看数据，请只输入日期：</p>
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
<p>如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 7/7/2012、结束日期为 2/28/2012、间隔为“每天”，则显示从 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 这些天的数据（即总共 31 天的数据）。</p></td>
</tr>
</tbody>
</table>


## 指标

下表列出了由会议摘要报告提供的信息。

### 会议摘要报告指标

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
<td><p><strong>每小时</strong></p>
<p><strong>每天</strong></p>
<p><strong>每周</strong></p>
<p><strong>每月</strong></p></td>
<td><p>否</p></td>
<td><p>指示在筛选器工具栏上选择的时间间隔。如果适用，可单击某一给定的时间间隔以查看该间隔的详细信息。例如，如果使用“每天”间隔并单击 7/7/2012，可查看当日用户注册活动的每小时细分信息。</p></td>
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
<p>A/V 会议总分钟数指标汇总所有音频/视频会议类型，包括：A/V 会议；IM 会议；应用共享会议；数据会议；以及 PSTN 会议。</p></td>
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

