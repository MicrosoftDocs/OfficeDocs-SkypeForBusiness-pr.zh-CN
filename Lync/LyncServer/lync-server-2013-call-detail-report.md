---
title: Lync Server 2013：呼叫详情报告
TOCTitle: 呼叫详情报告
ms:assetid: 38862e35-3fec-41b9-a035-0b301942d446
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg558637(v=OCS.15)
ms:contentKeyID: 49312535
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的呼叫详情报告

 

_**上一次修改主题：** 2015-03-09_

呼叫详情报告提供单个呼叫的详细信息；该报告包括 Lync Server 收集的几乎所有用户体验质量指标，并分为以下报告章节：

  - 呼叫信息

  - 呼叫者设备和信号指标

  - 被叫方设备和信号指标

  - 呼叫者客户端事件

  - 被叫方客户端事件

  - 音频流（呼叫者到被叫方）

  - 视频流（呼叫者到被叫方）

  - 视频流（被叫方到呼叫者）

  - 视频流（被叫方到呼叫者）

请记住，您在指定报告上看到的类别和指标取决于两个因素：会话类型和会话中使用的终结点类型。例如，纯音频呼叫不会报告视频流的相关指标；这是因为该呼叫没有视频流。同样，您的报告可能列出了呼叫者统计信息，而没有列出被叫方统计信息。这通常是因为被叫方没有使用符合 SIP 的设备。终结点负责在呼叫结束时报告统计信息；但是，移动电话（不了解有关 SIP 或 SIP 统计信息的任何情况）无法报告此类信息。如果您呼叫某人且此人用其移动电话应答您的呼叫，则呼叫结束时您将不会获得来自该移动电话的报告。

呼叫详情报告在您尝试准确确定指定呼叫遇到媒体质量问题的原因时最为有用。

## 访问呼叫详情报告

可以从下列任意报告中访问呼叫详情报告：

  - [Lync Server 2013 中的位置报告](lync-server-2013-location-report.md)（单击“呼叫量”或“质量欠佳的呼叫百分比”指标）

  - [Lync Server 2013 中的媒体质量摘要报告](lync-server-2013-media-quality-summary-report.md)（单击“呼叫量”或“质量欠佳的呼叫百分比”指标）

  - [媒体质量比较报告](lync-server-2013-media-quality-comparison-report.md)（单击[Lync Server 2013 中的呼叫列表报告](lync-server-2013-call-list-report.md)，然后单击“详细信息”指标）。

  - [Lync Server 2013 中的服务器性能报告](lync-server-2013-server-performance-report.md)（单击“呼叫量”或“质量欠佳的呼叫百分比”指标）

  - [Lync Server 2013 中的呼叫列表报告](lync-server-2013-call-list-report.md)（单击“详细信息”指标）

通过单击下列任一指标可以从呼叫详情报告中访问 [Lync Server 2013 中的设备报告](lync-server-2013-device-report.md)：

  - 捕获设备

  - 呈现设备

您还可以通过单击“A/V 边缘服务器”指标访问服务器媒体质量趋势报告。

## 充分利用呼叫详情报告

呼叫详情报告通常包括 250 多个不同的指标，其中包括麦克风时间戳偏移、低 SNR 时间和近端回声时间等项目。如果您不记得所有这些指标实际度量的内容，请尝试将鼠标指针置于指标标签上方；通常，将显示描述该指标的工具提示。

如果查找指标时遇到问题，请在搜索框中键入指标标签的部分内容，然后单击“查找”。例如，如果您无法找到“低 SNR 时间”指标，请在搜索框中键入“SNR”，然后单击“查找”。

请注意，报告仅跟踪关于呼叫的信息。不记录呼叫本身。

## 筛选器

无。您无法筛选呼叫详情报告。

## 指标

下表列出了每个呼叫的呼叫详情报告中提供的信息。

### 呼叫详情报告指标

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
<td><p><strong>呼叫者 PAI</strong></p></td>
<td><p>否</p></td>
<td><p>发起呼叫的用户的 P-Asserted-Identity。P-Asserted-Identity 用于传达受信任网络内用户经验证的身份。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫者 URI</strong></p></td>
<td><p>否</p></td>
<td><p>发起呼叫的用户的 SIP 地址。</p></td>
</tr>
<tr class="odd">
<td><p><strong>呼叫者终结点</strong></p></td>
<td><p>否</p></td>
<td><p>用于发出呼叫的设备。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫者用户代理</strong></p></td>
<td><p>否</p></td>
<td><p>发出呼叫的设备上使用的软件。</p></td>
</tr>
<tr class="odd">
<td><p><strong>呼叫开始</strong></p></td>
<td><p>否</p></td>
<td><p>最初发出呼叫的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>中介服务器旁路呼叫</strong></p></td>
<td><p>否</p></td>
<td><p>指示呼叫是否在不通过中介服务器的情况下连接到 PSTN 语音网关或合格的 IP-PBX。</p></td>
</tr>
<tr class="odd">
<td><p><strong>呼叫者 OS</strong></p></td>
<td><p>否</p></td>
<td><p>呼叫者计算机的操作系统。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫者 CPU</strong></p></td>
<td><p>否</p></td>
<td><p>发起呼叫的用户的计算机中安装的 CPU。</p></td>
</tr>
<tr class="odd">
<td><p><strong>呼叫者 CPU 内核数</strong></p></td>
<td><p>否</p></td>
<td><p>发起呼叫的人员使用的计算机中的处理器数量。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫者 CPU 速度</strong></p></td>
<td><p>否</p></td>
<td><p>发起呼叫的人员使用的计算机的 CPU 时钟频率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>呼叫者 CPU 虚拟化</strong></p></td>
<td><p>否</p></td>
<td><p>发起呼叫的人员使用的计算机上使用的虚拟化（如果有）。</p></td>
</tr>
<tr class="even">
<td><p><strong>被叫方 PAI</strong></p></td>
<td><p>否</p></td>
<td><p>受邀加入呼叫的用户的 P-Asserted-Identity。P-Asserted-Identity 用于传达受信任网络内用户经验证的身份。</p></td>
</tr>
<tr class="odd">
<td><p><strong>被叫方 URI</strong></p></td>
<td><p>否</p></td>
<td><p>被叫的用户的 SIP 地址。</p></td>
</tr>
<tr class="even">
<td><p><strong>被叫方终结点</strong></p></td>
<td><p>否</p></td>
<td><p>用于接收呼叫的设备。</p></td>
</tr>
<tr class="odd">
<td><p><strong>被叫方用户代理</strong></p></td>
<td><p>否</p></td>
<td><p>接收呼叫的设备上使用的软件。</p></td>
</tr>
<tr class="even">
<td><p><strong>持续时间</strong></p></td>
<td><p>否</p></td>
<td><p>呼叫的时长。</p></td>
</tr>
<tr class="odd">
<td><p><strong>媒体旁路警告标记</strong></p></td>
<td><p>否</p></td>
<td><p>在绕过中介服务器时发出的警告。</p></td>
</tr>
<tr class="even">
<td><p><strong>被叫方 OS</strong></p></td>
<td><p>否</p></td>
<td><p>被叫用户的计算机的操作系统。</p></td>
</tr>
<tr class="odd">
<td><p><strong>被叫方 CPU</strong></p></td>
<td><p>否</p></td>
<td><p>被叫用户的计算机中安装的 CPU。</p></td>
</tr>
<tr class="even">
<td><p><strong>被叫方内核数</strong></p></td>
<td><p>否</p></td>
<td><p>被叫人员使用的计算机中的处理器数量。</p></td>
</tr>
<tr class="odd">
<td><p><strong>被叫方 CPU 速度</strong></p></td>
<td><p>否</p></td>
<td><p>被叫人员使用的计算机的 CPU 时钟频率。</p></td>
</tr>
<tr class="even">
<td><p><strong>被叫方 CPU 虚拟化</strong></p></td>
<td><p>否</p></td>
<td><p>被叫人员使用的计算机上使用的虚拟化（如果有）。</p></td>
</tr>
</tbody>
</table>

