---
title: VideoStreamDetail 视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: VideoStreamDetail 视图在数据库中存储有关每个视频流信息。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: d102a5e99cfcecb7d5e2e35b113e13509662af4f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="videostreamdetail-view"></a>VideoStreamDetail 视图
 
VideoStreamDetail 视图在数据库中存储有关每个视频流信息。 在 Microsoft Lync Server 2013 引入了此视图。
  
|**列**|**数据类型**|**说明**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |从[MediaLine 表](medialine-0.md)引用。  <br/> |
|SessionSeq  <br/> |int  <br/> |从[MediaLine 表](medialine-0.md)引用。  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |从[MediaLine 表](medialine-0.md)引用。  <br/> |
|StreamId  <br/> |int  <br/> |在媒体行的唯一 ID。  <br/> |
|开始时间  <br/> |datetime  <br/> |会话的开始时间。  <br/> |
|结束时间  <br/> |datetime  <br/> |会话的结束时间。  <br/> |
|CallPriority  <br/> |int  <br/> |调用的优先级。  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |调用方池的 FQDN。  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |被调用方池的 FQDN。  <br/> |
|呼叫者  <br/> |nvarchar(450)  <br/> |调用方的 URI。  <br/> |
|被叫方  <br/> |nvarchar(450)  <br/> |被调用方的 URI。  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |调用方的用户代理字符串。  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |调用方的用户代理的类型。 [用户代理表](useragent.md)的详细信息，请参阅。 <br/> |
|CallerUserAgentCategory  <br/> |nvarchar(64)  <br/> |调用方的用户代理的类别。 [UserAgentDef 表 (QoE)](useragentdef-qoe.md)的详细信息，请参阅。 <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |被调用方的用户代理字符串。  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |被调用方的用户代理的类型。 [用户代理表](useragent.md)的信息，请参阅。 <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar(64)  <br/> |被调用方的用户代理的类别。 [UserAgentDef 表 (QoE)](useragentdef-qoe.md)的信息，请参阅。 <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |调用方的端点名称。  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |被调用方的端点名称。  <br/> |
|CallerOS  <br/> |nvarchar(128)  <br/> |操作系统 (OS) 的调用方的端点。  <br/> |
|CalleeOS  <br/> |nvarchar(128)  <br/> |操作系统 (OS) 的被调用方的端点。  <br/> |
|CallerCPUName  <br/> |nvarchar(128)  <br/> |CPU 的调用方的端点的名称。  <br/> |
|CalleeCPUName  <br/> |nvarchar(128)  <br/> |CPU 的被调用方的端点的名称。  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |调用方的端点的 CPU 内核的数量。  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |被调用方的端点的 CPU 内核的数量。  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |调用方的端点的 CPU 处理器速度。  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |被调用方的端点的 CPU 处理器速度。  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |指示是否在虚拟化环境中运行呼叫者的系统。 [终结点表](endpoint.md)的详细信息，请参阅。 <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |指示被调用方的系统是否正在运行在虚拟化环境中。 [终结点表](endpoint.md)的详细信息，请参阅。 <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |有关介质路径的信息，如直接或中继。 [MediaLine 表](medialine-0.md)的详细信息，请参阅。 <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |交互式连接建立 (ICE) 过程中介绍有关信息位标志的调用方。 有关详细信息，请参阅质量的体验监视服务器协议规范。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |有关交互式连接建立 (ICE) 过程的信息所述位标志的被调用方。 有关详细信息，请参阅质量的体验监视服务器协议规范。  <br/> |
|Transport  <br/> |int  <br/> |传输类型： 0 是 UDP，1 是 TCP。  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |调用方的 IP 地址。 这可能是 IPv4 或 IPv6 地址。  <br/> |
|CallerPort  <br/> |int  <br/> |呼叫者使用的端口。  <br/> |
|CallerInside  <br/> |bit  <br/> |指示调用方是否在组织网络中。 1 表示调用方位于企业网络，0 表示调用方是网络之外。  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |被调用方的 IP 地址。 这可能是 IPv4 或 IPv6 地址。  <br/> |
|CalleePort  <br/> |int  <br/> |被调用方所使用的端口。  <br/> |
|CalleeInside  <br/> |bit  <br/> |指示调用方是在组织 network.1 表示被调用方位于企业网络，0 表示被调用方位于外部网络。  <br/> |
|CallerUserSite  <br/> |nvarchar(128)  <br/> |呼叫者的站点的名称。  <br/> |
|CallerRegion  <br/> |nvarchar(128)  <br/> |调用方的网站的国家/地区的名称。  <br/> |
|CalleeUserSite  <br/> |nvarchar(128)  <br/> |被调用方的站点的名称。  <br/> |
|CalleeRegion  <br/> |nvarchar(128)  <br/> |被调用方的网站的国家/地区的名称。  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |IP 地址的 A / V 边缘服务由调用方。 [Ip 地址表](ipaddress.md)的详细信息，请参阅。 <br/> |
|CallerRelayPort  <br/> |int  <br/> |端口 A / V 边缘服务由调用方。  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |IP 地址键的 A / V 边缘服务由被调用方。 [Ip 地址表](ipaddress.md)的详细信息，请参阅。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |端口 A / V 边缘服务由被调用方。  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |调用方的捕获设备名称。  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |调用方的呈现的设备名称。  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |调用方的捕获设备驱动程序的名称。  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |调用方的呈现的设备驱动程序的名称。  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |被调用方的捕获设备名称。  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |被调用方的呈现的设备名称。  <br/> |
|CalleCaptureDevDriver  <br/> |varchar(256)  <br/> |被调用方的捕获设备驱动程序的名称。  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |被调用方的呈现的设备驱动程序的名称。  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |呼叫者的网络连接类型： 0 有线，1 为无线。  <br/> |
|CallerVPN  <br/> |bit  <br/> |指示调用方通过虚拟专用网络连接。 1 为虚拟专用网络 (VPN)，0 为非 VPN。  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,)  <br/> |在 bps 中的调用方的端点的网络链接速度。  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |被调用方的网络连接类型： 0 有线，1 为无线。  <br/> |
|CalleeVPN  <br/> |bit  <br/> |指示被调用方通过虚拟专用网络连接。 1 为虚拟专用网络 (VPN)，0 为非 VPN。  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |对于被调用方的端点 （以 bps) 网络链接速度。  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |窄带的口语 MOS （根据这两个音频流） 中的音频会话。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |实际带宽应用到给定的发送端流给出各种策略设置 （启用、 API、 SDP、 策略服务器等等）。 这并不是因为可以有较低的有效带宽基于带宽估计能有效带宽与混淆。 这基本上是发送流可以采取除非限制规定的带宽估计的最大带宽。  <br/> |
|JitterInterArrival  <br/> |int  <br/> |从实时控制协议 (RTCP) 统计的平均网络抖动。  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |在调用过程的最大网络抖动。  <br/> |
|往返  <br/> |int  <br/> |从 RTCP 统计信息的往返时间。  <br/> |
|RoundTripMax  <br/> |int  <br/> |音频流的最大往返时间。  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |在调用过程平均数据包丢失率。  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |在调用期间观察到的最大数据包丢失。  <br/> |
|PacketUtilization  <br/> |int  <br/> |（RTP 实时传输协议） 的视频流的数据包数。  <br/> |
|BandwidthEst  <br/> |int  <br/> |带宽估计的音频流。  <br/> |
|PayloadDescription  <br/> |int  <br/> |用于呼叫，从[PayloadDescription 表](payloaddescription.md)中引用的音频编解码器。  <br/> |
|VideoResolution  <br/> |char(9)  <br/> |在乘以像素高度的像素宽度的视频分辨率。 报告为一个字符串。  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |视频流的平均比特率。  <br/> |
|InboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |接收到的视频的帧速率。  <br/> |
|OutboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |发送的视频的帧速率。  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |视频会话期间的最大的视频比特率。  <br/> |
|VideoPacketLossRate  <br/> |decimal(9,4)  <br/> |视频数据包的丢失率。  <br/> |
|VideoFrameLossRate  <br/> |decimal(9.4)  <br/> |总将丢失的视频帧的百分比。  <br/> |
|VideoFEC  <br/> |bit  <br/> |不使用。  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |为视频分配带宽的平均金额。  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |decimal(9.4)  <br/> |总所丢失的视频帧的百分比。  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |P 断言的标识信息的流方向。 1 表示流方向是从调用方到被调用方。0 表示流方向是从被调用方调用方。  <br/> |
   

