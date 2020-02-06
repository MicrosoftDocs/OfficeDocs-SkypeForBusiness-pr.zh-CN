---
title: VideoStreamDetail 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: VideoStreamDetail 视图存储有关数据库中每个视频流的信息。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 3fb598feec3b4dca87086504c620109a99bce7d0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804142"
---
# <a name="videostreamdetail-view"></a>VideoStreamDetail 视图
 
VideoStreamDetail 视图存储有关数据库中每个视频流的信息。 此视图已在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**说明**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |从[MediaLine 表](medialine-0.md)中引用。  <br/> |
|SessionSeq  <br/> |int  <br/> |从[MediaLine 表](medialine-0.md)中引用。  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |从[MediaLine 表](medialine-0.md)中引用。  <br/> |
|StreamId  <br/> |int  <br/> |媒体行内的唯一 ID。  <br/> |
|StartTime  <br/> |datetime  <br/> |会话的开始时间。  <br/> |
|EndTime  <br/> |datetime  <br/> |会话的结束时间。  <br/> |
|CallPriority  <br/> |int  <br/> |通话的优先级。  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |呼叫方池 FQDN。  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |被调用池 FQDN。  <br/> |
|呼叫者  <br/> |nvarchar （450）  <br/> |调用方的 URI。  <br/> |
|被叫方  <br/> |nvarchar （450）  <br/> |被调用方的 URI。  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |呼叫方的用户代理字符串。  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |呼叫方的用户代理的类型。 有关详细信息，请参阅[UserAgent 表](useragent.md)。 <br/> |
|CallerUserAgentCategory  <br/> |nvarchar （64）  <br/> |呼叫者的用户代理类别。 有关详细信息，请参阅[UserAgentDef 表（QoE）](useragentdef-qoe.md) 。 <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |被呼叫方的用户代理字符串。  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |被调用方的用户代理的类型。 有关信息，请参阅[UserAgent 表](useragent.md)。 <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar （64）  <br/> |被呼叫方的用户代理类别。 有关信息，请参阅[UserAgentDef 表（QoE）](useragentdef-qoe.md) 。 <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |调用方的终结点名称。  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |被调用方的终结点名称。  <br/> |
|CallerOS  <br/> |nvarchar  <br/> |呼叫方终结点的操作系统（OS）。  <br/> |
|CalleeOS  <br/> |nvarchar  <br/> |被调用方终结点的操作系统（OS）。  <br/> |
|CallerCPUName  <br/> |nvarchar  <br/> |呼叫方终结点的 CPU 名称。  <br/> |
|CalleeCPUName  <br/> |nvarchar  <br/> |被调用方终结点的 CPU 名称。  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |呼叫方终结点的 CPU 内核数。  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |被调用方终结点的 CPU 内核数。  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |呼叫方终结点的 CPU 处理器速度。  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |被调用方终结点的 CPU 处理器速度。  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |指示呼叫者的系统是否在虚拟化环境中运行。 有关详细信息，请参阅[终结点表](endpoint.md)。 <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |指示被调用方的系统是否在虚拟化环境中运行。 有关详细信息，请参阅[终结点表](endpoint.md)。 <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |有关媒体路径（如直接或中继）的信息。 有关详细信息，请参阅[MediaLine 表](medialine-0.md)。 <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |有关在呼叫者的位标志中描述的交互式连接建立（ICE）流程的信息。 有关详细信息，请参阅体验质量监视服务器协议规范。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |有关被调用方的位标志中所述的交互式连接建立（ICE）流程的信息。 有关详细信息，请参阅体验质量监视服务器协议规范。  <br/> |
|Transport  <br/> |int  <br/> |传输类型：0是 UDP，1是 TCP。  <br/> |
|CallerIPAddr  <br/> |var （50）  <br/> |呼叫方的 IP 地址。 这可能是 IPv4 地址或 IPv6 地址。  <br/> |
|CallerPort  <br/> |int  <br/> |呼叫方使用的端口。  <br/> |
|CallerInside  <br/> |bit  <br/> |指示呼叫者是否在组织网络内。 1表示呼叫方位于企业网络内，0表示呼叫方位于网络外部。  <br/> |
|CalleeIPAddr  <br/> |var （50）  <br/> |被呼叫方的 IP 地址。 这可能是 IPv4 地址或 IPv6 地址。  <br/> |
|CalleePort  <br/> |int  <br/> |被呼叫方使用的端口。  <br/> |
|CalleeInside  <br/> |bit  <br/> |指示呼叫者是否在组织网络内。1表示被呼叫方位于企业网络内，0表示被呼叫方在网络外部。  <br/> |
|CallerUserSite  <br/> |nvarchar  <br/> |呼叫者站点的名称。  <br/> |
|CallerRegion  <br/> |nvarchar  <br/> |呼叫方网站的国家/地区的名称。  <br/> |
|CalleeUserSite  <br/> |nvarchar  <br/> |被调用方的网站的名称。  <br/> |
|CalleeRegion  <br/> |nvarchar  <br/> |被呼叫方网站的国家/地区的名称。  <br/> |
|CallerRelayIPAddr  <br/> |var （50）  <br/> |呼叫方使用的 A/V 边缘服务的 IP 地址。 有关详细信息，请参阅[IPAddress 表](ipaddress.md)。 <br/> |
|CallerRelayPort  <br/> |int  <br/> |呼叫方使用的 A/V 边缘服务上的端口。  <br/> |
|CalleeRelayIPAddr  <br/> |var （50）  <br/> |被呼叫方使用的 A/V 边缘服务的 IP 地址密钥。 有关详细信息，请参阅[IPAddress 表](ipaddress.md)。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |被呼叫方使用的 A/V 边缘服务上的端口。  <br/> |
|CallerCaptureDev  <br/> |varchar （256）  <br/> |呼叫方的捕获设备名称。  <br/> |
|CallerRenderDev  <br/> |varchar （256）  <br/> |调用方的呈现设备名称。  <br/> |
|CallerCaptureDevDriver  <br/> |varchar （256）  <br/> |呼叫方的捕获设备驱动程序名称。  <br/> |
|CallerRenderDevDriver  <br/> |varchar （256）  <br/> |呼叫方的呈现设备驱动程序名称。  <br/> |
|CalleeCaptureDev  <br/> |varchar （256）  <br/> |被调用方的捕获设备名称。  <br/> |
|CalleeRenderDev  <br/> |varchar （256）  <br/> |被调用方的呈现设备名称。  <br/> |
|CalleCaptureDevDriver  <br/> |varchar （256）  <br/> |被调用方的捕获设备驱动程序名称。  <br/> |
|CalleeRenderDevDriver  <br/> |varchar （256）  <br/> |被调用方的呈现设备驱动程序名称。  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |呼叫者的网络连接类型：0是 "有线"，1是 "无线"。  <br/> |
|CallerVPN  <br/> |bit  <br/> |指示呼叫者是否通过虚拟专用网络连接。 1是虚拟专用网络（VPN），0是非 VPN。  <br/> |
|CallerLinkSpeed  <br/> |十进制（18，）  <br/> |呼叫方终结点的网络链接速度（以 bps 为实现）。  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |被呼叫方的网络连接类型：0是 "有线"，1是 "无线"。  <br/> |
|CalleeVPN  <br/> |bit  <br/> |指示被呼叫方是否通过虚拟专用网络进行连接。 1是虚拟专用网络（VPN），0是非 VPN。  <br/> |
|CalleeLinkSpeed  <br/> |十进制（18，0）  <br/> |被调用方终结点的网络链接速度（以 bps 为 bps）。  <br/> |
|ConversationalMOS  <br/> |十进制（3，2）  <br/> |音频会话的 Narrowband 对话 MOS （基于两个音频流）。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |在给定各种策略设置（TURN、API、SDP、策略服务器等）的情况下，应用到给定发送端流的实际带宽。 此操作不会与有效的带宽混淆，因为根据带宽估计，可能会有较低的有效带宽。 这基本上是发送流可以通过带宽估计限制限制的最大带宽。  <br/> |
|JitterInterArrival  <br/> |int  <br/> |实时控制协议（RTCP）统计信息的平均网络抖动。  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |通话期间网络抖动的最大值。  <br/> |
|RoundTrip  <br/> |int  <br/> |从 RTCP 统计数据往返的时间。  <br/> |
|RoundTripMax  <br/> |int  <br/> |音频流的最大往返行程时间。  <br/> |
|PacketLossRate  <br/> |十进制（5，4）  <br/> |通话期间平均数据包丢失速率。  <br/> |
|PacketLossRateMax  <br/> |十进制（5，4）  <br/> |通话过程中观察到的最大数据包丢失。  <br/> |
|PacketUtilization  <br/> |int  <br/> |视频流的数据包计数（实时传输协议、RTP）。  <br/> |
|BandwidthEst  <br/> |int  <br/> |音频流的带宽估计。  <br/> |
|PayloadDescription  <br/> |int  <br/> |用于呼叫的音频编解码器，从[PayloadDescription 表](payloaddescription.md)中引用。  <br/> |
|VideoResolution  <br/> |char （9）  <br/> |以像素为单位的视频分辨率（以像素为单位）乘以像素高度。 报告为字符串。  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |视频流的平均比特率。  <br/> |
|InboundVideoFrameRateAvg  <br/> |十进制（9，4）  <br/> |收到的视频的帧速率。  <br/> |
|OutboundVideoFrameRateAvg  <br/> |十进制（9，4）  <br/> |已发送视频的帧速率。  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |视频会话期间的最大视频比特率。  <br/> |
|VideoPacketLossRate  <br/> |十进制（9，4）  <br/> |视频数据包丢失的速率。  <br/> |
|VideoFrameLossRate  <br/> |十进制（9.4）  <br/> |丢失的视频帧总数的百分比。  <br/> |
|VideoFEC  <br/> |bit  <br/> |未使用。  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |为视频分配的平均带宽量。  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |十进制（9.4）  <br/> |丢失的视频帧总数的百分比。  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |P 声明的标识信息的流方向。 1表示流方向从调用方到被调用方;0表示流方向来自被调用方的调用方。  <br/> |
   

