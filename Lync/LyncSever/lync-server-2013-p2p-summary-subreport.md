---
title: P2P 摘要子报表
TOCTitle: P2P 摘要子报表
ms:assetid: fc36185a-3cc5-4167-8c93-8a755fa75ac7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205416(v=OCS.15)
ms:contentKeyID: 49314849
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# P2P 摘要子报表

 

_**上一次修改主题：** 2015-03-09_

P2P 摘要子报表对失败点对点通信会话提供一个总体视图。

## 筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于 P2P 摘要子报表的筛选器。

### P2P 摘要子报表筛选器

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
<p>如果不输入开始时间，则报告不会自动在指定当天的 12:00 AM 开始。要按天查看数据，则只需输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="even">
<td><p><strong>结束日期</strong></p></td>
<td><p>时间范围的结束日期和时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您不输入结束时间，该报告将自动在指定当天的 12:00 AM 结束。要按天查看数据，则只需输入该日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>池</strong></p></td>
<td><p>注册器池 或 边缘服务器 的完全限定域名 (FQDN)。可以选择单个池，也可以单击“[所有]”查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</p></td>
</tr>
</tbody>
</table>


## 指标

下表列出了 P2P 摘要子报表中提供的信息。

### P2P 摘要子报告指标

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
<td><p>不支持</p></td>
<td><p>会话的总数，包括成功的会话、失败的会话（预期失败和意外失败）及未归类的会话。</p></td>
</tr>
<tr class="even">
<td><p><strong>故障率</strong></p></td>
<td><p>不支持</p></td>
<td><p>失败的点对点会话百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>按形式列出的会话</strong></p></td>
<td><p>不支持</p></td>
<td><p>按形式分组的会话总数（例如，即时消息）。</p></td>
</tr>
<tr class="even">
<td><p><strong>按形式列出的故障率</strong></p></td>
<td><p>不支持</p></td>
<td><p>按形式分组的失败会话总数（例如，即时消息）。</p></td>
</tr>
</tbody>
</table>

