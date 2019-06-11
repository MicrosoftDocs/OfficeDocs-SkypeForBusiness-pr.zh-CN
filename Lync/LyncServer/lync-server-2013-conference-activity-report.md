---
title: 'Lync Server 2013: 会议活动报告'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conference Activity Report
ms:assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558627(v=OCS.15)
ms:contentKeyID: 48183618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f96ddc5dfda18fa1d96903eb5755481f76853c06
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837504"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conference-activity-report-in-lync-server-2013"></a>Lync Server 2013 中的 "会议活动" 报表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-22_

会议活动报表使你可以轻松地回答以下问题: 每天保持多少个会议以及何时保留这些会议？ 此类信息不仅非常有用, 还可以作为疑难解答工具使用。 例如, 假设用户抱怨, 网络在一天的中间似乎非常慢。 快速浏览会议活动报表可能会提出一个可能的原因: 在 10:00 AM 和 2:00 PM 之间安排的会议时间比现在更多。

如果因网速慢而导致出现问题，您可以鼓励用户将他们的一些会议重新安排在一天中流量较少的时段。

<div>

## <a name="accessing-the-conference-activity-report"></a>访问会议活动报告

通过单击以下任一指标, 可从[Lync Server 2013 中的 "会议摘要" 报告](lync-server-2013-conference-summary-report.md)访问会议活动报告:

  - 会议总数

  - 参与者总数

</div>

<div>

## <a name="making-the-best-use-of-the-conference-activity-report"></a>充分利用会议活动报告

默认情况下，会议活动报告向您显示指定时段内的会议总数（例如，每天的会议总数或每小时的会议总数）。但是，您还可以选择显示该时段内与会者的总数或总参与分钟数。为此，请单击“显示/隐藏参数”按钮以显示筛选选项，然后从“报告依据”下拉列表中选择下列选项之一：

  - 参与者计数

  - 参与分钟数

  - 会议计数

</div>

<div>

## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于会议活动报告的筛选器。

### <a name="conference-activity-report-filters"></a>会议活动报告筛选器

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
<td><p><strong>从</strong></p></td>
<td><p>时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入开始时间，该报告会自动将将某个特定日期的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="even">
<td><p><strong>到</strong></p></td>
<td><p>时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入结束时间，该报告会自动将某个特定日期的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</p>
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
<p>如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。 例如, 如果选择 "开始日期 7/7/2012" 和 "结束日期 2/28/2012" 的 "每日间隔", 则会显示 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 的数据 (即, 总共31天的数据)。</p></td>
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


</div>

<div>

## <a name="metrics-for-conferences-by-pool"></a>按池分类的会议的指标

下表列出了每个池的会议活动报告中的信息。

### <a name="metrics-for-conferences-by-pool"></a>按池分类的会议的指标

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
<th>描述</th>
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


</div>

<div>

## <a name="metrics-for-conferences-by-server-type"></a>按服务器类型分类的会议的指标

下表列出了每种服务器类型的会议活动报告中的信息。

### <a name="metrics-for-conferences-by-server-type"></a>按服务器类型分类的会议的指标

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
<th>描述</th>
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


</div>

</div>

<span> </span>

</div>

</div>

</div>

