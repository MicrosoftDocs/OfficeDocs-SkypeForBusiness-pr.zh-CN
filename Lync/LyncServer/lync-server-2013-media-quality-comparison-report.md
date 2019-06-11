---
title: 'Lync Server 2013: 媒体质量比较报表'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media Quality Comparison Report
ms:assetid: c1d0b5a8-98ff-455a-b78b-a05a21cf066d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205236(v=OCS.15)
ms:contentKeyID: 48185317
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6697e02d7b821ebd3dc3cabc3a95c8d00960a08
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827443"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-quality-comparison-report-in-lync-server-2013"></a>Lync Server 2013 中的媒体质量比较报表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-04-22_

媒体质量比较报告使您能够比较不同类型的音频呼叫（例如，通过无线网络发出的呼叫与通过有线连接发出的呼叫）的呼叫质量值。

<div>

## <a name="accessing-the-media-quality-comparison-report"></a>访问媒体质量比较报告

媒体质量比较报告可以从“监控报告”主页进行访问。

</div>

<div>

## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。下表列出了可用于媒体质量比较报告的筛选器。

### <a name="media-quality-comparison-report-filters"></a>媒体质量比较报告筛选器

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
<td><p><strong>呼叫</strong></p></td>
<td><p>要用作主要比较项目的呼叫类型。允许的值包括：</p>
<ul>
<li><p>[所有]</p></li>
<li><p>外部</p></li>
<li><p>内部</p></li>
<li><p>VPN</p></li>
<li><p>非 VPN</p></li>
<li><p>有线</p></li>
<li><p>无线</p></li>
<li><p>外部和有线</p></li>
<li><p>外部和无线</p></li>
<li><p>外部和 VPN</p></li>
<li><p>外部和非 VPN</p></li>
<li><p>内部和有线</p></li>
<li><p>内部和无线</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>与呼叫进行比较</strong></p></td>
<td><p>要用作次要比较项目的呼叫类型，允许的值包括：</p>
<ul>
<li><p>[所有]</p></li>
<li><p>外部</p></li>
<li><p>内部</p></li>
<li><p>VPN</p></li>
<li><p>非 VPN</p></li>
<li><p>有线</p></li>
<li><p>无线</p></li>
<li><p>外部和有线</p></li>
<li><p>外部和无线</p></li>
<li><p>外部和 VPN</p></li>
<li><p>外部和非 VPN</p></li>
<li><p>内部和有线</p></li>
<li><p>内部和无线</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>间隔</strong></p></td>
<td><p>时间间隔。选择下列选项之一：</p>
<ul>
<li><p>每小时（最多可显示 25 个小时）</p></li>
<li><p>每天（最多可显示 31 天）</p></li>
<li><p>每周（最多可显示 12 周）</p></li>
</ul>
<p>如果开始日期和结束日期超出了所选间隔允许的最长时间，则仅显示最长时间（从开始日期开始）。 例如, 如果选择 "开始日期 7/7/2012" 和 "结束日期 2/28/2012" 的 "每日间隔", 则会显示 8/7/2012 12:00 AM 到 9/7/2012 12:00 AM 的数据 (即, 总共31天的数据)。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指标

下表列出了媒体质量比较报告中提供的信息。

### <a name="media-quality-comparison-report-metrics"></a>媒体质量比较报告指标

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
<td><p><strong>呼叫量</strong></p></td>
<td><p>否</p></td>
<td><p>呼叫总数。</p></td>
</tr>
<tr class="even">
<td><p><strong>性能降低 (MOS)</strong></p></td>
<td><p>否</p></td>
<td><p>呼叫过程中遇到的性能降低的 MOS（平均意见得分）的平均值。 性能降低值的范围介于 0.0 和 5.0 之间；该值小于或等于 0.5 表示可接受的性能降低。 过去，平均意见得分是通过让用户对呼叫质量进行评级（范围为 1 到 5）来计算得出的。 Lync 服务器使用一组算法来预测用户对呼叫的评分。</p>
<p>高性能降低值可能是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器或终结点超载造成的，从而导致音频失真或丢失。</p></td>
</tr>
<tr class="odd">
<td><p><strong>质量欠佳的呼叫百分比</strong></p></td>
<td><p>否</p></td>
<td><p>归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。</p></td>
</tr>
<tr class="even">
<td><p><strong>来回行程（毫秒）</strong></p></td>
<td><p>否</p></td>
<td><p>实时传输协议数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 200 毫秒被视为质量可接受。</p>
<p>高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</p></td>
</tr>
<tr class="odd">
<td><p><strong>数据包丢失</strong></p></td>
<td><p>否</p></td>
<td><p>平均实时传输协议 (RTP) 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时，即发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。数据包丢失通常导致音频失真或丢失。</p></td>
</tr>
<tr class="even">
<td><p><strong>抖动（毫秒）</strong></p></td>
<td><p>否</p></td>
<td><p>在 RTP 数据包到达之间检测到的平均抖动率。 (抖动是&quot;shakiness&quot;通话的衡量。)高抖动值通常由拥塞或过载的媒体服务器导致, 并导致失真或丢失的音频。</p></td>
</tr>
<tr class="odd">
<td><p><strong>修复程序隐藏比率</strong></p></td>
<td><p>否</p></td>
<td><p>隐藏的音频样本与样本总数的平均比率。（隐藏的音频样本是一项技术，用于消除通常由丢弃的网络数据包造成的意外转换。）高值指示数据包丢失或抖动造成的显著的丢失隐藏级别，从而导致音频失真或丢失。</p></td>
</tr>
<tr class="even">
<td><p><strong>修复程序拉伸比率</strong></p></td>
<td><p>否</p></td>
<td><p>拉伸的音频样本数与样本总数的平均比率。（拉伸的音频是一类已扩展的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本拉伸级别，从而导致音频听起来很机械或失真。</p></td>
</tr>
<tr class="odd">
<td><p><strong>修复程序压缩比率</strong></p></td>
<td><p>否</p></td>
<td><p>压缩的音频样本与样本总数的平均比率。（压缩的音频是一类已压缩的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本压缩级别，从而导致音频听起来像是已加速或失真。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

