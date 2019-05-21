---
title: AudioStream 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: 每条记录表示一个音频流。 一个音频媒体行通常包含两个音频流。
ms.openlocfilehash: eae96b08f3a365288f48b7a68c75d3fd9114107d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295046"
---
# <a name="audiostream-table"></a>AudioStream 表
 
每条记录表示一个音频流。 一个音频媒体行通常包含两个音频流。
  
|列|数据类型|键/索引|详细信息|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)中引用。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)中引用。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)中引用。  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |媒体行内的唯一 ID。  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |实时控制协议 (RTCP) 统计信息的平均网络抖动。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |通话期间网络抖动的最大值。  <br/> |
|**PacketLossRate** <br/> |十进制 (5, 4)  <br/> | <br/> |通话期间平均数据包丢失速率。  <br/> |
|**PacketLossRateMax** <br/> |十进制 (5, 4)  <br/> | <br/> |通话过程中观察到的最大数据包丢失。  <br/> |
|**BurstDensity** <br/> |十进制 (9, 4)  <br/> | <br/> |通话期间出现猝发损失期间的数据包丢失的平均密度。  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |通话期间出现猝发损失期间的数据包丢失的平均持续时间。  <br/> |
|**BurstGapDensity** <br/> |十进制 (9, 4)  <br/> | <br/> |出现猝发数据包丢失之间的平均数据包损失的平均密度。  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |爆发数据包损失之间的平均持续时间。  <br/> |
|**PacketUtilization** <br/> |整形  <br/> | <br/> |音频流的数据包计数。  <br/> |
|**BandwidthEst** <br/> |整形  <br/> | <br/> |音频流的带宽估计。  <br/> |
|**DegradationAvg** <br/> |十进制 (3, 2)  <br/> | <br/> |整个通话的网络 MOS 降级。 范围为0.0 到5.0。 此指标显示由于抖动和数据包丢失, 网络 MOS 的减少量。 对于可接受的质量, 它应小于0.5。  <br/> |
|**DegradationMax** <br/> |十进制 (3, 2)  <br/> | <br/> |通话期间最大网络 MOS 性能下降。  <br/> |
|**DegradationJitterAvg** <br/> |十进制 (3, 2)  <br/> | <br/> |由抖动导致的网络 MOS 性能下降。  <br/> |
|**DegradationPacketLossAvg** <br/> |十进制 (3, 2)  <br/> | <br/> |由于数据包丢失导致网络 MOS 性能下降。  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |外表  <br/> |用于呼叫的音频编解码器, 从 PayloadDescription 表中引用。  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |音频流的采样率。  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |从 RTCP 统计数据往返的时间。 为获得可接受的质量, 这应该小于100ms。  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |音频流的最大往返行程时间。  <br/> |
|**OverallAvgNetworkMOS** <br/> |十进制 (3, 2)  <br/> | <br/> |通话的平均宽带网络 MOS。 此指标取决于所使用的数据包丢失、抖动和编解码器。 范围为 [1.0 到 5.0]。  <br/> |
|**OverallMinNetworkMOS** <br/> |十进制 (3, 2)  <br/> | <br/> |通话的最低宽带网络 MOS。  <br/> |
|**SendListenMOS** <br/> |十进制 (3, 2)  <br/> | <br/> |平均预测宽带的 MOS 分数, 包括语音级别、噪声级别和捕获设备特征。  <br/> |
|**SendListenMOSMin** <br/> |十进制 (3, 2)  <br/> | <br/> |通话的最低 SendListenMOS。  <br/> |
|**RecvListenMOS** <br/> |十进制 (3, 2)  <br/> | <br/> |平均预测宽带从网络接收的音频的 MOS 分数, 包括语音级别、噪音级别、编解码器、网络条件和捕获设备特征。  <br/> |
|**RecvListenMOSMin** <br/> |十进制 (3, 2)  <br/> | <br/> |通话的最低 RecvListenMOS。  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||指示是否已将音频 FEC 用于呼叫的标志。  <br/> |
|**RatioConcealedSamplesAvg** <br/> |十进制 (5, 2)  <br/> ||通过音频康复为典型示例生成的隐藏样本的平均比率。  <br/> |
|**RatioStretchedSamplesAvg** <br/> |十进制 (5, 2)  <br/> ||通过音频康复为典型示例生成的拉伸样本的平均比率。  <br/> |
|**RatioCompressedSamplesAvg** <br/> |十进制 (5, 2)  <br/> ||从音频修复到典型示例生成的压缩样本的平均比率。  <br/> |
|**封** <br/> |bit  <br/> | <br/> |接收接收方的数据流数据。  <br/> |
|**出站** <br/> |bit  <br/> | <br/> |接收发件人端的数据流数据。  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1表示流方向从调用方到被调用方。  <br/> 0表示流方向来自被调用方的调用方。  <br/> |
|**JitterInterArrivalSD** <br/> |float  <br/> ||抖动到达时间的标准偏差。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**ConcealRatioMax** <br/> |float  <br/> ||由 healer 隐藏的数据包的最大比率。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**ConcealRatioSD** <br/> |float  <br/> ||由 healer 隐藏的数据包比率的标准偏差。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**HealerPacketDropRatio** <br/> |float  <br/> ||Healer 丢弃的数据包与接收的总数据包数之比。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**HealerFECPacketUsedRatio** <br/> |float  <br/> ||与接收的总数据包数相比已使用的转发纠错数据包的比率。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**MaxCompressedSamples** <br/> |float  <br/> ||由 healer 压缩的音频数据包的最大数量。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||指示通话处于损失拥塞状态的时间百分比。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||指示由于网络数据包的延迟到达而导致的阻塞的调用百分比。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||表示呼叫竞争网络资源的时间百分比。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||在通话期间测量的最小带宽估计量。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||在通话期间测量的最大带宽估计量。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||在通话过程中测量的带宽估计的标准偏差。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||通话期间测量的平均估计带宽量。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||单向延迟的总金额。 相对单向延迟测量客户端与服务器之间的延迟。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||单向延迟的平均量。 相对单向延迟测量客户端与服务器之间的延迟。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||单向延迟的最大值。 相对单向延迟测量客户端与服务器之间的延迟。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||总单向爆发次数。 "Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 数据流处于不可预知的突发流量。 此指标测量客户端与服务器之间的数据流。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||总单向脉冲密度。 "Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 数据流处于不可预知的突发流量。 此指标测量客户端与服务器之间的数据流。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||总的单向脉冲持续时间。 "Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 数据流处于不可预知的突发流量。 此指标测量客户端与服务器之间的数据流。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||总的单向间隔发生次数。 "Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 其数据流可预料的猝发。间隙表示这些猝发之间的延迟。 此指标测量客户端与服务器之间的数据流。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||总单向间距密度。 "Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 其数据流可预料的猝发。间隙表示这些猝发之间的延迟。 此指标测量客户端与服务器之间的数据流。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||总的单间隔持续时间。 "Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 其数据流可预料的猝发。间隙表示这些猝发之间的延迟。 此指标测量客户端与服务器之间的数据流。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**DecodeStereoPercent** <br/> |float  <br/> ||解码为立体声的通话百分比。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**AecRenderStereoPercent** <br/> |float  <br/> ||通过音响回声抵消器呈现为立体声的通话百分比。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**AudioPostFECPLR** <br/> |float  <br/> ||已应用转发纠错后的数据包丢失率。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**EncodeStereoPercent** <br/> |float  <br/> ||编码为立体声的通话百分比。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**AecCaptureStereoPercent** <br/> |float  <br/> ||通过音响回声抵消器以立体声形式捕获的通话百分比。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
