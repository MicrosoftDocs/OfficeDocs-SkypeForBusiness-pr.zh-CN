---
title: AppSharingMetricsThreshold 表
TOCTitle: AppSharingMetricsThreshold 表
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205018(v=OCS.15)
ms:contentKeyID: 49313319
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# AppSharingMetricsThreshold 表

 

_**上一次修改主题：** 2015-12-08_

AppSharingMetricsThreshold 表包含用于应用程序共享的用户体验质量指标的最佳值和可接受的值。这些阈值用于确定是否应将应用程序共享体验归类为质量欠佳。

此表是在 Microsoft Lync Server 2013 中引入的。


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>列</strong></th>
<th><strong>数据类型</strong></th>
<th><strong>键/索引</strong></th>
<th><strong>详细信息</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>CallType</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>已发出的呼叫的类型。</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimitOptimal</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>应用程序共享的最佳带宽限制。默认值为 1000000。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthLimitAcceptable</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>应用程序共享的可接受带宽限制。默认值为 500000。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotalOptimal</strong></p></td>
<td><p>decimal(5.2)</p></td>
<td><p></p></td>
<td><p>用于归类应用程序共享质量的“已损坏”图块的最佳百分率。此值是共享方中未到达查看方的内容的百分比。当共享方丢弃图形源中的图块或 ASMCU 图块丢弃共享方中的图块时，内容可能被丢弃（或被损坏）。默认值为 11%。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentTotalAcceptable</strong></p></td>
<td><p>decimal(5.2)</p></td>
<td><p></p></td>
<td><p>用于归类应用程序共享质量的“已损坏”图块的可接受百分率。此值是共享方中未到达查看方的内容的百分比。当共享方丢弃图形源中的图块或 ASMCU 图块丢弃共享方中的图块时，内容可能被丢弃（或被损坏）。默认值为 36%。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalOptimal</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>此列不用于 Microsoft Lync Server 2013 中。</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalAcceptable</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>此列不用于 Microsoft Lync Server 2013 中。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensityOptimal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>此列不用于 Microsoft Lync Server 2013 中。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensityAcceptable</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>此列不用于 Microsoft Lync Server 2013 中。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>此列不用于 Microsoft Lync Server 2013 中。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>此列不用于 Microsoft Lync Server 2013 中。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverageOptimal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>应用程序共享中涉及的两个媒体终结点之间的相对单向延迟的最佳值。这是单跃点延迟度量。默认值为 1.0 秒。</p>
<p>此列是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverageAcceptable</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>应用程序共享中涉及的两个媒体终结点之间的相对单向延迟的最佳值。这是单跃点延迟度量。默认值为 1.75 秒。</p>
<p>此列是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyAverageOptimal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>查看会话持续时间内 AS 会议服务器中的平均 RDP 图块处理延迟的最佳值。此指标不涉及网络延迟。</p>
<p>高平均值反映了查看体验中的延迟较长。过载的会议服务器可能会遇到更长的平均延迟。默认值为 200 毫秒。</p>
<p>此列是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverageAcceptable</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>查看会话持续时间内 AS 会议服务器中的平均 RDP 图块处理延迟的可接受值。此指标不涉及网络延迟。</p>
<p>高平均值反映了查看体验中的延迟较长。过载的会议服务器可能会遇到更长的平均延迟。默认值为 200 毫秒。</p>
<p>此列是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
</tbody>
</table>

