---
title: Lync Server 2013：PSTN 会议摘要报告
TOCTitle: PSTN 会议摘要报告
ms:assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615014(v=OCS.15)
ms:contentKeyID: 49313551
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 PSTN 会议摘要报告

 

_**上一次修改主题：** 2015-03-09_

在 Microsoft Lync Server 2013 中，PSTN 会议是指满足以下条件的任何会议：至少有一个参与者使用 PSTN（公用电话交换网）进行电话拨入来访问音频部分。（PSTN 电话是“固话”、手机或任何其他不使用 IP 语音的电话。）虽然这些会议在监控报告中称作“PSTN 会议”，但它们也许更常称作“电话拨入式会议”。

PSTN 会议摘要报告提供了有关您组织中召开的所有 PSTN 会议（即，所有至少有一个电话拨入式用户的会议）的信息。此报告包括有关 PSTN 会议总数和参与这些会议的人员总数的信息，并且可能包括有关电话拨入式用户的总数（PSTN 参与者指标总计）的信息（此信息最重要）。

## 访问 PSTN 会议摘要报告

只能从监控报告主页访问 PSTN 会议摘要报告。此报告未链接到任何其他报告。请注意，您无法检索 PSTN 会议的详细呼叫信息，部分原因在于单个终结点负责提交此信息。PSTN 电话无法跟踪或提交呼叫详细信息。

## 最充分地利用 PSTN 会议摘要报告

若要确定包括电话拨入式用户的所有会议的百分比，请将 PSTN 会议指标总计的值与在 [Lync Server 2013 中的会议摘要报告](lync-server-2013-conference-summary-report.md)中找到的会议指标总计进行比较。

如果您未看到所预计数目的 PSTN 会议，请记住，组织允许电话拨入式用户的会议的能力取决于已分配给用户的会议策略：如果仅允许几个用户主持 PSTN 会议，则可以明显看到 PSTN 会议的数目极少。您可以快速确定哪个会议策略（如果有）允许用户通过从 Lync Server 命令行管理程序中运行以下命令来计划 PSTN 会议：

    Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing

这将返回与以下类似的数据：

    Identity                                EnableDialInConferencing
    --------                                ------------------------
    Global                                                      True
    site:Redmond                                               False
    site:Dublin                                                False
    Tag:RedmondDialInUsers                                      True
    Tag:DublinDialInUsers                                       True

这将返回与以下类似的数据：

## 筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，PSTN 会议摘要报告允许您选择数据的分组方式。在此示例中，将按小时、日、周或月对会议进行分组。

下表列出了可用于 PSTN 会议摘要报告的筛选器。

### PSTN 会议摘要报告筛选器

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
<p>如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="even">
<td><p><strong>结束日期</strong></p></td>
<td><p>时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</p>
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
<p>如果开始日期和结束日期超出了所选间隔允许的最大时间长度，则仅显示最长数值（从开始日期开始）。例如，如果选择的开始日期为 8/7/2012、结束日期为 9/28/2012、间隔为“每天”，则显示从 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 这些天的数据（即总共 31 天的数据）。</p></td>
</tr>
</tbody>
</table>


## 指标

下表列出了 PSTN 会议摘要报告中的信息。

### PSTN 会议摘要报告指标

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
<td><p>指示所选的时间间隔。如果适用，可单击某一给定的时间间隔以查看该间隔的详细信息。例如，如果使用“每天”间隔并单击 7/7/2012，可查看当日用户注册活动的每小时细分信息。</p></td>
</tr>
<tr class="even">
<td><p><strong>PSTN 会议总数</strong></p></td>
<td><p>否</p></td>
<td><p>允许拨入访问的会议总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>参与者总数</strong></p></td>
<td><p>否</p></td>
<td><p>参与允许拨入访问的会议的人员总数。</p></td>
</tr>
<tr class="even">
<td><p><strong>A/V 会议总分钟数</strong></p></td>
<td><p>否</p></td>
<td><p>音频/视频会议时间的总长度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>A/V 会议参与者总分钟数</strong></p></td>
<td><p>否</p></td>
<td><p>音频/视频参与者时间的总长度。例如，如果一个参与者在 A/V 会议中花费了 5 分钟，另一个参与者在相同的会议中花费了 3 分钟，则 A/V 会议参与者总时间将为 8 分钟。</p></td>
</tr>
<tr class="even">
<td><p><strong>PSTN 参与者总数</strong></p></td>
<td><p>否</p></td>
<td><p>拨入允许拨入访问的会议的用户的总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PSTN 参与者总分钟数</strong></p></td>
<td><p>否</p></td>
<td><p>拨入用户花费的总会议时间长度。例如，如果一个拨入参与者在会议中花费了 5 分钟，另一个参与者在相同的会议中花费了 3 分钟，则 PSTN 参与者总时间将为 8 分钟。</p></td>
</tr>
<tr class="even">
<td><p><strong>唯一会议组织者</strong></p></td>
<td><p>否</p></td>
<td><p>至少组织过一次允许拨入访问的会议的用户总数。与仅组织过一次会议的用户一样，组织过多次会议的用户算作一个唯一组织者。</p></td>
</tr>
</tbody>
</table>

