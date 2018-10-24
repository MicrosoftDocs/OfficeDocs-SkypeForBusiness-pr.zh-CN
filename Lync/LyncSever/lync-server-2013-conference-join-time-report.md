---
title: 会议加入时间报告
TOCTitle: 会议加入时间报告
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205344(v=OCS.15)
ms:contentKeyID: 49314565
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 会议加入时间报告

 

_**上一次修改主题：** 2015-03-09_

会议加入时间摘要可使您确定用户要花多长时间才能加入会议。该报告显示平均加入时间（以毫秒计），同时提供一个细目，让您知道有多少用户在 2 秒或更少时间内加入了会议，有多少用户要求在 2 秒和 5 秒间加入会议等。

## 访问会议加入时间报告

可从监控报告主页访问会议加入时间报告。

## 筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于会议加入时间报告的筛选器。

### 会议加入时间报告筛选器

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
<p>如果不输入开始时间，则报告不会自动在指定当天的 12:00 AM 开始。要按天查看数据，则只需输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="even">
<td><p><strong>结束日期</strong></p></td>
<td><p>时间范围的结束日期/时间。若要按小时数时查看数据，请输入结束日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您不输入结束时间，该报告将自动在指定当天的 12:00 AM 结束。要按天查看数据，则只需输入该日期：</p>
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
<tr class="even">
<td><p><strong>池</strong></p></td>
<td><p>注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“[所有]”查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>会议会话</strong></p></td>
<td><p>会话类型。允许的值包括：</p>
<ul>
<li><p>[所有]</p></li>
<li><p>焦点会话</p></li>
<li><p>应用程序共享</p></li>
<li><p>A/V 会议</p></li>
</ul>
<p>如果选择 [所有]，则总会议加入时间将显示在报告的顶部。请注意，这些总数仅用于通过使用 Microsoft Exchange 或 Microsoft Outlook 安排的会议。</p></td>
</tr>
</tbody>
</table>


## 指标

下表列出了会议加入时间报告中提供的信息。

### 会议加入时间报告标准

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
<td><p><strong>日期</strong></p>
<p>此指标的实际标题完全取决于所选的间隔。</p></td>
<td><p>不支持</p></td>
<td><p>会议发生的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>会话总数</strong></p></td>
<td><p>不支持</p></td>
<td><p>会话的总数，包括成功的会话、失败的会话（预期失败和意外失败）及未归类的会话。</p></td>
</tr>
<tr class="odd">
<td><p><strong>平均 (ms)</strong></p></td>
<td><p>不支持</p></td>
<td><p>参与者加入会议花费的平均时间量（以毫秒计）。</p></td>
</tr>
<tr class="even">
<td><p><strong>会话 &lt; 2 秒，量</strong></p></td>
<td><p>不支持</p></td>
<td><p>在不到 2 秒的时间内加入会议的参与者的人数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>会话 &lt; 2 秒，百分比</strong></p></td>
<td><p>不支持</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>会话 2-5 秒，量</strong></p></td>
<td><p>不支持</p></td>
<td><p>在 2 秒到 5 秒之间加入会议的参与者人数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>会话 2-5 秒，百分比</strong></p></td>
<td><p>不支持</p></td>
<td><p>在 2 秒到 5 秒之间加入到会议的总呼叫参与者的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>会话 5-10 秒，量</strong></p></td>
<td><p>不支持</p></td>
<td><p>在 5 秒到 10 秒之间加入到会议参与者的人数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>会话 5-10 秒，百分比</strong></p></td>
<td><p>不支持</p></td>
<td><p>在 5 秒到 10 秒间加入会议的总呼叫参与者的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>会话 &gt; 10 秒，量</strong></p></td>
<td><p>不支持</p></td>
<td><p>需要 10 秒之上加入会议的参与者人数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>会话 &gt; 10 秒，百分比</strong></p></td>
<td><p>不支持</p></td>
<td><p>需要 10 秒之上加入会议的总呼叫参与者百分比。</p></td>
</tr>
</tbody>
</table>

