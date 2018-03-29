---
title: AppSharingStream 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: AppSharingStream 表中包含用于应用程序共享的网络流的体验质量指标。 在 Microsoft Lync Server 2013 引入了此表。
ms.openlocfilehash: a10370814da5630a6d453b2ff4cad44b16b74ff1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="appsharingstream-table"></a>AppSharingStream 表
 
AppSharingStream 表中包含用于应用程序共享的网络流的体验质量指标。 在 Microsoft Lync Server 2013 引入了此表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |日期时间  <br/> |主键和外  <br/> |日期和启动会话的时间。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主键和外  <br/> |连续用来区分同一天的日期，并在同一时间启动的会话的标识符。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |主键和外  <br/> |表示在调用中使用的视频线的类型。 允许的值包括：  <br/> 0-音频  <br/> 1-视频  <br/> 2-全景视频  <br/> 3-应用程序/桌面共享  <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |应用程序共享流的唯一标识符。  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||在 RTP 数据包到达之间检测到的平均抖动率。（抖动是针对呼叫的“不稳定性”的度量。）高抖动值通常是由拥塞或媒体服务器超载造成的，从而导致音频失真或丢失。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||RTP 数据包到达之间检测到的最大抖动。 （抖动是一种"抖动"的调用）。高抖动值通常由拥塞或重载的媒体服务器上，并导致扭曲或丢失的音频。  <br/> |
|**往返** <br/> |int  <br/> ||实时传输协议数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 200 毫秒被视为质量可接受。  <br/> 高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||最大的量 （以毫秒为单位） 所需的实时传输协议数据包来旅行到另一个终结点，然后再设置。 来回行程的时间小于或等于 200 毫秒被视为质量可接受。  <br/> 高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。  <br/> |
|**PacketLossRate** <br/> |float  <br/> ||平均实时传输协议 (RTP) 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时，即发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。数据包丢失通常导致音频失真或丢失。  <br/> |
|**PacketLossRateMax** <br/> |float  <br/> ||实时传输协议 (RTP) 数据包丢失的最大速率。 （丢失数据包的情况发生在 RTP 数据包，用于在 Internet 上传输音频和视频的协议无法到达其目的地时）。高丢失率通常所导致的拥堵。缺少的带宽;无线拥挤或无干扰;或重载的媒体服务器。 数据包丢失通常导致音频失真或丢失。  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||发送的数据包数。  <br/> |
|**BandwidthEst** <br/> |int  <br/> ||估计的单向会话的末尾的可用带宽。 报告以位 / 秒。  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||应用程序共享负载的描述。  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||单向延迟的总金额。 相对的单向延迟测量客户端和服务器之间的延迟。  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||单向延迟平均量。 相对的单向延迟测量客户端和服务器之间的延迟。  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||单向延迟的最大数量。 相对的单向延迟测量客户端和服务器之间的延迟。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||总的单向突发事件。 "突发"传输是传输其中的数据排列在不可预知的突发情况，而不是稳定。 此指标用于衡量客户端和服务器之间的数据流。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||总的单向爆发密度。 "突发"传输是传输其中的数据排列在不可预知的突发情况，而不是稳定。 此指标用于衡量客户端和服务器之间的数据流。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||总的单向脉冲持续时间。 "突发"传输是传输其中的数据排列在不可预知的突发情况，而不是稳定。 此指标用于衡量客户端和服务器之间的数据流。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||总的单向差距出现次数。 "突发"传输是传输其中的数据排列在不可预知的突发情况相对稳定;间隙表示这些突发情况之间的延迟。 此指标用于衡量客户端和服务器之间的数据流。  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||总的单向间隙密度。 "突发"传输是传输其中的数据排列在不可预知的突发情况相对稳定;间隙表示这些突发情况之间的延迟。 此指标用于衡量客户端和服务器之间的数据流。  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||总的单向差距持续时间。 "突发"传输是传输其中的数据排列在不可预知的突发情况相对稳定;间隙表示这些突发情况之间的延迟。 此指标用于衡量客户端和服务器之间的数据流。  <br/> |
|**ApplicationSharingType** <br/> |varChar(256)  <br/> ||应用程序角色 （共享或查看器） 和内容类型。  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |float  <br/> ||远程桌面协议 (RDP) 拼贴的总处理时间。 高总和等同于观赏体验中较长的延迟。  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |float  <br/> ||平铺显示远程桌面协议 (RDP) 的平均处理时间。 高总和等同于观赏体验中较长的延迟。  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |float  <br/> ||远程桌面协议 (RDP) 平铺的最长处理时间。 高总和等同于观赏体验中较长的延迟。  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||对于远程桌面协议 (RDP) 图块的处理时间在突发事件。 "突发"传输是传输其中的数据排列在不可预知的突发情况，而不是稳定。  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |float  <br/> ||对于远程桌面协议 (RDP) 图块的处理时间在爆发密度。 "突发"传输是传输其中的数据排列在不可预知的突发情况，而不是稳定。  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |float  <br/> ||爆发在远程桌面协议 (RDP) 拼贴的处理时间的持续时间。 "突发"传输是传输其中的数据排列在不可预知的突发情况，而不是稳定。  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||对于远程桌面协议 (RDP) 图块的处理时间间隔出现次数。  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |float  <br/> ||在远程桌面协议 (RDP) 的处理时间间隔密度平铺。 间隙低密度等于更好的观赏体验。  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |float  <br/> ||远程桌面协议 (RDP) 拼贴的处理时间间隔的持续时间。 短间隔持续时间等于更好的观赏体验。  <br/> |
|**CaptureTileRateTotal** <br/> |float  <br/> ||（中图块每秒） 的捕获的总速率。  <br/> |
|**CaptureTileRateAverage** <br/> |float  <br/> ||平均速率 （以每秒的图块） 捕获的拼贴。  <br/> |
|**CaptureTileRateMax** <br/> |float  <br/> ||（中图块每秒） 的捕获的最大速率。  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |在 t  <br/> ||突发事件 （中每秒的图块） 的捕获率。  <br/> |
|**CaptureTileRateBurstDensity** <br/> |float  <br/> ||（中图块每秒） 的捕获率爆发密度。  <br/> |
|**CaptureTileRateBurstDuration** <br/> |float  <br/> ||（中图块每秒） 的捕获率爆发持续时间。  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||（中图块每秒） 的捕获率差距出现。  <br/> |
|**CaptureTileRateGapDensity** <br/> |float  <br/> ||（中图块每秒） 的捕获率差距密度。  <br/> |
|**CaptureTileRateGapDuration** <br/> |float  <br/> ||捕获的拼贴 （以每秒的图块） 的收益率差距持续时间。  <br/> |
|**SpoiledTilePercentTotal** <br/> |float  <br/> ||总百分比的内容没有到达查看器，但已改为丢弃和覆盖新的内容。  <br/> |
|**SpoiledTilePercentAverage** <br/> |float  <br/> ||未达到查看器，但已改为丢弃并覆盖新的内容的内容的平均百分比。  <br/> |
|**SpoiledTilePercentMax** <br/> |float  <br/> ||未达到查看器，但已改为丢弃并覆盖新的内容的内容的最大百分比。  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||突发性发作的内容没有到达查看器，但已改为丢弃和覆盖新的内容。  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |float  <br/> ||突发性密度的内容没有到达查看器，但已改为丢弃和覆盖新的内容。  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |float  <br/> ||爆发持续时间未达到查看器，但已改为丢弃并覆盖新的内容的内容。  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||间隙发作的内容没有到达查看器，但已改为丢弃和覆盖新的内容。  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |float  <br/> ||间隙密度未达到查看器，但已改为丢弃并覆盖新的内容的内容。  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |float  <br/> ||缺口持续时间未达到查看器，但已改为丢弃并覆盖新的内容的内容。  <br/> |
|**ScrapingFrameRateTotal** <br/> |float  <br/> ||总从图形源攒钱的帧数。  <br/> |
|**ScrapingFrameRateAverage** <br/> |float  <br/> ||平均的攒钱的图形来源的帧数。  <br/> |
|**ScrapingFrameRateMax** <br/> |float  <br/> ||最大图形来源攒钱的帧数。  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||从图形源攒钱的帧中爆发事件。  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |float  <br/> ||从图形源攒钱的帧中爆发密度。  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |float  <br/> ||从图形源攒钱的帧中爆发持续时间。  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||差距从图形源攒钱的帧中的出现次数。  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |float  <br/> ||差距从图形源攒钱的帧中的密度。  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |float  <br/> ||差距从图形源攒钱的帧持续时间。  <br/> |
|**IncomingTileRateTotal** <br/> |float  <br/> ||查看接收到的总传入帧速率。  <br/> |
|**IncomingTileRateAverage** <br/> |float  <br/> ||查看接收到的平均接收的帧速率。  <br/> |
|**IncomingTileRateMax** <br/> |float  <br/> ||最大传入平铺率，观察者接收到。  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||传入的平铺率爆发出现，观察者接收到。  <br/> |
|**IncomingTileRateBurstDensity** <br/> |float  <br/> ||爆发密度比率的平铺中，观察者接收到。  <br/> |
|**IncomingTileRateBurstDuration** <br/> |float  <br/> ||平铺比率在爆发持续时间，观察者接收到。  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||查看器接收到差距出现在平铺的比率。  <br/> |
|**IncomingTileRateGapDensity** <br/> |float  <br/> ||为查看器接收传入铺率差距密度。  <br/> |
|**IncomingTileRateGapDuration** <br/> |float  <br/> ||为查看器接收到图块比率差距持续时间。  <br/> |
|**IncomingFrameRateTotal** <br/> |float  <br/> ||查看接收到的总传入帧速率。  <br/> |
|**IncomingFrameRateAverage** <br/> |float  <br/> ||查看接收到的平均接收的帧速率。  <br/> |
|**IncomingFrameRateMax** <br/> |float  <br/> ||为查看器接收到的最大传入帧速率。  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||中输入的帧频爆发事件，观察者接收到。  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |float  <br/> ||在传入帧速率爆发密度，观察者接收到。  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |float  <br/> ||在传入帧速率爆发持续时间，观察者接收到。  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||在为查看器接收的传入帧速率差距出现次数。  <br/> |
|**IncomingFrameRateGapDensity** <br/> |float  <br/> ||在为查看器接收的传入帧速率差距密度。  <br/> |
|**IncomingFrameRateDuration** <br/> |float  <br/> ||为查看器接收的传入帧速率差距持续时间。  <br/> |
|**OutgoingTileRateTotal** <br/> |float  <br/> ||发件人的总传出平铺速率。  <br/> |
|**OutgoingTileRateAverage** <br/> |float  <br/> ||发件人的平均传出平铺速率。  <br/> |
|**OutgoingTileRateMax** <br/> |float  <br/> ||发件人的最大传出平铺速率。  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||发件人中传出的平铺率突发事件。  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |float  <br/> ||发件人中传出的平铺率爆发密度。  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |float  <br/> ||发件人中传出的平铺率爆发持续时间。  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||间隙发件人中传出的平铺率的发作。  <br/> |
|**OutgoingTileRateGapDensity** <br/> |float  <br/> ||发件人传出平铺率差距密度。  <br/> |
|**OutgoingTileRateGapDuration** <br/> |float  <br/> ||发件人的传出平铺率差距持续时间。  <br/> |
|**OutgoingFrameRateTotal** <br/> |float  <br/> ||发件人的总传出帧速率。  <br/> |
|**OutgoingFrameRateAverage** <br/> |float  <br/> ||发件人的平均传出帧速率。  <br/> |
|**OutgoingFrameRateMax** <br/> |float  <br/> ||发件人的最大传出帧速率。  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||发件人中传出的帧速率突发事件。  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |float  <br/> ||发件人在发送的帧速率爆发密度。  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |float  <br/> ||发件人在发送的帧速率爆发持续时间。  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||间隙发件人在发送的帧速率的发作。  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |float  <br/> ||在发件人发送的帧速率差距密度。  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |float  <br/> ||发件人发送的帧速率差距持续时间。  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||平均的视频分辨率高度 （以像素为单位）。  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||平均的视频分辨率宽度 （以像素为单位）。  <br/> |
|**入站** <br/> |bit  <br/> ||平均帧速率 （以每秒的帧） 的入站传输。  <br/> |
|**出站** <br/> |bit  <br/> ||出站传输的平均帧速率 （以每秒的帧）。  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1 表示流方向是从调用方对被调用方。  <br/> 0 表示流方向是从被调用方调用方。  <br/> |
   

