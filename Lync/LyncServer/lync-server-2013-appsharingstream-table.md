---
title: AppSharingStream 表
TOCTitle: AppSharingStream 表
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204808(v=OCS.15)
ms:contentKeyID: 49312542
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# AppSharingStream 表

 

_**上一次修改主题：** 2015-03-09_

AppSharingStream 表包含用于应用程序共享的网络流的用户体验质量指标。此表是在 Microsoft Lync Server 2013 中引入的。


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
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>dateTime</p></td>
<td><p>主、外</p></td>
<td><p>会话开始的日期和时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主、外</p></td>
<td><p>用于区分在相同日期和时间开始的会话的顺序标识符。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主、外</p></td>
<td><p>表示在呼叫中使用的视频行的类型。允许的值包括：</p>
<ul>
<li><p>0 - 音频</p></li>
<li><p>1 - 视频</p></li>
<li><p>2 – 全景视频</p></li>
<li><p>3 - 应用程序/桌面共享</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>应用程序共享流的唯一标识符。</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>在 RTP 数据包到达之间检测到的平均抖动率。（抖动是针对呼叫的“不稳定性”的度量。）高抖动值通常是由拥塞或媒体服务器超载造成的，从而导致音频失真或丢失。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>在 RTP 数据包到达之间检测到的最大抖动率。（抖动是针对呼叫的“不稳定性”的度量。）高抖动值通常是由拥塞或媒体服务器超载造成的，从而导致音频失真或丢失。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>实时传输协议数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 200 毫秒被视为质量可接受。</p>
<p>高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>实时传输协议数据包来往于另一个终结点所需的最大时间量（以毫秒为单位）。来回行程的时间小于或等于 200 毫秒被视为质量可接受。</p>
<p>高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>平均实时传输协议 (RTP) 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时，即发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。数据包丢失通常导致音频失真或丢失。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>最大实时传输协议 (RTP) 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时，即发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。数据包丢失通常导致音频失真或丢失。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>发送的数据包数。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>在会话末尾可用的单向带宽的估计值。以每秒的位数的形式报告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppSharingPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>应用程序共享负载的描述。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>单向延迟的总量。相对单向延迟用于度量客户端和服务器之间的延迟。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>单向延迟的平均量。相对单向延迟用于度量客户端和服务器之间的延迟。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>单向延迟的最大量。相对单向延迟用于度量客户端和服务器之间的延迟。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>单向突发总发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>单向突发总密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>单向突发总持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>单向间隙总发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>单向间隙总密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>单向间隙总持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ApplicationSharingType</strong></p></td>
<td><p>varChar(256)</p></td>
<td><p></p></td>
<td><p>应用程序角色（共享者或查看者）和内容类型。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>远程桌面协议 (RDP) 图块的总处理时间。总时间量越大，查看体验的延迟就越长。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>远程桌面协议 (RDP) 图块的平均处理时间。总时间量越大，查看体验的延迟就越长。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>远程桌面协议 (RDP) 图块的最大处理时间。总时间量越大，查看体验的延迟就越长。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>远程桌面协议 (RDP) 图块的处理时间中的突发发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>远程桌面协议 (RDP) 图块的处理时间中的突发密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>远程桌面协议 (RDP) 图块的处理时间中的突发持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>远程桌面协议 (RDP) 图块的处理时间中的间隙发生次数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RDPTileProcessingLatencyGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>远程桌面协议 (RDP) 图块的处理时间中的间隙密度。间隙密度越低，查看体验就越佳。</p></td>
</tr>
<tr class="even">
<td><p><strong>RDPTileProcessingLatencyGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>远程桌面协议 (RDP) 图块的处理时间中的间隙持续时间。间隙持续时间越短，查看体验就越佳。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>图块的总捕获率（以每秒的图块数为单位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>图块的平均捕获率（以每秒的图块数为单位）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>图块的最大捕获率（以每秒的图块数为单位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>图块的捕获率的突发发生次数（以每秒的图块数为单位）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>图块的捕获率的突发密度（以每秒的图块数为单位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>图块的捕获率的突发持续时间（以每秒的图块数为单位）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>图块的捕获率的间隙发生次数（以每秒的图块数为单位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>CaptureTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>图块的捕获率的间隙密度（以每秒的图块数为单位）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CaptureTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>图块的捕获率的间隙持续时间（以每秒的图块数为单位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的总百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的平均百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的最大百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的突发发生次数。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的突发密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的突发持续时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的间隙发生次数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SpoiledTilePercentGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的间隙密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>SpoiledTilePercentGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的间隙持续时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>从图形源擦除的总帧数。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>从图形源擦除的平均帧数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>从图形源擦除的最大帧数。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>从图形源擦除的帧数的突发发生次数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>从图形源擦除的帧数的突发密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>从图形源擦除的帧数的突发持续时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>从图形源擦除的帧数的间隙发生次数。</p></td>
</tr>
<tr class="even">
<td><p><strong>ScrapingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>从图形源擦除的帧数的间隙密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ScrapingFrameRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>从图形源擦除的帧数的间隙持续时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>查看者收到的总传入帧速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>查看者收到的平均传入帧速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>查看者收到的最大传入图块速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>查看者收到的传入图块速率的突发发生次数。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>查看者收到的传入图块速率的突发密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>查看者收到的传入图块速率的突发持续时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>查看者收到的传入图块速率的间隙发生次数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>查看者收到的传入图块速率的间隙密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>查看者收到的传入图块速率的间隙持续时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>查看者收到的总传入帧速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>查看者收到的平均传入帧速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>查看者收到的最大传入帧速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>查看者收到的传入帧速率的突发发生次数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>查看者收到的传入帧速率的突发密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>查看者收到的传入帧速率的突发持续时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>查看者收到的传入帧速率的间隙发生次数。</p></td>
</tr>
<tr class="even">
<td><p><strong>IncomingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>查看者收到的传入帧速率的间隙密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IncomingFrameRateDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>查看者收到的传入帧速率的间隙持续时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>发送者的总传出图块速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>发送者的平均传出图块速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>发送者的最大传出图块速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>发送者的传出图块速率的突发发生次数。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>发送者的传出图块速率的突发密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>发送者的传出图块速率的突发持续时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>发送者的传出图块速率的间隙发生次数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingTileRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>发送者的传出图块速率的间隙密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingTileRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>发送者的传出图块速率的间隙持续时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateTotal</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>发送者的总传出帧速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>发送者的平均传出帧速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateMax</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>发送者的最大传出帧速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>发送者的传出帧速率的突发发生次数。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateBurstDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>发送者的传出帧速率的突发密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateBurstDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>发送者的传出帧速率的突发持续时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>发送者的传出帧速率的间隙发生次数。</p></td>
</tr>
<tr class="even">
<td><p><strong>OutgoingFrameRateGapDensity</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>发送者的传出帧速率的间隙密度。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutgoingFrameRateGapDuration</strong></p></td>
<td><p>float</p></td>
<td><p></p></td>
<td><p>发送者的传出帧速率的间隙持续时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>AverageRectangleHeight</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>平均视频分辨率高度（以像素为单位）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AverageRectangleWidth</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>平均视频分辨率宽度（以像素为单位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>Inbound</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>入站传输的平均帧速率（以每秒帧数为单位）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Outbound</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>出站传输的平均帧速率（以每秒帧数为单位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>1 表示流方向是从呼叫者到被叫方。</p>
<p>0 表示流方向是从被叫方到呼叫者。</p></td>
</tr>
</tbody>
</table>

