---
title: AudioStreamDetail 视图
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: AudioStreamDetail 视图在数据库中存储有关每个音频流的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: c5078a0d936cce0dec29ddfee3813db7334aba71
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212289"
---
# <a name="audiostreamdetail-view"></a>AudioStreamDetail 视图
 
AudioStreamDetail 视图在数据库中存储有关每个音频流的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |引用[自 MediaLine table](medialine-0.md)。  <br/> |
|SessionSeq  <br/> |int  <br/> |引用[自 MediaLine table](medialine-0.md)。  <br/> |
|StreamId  <br/> |int  <br/> |媒体行中的唯一 ID。  <br/> |
|StartTime  <br/> |datetime  <br/> |会话的开始时间。  <br/> |
|EndTime  <br/> |datetime  <br/> |会话的结束时间。  <br/> |
|DialogCategory  <br/> |bit  <br/> |对话类别： 0 是业务服务器 Skype 到中介服务器线路;1 是中介服务器到 PSTN 网关线路。  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |标志指示绕过呼叫。  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |如果存在此参数，指示为什么呼叫不绕过即使绕过 Id 匹配。 定义只有一个值：  <br/> 0x0001-默认网络适配器的未知绕过 ID。  <br/> |
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
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |在呼叫者终结点的 CPU 内核数。  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |被叫方的终结点中的 CPU 内核数。  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |呼叫者的终结点的 CPU 处理器速度。  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |被叫方的终结点的 CPU 处理器速度。  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |指示呼叫者的系统是否正在运行的虚拟化环境中。 请参阅[Endpoint 表](endpoint.md)的详细信息。 <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |指示被叫方的系统是否正在运行的虚拟化环境中。 请参阅[Endpoint 表](endpoint.md)的详细信息。 <br/> |
|CorrelationKey  <br/> ||相关键。 从[SessionCorrelation 表](sessioncorrelation.md)引用。  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |信息的媒体路径，例如直接或中继。 请参阅[自 MediaLine table](medialine-0.md)的详细信息。 <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |有关互动式连接建立 (ICE) 过程中介绍信息位标志为呼叫者。 有关详细信息，请参阅质量的体验监控服务器协议规范。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |有关互动式连接建立 (ICE) 过程的信息中所述位标志为被叫方。 有关详细信息，请参阅质量的体验监控服务器协议规范。  <br/> |
|Transport  <br/> |tinyint  <br/> |传输类型： 0 是 UDP，1 是 TCP。  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |呼叫者的 IP 地址。 这可能是 IPv4 或 IPv6 地址。  <br/> |
|CallerPort  <br/> |int  <br/> |呼叫者使用的端口。  <br/> |
|CallerInside  <br/> |bit  <br/> |指示呼叫者是否位于间隔网络内部： 1 表示呼叫者位于企业网络内部，0 表示呼叫者位于网络外部。  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |被叫方的 IP 地址。 这可能是 IPv4 或 IPv6 地址。  <br/> |
|CalleePort  <br/> |int  <br/> |被叫方所使用的端口。  <br/> |
|CalleeInside  <br/> |bit  <br/> |指示被叫方是否位于间隔网络内部： 1 表示被叫方位于企业网络内部，0 表示被叫方位于网络外部。  <br/> |
|CallerUserSite  <br/> |nvarchar(128)  <br/> |呼叫者的站点的名称。  <br/> |
|CallerRegion  <br/> |nvarchar(128)  <br/> |呼叫者的站点的国家/地区的名称。  <br/> |
|CalleeUserSite  <br/> |nvarchar(128)  <br/> |被叫方的站点的名称。  <br/> |
|CalleeRegion  <br/> |nvarchar(128)  <br/> |被叫方的站点的国家/地区的名称。  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |IP 地址的 A / V 边缘服务使用的呼叫者。 请参阅[IPAddress 表](ipaddress.md)的详细信息。 <br/> |
|CallerRelayPort  <br/> |int  <br/> |端口在 a / V 边缘服务使用的呼叫者。  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |IP 地址密钥的 A / V 边缘服务由被叫方。 请参阅[IPAddress 表](ipaddress.md)的详细信息。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |端口在 a / V 边缘服务由被叫方。  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |呼叫者的捕获设备名称。  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |呼叫者呈现设备名称。  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |呼叫者的捕获设备驱动程序名称。  <br/> |
|CallerRenderDriver  <br/> |varchar(256)  <br/> |呼叫者的呈现设备驱动程序名称。  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |被叫方的捕获设备名称。  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |被叫方的呈现设备名称。  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |被叫方的捕获设备驱动程序名称。  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |被叫方的呈现设备驱动程序名称。  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |呼叫者的网络连接类型： 0 有线，1 是无线。  <br/> |
|CallerVPN  <br/> |bit  <br/> |指示呼叫者是否通过虚拟专用网络连接： 1 是虚拟专用网络 (VPN)，0 为非 VPN。  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,0)  <br/> |Bps 中的呼叫者的终结点的网络链接速度。  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |被叫方的网络连接类型： 0 有线，1 是无线。  <br/> |
|CalleeVPN  <br/> |bit  <br/> |指示呼叫者是否通过虚拟专用网络连接： 1 是虚拟专用网络 (VPN)，0 为非 VPN。  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |被叫方的终结点 bps 中的网络链接速度。  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |窄带交谈 MOS （基于两个音频流） 的音频会话。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |应用于给定的各种策略设置 （打开、 API、 SDP、 策略服务器等） 的给定的发送端流实际带宽。 这是不是有效的带宽与混淆，因为可以基于带宽估计较低的有效带宽。 基本上是发送流花费除非按带宽估计施加限制的最大带宽  <br/> |
|JitterInterArrival  <br/> |int  <br/> |实时控制协议 (RTCP) 统计信息中的平均网络抖动。  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |呼叫期间的最大网络抖动。  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |呼叫期间的平均数据包丢失率。  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |呼叫期间观测到的最大的数据包丢失。  <br/> |
|BurstDensity  <br/> |decimal(9,4)  <br/> |在呼叫过程中出现间歇的数据包丢失的平均密度。  <br/> |
|BurstDuration  <br/> |int  <br/> |在呼叫过程中出现间歇的数据包丢失的平均持续时间。  <br/> |
|BurstGapDensity  <br/> |decimal(9,4)  <br/> |间歇的数据包丢失之间出现间隙期间数据包丢失的平均密度。  <br/> |
|BurstGapDuration  <br/> |int  <br/> |间歇的数据包丢失之间出现间隙的平均持续时间。  <br/> |
|PacketUtilization  <br/> |int  <br/> |音频流的数据包计数。  <br/> |
|BandwidthEst  <br/> |int  <br/> |音频流的带宽预估。  <br/> |
|DegradationAvg  <br/> |decimal(3,2)  <br/> |用于整个呼叫的网络 MOS 性能降低。 范围是 0.0 为 5.0。 此指标显示网络 MOS 减少由于抖动和丢包的量。 可接受的质量，它应小于 0.5。  <br/> |
|DegradationMax  <br/> |decimal(3,2)  <br/> |呼叫期间的最大网络 MOS 性能降低。  <br/> |
|DegradationJitterAvg  <br/> |decimal(3,2)  <br/> |抖动导致的网络 MOS 性能降低。  <br/> |
|DegradationPacketLossAvg  <br/> |decimal(3,2)  <br/> |数据包丢失导致的网络 MOS 性能降低。  <br/> |
|PayloadDescription  <br/> |int  <br/> |音频编解码器用于呼叫，引用[自 PayloadDescription table](payloaddescription.md)。  <br/> |
|AudioSampleRate  <br/> |int  <br/> |音频流的采样率。  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |后模拟增益控制音频信号级别实现音频呼叫者发送。 此度量单位是 dBmo。 对于可接受的质量，它应至少 30 dBmo。 此指标未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |音频呼叫者收到的音频信号级别。 此度量单位是 dBmo。 对于可接受的质量，它应至少 30 dBmo。 此指标未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |对于音频呼叫者发送后模拟增益控制音频的噪音级别。 此度量单位是 dBmo。 对于可接受的质量，它应小于 35 dBmo。 此指标未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |对于音频呼叫者接收后模拟增益控制音频的噪音级别。 此度量单位是 dBmo。 对于可接受的质量，它应小于 35 dBmo。 此指标未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |回声返回丢失增强呼叫者。 此度量单位是 dB。 较低值表示减少回声。 此指标未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |每五分钟的呼叫者的扬声器呈现的平均难题。 良好质量，应小于 1 每五分钟。 未报告的 A / V 会议服务器、 中介服务器或 IP 电话。  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |平均难题每五分钟的呼叫者的麦克风捕获。 良好质量这应该是小于 1 每五分钟。 未报告的 A / V 会议服务器、 中介服务器或 IP 电话。  <br/> |
|CallerTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |呼叫者的麦克风设备时钟的偏移率，相对于 CPU 时钟。  <br/> |
|CallerTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |呼叫者的扬声器设备时钟的偏移率，相对于 CPU 时钟。  <br/> |
|CallerTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |呼叫的最后 20 秒内的平均麦克风捕获流时间戳错误，以毫秒为单位。  <br/> |
|CallerTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |将呈现流时间戳错误，以毫秒为单位的呼叫者的扬声器平均呼叫的最后 20 秒内。  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |语音切换是半双工模式，减少了的中断功能。 请参阅[自 MediaLine table](medialine-0.md)的详细信息。 <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |呼叫者的回声事件的原因。 请参阅[自 MediaLine table](medialine-0.md)的详细信息。 <br/> |
|CallerEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |在呼叫者的麦克风捕获流中检测到回声的时的时间的百分比。 如果使用耳麦，则值应为低。  <br/> |
|CallerEchoPercentSend  <br/> |decimal(5,2)  <br/> |当呼叫者中检测到回声的时间的百分比的发送流。 在高回声百分比发送流相对值的回声泄漏。  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |从网关的呼叫者的音频，则在中介服务器上收到的信号级别这仅适用于中介服务器。 此指标的单位是 dBoV。 良好质量，可接受的范围应为-30 至-18 dBoV。  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |已收到的信号级别从呼叫者的网关在中介服务器上的音频。 这仅适用于中介服务器。 此指标的单位是 dBoV。 良好质量，可接受的范围应小于-50 dBoV。  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |在应用到呼叫者音频的中介服务器方的自动增益控制 (AGC)。  <br/> |
|CallerInitialSignalLevelRMS  <br/> |float  <br/> |方根 (RMS) 到最多为前 30 秒钟的呼叫的呼叫者的传入信号的均。  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |表示被叫方发送的音频的后模拟增益控制音频信号级别。 此度量单位是 dBmo。 对于可接受的质量，它应至少 30 dBmo。 此指标未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |对于音频被叫方接收音频信号级别。 此度量单位是 dBmo。 对于可接受的质量，它应至少 30 dBmo。 此指标未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |对于音频被叫方发送后模拟增益控制音频的噪音级别。 此度量单位是 dBmo。 对于可接受的质量，它应小于 35 dBmo。 此指标未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |被叫方接收音频后模拟增益控制音频的噪音级别。 此度量单位是 dBmo。 对于可接受的质量，它应小于 35 dBmo。 此指标未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |回声返回丢失增强的被叫方。 此度量单位是 dB。 较低值表示减少回声。 此指标未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |每五分钟的被叫方的扬声器呈现的平均难题。 良好质量，应小于 1 每五分钟。 未报告的 A / V 会议服务器、 中介服务器或 IP 电话。  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |平均难题每五分钟的被叫方的麦克风捕获。 良好质量这应该是小于 1 每五分钟。 未报告的 A / V 会议服务器、 中介服务器或 IP 电话。  <br/> |
|CalleeTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |被叫方的麦克风设备时钟的偏移率，相对于 CPU 时钟。  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |被叫方的扬声器设备时钟的偏移率，相对于 CPU 时钟。  <br/> |
|CalleeTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |呼叫的最后 20 秒内的平均麦克风捕获流时间戳错误，以毫秒为单位。  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |被叫方的扬声器的平均呼叫的最后 20 秒内呈现流时间戳错误，以毫秒为单位。  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |语音切换是半双工模式，减少了的中断功能。 请参阅[自 MediaLine table](medialine-0.md)的详细信息。 <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |被叫方的回声事件的原因。 请参阅[自 MediaLine table](medialine-0.md)的详细信息。 <br/> |
|CalleeEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |被叫方的麦克风捕获流中检测到回声的时的时间的百分比。 如果使用耳麦，则值应为低。  <br/> |
|CalleeEchoPercentSend  <br/> |decimal(5,2)  <br/> |回声检测到被叫方中时的时间的百分比的发送流。 在高回声百分比发送流相对值的回声泄漏。  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |从被叫方的音频，则网关在中介服务器上收到的信号级别这仅适用于中介服务器。 此指标的单位是 dBoV。 良好质量，可接受的范围应 [-30-18 至] dBoV。  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |已收到的信号级别从被叫方的网关在中介服务器上的音频。 这仅适用于中介服务器。 此指标的单位是 dBoV。 良好质量，可接受的范围应小于-50 dBoV。  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |在应用到被叫方的音频的中介服务器方的自动增益控制 (AGC)。  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |float  <br/> |方根 (RMS) 到被叫方的最多的呼叫的前 30 秒钟的传入信号的均。  <br/> |
|RatioConcealedSamplesAvg  <br/> |decimal(5,2)  <br/> |生成的典型示例音频样本隐藏样本数的平均比率。  <br/> |
|RatioStretchedSamplesAvg  <br/> |decimal(5,2)  <br/> |通过典型示例的音频修复生成的拉伸样本数的平均比率。  <br/> |
|RatioCompressedSamplesAvg  <br/> |decimal(5,2)  <br/> |生成的典型示例的音频修复的压缩样本数的平均比率。  <br/> |
|RoundTrip  <br/> |int  <br/> |RTCP 统计信息中的来回行程时间。  <br/> |
|RoundTripMax  <br/> |int  <br/> |音频流的最大来回行程时间。  <br/> |
|OverallAvgNetworkMOS  <br/> |decimal(3,2)  <br/> |平均宽带网络 MOS，呼叫。 此指标取决于数据包丢失、 抖动和编解码器。 范围是 1.0 到 5.0。  <br/> |
|OverallMinNetworkMOS  <br/> |decimal(3,2)  <br/> |最小宽带网络 MOS，呼叫。  <br/> |
|SendListenMOS  <br/> |decimal(3,2)  <br/> |平均预测的宽带倾听 MOS 得分音频发送，包括语音级别、 噪音级别和捕获设备特征。  <br/> |
|SendListenMOSMin  <br/> |decimal(3,2)  <br/> |呼叫的最小 SendListenMOS。  <br/> |
|RecvListenMOS  <br/> |decimal(3,2)  <br/> |从网络包括语音级别、 噪音级别、 编解码器、 网络条件和捕获设备特征接收音频的平均预测的宽带倾听 MOS 得分。  <br/> |
|RecvListenMOSMin  <br/> |decimal(3,2)  <br/> |呼叫的最小 RecvListenMOS。  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |指示音频 FEC 是否已用于呼叫。  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |指示方向的 p 已断言标识信息;1 表示流方向从呼叫者到被叫方;0 表示流方向从被叫方到呼叫者。  <br/> |
   

