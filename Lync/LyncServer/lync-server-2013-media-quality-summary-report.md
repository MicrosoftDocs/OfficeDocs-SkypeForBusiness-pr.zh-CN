---
title: Lync Server 2013：媒体质量摘要报告
TOCTitle: 媒体质量摘要报告
ms:assetid: 8bd59ad6-3087-49c8-b692-5573fe2ffcd8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615012(v=OCS.15)
ms:contentKeyID: 49313534
ms.date: 06/29/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的媒体质量摘要报告

 

_**上一次修改主题：** 2016-06-29_

媒体质量摘要报告可能最适合用来分析组织内部的呼叫质量，此报告提供了分为以下几个类别的详细的用户体验质量 (QoE) 呼叫指标：

  - UC 对等呼叫（如 Microsoft Lync 2013 到 Microsoft Lync 2013 的呼叫）

  - UC 会议会话

  - PSTN 会议会话

  - PSTN 呼叫: 媒体旁路

  - PSTN 呼叫(无旁路): UC 线路

  - PSTN 呼叫(无旁路): 网关线路

  - 其他呼叫类型

一打开报告您就会看到有关所有这些类别的摘要信息。可以展开每种类别以查看子类别（如从 Office Communicator 2007 R2 到 Lync 2013 的呼叫）而无需退出报告。反过来，您可以向下钻取这些子类别以查看有关在该类别中进行的每个呼叫的详细信息。

在 Microsoft Lync Server 2013 中，媒体质量摘要报告会进一步将数据分为三种呼叫类型：音频呼叫、视频呼叫和应用程序共享呼叫。每种呼叫类型在报告中都具有自己对应的部分，并具有自己的自定义呼叫指标集。

此外，可利用媒体质量摘要报告来应用一些筛选器，以便能够比较有线呼叫与无线呼叫的呼叫质量、内部呼叫与外部呼叫的呼叫质量以及 VPN 呼叫与非 VPN 呼叫的呼叫质量。

## 访问媒体质量摘要报告

可从监控报告主页访问媒体质量摘要报告。您可以通过单击以下任一指标来向下钻取到 [Lync Server 2013 中的呼叫列表报告](lync-server-2013-call-list-report.md)：

  - 呼叫量

  - 质量欠佳的呼叫百分比

此外，您可以通过单击以下任一音频呼叫指标来访问媒体质量指标分布报告：

  - 来回行程(毫秒)

  - 性能降低(MOS)

  - 数据包丢失

  - 抖动(毫秒)

  - 修复程序隐藏比率

  - 修复程序拉伸比率

  - 修复程序压缩比率

## 筛选器

利用筛选器，您可以返回一组针对性更强的数据或通过不同的方式查看返回的数据。例如，媒体质量摘要报告使您能够按访问类型（即内部访问与外部访问）或有线/无线网络连接等条件来筛选返回的数据。您还可以选择数据的分组方式。在此示例中，将按小时、日、周或月对呼叫进行分组。

下表列出了可用于媒体质量摘要报告的筛选器。

### 媒体质量摘要报告筛选器

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
<td><p><strong>访问类型</strong></p></td>
<td><p>指示客户端在发起呼叫时已登录到内部网络还是外部网络。选择下列选项之一：</p>
<ul>
<li><p>[所有]</p></li>
<li><p>内部</p></li>
<li><p>外部</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>网络类型</strong></p></td>
<td><p>指示客户端在发起呼叫时已连接到的网络的类型。选择下列选项之一：</p>
<ul>
<li><p>[所有]</p></li>
<li><p>有线</p></li>
<li><p>无线</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>VPN</strong></p></td>
<td><p>指示外部客户端在发起呼叫时是否使用了虚拟专用网 (VPN) 连接。选择下列选项之一：</p>
<ul>
<li><p>[所有]</p></li>
<li><p>VPN</p></li>
<li><p>非 VPN</p></li>
</ul></td>
</tr>
</tbody>
</table>


## 指标

下表列出了媒体质量摘要报告中提供的信息。

### 媒体质量摘要报告指标：音频呼叫摘要

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
<td><p><strong>呼叫量(无线呼叫)</strong></p></td>
<td><p>否</p></td>
<td><p>使用了无线连接的呼叫的总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>呼叫量(VPN 呼叫)</strong></p></td>
<td><p>否</p></td>
<td><p>使用了 VPN 连接的呼叫的总数。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫量(外部呼叫)</strong></p></td>
<td><p>否</p></td>
<td><p>使用了外部连接（即内部网络外部的连接）的呼叫的总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>来回行程(毫秒)</strong></p></td>
<td><p>否</p></td>
<td><p>实时传输协议 (RTP) 数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 100 毫秒被视为质量可接受。</p>
<p>高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</p></td>
</tr>
<tr class="even">
<td><p><strong>性能降低(MOS)</strong></p></td>
<td><p>否</p></td>
<td><p>呼叫过程中遇到的性能降低的平均意见得分 (MOS) 的平均值。性能降低值的范围介于 0.0 和 5.0 之间。该值小于或等于 0.5 表示可接受的性能降低。过去，平均意见得分是通过让用户对呼叫质量进行评级（范围为 1 到 5）来计算得出的。在 Lync Server 中， Lync Server 会使用一组算法来预测用户对呼叫进行评级的方式。</p>
<p>高性能降低值可能是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器或终结点超载造成的，从而导致音频失真或丢失。</p></td>
</tr>
<tr class="odd">
<td><p><strong>数据包丢失</strong></p></td>
<td><p>否</p></td>
<td><p>平均 RTP 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时将发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的，从而导致音频失真或丢失。</p></td>
</tr>
<tr class="even">
<td><p><strong>抖动(毫秒)</strong></p></td>
<td><p>否</p></td>
<td><p>在 RTP 数据包到达之间检测到的平均抖动率。（抖动是针对呼叫的“不稳定性”的度量。）高抖动值通常是由拥塞或媒体服务器超载造成的，从而导致音频失真或丢失。</p></td>
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


### 媒体质量摘要报告指标：视频呼叫摘要

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
<td><p><strong>呼叫量(无线呼叫)</strong></p></td>
<td><p>否</p></td>
<td><p>使用了无线连接的呼叫的总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>呼叫量(VPN 呼叫)</strong></p></td>
<td><p>否</p></td>
<td><p>使用了 VPN 连接的呼叫的总数。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫量(外部呼叫)</strong></p></td>
<td><p>否</p></td>
<td><p>使用了外部连接（即内部网络外部的连接）的呼叫的总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>平均比特率(Kb/s)</strong></p></td>
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
<td><p><strong>入站低帧速率(%)</strong></p></td>
<td><p>否</p></td>
<td><p>传入视频的比特率较低的呼叫的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>客户端健康状态百分比</strong></p></td>
<td><p></p></td>
<td><p>指示呼叫期间客户端设备的相对健康状态。</p></td>
</tr>
</tbody>
</table>


### 媒体质量摘要报告指标：应用程序共享呼叫摘要

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
<td><p><strong>呼叫量(无线呼叫)</strong></p></td>
<td><p>否</p></td>
<td><p>使用了无线连接的呼叫的总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>呼叫量(VPN 呼叫)</strong></p></td>
<td><p>否</p></td>
<td><p>使用了 VPN 连接的呼叫的总数。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫量(外部呼叫)</strong></p></td>
<td><p>否</p></td>
<td><p>使用了外部连接（即内部网络外部的连接）的呼叫的总数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>抖动(毫秒)</strong></p></td>
<td><p>否</p></td>
<td><p>在 RTP 数据包到达之间检测到的平均抖动率。（抖动是针对呼叫的“不稳定性”的度量。）高抖动值通常是由拥塞或媒体服务器超载造成的，从而导致音频失真或丢失。</p></td>
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

