---
title: AudioStream 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: 每条记录代表一个音频流。 一个音频媒体行通常包含两个音频流。
ms.openlocfilehash: 7c1e7ae70a04aabc7db704aaaad873bc5b2100c9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894133"
---
# <a name="audiostream-table"></a>AudioStream 表
 
每条记录代表一个音频流。 一个音频媒体行通常包含两个音频流。
  
|列|数据类型|键/索引|详细信息|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |引用[自 MediaLine table](medialine-0.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |引用[自 MediaLine table](medialine-0.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |引用[自 MediaLine table](medialine-0.md)。  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |媒体行中的唯一 ID。  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |实时控制协议 (RTCP) 统计信息中的平均网络抖动。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |呼叫期间的最大网络抖动。  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |呼叫期间的平均数据包丢失率。  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |呼叫期间观测到的最大的数据包丢失。  <br/> |
|**BurstDensity** <br/> |decimal(9,4)  <br/> | <br/> |在呼叫过程中出现间歇的数据包丢失的平均密度。  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |在呼叫过程中出现间歇的数据包丢失的平均持续时间。  <br/> |
|**BurstGapDensity** <br/> |decimal(9,4)  <br/> | <br/> |间歇的数据包丢失之间出现间隙期间数据包丢失的平均密度。  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |间歇的数据包丢失之间出现间隙的平均持续时间。  <br/> |
|**PacketUtilization** <br/> |Int  <br/> | <br/> |音频流的数据包计数。  <br/> |
|**BandwidthEst** <br/> |Int  <br/> | <br/> |音频流的带宽预估。  <br/> |
|**DegradationAvg** <br/> |decimal(3,2)  <br/> | <br/> |用于整个呼叫的网络 MOS 性能降低。 范围是 0.0 为 5.0。 此指标显示网络 MOS 减少由于抖动和丢包的量。 可接受的质量，它应小于 0.5。  <br/> |
|**DegradationMax** <br/> |decimal(3,2)  <br/> | <br/> |呼叫期间的最大网络 MOS 性能降低。  <br/> |
|**DegradationJitterAvg** <br/> |decimal(3,2)  <br/> | <br/> |抖动导致的网络 MOS 性能降低。  <br/> |
|**DegradationPacketLossAvg** <br/> |decimal(3,2)  <br/> | <br/> |数据包丢失导致的网络 MOS 性能降低。  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |外  <br/> |音频编解码器用于呼叫，引用自 PayloadDescription 表。  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |音频流的采样率。  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |RTCP 统计信息中的来回行程时间。 可接受的质量应小于为 100 毫秒。  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |音频流的最大来回行程时间。  <br/> |
|**OverallAvgNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |平均宽带网络 MOS，呼叫。 此指标取决于数据包丢失、 抖动和编解码器。 范围为 [1.0 5.0]。  <br/> |
|**OverallMinNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |最小宽带网络 MOS，呼叫。  <br/> |
|**SendListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |平均预测的宽带倾听 MOS 得分音频发送，包括语音级别、 噪音级别和捕获设备特征。  <br/> |
|**SendListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |呼叫最小 SendListenMOS。  <br/> |
|**RecvListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |从网络包括语音级别、 噪音级别、 编解码器、 网络条件和捕获设备特征接收音频的平均预测的宽带倾听 MOS 得分。  <br/> |
|**RecvListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |呼叫最小 RecvListenMOS。  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||标志指示音频 FEC 已用于呼叫。  <br/> |
|**RatioConcealedSamplesAvg** <br/> |decimal(5,2)  <br/> ||生成的典型示例音频样本隐藏样本数的平均比率。  <br/> |
|**RatioStretchedSamplesAvg** <br/> |decimal(5,2)  <br/> ||通过典型示例的音频修复生成的拉伸样本数的平均比率。  <br/> |
|**RatioCompressedSamplesAvg** <br/> |decimal(5,2)  <br/> ||生成的典型示例的音频修复的压缩样本数的平均比率。  <br/> |
|**入站** <br/> |bit  <br/> | <br/> |已收到接收端的流数据。  <br/> |
|**出站** <br/> |bit  <br/> | <br/> |已收到发送端的流数据。  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 表示流方向从呼叫者到被叫方。  <br/> 0 表示流方向从被叫方到呼叫者。  <br/> |
|**JitterInterArrivalSD** <br/> |float  <br/> ||抖动到达时间的标准偏差。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ConcealRatioMax** <br/> |float  <br/> ||修复程序隐藏的数据包的最大比率。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ConcealRatioSD** <br/> |float  <br/> ||修复程序隐藏的数据包的比率的标准偏差。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**HealerPacketDropRatio** <br/> |float  <br/> ||收到的数据包的总数比较修复程序丢弃的数据包的比率。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**HealerFECPacketUsedRatio** <br/> |float  <br/> ||使用前向纠错数据包与收到的数据包的总数的比率。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**MaxCompressedSamples** <br/> |float  <br/> ||修复程序压缩的音频数据包的最大数量。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||指示呼叫处于损耗拥塞状态的时间的时间的百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||指示在此期间导致出现拥塞的网络数据包延迟到达的呼叫的百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||指示呼叫被竞争时网络资源的时间的百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||呼叫期间度量的最小带宽估计量。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||呼叫期间度量的最大带宽估计量。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||呼叫期间度量的带宽估计的标准偏差。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||呼叫期间度量的平均带宽估计量。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||单向滞后时间总量。 相对单向延迟测量客户端和服务器之间的延迟。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||单向延迟的平均量。 相对单向延迟测量客户端和服务器之间的延迟。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||最大单向滞后时间量。 相对单向延迟测量客户端和服务器之间的延迟。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||总单向的突发发生次数。 "突发"传输是其中数据排列中而不是稳定的不可预知间歇传输。 此指标来衡量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||总单向的突发密度。 "突发"传输是其中数据排列中而不是稳定的不可预知间歇传输。 此指标来衡量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||总单向的突发持续时间。 "突发"传输是其中数据排列中而不是稳定的不可预知间歇传输。 此指标来衡量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||总单向的间隙发生次数。 "突发"传输是传输其中数据排列中而不是稳定流; 无法预料间歇间隙指示这些间歇之间的延迟。 此指标来衡量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||总单向的间隙密度。 "突发"传输是传输其中数据排列中而不是稳定流; 无法预料间歇间隙指示这些间歇之间的延迟。 此指标来衡量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||总单向的间隙持续时间。 "突发"传输是传输其中数据排列中而不是稳定流; 无法预料间歇间隙指示这些间歇之间的延迟。 此指标来衡量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**DecodeStereoPercent** <br/> |float  <br/> ||解码为立体声的呼叫的百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**AecRenderStereoPercent** <br/> |float  <br/> ||由回声抑制消除器呈现为立体声的呼叫的百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**AudioPostFECPLR** <br/> |float  <br/> ||应用前向纠错后的数据包丢失率。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**EncodeStereoPercent** <br/> |float  <br/> ||编码为立体声的呼叫的百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**AecCaptureStereoPercent** <br/> |float  <br/> ||由回声抑制消除器作为立体声捕获的呼叫的百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
