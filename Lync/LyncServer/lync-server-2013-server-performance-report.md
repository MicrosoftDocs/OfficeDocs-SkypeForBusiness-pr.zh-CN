---
title: Lync Server 2013：服务器性能报告
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server Performance Report
ms:assetid: 942bb39a-1790-498e-9d99-8f6ce2d155c3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615018(v=OCS.15)
ms:contentKeyID: 48184879
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: acb7e01086ac423380a913b75391ec3086ee3736
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764860"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-performance-report-in-lync-server-2013"></a>Lync Server 2013 中的服务器性能报告

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-01_

服务器性能报告提供了已经历最高的通话不佳百分比的 Microsoft Lync Server 2013 服务器列表。 该报告按服务器类型对服务器进行了分类，并为以下类型报告了单独的统计信息：

  - 中介服务器

  - A/V 会议服务器

  - A/V 边缘服务器

  - 网关（中介服务器）

  - 网关（中介服务器旁路）

  - 视频（包括 A/V 会议服务器和 A/V 边缘服务器的视频指标）

  - 应用程序共享（包括 A/V 会议服务器和 A/V 边缘服务器的应用程序共享指标）

请务必记住，此报告中显示的等级是相对等级。例如，假定您的性能最差的服务器的 1,000 个已发出的呼叫中有一个质量欠佳的呼叫。此百分比为 .1%，它超出了可接受的百分比。但是，如果这是您性能最差的服务器（即，如果您所有其他服务器的质量欠佳的呼叫的百分比甚至低于 .1%），则该服务器仍会显示在服务器性能报告中。

<div>

## <a name="accessing-the-server-performance-report"></a>访问服务器性能报告

服务器性能报告是从监控报告主页访问的。 您可以通过单击以下任一指标，向下钻取到[Lync Server 2013 中的 "通话清单" 报告](lync-server-2013-call-list-report.md)：

  - 呼叫量

  - 质量欠佳的呼叫百分比

此外，您还可以通过单击以下任一指标向下钻取到服务器媒体质量趋势报告：

  - 趋势

</div>

<div>

## <a name="making-the-best-use-of-the-server-performance-report"></a>充分利用服务器性能报告

服务器性能报告提供了很多筛选数据的方式；例如，您可以基于网络类型（从有线连接发出的呼叫与从无线连接发出的呼叫）和访问类型（从防火墙内发出的呼叫与从防火墙外发出的呼叫）进行筛选。最好在查看服务器性能报告时利用这些筛选器。例如，假设您有一台中介服务器，该服务器的质量欠佳的呼叫的百分比是 3.24%。如果您只查看无线呼叫，同一服务器的质量欠佳的呼叫的百分比可能接近 20%。这意味着服务器进行无线呼叫有困难，由于服务器的无线呼叫没有问题，此问题被部分掩盖了。

</div>

<div>

## <a name="filters"></a>筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，服务器性能报告使您能够执行按服务器类型或按网络类型（即有线或无线）筛选返回的数据之类的操作。您还可以选择数据的分组方式。在此示例中，将按小时、日、周或月对数据进行分组。

下表列出了可用于服务器性能报告的筛选器。

### <a name="server-performance-report-filters"></a>服务器性能报告筛选器

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
<td><p><strong>服务器类型</strong></p></td>
<td><p>指示应报告其性能的服务器的类型。选择下列选项之一：</p>
<ol>
<li><p>[所有]</p></li>
<li><p>中介服务器</p></li>
<li><p>A/V 会议服务器</p></li>
<li><p>A/V 边缘服务器</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>前 N 个</strong></p></td>
<td><p>指示每个类别中将显示的服务器数（基于其质量欠佳的呼叫百分比）。例如，如果您选择“<strong>5</strong>”，则将显示 5 个性能最差的服务器。选择下列选项之一：</p>
<ol>
<li><p>[所有]</p></li>
<li><p>5</p></li>
<li><p>10</p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><strong>访问类型</strong></p></td>
<td><p>指示客户端在发起呼叫时已登录到内部网络还是外部网络。选择下列选项之一：</p>
<ol>
<li><p>[所有]</p></li>
<li><p>内部</p></li>
<li><p>外部</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p><strong>网络类型</strong></p></td>
<td><p>指示客户端在发起呼叫时已连接到的网络的类型。选择下列选项之一：</p>
<ol>
<li><p>[所有]</p></li>
<li><p>有线</p></li>
<li><p>无线</p></li>
</ol></td>
</tr>
<tr class="odd">
<td><p><strong>VPN</strong></p></td>
<td><p>指示外部客户端在发起呼叫时是否使用了虚拟专用网 (VPN) 连接。选择下列选项之一：</p>
<ol>
<li><p>[所有]</p></li>
<li><p>VPN</p></li>
<li><p>非 VPN</p></li>
</ol></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>指标

下表列出了服务器性能报告中提供的信息。

### <a name="server-performance-report-metrics-audio-call-summary"></a>服务器性能报告指标：音频呼叫摘要

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>名称</th>
<th>是否可用作排序依据</th>
<th>描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>服务器</strong></p></td>
<td><p>否</p></td>
<td><p>服务器的名称/IP 地址。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫量</strong></p></td>
<td><p>否</p></td>
<td><p>进行的呼叫总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>质量欠佳的呼叫百分比</strong></p></td>
<td><p>否</p></td>
<td><p>归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。</p></td>
</tr>
<tr class="even">
<td><p><strong>来回行程（毫秒）</strong></p></td>
<td><p>是</p></td>
<td><p>实时传输协议 (RTP) 数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 100 毫秒被视为质量可接受。</p>
<p>高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</p></td>
</tr>
<tr class="odd">
<td><p><strong>性能降低 (MOS)</strong></p></td>
<td><p>是</p></td>
<td><p>呼叫过程中遇到的性能降低的平均意见得分 (MOS) 的平均值。 性能降低值的范围介于 0.0 和 5.0 之间。 该值小于或等于 0.5 表示可接受的性能降低。 过去，平均意见得分是通过让用户对呼叫质量进行评级（范围为 1 到 5）来计算得出的。 在 Lync Server 中，监视服务器使用一组算法来预测用户对呼叫的评分。</p>
<p>高性能降低值可能是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器或终结点超载造成的，从而导致音频失真或丢失。</p></td>
</tr>
<tr class="even">
<td><p><strong>数据包丢失</strong></p></td>
<td><p>是</p></td>
<td><p>平均实时传输协议 (RTP) 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时，即发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。数据包丢失通常导致音频失真或丢失。</p></td>
</tr>
<tr class="odd">
<td><p><strong>抖动（毫秒）</strong></p></td>
<td><p>是</p></td>
<td><p>在 RTP 数据包到达之间检测到的平均抖动率。 （抖动是&quot;shakiness&quot;通话的衡量。）高抖动值通常由拥塞或过载的媒体服务器导致，并导致失真或丢失的音频。</p></td>
</tr>
<tr class="even">
<td><p><strong>修复程序隐藏比率</strong></p></td>
<td><p>是</p></td>
<td><p>隐藏的音频样本与样本总数的平均比率。（隐藏的音频样本是一项技术，用于消除通常由丢弃的网络数据包造成的意外转换。）高值指示数据包丢失或抖动造成的显著的丢失隐藏级别，从而导致音频失真或丢失。</p></td>
</tr>
<tr class="odd">
<td><p><strong>修复程序拉伸比率</strong></p></td>
<td><p>是</p></td>
<td><p>拉伸的音频样本数与样本总数的平均比率。（拉伸的音频是一类已扩展的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本拉伸级别，从而导致音频听起来很机械或失真。</p></td>
</tr>
<tr class="even">
<td><p><strong>修复程序压缩比率</strong></p></td>
<td><p>是</p></td>
<td><p>压缩的音频样本与样本总数的平均比率。（压缩的音频是一类已压缩的音频，可在检测到丢弃的网络数据包时帮助保持呼叫质量。）高值指示抖动造成的显著的样本压缩级别，从而导致音频听起来像是已加速或失真。</p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-video-call-summary"></a>服务器性能报告指标：视频呼叫摘要

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
<td><p><strong>呼叫类型/终结点类型</strong></p></td>
<td><p>否</p></td>
<td><p>当您单击此项时，该报告会显示有关基于这个类型的呼叫的详细信息。呼叫类型包括：</p>
<ul>
<li><p>UC 对等呼叫</p></li>
<li><p>UC 会议会话</p></li>
<li><p>PSTN 会议会话</p></li>
<li><p>PSTN 呼叫: 媒体旁路</p></li>
<li><p>PSTN 呼叫(无旁路): UC 线路</p></li>
<li><p>PSTN 呼叫(无旁路): 网关线路</p></li>
<li><p>其他呼叫类型</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>呼叫量</strong></p></td>
<td><p>否</p></td>
<td><p>每个呼叫类型的呼叫总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>质量欠佳的呼叫百分比</strong></p></td>
<td><p>否</p></td>
<td><p>归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫量（无线呼叫）</strong></p></td>
<td><p>否</p></td>
<td><p>使用了无线连接的呼叫的总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>呼叫量（VPN 呼叫）</strong></p></td>
<td><p>否</p></td>
<td><p>使用了 VPN 连接的呼叫的总数。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫量（外部呼叫）</strong></p></td>
<td><p>否</p></td>
<td><p>使用了外部连接（即内部网络外部的连接）的呼叫的总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>平均比特率 (Kb/s)</strong></p></td>
<td><p>否</p></td>
<td><p>平均视频比特率 (Kb/s)。</p></td>
</tr>
<tr class="even">
<td><p><strong>低比特率百分比</strong></p></td>
<td><p>否</p></td>
<td><p>比特率较低的呼叫的百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>出站数据包丢失</strong></p></td>
<td><p>否</p></td>
<td><p>出站数据包的实时传输协议 (RTP) 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时，即发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。数据包丢失通常导致音频失真或丢失。</p></td>
</tr>
<tr class="even">
<td><p><strong>冻结帧百分比</strong></p></td>
<td><p>否</p></td>
<td><p>“冻结”帧的百分比。在一个冻结帧中，视频将停止前进，而呼叫的音频部分将继续。</p></td>
</tr>
<tr class="odd">
<td><p><strong>出站平均帧速率</strong></p></td>
<td><p>否</p></td>
<td><p>呼叫期间的出站传输的平均帧速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>入站平均帧速率</strong></p></td>
<td><p>否</p></td>
<td><p>呼叫期间的入站传输的平均帧速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>入站低帧速率百分比</strong></p></td>
<td><p>否</p></td>
<td><p>传入视频的比特率较低的呼叫的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>客户端健康状态百分比</strong></p></td>
<td></td>
<td><p>指示呼叫期间客户端设备的相对健康状态。</p></td>
</tr>
</tbody>
</table>


### <a name="server-performance-report-metrics-application-sharing-call-summary"></a>服务器性能报告指标：应用程序共享呼叫摘要

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
<td><p><strong>呼叫类型/终结点类型</strong></p></td>
<td><p>否</p></td>
<td><p>当您单击此项时，该报告会显示有关基于这个类型的呼叫的详细信息。呼叫类型包括：</p>
<ul>
<li><p>UC 对等呼叫</p></li>
<li><p>UC 会议会话</p></li>
<li><p>PSTN 会议会话</p></li>
<li><p>PSTN 呼叫: 媒体旁路</p></li>
<li><p>PSTN 呼叫(无旁路): UC 线路</p></li>
<li><p>PSTN 呼叫(无旁路): 网关线路</p></li>
<li><p>其他呼叫类型</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>呼叫量</strong></p></td>
<td><p>否</p></td>
<td><p>每个呼叫类型的呼叫总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>质量欠佳的呼叫百分比</strong></p></td>
<td><p>否</p></td>
<td><p>归类为质量欠佳的呼叫的总数。质量欠佳的呼叫是指至少一项测量指标超过允许的值的任何呼叫（例如，信号极不稳定的呼叫）。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫量（无线呼叫）</strong></p></td>
<td><p>否</p></td>
<td><p>使用了无线连接的呼叫的总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>呼叫量（VPN 呼叫）</strong></p></td>
<td><p>否</p></td>
<td><p>使用了 VPN 连接的呼叫的总数。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫量（外部呼叫）</strong></p></td>
<td><p>否</p></td>
<td><p>使用了外部连接（即内部网络外部的连接）的呼叫的总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>抖动（毫秒）</strong></p></td>
<td><p>否</p></td>
<td><p>在 RTP 数据包到达之间检测到的平均抖动率。 （抖动是&quot;shakiness&quot;通话的衡量。）高抖动值通常由拥塞或过载的媒体服务器导致，并导致失真或丢失的音频。</p></td>
</tr>
<tr class="even">
<td><p><strong>相对单向平均值</strong></p></td>
<td><p>否</p></td>
<td><p>两个媒体终结点之间的平均相对单向延迟。这是单跃点延迟度量。</p></td>
</tr>
<tr class="odd">
<td><p><strong>平均 RDP 图块处理延迟</strong></p></td>
<td><p>否</p></td>
<td><p>查看会话持续时间内 AS 会议服务器中的平均 RDP 图块处理延迟。此指标不涉及网络延迟。高平均值反映了查看体验中的延迟较长。过载的会议服务器可能会遇到更长的平均延迟。</p></td>
</tr>
<tr class="even">
<td><p><strong>总损坏图块百分比</strong></p></td>
<td><p>否</p></td>
<td><p>已损坏 RDP 图块的总百分比。</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

