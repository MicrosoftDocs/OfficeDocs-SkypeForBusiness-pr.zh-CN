---
title: Lync Server 2013：对等 IM 报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer IM Report
ms:assetid: 19ec0145-2398-437b-8989-f780c179b798
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558620(v=OCS.15)
ms:contentKeyID: 48183533
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b74f22e422539a8d7de1f2f7bad29a72d43646a5
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "41989287"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-im-report-in-lync-server-2013"></a>Lync Server 2013 中的对等 IM 报告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

对等 IM 报告提供了有关按池和身份验证类型分类的对等即时消息 (IM) 会话的趋势信息。该报告可以显示在指定时间段内（例如，每天或每小时）进行的会话总数或显示在该时间段内发送的即时消息总数。

<div>

## <a name="accessing-the-peer-to-peer-im-report"></a>访问对等 IM 报告

您可以仅通过[在 Lync Server 2013 中打开对等活动摘要报告](lync-server-2013-peer-to-peer-activity-summary-report.md)，然后单击以下任一指标来访问对等 IM 报告：

  - 对等 IM 会话总数

  - 对等 IM 消息总数

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-im-report"></a>充分利用对等 IM 报告

默认情况下，对等 IM 报告显示每小时（或每天，具体取决于设置）的消息计数。但是，还可以选择按每小时会话数来查看日期。为此，请单击“报告”窗口右上角的“隐藏/显示参数”****，然后从“报告依据”**** 列表中单击“会话计数”****。

</div>

<div>

## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于对等 IM 报告的筛选器。

### <a name="peer-to-peer-im-report-filters"></a>点对点 IM 报告筛选器

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
<td><p>时间范围的开始日期和时间。若要按小时查看数据，请输入开始日期和时间，如下所示：</p>
<p>7/7/2012 1:00 PM</p>
<p>如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</p>
<p>7/7/2012</p>
<p>若要按周或按月查看，请输入周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/3/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>时间范围的结束日期和时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</p>
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


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>按池列出的点对点 IM 会话的指标

下表列出了点对点 IM 报告中提供的信息。

### <a name="metrics-for-peer-to-peer-im-session-by-pool"></a>按池列出的点对点 IM 会话的指标

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
<td><p><strong>Pool</strong></p></td>
<td><p>否</p></td>
<td><p>注册器池或边缘服务器的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>日期/时间</strong></p></td>
<td><p>否</p></td>
<td><p>会话发生的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>否</p></td>
<td><p>会话总数或消息总数。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>按身份验证类型列出的点对点 IM 会话的指标

下表列出了点对点会话中的参与者所用各个身份验证类型的点对点 IM 报告中提供的信息。

### <a name="metrics-for-peer-to-peer-im-session-by-authentication-type"></a>按身份验证类型列出的点对点 IM 会话的指标

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
<li><p>企业版</p></li>
<li><p>联合</p></li>
<li><p>PIC</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>日期/时间</strong></p></td>
<td><p>否</p></td>
<td><p>会话发生的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Total</strong></p></td>
<td><p>否</p></td>
<td><p>会话总数或消息总数。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

