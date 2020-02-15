---
title: Lync Server 2013： AudioStream 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 44f41dc95e1c7c39a0c9c2cc4dd0a3a2462083e7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044574"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a>Lync Server 2013 中的 AudioStream 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-02_

每个记录表示一个音频流。 一个音频媒体行通常包含两个音频流。


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
<th><strong>Details</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>StreamID</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>媒体行中的唯一 ID。</p></td>
</tr>
<tr class="odd">
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>实时控制协议 (RTCP) 统计信息中的平均网络抖动。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>呼叫期间的最大网络抖动。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>decimal （5，4）</p></td>
<td><p> </p></td>
<td><p>呼叫期间的平均数据包丢失率。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>decimal （5，4）</p></td>
<td><p> </p></td>
<td><p>呼叫期间观测到的数据包丢失最大值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstDensity</strong></p></td>
<td><p>小数（9，4）</p></td>
<td><p> </p></td>
<td><p>呼叫期间出现猝发损失期间的数据包丢失的平均密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>呼叫期间出现猝发损失期间的数据包丢失的平均持续时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstGapDensity</strong></p></td>
<td><p>小数（9，4）</p></td>
<td><p> </p></td>
<td><p>在出现猝发数据包丢失之间间隔期间的数据包丢失的平均密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstGapDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>猝发数据包丢失间隔的平均持续时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>音频流的数据包计数。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>Int</p></td>
<td><p> </p></td>
<td><p>音频流的带宽预估。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationAvg</strong></p></td>
<td><p>decimal （3，2）</p></td>
<td><p> </p></td>
<td><p>整个呼叫的网络 MOS 降级。 范围是0.0 到5.0。 此指标显示由于抖动和数据包丢失而导致网络 MOS 减少的量。 对于可接受的质量，它应小于0.5。</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationMax</strong></p></td>
<td><p>decimal （3，2）</p></td>
<td><p> </p></td>
<td><p>呼叫期间的最大网络 MOS 降级。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationJitterAvg</strong></p></td>
<td><p>decimal （3，2）</p></td>
<td><p> </p></td>
<td><p>由抖动引起的网络 MOS 性能下降。</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationPacketLossAvg</strong></p></td>
<td><p>decimal （3，2）</p></td>
<td><p> </p></td>
<td><p>因数据包丢失而导致的网络 MOS 降级。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td><p>对外</p></td>
<td><p>用于呼叫的音频编解码器，从 PayloadDescription 表中引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSampleRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>音频流的采样率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>工程</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>RTCP 统计信息中的来回行程时间。 为了获得可接受的质量，此数量应小于100毫秒。</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>音频流的最大来回行程时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OverallAvgNetworkMOS</strong></p></td>
<td><p>decimal （3，2）</p></td>
<td><p> </p></td>
<td><p>呼叫的平均宽带网络 MOS。 此指标取决于所使用的数据包丢失、抖动和编解码器。 范围为 [1.0 至 5.0]。</p></td>
</tr>
<tr class="even">
<td><p><strong>OverallMinNetworkMOS</strong></p></td>
<td><p>decimal （3，2）</p></td>
<td><p> </p></td>
<td><p>呼叫的最小宽带网络 MOS。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendListenMOS</strong></p></td>
<td><p>decimal （3，2）</p></td>
<td><p> </p></td>
<td><p>平均预测的宽带侦听音频发送的 MOS 分数，包括语音级别、噪声级别和捕获设备特征。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendListenMOSMin</strong></p></td>
<td><p>decimal （3，2）</p></td>
<td><p> </p></td>
<td><p>呼叫的最小 SendListenMOS。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvListenMOS</strong></p></td>
<td><p>decimal （3，2）</p></td>
<td><p> </p></td>
<td><p>平均预测宽带侦听从网络接收的音频的 MOS 分数，包括语音级别、噪音级别、编解码器、网络条件和捕获设备特征。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvListenMOSMin</strong></p></td>
<td><p>decimal （3，2）</p></td>
<td><p> </p></td>
<td><p>呼叫的最小 RecvListenMOS。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioFECUsed</strong></p></td>
<td><p>位</p></td>
<td></td>
<td><p>指示是否已对呼叫使用音频 FEC 的标志。</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioConcealedSamplesAvg</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td></td>
<td><p>通过音频康复对典型示例生成的隐藏样本的平均比率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RatioStretchedSamplesAvg</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td></td>
<td><p>由音频康复生成的一般示例中的延伸样本的平均比率。</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioCompressedSamplesAvg</strong></p></td>
<td><p>decimal （5，2）</p></td>
<td></td>
<td><p>由音频康复生成的压缩样本的平均比率到典型示例。</p></td>
</tr>
<tr class="odd">
<td><p><strong>进货</strong></p></td>
<td><p>位</p></td>
<td><p> </p></td>
<td><p>接收接收器端的数据流数据。</p></td>
</tr>
<tr class="even">
<td><p><strong>出站</strong></p></td>
<td><p>位</p></td>
<td><p> </p></td>
<td><p>接收发件人端上的数据流数据。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>位</p></td>
<td><p> </p></td>
<td><p>1表示流方向从呼叫者到被叫方。</p>
<p>0 表示流方向是从被叫方到呼叫者。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalSD</strong></p></td>
<td><p>点数</p></td>
<td></td>
<td><p>抖动到达时间的标准偏差。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConcealRatioMax</strong></p></td>
<td><p>点数</p></td>
<td></td>
<td><p>由修复程序隐藏的数据包的最大比率。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConcealRatioSD</strong></p></td>
<td><p>点数</p></td>
<td></td>
<td><p>修复程序隐藏的数据包比率的标准偏差。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>HealerPacketDropRatio</strong></p></td>
<td><p>点数</p></td>
<td></td>
<td><p>修复程序丢弃的数据包与接收的数据包总数的比率。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>HealerFECPacketUsedRatio</strong></p></td>
<td><p>点数</p></td>
<td></td>
<td><p>与接收的数据包总数相比使用的转发错误纠正数据包的比率。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCompressedSamples</strong></p></td>
<td><p>点数</p></td>
<td></td>
<td><p>由修复程序压缩的最大音频数据包数。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>点数</p></td>
<td></td>
<td><p>指示呼叫处于丢失拥塞状态的时间百分比。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>点数</p></td>
<td></td>
<td><p>指示因网络数据包的延迟到达而导致拥塞的呼叫的百分比。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>点数</p></td>
<td></td>
<td><p>指示呼叫竞争网络资源的时间百分比。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>在呼叫过程中测量的最小带宽估计量。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>在呼叫过程中测量的最大带宽估计量。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>在呼叫过程中测量的带宽估计的标准偏差。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>呼叫期间衡量的平均带宽估计量。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayTotal</strong></p></td>
<td><p>点数</p></td>
<td></td>
<td><p>单向延迟的总量。相对单向延迟用于度量客户端和服务器之间的延迟。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayAverage</strong></p></td>
<td><p>点数</p></td>
<td></td>
<td><p>单向延迟的平均量。相对单向延迟用于度量客户端和服务器之间的延迟。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayMax</strong></p></td>
<td><p>点数</p></td>
<td></td>
<td><p>单向延迟的最大量。相对单向延迟用于度量客户端和服务器之间的延迟。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>单向突发总发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>点数</p></td>
<td></td>
<td><p>单向突发总密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>点数</p></td>
<td></td>
<td><p>单向突发总持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>单向间隙总发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>点数</p></td>
<td></td>
<td><p>单向间隙总密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>点数</p></td>
<td></td>
<td><p>单向间隙总持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>DecodeStereoPercent</strong></p></td>
<td><p>点数</p></td>
<td></td>
<td><p>被解码为立体声的呼叫的百分比。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AecRenderStereoPercent</strong></p></td>
<td><p>点数</p></td>
<td></td>
<td><p>通过音响回声消除器呈现为立体声的呼叫的百分比。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioPostFECPLR</strong></p></td>
<td><p>点数</p></td>
<td></td>
<td><p>应用转发错误纠正率后的数据包丢失率。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EncodeStereoPercent</strong></p></td>
<td><p>点数</p></td>
<td></td>
<td><p>编码为立体声的呼叫的百分比。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>AecCaptureStereoPercent</strong></p></td>
<td><p>点数</p></td>
<td></td>
<td><p>通过音响回声消除器以立体声形式捕获的呼叫的百分比。</p>
<p>本专栏是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

