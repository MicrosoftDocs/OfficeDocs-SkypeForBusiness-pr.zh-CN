---
title: AudioStream 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
description: 每个记录都表示一个音频流。 通常，音频媒体一行包含两个音频流。
ms.openlocfilehash: 63cd2f63eed5d423750a50a23ae347a97725d65f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="audiostream-table"></a>AudioStream 表
 
每个记录都表示一个音频流。 通常，音频媒体一行包含两个音频流。
  
|列 ***|数据类型 ***|键 / 索引 ***|详细信息 ***|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)引用。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)引用。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)引用。  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |在媒体行的唯一 ID。  <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |从实时控制协议 (RTCP) 统计的平均网络抖动。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |在调用过程的最大网络抖动。  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |在调用过程平均数据包丢失率。  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |在调用期间观察到的最大数据包丢失。  <br/> |
|**BurstDensity** <br/> |decimal(9,4)  <br/> | <br/> |在过程调用中的损失的突发数据包丢失的平均密度。  <br/> |
|**BurstDuration** <br/> |int  <br/> | <br/> |平均持续时间在猝发过程中调用的损失的期间丢失数据包的情况。  <br/> |
|**BurstGapDensity** <br/> |decimal(9,4)  <br/> | <br/> |数据包丢失期间突发的数据包丢失率之间的差距平均密度。  <br/> |
|**BurstGapDuration** <br/> |int  <br/> | <br/> |猝发的数据包丢失率之间的差距平均持续时间。  <br/> |
|**PacketUtilization** <br/> |Int  <br/> | <br/> |音频流的数据包数。  <br/> |
|**BandwidthEst** <br/> |Int  <br/> | <br/> |带宽估计的音频流。  <br/> |
|**DegradationAvg** <br/> |decimal(3,2)  <br/> | <br/> |整个呼叫网络 MOS 有所下降。 范围是 0.0 到 5.0。 此统计数据显示了网络 MOS 减少由于抖动和包丢失量。 可接受的质量应该小于 0.5。  <br/> |
|**DegradationMax** <br/> |decimal(3,2)  <br/> | <br/> |在调用过程的最大网络 MOS 下降。  <br/> |
|**DegradationJitterAvg** <br/> |decimal(3,2)  <br/> | <br/> |网络 MOS 下降引起的抖动。  <br/> |
|**DegradationPacketLossAvg** <br/> |decimal(3,2)  <br/> | <br/> |网络数据包丢失所致的 MOS 下降。  <br/> |
|**AudioPayloadDescription** <br/> |int  <br/> |外  <br/> |音频编解码器用于调用中，从 PayloadDescription 表引用。  <br/> |
|**AudioSampleRate** <br/> |int  <br/> | <br/> |采样速度，以音频流。  <br/> |
|**往返** <br/> |int  <br/> | <br/> |从 RTCP 统计信息的往返时间。 对于可接受的质量，这应该是小于 100 毫秒。  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |音频流的最大往返时间。  <br/> |
|**OverallAvgNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |宽带网络 MOS 的调用的平均。 此指标取决于数据包丢失、 抖动和使用的编解码器。 范围是 [1.0 到 5.0]。  <br/> |
|**OverallMinNetworkMOS** <br/> |decimal(3,2)  <br/> | <br/> |最小宽带网络 MOS 的呼叫。  <br/> |
|**SendListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |平均预测的宽带侦听 MOS 得分音频发送，包括语音级别、 噪音级别和捕获设备特征。  <br/> |
|**SendListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |调用最小 SendListenMOS。  <br/> |
|**RecvListenMOS** <br/> |decimal(3,2)  <br/> | <br/> |从网络语音级别、 噪声水平、 编解码器、 网络状况和捕获设备特征包括接收音频的平均预测的宽带侦听 MOS 得分。  <br/> |
|**RecvListenMOSMin** <br/> |decimal(3,2)  <br/> | <br/> |调用最小 RecvListenMOS。  <br/> |
|**AudioFECUsed** <br/> |bit  <br/> ||指示如果为呼叫使用的音频 FEC 的标志。  <br/> |
|**RatioConcealedSamplesAvg** <br/> |decimal(5,2)  <br/> ||生成的音频康复对典型样本的隐蔽样本的平均比率。  <br/> |
|**RatioStretchedSamplesAvg** <br/> |decimal(5,2)  <br/> ||拉伸示例生成的音频康复对典型样本的平均比率。  <br/> |
|**RatioCompressedSamplesAvg** <br/> |decimal(5,2)  <br/> ||通过对典型样本的音频修复生成压缩样本的平均比率。  <br/> |
|**入站** <br/> |bit  <br/> | <br/> |接收到接收端的流数据。  <br/> |
|**出站** <br/> |bit  <br/> | <br/> |接收流数据发送方一侧。  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 表示流方向是从调用方对被调用方。  <br/> 0 表示流方向是从被调用方调用方。  <br/> |
|**JitterInterArrivalSD** <br/> |float  <br/> ||抖动到达时间的标准偏差。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**ConcealRatioMax** <br/> |float  <br/> ||Healer 隐藏其数据包的最大比率。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**ConcealRatioSD** <br/> |float  <br/> ||隐藏，healer 将其数据包的比率的标准偏差。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**HealerPacketDropRatio** <br/> |float  <br/> ||通过与接收到的数据包的总数相比 healer 丢弃的数据包的比率。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**HealerFECPacketUsedRatio** <br/> |float  <br/> ||使用转发错误更正数据包接收的数据包的总数相比的比率。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**MaxCompressedSamples** <br/> |float  <br/> ||Healer 由被压缩的音频数据包的最大数目。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||指示调用时丢失拥塞状态的时间的百分比。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||指示的调用其间拥塞由网络数据包延迟到达的百分比。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||指示当调用了竞争的网络资源的时间的百分比。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||在调用期间测量带宽估计的最小金额。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||在调用期间测量带宽估计的最大金额。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||在调用期间测量带宽估计的标准偏差。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||在调用期间测量带宽估计的平均量。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||单向延迟的总金额。 相对的单向延迟测量客户端和服务器之间的延迟。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||单向延迟平均量。 相对的单向延迟测量客户端和服务器之间的延迟。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||单向延迟的最大数量。 相对的单向延迟测量客户端和服务器之间的延迟。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||总的单向突发事件。 "突发"传输是传输其中的数据排列在不可预知的突发情况，而不是稳定。 此指标用于衡量客户端和服务器之间的数据流。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||总的单向爆发密度。 "突发"传输是传输其中的数据排列在不可预知的突发情况，而不是稳定。 此指标用于衡量客户端和服务器之间的数据流。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||总的单向脉冲持续时间。 "突发"传输是传输其中的数据排列在不可预知的突发情况，而不是稳定。 此指标用于衡量客户端和服务器之间的数据流。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||总的单向差距出现次数。 "突发"传输是传输其中的数据排列在不可预知的突发情况相对稳定;间隙表示这些突发情况之间的延迟。 此指标用于衡量客户端和服务器之间的数据流。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||总的单向间隙密度。 "突发"传输是传输其中的数据排列在不可预知的突发情况相对稳定;间隙表示这些突发情况之间的延迟。 此指标用于衡量客户端和服务器之间的数据流。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||总的单向差距持续时间。 "突发"传输是传输其中的数据排列在不可预知的突发情况相对稳定;间隙表示这些突发情况之间的延迟。 此指标用于衡量客户端和服务器之间的数据流。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**DecodeStereoPercent** <br/> |float  <br/> ||解码为立体声音频呼叫的百分比。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**AecRenderStereoPercent** <br/> |float  <br/> ||呈现为立体声音频回声 canceller 调用的百分比。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**AudioPostFECPLR** <br/> |float  <br/> ||应用正向纠错后的数据包丢失率。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**EncodeStereoPercent** <br/> |float  <br/> ||作为立体声编码调用的百分比。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**AecCaptureStereoPercent** <br/> |float  <br/> ||捕获为立体声音频回声 canceller 调用的百分比。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
   

