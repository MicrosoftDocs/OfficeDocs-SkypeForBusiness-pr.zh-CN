---
title: Lync Server 2013：对等语音和视频报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Peer-to-Peer Voice and Video Report
ms:assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615040(v=OCS.15)
ms:contentKeyID: 48185535
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 974f403f65b494964affc4fbdc4880820ecb2db2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038654"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="peer-to-peer-voice-and-video-report-in-lync-server-2013"></a>Lync Server 2013 中的对等语音和视频报告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-21_

对等语音和视频报告提供了在指定时间段内语音和视频呼叫的分布的详细信息（例如，每小时的呼叫数或每天的呼叫数）。 该报告还提供了查看所有发出的语音和视频呼叫，或仅查看成功或失败呼叫的选项。 这些报告显示了从细分为以下分组的呼叫信息：

  - 每个池的调用

  - 每个呼叫类型的呼叫（例如，Lync to Lync 呼叫，以及对 PSTN 网络中某个人的 Lync 呼叫）

  - 每种访问类型的呼叫数（登录到内部网络的用户数与登录到外部网络的用户数）

  - 每个中介服务器的呼叫数

<div>

## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a>访问对等语音和视频报告

您只能通过打开对等活动摘要报告，然后单击以下任一指标来访问对等语音和视频报告：

  - 点对点音频会话总数

  - 对等音频总分钟数

  - 点对点视频会话总数

  - 对等视频总分钟数

</div>

<div>

## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a>最大限度地利用对等语音和视频报告

您可以通过多种方式筛选对等语音和视频报告。 但是，默认情况下，这些筛选选项在视图中是隐藏的。 若要查看可用的筛选选项，请单击报告窗口右上角的 "**显示/隐藏参数**" 按钮。

</div>

<div>

## <a name="filters"></a>筛选器

筛选器提供了一种方法，可用于返回更精细的目标数据集或以不同方式查看数据。 下表列出了可用于对等语音和视频报告的筛选器。

### <a name="peer-to-peer-voice-and-video-report-filters"></a>对等语音和视频报告筛选器

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
<td><p><strong>媒体类型</strong></p></td>
<td><p>指示会话中使用的媒体的类型。 选择下列选项之一：</p>
<ul>
<li><p>两者都有</p></li>
<li><p>音频</p></li>
<li><p>视频</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>呼叫处置</strong></p></td>
<td><p>指示会话是成功还是失败。 选择下列选项之一：</p>
<ul>
<li><p>各种</p></li>
<li><p>成功调用</p></li>
<li><p>失败的呼叫</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>报告依据</strong></p></td>
<td><p>指示要在报告中使用的值。选择下列选项之一：</p>
<ul>
<li><p>会话计数</p></li>
<li><p>呼叫分钟数</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>按池的对等语音和视频活动的指标

下表列出了每个池的对等语音和视频报告中提供的信息。

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>按池的对等语音和视频活动的指标

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
<td><p>用于呼叫的注册器池或边缘服务器的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>日期/时间</strong></p></td>
<td><p>否</p></td>
<td><p>呼叫发生的日期和时间段。</p></td>
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

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>按呼叫类型的对等语音和视频活动的指标

下表列出了对等语音和视频报告中提供的针对每种类型的呼叫的信息。

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>按呼叫类型的对等语音和视频活动的指标

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
<td><p><strong>呼叫类型</strong></p></td>
<td><p>否</p></td>
<td><p>指示发起的呼叫类型。 值为下列值之一：</p>
<ul>
<li><p>UC 到 UC</p></li>
<li><p>UC 到 PSTN</p></li>
<li><p>PSTN 到 UC</p></li>
<li><p>PSTN 到 PSTN</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>日期/时间</strong></p></td>
<td><p>否</p></td>
<td><p>呼叫发生的日期和时间段。</p></td>
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

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>按访问类型的对等语音和视频活动的指标

下表列出了对每种网络访问类型的对等语音和视频报告中提供的信息。

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>按访问类型的对等语音和视频活动的指标

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
<td><p><strong>活动类型</strong></p></td>
<td><p>否</p></td>
<td><p>指示在发出呼叫时，客户端是否登录到内部网络或外部网络。 通常可指定下列值之一：</p>
<ul>
<li><p>内部</p></li>
<li><p>外部</p></li>
<li><p>混合</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>日期/时间</strong></p></td>
<td><p>否</p></td>
<td><p>呼叫发生的日期和时间段。</p></td>
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

## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>中介服务器的对等语音和视频活动的指标

下表列出了每个中介服务器的对等语音和视频报告中提供的信息。

### <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>中介服务器的对等语音和视频活动的指标

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
<td><p><strong>中介服务器</strong></p></td>
<td><p>否</p></td>
<td><p>中介服务器的名称。</p></td>
</tr>
<tr class="even">
<td><p><strong>日期/时间</strong></p></td>
<td><p>否</p></td>
<td><p>呼叫发生的日期和时间段。</p></td>
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

