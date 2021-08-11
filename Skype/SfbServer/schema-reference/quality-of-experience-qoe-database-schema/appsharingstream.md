---
title: AppSharingStream 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: AppSharingStream 表包含用于应用程序共享的网络流的用户体验质量指标。 此表在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 68f43e9d783cd0f30d89bf9f4f13c0fe5329bbf3755e6b2c3eba897b86ead6c5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54329347"
---
# <a name="appsharingstream-table"></a>AppSharingStream 表
 
AppSharingStream 表包含用于应用程序共享的网络流的用户体验质量指标。 此表在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dateTime  <br/> |主、外  <br/> |会话开始的日期和时间。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主、外  <br/> |用于区分在相同日期和时间开始的会话的顺序标识符。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |主、外  <br/> | 请参阅 [MediaLine Table](./medialine-0.md)。 <br/> |
|**StreamID** <br/> |int  <br/> |主  <br/> |应用程序共享流的唯一标识符。  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||在 RTP 数据包到达之间检测到的平均抖动率。（抖动是针对呼叫的“不稳定性”的度量。）高抖动值通常是由拥塞或媒体服务器超载造成的，从而导致音频失真或丢失。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||在 RTP 数据包到达之间检测到的最大抖动率。（抖动是针对呼叫的“不稳定性”的度量。）高抖动值通常是由拥塞或媒体服务器超载造成的，从而导致音频失真或丢失。  <br/> |
|**RoundTrip** <br/> |int  <br/> ||实时传输协议数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 200 毫秒被视为质量可接受。  <br/> 高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||实时传输协议数据包来往于另一个终结点所需的最大时间量（以毫秒为单位）。来回行程的时间小于或等于 200 毫秒被视为质量可接受。  <br/> 高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。  <br/> |
|**PacketLossRate** <br/> |float  <br/> ||平均实时传输协议 (RTP) 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时，即发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。数据包丢失通常导致音频失真或丢失。  <br/> |
|**PacketLossRateMax** <br/> |float  <br/> ||最大实时传输协议 (RTP) 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时，即发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。数据包丢失通常导致音频失真或丢失。  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||发送的数据包数。  <br/> |
|**BandwidthEst** <br/> |int  <br/> ||在会话末尾可用的单向带宽的估计值。以每秒的位数的形式报告。  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||应用程序共享负载的描述。  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||单向延迟的总量。相对单向延迟用于度量客户端和服务器之间的延迟。  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||单向延迟的平均量。相对单向延迟用于度量客户端和服务器之间的延迟。  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||单向延迟的最大量。相对单向延迟用于度量客户端和服务器之间的延迟。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||单向突发总发生次数。 "突发"传输是数据流以不可预知的突发方式（与稳定流相反）的传输。 此指标用于度量客户端和服务器之间的数据流。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||单向突发总密度。 "突发"传输是数据流以不可预知的突发方式（与稳定流相反）的传输。 此指标用于度量客户端和服务器之间的数据流。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||单向突发总持续时间。 "突发"传输是数据流以不可预知的突发方式（与稳定流相反）的传输。 此指标用于度量客户端和服务器之间的数据流。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||单向间隙总发生次数。 "突发"传输是数据流以不可预知的突发方式（与稳定流相反）的传输;间隙指示这些突发之间的延迟。 此指标用于度量客户端和服务器之间的数据流。  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||单向间隙总密度。 "突发"传输是数据流以不可预知的突发方式（与稳定流相反）的传输;间隙指示这些突发之间的延迟。 此指标用于度量客户端和服务器之间的数据流。  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||单向间隙总持续时间。 "突发"传输是数据流以不可预知的突发方式（与稳定流相反）的传输;间隙指示这些突发之间的延迟。 此指标用于度量客户端和服务器之间的数据流。  <br/> |
|**ApplicationSharingType** <br/> |varChar (256)   <br/> ||应用程序角色（共享者或查看者）和内容类型。  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |float  <br/> ||远程桌面协议 (RDP) 图块的总处理时间。总时间量越大，查看体验的延迟就越长。  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |float  <br/> ||远程桌面协议 (RDP) 图块的平均处理时间。总时间量越大，查看体验的延迟就越长。  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |float  <br/> ||远程桌面协议 (RDP) 图块的最大处理时间。总时间量越大，查看体验的延迟就越长。  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||远程桌面协议 (RDP) 图块的处理时间中的突发发生次数。 "突发"传输是数据流以不可预知的突发方式（与稳定流相反）的传输。  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |float  <br/> ||远程桌面协议 (RDP) 图块的处理时间中的突发密度。 "突发"传输是数据流以不可预知的突发方式（与稳定流相反）的传输。  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |float  <br/> ||远程桌面协议 (RDP) 图块的处理时间中的突发持续时间。 "突发"传输是数据流以不可预知的突发方式（与稳定流相反）的传输。  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||远程桌面协议 (RDP) 图块的处理时间中的间隙发生次数。  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |float  <br/> ||远程桌面协议 (RDP) 图块的处理时间中的间隙密度。间隙密度越低，查看体验就越佳。  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |float  <br/> ||远程桌面协议 (RDP) 图块的处理时间中的间隙持续时间。间隙持续时间越短，查看体验就越佳。  <br/> |
|**CaptureTileRateTotal** <br/> |float  <br/> ||图块的总捕获率（以每秒的图块数为单位）。  <br/> |
|**CaptureTileRateAverage** <br/> |float  <br/> ||图块的平均捕获率（以每秒的图块数为单位）。  <br/> |
|**CaptureTileRateMax** <br/> |float  <br/> ||图块的最大捕获率（以每秒的图块数为单位）。  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |int  <br/> ||图块的捕获率的突发发生次数（以每秒的图块数为单位）。  <br/> |
|**CaptureTileRateBurstDensity** <br/> |float  <br/> ||图块的捕获率的突发密度（以每秒的图块数为单位）。  <br/> |
|**CaptureTileRateBurstDuration** <br/> |float  <br/> ||图块的捕获率的突发持续时间（以每秒的图块数为单位）。  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||图块的捕获率的间隙发生次数（以每秒的图块数为单位）。  <br/> |
|**CaptureTileRateGapDensity** <br/> |float  <br/> ||图块的捕获率的间隙密度（以每秒的图块数为单位）。  <br/> |
|**CaptureTileRateGapDuration** <br/> |float  <br/> ||图块的捕获率的间隙持续时间（以每秒的图块数为单位）。  <br/> |
|**SpoiledTilePercentTotal** <br/> |float  <br/> ||未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的总百分比。  <br/> |
|**SpoiledTilePercentAverage** <br/> |float  <br/> ||未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的平均百分比。  <br/> |
|**SpoiledTilePercentMax** <br/> |float  <br/> ||未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的最大百分比。  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的突发发生次数。  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |float  <br/> ||未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的突发密度。  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |float  <br/> ||未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的突发持续时间。  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的间隙发生次数。  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |float  <br/> ||未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的间隙密度。  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |float  <br/> ||未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的间隙持续时间。  <br/> |
|**ScrapingFrameRateTotal** <br/> |float  <br/> ||从图形源擦除的总帧数。  <br/> |
|**ScrapingFrameRateAverage** <br/> |float  <br/> ||从图形源擦除的平均帧数。  <br/> |
|**ScrapingFrameRateMax** <br/> |float  <br/> ||从图形源擦除的最大帧数。  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||从图形源擦除的帧数的突发发生次数。  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |float  <br/> ||从图形源擦除的帧数的突发密度。  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |float  <br/> ||从图形源擦除的帧数的突发持续时间。  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||从图形源擦除的帧数的间隙发生次数。  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |float  <br/> ||从图形源擦除的帧数的间隙密度。  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |float  <br/> ||从图形源擦除的帧数的间隙持续时间。  <br/> |
|**IncomingTileRateTotal** <br/> |float  <br/> ||查看者收到的总传入帧速率。  <br/> |
|**IncomingTileRateAverage** <br/> |float  <br/> ||查看者收到的平均传入帧速率。  <br/> |
|**IncomingTileRateMax** <br/> |float  <br/> ||查看者收到的最大传入图块速率。  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||查看者收到的传入图块速率的突发发生次数。  <br/> |
|**IncomingTileRateBurstDensity** <br/> |float  <br/> ||查看者收到的传入图块速率的突发密度。  <br/> |
|**IncomingTileRateBurstDuration** <br/> |float  <br/> ||查看者收到的传入图块速率的突发持续时间。  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||查看者收到的传入图块速率的间隙发生次数。  <br/> |
|**IncomingTileRateGapDensity** <br/> |float  <br/> ||查看者收到的传入图块速率的间隙密度。  <br/> |
|**IncomingTileRateGapDuration** <br/> |float  <br/> ||查看者收到的传入图块速率的间隙持续时间。  <br/> |
|**IncomingFrameRateTotal** <br/> |float  <br/> ||查看者收到的总传入帧速率。  <br/> |
|**IncomingFrameRateAverage** <br/> |float  <br/> ||查看者收到的平均传入帧速率。  <br/> |
|**IncomingFrameRateMax** <br/> |float  <br/> ||查看者收到的最大传入帧速率。  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||查看者收到的传入帧速率的突发发生次数。  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |float  <br/> ||查看者收到的传入帧速率的突发密度。  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |float  <br/> ||查看者收到的传入帧速率的突发持续时间。  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||查看者收到的传入帧速率的间隙发生次数。  <br/> |
|**IncomingFrameRateGapDensity** <br/> |float  <br/> ||查看者收到的传入帧速率的间隙密度。  <br/> |
|**IncomingFrameRateDuration** <br/> |float  <br/> ||查看者收到的传入帧速率的间隙持续时间。  <br/> |
|**OutgoingTileRateTotal** <br/> |float  <br/> ||发送者的总传出图块速率。  <br/> |
|**OutgoingTileRateAverage** <br/> |float  <br/> ||发送者的平均传出图块速率。  <br/> |
|**OutgoingTileRateMax** <br/> |float  <br/> ||发送者的最大传出图块速率。  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||发送者的传出图块速率的突发发生次数。  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |float  <br/> ||发送者的传出图块速率的突发密度。  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |float  <br/> ||发送者的传出图块速率的突发持续时间。  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||发送者的传出图块速率的间隙发生次数。  <br/> |
|**OutgoingTileRateGapDensity** <br/> |float  <br/> ||发送者的传出图块速率的间隙密度。  <br/> |
|**OutgoingTileRateGapDuration** <br/> |float  <br/> ||发送者的传出图块速率的间隙持续时间。  <br/> |
|**OutgoingFrameRateTotal** <br/> |float  <br/> ||发送者的总传出帧速率。  <br/> |
|**OutgoingFrameRateAverage** <br/> |float  <br/> ||发送者的平均传出帧速率。  <br/> |
|**OutgoingFrameRateMax** <br/> |float  <br/> ||发送者的最大传出帧速率。  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||发送者的传出帧速率的突发发生次数。  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |float  <br/> ||发送者的传出帧速率的突发密度。  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |float  <br/> ||发送者的传出帧速率的突发持续时间。  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||发送者的传出帧速率的间隙发生次数。  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |float  <br/> ||发送者的传出帧速率的间隙密度。  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |float  <br/> ||发送者的传出帧速率的间隙持续时间。  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||平均视频分辨率高度（以像素为单位）。  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||平均视频分辨率宽度（以像素为单位）。  <br/> |
|**入站** <br/> |bit  <br/> ||入站传输的平均帧速率（以每秒帧数为单位）。  <br/> |
|**出站** <br/> |bit  <br/> ||出站传输的平均帧速率（以每秒帧数为单位）。  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1 表示流方向是从呼叫者到被叫方。  <br/> 0 表示流方向是从被叫方到呼叫者。  <br/> |
