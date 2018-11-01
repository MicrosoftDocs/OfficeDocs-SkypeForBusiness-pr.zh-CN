---
title: Lync Server 2013：会议活动报告
TOCTitle: 会议活动报告
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558627(v=OCS.15)
ms:contentKeyID: 49312250
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的会议活动报告

 

_**上一次修改主题：** 2015-03-09_

会议活动报告使您可以轻松地回答如下问题：每天将召开多少会议？何时召开这些会议？诸如此类的信息不仅本身很有用，而且还可作为故障排除工具。例如，假设用户抱怨网络在中午时似乎特别慢。通过快速浏览会议活动报告，可以发现其中一个可能的原因：安排在上午 10:00 至下午 2:00 这一时段召开的会议远远多于其他时段的会议。

如果因网速慢而导致出现问题，您可以鼓励用户将他们的一些会议重新安排在一天中流量较少的时段。

## 访问会议活动报告

可从[Lync Server 2013 中的会议摘要报告](lync-server-2013-conference-summary-report.md)中通过单击下列指标之一来访问会议活动报告：

  - 会议总数

  - 参与者总数

## 充分利用会议活动报告

默认情况下，会议活动报告向您显示指定时段内的会议总数（例如，每天的会议总数或每小时的会议总数）。但是，您还可以选择显示该时段内与会者的总数或总参与分钟数。为此，请单击“显示/隐藏参数”按钮以显示筛选选项，然后从“报告依据”下拉列表中选择下列选项之一：

  - 参与者计数

  - 参与分钟数

  - 会议计数

## 筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于会议活动报告的筛选器。

### 会议活动报告筛选器

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
<td><p>时间间隔。选择下列任意选项：</p>
<ul>
<li><p>每小时（最多可显示 25 个小时）</p></li>
<li><p>每天（最多可显示 31 天）</p></li>
<li><p>每周（最多可显示 12 周）</p></li>
<li><p>每月（最多可显示 12 个月）</p></li>
</ul>
<p>如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 7/7/2012、结束日期为 2/28/2012、间隔为“每天”，则显示从 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 这些天的数据（即总共 31 天的数据）。</p></td>
</tr>
<tr class="even">
<td><p><strong>报告依据</strong></p></td>
<td><p>指示要在报告中使用的值。可选择下列选项之一：</p>
<ul>
<li><p>参与者计数</p></li>
<li><p>参与分钟数</p></li>
<li><p>会议计数</p></li>
</ul></td>
</tr>
</tbody>
</table>


## 按池分类的会议的指标

下表列出了每个池的会议活动报告中的信息。

### 按池分类的会议的指标

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
<td><p><strong>池</strong></p></td>
<td><p>否</p></td>
<td><p>会议中使用的注册器池或边缘服务器的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>日期/时间</strong></p></td>
<td><p>否</p></td>
<td><p>召开会议的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>总计</strong></p></td>
<td><p>否</p></td>
<td><p>参与者总数、总参与时间（以分钟计）或会议总数。</p></td>
</tr>
</tbody>
</table>


## 按服务器类型分类的会议的指标

下表列出了每种服务器类型的会议活动报告中的信息。

### 按服务器类型分类的会议的指标

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
<td><p><strong>会议服务器类型</strong></p></td>
<td><p>否</p></td>
<td><p>会议中使用的服务器的类型，通常为下列类型之一：</p>
<ul>
<li><p>Web 会议服务器</p></li>
<li><p>IM 会议服务器</p></li>
<li><p>电话会议服务器</p></li>
<li><p>AV 会议服务器</p></li>
<li><p>应用程序共享</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>日期/时间</strong></p></td>
<td><p>否</p></td>
<td><p>召开会议的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>总计</strong></p></td>
<td><p>否</p></td>
<td><p>参与者总数、总参与时间（以分钟计）或会议总数。</p></td>
</tr>
</tbody>
</table>

