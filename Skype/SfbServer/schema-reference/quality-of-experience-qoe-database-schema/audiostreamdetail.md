---
title: AudioStreamDetail 视图
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: AudioStreamDetail 视图存储有关数据库中每个音频流的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 4a675f2b7a8cf4e0aaa322bb63d804edf27625cb
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823092"
---
# <a name="audiostreamdetail-view"></a>AudioStreamDetail 视图
 
AudioStreamDetail 视图存储有关数据库中每个音频流的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**Details**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|SessionSeq  <br/> |int  <br/> |从 [MediaLine 表引用](medialine-0.md)。  <br/> |
|StreamId  <br/> |int  <br/> |媒体行中的唯一 ID。  <br/> |
|StartTime  <br/> |datetime  <br/> |会话的开始时间。  <br/> |
|EndTime  <br/> |datetime  <br/> |会话的结束时间。  <br/> |
|DialogCategory  <br/> |bit  <br/> |对话框类别：0 是 Skype for Business Server 到中介服务器;0 表示 Skype for Business Server 到中介服务器;1 是中介服务器到 PSTN 网关的通道。  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |指示呼叫是否绕过的标志。  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |如果存在，则指示为什么即使绕过 ID 匹配，也未绕过呼叫。 只定义了一个值：  <br/> 0x0001 - 默认网络适配器的未知绕过 ID。  <br/> |
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
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |呼叫者的终结点中的 CPU 内核数。  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |被叫方终结点中的 CPU 内核数。  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |呼叫者的终结点的 CPU 处理器速度。  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |被叫方终结点的 CPU 处理器速度。  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |指示呼叫者的系统是否在虚拟化环境中运行。 有关详细信息， [请参阅 Endpoint](endpoint.md) 表。 <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |指示被叫方的系统是否在虚拟化环境中运行。 有关详细信息， [请参阅 Endpoint](endpoint.md) 表。 <br/> |
|CorrelationKey  <br/> ||相关键。 从 [SessionCorrelation 表引用](sessioncorrelation.md)。  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |有关媒体路径的信息，例如直接或中继。 有关详细信息， [请参阅 MediaLine](medialine-0.md) 表。 <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |关于呼叫者的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“用户体验质量监控服务器协议规范”。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |关于被叫方的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“用户体验质量监控服务器协议规范”。  <br/> |
|Transport  <br/> |tinyint  <br/> |传输类型：0 是 UDP，1 是 TCP。  <br/> |
|CallerIPAddr  <br/> |var (50)   <br/> |呼叫者的 IP 地址。 这可能是 IPv4 或 IPv6 地址。  <br/> |
|CallerPort  <br/> |int  <br/> |呼叫者使用的端口。  <br/> |
|CallerInside  <br/> |bit  <br/> |指示呼叫者是否位于间隔网络内：1 表示呼叫者在企业网络内部，0 表示呼叫者位于网络外部。  <br/> |
|CalleeIPAddr  <br/> |var (50)   <br/> |被叫方的 IP 地址。 这可能是 IPv4 或 IPv6 地址。  <br/> |
|CalleePort  <br/> |int  <br/> |被叫方所使用的端口。  <br/> |
|CalleeInside  <br/> |bit  <br/> |指示被叫方是否位于间隔网络内：1 表示被叫方在企业网络内部，0 表示被叫方在网络外。  <br/> |
|CallerUserSite  <br/> |nvarchar (128)   <br/> |呼叫者网站的名称。  <br/> |
|CallerRegion  <br/> |nvarchar (128)   <br/> |呼叫者网站的国家/地区的名称。  <br/> |
|CalleeUserSite  <br/> |nvarchar (128)   <br/> |被叫方网站的名称。  <br/> |
|CalleeRegion  <br/> |nvarchar (128)   <br/> |被叫方网站的国家/地区的名称。  <br/> |
|CallerRelayIPAddr  <br/> |var (50)   <br/> |呼叫者所使用的 A/V 边缘服务的 IP 地址。 有关详细信息， [请参阅 IPAddress](ipaddress.md) 表。 <br/> |
|CallerRelayPort  <br/> |int  <br/> |呼叫者在 A/V 边缘服务中使用的端口。  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)   <br/> |被叫方所使用的 A/V 边缘服务的 IP 地址密钥。 有关详细信息， [请参阅 IPAddress](ipaddress.md) 表。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |被叫方在 A/V 边缘服务中使用的端口。  <br/> |
|CallerCaptureDev  <br/> |varchar (256)   <br/> |呼叫者的捕获设备名称。  <br/> |
|CallerRenderDev  <br/> |varchar (256)   <br/> |呼叫者的呈现设备名称。  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)   <br/> |呼叫者的捕获设备驱动程序名称。  <br/> |
|CallerRenderDriver  <br/> |varchar (256)   <br/> |呼叫者的呈现设备驱动程序名称。  <br/> |
|CalleeCaptureDev  <br/> |varchar (256)   <br/> |被叫方捕获设备名称。  <br/> |
|CalleeRenderDev  <br/> |varchar (256)   <br/> |被叫方呈现设备名称。  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar (256)   <br/> |被叫方捕获设备驱动程序名称。  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)   <br/> |被叫方呈现设备驱动程序名称。  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |呼叫者的网络连接类型：0 为有线，1 为无线。  <br/> |
|CallerVPN  <br/> |bit  <br/> |指示呼叫者是否通过虚拟专用网络进行连接：1 是虚拟专用 (VPN) ，0 是非 VPN。  <br/> |
|CallerLinkSpeed  <br/> |decimal (18，0)   <br/> |呼叫者终结点的网络链接速度（以 bps 为单位）。  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |被叫方网络连接类型：0 为有线，1 为无线。  <br/> |
|CalleeVPN  <br/> |bit  <br/> |指示呼叫者是否通过虚拟专用网络进行连接：1 是虚拟专用 (VPN) ，0 是非 VPN。  <br/> |
|CalleeLinkSpeed  <br/> |decimal (18，0)   <br/> |被叫方终结点的网络链接速度（以 bps 表示）。  <br/> |
|ConversationalMOS  <br/> |decimal (3，2)   <br/> |音频会话的窄带交谈 MOS（基于两个音频流）。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |应用于指定发送端流指定的多种策略设置（TURN、API、SDP、策略服务器等）的实际带宽。 不要将其与有效带宽混淆，因为根据带宽预估的不同，可能会降低带宽的有效性。 这基本上是发送流可以达到的带宽估计限制的最大带宽  <br/> |
|JitterInterArrival  <br/> |int  <br/> |实时控制协议 (RTCP) 统计信息中的平均网络抖动。  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |呼叫期间的最大网络抖动。  <br/> |
|PacketLossRate  <br/> |decimal (5，4)   <br/> |呼叫期间的平均数据包丢失率。  <br/> |
|PacketLossRateMax  <br/> |decimal (5，4)   <br/> |呼叫期间观测到的数据包丢失最大值。  <br/> |
|BurstDensity  <br/> |decimal (9，4)   <br/> |呼叫过程中丢失突发丢失的平均数据包密度。  <br/> |
|BurstDuration  <br/> |int  <br/> |呼叫期间突发丢失数据包的平均持续时间。  <br/> |
|BurstGapDensity  <br/> |decimal (9，4)   <br/> |数据包丢失的突发间隔期间数据包丢失的平均密度。  <br/> |
|BurstGapDuration  <br/> |int  <br/> |数据包丢失突发之间的平均间隔持续时间。  <br/> |
|PacketUtilization  <br/> |int  <br/> |音频流的数据包计数。  <br/> |
|BandwidthEst  <br/> |int  <br/> |音频流的带宽预估。  <br/> |
|DegradationAvg  <br/> |decimal (3，2)   <br/> |整个呼叫的网络 MOS 降级。 范围为 0.0 到 5.0。 此指标显示由于抖动和数据包丢失而减少的网络 MOS 量。 对于可接受的质量，它应小于 0.5。  <br/> |
|DegradationMax  <br/> |decimal (3，2)   <br/> |呼叫期间最大网络 MOS 下降。  <br/> |
|DegradationJitterAvg  <br/> |decimal (3，2)   <br/> |抖动导致网络 MOS 下降。  <br/> |
|DegradationPacketLossAvg  <br/> |decimal (3，2)   <br/> |数据包丢失导致网络 MOS 下降。  <br/> |
|PayloadDescription  <br/> |int  <br/> |用于呼叫的音频编解码器，从 [PayloadDescription](payloaddescription.md)表引用。  <br/> |
|AudioSampleRate  <br/> |int  <br/> |音频流的采样率。  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |呼叫者发送的音频的模拟后增益控制音频信号级别。 此指标的单位为 dBmo。 对于可接受的质量，它应至少为 30 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |呼叫者接收的音频的音频信号级别。 此指标的单位为 dBmo。 对于可接受的质量，它应至少为 30 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |模拟后增益控制呼叫者发送的音频的音频噪音级别。 此指标的单位为 dBmo。 对于可接受的质量，它应小于 35 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |模拟后增益控制呼叫者接收的音频的音频噪音级别。 此指标的单位为 dBmo。 对于可接受的质量，它应小于 35 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |呼叫者的回声返回丢失增强功能。 此指标的单位为 dB。 较低的值表示较少的回声。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |呼叫者的扬声器呈现每五分钟的平均故障数。 为保证良好的质量，此时间应小于每五分钟一个。 A/V 会议服务器、中介服务器或 IP 电话未报告。  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |呼叫者的麦克风捕获每五分钟的平均故障数。 为保证良好的质量，此时间应小于每五分钟一个。 A/V 会议服务器、中介服务器或 IP 电话未报告。  <br/> |
|CallerTimestampDriftRateMic  <br/> |decimal (9，2)   <br/> |呼叫者的麦克风设备时钟偏移率，相对于 CPU 时钟。  <br/> |
|CallerTimestampDriftRateSpk  <br/> |decimal (9，2)   <br/> |呼叫者的扬声器设备时钟偏移速率，相对于 CPU 时钟。  <br/> |
|CallerTimestampErrorMicMs  <br/> |decimal (9，2)   <br/> |呼叫的最后 20 秒的平均麦克风捕获流时间戳错误（以毫秒为单位）。  <br/> |
|CallerTimestampErrorSpkMs  <br/> |decimal (9，2)   <br/> |呼叫者扬声器呈现流时间戳错误（以毫秒为单位）在呼叫的最后 20 秒的平均值。  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |语音切换是半双工模式，中断能力降低。 有关详细信息， [请参阅 MediaLine](medialine-0.md) 表。 <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |呼叫者出现回声事件的原因。 有关详细信息， [请参阅 MediaLine](medialine-0.md) 表。 <br/> |
|CallerEchoPercentMicIn  <br/> |decimal (5，2)   <br/> |在呼叫者的麦克风捕获流中检测到回声的时间百分比。 如果使用耳机，则值应较低。  <br/> |
|CallerEchoPercentSend  <br/> |decimal (5，2)   <br/> |在呼叫者的发送流中检测到回声的时间百分比。 发送流中的高回声百分比表示回声泄漏。  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |从网关接收来自呼叫者音频的中介服务器的信号级别;这仅适用于中介服务器。 此指标的单位为 dBoV。 为获得良好的质量，可接受的范围应为 -30 到 -18 dBoV。  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |从网关接收来自呼叫者音频的中介服务器的信号级别。 这仅适用于中介服务器。 此指标的单位为 dBoV。 为了质量良好，可接受的范围应小于 -50 dBoV。  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |自动获取 (AGC) 应用到呼叫者音频的中介服务器端的 AGC 控制。  <br/> |
|CallerInitialSignalLevelRMS  <br/> |float  <br/> |在呼叫 (前 30) ，向呼叫者发送传入信号的 RMS 信号的根平均值平方值。  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |表示被叫方发送的音频的模拟后增益控制音频信号级别。 此指标的单位为 dBmo。 对于可接受的质量，它应至少为 30 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |被叫方接收的音频的音频信号级别。 此指标的单位为 dBmo。 对于可接受的质量，它应至少为 30 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |被叫方发送的音频的模拟后增益控制音频噪音级别。 此指标的单位为 dBmo。 对于可接受的质量，它应小于 35 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |被叫方收到的音频的模拟后增益控制音频噪音级别。 此指标的单位为 dBmo。 对于可接受的质量，它应小于 35 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |被叫方回声返回丢失增强功能。 此指标的单位为 dB。 较低的值表示较少的回声。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |被叫方呈现的扬声器时每五分钟的平均故障数。 为保证良好的质量，此时间应小于每五分钟一个。 A/V 会议服务器、中介服务器或 IP 电话未报告。  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |被叫方麦克风捕获每五分钟的平均故障数。 为保证良好的质量，此时间应小于每五分钟一个。 A/V 会议服务器、中介服务器或 IP 电话未报告。  <br/> |
|CalleeTimestampDriftRateMic  <br/> |decimal (9，2)   <br/> |被叫方麦克风设备时钟偏移率，相对于 CPU 时钟。  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |decimal (9，2)   <br/> |被叫方扬声器设备相对于 CPU 时钟的时钟偏移速率。  <br/> |
|CalleeTimestampErrorMicMs  <br/> |decimal (9，2)   <br/> |呼叫的最后 20 秒的平均麦克风捕获流时间戳错误（以毫秒为单位）。  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |decimal (9，2)   <br/> |被叫方扬声器呈现流时间戳错误（以毫秒为单位）在呼叫的最后 20 秒的平均值。  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |语音切换是半双工模式，中断能力降低。 有关详细信息， [请参阅 MediaLine](medialine-0.md) 表。 <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |被叫方出现回声事件的原因。 有关详细信息， [请参阅 MediaLine](medialine-0.md) 表。 <br/> |
|CalleeEchoPercentMicIn  <br/> |decimal (5，2)   <br/> |在被叫方麦克风捕获流中检测到回声的时间百分比。 如果使用耳机，则值应较低。  <br/> |
|CalleeEchoPercentSend  <br/> |decimal (5，2)   <br/> |在被叫方发送的流中检测到回声的时间百分比。 发送流中的高回声百分比表示回声泄漏。  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |从网关接收来自被叫方音频的中介服务器的信号级别;这仅适用于中介服务器。 此指标的单位为 dBoV。 为获得良好的质量，可接受的范围应为 [-30 至 -18] dBoV。  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |从网关接收来自被叫方音频的中介服务器的信号级别。 这仅适用于中介服务器。 此指标的单位为 dBoV。 为了质量良好，可接受的范围应小于 -50 dBoV。  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |自动获取 (AGC) 应用到被叫方音频的中介服务器端的 AGC 设置。  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |float  <br/> |传入信号 (RMS) 的根平均值平方值，最多在呼叫的前 30 秒。  <br/> |
|RatioConcealedSamplesAvg  <br/> |decimal (5，2)   <br/> |音频处理生成的隐藏样本与典型样本的平均比率。  <br/> |
|RatioStretchedSamplesAvg  <br/> |decimal (5，2)   <br/> |音频处理生成的拉伸样本与典型样本的平均比率。  <br/> |
|RatioCompressedSamplesAvg  <br/> |decimal (5，2)   <br/> |音频处理生成的压缩样本与典型样本的平均比率。  <br/> |
|RoundTrip  <br/> |int  <br/> |RTCP 统计信息中的来回行程时间。  <br/> |
|RoundTripMax  <br/> |int  <br/> |音频流的最大来回行程时间。  <br/> |
|OverallAvgNetworkMOS  <br/> |decimal (3，2)   <br/> |呼叫的平均宽带网络 MOS。 此指标取决于数据包丢失、抖动和使用的编解码器。 范围为 1.0 到 5.0。  <br/> |
|OverallMinNetworkMOS  <br/> |decimal (3，2)   <br/> |呼叫的最低宽带网络 MOS。  <br/> |
|SendListenMOS  <br/> |decimal (3，2)   <br/> |已发送音频的平均预测宽带侦听 MOS 得分，包括语音级别、噪音级别和捕获设备特征。  <br/> |
|SendListenMOSMin  <br/> |decimal (3，2)   <br/> |呼叫的最低 SendListenMOS。  <br/> |
|RecvListenMOS  <br/> |decimal (3，2)   <br/> |从网络接收的音频的平均预测宽带侦听 MOS 得分，包括语音级别、噪音级别、编解码器、网络条件和捕获设备特征。  <br/> |
|RecvListenMOSMin  <br/> |decimal (3，2)   <br/> |呼叫的最低 RecvListenMOS。  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |指示音频 FEC 是否用于呼叫。  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |指示 p 断言标识信息的方向;1 表示流方向从呼叫者到被叫方;0 表示流方向为从被叫方到呼叫者。  <br/> |
   

