---
title: AppSharingStream 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: AppSharingStream 表包含用于应用程序共享的网络流的用户体验质量指标。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 8e01cc4d35269b34e3e6fba13fd331139e3f7ae7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30877012"
---
# <a name="appsharingstream-table"></a>AppSharingStream 表
 
AppSharingStream 表包含用于应用程序共享的网络流的用户体验质量指标。 此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |dateTime  <br/> |主、 外  <br/> |日期和时间的会话开始。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主、 外  <br/> |用于区分在相同日期和相同时间开始的会话的顺序标识符。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |主、 外  <br/> | 请参阅[自 MediaLine Table](https://docs.microsoft.com/skypeforbusiness/schema-reference/quality-of-experience-qoe-database-schema/medialine-0)。 <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |应用程序共享流的唯一标识符。  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||在 RTP 数据包到达之间检测到的平均抖动率。（抖动是针对呼叫的“不稳定性”的度量。）高抖动值通常是由拥塞或媒体服务器超载造成的，从而导致音频失真或丢失。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||最大 RTP 数据包到达之间检测的抖动。 （抖动是一种呼叫"抖动"）。高抖动值通常由拥塞或重载的媒体服务器上，并导致音频失真或丢失。  <br/> |
|**RoundTrip** <br/> |int  <br/> ||实时传输协议数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 200 毫秒被视为质量可接受。  <br/> 高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||最大量 （以毫秒计） 所需的实时传输协议数据包传输到另一个终结点，然后再返回。 来回行程的时间小于或等于 200 毫秒被视为质量可接受。  <br/> 高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。  <br/> |
|**PacketLossRate** <br/> |float  <br/> ||平均实时传输协议 (RTP) 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时，即发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。数据包丢失通常导致音频失真或丢失。  <br/> |
|**PacketLossRateMax** <br/> |float  <br/> ||实时传输协议 (RTP) 数据包丢失的最大速率。 （数据包丢失发生时未能达到其目标 RTP 数据包，用于通过 Internet 传输音频和视频的协议）。由拥塞; 通常导致高丢失率缺少的带宽;无线拥塞或干扰;或重载的媒体服务器。 数据包丢失通常导致音频失真或丢失。  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||发送的数据包的数目。  <br/> |
|**BandwidthEst** <br/> |int  <br/> ||可在会话结束的估计单向带宽。 报告以位 / 秒。  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||应用程序共享负载的描述。  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||单向滞后时间总量。 相对单向延迟测量客户端和服务器之间的延迟。  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||单向延迟的平均量。 相对单向延迟测量客户端和服务器之间的延迟。  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||最大单向滞后时间量。 相对单向延迟测量客户端和服务器之间的延迟。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||总单向的突发发生次数。 "突发"传输是其中数据排列中而不是稳定的不可预知间歇传输。 此指标来衡量客户端和服务器之间的数据流。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||总单向的突发密度。 "突发"传输是其中数据排列中而不是稳定的不可预知间歇传输。 此指标来衡量客户端和服务器之间的数据流。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||总单向的突发持续时间。 "突发"传输是其中数据排列中而不是稳定的不可预知间歇传输。 此指标来衡量客户端和服务器之间的数据流。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||总单向的间隙发生次数。 "突发"传输是传输其中数据排列中而不是稳定流; 无法预料间歇间隙指示这些间歇之间的延迟。 此指标来衡量客户端和服务器之间的数据流。  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||总单向的间隙密度。 "突发"传输是传输其中数据排列中而不是稳定流; 无法预料间歇间隙指示这些间歇之间的延迟。 此指标来衡量客户端和服务器之间的数据流。  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||总单向的间隙持续时间。 "突发"传输是传输其中数据排列中而不是稳定流; 无法预料间歇间隙指示这些间歇之间的延迟。 此指标来衡量客户端和服务器之间的数据流。  <br/> |
|**ApplicationSharingType** <br/> |varChar(256)  <br/> ||应用程序角色 （共享者或查看器） 和内容类型。  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |float  <br/> ||远程桌面协议 (RDP) 图块的总处理时间。 更高的总等于查看体验中较长的延迟。  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |float  <br/> ||远程桌面协议 (RDP) 的平均处理时间平铺。 更高的总等于查看体验中较长的延迟。  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |float  <br/> ||远程桌面协议 (RDP) 图块的最长处理时间。 更高的总等于查看体验中较长的延迟。  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||在远程桌面协议 (RDP) 图块的处理时间突发发生次数。 "突发"传输是其中数据排列中而不是稳定的不可预知间歇传输。  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |float  <br/> ||远程桌面协议 (RDP) 图块的处理时间中的突发密度。 "突发"传输是其中数据排列中而不是稳定的不可预知间歇传输。  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |float  <br/> ||突发持续时间在远程桌面协议 (RDP) 图块的处理时间。 "突发"传输是其中数据排列中而不是稳定的不可预知间歇传输。  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||远程桌面协议 (RDP) 图块的处理时间中的间隙发生次数。  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |float  <br/> ||远程桌面协议 (RDP) 图块的处理时间中的间隙密度。 低的间隙密度等于更好的观看体验。  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |float  <br/> ||远程桌面协议 (RDP) 图块的处理时间间隙持续时间。 简短的间隙持续时间相当于更好的观看体验。  <br/> |
|**CaptureTileRateTotal** <br/> |float  <br/> ||（以每秒的图块） 捕获图块的总速率。  <br/> |
|**CaptureTileRateAverage** <br/> |float  <br/> ||平均速率 （以每秒的图块） 捕获图块数为单位。  <br/> |
|**CaptureTileRateMax** <br/> |float  <br/> ||（以每秒的图块） 捕获图块的最大速率。  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |int  <br/> ||速率 （以每秒的图块） 捕获图块的突发发生次数。  <br/> |
|**CaptureTileRateBurstDensity** <br/> |float  <br/> ||（以每秒的图块） 捕获图块速率的突发密度。  <br/> |
|**CaptureTileRateBurstDuration** <br/> |float  <br/> ||（以每秒的图块） 捕获图块速率的突发持续时间。  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||（以每秒的图块） 捕获图块速率的间隙发生次数。  <br/> |
|**CaptureTileRateGapDensity** <br/> |float  <br/> ||（以每秒的图块） 捕获图块速率的间隙密度。  <br/> |
|**CaptureTileRateGapDuration** <br/> |float  <br/> ||（以每秒的图块） 捕获图块速率的间隙持续时间。  <br/> |
|**SpoiledTilePercentTotal** <br/> |float  <br/> ||未送达查看器，但已而被丢弃和已被新鲜内容覆盖的内容的总百分比。  <br/> |
|**SpoiledTilePercentAverage** <br/> |float  <br/> ||未送达查看器，但已而被丢弃和已被新鲜内容覆盖的内容的平均百分比。  <br/> |
|**SpoiledTilePercentMax** <br/> |float  <br/> ||未送达查看器，但已而被丢弃和已被新鲜内容覆盖的内容的最大百分比。  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||突发发生次数未到达查看器，但已而被丢弃和已被新鲜内容覆盖的内容。  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |float  <br/> ||突发密度未到达查看器，但已而被丢弃和已被新鲜内容覆盖的内容。  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |float  <br/> ||突发持续时间没有到达查看器，但已而被丢弃和已被新鲜内容覆盖的内容。  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||未送达查看器，但已而被丢弃和已被新鲜内容覆盖的内容的间隙发生次数。  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |float  <br/> ||未送达查看器，但已而被丢弃和已被新鲜内容覆盖的内容的间隙密度。  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |float  <br/> ||未送达查看器，但已而被丢弃和已被新鲜内容覆盖的内容的间隙持续时间。  <br/> |
|**ScrapingFrameRateTotal** <br/> |float  <br/> ||总从图形源擦除的帧数。  <br/> |
|**ScrapingFrameRateAverage** <br/> |float  <br/> ||平均从图形源擦除的帧数。  <br/> |
|**ScrapingFrameRateMax** <br/> |float  <br/> ||最大从图形源擦除的帧数。  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||从图形源擦除的帧数的突发发生次数。  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |float  <br/> ||从图形源擦除的帧数的突发密度。  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |float  <br/> ||从图形源擦除的帧数的突发持续时间。  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||从图形源擦除的帧数的间隙发生次数。  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |float  <br/> ||从图形源擦除的帧数的间隙密度。  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |float  <br/> ||从图形源擦除的帧数的间隙持续时间。  <br/> |
|**IncomingTileRateTotal** <br/> |float  <br/> ||查看者收到的总传入帧速率。  <br/> |
|**IncomingTileRateAverage** <br/> |float  <br/> ||查看者收到的平均传入帧速率。  <br/> |
|**IncomingTileRateMax** <br/> |float  <br/> ||查看者收到，最大传入图块速率。  <br/> |
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
|**OutgoingTileRateTotal** <br/> |float  <br/> ||发件人的总传出图块速率。  <br/> |
|**OutgoingTileRateAverage** <br/> |float  <br/> ||发件人的平均传出图块速率。  <br/> |
|**OutgoingTileRateMax** <br/> |float  <br/> ||发件人的最大传出图块速率。  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||发送者的传出图块速率的突发发生次数。  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |float  <br/> ||发送者的传出图块速率的突发密度。  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |float  <br/> ||发件人的传出图块速率的突发持续时间。  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||间隙发生次数的传出图块速率的发件人。  <br/> |
|**OutgoingTileRateGapDensity** <br/> |float  <br/> ||发送者的传出图块速率的间隙密度。  <br/> |
|**OutgoingTileRateGapDuration** <br/> |float  <br/> ||发送者的传出图块速率的间隙持续时间。  <br/> |
|**OutgoingFrameRateTotal** <br/> |float  <br/> ||发件人的总传出帧速率。  <br/> |
|**OutgoingFrameRateAverage** <br/> |float  <br/> ||发件人的平均传出帧速率。  <br/> |
|**OutgoingFrameRateMax** <br/> |float  <br/> ||发件人的最大传出帧速率。  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||发送者的传出帧速率的突发发生次数。  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |float  <br/> ||发送者的传出帧速率的突发密度。  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |float  <br/> ||发件人的传出帧速率的突发持续时间。  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||间隙发生次数的传出帧速率的发件人。  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |float  <br/> ||发送者的传出帧速率的间隙密度。  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |float  <br/> ||发送者的传出帧速率的间隙持续时间。  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||平均视频分辨率高度，以像素为单位。  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||平均视频分辨率宽度，以像素为单位。  <br/> |
|**入站** <br/> |bit  <br/> ||入站传输的平均帧速率 （以每秒帧数）。  <br/> |
|**出站** <br/> |bit  <br/> ||出站传输的平均帧速率 （以每秒帧数）。  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1 表示流方向从呼叫者到被叫方。  <br/> 0 表示流方向从被叫方到呼叫者。  <br/> |
   

