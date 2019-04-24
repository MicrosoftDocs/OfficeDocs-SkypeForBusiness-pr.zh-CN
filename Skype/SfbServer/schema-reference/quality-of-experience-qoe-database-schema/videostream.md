---
title: VideoStream 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: 每条记录代表一个视频流。 一个视频媒体行通常包含两个视频流。
ms.openlocfilehash: d6eeeb96acc766859d6b57594bd11a5538593da3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212016"
---
# <a name="videostream-table"></a>VideoStream 表
 
每条记录代表一个视频流。 一个视频媒体行通常包含两个视频流。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |引用[自 MediaLine table](medialine-0.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |R 引用[自 MediaLine table](medialine-0.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |引用[自 MediaLine table](medialine-0.md)。  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |媒体行中的唯一 ID。  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |外、 主  <br/> |负载说明。 请参阅[自 PayloadDescription table](payloaddescription.md)的详细信息。 <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |实时控制协议 (RTCP) 统计信息中的平均网络抖动。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |视频会话期间的最大网络抖动。  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |RTCP 统计信息中的来回行程时间。  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |视频流的最大来回行程时间。  <br/> |
|**PacketLossRate** <br/> |decimal(5,4)  <br/> | <br/> |呼叫期间的平均数据包丢失率。  <br/> |
|**PacketLossRateMax** <br/> |decimal(5,4)  <br/> | <br/> |呼叫期间观测到的最大的数据包丢失。  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |（实时传输协议，RTP） 的视频流的数据包计数。  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |视频流的带宽预估。  <br/> |
|**VideoResolution** <br/> |char(9)  <br/> | <br/> |乘以像素高度的像素宽度中的视频分辨率。 报告为 string。  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |视频流的平均比特率。  <br/> |
|**InboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |接收的视频帧速率。  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |decimal(9,4)  <br/> | <br/> |发送的视频帧速率。  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |视频会话期间的最大视频比特率。  <br/> |
|**VideoFrameLossRate** <br/> |decimal(9,4)  <br/> | <br/> |丢失的全部视频帧的百分比。  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |不可用。  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |decimal(9,4)  <br/> ||丢失的全部视频帧的百分比。  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||已在公共交换格式 (CIF) 解决方案的呼叫的百分比。  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||VGA 分辨率的呼叫的百分比。  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||HD720 分辨率的呼叫的百分比。  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||没有框架投递呼叫持续时间的百分比。  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||丢弃 B 帧下呼叫持续时间的百分比。  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||呼叫持续时间 bp 帧的百分比。  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||呼叫持续时间 bpsp 帧的百分比。  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||呼叫持续时间 bpsp 帧的百分比。  <br/> |
|**入站** <br/> |bit  <br/> | <br/> |已收到接收端的流数据。  <br/> |
|**出站** <br/> |bit  <br/> | <br/> |已收到发送端的流数据。  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 表示流方向从呼叫者到被叫方。  <br/> 0 表示流方向从被叫方到呼叫者。  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||指示呼叫处于损耗拥塞状态的时间的时间的百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||指示在此期间导致出现拥塞的网络数据包延迟到达的呼叫的百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||指示呼叫被竞争时网络资源的时间的百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||呼叫期间度量的最小带宽估计量。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||呼叫期间度量的最大带宽估计量。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||呼叫期间度量的带宽估计的标准偏差。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||呼叫期间度量的平均带宽估计量。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LowBandwidthForMultiview** <br/> |float  <br/> ||其中终结点已确定网络连接无法支持多视图视频呼叫的百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||单向滞后时间总量。 相对单向延迟测量客户端和服务器之间的延迟。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||单向延迟的平均量。 相对单向延迟测量客户端和服务器之间的延迟。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||最大单向滞后时间量。 相对单向延迟测量客户端和服务器之间的延迟。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||总单向的突发发生次数。 "突发"传输是其中数据排列中而不是稳定的不可预知间歇传输。 此指标来衡量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||总单向的突发密度。 "突发"传输是其中数据排列中而不是稳定的不可预知间歇传输。 此指标来衡量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||总单向的突发持续时间。 "突发"传输是其中数据排列中而不是稳定的不可预知间歇传输。 此指标来衡量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||总单向的间隙发生次数。 "突发"传输是传输其中数据排列中而不是稳定流; 无法预料间歇间隙指示这些间歇之间的延迟。 此指标来衡量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||总单向的间隙密度。 "突发"传输是传输其中数据排列中而不是稳定流; 无法预料间歇间隙指示这些间歇之间的延迟。 此指标来衡量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||总单向的间隙持续时间。 "突发"传输是传输其中数据排列中而不是稳定流; 无法预料间歇间隙指示这些间歇之间的延迟。 此指标来衡量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**VideoPacketLossRate** <br/> |decimal(9,4)  <br/> ||视频数据包丢失的速率。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||平均视频的带宽总量量。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |外  <br/> |由发件人的视频编解码器的类型。 请参阅[CodecDescription 表](codecdescription.md)的详细信息。 <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||发件人使用的分辨率宽度。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||发件人使用的分辨率高度。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendFrameRateAverage** <br/> |float  <br/> ||平均视频帧速率传输发件人使用。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||发件人的最大比特率。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||发送者的平均比特率。  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||最大数量由发件人的视频流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |外  <br/> |接收方使用的视频代码。 请参阅[CodecDescription 表](codecdescription.md)的详细信息。 <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||接收方使用的分辨率宽度。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||接收方使用的分辨率高度。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvFrameRateAverage** <br/> |float  <br/> ||接收方使用的平均视频帧速率。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||接收方的最大比特率。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||接收方的平均比特率。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||接收方的最大视频流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||接收方的最小视频流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||视频模式 （例如，库或单个流） 接收器。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**VideoPostFECPLR** <br/> |float  <br/> ||应用前向纠错后的数据包丢失率。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**DynamicCapabilityPercent** <br/> |float  <br/> ||动态功能标志处于活动状态的时间的百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ResolutionMin** <br/> |char(9)  <br/> ||呼叫期间度量的最小分辨率。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LowBitRateCallPercent** <br/> |float  <br/> ||低比特率阈值 （70 千位每秒） 下的呼叫的百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LowFrameRateCallPercent** <br/> |float  <br/> ||低帧速率阈值下的呼叫的百分比 （7.5 帧 / 秒，入站）。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LowResolutionCallPercent** <br/> |float  <br/> ||最低分辨率发生的呼叫百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**DurationSeconds** <br/> |float  <br/> ||以秒为单位的呼叫的长度。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||指示是否已通过多个呼叫聚合数据。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
   

