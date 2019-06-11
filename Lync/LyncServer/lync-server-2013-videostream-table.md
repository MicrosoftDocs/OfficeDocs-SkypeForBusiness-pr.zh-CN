---
title: Lync Server 2013：VideoStream 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98e0ad3f7c18032dd903d2f8d1d41428ccc12cf9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a>Lync Server 2013 中的 VideoStream 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-12-13_

每条记录表示一个视频流。 一个视频媒体线通常包含两个视频流。


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
<td><p>datetime</p></td>
<td><p>Primary</p></td>
<td><p>从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表</a>引用的 R。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>媒体行内的唯一 ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoPayloadDescription</strong></p></td>
<td><p>smallint</p></td>
<td><p>外部、主要</p></td>
<td><p>负载说明。 有关详细信息, 请参阅<a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中的 PayloadDescription 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>实时控制协议 (RTCP) 统计信息的平均网络抖动。</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>视频会话期间的最大网络抖动。</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>从 RTCP 统计数据往返的时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>视频流的最大往返行程时间。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>十进制 (5, 4)</p></td>
<td><p> </p></td>
<td><p>通话期间平均数据包丢失速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>十进制 (5, 4)</p></td>
<td><p> </p></td>
<td><p>通话过程中观察到的最大数据包丢失。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>视频流的数据包计数 (实时传输协议、RTP)。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>视频流的带宽估计。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoResolution</strong></p></td>
<td><p>char (9)</p></td>
<td><p> </p></td>
<td><p>以像素为单位的视频分辨率 (以像素为单位) 乘以像素高度。 报告为字符串。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoBitRateAvg</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>视频流的平均比特率。</p></td>
</tr>
<tr class="even">
<td><p><strong>InboundVideoFrameRateAvg</strong></p></td>
<td><p>十进制 (9, 4)</p></td>
<td><p> </p></td>
<td><p>收到的视频帧速率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OutboundVideoFrameRateAvg</strong></p></td>
<td><p>十进制 (9, 4)</p></td>
<td><p> </p></td>
<td><p>已发送视频帧速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoBitRateMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>视频会话期间的最大视频比特率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoFrameLossRate</strong></p></td>
<td><p>十进制 (9, 4)</p></td>
<td><p> </p></td>
<td><p>丢失的视频帧总数的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoFEC</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>不可用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoLocalFrameLossPercentageAvg</strong></p></td>
<td><p>十进制 (9, 4)</p></td>
<td></td>
<td><p>丢失的视频帧总数的百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>CIFQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>以通用交换格式 (CIF) 分辨率表示的通话百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VGAQualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>以 VGA 分辨率表示的通话百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>HD720QualityRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>以 HD720 分辨率表示的通话百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>NoneDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>不带帧丢弃的通话持续时间百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>BDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>B 帧丢弃的通话持续时间百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>具有 BP 帧丢弃的通话持续百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>BPSPDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>带有 BPSP 帧丢弃的通话持续时间百分比。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BPSPIDropRatio</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>带有 BPSPI 帧丢弃的通话持续时间百分比。</p></td>
</tr>
<tr class="even">
<td><p><strong>封</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>接收接收方的数据流数据。</p></td>
</tr>
<tr class="odd">
<td><p><strong>出站</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>接收发件人端的数据流数据。</p></td>
</tr>
<tr class="even">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1表示流方向来自调用方的调用方。</p>
<p>0表示流方向来自被调用方的调用方。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>指示通话处于损失拥塞状态的时间百分比。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>指示由于网络数据包的延迟到达而导致的阻塞的调用百分比。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>表示呼叫竞争网络资源的时间百分比。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>在通话期间测量的最小带宽估计量。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>在通话期间测量的最大带宽估计量。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>在通话过程中测量的带宽估计的标准偏差。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通话期间测量的平均估计带宽量。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>LowBandwidthForMultiview</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>终结点确定网络连接无法支持多种显示视频的调用的百分比。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>单向延迟的总金额。 相对单向延迟测量客户端与服务器之间的延迟。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>单向延迟的平均量。 相对单向延迟测量客户端与服务器之间的延迟。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>单向延迟的最大值。 相对单向延迟测量客户端与服务器之间的延迟。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>总单向爆发次数。 "Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 数据流处于不可预知的突发流量。 此指标测量客户端与服务器之间的数据流。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>总单向脉冲密度。 "Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 数据流处于不可预知的突发流量。 此指标测量客户端与服务器之间的数据流。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>总的单向脉冲持续时间。 "Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 数据流处于不可预知的突发流量。 此指标测量客户端与服务器之间的数据流。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>总的单向间隔发生次数。 "Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 其数据流可预料的猝发。间隙表示这些猝发之间的延迟。 此指标测量客户端与服务器之间的数据流。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>总单向间距密度。 "Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 其数据流可预料的猝发。间隙表示这些猝发之间的延迟。 此指标测量客户端与服务器之间的数据流。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>总的单间隔持续时间。 "Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 其数据流可预料的猝发。间隙表示这些猝发之间的延迟。 此指标测量客户端与服务器之间的数据流。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPacketLossRate</strong></p></td>
<td><p>十进制 (9, 4)</p></td>
<td></td>
<td><p>视频数据包丢失的速率。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>VideoAllocateBWAvg</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>为视频分配的平均带宽量。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendCodecTypes</strong></p></td>
<td><p>smallint</p></td>
<td><p>外表</p></td>
<td><p>发件人使用的视频编解码器类型。 有关详细信息, 请参阅<a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表</a>。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>发件人使用的分辨率宽度。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>发件人使用的分辨率高度。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>发件人使用的平均视频帧速率传输。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>发件人的最大比特率。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>发件人的平均比特率。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>发件人使用的视频流的最大数量。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvCodecTypes</strong></p></td>
<td><p>smallint</p></td>
<td><p>外表</p></td>
<td><p>接收方使用的视频代码。 有关详细信息, 请参阅<a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表</a>。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvResolutionWidth</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收器使用的分辨率宽度。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvResolutionHeight</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收方使用的分辨率高度。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvFrameRateAverage</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>接收方使用的平均视频帧速率。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvBitRateMaximum</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收方的最大比特率。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvBitRateAverage</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收方的平均比特率。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收方的最大视频流。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvVideoStreamsMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收方的最小视频流。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvVideoStreamsMode</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>接收方的视频模式 (例如, 库或单流)。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoPostFECPLR</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>已应用转发纠错后的数据包丢失率。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DynamicCapabilityPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>动态功能标志处于活动状态的时间百分比。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>ResolutionMin</strong></p></td>
<td><p>char (9)</p></td>
<td></td>
<td><p>通话过程中测量的最低分辨率。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowBitRateCallPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>低于低比特率阈值的通话百分比 (70 千位/秒)。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>LowFrameRateCallPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>低于低帧速率阈值 (每秒7.5 帧, 入站) 的通话百分比。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>LowResolutionCallPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>以最低分辨率发生的通话的百分比。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>DurationSeconds</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>通话长度 (以秒为单位)。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>IsAggregatedData</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>指示数据是否已从多个调用聚合。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

