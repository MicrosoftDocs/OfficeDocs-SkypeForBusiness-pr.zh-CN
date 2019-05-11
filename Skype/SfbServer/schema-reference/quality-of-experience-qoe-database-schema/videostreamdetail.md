---
title: VideoStreamDetail 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: VideoStreamDetail 视图在数据库中存储有关每个视频流的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: fdcb81ea74f4aab91b27b3989d6a41976a9c09de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33925262"
---
# <a name="videostreamdetail-view"></a>VideoStreamDetail 视图
 
VideoStreamDetail 视图在数据库中存储有关每个视频流的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**说明**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |引用[自 MediaLine table](medialine-0.md)。  <br/> |
|SessionSeq  <br/> |int  <br/> |引用[自 MediaLine table](medialine-0.md)。  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |引用[自 MediaLine table](medialine-0.md)。  <br/> |
|StreamId  <br/> |int  <br/> |媒体行中的唯一 ID。  <br/> |
|StartTime  <br/> |datetime  <br/> |会话的开始时间。  <br/> |
|EndTime  <br/> |datetime  <br/> |会话的结束时间。  <br/> |
|CallPriority  <br/> |int  <br/> |呼叫的优先级。  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |呼叫者池 FQDN。  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |被叫方池 FQDN。  <br/> |
|呼叫者  <br/> |nvarchar(450)  <br/> |呼叫者的 URI。  <br/> |
|被叫方  <br/> |nvarchar(450)  <br/> |被叫方的 URI。  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |呼叫者的用户代理字符串。  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |呼叫者的用户代理的类型。 请参阅[UserAgent 表](useragent.md)的详细信息。 <br/> |
|CallerUserAgentCategory  <br/> |nvarchar(64)  <br/> |呼叫者的用户代理的类别。 请参阅[UserAgentDef 表 (QoE)](useragentdef-qoe.md)的详细信息。 <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |被叫方的用户代理字符串。  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |被叫方的用户代理的类型。 请参阅[UserAgent 表](useragent.md)的信息。 <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar(64)  <br/> |被叫方的用户代理的类别。 请参阅[UserAgentDef 表 (QoE)](useragentdef-qoe.md)的信息。 <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |呼叫者的终结点名称。  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |被叫方的终结点名称。  <br/> |
|CallerOS  <br/> |nvarchar(128)  <br/> |操作系统 (OS) 的呼叫者终结点。  <br/> |
|CalleeOS  <br/> |nvarchar(128)  <br/> |操作系统 (OS) 被叫方的终结点。  <br/> |
|CallerCPUName  <br/> |nvarchar(128)  <br/> |呼叫者的终结点的 CPU 名称。  <br/> |
|CalleeCPUName  <br/> |nvarchar(128)  <br/> |被叫方的终结点的 CPU 名称。  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |呼叫者的终结点的 CPU 内核数。  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |被叫方的终结点的 CPU 内核数。  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |呼叫者的终结点的 CPU 处理器速度。  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |被叫方的终结点的 CPU 处理器速度。  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |指示呼叫者的系统是否正在运行的虚拟化环境中。 请参阅[Endpoint 表](endpoint.md)的详细信息。 <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |指示被叫方的系统是否正在运行的虚拟化环境中。 请参阅[Endpoint 表](endpoint.md)的详细信息。 <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |有关媒体路径的信息，如直接或中继。 请参阅[自 MediaLine table](medialine-0.md)的详细信息。 <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |有关互动式连接建立 (ICE) 过程中介绍信息位标志为呼叫者。 有关详细信息，请参阅质量的体验监控服务器协议规范。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |有关互动式连接建立 (ICE) 过程的信息中所述位标志为被叫方。 有关详细信息，请参阅质量的体验监控服务器协议规范。  <br/> |
|Transport  <br/> |int  <br/> |传输类型： 0 是 UDP，1 是 TCP。  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |呼叫者的 IP 地址。 这可能是 IPv4 或 IPv6 地址。  <br/> |
|CallerPort  <br/> |int  <br/> |呼叫者使用的端口。  <br/> |
|CallerInside  <br/> |bit  <br/> |指示呼叫者是否位于组织网络内部。 1 表示呼叫者位于企业网络内部，0 表示呼叫者位于网络外部。  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |被叫方的 IP 地址。 这可能是 IPv4 或 IPv6 地址。  <br/> |
|CalleePort  <br/> |int  <br/> |被叫方所使用的端口。  <br/> |
|CalleeInside  <br/> |bit  <br/> |指示是否将呼叫者位于组织 network.1 表示被叫方位于企业网络内部，0 表示被叫方位于网络外部。  <br/> |
|CallerUserSite  <br/> |nvarchar(128)  <br/> |呼叫者的站点的名称。  <br/> |
|CallerRegion  <br/> |nvarchar(128)  <br/> |呼叫者的站点的国家/地区的名称。  <br/> |
|CalleeUserSite  <br/> |nvarchar(128)  <br/> |被叫方的站点的名称。  <br/> |
|CalleeRegion  <br/> |nvarchar(128)  <br/> |被叫方的站点的国家/地区的名称。  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |IP 地址的 A / V 边缘服务使用的呼叫者。 请参阅[IPAddress 表](ipaddress.md)的详细信息。 <br/> |
|CallerRelayPort  <br/> |int  <br/> |端口上 A / V 边缘服务使用的呼叫者。  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |IP 地址密钥的 A / V 边缘服务由被叫方。 请参阅[IPAddress 表](ipaddress.md)的详细信息。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |端口上 A / V 边缘服务由被叫方。  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |呼叫者的捕获设备名称。  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |呼叫者呈现设备名称。  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |呼叫者的捕获设备驱动程序名称。  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |呼叫者的呈现设备驱动程序名称。  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |被叫方的捕获设备名称。  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |被叫方的呈现设备名称。  <br/> |
|CalleCaptureDevDriver  <br/> |varchar(256)  <br/> |被叫方的捕获设备驱动程序名称。  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |被叫方的呈现设备驱动程序名称。  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |呼叫者的网络连接类型： 0 有线，1 是无线。  <br/> |
|CallerVPN  <br/> |bit  <br/> |指示呼叫者通过虚拟专用网络连接。 1 是虚拟专用网络 (VPN)，0 为非 VPN。  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,)  <br/> |Bps 中的呼叫者的终结点的网络链接速度。  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |被叫方的网络连接类型： 0 有线，1 是无线。  <br/> |
|CalleeVPN  <br/> |bit  <br/> |指示被叫方通过虚拟专用网络连接。 1 是虚拟专用网络 (VPN)，0 为非 VPN。  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |被叫方的终结点 （以 bps 为单位） 的网络链接速度。  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |窄带交谈 MOS （基于两个音频流） 的音频会话。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |应用于给定的各种策略设置 （打开、 API、 SDP、 策略服务器等） 的给定的发送端流实际带宽。 这是不是有效的带宽与混淆，因为可以基于带宽估计较低的有效带宽。 这是一种基本上发送流花费除非按带宽估计施加限制的最大带宽。  <br/> |
|JitterInterArrival  <br/> |int  <br/> |实时控制协议 (RTCP) 统计信息中的平均网络抖动。  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |呼叫期间的最大网络抖动。  <br/> |
|RoundTrip  <br/> |int  <br/> |RTCP 统计信息中的来回行程时间。  <br/> |
|RoundTripMax  <br/> |int  <br/> |音频流的最大来回行程时间。  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |呼叫期间的平均数据包丢失率。  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |呼叫期间观测到的最大的数据包丢失。  <br/> |
|PacketUtilization  <br/> |int  <br/> |（实时传输协议，RTP） 的视频流的数据包计数。  <br/> |
|BandwidthEst  <br/> |int  <br/> |音频流的带宽预估。  <br/> |
|PayloadDescription  <br/> |int  <br/> |音频编解码器用于呼叫，引用[自 PayloadDescription table](payloaddescription.md)。  <br/> |
|VideoResolution  <br/> |char(9)  <br/> |乘以像素高度的像素宽度中的视频分辨率。 报告为 string。  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |视频流的平均比特率。  <br/> |
|InboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |接收的视频帧速率。  <br/> |
|OutboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |发送的视频帧速率。  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |视频会话期间的最大视频比特率。  <br/> |
|VideoPacketLossRate  <br/> |decimal(9,4)  <br/> |视频数据包丢失的速率。  <br/> |
|VideoFrameLossRate  <br/> |decimal(9.4)  <br/> |丢失的全部视频帧的百分比。  <br/> |
|VideoFEC  <br/> |bit  <br/> |不使用。  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |平均视频的带宽总量量。  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |decimal(9.4)  <br/> |丢失的全部视频帧的百分比。  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |流方向的 p 已断言标识信息。 1 表示流方向从呼叫者到被叫方;0 表示流方向从被叫方到呼叫者。  <br/> |
   

