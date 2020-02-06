---
title: AppSharingStream 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
description: AppSharingStream 表包含用于应用程序共享的网络流的体验指标的质量。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 1ebcfe16fe5863bcb3046e88ba5cdc2079f22a9c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41811100"
---
# <a name="appsharingstream-table"></a>AppSharingStream 表
 
AppSharingStream 表包含用于应用程序共享的网络流的体验指标的质量。 此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |从中  <br/> |主、外部  <br/> |会话开始的日期和时间。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主、外部  <br/> |用于区分在同一日期和同一时间启动的会话的顺序标识符。  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |主、外部  <br/> | 请参阅[MediaLine 表](https://docs.microsoft.com/skypeforbusiness/schema-reference/quality-of-experience-qoe-database-schema/medialine-0)。 <br/> |
|**StreamID** <br/> |int  <br/> |Primary  <br/> |应用程序共享流的唯一标识符。  <br/> |
|**JitterInterArrival** <br/> |int  <br/> ||在 RTP 数据包到达之间检测到的平均抖动率。（抖动是针对呼叫的“不稳定性”的度量。）高抖动值通常是由拥塞或媒体服务器超载造成的，从而导致音频失真或丢失。  <br/> |
|**JitterInterArrivalMax** <br/> |int  <br/> ||在 RTP 数据包到达之间检测到最大抖动。 （抖动是指通话的 "shakiness" 的衡量。）高抖动值通常由拥塞或过载的媒体服务器导致，并导致失真或丢失的音频。  <br/> |
|**RoundTrip** <br/> |int  <br/> ||实时传输协议数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 200 毫秒被视为质量可接受。  <br/> 高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。  <br/> |
|**RoundTripMax** <br/> |int  <br/> ||实时传输协议数据包传送到另一个终结点和后端所需的最大值（以毫秒为单位）。 来回行程的时间小于或等于 200 毫秒被视为质量可接受。  <br/> 高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。  <br/> |
|**PacketLossRate** <br/> |float  <br/> ||平均实时传输协议 (RTP) 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时，即发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。数据包丢失通常导致音频失真或丢失。  <br/> |
|**PacketLossRateMax** <br/> |float  <br/> ||实时传输协议（RTP）数据包丢失的最大速率。 （当 RTP 数据包（用于在 Internet 上传输音频和视频的协议）无法访问目标时，将发生数据包丢失。）高损失率通常由拥塞引起;缺少带宽;无线拥挤或干扰;或重载的媒体服务器。 数据包丢失通常导致音频失真或丢失。  <br/> |
|**PacketUtilization** <br/> |int  <br/> ||发送的数据包数。  <br/> |
|**BandwidthEst** <br/> |int  <br/> ||在会话结束时可用的估计单向带宽。 以位/秒为单位报告。  <br/> |
|**AppSharingPayloadDescription** <br/> |int  <br/> ||应用程序共享负载的说明。  <br/> |
|**RelativeOneWayTotal** <br/> |float  <br/> ||单向延迟的总金额。 相对单向延迟测量客户端与服务器之间的延迟。  <br/> |
|**RelativeOneWayAverage** <br/> |float  <br/> ||单向延迟的平均量。 相对单向延迟测量客户端与服务器之间的延迟。  <br/> |
|**RelativeOneWayMax** <br/> |float  <br/> ||单向延迟的最大值。 相对单向延迟测量客户端与服务器之间的延迟。  <br/> |
|**RelativeOneWayBurstOccurrences** <br/> |int  <br/> ||总单向爆发次数。 "Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，数据流处于不可预知的突发流量。 此指标测量客户端与服务器之间的数据流。  <br/> |
|**RelativeOneWayBurstDensity** <br/> |float  <br/> ||总单向脉冲密度。 "Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，数据流处于不可预知的突发流量。 此指标测量客户端与服务器之间的数据流。  <br/> |
|**RelativeOneWayBurstDuration** <br/> |float  <br/> ||总的单向脉冲持续时间。 "Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，数据流处于不可预知的突发流量。 此指标测量客户端与服务器之间的数据流。  <br/> |
|**RelativeOneWayGapOccurrences** <br/> |int  <br/> ||总的单向间隔发生次数。 "Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，其数据流可预料的猝发。间隙表示这些猝发之间的延迟。 此指标测量客户端与服务器之间的数据流。  <br/> |
|**RelativeOneWayGapDensity** <br/> |float  <br/> ||总单向间距密度。 "Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，其数据流可预料的猝发。间隙表示这些猝发之间的延迟。 此指标测量客户端与服务器之间的数据流。  <br/> |
|**RelativeOneWayGapDuration** <br/> |float  <br/> ||总的单间隔持续时间。 "Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，其数据流可预料的猝发。间隙表示这些猝发之间的延迟。 此指标测量客户端与服务器之间的数据流。  <br/> |
|**ApplicationSharingType** <br/> |varChar （256）  <br/> ||应用程序角色（共享者或查看者）和内容类型。  <br/> |
|**RDPTileProcessingLatencyTotal** <br/> |float  <br/> ||远程桌面协议（RDP）磁贴的处理总时间。 较高的总计等于查看体验中较长的延迟。  <br/> |
|**RDPTileProcessingLatencyAverage** <br/> |float  <br/> ||远程桌面协议（RDP）磁贴的平均处理时间。 较高的总计等于查看体验中较长的延迟。  <br/> |
|**RDPTileProcessingLatencyMax** <br/> |float  <br/> ||远程桌面协议（RDP）磁贴的最长处理时间。 较高的总计等于查看体验中较长的延迟。  <br/> |
|**RDPTileProcessingLatencyBurstOccurrences** <br/> |int  <br/> ||远程桌面协议（RDP）磁贴的处理时间内的爆发次数。 "Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，数据流处于不可预知的突发流量。  <br/> |
|**RDPTileProcessingLatencyBurstDensity** <br/> |float  <br/> ||远程桌面协议（RDP）磁贴的处理时间中的爆发密度。 "Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，数据流处于不可预知的突发流量。  <br/> |
|**RDPTileProcessingLatencyBurstDuration** <br/> |float  <br/> ||远程桌面协议（RDP）磁贴的处理时间内的爆发持续时间。 "Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，数据流处于不可预知的突发流量。  <br/> |
|**RDPTileProcessingLatencyGapOccurrences** <br/> |int  <br/> ||在远程桌面协议（RDP）磁贴的处理时间内出现间隙的情况。  <br/> |
|**RDPTileProcessingLatencyGapDensity** <br/> |float  <br/> ||远程桌面协议（RDP）磁贴的处理时间方面的差距密度。 低间隙密度相当于更好的观看体验。  <br/> |
|**RDPTileProcessingLatencyGapDuration** <br/> |float  <br/> ||远程桌面协议（RDP）磁贴的处理时间中的差距持续时间。 短间隙持续时间等于更好的观看体验。  <br/> |
|**CaptureTileRateTotal** <br/> |float  <br/> ||捕获的磁贴的总速率（以平铺/秒为单位）。  <br/> |
|**CaptureTileRateAverage** <br/> |float  <br/> ||捕获的图块的平均速率（以平铺/秒为单位）。  <br/> |
|**CaptureTileRateMax** <br/> |float  <br/> ||捕获的磁贴的最大速率（以平铺/秒为单位）。  <br/> |
|**CaptureTileRateBurstOccurrences** <br/> |在 t  <br/> ||在捕获的磁贴（每秒的平铺）的速率中的爆发次数。  <br/> |
|**CaptureTileRateBurstDensity** <br/> |float  <br/> ||已捕获磁贴（以平铺/秒为单位）的速率的脉冲密度。  <br/> |
|**CaptureTileRateBurstDuration** <br/> |float  <br/> ||以捕获的磁贴的速率（在每秒的平铺中）的爆发持续时间。  <br/> |
|**CaptureTileRateGapOccurrences** <br/> |int  <br/> ||在捕获的磁贴（每秒平铺）的速率中的间隙发生次数。  <br/> |
|**CaptureTileRateGapDensity** <br/> |float  <br/> ||在捕获的图块（每秒平铺）的速率中的间隙密度。  <br/> |
|**CaptureTileRateGapDuration** <br/> |float  <br/> ||以捕获的磁贴的速率（以平铺/秒为单位）为单位的间隙持续时间。  <br/> |
|**SpoiledTilePercentTotal** <br/> |float  <br/> ||未到达查看器但已被新内容放弃和覆盖的内容的总百分比。  <br/> |
|**SpoiledTilePercentAverage** <br/> |float  <br/> ||未到达查看器但已被新内容放弃和覆盖的内容的平均百分比。  <br/> |
|**SpoiledTilePercentMax** <br/> |float  <br/> ||未到达查看的内容的最大百分比，而是丢弃并被新内容覆盖。  <br/> |
|**SpoiledTilePercentBurstOccurrences** <br/> |int  <br/> ||未到达查看器但已被新内容放弃和覆盖的内容的突发事件发生。  <br/> |
|**SpoiledTilePercentBurstDensity** <br/> |float  <br/> ||未到达查看器的内容的爆发密度，但已被新内容放弃和覆盖。  <br/> |
|**SpoiledTilePercentBurstDuration** <br/> |float  <br/> ||未到达查看器的内容的爆发期，而是丢弃并被新内容覆盖。  <br/> |
|**SpoiledTilePercentGapOccurrences** <br/> |int  <br/> ||未到达查看器的内容的间隙出现次数，但已被新内容放弃和覆盖。  <br/> |
|**SpoiledTilePercentGapDensity** <br/> |float  <br/> ||未到达查看器但已被新内容放弃和覆盖的内容的差距密度。  <br/> |
|**SpoiledTilePercentGapDuration** <br/> |float  <br/> ||未到达查看器的内容的间距持续时间，但已被新内容放弃和覆盖。  <br/> |
|**ScrapingFrameRateTotal** <br/> |float  <br/> ||从图形源 scraped 的总帧数。  <br/> |
|**ScrapingFrameRateAverage** <br/> |float  <br/> ||从图形源 scraped 的平均帧数。  <br/> |
|**ScrapingFrameRateMax** <br/> |float  <br/> ||从图形源 scraped 的最大帧数。  <br/> |
|**ScrapingFrameRateBurstOccurrences** <br/> |int  <br/> ||帧 scraped 中的爆发出现在图形源中。  <br/> |
|**ScrapingFrameRateBurstDensity** <br/> |float  <br/> ||来自图形源的帧 scraped 中的脉冲密度。  <br/> |
|**ScrapingFrameRateBurstDuration** <br/> |float  <br/> ||帧 scraped 中的爆发持续时间（来自图形源）。  <br/> |
|**ScrapingFrameRateGapOccurrences** <br/> |int  <br/> ||从图形源 scraped 的帧中的间隙出现次数。  <br/> |
|**ScrapingFrameRateGapDensity** <br/> |float  <br/> ||从图形源 scraped 的帧中的间隙密度。  <br/> |
|**ScrapingFrameRateGapDuration** <br/> |float  <br/> ||帧 scraped 中的间距持续时间从图形源开始。  <br/> |
|**IncomingTileRateTotal** <br/> |float  <br/> ||由查看器接收的传入帧速率总数。  <br/> |
|**IncomingTileRateAverage** <br/> |float  <br/> ||查看器接收的平均传入帧速率。  <br/> |
|**IncomingTileRateMax** <br/> |float  <br/> ||查看器接收到的最大传入磁贴速度。  <br/> |
|**IncomingTileRateBurstOccurrences** <br/> |int  <br/> ||由查看器接收的传入磁贴速率中的爆发次数。  <br/> |
|**IncomingTileRateBurstDensity** <br/> |float  <br/> ||由查看器接收的传入磁贴速率中的脉冲密度。  <br/> |
|**IncomingTileRateBurstDuration** <br/> |float  <br/> ||由查看器接收的传入磁贴速率中的脉冲持续时间。  <br/> |
|**IncomingTileRateGapOccurrences** <br/> |int  <br/> ||由查看器接收的传入磁贴速率中的间隙出现次数。  <br/> |
|**IncomingTileRateGapDensity** <br/> |float  <br/> ||由查看器接收的传入磁贴费率中的间隙密度。  <br/> |
|**IncomingTileRateGapDuration** <br/> |float  <br/> ||由查看器接收的传入磁贴速率中的间隙持续时间。  <br/> |
|**IncomingFrameRateTotal** <br/> |float  <br/> ||由查看器接收的传入帧速率总数。  <br/> |
|**IncomingFrameRateAverage** <br/> |float  <br/> ||查看器接收的平均传入帧速率。  <br/> |
|**IncomingFrameRateMax** <br/> |float  <br/> ||查看器接收到的最大传入帧速率。  <br/> |
|**IncomingFrameRateBurstOccurrences** <br/> |int  <br/> ||由查看器接收的传入帧速率中的爆发次数。  <br/> |
|**IncomingFrameRateBurstDensity** <br/> |float  <br/> ||查看器接收的传入帧速率中的脉冲密度。  <br/> |
|**IncomingFrameRateBurstDuration** <br/> |float  <br/> ||按浏览器接收的传入帧速率中的爆发持续时间。  <br/> |
|**IncomingFrameRateGapOccurrences** <br/> |int  <br/> ||由查看器接收的传入帧速率中的间隙出现次数。  <br/> |
|**IncomingFrameRateGapDensity** <br/> |float  <br/> ||查看器接收的传入帧速率中的间隙密度。  <br/> |
|**IncomingFrameRateDuration** <br/> |float  <br/> ||按查看器接收的传入帧速率中的间隙持续时间。  <br/> |
|**OutgoingTileRateTotal** <br/> |float  <br/> ||发件人的传出磁贴总费率。  <br/> |
|**OutgoingTileRateAverage** <br/> |float  <br/> ||发件人的平均传出磁贴速率。  <br/> |
|**OutgoingTileRateMax** <br/> |float  <br/> ||发件人的最大传出磁贴费率。  <br/> |
|**OutgoingTileRateBurstOccurrences** <br/> |int  <br/> ||发件人的传出磁贴速率中的爆发次数。  <br/> |
|**OutgoingTileRateBurstDensity** <br/> |float  <br/> ||发件人的传出磁贴费率的脉冲密度。  <br/> |
|**OutgoingTileRateBurstDuration** <br/> |float  <br/> ||发件人的传出磁贴费率的爆发持续时间。  <br/> |
|**OutgoingTileRateGapOccurrences** <br/> |int  <br/> ||发件人的传出磁贴费率中的间隙发生次数。  <br/> |
|**OutgoingTileRateGapDensity** <br/> |float  <br/> ||发件人的传出磁贴费率的差距密度。  <br/> |
|**OutgoingTileRateGapDuration** <br/> |float  <br/> ||发件人的传出磁贴费率的差距持续时间。  <br/> |
|**OutgoingFrameRateTotal** <br/> |float  <br/> ||发件人的传出帧费率总数。  <br/> |
|**OutgoingFrameRateAverage** <br/> |float  <br/> ||发件人的平均传出帧速率。  <br/> |
|**OutgoingFrameRateMax** <br/> |float  <br/> ||发件人的最大传出帧速率。  <br/> |
|**OutgoingFrameRateBurstOccurrences** <br/> |int  <br/> ||发件人的传出帧费率中出现爆发。  <br/> |
|**OutgoingFrameRateBurstDensity** <br/> |float  <br/> ||发件人的传出帧费率的脉冲密度。  <br/> |
|**OutgoingFrameRateBurstDuration** <br/> |float  <br/> ||发件人的传出帧费率中的爆发持续时间。  <br/> |
|**OutgoingFrameRateGapOccurrences** <br/> |int  <br/> ||发件人的传出帧费率中的间隙出现次数。  <br/> |
|**OutgoingFrameRateGapDensity** <br/> |float  <br/> ||发件人的传出帧费率中的间隙密度。  <br/> |
|**OutgoingFrameRateGapDuration** <br/> |float  <br/> ||发件人的传出帧费率中的差距持续时间。  <br/> |
|**AverageRectangleHeight** <br/> |int  <br/> ||平均视频分辨率高度（以像素为单位）。  <br/> |
|**AverageRectangleWidth** <br/> |int  <br/> ||平均视频分辨率宽度（以像素为单位）。  <br/> |
|**封** <br/> |bit  <br/> ||入站传输的平均帧速率（以每秒帧数为单位）。  <br/> |
|**出站** <br/> |bit  <br/> ||出站传输的平均帧速率（以每秒帧数为单位）。  <br/> |
|**SenderIsCallerPAI** <br/> |bit  <br/> ||1表示流方向来自调用方的调用方。  <br/> 0表示流方向来自被调用方的调用方。  <br/> |
   

