---
title: VideoStream 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
description: 每条记录表示一个视频流。 一个视频媒体线通常包含两个视频流。
ms.openlocfilehash: 678f8b14fb3746ddd50a83ebd68c3878237908e4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294521"
---
# <a name="videostream-table"></a>VideoStream 表
 
每条记录表示一个视频流。 一个视频媒体线通常包含两个视频流。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)中引用。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |[MediaLine 表](medialine-0.md)中引用的 R。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primary  <br/> |从[MediaLine 表](medialine-0.md)中引用。  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |媒体行内的唯一 ID。  <br/> |
|**VideoPayloadDescription** <br/> |smallint  <br/> |外部、主要  <br/> |负载说明。 有关详细信息, 请参阅[PayloadDescription 表](payloaddescription.md)。 <br/> |
|**JitterInterArrival** <br/> |int  <br/> | <br/> |实时控制协议 (RTCP) 统计信息的平均网络抖动。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> | <br/> |视频会话期间的最大网络抖动。  <br/> |
|**RoundTrip** <br/> |int  <br/> | <br/> |从 RTCP 统计数据往返的时间。  <br/> |
|**RoundTripMax** <br/> |int  <br/> | <br/> |视频流的最大往返行程时间。  <br/> |
|**PacketLossRate** <br/> |十进制 (5, 4)  <br/> | <br/> |通话期间平均数据包丢失速率。  <br/> |
|**PacketLossRateMax** <br/> |十进制 (5, 4)  <br/> | <br/> |通话过程中观察到的最大数据包丢失。  <br/> |
|**PacketUtilization** <br/> |int  <br/> | <br/> |视频流的数据包计数 (实时传输协议、RTP)。  <br/> |
|**BandwidthEst** <br/> |int  <br/> | <br/> |视频流的带宽估计。  <br/> |
|**VideoResolution** <br/> |char (9)  <br/> | <br/> |以像素为单位的视频分辨率 (以像素为单位) 乘以像素高度。 报告为字符串。  <br/> |
|**VideoBitRateAvg** <br/> |int  <br/> | <br/> |视频流的平均比特率。  <br/> |
|**InboundVideoFrameRateAvg** <br/> |十进制 (9, 4)  <br/> | <br/> |收到的视频帧速率。  <br/> |
|**OutboundVideoFrameRateAvg** <br/> |十进制 (9, 4)  <br/> | <br/> |已发送视频帧速率。  <br/> |
|**VideoBitRateMax** <br/> |int  <br/> | <br/> |视频会话期间的最大视频比特率。  <br/> |
|**VideoFrameLossRate** <br/> |十进制 (9, 4)  <br/> | <br/> |丢失的视频帧总数的百分比。  <br/> |
|**VideoFEC** <br/> |bit  <br/> | <br/> |不可用。  <br/> |
|**VideoLocalFrameLossPercentageAvg** <br/> |十进制 (9, 4)  <br/> ||丢失的视频帧总数的百分比。  <br/> |
|**CIFQualityRatio** <br/> |tinyint  <br/> ||以通用交换格式 (CIF) 分辨率表示的通话百分比。  <br/> |
|**VGAQualityRatio** <br/> |tinyint  <br/> ||以 VGA 分辨率表示的通话百分比。  <br/> |
|**HD720QualityRatio** <br/> |tinyint  <br/> ||以 HD720 分辨率表示的通话百分比。  <br/> |
|**NoneDropRatio** <br/> |tinyint  <br/> ||不带帧丢弃的通话持续时间百分比。  <br/> |
|**BDropRatio** <br/> |tinyint  <br/> ||B 帧丢弃的通话持续时间百分比。  <br/> |
|**BPDropRatio** <br/> |tinyint  <br/> ||具有 BP 帧丢弃的通话持续百分比。  <br/> |
|**BPSPDropRatio** <br/> |tinyint  <br/> ||带有 BPSP 帧丢弃的通话持续时间百分比。  <br/> |
|**BPSPIDropRatio** <br/> |tinyint  <br/> ||带有 BPSPI 帧丢弃的通话持续时间百分比。  <br/> |
|**封** <br/> |bit  <br/> | <br/> |接收接收方的数据流数据。  <br/> |
|**出站** <br/> |bit  <br/> | <br/> |接收发件人端的数据流数据。  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> | <br/> |1表示流方向来自调用方的调用方。  <br/> 0表示流方向来自被调用方的调用方。  <br/> |
|**LossCongestionPercent** <br/> |float  <br/> ||指示通话处于损失拥塞状态的时间百分比。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**DelayCongestionPercent** <br/> |float  <br/> ||指示由于网络数据包的延迟到达而导致的阻塞的调用百分比。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**ContentionDetectedPercent** <br/> |float  <br/> ||表示呼叫竞争网络资源的时间百分比。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**BandwidthEstMin** <br/> |int  <br/> ||在通话期间测量的最小带宽估计量。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**BandwidthEstMax** <br/> |int  <br/> ||在通话期间测量的最大带宽估计量。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**BandwidthEstStdDev** <br/> |int  <br/> ||在通话过程中测量的带宽估计的标准偏差。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**BandwidthEstAvge** <br/> |int  <br/> ||通话期间测量的平均估计带宽量。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**LowBandwidthForMultiview** <br/> |float  <br/> ||终结点确定网络连接无法支持多种显示视频的调用的百分比。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||单向延迟的总金额。 相对单向延迟测量客户端与服务器之间的延迟。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||单向延迟的平均量。 相对单向延迟测量客户端与服务器之间的延迟。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||单向延迟的最大值。 相对单向延迟测量客户端与服务器之间的延迟。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||总单向爆发次数。 "Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 数据流处于不可预知的突发流量。 此指标测量客户端与服务器之间的数据流。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |int  <br/> ||总单向脉冲密度。 "Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 数据流处于不可预知的突发流量。 此指标测量客户端与服务器之间的数据流。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||总的单向脉冲持续时间。 "Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 数据流处于不可预知的突发流量。 此指标测量客户端与服务器之间的数据流。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||总的单向间隔发生次数。 "Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 其数据流可预料的猝发。间隙表示这些猝发之间的延迟。 此指标测量客户端与服务器之间的数据流。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||总单向间距密度。 "Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 其数据流可预料的猝发。间隙表示这些猝发之间的延迟。 此指标测量客户端与服务器之间的数据流。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||总的单间隔持续时间。 "Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 其数据流可预料的猝发。间隙表示这些猝发之间的延迟。 此指标测量客户端与服务器之间的数据流。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**VideoPacketLossRate** <br/> |十进制 (9, 4)  <br/> ||视频数据包丢失的速率。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**VideoAllocateBWAvg** <br/> |int  <br/> ||为视频分配的平均带宽量。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**SendCodecTypes** <br/> |smallint  <br/> |外表  <br/> |发件人使用的视频编解码器类型。 有关详细信息, 请参阅[CodecDescription 表](codecdescription.md)。 <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**SendResolutionWidth** <br/> |int  <br/> ||发件人使用的分辨率宽度。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**SendResolutionHeight** <br/> |int  <br/> ||发件人使用的分辨率高度。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**SendFrameRateAverage** <br/> |float  <br/> ||发件人使用的平均视频帧速率传输。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**SendBitRateMaximum** <br/> |int  <br/> ||发件人的最大比特率。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**SendBitRateAverage** <br/> |int  <br/> ||发件人的平均比特率。  <br/> |
|**SendVideoStreamsMax** <br/> |int  <br/> ||发件人使用的视频流的最大数量。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RecvCodecTypes** <br/> |smallint  <br/> |外表  <br/> |接收方使用的视频代码。 有关详细信息, 请参阅[CodecDescription 表](codecdescription.md)。 <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RecvResolutionWidth** <br/> |int  <br/> ||接收器使用的分辨率宽度。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RecvResolutionHeight** <br/> |int  <br/> ||接收方使用的分辨率高度。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RecvFrameRateAverage** <br/> |float  <br/> ||接收方使用的平均视频帧速率。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RecvBitRateMaximum** <br/> |int  <br/> ||接收方的最大比特率。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RecvBitRateAverage** <br/> |int  <br/> ||接收方的平均比特率。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RecvVideoStreamsMax** <br/> |int  <br/> ||接收方的最大视频流。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RecvVideoStreamsMin** <br/> |int  <br/> ||接收方的最小视频流。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**RecvVideoStreamsMode** <br/> |int  <br/> ||接收方的视频模式 (例如, 库或单流)。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**VideoPostFECPLR** <br/> |float  <br/> ||已应用转发纠错后的数据包丢失率。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**DynamicCapabilityPercent** <br/> |float  <br/> ||动态功能标志处于活动状态的时间百分比。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**ResolutionMin** <br/> |char (9)  <br/> ||通话过程中测量的最低分辨率。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**LowBitRateCallPercent** <br/> |float  <br/> ||低于低比特率阈值的通话百分比 (70 千位/秒)。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**LowFrameRateCallPercent** <br/> |float  <br/> ||低于低帧速率阈值 (每秒7.5 帧, 入站) 的通话百分比。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**LowResolutionCallPercent** <br/> |float  <br/> ||以最低分辨率发生的通话的百分比。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**DurationSeconds** <br/> |float  <br/> ||通话长度 (以秒为单位)。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
|**IsAggregatedData** <br/> |bit  <br/> ||指示数据是否已从多个调用聚合。  <br/> 此列已在 Microsoft Lync Server 2013 中引入。  <br/> |
   

