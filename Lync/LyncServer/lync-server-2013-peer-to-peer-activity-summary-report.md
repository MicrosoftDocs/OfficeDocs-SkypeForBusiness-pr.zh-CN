---
title: Lync Server 2013：对等活动摘要报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Activity Summary Report
ms:assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615041(v=OCS.15)
ms:contentKeyID: 48185884
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e232d6ffee5e49d52eef68c9668d7d8b6325f13d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520799"
---
# <a name="peer-to-peer-activity-summary-report-in-lync-server-2013"></a>Lync Server 2013 中的对等活动摘要报告

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-21_

点对点活动摘要报告提供点对点通信会话的整体视图。 对等会话通常只涉及两个用户，不需要使用 Lync Server 会议服务。 相比之下，会议通常涉及两个以上的用户，并且需要使用 Microsoft Lync Server 2013 会议服务。 会议活动在会议摘要报告上进行报告。

点对点活动摘要报告帮助您回答诸如下列问题：

  - 在特定某一天，我的用户发送了多少点对点即时消息？

  - 我的任何用户是否确实利用 Lync Server 应用程序共享和文件传输功能？

  - 用户曾报怨在一天的特定时间网络看上去很慢。在此期间点对点音频和视频会话占用了多少分钟时间？

<div>

## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>访问点对点活动摘要报告

可从监视报告主页访问点对点活动摘要报告。 您可以通过单击以下任一指标 [在 Lync Server 2013 中打开对等 IM 报告](lync-server-2013-peer-to-peer-im-report.md) ：

  - 对等 IM 会话总数

  - 点对点 IM 消息总数

同样，通过单击以下任何指标可打开点对点语音和视频报告：

  - 点对点音频会话总数

  - 点对点音频会话分钟总数

  - 点对点音频会话总数

  - 点对点音频会话分钟总数

</div>

<div>

## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>充分利用点对点活动摘要报告

在点对点活动摘要报告的底部，您将找到总标准数，例如，总点对点 IM 会话数和总点对点 IM 消息。这提供了报告正文中找到的详细信息的快速摘要。

</div>

<div>

## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，点对点活动摘要报告允许您选择数据的分组方式。在此示例中，将按小时、日、周或月对活动进行分组。

下表列出了可用于点对点活动摘要报告的筛选器。

### <a name="peer-to-peer-activity-summary-report-filters"></a>点对点活动摘要报告筛选器

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
<p>7/17/2012 1:00 PM</p>
<p>如果您未输入开始时间，该报告会自动将某个特定日的上午 12:00 作为开始时间。若要按日查看数据，请只输入日期：</p>
<p>7/17/12012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/13/2012</p>
<p>一周始终是从星期日开始至星期六结束。</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>时间范围的结束日期和时间。若要按小时查看数据，请输入结束日期和时间，如下所示：</p>
<p>7/17/2012 1:00 PM</p>
<p>如果您未输入结束时间，该报告会自动将某个特定日的上午 12:00 作为结束时间。若要按日查看数据，请只输入日期：</p>
<p>7/17/12012</p>
<p>若要按周或按月查看，请输入您要查看的周或月中的任一日期（您不必输入周或月的第一天）：</p>
<p>7/13/2012</p>
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
<p>如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。例如，如果选择的开始日期为 8/7/2012、结束日期为 9/28/2012、间隔为“每天”，则显示从 8/7/2012 12:00 AM 到 9/7/2012  12:00 AM 这些天的数据（即总共 31 天的数据）。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指标

下表列出了点对点活动摘要报告中提供的信息。

### <a name="peer-to-peer-activity-summary-report-metrics"></a>点对点活动摘要报告指标

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
<td><p><strong>每小时</strong></p>
<p><strong>每天</strong></p>
<p><strong>每周</strong></p>
<p><strong>每月</strong></p></td>
<td><p>否</p></td>
<td><p>指示在筛选器工具栏上选择的时间间隔。如果适用，可单击某一给定的时间间隔以查看该间隔的详细信息。例如，如果使用“每天”间隔并单击 7/17/2012，可查看当日用户注册活动的每小时细分信息。</p></td>
</tr>
<tr class="even">
<td><p><strong>点对点会话总数</strong></p></td>
<td><p>否</p></td>
<td><p>发起的点对点会话总数（无论是哪种会话类型）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>点对点 IM 会话总数</strong></p></td>
<td><p>否</p></td>
<td><p>点对点即时消息 (IM) 会话总数。单击此项时，报告将显示所选时间段的点对点 IM 报告。</p></td>
</tr>
<tr class="even">
<td><p><strong>点对点 IM 消息总数</strong></p></td>
<td><p>否</p></td>
<td><p>在点对点会话中发送的即时消息总数。单击此项时，报告将显示所选时间段的点对点 IM 报告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>点对点音频会话总数</strong></p></td>
<td><p>否</p></td>
<td><p>点对点音频呼叫总数。单击此字段时，报告将显示所选时间段的点对点语音和视频报告。</p></td>
</tr>
<tr class="even">
<td><p><strong>点对点音频会话总分钟数</strong></p></td>
<td><p>否</p></td>
<td><p>点对点音频会话持续的总时间。 单击此项时，报告将显示所选时间段的点对点语音和视频报告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>点对点音频会话平均分钟数</strong></p></td>
<td><p>否</p></td>
<td><p>点对点音频会话持续的平均时间。计算方法是音频会话总时间除以音频会话总数。</p></td>
</tr>
<tr class="even">
<td><p><strong>点对点视频会话总数</strong></p></td>
<td><p>否</p></td>
<td><p>点对点视频呼叫总数。请注意，视频会话还算作音频会话：每个视频会话算作一个视频会话和一个音频会话。单击此项时，报告将显示所选时间段的点对点语音和视频报告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>点对点视频会话总分钟数</strong></p></td>
<td><p>否</p></td>
<td><p>点对点视频会话持续的总时间。单击此项时，报告将显示所选时间段的点对点语音和视频报告。</p></td>
</tr>
<tr class="even">
<td><p><strong>点对点视频会话平均分钟数</strong></p></td>
<td><p>否</p></td>
<td><p>点对点视频会话持续的平均时间。计算方法是视频会话总时间除以视频会话总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>点对点文件传输会话总数</strong></p></td>
<td><p>否</p></td>
<td><p>包含文件传输的点对点会话总数。</p></td>
</tr>
<tr class="even">
<td><p><strong>点对点应用程序共享会话总数</strong></p></td>
<td><p>否</p></td>
<td><p>包含应用程序共享的点对点会话总数。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

