---
title: Lync Server 2013：主要故障报告
TOCTitle: 主要故障报告
ms:assetid: 438942e2-580a-4b67-9d42-f116111fb26a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558640(v=OCS.15)
ms:contentKeyID: 49312681
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的主要故障报告

 

_**上一次修改主题：** 2015-03-09_

主要故障报告说明了最常报告的故障及其在一段时间内的趋势。故障基于以下两项指标的组合：

  - **诊断 ID** 。附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式）。诊断 ID 提供的信息在解决与呼叫相关的问题时很有用。

  - **响应代码** 。响应代码在 SIP 通信会话中用来响应 SIP 请求。例如，假定 Ken 将 INVITE 请求发送给 Pilar Ackerman（即，假定 Ken Myer 呼叫 Pilar Ackerman）。如果 Pilar 应答，则她的电话将发送响应代码 200（确定），以便让 Ken 的电话获知 Pilar 已应答。主要故障报告仅包括为响应呼叫故障而发送的响应代码； Lync Server 不会跟踪呼叫过程中发出的所有响应代码。

不仅将报告与出现故障的会话的总数相关的信息，而且还将报告与受故障影响的用户总数相关的信息。

## 访问主要故障报告

可从监控报告主页访问主要故障报告。通过单击报告的会话指标可访问 [Lync Server 2013 中的故障分布报告](lync-server-2013-failure-distribution-report.md)。

## 最充分地利用主要故障报告

主要故障报告有一个与众不同的方面：它允许您一次性对最多 5 个诊断 ID 进行筛选。（通常，您一次只能筛选一项 - 例如，一个用户 SIP 地址。）若要对多个诊断 ID 进行筛选，只需在诊断 ID 框中输入每个 ID，并使用逗号分隔这些 ID。（如果需要，您可以在每个逗号后面保留一个空格。）例如：

1011, 2412, 1033, 52116, 1008

这样一来，将仅显示报告了这五个诊断 ID 中的至少一个 ID 的失败呼叫。

如果您将鼠标指针悬停在响应代码的上方，则将显示一个工具提示，告知您有问题的响应代码的含义。例如，如果您将鼠标指针悬停在响应代码 486 的上方，则将显示以下消息：

此处忙碌。

## 筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，主要故障报告允许您基于活动类型（点对点会话还是会议会话）或失败会话附带的 SIP 响应代码等条件筛选返回的数据。您还可以选择数据的分组方式。在此示例中，将按小时、日、周或月对使用情况进行分组。

下表列出了可用于主要故障报告的筛选器。

### 主要故障报告筛选器

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
<p>如果您未输入开始时间，该报告会自动将某个特定日的 12:00 AM 作为开始时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="even">
<td><p><strong>结束日期</strong></p></td>
<td><p>时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入结束时间，该报告会自动将某个特定日的 12:00 AM 作为结束时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>活动类型</strong></p></td>
<td><p>活动的类型。选择下列选项之一：</p>
<ul>
<li><p>[所有]</p></li>
<li><p>点对点</p></li>
<li><p>会议</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>形式</strong></p></td>
<td><p>在这里，只能选择“[所有]”选项。</p></td>
</tr>
<tr class="odd">
<td><p><strong>池</strong></p></td>
<td><p>注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“[所有]”查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</p></td>
</tr>
<tr class="even">
<td><p><strong>类别</strong></p></td>
<td><p>遇到的故障的类型。选择下列选项之一：</p>
<ul>
<li><p>预期失败和意外失败</p></li>
<li><p>意外失败</p></li>
</ul>
<p>“预期失败”是指预计会出现的失败情况。例如，如果用户将其状态设置为“请勿打扰”，那么向该用户发出的任何呼叫应该都会失败。“意外失败”是指在本该正常运行的系统中出现的失败情况。例如，如果呼叫者处于呼叫等待状态，则不应该终止呼叫。如果终止，则会被标记为意外失败。</p></td>
</tr>
<tr class="odd">
<td><p><strong>响应代码</strong></p></td>
<td><p>会议失败时发送的 SIP 响应代码。请输入完整的响应代码。例如：</p>
<p>400</p></td>
</tr>
<tr class="even">
<td><p><strong>诊断 ID</strong></p></td>
<td><p>附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。诊断标头是可选的（SIP 会话可以不包含这些标头），并且只对遇到此类问题的会话报告诊断 ID。</p></td>
</tr>
</tbody>
</table>


## 指标

下表列出了主要故障报告中提供的信息。

### 主要故障报告指标

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
<td><p><strong>等级</strong></p></td>
<td><p>是</p></td>
<td><p>基于报告的会话数确定的相对等级。</p></td>
</tr>
<tr class="even">
<td><p><strong>报告的会话</strong></p></td>
<td><p>是</p></td>
<td><p>基于诊断 ID 和 SIP 响应代码确定的失败会话总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>影响的用户</strong></p></td>
<td><p>是</p></td>
<td><p>失败会话影响的用户总数。</p></td>
</tr>
<tr class="even">
<td><p><strong>故障信息</strong></p></td>
<td><p>否</p></td>
<td><p>有关故障的详细信息，包括诊断 ID、SIP 响应代码和有关会话失败原因的说明。</p></td>
</tr>
<tr class="odd">
<td><p><strong>过去的趋势</strong></p></td>
<td><p>否</p></td>
<td><p>以图形的形式显示失败会话在一段时间内的趋势。</p></td>
</tr>
</tbody>
</table>

