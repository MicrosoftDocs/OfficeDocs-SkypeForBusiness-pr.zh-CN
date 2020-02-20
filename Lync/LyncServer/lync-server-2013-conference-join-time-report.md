---
title: Lync Server 2013：会议加入时间报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conference Join Time Report
ms:assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205344(v=OCS.15)
ms:contentKeyID: 48185686
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e11932d1f63e6d756b0a3a5ba1eb7b33498dac61
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conference-join-time-report-in-lync-server-2013"></a>Lync Server 2013 中的会议加入时间报告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-04-23_

会议加入时间摘要使您能够确定用户加入会议所需的时间。 该报告显示平均联接时间（以毫秒为单位），并提供一个细目，让你知道有多少用户能够在2秒或更短的时间内加入会议，在2到5秒的用户加入会议时需要多少用户，等等。

<div>

## <a name="accessing-the-conference-join-time-report"></a>访问会议加入时间报告

可以从 "监控报告" 主页访问会议加入时间报告。

</div>

<div>

## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。 下表列出了可用于会议加入时间报告的筛选器。

### <a name="conference-join-time-report-filters"></a>会议加入时间报告筛选器

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
<td><p><strong>From</strong></p></td>
<td><p>时间范围的开始日期/时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>时间范围的结束日期/时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Interval</strong></p></td>
<td><p>时间间隔。选择下列选项之一：</p>
<ul>
<li><p>每小时（最多可显示 25 个小时）</p></li>
<li><p>每天（最多可显示 31 天）</p></li>
<li><p>每周（最多可显示 12 周）</p></li>
<li><p>每月（最多可显示 12 个月）</p></li>
</ul>
<p>如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 8/7/2012、结束日期为 9/28/2012、间隔为“每天”，则显示从 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 这些天的数据（即总共 31 天的数据）。</p></td>
</tr>
<tr class="even">
<td><p><strong>Pool</strong></p></td>
<td><p>注册器池或边缘服务器的完全限定域名 (FQDN)。可以选择单个池，也可以单击“[所有]”<strong></strong>查看所有池的数据。系统根据数据库中的记录自动为您填充该下拉列表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>会议会话</strong></p></td>
<td><p>会话类型。 允许的值包括：</p>
<ul>
<li><p>各种</p></li>
<li><p>聚焦会话（焦点是在线会议的中心策略和状态管理器，并协调会议的各个方面</p></li>
<li><p>应用程序共享</p></li>
<li><p>A/V 会议</p></li>
</ul>
<p>如果选择 "[所有]"，会议总加入时间将显示在报告的顶部。 请注意，这些总和仅适用于通过使用 Microsoft Exchange 或 Microsoft Outlook 安排的会议。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指标

下表列出了会议加入时间报告中提供的信息。

### <a name="conference-join-time-report-metrics"></a>会议加入时间报告指标

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
<td><p><strong>Date</strong></p>
<p>此指标的实际标题将根据所选的间隔而有所不同。</p></td>
<td><p>否</p></td>
<td><p>会议发生的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>会话总数</strong></p></td>
<td><p>否</p></td>
<td><p>会话的总数，包括成功的会话、失败的会话（预期失败和意外失败）及未归类的会话。</p></td>
</tr>
<tr class="odd">
<td><p><strong>平均值（毫秒）</strong></p></td>
<td><p>否</p></td>
<td><p>参与者加入会议所需的平均时间（以毫秒为单位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>会话&lt; 2 秒，批量</strong></p></td>
<td><p>否</p></td>
<td><p>能够在不到2秒的时间内加入会议的参与者的人数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>会话&lt; 2 秒，百分比</strong></p></td>
<td><p>否</p></td>
<td></td>
</tr>
<tr class="even">
<td><p><strong>会话2-5 秒，卷</strong></p></td>
<td><p>否</p></td>
<td><p>在2秒到5秒之间加入会议的参与者的人数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>会话2-5 秒，百分比</strong></p></td>
<td><p>否</p></td>
<td><p>在2秒到5秒之间加入会议的呼叫参与者总数的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>会话5-10 秒，卷</strong></p></td>
<td><p>否</p></td>
<td><p>在5秒和10秒之间加入会议的参与者的人数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>会话5-10 秒，百分比</strong></p></td>
<td><p>否</p></td>
<td><p>在5秒和10秒之间加入会议的总呼叫参与者的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>会话&gt; 10 秒，批量</strong></p></td>
<td><p>否</p></td>
<td><p>需要10秒以上加入会议的参与者的人数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>会话&gt; 10 秒，百分比</strong></p></td>
<td><p>否</p></td>
<td><p>需要10秒以上加入会议的总呼叫参与者的百分比。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

