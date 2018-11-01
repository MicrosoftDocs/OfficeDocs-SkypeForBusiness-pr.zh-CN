---
title: Lync Server 2013：故障分布报告
TOCTitle: 故障分布报告
ms:assetid: 365c7beb-24d4-40f5-92e7-4978b9688916
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558635(v=OCS.15)
ms:contentKeyID: 49312480
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的故障分布报告

 

_**上一次修改主题：** 2015-03-09_

故障分布报告按以下类别对失败会话进行分级：

  - 主要诊断原因

  - 主要形式

  - 主要池

  - 主要来源

  - 主要组件

  - 主要来源用户

  - 主要目标用户

  - 主要来源用户代理

可以使用这些类别准确确定出现问题的位置，在某些情况下还可准确确定出现问题的原因。例如，假设您在指定的一天内记录了 242 个失败的音频/视频会话。如果您查看故障分布报告，它可能会指示这些失败会话中有 237 个发生在您的 Dublin 池中。在跟踪和诊断出现这些故障的原因时，这为您提供了一个良好的开端。如果单击“主要池”类别下的 Dublin 池，即可看到该池的故障分布报告。然后您可以开始分析 Dublin 池为何出现如此多的问题。

## 查看故障分布报告

您可以通过单击“预期失败量”或“意外失败量”指标，从以下任意报告中访问故障分布报告：

  - [Lync Server 2013 中的主要故障报告](lync-server-2013-top-failures-report.md)

  - [Lync Server 2013 中的会议诊断报告](lync-server-2013-conference-diagnostic-report.md)

  - [Lync Server 2013 中的点对点活动诊断报告](lync-server-2013-peer-to-peer-activity-diagnostic-report.md)

从故障分布报告中，您可以单击下列任意指标以查看 [Lync Server 2013 中的故障列表报告](lync-server-2013-failure-list-report.md)：

  - 主要诊断原因（会话）

  - 主要形式（会话）

  - 主要池（会话）

  - 主要来源（会话）

  - 主要组件（会话）

  - 主要来源用户（会话）

  - 主要目标用户（会话）

  - 主要来源用户代理（会话）

## 使用故障分布报告

根据您的监视器尺寸和屏幕分辨率，当您在屏幕上查看故障分布报告中显示的某些数据时，这些数据可能会被截断。用户代理（可能具有很长的标签）等指标尤其可能出现这种情况。例如，具有类似“UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Lync 2013)”的名称的用户代理可能只会部分显示在屏幕上：

UCCAPI/4.0.7400.0 OC/4.0.7400.0 (Microsoft Ly...

幸运的是，只需将鼠标指针停留在截断值上方即可查看整个标签。

可以使用故障分布报告按其进行筛选的一个有用指标是诊断 ID。如果您看到其他报告中出现相同的诊断 ID，则可以在故障分布报告中按此 ID 进行筛选，并获得有关失败会话期间报告此 ID 的准确位置及频率的十分详细的信息。

## 筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，故障分布报告允许您依据活动类型（点对点会话还是会议会话）或每个失败会话附带的诊断 ID 等条件进行筛选。

下表列出了可用于故障分布报告的筛选器。

### 故障分布报告筛选器

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
<td><p>注册器池或边缘服务器的完全限定的域名 (FQDN)。可以选择单个池，也可以单击“[所有]”查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</p></td>
</tr>
<tr class="even">
<td><p><strong>活动类型</strong></p></td>
<td><p>要筛选的活动类型。选择下列选项之一：</p>
<ul>
<li><p>[所有]</p></li>
<li><p>点对点</p></li>
<li><p>会议</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>会话类别</strong></p></td>
<td><p>指示相应活动已成功还是失败。选择下列选项之一：</p>
<ul>
<li><p>[所有]</p></li>
<li><p>成功</p></li>
<li><p>预期失败</p></li>
<li><p>意外失败</p></li>
</ul>
<p>“预期失败”是指预计会出现的失败情况。例如，如果用户将其状态设置为“请勿打扰”，那么向该用户发出的任何呼叫应该都会失败。“意外失败”是指在本该正常运行的系统中出现的失败情况。例如，如果呼叫者处于呼叫等待状态，则不应该终止呼叫。如果终止，则会被标记为意外失败。</p></td>
</tr>
<tr class="even">
<td><p><strong>诊断 ID</strong></p></td>
<td><p>附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。诊断标头是可选的（SIP 会话可以不包含这些标头），并且只对遇到此类问题的会话报告诊断 ID。</p></td>
</tr>
</tbody>
</table>


## 主要诊断原因的指标

下表列出了故障分布报告中基于最常见的诊断 ID 提供的信息。

### 主要诊断原因的指标

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
<td><p>否</p></td>
<td><p>失败会话的相对等级，根据诊断 ID 确定。诊断 ID 是附加到 SIP 消息的唯一标识符（采用 ms-diagnostics 标头的形式），提供的信息在排查错误时通常很有帮助。</p></td>
</tr>
<tr class="even">
<td><p><strong>主要诊断原因</strong></p></td>
<td><p>否</p></td>
<td><p>会话中生成的诊断 ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>会话数</strong></p></td>
<td><p>否</p></td>
<td><p>生成了指定诊断 ID 的失败会话总数。</p></td>
</tr>
</tbody>
</table>


## 主要形式的指标

下表列出了故障分布报告中基于所遇故障最多的会话形式提供的信息。

### 主要形式的指标

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
<td><p>否</p></td>
<td><p>失败会话的相对等级，根据会话类型（例如，音频/视频会议或点对点文件传输会话）确定。</p></td>
</tr>
<tr class="even">
<td><p><strong>主要形式</strong></p></td>
<td><p>否</p></td>
<td><p>会话类型。</p></td>
</tr>
<tr class="odd">
<td><p><strong>会话数</strong></p></td>
<td><p>否</p></td>
<td><p>涉及指定形式的失败会话总数。</p></td>
</tr>
</tbody>
</table>


## 主要池的指标

下表列出了故障分布报告中基于所遇故障最多的池提供的信息。

### 主要池的指标

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
<td><p>否</p></td>
<td><p>失败会话的相对等级，根据执行会话的 注册器池或 边缘服务器确定。</p></td>
</tr>
<tr class="even">
<td><p><strong>主要池</strong></p></td>
<td><p>否</p></td>
<td><p>注册器池或 边缘服务器的名称。</p></td>
</tr>
<tr class="odd">
<td><p><strong>会话数</strong></p></td>
<td><p>否</p></td>
<td><p>每个 注册器池或 边缘服务器的失败会话总数。</p></td>
</tr>
</tbody>
</table>


## 主要来源的指标

下表列出了故障分布报告中基于所遇故障最多的计算机提供的信息。

### 主要来源的指标

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
<td><p>否</p></td>
<td><p>失败会话的相对等级，根据计算机确定。</p></td>
</tr>
<tr class="even">
<td><p><strong>主要来源</strong></p></td>
<td><p>否</p></td>
<td><p>失败会话所涉及的计算机的名称。</p></td>
</tr>
<tr class="odd">
<td><p><strong>会话数</strong></p></td>
<td><p>否</p></td>
<td><p>每台计算机的失败会话总数。</p></td>
</tr>
</tbody>
</table>


## 主要组件的指标

下表列出了故障分布报告中基于所遇故障最多的 Microsoft Lync Server 2010 组件提供的信息。

### 主要组件的指标

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
<td><p>否</p></td>
<td><p>失败会话的相对等级，根据 Lync Server 2010 组件（例如，ExumRouting、GroupChat 或 MediationServer）确定。</p></td>
</tr>
<tr class="even">
<td><p><strong>主要组件</strong></p></td>
<td><p>否</p></td>
<td><p>失败会话所涉及的组件的名称。</p></td>
</tr>
<tr class="odd">
<td><p><strong>会话数</strong></p></td>
<td><p>否</p></td>
<td><p>每个组件的失败会话总数。</p></td>
</tr>
</tbody>
</table>


## 主要来源用户的指标

下表列出了故障分布报告中基于尝试呼叫其他人时所遇故障最多的用户提供的信息，尝试呼叫其他人的用户称为“来源”用户。

### 主要来源用户的指标

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
<td><p>否</p></td>
<td><p>失败会话的相对等级，根据受邀加入会话的用户确定。</p></td>
</tr>
<tr class="even">
<td><p><strong>主要来源用户</strong></p></td>
<td><p>否</p></td>
<td><p>受邀加入会话的用户的 SIP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>会话数</strong></p></td>
<td><p>否</p></td>
<td><p>每个用户的失败会话总数。</p></td>
</tr>
</tbody>
</table>


## 主要目标用户的指标

下表列出了故障分布报告中基于其他人尝试呼叫的所遇故障最多的用户提供的信息，其他人尝试呼叫的用户称为“目标”用户。


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
<td><p>否</p></td>
<td><p>失败会话的相对等级，根据发起会话的用户确定。</p></td>
</tr>
<tr class="even">
<td><p><strong>主要目标用户</strong></p></td>
<td><p>否</p></td>
<td><p>发起会话的用户的 SIP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>会话数</strong></p></td>
<td><p>否</p></td>
<td><p>每个用户的失败会话总数。</p></td>
</tr>
</tbody>
</table>


## 主要用户代理的指标

下表列出了故障分布报告中基于所遇故障最多的终结点软件提供的信息。

### 主要用户代理的指标

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
<td><p>否</p></td>
<td><p>失败会话的相对等级，根据会话所涉及的用户代理（软件）确定。例如：RTCC/4.0.0.0 Inbound Routing/4.0.0.0。</p></td>
</tr>
<tr class="even">
<td><p><strong>主要用户代理</strong></p></td>
<td><p>否</p></td>
<td><p>失败会话所涉及的用户代理的名称。</p></td>
</tr>
<tr class="odd">
<td><p><strong>会话数</strong></p></td>
<td><p>否</p></td>
<td><p>每个用户代理的失败会话总数。</p></td>
</tr>
</tbody>
</table>

