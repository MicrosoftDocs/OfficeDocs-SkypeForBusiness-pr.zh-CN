---
title: Lync Server 2013：AudioStream 表
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
ms.openlocfilehash: 97a8015bce118991b21b541faf588dd4d76ac784
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a>Lync Server 2013 中的 AudioStream 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-02_

每条记录表示一个音频流。 一个音频媒体行通常包含两个音频流。


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
<td><p>从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</p></td>
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
<td><p><strong>JitterInterArrival</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>实时控制协议（RTCP）统计信息的平均网络抖动。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>通话期间网络抖动的最大值。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketLossRate</strong></p></td>
<td><p>十进制（5，4）</p></td>
<td><p> </p></td>
<td><p>通话期间平均数据包丢失速率。</p></td>
</tr>
<tr class="even">
<td><p><strong>PacketLossRateMax</strong></p></td>
<td><p>十进制（5，4）</p></td>
<td><p> </p></td>
<td><p>通话过程中观察到的最大数据包丢失。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstDensity</strong></p></td>
<td><p>十进制（9，4）</p></td>
<td><p> </p></td>
<td><p>通话期间出现猝发损失期间的数据包丢失的平均密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>通话期间出现猝发损失期间的数据包丢失的平均持续时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BurstGapDensity</strong></p></td>
<td><p>十进制（9，4）</p></td>
<td><p> </p></td>
<td><p>出现猝发数据包丢失之间的平均数据包损失的平均密度。</p></td>
</tr>
<tr class="even">
<td><p><strong>BurstGapDuration</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>爆发数据包损失之间的平均持续时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>PacketUtilization</strong></p></td>
<td><p>整形</p></td>
<td><p> </p></td>
<td><p>音频流的数据包计数。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEst</strong></p></td>
<td><p>整形</p></td>
<td><p> </p></td>
<td><p>音频流的带宽估计。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationAvg</strong></p></td>
<td><p>十进制（3，2）</p></td>
<td><p> </p></td>
<td><p>整个通话的网络 MOS 降级。 范围为0.0 到5.0。 此指标显示由于抖动和数据包丢失，网络 MOS 的减少量。 对于可接受的质量，它应小于0.5。</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationMax</strong></p></td>
<td><p>十进制（3，2）</p></td>
<td><p> </p></td>
<td><p>通话期间最大网络 MOS 性能下降。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DegradationJitterAvg</strong></p></td>
<td><p>十进制（3，2）</p></td>
<td><p> </p></td>
<td><p>由抖动导致的网络 MOS 性能下降。</p></td>
</tr>
<tr class="even">
<td><p><strong>DegradationPacketLossAvg</strong></p></td>
<td><p>十进制（3，2）</p></td>
<td><p> </p></td>
<td><p>由于数据包丢失导致网络 MOS 性能下降。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioPayloadDescription</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>用于呼叫的音频编解码器，从 PayloadDescription 表中引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioSampleRate</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>音频流的采样率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RoundTrip</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>从 RTCP 统计数据往返的时间。 为获得可接受的质量，这应该小于100ms。</p></td>
</tr>
<tr class="even">
<td><p><strong>RoundTripMax</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>音频流的最大往返行程时间。</p></td>
</tr>
<tr class="odd">
<td><p><strong>OverallAvgNetworkMOS</strong></p></td>
<td><p>十进制（3，2）</p></td>
<td><p> </p></td>
<td><p>通话的平均宽带网络 MOS。 此指标取决于所使用的数据包丢失、抖动和编解码器。 范围为 [1.0 到 5.0]。</p></td>
</tr>
<tr class="even">
<td><p><strong>OverallMinNetworkMOS</strong></p></td>
<td><p>十进制（3，2）</p></td>
<td><p> </p></td>
<td><p>通话的最低宽带网络 MOS。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SendListenMOS</strong></p></td>
<td><p>十进制（3，2）</p></td>
<td><p> </p></td>
<td><p>平均预测宽带的 MOS 分数，包括语音级别、噪声级别和捕获设备特征。</p></td>
</tr>
<tr class="even">
<td><p><strong>SendListenMOSMin</strong></p></td>
<td><p>十进制（3，2）</p></td>
<td><p> </p></td>
<td><p>通话的最低 SendListenMOS。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RecvListenMOS</strong></p></td>
<td><p>十进制（3，2）</p></td>
<td><p> </p></td>
<td><p>平均预测宽带从网络接收的音频的 MOS 分数，包括语音级别、噪音级别、编解码器、网络条件和捕获设备特征。</p></td>
</tr>
<tr class="even">
<td><p><strong>RecvListenMOSMin</strong></p></td>
<td><p>十进制（3，2）</p></td>
<td><p> </p></td>
<td><p>通话的最低 RecvListenMOS。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AudioFECUsed</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>指示是否已将音频 FEC 用于呼叫的标志。</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioConcealedSamplesAvg</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td></td>
<td><p>通过音频康复为典型示例生成的隐藏样本的平均比率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RatioStretchedSamplesAvg</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td></td>
<td><p>通过音频康复为典型示例生成的拉伸样本的平均比率。</p></td>
</tr>
<tr class="even">
<td><p><strong>RatioCompressedSamplesAvg</strong></p></td>
<td><p>十进制（5，2）</p></td>
<td></td>
<td><p>从音频修复到典型示例生成的压缩样本的平均比率。</p></td>
</tr>
<tr class="odd">
<td><p><strong>封</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>接收接收方的数据流数据。</p></td>
</tr>
<tr class="even">
<td><p><strong>出站</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>接收发件人端的数据流数据。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SenderIsCallerPAI</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1表示流方向从调用方到被调用方。</p>
<p>0表示流方向来自被调用方的调用方。</p></td>
</tr>
<tr class="even">
<td><p><strong>JitterInterArrivalSD</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>抖动到达时间的标准偏差。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConcealRatioMax</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>由 healer 隐藏的数据包的最大比率。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConcealRatioSD</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>由 healer 隐藏的数据包比率的标准偏差。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>HealerPacketDropRatio</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>Healer 丢弃的数据包与接收的总数据包数之比。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>HealerFECPacketUsedRatio</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>与接收的总数据包数相比已使用的转发纠错数据包的比率。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MaxCompressedSamples</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>由 healer 压缩的音频数据包的最大数量。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>LossCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>指示通话处于损失拥塞状态的时间百分比。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DelayCongestionPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>指示由于网络数据包的延迟到达而导致的阻塞的调用百分比。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>ContentionDetectedPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>表示呼叫竞争网络资源的时间百分比。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstMin</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>在通话期间测量的最小带宽估计量。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstMax</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>在通话期间测量的最大带宽估计量。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>BandwidthEstStdDev</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>在通话过程中测量的带宽估计的标准偏差。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>BandwidthEstAvge</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>通话期间测量的平均估计带宽量。</p>
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
<td><p>总单向爆发次数。 "Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，数据流处于不可预知的突发流量。 此指标测量客户端与服务器之间的数据流。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayBurstDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>总单向脉冲密度。 "Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，数据流处于不可预知的突发流量。 此指标测量客户端与服务器之间的数据流。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayBurstDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>总的单向脉冲持续时间。 "Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，数据流处于不可预知的突发流量。 此指标测量客户端与服务器之间的数据流。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapOccurrences</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>总的单向间隔发生次数。 "Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，其数据流可预料的猝发。间隙表示这些猝发之间的延迟。 此指标测量客户端与服务器之间的数据流。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>RelativeOneWayGapDensity</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>总单向间距密度。 "Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，其数据流可预料的猝发。间隙表示这些猝发之间的延迟。 此指标测量客户端与服务器之间的数据流。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>RelativeOneWayGapDuration</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>总的单间隔持续时间。 "Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，其数据流可预料的猝发。间隙表示这些猝发之间的延迟。 此指标测量客户端与服务器之间的数据流。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>DecodeStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>解码为立体声的通话百分比。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AecRenderStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>通过音响回声抵消器呈现为立体声的通话百分比。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>AudioPostFECPLR</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>已应用转发纠错后的数据包丢失率。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>EncodeStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>编码为立体声的通话百分比。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>AecCaptureStereoPercent</strong></p></td>
<td><p>float</p></td>
<td></td>
<td><p>通过音响回声抵消器以立体声形式捕获的通话百分比。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

