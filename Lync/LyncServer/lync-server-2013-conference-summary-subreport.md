---
title: 会议摘要子报表
TOCTitle: 会议摘要子报表
ms:assetid: 2fc1d2bf-34f5-4093-a6e2-250ec1f1b004
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204779(v=OCS.15)
ms:contentKeyID: 49312399
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 会议摘要子报表

 

_**上一次修改主题：** 2015-03-09_

会议摘要子报告提供了失败的会议会话的总体概述。这些失败的会话按以下会话类型进一步细分：焦点会话和 MCU 会话。

## 筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于会议摘要子报告的筛选器。

### 会议摘要子报告筛选器

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
<td><p><strong>池</strong></p></td>
<td><p>注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“[所有]”查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</p></td>
</tr>
</tbody>
</table>


## 指标

下表列出了会议摘要子报告中提供的信息。

### 会议摘要子报告指标

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
<td><p>会议会话总数。单个会议可以具有多个会话；例如，会议可能同时包括焦点会话和 MCU 会话。</p></td>
</tr>
<tr class="odd">
<td><p><strong>总体会话故障率</strong></p></td>
<td><p>否</p></td>
<td><p>所有失败会议的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>焦点会话</strong></p></td>
<td><p>否</p></td>
<td><p>焦点会话总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>焦点故障率</strong></p></td>
<td><p>否</p></td>
<td><p>失败的焦点会话的百分比。</p></td>
</tr>
<tr class="even">
<td><p>MCU 会话</p></td>
<td><p>否</p></td>
<td><p>MCU 会话总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MCU 故障率</strong></p></td>
<td><p>否</p></td>
<td><p>失败的 MCU 会话的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>按形式列出的 MCU 会话</strong></p></td>
<td><p>否</p></td>
<td><p>按形式分组的 MCU 会话总数（例如，IM 会议）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>按形式列出的故障率</strong></p></td>
<td><p>否</p></td>
<td><p>按形式分组的失败的 MCU 会话的百分比（例如，IM 会议）。</p></td>
</tr>
</tbody>
</table>

