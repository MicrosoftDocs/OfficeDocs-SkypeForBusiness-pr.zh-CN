---
title: AudioStream 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: 每条记录代表一个音频流。 一个音频媒体行通常包含两个音频流。
ms.openlocfilehash: 28111f9c97efdc729d13fda824f4236caad97eee1f08ff31eea0b751dda1cb88
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309191"
---
# <a name="audiostream-table"></a>AudioStream 表
 
每条记录代表一个音频流。 一个音频媒体行通常包含两个音频流。
  
|列|数据类型|键/索引|详细信息|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |主  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|**StreamID** <br/> |int  <br/> |主  <br/> |媒体行中的唯一 ID。  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |实时控制协议 (RTCP) 统计信息中的平均网络抖动。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |呼叫期间的最大网络抖动。  <br/> |
|**PacketLossRate** <br/> |decimal (5，4)   <br/> | <br/> |呼叫期间的平均数据包丢失率。  <br/> |
|**PacketLossRateMax** <br/> |decimal (5，4)   <br/> | <br/> |呼叫期间观测到的数据包丢失最大值。  <br/> |
|**BurstDensity** <br/> |decimal (9，4)   <br/> | <br/> |呼叫过程中突发丢失的数据包丢失的平均密度。  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |呼叫过程中突发丢失数据包的平均持续时间。  <br/> |
|**BurstGapDensity** <br/> |decimal (9，4)   <br/> | <br/> |数据包丢失的突发间隔期间数据包丢失的平均密度。  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |数据包丢失突发之间的平均间隔持续时间。  <br/> |
|**PacketUtilization** <br/> |Int  <br/> | <br/> |音频流的数据包计数。  <br/> |
|**BandwidthEst** <br/> |Int  <br/> | <br/> |音频流的带宽预估。  <br/> |
|**DegradationAvg** <br/> |decimal (3，2)   <br/> | <br/> |整个呼叫的网络 MOS 降级。 范围为 0.0 到 5.0。 此指标显示由于抖动和数据包丢失而减少的网络 MOS 量。 对于可接受的质量，它应小于 0.5。  <br/> |
|**DegradationMax** <br/> |decimal (3，2)   <br/> | <br/> |呼叫期间最大网络 MOS 下降。  <br/> |
|**DegradationJitterAvg** <br/> |decimal (3，2)   <br/> | <br/> |抖动造成的网络 MOS 下降。  <br/> |
|**DegradationPacketLossAvg** <br/> |decimal (3，2)   <br/> | <br/> |因数据包丢失导致网络 MOS 下降。  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |Foreign  <br/> |用于呼叫的音频编解码器，从 PayloadDescription Table 引用。  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |音频流的采样率。  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |RTCP 统计信息中的来回行程时间。 对于可接受的质量，此时间应小于 100 毫秒。  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |音频流的最大来回行程时间。  <br/> |
|**OverallAvgNetworkMOS** <br/> |decimal (3，2)   <br/> | <br/> |呼叫的平均宽带网络 MOS。 此指标取决于使用的数据包丢失、抖动和编解码器。 范围为 [1.0 至 5.0]。  <br/> |
|**OverallMinNetworkMOS** <br/> |decimal (3，2)   <br/> | <br/> |呼叫的最小宽带网络 MOS。  <br/> |
|**SendListenMOS** <br/> |decimal (3，2)   <br/> | <br/> |已发送音频的平均预测宽带侦听 MOS 得分，包括语音级别、噪音级别和捕获设备特征。  <br/> |
|**SendListenMOSMin** <br/> |decimal (3，2)   <br/> | <br/> |呼叫的最低 SendListenMOS。  <br/> |
|**RecvListenMOS** <br/> |decimal (3，2)   <br/> | <br/> |从网络接收的音频的平均预测宽带侦听 MOS 得分，包括语音级别、噪音级别、编解码器、网络条件和捕获设备特征。  <br/> |
|**RecvListenMOSMin** <br/> |decimal (3，2)   <br/> | <br/> |呼叫的最低 RecvListenMOS。  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||指示是否对呼叫使用音频 FEC 的标志。  <br/> |
|**RatioConcealedSamplesAvg** <br/> |decimal (5，2)   <br/> ||音频修复生成的隐藏样本与典型样本的平均比率。  <br/> |
|**RatioStretchedSamplesAvg** <br/> |decimal (5，2)   <br/> ||音频处理生成的拉伸样本与典型样本的平均比率。  <br/> |
|**RatioCompressedSamplesAvg** <br/> |decimal (5，2)   <br/> ||音频处理生成的压缩样本与典型样本的平均比率。  <br/> |
|**入站** <br/> |bit  <br/> | <br/> |接收接收方上的流数据。  <br/> |
|**出站** <br/> |bit  <br/> | <br/> |接收发件人端上的流数据。  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 表示流方向从呼叫者到被叫方。  <br/> 0 表示流方向是从被叫方到呼叫者。  <br/> |
|**JitterInterArrivalSD** <br/> |float  <br/> ||抖动到达时间的标准偏差。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ConcealRatioMax** <br/> |float  <br/> ||修复程序隐藏的数据包的最大比率。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ConcealRatioSD** <br/> |float  <br/> ||修复程序隐藏数据包比率的标准偏差。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**HealerPacketDropRatio** <br/> |float  <br/> ||修复程序丢弃的数据包与收到的数据包总数的比率。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**HealerFECPacketUsedRatio** <br/> |float  <br/> ||使用的前向错误更正数据包与收到的数据包总数的比率。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**MaxCompressedSamples** <br/> |float  <br/> ||由修复程序压缩的音频数据包的最大数目。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||指示呼叫丢失拥塞状态的时间百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||指示网络数据包延迟到达导致拥塞的呼叫所占的百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||指示呼叫与网络资源竞争的时间百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||呼叫期间测量的最小带宽估计量。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||呼叫期间测量的最大带宽估计量。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||呼叫期间测量的带宽估计的标准偏差。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||呼叫期间测量的平均带宽估计量。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||单向延迟的总量。相对单向延迟用于度量客户端和服务器之间的延迟。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||单向延迟的平均量。相对单向延迟用于度量客户端和服务器之间的延迟。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||单向延迟的最大量。相对单向延迟用于度量客户端和服务器之间的延迟。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||单向突发总发生次数。 "突发"传输是数据流以不可预知的突发方式（与稳定流相反）的传输。 此指标用于度量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||单向突发总密度。 "突发"传输是数据流以不可预知的突发方式（与稳定流相反）的传输。 此指标用于度量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||单向突发总持续时间。 "突发"传输是数据流以不可预知的突发方式（与稳定流相反）的传输。 此指标用于度量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||单向间隙总发生次数。 "突发"传输是数据流以不可预知的突发方式（与稳定流相反）的传输;间隙指示这些突发之间的延迟。 此指标用于度量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||单向间隙总密度。 "突发"传输是数据流以不可预知的突发方式（与稳定流相反）的传输;间隙指示这些突发之间的延迟。 此指标用于度量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||单向间隙总持续时间。 "突发"传输是数据流以不可预知的突发方式（与稳定流相反）的传输;间隙指示这些突发之间的延迟。 此指标用于度量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**DecodeStereoPercent** <br/> |float  <br/> ||解码为立体声的呼叫的百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**AecRenderStereoPercent** <br/> |float  <br/> ||声音回声消除器呈现为立体声的呼叫百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**AudioPostFECPLR** <br/> |float  <br/> ||应用前向错误更正后的数据包丢失率。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**EncodeStereoPercent** <br/> |float  <br/> ||编码为立体声的呼叫的百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**AecCaptureStereoPercent** <br/> |float  <br/> ||声音回声消除器捕获为立体声的呼叫百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
