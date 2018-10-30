---
title: Lync Server 2013：点对点 IM 报告
TOCTitle: 点对点 IM 报告
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558620(v=OCS.15)
ms:contentKeyID: 49312152
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的点对点 IM 报告

 

_**上一次修改主题：** 2015-03-09_

对等 IM 报告提供了有关按池和身份验证类型分类的对等即时消息 (IM) 会话的趋势信息。该报告可以显示在指定时间段内（例如，每天或每小时）进行的会话总数或显示在该时间段内发送的即时消息总数。

## 访问对等 IM 报告

只能通过打开[Lync Server 2013 中的点对点活动摘要报告](lync-server-2013-peer-to-peer-activity-summary-report.md)、然后单击以下指标之一来访问对等 IM 报告：

  - 对等 IM 会话总数

  - 对等 IM 消息总数

## 充分利用对等 IM 报告

默认情况下，对等 IM 报告显示每小时（或每天，具体取决于设置）的消息计数。但是，还可以选择按每小时会话数来查看日期。为此，请单击“报告”窗口右上角的“隐藏/显示参数”，然后从“报告依据”列表中单击“会话计数”。

## 筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于对等 IM 报告的筛选器。

### 对等 IM 报告筛选器

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
<td><p>时间范围的开始日期和时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="even">
<td><p><strong>结束日期</strong></p></td>
<td><p>时间范围的结束日期和时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</p>
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
<p>如果开始日期和结束日期超出了所选间隔允许的最大值数，则仅显示最大值数（从开始日期开始）。例如，如果选择“每天”间隔并且开始日期为 7/7/2012、结束日期为 2/28/2012，则显示从 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 这些天的数据（即总共 31 天的数据）。</p></td>
</tr>
<tr class="even">
<td><p><strong>报告依据</strong></p></td>
<td><p>指示要在报告中使用的值。选择下列选项之一：</p>
<ul>
<li><p>会话计数</p></li>
<li><p>消息计数</p></li>
</ul></td>
</tr>
</tbody>
</table>


## 按池列出的点对点 IM 会话的指标

下表列出了点对点 IM 报告中提供的信息。

### 按池列出的点对点 IM 会话的指标

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
<td><p>注册器池或边缘服务器的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>日期/时间</strong></p></td>
<td><p>否</p></td>
<td><p>会话发生的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>总计</strong></p></td>
<td><p>否</p></td>
<td><p>会话总数或消息总数。</p></td>
</tr>
</tbody>
</table>


## 按身份验证类型列出的对等 IM 会话的指标

下表列出了点对点会话中的参与者所用各个身份验证类型的点对点 IM 报告中提供的信息。

### 按身份验证类型列出的对等 IM 会话的指标

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
<td><p><strong>身份验证类型</strong></p></td>
<td><p>否</p></td>
<td><p>会话参与者使用的身份验证的类型。通常可指定下列值之一：</p>
<ul>
<li><p>企业</p></li>
<li><p>联盟</p></li>
<li><p>PIC</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>日期/时间</strong></p></td>
<td><p>否</p></td>
<td><p>会话发生的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>总计</strong></p></td>
<td><p>否</p></td>
<td><p>会话总数或消息总数。</p></td>
</tr>
</tbody>
</table>

