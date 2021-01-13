---
title: VideoStreamDetail 视图
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: VideoStreamDetail 视图存储有关每个数据库中视频流的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 6341febeb8d43e36975c5b4cc446ac24ff1287c2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834342"
---
# <a name="videostreamdetail-view"></a>VideoStreamDetail 视图
 
VideoStreamDetail 视图存储有关每个数据库中视频流的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**说明**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|SessionSeq  <br/> |int  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|StreamId  <br/> |int  <br/> |媒体行中的唯一 ID。  <br/> |
|StartTime  <br/> |datetime  <br/> |会话的开始时间。  <br/> |
|EndTime  <br/> |datetime  <br/> |会话的结束时间。  <br/> |
|CallPriority  <br/> |int  <br/> |呼叫的优先级。  <br/> |
|CallerPool  <br/> |nvarchar (256)   <br/> |呼叫者池 FQDN。  <br/> |
|CalleePool  <br/> |nvarchar (256)   <br/> |被叫方池 FQDN。  <br/> |
|Caller  <br/> |nvarchar (450)   <br/> |呼叫者的 URI。  <br/> |
|被叫方  <br/> |nvarchar (450)   <br/> |被叫方 URI。  <br/> |
|CallerUserAgent  <br/> |nvarchar (256)   <br/> |呼叫者的用户代理字符串。  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |呼叫者的用户代理的类型。 有关详细信息， [请参阅 UserAgent](useragent.md) 表。 <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)   <br/> |呼叫者的用户代理的类别。 有关详细信息， [请参阅 QoE (UserAgentDef) ](useragentdef-qoe.md) 表。 <br/> |
|CalleeUserAgent  <br/> |nvarchar (256)   <br/> |被叫方的用户代理字符串。  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |被叫方的用户代理类型。 有关信息 [，请参阅 UserAgent](useragent.md) 表。 <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)   <br/> |被叫方的用户代理的类别。 有关信息 [，请参阅 QoE (UserAgentDef) ](useragentdef-qoe.md) 表。 <br/> |
|CallerEndpoint  <br/> |nvarchar (256)   <br/> |呼叫者的终结点名称。  <br/> |
|CalleeEndpoint  <br/> |nvarchar (256)   <br/> |被叫方终结点名称。  <br/> |
|CallerOS  <br/> |nvarchar (128)   <br/> |操作系统 () 终结点的操作系统。  <br/> |
|CalleeOS  <br/> |nvarchar (128)   <br/> |操作系统 (被) 终结点的操作系统。  <br/> |
|CallerCPUName  <br/> |nvarchar (128)   <br/> |呼叫者的终结点的 CPU 名称。  <br/> |
|CalleeCPUName  <br/> |nvarchar (128)   <br/> |被叫方终结点的 CPU 名称。  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |呼叫者的终结点的 CPU 内核数。  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |被叫方终结点的 CPU 内核数。  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |呼叫者的终结点的 CPU 处理器速度。  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |被叫方终结点的 CPU 处理器速度。  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |指示呼叫者的系统是否在虚拟化环境中运行。 有关详细信息， [请参阅 Endpoint](endpoint.md) 表。 <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |指示被叫方的系统是否在虚拟化环境中运行。 有关详细信息， [请参阅 Endpoint](endpoint.md) 表。 <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |有关媒体路径的信息，例如直接或中继。 有关详细信息， [请参阅 MediaLine](medialine-0.md) 表。 <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |关于呼叫者的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“用户体验质量监控服务器协议规范”。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |关于被叫方的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“用户体验质量监控服务器协议规范”。  <br/> |
|Transport  <br/> |int  <br/> |传输类型：0 是 UDP，1 是 TCP。  <br/> |
|CallerIPAddr  <br/> |var (50)   <br/> |呼叫者的 IP 地址。 这可能是 IPv4 或 IPv6 地址。  <br/> |
|CallerPort  <br/> |int  <br/> |呼叫者使用的端口。  <br/> |
|CallerInside  <br/> |bit  <br/> |指示呼叫者是否位于组织网络的内部。1 表示呼叫者位于企业网络内部，0 表示呼叫者位于该网络外部。  <br/> |
|CalleeIPAddr  <br/> |var (50)   <br/> |被叫方的 IP 地址。 这可能是 IPv4 或 IPv6 地址。  <br/> |
|CalleePort  <br/> |int  <br/> |被叫方所使用的端口。  <br/> |
|CalleeInside  <br/> |bit  <br/> |指示呼叫者是否位于组织网络的内部。1 表示被叫方位于企业网络内部，0 表示被叫方位于该网络外部。  <br/> |
|CallerUserSite  <br/> |nvarchar (128)   <br/> |呼叫者网站的名称。  <br/> |
|CallerRegion  <br/> |nvarchar (128)   <br/> |呼叫者网站的国家/地区的名称。  <br/> |
|CalleeUserSite  <br/> |nvarchar (128)   <br/> |被叫方网站的名称。  <br/> |
|CalleeRegion  <br/> |nvarchar (128)   <br/> |被叫方网站的国家/地区的名称。  <br/> |
|CallerRelayIPAddr  <br/> |var (50)   <br/> |呼叫者所使用的 A/V 边缘服务的 IP 地址。 有关详细信息， [请参阅 IPAddress](ipaddress.md) 表。 <br/> |
|CallerRelayPort  <br/> |int  <br/> |呼叫者使用的 A/V 边缘服务上的端口。  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)   <br/> |被叫方所使用的 A/V 边缘服务的 IP 地址密钥。 有关详细信息， [请参阅 IPAddress](ipaddress.md) 表。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |被叫方使用的 A/V 边缘服务上的端口。  <br/> |
|CallerCaptureDev  <br/> |varchar (256)   <br/> |呼叫者的捕获设备名称。  <br/> |
|CallerRenderDev  <br/> |varchar (256)   <br/> |呼叫者的呈现设备名称。  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)   <br/> |呼叫者的捕获设备驱动程序名称。  <br/> |
|CallerRenderDevDriver  <br/> |varchar (256)   <br/> |呼叫者的呈现设备驱动程序名称。  <br/> |
|CalleeCaptureDev  <br/> |varchar (256)   <br/> |被叫方捕获设备名称。  <br/> |
|CalleeRenderDev  <br/> |varchar (256)   <br/> |被叫方呈现设备名称。  <br/> |
|CalleCaptureDevDriver  <br/> |varchar (256)   <br/> |被叫方捕获设备驱动程序名称。  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)   <br/> |被叫方呈现设备驱动程序名称。  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |呼叫者的网络连接类型：0 为有线，1 为无线。  <br/> |
|CallerVPN  <br/> |bit  <br/> |指示呼叫者是否通过虚拟专用网络连接：1 是虚拟专用网络 (VPN)，0 是非 VPN。  <br/> |
|CallerLinkSpeed  <br/> |decimal (18，)   <br/> |呼叫者终结点的网络链接速度（以 bps 为单位）。  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |被叫方网络连接类型：0 为有线，1 为无线。  <br/> |
|CalleeVPN  <br/> |bit  <br/> |指示被叫方是否通过虚拟专用网络连接：1 是虚拟专用网络 (VPN)，0 是非 VPN。  <br/> |
|CalleeLinkSpeed  <br/> |decimal (18，0)   <br/> |被叫方终结点的网络链接速度 (bps) 。  <br/> |
|ConversationalMOS  <br/> |decimal (3，2)   <br/> |音频会话的窄带交谈 MOS（基于两个音频流）。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |应用于指定发送端流指定的多种策略设置（TURN、API、SDP、策略服务器等）的实际带宽。不要将其与有效带宽混淆，因为根据带宽预估的不同，可能会降低带宽的有效性。这基本上是发送流可禁止带宽预估设定的限制的最大带宽。  <br/> |
|JitterInterArrival  <br/> |int  <br/> |实时控制协议 (RTCP) 统计信息中的平均网络抖动。  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |呼叫期间的最大网络抖动。  <br/> |
|RoundTrip  <br/> |int  <br/> |RTCP 统计信息中的来回行程时间。  <br/> |
|RoundTripMax  <br/> |int  <br/> |音频流的最大来回行程时间。  <br/> |
|PacketLossRate  <br/> |decimal (5，4)   <br/> |呼叫期间的平均数据包丢失率。  <br/> |
|PacketLossRateMax  <br/> |decimal (5，4)   <br/> |呼叫期间观测到的数据包丢失最大值。  <br/> |
|PacketUtilization  <br/> |int  <br/> |视频流的数据包计数（实时传输协议，RTP）。  <br/> |
|BandwidthEst  <br/> |int  <br/> |音频流的带宽预估。  <br/> |
|PayloadDescription  <br/> |int  <br/> |用于呼叫的音频编解码器，从 [PayloadDescription](payloaddescription.md)表引用。  <br/> |
|VideoResolution  <br/> |char (9)   <br/> |视频的分辨率（像素宽乘以像素高）。报告为字符串。  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |视频流的平均比特率。  <br/> |
|InboundVideoFrameRateAvg  <br/> |decimal (9，4)   <br/> |接收的视频帧速率。  <br/> |
|OutboundVideoFrameRateAvg  <br/> |decimal (9，4)   <br/> |发送的视频帧速率。  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |视频会话期间的最大视频比特率。  <br/> |
|VideoPacketLossRate  <br/> |decimal (9，4)   <br/> |视频数据包丢失的比特率。  <br/> |
|VideoFrameLossRate  <br/> |decimal (9.4)   <br/> |丢失的全部视频帧的百分比。  <br/> |
|VideoFEC  <br/> |bit  <br/> |未使用。  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |为视频分配的平均带宽量。  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |decimal (9.4)   <br/> |丢失的全部视频帧的百分比。  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |已断言标识信息的流方向。1 表示流方向从呼叫者到被叫方；0 表示流方向从被叫方到呼叫者。  <br/> |
   

