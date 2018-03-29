---
title: VideoStream 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: 每个记录都表示一个视频流。 视频媒体一行通常包含两个视频流。
ms.openlocfilehash: 27a9c8cdd8b1975b7854147b5855a8494155ce2a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="videostream-table"></a>VideoStream 表
 
每个记录都表示一个视频流。 视频媒体一行通常包含两个视频流。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)引用。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |R 从[MediaLine 表](medialine-0.md)引用。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)引用。  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |在媒体行的唯一 ID。  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |外主  <br/> |有效载荷描述。 [PayloadDescription 表](payloaddescription.md)的详细信息，请参阅。 <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |从实时控制协议 (RTCP) 统计的平均网络抖动。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |最大的网络视频会话期间不稳定。  <br/> |
|**往返** <br/> |int  <br/> | <br/> |从 RTCP 统计信息的往返时间。  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |视频流的最大往返时间。  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |在调用过程平均数据包丢失率。  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |在调用期间观察到的最大数据包丢失。  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |（RTP 实时传输协议） 的视频流的数据包数。  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |带宽估计的视频流。  <br/> |
|**VideoResolution** <br/> |char(9)  <br/> | <br/> |在乘以像素高度的像素宽度的视频分辨率。 报告为一个字符串。  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |视频流的平均比特率。  <br/> |
|**InboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |接收的视频帧速率。  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |发送的视频帧速率。  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |视频会话期间大视频比特率。  <br/> |
|**VideoFrameLossRate** <br/> |decimal(9,4)  <br/> | <br/> |总将丢失的视频帧的百分比。  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |不可用。  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |decimal(9,4)  <br/> ||总将丢失的视频帧的百分比。  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||通用交换格式 (CIF) 的分辨率被调用的百分比。  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||在 VGA 分辨率已调用的百分比。  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||在 HD720 分辨率已调用的百分比。  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||没有框架垂直呼叫持续时间的百分比。  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||与 B 帧放呼叫持续时间的百分比。  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||与 BP 框架放呼叫持续时间的百分比。  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||使用 BPSP 框架放呼叫持续时间的百分比。  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||使用 BPSPI 框架放呼叫持续时间的百分比。  <br/> |
|**入站** <br/> |bit  <br/> | <br/> |接收到接收端的流数据。  <br/> |
|**出站** <br/> |bit  <br/> | <br/> |接收流数据发送方一侧。  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 表示流方向是从调用方对被调用方。  <br/> 0 表示流方向是从被调用方调用方。  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||指示调用时丢失拥塞状态的时间的百分比。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||指示的调用其间拥塞由网络数据包延迟到达的百分比。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||指示当调用了竞争的网络资源的时间的百分比。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||在调用期间测量带宽估计的最小金额。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||在调用期间测量带宽估计的最大金额。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||在调用期间测量带宽估计的标准偏差。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||在调用期间测量带宽估计的平均量。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**LowBandwidthForMultiview** <br/> |float  <br/> ||在终结点确定的网络连接可能不支持多视图视频呼叫的百分比。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||单向延迟的总金额。 相对的单向延迟测量客户端和服务器之间的延迟。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||单向延迟平均量。 相对的单向延迟测量客户端和服务器之间的延迟。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||单向延迟的最大数量。 相对的单向延迟测量客户端和服务器之间的延迟。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||总的单向突发事件。 "突发"传输是传输其中的数据排列在不可预知的突发情况，而不是稳定。 此指标用于衡量客户端和服务器之间的数据流。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||总的单向爆发密度。 "突发"传输是传输其中的数据排列在不可预知的突发情况，而不是稳定。 此指标用于衡量客户端和服务器之间的数据流。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||总的单向脉冲持续时间。 "突发"传输是传输其中的数据排列在不可预知的突发情况，而不是稳定。 此指标用于衡量客户端和服务器之间的数据流。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||总的单向差距出现次数。 "突发"传输是传输其中的数据排列在不可预知的突发情况相对稳定;间隙表示这些突发情况之间的延迟。 此指标用于衡量客户端和服务器之间的数据流。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||总的单向间隙密度。 "突发"传输是传输其中的数据排列在不可预知的突发情况相对稳定;间隙表示这些突发情况之间的延迟。 此指标用于衡量客户端和服务器之间的数据流。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||总的单向差距持续时间。 "突发"传输是传输其中的数据排列在不可预知的突发情况相对稳定;间隙表示这些突发情况之间的延迟。 此指标用于衡量客户端和服务器之间的数据流。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**VideoPacketLossRate** <br/> |decimal(9,4)  <br/> ||视频数据包的丢失率。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||为视频分配带宽的平均金额。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |外  <br/> |发件人所使用的视频编解码器类型。 [CodecDescription 表](codecdescription.md)的详细信息，请参阅。 <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||解析发件人所使用的宽度。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||解析发件人所使用的高度。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**SendFrameRateAverage** <br/> |float  <br/> ||发件人所使用的视频帧速率传输的平均。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||发件人的最大比特率。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||发件人的平均比特率。  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||发件人所使用的视频流的最大数目。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |外  <br/> |使用接收方的视频代码。 [CodecDescription 表](codecdescription.md)的详细信息，请参阅。 <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||解决使用接收方的宽度。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||解决使用接收方的高度。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RecvFrameRateAverage** <br/> |float  <br/> ||使用接收方的平均视频的帧速率。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||接收方的最大比特率。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||接收方的平均比特率。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||最大接收方的视频流。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||对接收方的最低视频流。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||视频模式 （例如，库或单个流） 的接收器。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**VideoPostFECPLR** <br/> |float  <br/> ||应用正向纠错后的数据包丢失率。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**DynamicCapabilityPercent** <br/> |float  <br/> ||动态的功能标志处于活动状态的时间百分比。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**ResolutionMin** <br/> |char(9)  <br/> ||在调用期间测量最小分辨率。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**LowBitRateCallPercent** <br/> |float  <br/> ||低位率阈值 （70 千比特每秒） 以下调用的百分比。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**LowFrameRateCallPercent** <br/> |float  <br/> ||低于低帧速率阈值呼叫的百分比 （7.5 帧 / 秒，入站）。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**LowResolutionCallPercent** <br/> |float  <br/> ||发生在低分辨率的调用的百分比。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**DurationSeconds** <br/> |float  <br/> ||调用以秒为单位的长度。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||指示是否已从多个调用聚合数据。  <br/> 在 Microsoft Lync Server 2013 引入了此列。  <br/> |
   

