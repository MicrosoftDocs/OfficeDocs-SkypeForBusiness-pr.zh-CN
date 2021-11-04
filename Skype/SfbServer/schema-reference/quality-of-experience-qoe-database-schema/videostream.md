---
title: VideoStream 表
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: 每条记录代表一个视频流。 一个视频媒体行通常包含两个视频流。
ms.openlocfilehash: 78bc415c7b95fd0f9b6ecb3f3242b5a29c93c0dd
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60756063"
---
# <a name="videostream-table"></a>VideoStream 表
 
每条记录代表一个视频流。 一个视频媒体行通常包含两个视频流。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主  <br/> |R 从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |主  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|**StreamID** <br/> |int  <br/> |主  <br/> |媒体行中的唯一 ID。  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |Foreign、Primary  <br/> |有效负载描述。 有关详细信息， [请参阅 PayloadDescription](payloaddescription.md) 表。 <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |实时控制协议 (RTCP) 统计信息中的平均网络抖动。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |视频会话期间的最大网络抖动。  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |RTCP 统计信息中的来回行程时间。  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |视频流的最大往返时间。  <br/> |
|**PacketLossRate** <br/> |decimal (5，4)   <br/> | <br/> |呼叫期间的平均数据包丢失率。  <br/> |
|**PacketLossRateMax** <br/> |decimal (5，4)   <br/> | <br/> |呼叫期间观测到的数据包丢失最大值。  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |视频流的数据包计数（实时传输协议，RTP）。  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |视频流的带宽估计值。  <br/> |
|**VideoResolution** <br/> |char (9)   <br/> | <br/> |视频的分辨率（像素宽乘以像素高）。报告为字符串。  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |视频流的平均比特率。  <br/> |
|**InboundVideoFrameRateAvg** <br/> |decimal (9，4)   <br/> | <br/> |接收的视频帧速率。  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |decimal (9，4)   <br/> | <br/> |发送的视频帧速率。  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |视频会话期间的最大视频比特率。  <br/> |
|**VideoFrameLossRate** <br/> |decimal (9，4)   <br/> | <br/> |丢失的总视频帧百分比。  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |不可用。  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |decimal (9，4)   <br/> ||丢失的总视频帧百分比。  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||采用通用交换格式的呼叫的百分比 (CIF) 分辨率。  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||使用 VGA 分辨率的呼叫的百分比。  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||分辨率为 HD720 的呼叫的百分比。  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||无帧拖放的呼叫持续时间百分比。  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||B 帧丢弃的呼叫持续时间百分比。  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||BP 帧丢弃的呼叫持续时间百分比。  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||呼叫持续时间与 BPSP 帧丢弃的百分比。  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||呼叫持续时间与 BPSPI 帧丢弃的百分比。  <br/> |
|**入站** <br/> |bit  <br/> | <br/> |接收接收方上的流数据。  <br/> |
|**出站** <br/> |bit  <br/> | <br/> |接收发件人端上的流数据。  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1 表示流方向是从呼叫者到被叫方。  <br/> 0 表示流方向是从被叫方到呼叫者。  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||指示呼叫丢失拥塞状态的时间百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||指示网络数据包延迟到达导致拥塞的呼叫所占的百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||指示呼叫与网络资源竞争的时间百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||呼叫期间测量的最小带宽估计量。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||呼叫期间测量的最大带宽估计量。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||呼叫期间测量的带宽估计的标准偏差。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||呼叫期间测量的平均带宽估计量。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LowBandwidthForMultiview** <br/> |float  <br/> ||终结点确定网络连接不支持多视图视频的呼叫百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||单向延迟的总量。相对单向延迟用于度量客户端和服务器之间的延迟。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||单向延迟的平均量。相对单向延迟用于度量客户端和服务器之间的延迟。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||单向延迟的最大量。相对单向延迟用于度量客户端和服务器之间的延迟。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||单向突发总发生次数。 "突发"传输是数据流以不可预知的突发方式（与稳定流相反）的传输。 此指标用于度量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||单向突发总密度。 "突发"传输是数据流以不可预知的突发方式（与稳定流相反）的传输。 此指标用于度量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||单向突发总持续时间。 "突发"传输是数据流以不可预知的突发方式（与稳定流相反）的传输。 此指标用于度量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||单向间隙总发生次数。 "突发"传输是数据流以不可预知的突发方式（与稳定流相反）的传输;间隙指示这些突发之间的延迟。 此指标用于度量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||单向间隙总密度。 "突发"传输是数据流以不可预知的突发方式（与稳定流相反）的传输;间隙指示这些突发之间的延迟。 此指标用于度量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||单向间隙总持续时间。 "突发"传输是数据流以不可预知的突发方式（与稳定流相反）的传输;间隙指示这些突发之间的延迟。 此指标用于度量客户端和服务器之间的数据流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**VideoPacketLossRate** <br/> |decimal (9，4)   <br/> ||视频数据包丢失的比特率。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||为视频分配的平均带宽量。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |Foreign  <br/> |发件人使用的视频编解码器的类型。 有关详细信息 [，请参阅 CodecDescription](codecdescription.md) 表。 <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||发件人使用的分辨率宽度。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||发件人使用的分辨率高度。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendFrameRateAverage** <br/> |float  <br/> ||发件人使用的平均视频帧速率传输。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||发件人的最大比特率。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||发件人的平均比特率。  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||发件人使用的最大视频流数。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |Foreign  <br/> |接收器使用的视频代码。 有关详细信息 [，请参阅 CodecDescription](codecdescription.md) 表。 <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||接收器使用的分辨率宽度。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||接收器使用的分辨率高度。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvFrameRateAverage** <br/> |float  <br/> ||接收方使用的平均视频帧速率。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||接收器的最大比特率。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||接收器的平均比特率。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||接收器的最大视频流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||接收器的最低视频流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||视频模式 (例如，接收器的库或) 流。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**VideoPostFECPLR** <br/> |float  <br/> ||应用前向错误更正后的数据包丢失率。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**DynamicCapabilityPercent** <br/> |float  <br/> ||动态功能标志处于活动状态的时间百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**ResolutionMin** <br/> |char (9)   <br/> ||呼叫期间测量的最小分辨率。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LowBitRateCallPercent** <br/> |float  <br/> ||低于低比特率阈值的呼叫百分比 (70 KB/秒) 。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LowFrameRateCallPercent** <br/> |float  <br/> ||低于低帧速率阈值的呼叫百分比 (每秒 7.5 帧，入站) 。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LowResolutionCallPercent** <br/> |float  <br/> ||以最低分辨率发生的呼叫的百分比。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**DurationSeconds** <br/> |float  <br/> ||呼叫时长（以秒表示）。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||指示数据是否已从多个调用聚合。  <br/> 此列是在 Microsoft Lync Server 2013 中引入的。  <br/> |
   

