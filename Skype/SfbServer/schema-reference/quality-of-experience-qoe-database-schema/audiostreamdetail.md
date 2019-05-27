---
title: AudioStreamDetail 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: AudioStreamDetail 视图存储有关数据库中每个音频流的信息。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 16f97fc367b171ceb0ddc5b5c0024bd88c7b5268
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295053"
---
# <a name="audiostreamdetail-view"></a>AudioStreamDetail 视图
 
AudioStreamDetail 视图存储有关数据库中每个音频流的信息。 此视图已在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |从[MediaLine 表](medialine-0.md)中引用。  <br/> |
|SessionSeq  <br/> |int  <br/> |从[MediaLine 表](medialine-0.md)中引用。  <br/> |
|StreamId  <br/> |int  <br/> |媒体行内的唯一 ID。  <br/> |
|StartTime  <br/> |datetime  <br/> |会话的开始时间。  <br/> |
|EndTime  <br/> |datetime  <br/> |会话的结束时间。  <br/> |
|DialogCategory  <br/> |bit  <br/> |对话框类别: 0 是 Skype for business 服务器, 用于采集服务器腿;1是中介服务器到 PSTN 网关腿。  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |指示是否已绕过呼叫的标志。  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |如果存在, 则指示未跳过呼叫的原因, 即使旁路 Id 匹配也是如此。 仅定义了一个值:  <br/> 0x0001-默认网络适配器的旁路 ID 未知。  <br/> |
|CallPriority  <br/> |int  <br/> |通话的优先级。  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |呼叫方池 FQDN。  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |被调用池 FQDN。  <br/> |
|呼叫者  <br/> |nvarchar (450)  <br/> |调用方的 URI。  <br/> |
|被叫方  <br/> |nvarchar (450)  <br/> |被调用方的 URI。  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |呼叫方的用户代理字符串。  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |呼叫方的用户代理的类型。 有关详细信息, 请参阅[UserAgent 表](useragent.md)。 <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |呼叫方的用户代理类别。 有关详细信息, 请参阅[UserAgentDef 表 (QoE)](useragentdef-qoe.md) 。 <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |被呼叫方的用户代理字符串。  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |被调用方的用户代理的类型。 有关信息, 请参阅[UserAgent 表](useragent.md)。 <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |被呼叫方的用户代理类别。 有关信息, 请参阅[UserAgentDef 表 (QoE)](useragentdef-qoe.md) 。 <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |调用方的终结点名称。  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |被调用方的终结点名称。  <br/> |
|CallerOS  <br/> |nvarchar  <br/> |呼叫方终结点的操作系统 (OS)。  <br/> |
|CalleeOS  <br/> |nvarchar  <br/> |被调用方终结点的操作系统 (OS)。  <br/> |
|CallerCPUName  <br/> |nvarchar  <br/> |呼叫方终结点的 CPU 名称。  <br/> |
|CalleeCPUName  <br/> |nvarchar  <br/> |被调用方终结点的 CPU 名称。  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |呼叫方终结点中的 CPU 内核数。  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |被调用方的终结点中的 CPU 内核数。  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |呼叫方终结点的 CPU 处理器速度。  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |被调用方终结点的 CPU 处理器速度。  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |指示呼叫者的系统是否在虚拟化环境中运行。 有关详细信息, 请参阅[终结点表](endpoint.md)。 <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |指示被调用方的系统是否在虚拟化环境中运行。 有关详细信息, 请参阅[终结点表](endpoint.md)。 <br/> |
|CorrelationKey  <br/> ||相关密钥。 从[SessionCorrelation 表](sessioncorrelation.md)中引用。  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |有关媒体路径 (如直接或中继) 的信息。 有关详细信息, 请参阅[MediaLine 表](medialine-0.md)。 <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |有关在呼叫者的位标志中描述的交互式连接建立 (ICE) 流程的信息。 有关详细信息, 请参阅体验质量监视服务器协议规范。  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |有关被调用方的位标志中所述的交互式连接建立 (ICE) 流程的信息。 有关详细信息, 请参阅体验质量监视服务器协议规范。  <br/> |
|Transport  <br/> |tinyint  <br/> |传输类型: 0 是 UDP, 1 是 TCP。  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |呼叫方的 IP 地址。 这可能是 IPv4 地址或 IPv6 地址。  <br/> |
|CallerPort  <br/> |int  <br/> |呼叫方使用的端口。  <br/> |
|CallerInside  <br/> |bit  <br/> |指示呼叫者是否在间隔网络内: 1 表示呼叫方位于企业网络内, 0 表示呼叫方位于网络外部。  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |被呼叫方的 IP 地址。 这可能是 IPv4 地址或 IPv6 地址。  <br/> |
|CalleePort  <br/> |int  <br/> |被呼叫方使用的端口。  <br/> |
|CalleeInside  <br/> |bit  <br/> |指示被调用方是否在间隔网络内: 1 表示被呼叫方位于企业网络内, 0 表示被呼叫方位于网络外部。  <br/> |
|CallerUserSite  <br/> |nvarchar  <br/> |呼叫者站点的名称。  <br/> |
|CallerRegion  <br/> |nvarchar  <br/> |呼叫方网站的国家/地区的名称。  <br/> |
|CalleeUserSite  <br/> |nvarchar  <br/> |被调用方的网站的名称。  <br/> |
|CalleeRegion  <br/> |nvarchar  <br/> |被呼叫方网站的国家/地区的名称。  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |呼叫方使用的 A/V 边缘服务的 IP 地址。 有关详细信息, 请参阅[IPAddress 表](ipaddress.md)。 <br/> |
|CallerRelayPort  <br/> |int  <br/> |由呼叫方使用的 A/V 边缘服务使用的端口。  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |被呼叫方使用的 A/V 边缘服务的 IP 地址密钥。 有关详细信息, 请参阅[IPAddress 表](ipaddress.md)。 <br/> |
|CalleeRelayPort  <br/> |int  <br/> |用于由被呼叫方使用的 A/V 边缘服务的端口。  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |呼叫方的捕获设备名称。  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |调用方的呈现设备名称。  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |呼叫方的捕获设备驱动程序名称。  <br/> |
|CallerRenderDriver  <br/> |varchar (256)  <br/> |呼叫方的呈现设备驱动程序名称。  <br/> |
|CalleeCaptureDev  <br/> |varchar (256)  <br/> |被调用方的捕获设备名称。  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |被调用方的呈现设备名称。  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar (256)  <br/> |被调用方的捕获设备驱动程序名称。  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |被调用方的呈现设备驱动程序名称。  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |呼叫者的网络连接类型: 0 是 "有线", 1 是 "无线"。  <br/> |
|CallerVPN  <br/> |bit  <br/> |指示呼叫者是否通过虚拟专用网络连接: 1 是虚拟专用网 (VPN), 0 是非 VPN。  <br/> |
|CallerLinkSpeed  <br/> |十进制 (18, 0)  <br/> |呼叫方终结点的网络链接速度 (以 bps 为实现)。  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |被呼叫方的网络连接类型: 0 是 "有线", 1 是 "无线"。  <br/> |
|CalleeVPN  <br/> |bit  <br/> |指示呼叫者是否通过虚拟专用网络连接: 1 是虚拟专用网 (VPN), 0 是非 VPN。  <br/> |
|CalleeLinkSpeed  <br/> |十进制 (18, 0)  <br/> |被呼叫方终结点的网络链接速度, 以 bps 为限。  <br/> |
|ConversationalMOS  <br/> |十进制 (3, 2)  <br/> |音频会话的 Narrowband 对话 MOS (基于两个音频流)。  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |在给定各种策略设置 (TURN、API、SDP、策略服务器等) 的情况下, 应用到给定发送端流的实际带宽。 此操作不会与有效的带宽混淆, 因为根据带宽估计, 可能会有较低的有效带宽。 这基本上是发送流对带宽估计所施加限制限制的最大带宽  <br/> |
|JitterInterArrival  <br/> |int  <br/> |实时控制协议 (RTCP) 统计信息的平均网络抖动。  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |通话期间网络抖动的最大值。  <br/> |
|PacketLossRate  <br/> |十进制 (5, 4)  <br/> |通话期间平均数据包丢失速率。  <br/> |
|PacketLossRateMax  <br/> |十进制 (5, 4)  <br/> |通话过程中观察到的最大数据包丢失。  <br/> |
|BurstDensity  <br/> |十进制 (9, 4)  <br/> |通话期间出现猝发损失期间的数据包丢失的平均密度。  <br/> |
|BurstDuration  <br/> |int  <br/> |通话期间出现猝发损失期间的数据包丢失的平均持续时间。  <br/> |
|BurstGapDensity  <br/> |十进制 (9, 4)  <br/> |出现猝发数据包丢失之间的平均数据包损失的平均密度。  <br/> |
|BurstGapDuration  <br/> |int  <br/> |爆发数据包损失之间的平均持续时间。  <br/> |
|PacketUtilization  <br/> |int  <br/> |音频流的数据包计数。  <br/> |
|BandwidthEst  <br/> |int  <br/> |音频流的带宽估计。  <br/> |
|DegradationAvg  <br/> |十进制 (3, 2)  <br/> |整个通话的网络 MOS 降级。 范围为0.0 到5.0。 此指标显示由于抖动和数据包丢失, 网络 MOS 的减少量。 对于可接受的质量, 它应小于0.5。  <br/> |
|DegradationMax  <br/> |十进制 (3, 2)  <br/> |通话期间最大网络 MOS 性能下降。  <br/> |
|DegradationJitterAvg  <br/> |十进制 (3, 2)  <br/> |由抖动导致的网络 MOS 性能下降。  <br/> |
|DegradationPacketLossAvg  <br/> |十进制 (3, 2)  <br/> |由于数据包丢失导致网络 MOS 性能下降。  <br/> |
|PayloadDescription  <br/> |int  <br/> |用于调用的音频编解码器, 从[PayloadDescription 表](payloaddescription.md)中引用。  <br/> |
|AudioSampleRate  <br/> |int  <br/> |音频流的采样率。  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |呼叫者发送的音频的模拟增益控制音频信号级别。 此指标的单位为 dBmo。 为获得可接受的质量, 它至少应为 30 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |呼叫者收到的音频的音频信号级别。 此指标的单位为 dBmo。 为获得可接受的质量, 它至少应为 30 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |为呼叫者发送的音频的模拟后增益控制音频噪音级别。 此指标的单位为 dBmo。 为获得可接受的质量, 它应小于 35 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |呼叫者收到的音频的后模拟增益控制音频噪音级别。 此指标的单位为 dBmo。 为获得可接受的质量, 它应小于 35 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |呼叫方的回音返回损失增强。 此指标的单位为 dB。 较低的值表示较少的回声。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |呼叫者的扬声器呈现每五分钟的平均故障。 为了获得良好的质量, 这应该小于每五分钟一次。 不由 A/V 式会议服务器、中介服务器或 IP 电话报告。  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |呼叫者的麦克风捕获每五分钟的平均故障。 为了获得良好的质量, 这应该小于每五分钟一次。 不由 A/V 式会议服务器、中介服务器或 IP 电话报告。  <br/> |
|CallerTimestampDriftRateMic  <br/> |十进制 (9, 2)  <br/> |呼叫者的麦克风设备时钟偏移速率, 相对于 CPU 时钟。  <br/> |
|CallerTimestampDriftRateSpk  <br/> |十进制 (9, 2)  <br/> |呼叫者的扬声器设备时钟偏移率 (相对于 CPU 时钟)。  <br/> |
|CallerTimestampErrorMicMs  <br/> |十进制 (9, 2)  <br/> |在呼叫的最后20秒内, 麦克风捕获流时间戳的平均时间戳错误 (以毫秒为单位)。  <br/> |
|CallerTimestampErrorSpkMs  <br/> |十进制 (9, 2)  <br/> |呼叫者最近20秒内呼叫者的扬声器渲染流时间戳错误的平均值。  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |语音开关是一种具有更低中断能力的半双工模式。 有关详细信息, 请参阅[MediaLine 表](medialine-0.md)。 <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |呼叫方的 echo 事件的原因。 有关详细信息, 请参阅[MediaLine 表](medialine-0.md)。 <br/> |
|CallerEchoPercentMicIn  <br/> |十进制 (5, 2)  <br/> |在呼叫者的麦克风捕获流中检测到回声的时间的百分比。 如果使用耳机, 则该值应较低。  <br/> |
|CallerEchoPercentSend  <br/> |十进制 (5, 2)  <br/> |在呼叫方的发送流中检测到回显的时间的百分比。 发送流中的高回显百分比表示回声泄漏。  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |在中介服务器上收到来自呼叫者音频的网关的信号级别;这仅适用于中介服务器。 此指标的单位为 dBoV。 为了获得优质, 可接受范围应为-30 至-18 dBoV。  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |在中介服务器上从呼叫方音频的网关接收的信号级别。 这仅适用于中介服务器。 此指标的单位为 dBoV。 为了获得优质, 可接受范围应小于-50 dBoV。  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |在中介服务器端应用于呼叫方音频的自动增益控制 (AGC)。  <br/> |
|CallerInitialSignalLevelRMS  <br/> |float  <br/> |呼叫方的传入信号的根平均值平方 (RMS), 最多可拨出前30秒。  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |表示被呼叫者发送的音频的后模拟增益控制音频信号级别。 此指标的单位为 dBmo。 为获得可接受的质量, 它至少应为 30 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |被呼叫方收到的音频的音频信号级别。 此指标的单位为 dBmo。 为获得可接受的质量, 它至少应为 30 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |对被呼叫者发送的音频进行模拟提升控制音频噪音级别。 此指标的单位为 dBmo。 为获得可接受的质量, 它应小于 35 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |被呼叫方接收的音频的模拟后增益控制音频噪音级别。 此指标的单位为 dBmo。 为获得可接受的质量, 它应小于 35 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |被调用方的回音返回损失增强。 此指标的单位为 dB。 较低的值表示较少的回声。 A/V 会议服务器或 IP 电话不报告此指标。  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |被调用方的扬声器呈现每五分钟的平均故障。 为了获得良好的质量, 这应该小于每五分钟一次。 不由 A/V 式会议服务器、中介服务器或 IP 电话报告。  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |被呼叫者的麦克风捕获每五分钟的平均故障。 为了获得良好的质量, 这应该小于每五分钟一次。 不由 A/V 式会议服务器、中介服务器或 IP 电话报告。  <br/> |
|CalleeTimestampDriftRateMic  <br/> |十进制 (9, 2)  <br/> |被呼叫者的麦克风设备时钟偏移速率, 相对于 CPU 时钟。  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |十进制 (9, 2)  <br/> |被呼叫者的扬声器设备时钟偏移速率, 相对于 CPU 时钟。  <br/> |
|CalleeTimestampErrorMicMs  <br/> |十进制 (9, 2)  <br/> |在呼叫的最后20秒内, 麦克风捕获流时间戳的平均时间戳错误 (以毫秒为单位)。  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |十进制 (9, 2)  <br/> |在呼叫的最后20秒内, 被调用方的扬声器的平均呈现流时间戳错误 (以毫秒为单位)。  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |语音开关是一种具有更低中断能力的半双工模式。 有关详细信息, 请参阅[MediaLine 表](medialine-0.md)。 <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |被调用方的 echo 事件的原因。 有关详细信息, 请参阅[MediaLine 表](medialine-0.md)。 <br/> |
|CalleeEchoPercentMicIn  <br/> |十进制 (5, 2)  <br/> |在被呼叫者的麦克风捕获流中检测到回显的时间百分比。 如果使用耳机, 则该值应较低。  <br/> |
|CalleeEchoPercentSend  <br/> |十进制 (5, 2)  <br/> |在被调用方的发送流中检测到回显的时间的百分比。 发送流中的高回显百分比表示回声泄漏。  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |在中介服务器上从被呼叫方的音频的网关接收的信号级别;这仅适用于中介服务器。 此指标的单位为 dBoV。 为了获得良好的质量, 可接受的范围应为 [-30 至-18] dBoV。  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |在中介服务器上从被呼叫方的音频的网关接收的信号级别。 这仅适用于中介服务器。 此指标的单位为 dBoV。 为了获得优质, 可接受范围应小于-50 dBoV。  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |在中介服务器端应用于被呼叫方的音频的自动增益控制 (AGC)。  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |float  <br/> |到达呼叫的前30秒内被呼叫方的传入信号的根平均值方块 (RMS)。  <br/> |
|RatioConcealedSamplesAvg  <br/> |十进制 (5, 2)  <br/> |通过音频康复为典型示例生成的隐藏样本的平均比率。  <br/> |
|RatioStretchedSamplesAvg  <br/> |十进制 (5, 2)  <br/> |通过音频康复为典型示例生成的拉伸样本的平均比率。  <br/> |
|RatioCompressedSamplesAvg  <br/> |十进制 (5, 2)  <br/> |从音频修复到典型示例生成的压缩样本的平均比率。  <br/> |
|RoundTrip  <br/> |int  <br/> |从 RTCP 统计数据往返的时间。  <br/> |
|RoundTripMax  <br/> |int  <br/> |音频流的最大往返行程时间。  <br/> |
|OverallAvgNetworkMOS  <br/> |十进制 (3, 2)  <br/> |通话的平均宽带网络 MOS。 此指标取决于所使用的数据包丢失、抖动和编解码器。 范围为1.0 到5.0。  <br/> |
|OverallMinNetworkMOS  <br/> |十进制 (3, 2)  <br/> |通话最少宽带网络 MOS。  <br/> |
|SendListenMOS  <br/> |十进制 (3, 2)  <br/> |平均预测宽带为已发送音频的 MOS 分数, 包括语音级别、噪声级别和捕获设备特征。  <br/> |
|SendListenMOSMin  <br/> |十进制 (3, 2)  <br/> |通话的最低 SendListenMOS。  <br/> |
|RecvListenMOS  <br/> |十进制 (3, 2)  <br/> |平均预测宽带从网络接收的音频的 MOS 分数, 包括语音级别、噪音级别、编解码器、网络条件和捕获设备特征。  <br/> |
|RecvListenMOSMin  <br/> |十进制 (3, 2)  <br/> |通话的最低 RecvListenMOS。  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |指示是否已将音频 FEC 用于呼叫。  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |指示 p 声明的标识信息的方向;1表示流方向从调用方到被调用方;0表示流方向来自被调用方的调用方。  <br/> |
   

