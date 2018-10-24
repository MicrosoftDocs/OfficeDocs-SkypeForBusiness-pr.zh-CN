---
title: Lync Server 2013：呼叫列表报告
TOCTitle: 呼叫列表报告
ms:assetid: 9739f9f0-7a37-4844-91d5-f089d2011013
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg615020(v=OCS.15)
ms:contentKeyID: 49313671
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的呼叫列表报告

 

_**上一次修改主题：** 2015-03-09_

呼叫列表报告提供了针对您组织中发出和接收的单个呼叫的用户体验质量 (QoE) 指标。请注意，报告的实际指标将取决于您访问呼叫列表报告的方式。例如，如果从 [Lync Server 2013 中的设备报告](lync-server-2013-device-report.md)中打开报告，则您将看到与诸如以下内容的指标，设备报告中也报告了这些指标：

  - 呼叫者的麦克风

  - 呼叫者的扬声器

  - 被叫方的麦克风

  - 被叫方的扬声器

  - 语音切换时间比率

但是，如果您从 [Lync Server 2013 中的位置报告](lync-server-2013-location-report.md)中打开呼叫列表报告，则您将看不到任何这些指标；相反，您看到的指标类似于：

  - 来回行程(毫秒)

  - 性能降低(MOS)

  - 数据包丢失

  - 抖动(毫秒)

这些是在位置报告上报告的指标。但是，您始终能够从呼叫列表报告中单击“详细信息”指标来提供任何呼叫的完整 QoE 信息。

## 访问呼叫列表报告

可从以下任一报告访问呼叫列表报告：

  - [Lync Server 2013 中的位置报告](lync-server-2013-location-report.md)（通过单击呼叫量或质量欠佳的呼叫百分比指标）

  - [Lync Server 2013 中的设备报告](lync-server-2013-device-report.md)（通过单击呼叫量或质量欠佳的呼叫百分比指标）

  - [Lync Server 2013 中的媒体质量摘要报告](lync-server-2013-media-quality-summary-report.md)（通过单击呼叫量或质量欠佳的呼叫百分比指标）

  - [Lync Server 2013 中的服务器性能报告](lync-server-2013-server-performance-report.md)（通过单击呼叫量或质量欠佳的呼叫百分比指标）

从呼叫列表报告中，可通过单击详细信息指标来访问 [Lync Server 2013 中的呼叫详情报告](lync-server-2013-call-detail-report.md)。

## 最充分地利用呼叫列表报告

如果您记不住实际度量哪些呼叫列表报告指标（例如语音切换时间比率），请将鼠标指针悬停在指标标签的上方；这将显示一个工具提示，它为您简述了此指标。

## 筛选器

无。您无法筛选呼叫列表报告。

## 指标

下表列出了呼叫列表报告中提供的有关每个呼叫的信息。

### 呼叫列表报告指标

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
<td><p><strong>详细信息</strong></p></td>
<td><p>否</p></td>
<td><p>单击此项时，报告将显示有关呼叫的其他信息。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫者</strong></p></td>
<td><p>是</p></td>
<td><p>发起呼叫的人的 SIP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>被叫方</strong></p></td>
<td><p>是</p></td>
<td><p>被呼叫的人的 SIP 地址。</p></td>
</tr>
<tr class="even">
<td><p><strong>开始时间</strong></p></td>
<td><p>是</p></td>
<td><p>呼叫开始的日期和时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>结束时间</strong></p></td>
<td><p>是</p></td>
<td><p>呼叫结束的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫者用户代理</strong></p></td>
<td><p>是</p></td>
<td><p>发出呼叫的人的终结点使用的软件。</p></td>
</tr>
<tr class="odd">
<td><p><strong>被叫方用户代理</strong></p></td>
<td><p>是</p></td>
<td><p>被呼叫的人的终结点使用的软件。</p></td>
</tr>
<tr class="even">
<td><p><strong>来回行程(毫秒)</strong></p></td>
<td><p>是</p></td>
<td><p>实时传输协议 (RTP) 数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 100 毫秒被视为质量可接受。</p>
<p>高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</p></td>
</tr>
<tr class="odd">
<td><p><strong>性能降低(MOS)</strong></p></td>
<td><p>是</p></td>
<td><p>呼叫过程中遇到的性能降低的平均意见得分 (MOS) 的平均值。性能降低值的范围介于 0.0 和 5.0 之间。该值小于或等于 0.5 表示可接受的性能降低。过去，平均意见得分是通过让用户对呼叫质量进行评级（范围为 1 到 5）来计算得出的。在 Lync Server 中， Lync Server 会使用一组算法来预测用户对呼叫进行评级的方式。</p>
<p>高性能降低值可能是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器或终结点超载造成的，从而导致音频失真或丢失。</p></td>
</tr>
<tr class="even">
<td><p><strong>数据包丢失</strong></p></td>
<td><p>是</p></td>
<td><p>平均 RTP 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时将发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的，从而导致音频失真或丢失。</p></td>
</tr>
<tr class="odd">
<td><p><strong>抖动</strong></p></td>
<td><p>是</p></td>
<td><p>在 RTP 数据包到达之间检测到的平均抖动率。（抖动是针对呼叫的“不稳定性”的度量。）高抖动值通常是由拥塞或媒体服务器超载造成的，从而导致音频失真或丢失。</p></td>
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
<tr class="odd">
<td><p><strong>连接</strong></p></td>
<td><p>是</p></td>
<td><p>无线通信链路的类型。通常，这是以下选项之一：</p>
<ul>
<li><p>中继</p></li>
<li><p>直接</p></li>
</ul></td>
</tr>
</tbody>
</table>

