---
title: Lync Server 2013：呼叫诊断摘要报告
TOCTitle: 呼叫诊断摘要报告
ms:assetid: 9091de56-13e6-440e-9353-f57c10c906fe
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615016(v=OCS.15)
ms:contentKeyID: 49313602
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的呼叫诊断摘要报告

 

_**上一次修改主题：** 2015-03-09_

呼叫诊断摘要报告提供失败的点对点会话和会议会话的整体情况。该报告显示了两种类型的会话的整体故障率，并按以下会话形式类型进一步为故障信息分类：

  - 即时消息

  - 应用程序共享

  - 文件传输

  - 音频

  - 视频

## 访问呼叫诊断摘要报告

呼叫诊断摘要报告是从监控报告主页访问的。在呼叫诊断摘要报告中，您可以通过单击报告的“点对点会话摘要”部分下的故障率指标访问[Lync Server 2013 中的点对点活动诊断报告](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)。您还可以通过单击以下任一会议指标来访问[Lync Server 2013 中的会议诊断报告](lync-server-2013-conference-diagnostic-report.md)：

  - 总体会话故障率

  - 焦点故障率

  - MCU 故障率

## 充分利用呼叫诊断摘要报告

呼叫诊断摘要报告包括用于比较 Microsoft Lync Server 2013 中使用的各种形式的失败率的图形。这些图形中的列实际上是热链接；例如，如果单击对等会话的即时消息列，则会向下钻取到 [Lync Server 2013 中的点对点活动诊断报告](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)的实例 - 提供有关呼叫诊断摘要报告中包含的所有即时消息会话的更多详细信息的报告。

## 筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，呼叫诊断摘要报告允许您依据会话中使用的注册器池或边缘服务器等条件进行筛选。您还可以选择数据的分组方式。在此示例中，将按小时、天、周或月对呼叫进行分组。

下表列出了可用于呼叫诊断摘要报告的筛选器。

### 呼叫诊断摘要报告筛选器

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
<p>如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 7/7/2012、结束日期为 2/28/2012、间隔为“每天”，则显示从 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 这些天的数据（即总共 31 天的数据）。</p></td>
</tr>
<tr class="even">
<td><p><strong>池</strong></p></td>
<td><p>注册器池或边缘服务器的完全限定的域名 (FQDN)。可以选择单个池，也可以单击“[所有]”查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</p></td>
</tr>
</tbody>
</table>


## 点对点会话的指标

下表列出了点对点会话（即，只涉及两个参与者的会话）的呼叫诊断摘要报告中提供的信息。

### 点对点会话的指标

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
<td><p><strong>会话总数</strong></p></td>
<td><p>否</p></td>
<td><p>发起的点对点会话总数。</p></td>
</tr>
<tr class="even">
<td><p><strong>故障率</strong></p></td>
<td><p>否</p></td>
<td><p>失败的点对点会话百分比。单击此项时，报告将显示点对点活动诊断报告，其中显示有关失败的点对点会话的详细信息。</p></td>
</tr>
</tbody>
</table>


## 会议会话的指标

下表列出了会议会话（即，涉及三个或更多参与者的会话）的呼叫诊断报告中提供的信息。

### 会议会话的指标

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
<td><p><strong>会议总数</strong></p></td>
<td><p>否</p></td>
<td><p>举行的会议总数。</p></td>
</tr>
<tr class="even">
<td><p><strong>会议会话总数</strong></p></td>
<td><p>否</p></td>
<td><p>发起的会议会话总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>总体会话故障率</strong></p></td>
<td><p>否</p></td>
<td><p>失败的会议会话百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>焦点会话</strong></p></td>
<td><p>否</p></td>
<td><p>失败的基于会议状态中心的会议会话总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>焦点故障率</strong></p></td>
<td><p>否</p></td>
<td><p>失败的基于会议状态中心的会议会话百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>MCU 会话</strong></p></td>
<td><p>否</p></td>
<td><p>失败的基于会议服务器（以前称为多点控制单元，简称 MCU）的会议总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MCU 故障率</strong></p></td>
<td><p>否</p></td>
<td><p>失败的基于会议服务器（以前称为多点控制单元，简称 MCU）的会议百分比。</p></td>
</tr>
</tbody>
</table>

