---
title: AudioStreamDetail 视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: AudioStreamDetail 视图在数据库中存储有关每个音频流信息。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: 4dadc53f0641e2d59dc72b2add433c69fc9b8ad1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="audiostreamdetail-view"></a>AudioStreamDetail 视图
 
AudioStreamDetail 视图在数据库中存储有关每个音频流信息。 在 Microsoft Lync Server 2013 引入了此视图。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |从[MediaLine 表](medialine-0.md)引用。  <br/> |
|SessionSeq  <br/> |int  <br/> |从[MediaLine 表](medialine-0.md)引用。  <br/> |
|StreamId  <br/> |int  <br/> |在媒体行的唯一 ID。  <br/> |
|开始时间  <br/> |datetime  <br/> |会话的开始时间。  <br/> |
|结束时间  <br/> |datetime  <br/> |会话的结束时间。  <br/> |
|DialogCategory  <br/> |bit  <br/> |对话框类别： 0 是 Skype 业务服务器到中介服务器腿;1 是中介服务器到 PSTN 网关腿。  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |该标志指明如果呼叫被绕过或不。  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |如果存在，表明为什么调用不会绕过即使旁路 Id 匹配。 只有一个值的定义：  <br/> 0x0001-未知绕过默认的网络适配器的 ID。  <br/> |
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
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |在调用方的端点的 CPU 内核的数量。  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |被调用方的端点中的 CPU 内核的数量。  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |调用方的端点的 CPU 处理器速度。  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |被调用方的端点的 CPU 处理器速度。  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |指示是否在虚拟化环境中运行呼叫者的系统。 [终结点表](endpoint.md)的详细信息，请参阅。 <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |指示被调用方的系统是否正在运行在虚拟化环境中。 [终结点表](endpoint.md)的详细信息，请参阅。 <br/> |
|CorrelationKey  <br/> ||关联的键。 从[SessionCorrelation 表](sessioncorrelation.md)引用。  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |有关介质路径的信息，如直接或中继。 [MediaLine 表](medialine-0.md)的详细信息，请参阅。 <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |交互式连接建立 (ICE) 过程中介绍有关信息位标志的调用方。 有关详细信息，请参阅质量的体验监视服务器协议规范。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |有关交互式连接建立 (ICE) 过程的信息所述位标志的被调用方。 有关详细信息，请参阅质量的体验监视服务器协议规范。  <br/> |
|Transport  <br/> |tinyint  <br/> |传输类型： 0 是 UDP，1 是 TCP。  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |调用方的 IP 地址。 这可能是 IPv4 或 IPv6 地址。  <br/> |
|CallerPort  <br/> |int  <br/> |呼叫者使用的端口。  <br/> |
|CallerInside  <br/> |bit  <br/> |指示调用方是否在间隔网络： 1 方法调用方位于企业网络，0 表示调用方是网络之外。  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |被调用方的 IP 地址。 这可能是 IPv4 或 IPv6 地址。  <br/> |
|CalleePort  <br/> |int  <br/> |被调用方所使用的端口。  <br/> |
|CalleeInside  <br/> |bit  <br/> |指示被调用方是否在间隔网络： 1 的方法被调用方位于企业网络，0 表示被调用方位于外部网络。  <br/> |
|CallerUserSite  <br/> |nvarchar(128)  <br/> |呼叫者的站点的名称。  <br/> |
|CallerRegion  <br/> |nvarchar(128)  <br/> |调用方的网站的国家/地区的名称。  <br/> |
|CalleeUserSite  <br/> |nvarchar(128)  <br/> |被调用方的站点的名称。  <br/> |
|CalleeRegion  <br/> |nvarchar(128)  <br/> |被调用方的网站的国家/地区的名称。  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |IP 地址的 A / V 边缘服务由调用方。 [Ip 地址表](ipaddress.md)的详细信息，请参阅。 <br/> |
|CallerRelayPort  <br/> |int  <br/> |端口用于 A / V 边缘服务由调用方。  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |IP 地址键的 A / V 边缘服务由被调用方。 [Ip 地址表](ipaddress.md)的详细信息，请参阅。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |端口用于 A / V 边缘服务由被调用方。  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |调用方的捕获设备名称。  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |调用方的呈现的设备名称。  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |调用方的捕获设备驱动程序的名称。  <br/> |
|CallerRenderDriver  <br/> |varchar(256)  <br/> |调用方的呈现的设备驱动程序的名称。  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |被调用方的捕获设备名称。  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |被调用方的呈现的设备名称。  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |被调用方的捕获设备驱动程序的名称。  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |被调用方的呈现的设备驱动程序的名称。  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |呼叫者的网络连接类型： 0 有线，1 为无线。  <br/> |
|CallerVPN  <br/> |bit  <br/> |指示调用方是否通过虚拟专用网络连接： 1 为虚拟专用网络 (VPN)，0 为非 VPN。  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,0)  <br/> |在 bps 中的调用方的端点的网络链接速度。  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |被调用方的网络连接类型： 0 有线，1 为无线。  <br/> |
|CalleeVPN  <br/> |bit  <br/> |指示调用方是否通过虚拟专用网络连接： 1 为虚拟专用网络 (VPN)，0 为非 VPN。  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |对于被调用方的端点在 bps 中网络链接速度。  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |窄带的口语 MOS （根据这两个音频流） 中的音频会话。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |实际带宽应用到给定的发送端流给出各种策略设置 （启用、 API、 SDP、 策略服务器等等）。 这并不是因为可以有较低的有效带宽基于带宽估计能有效带宽与混淆。 这基本上是发送流可以采取除非限制规定的带宽估计的最大带宽  <br/> |
|JitterInterArrival  <br/> |int  <br/> |从实时控制协议 (RTCP) 统计的平均网络抖动。  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |在调用过程的最大网络抖动。  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |在调用过程平均数据包丢失率。  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |在调用期间观察到的最大数据包丢失。  <br/> |
|BurstDensity  <br/> |decimal(9,4)  <br/> |在过程调用中的损失的突发数据包丢失的平均密度。  <br/> |
|BurstDuration  <br/> |int  <br/> |平均持续时间在猝发过程中调用的损失的期间丢失数据包的情况。  <br/> |
|BurstGapDensity  <br/> |decimal(9,4)  <br/> |数据包丢失期间突发的数据包丢失率之间的差距平均密度。  <br/> |
|BurstGapDuration  <br/> |int  <br/> |猝发的数据包丢失率之间的差距平均持续时间。  <br/> |
|PacketUtilization  <br/> |int  <br/> |音频流的数据包数。  <br/> |
|BandwidthEst  <br/> |int  <br/> |带宽估计的音频流。  <br/> |
|DegradationAvg  <br/> |decimal(3,2)  <br/> |整个呼叫网络 MOS 有所下降。 范围是 0.0 到 5.0。 此统计数据显示了网络 MOS 减少由于抖动和包丢失量。 可接受的质量应该小于 0.5。  <br/> |
|DegradationMax  <br/> |decimal(3,2)  <br/> |在调用过程的最大网络 MOS 下降。  <br/> |
|DegradationJitterAvg  <br/> |decimal(3,2)  <br/> |网络 MOS 下降引起的抖动。  <br/> |
|DegradationPacketLossAvg  <br/> |decimal(3,2)  <br/> |网络数据包丢失所致的 MOS 下降。  <br/> |
|PayloadDescription  <br/> |int  <br/> |音频编解码器用于呼叫，从[PayloadDescription 表](payloaddescription.md)引用。  <br/> |
|AudioSampleRate  <br/> |int  <br/> |采样速度，以音频流。  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |调用方发送的音频后模拟获得控制音频信号级别。 此度量单位是 dBmo。 对于可接受的质量，它应该至少 30 dBmo。 此统计数据未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |调用方接收到的音频的音频信号级别。 此度量单位是 dBmo。 对于可接受的质量，它应该至少 30 dBmo。 此统计数据未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |调用方发送的音频后模拟获得控制音频噪声级别。 此度量单位是 dBmo。 对于可接受的质量，它应该是少于 35 dBmo。 此统计数据未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |后模拟获得控制音频噪声音频接收到调用方。 此度量单位是 dBmo。 对于可接受的质量，它应该是少于 35 dBmo。 此统计数据未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |回声返回丢失增强对调用方。 此度量单位为 dB。 较低的值表示较少的回响。 此统计数据未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |每个调用方的扬声器呈现五分钟的平均失灵。 良好的质量，这应该是每五分钟不少于一次。 未报告的 A / V 会议服务器、 中介服务器或 IP 电话。  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |平均每五分钟的时间调用方的麦克风失灵捕获。 良好的质量，这应该是每五分钟不少于一次。 未报告的 A / V 会议服务器、 中介服务器或 IP 电话。  <br/> |
|CallerTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |调用方的麦克风设备时钟偏移比率，相对于 CPU 时钟。  <br/> |
|CallerTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |调用方的扬声器设备时钟偏移比率，相对于 CPU 时钟。  <br/> |
|CallerTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |平均的麦克风捕捉流时间戳错误，以毫秒为单位，在最后 20 秒的呼叫。  <br/> |
|CallerTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |调用方的扬声器的平均呈现流时间戳错误，以毫秒为单位，在最后 20 秒的呼叫。  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |语音交换机是半双工模式，减少了的中断能力。 [MediaLine 表](medialine-0.md)的详细信息，请参阅。 <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |调用方的回应事件的原因。 [MediaLine 表](medialine-0.md)的详细信息，请参阅。 <br/> |
|CallerEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |当回响时检测到调用方的麦克风捕获流的时间的百分比。 如果使用头戴式耳机，则值应为低。  <br/> |
|CallerEchoPercentSend  <br/> |decimal(5,2)  <br/> |在调用方中检测到回声时的时间的百分比的发送流。 在高回声百分比将流发送回显泄漏的指示。  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |从调用方的音频，则网关中介服务器的接收的信号强度这仅适用于中介服务器。 此度量单位是 dBoV。 良好的质量，在可接受范围应为 dBoV-18-30。  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |从调用方的网关中介服务器上接收到的信号级别的音频。 这仅适用于中介服务器。 此度量单位是 dBoV。 良好的质量，在可接受范围应小于-50 dBoV。  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |自动控制 (AGC) 在中介服务器端到调用方的音频应用。  <br/> |
|CallerInitialSignalLevelRMS  <br/> |float  <br/> |根均方 (RMS) 的调用方调用前 30 秒到传入信号。  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |表示被调用方发送的音频后模拟获得控制音频信号级别。 此度量单位是 dBmo。 对于可接受的质量，它应该至少 30 dBmo。 此统计数据未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |被调用方接收到的音频的音频信号级别。 此度量单位是 dBmo。 对于可接受的质量，它应该至少 30 dBmo。 此统计数据未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |对于被调用方发送的音频后模拟获得控制音频噪声级别。 此度量单位是 dBmo。 对于可接受的质量，它应该是少于 35 dBmo。 此统计数据未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |对于被调用方接收到的音频后模拟获得控制音频噪声级别。 此度量单位是 dBmo。 对于可接受的质量，它应该是少于 35 dBmo。 此统计数据未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |回声返回丢失增强被调用方。 此度量单位为 dB。 较低的值表示较少的回响。 此统计数据未报告的 A / V 会议服务器或 IP 电话。  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |每五分钟的时间被调用方的扬声器呈现的平均失灵。 良好的质量，这应该是每五分钟不少于一次。 未报告的 A / V 会议服务器、 中介服务器或 IP 电话。  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |平均每五分钟的时间被调用方的麦克风失灵捕获。 良好的质量，这应该是每五分钟不少于一次。 未报告的 A / V 会议服务器、 中介服务器或 IP 电话。  <br/> |
|CalleeTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |被调用方的麦克风设备时钟偏移比率，相对于 CPU 时钟。  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |被调用方的扬声器设备时钟偏移比率，相对于 CPU 时钟。  <br/> |
|CalleeTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |平均的麦克风捕捉流时间戳错误，以毫秒为单位，在最后 20 秒的呼叫。  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |被调用方的扬声器的平均呈现流时间戳错误，以毫秒为单位，在最后 20 秒的呼叫。  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |语音交换机是半双工模式，减少了的中断能力。 [MediaLine 表](medialine-0.md)的详细信息，请参阅。 <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |对于被调用方回响事件的原因。 [MediaLine 表](medialine-0.md)的详细信息，请参阅。 <br/> |
|CalleeEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |在被调用方的麦克风捕捉流中检测到回音的时的时间的百分比。 如果使用头戴式耳机，则值应为低。  <br/> |
|CalleeEchoPercentSend  <br/> |decimal(5,2)  <br/> |回声检测到被调用方中时的时间的百分比的发送流。 在高回声百分比将流发送回显泄漏的指示。  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |从被调用方的音频，则网关中介服务器的接收的信号强度这仅适用于中介服务器。 此度量单位是 dBoV。 良好的质量，对于可接受的范围应为 [-30 至-18] dBoV。  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |从被调用方的网关中介服务器上的接收的信号电平的音频。 这仅适用于中介服务器。 此度量单位是 dBoV。 良好的质量，在可接受范围应小于-50 dBoV。  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |自动控制 (AGC) 在中介服务器端到被调用方的音频应用。  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |float  <br/> |根均方 (RMS) 到被调用方的调用的第一个 30 秒到传入信号。  <br/> |
|RatioConcealedSamplesAvg  <br/> |decimal(5,2)  <br/> |生成的音频康复对典型样本的隐蔽样本的平均比率。  <br/> |
|RatioStretchedSamplesAvg  <br/> |decimal(5,2)  <br/> |拉伸示例生成的音频康复对典型样本的平均比率。  <br/> |
|RatioCompressedSamplesAvg  <br/> |decimal(5,2)  <br/> |通过对典型样本的音频修复生成压缩样本的平均比率。  <br/> |
|往返  <br/> |int  <br/> |从 RTCP 统计信息的往返时间。  <br/> |
|RoundTripMax  <br/> |int  <br/> |音频流的最大往返时间。  <br/> |
|OverallAvgNetworkMOS  <br/> |decimal(3,2)  <br/> |宽带网络 MOS 的调用的平均。 此指标取决于数据包丢失、 抖动和使用的编解码器。 范围是 1.0 到 5.0。  <br/> |
|OverallMinNetworkMOS  <br/> |decimal(3,2)  <br/> |最小的宽带网络 MOS 的呼叫。  <br/> |
|SendListenMOS  <br/> |decimal(3,2)  <br/> |平均预测的宽带侦听 MOS 得分音频发送，包括语音级别、 噪音级别和捕获设备特征。  <br/> |
|SendListenMOSMin  <br/> |decimal(3,2)  <br/> |调用的最小 SendListenMOS。  <br/> |
|RecvListenMOS  <br/> |decimal(3,2)  <br/> |平均预测的宽带音频监听 MOS 得分来自网络包括语音级别、 噪声水平、 编解码器、 网络状况和捕获设备特征。  <br/> |
|RecvListenMOSMin  <br/> |decimal(3,2)  <br/> |调用的最小 RecvListenMOS。  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |指示音频 FEC 用于调用。  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |指示方向 p 断言标识信息;1 表示流方向是从调用方到被调用方。0 表示流方向是从被调用方调用方。  <br/> |
   

