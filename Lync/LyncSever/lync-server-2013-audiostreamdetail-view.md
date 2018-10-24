---
title: AudioStreamDetail 视图
TOCTitle: AudioStreamDetail 视图
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49888575
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# AudioStreamDetail 视图

 

_**上一次修改主题：** 2015-03-09_

AudioStreamDetail 视图会存储有关数据库中每个音频流的信息。此视图是在 Microsoft Lync Server 2013 中引入的。


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>列</th>
<th>数据类型</th>
<th>详细信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SessionTime</p></td>
<td><p>datetime</p></td>
<td><p>引用自 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>引用自 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>媒体行中的唯一 ID。</p></td>
</tr>
<tr class="even">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>会话的开始时间。</p></td>
</tr>
<tr class="odd">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>会话的结束时间。</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>bit</p></td>
<td><p>对话类别：0 是 Lync Server 到中介服务器线路；1 是中介服务器到 PSTN 网关线路。</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>bit</p></td>
<td><p>指示是否绕过了呼叫的标记。</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>如果存在，则指示即使绕过 ID 相匹配也没有绕过呼叫的原因。仅定义一个值：</p>
<p>0x0001 – 默认网络适配器的未知绕过 ID。</p></td>
</tr>
<tr class="odd">
<td><p>CallPriority</p></td>
<td><p>int</p></td>
<td><p>呼叫的优先级。</p></td>
</tr>
<tr class="even">
<td><p>CallerPool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>呼叫者池 FQDN。</p></td>
</tr>
<tr class="odd">
<td><p>CalleePool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>被叫方池 FQDN。</p></td>
</tr>
<tr class="even">
<td><p>Caller</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>呼叫者的 URI。</p></td>
</tr>
<tr class="odd">
<td><p>Callee</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>被叫方的 URI。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>呼叫者的用户代理字符串。</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>呼叫者的用户代理类型。有关详细信息，请参阅 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar(64)</p></td>
<td><p>呼叫者的用户代理类别。有关详细信息，请参阅 <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef 表 (QoE)</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>被叫方的用户代理字符串。</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>被叫方的用户代理类型。有关信息，请参阅 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar(64)</p></td>
<td><p>被叫方的用户代理类别。有关信息，请参阅 <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef 表 (QoE)</a>。</p></td>
</tr>
<tr class="even">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>呼叫者的终结点名称。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>被叫方的终结点名称。</p></td>
</tr>
<tr class="even">
<td><p>CallerOS</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>呼叫者终结点的操作系统 (OS)。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeOS</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>被叫方终结点的操作系统 (OS)。</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUName</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>呼叫者终结点的 CPU 名称。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUName</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>被叫方终结点的 CPU 名称。</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>呼叫者终结点中的 CPU 核心数目。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>被叫方终结点中的 CPU 核心数目。</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>呼叫者终结点的 CPU 处理器速度。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>被叫方终结点的 CPU 处理器速度。</p></td>
</tr>
<tr class="even">
<td><p>CallerVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>指示呼叫者的系统是否正在虚拟化环境中运行。有关详细信息，请参阅 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的 Endpoint 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>指示被叫方的系统是否正在虚拟化环境中运行。有关详细信息，请参阅 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的 Endpoint 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CorrelationKey</p></td>
<td><p></p></td>
<td><p>相关密钥。引用自 <a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 中的 SessionCorrelation 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>有关媒体路径的信息，例如直接或中继。有关详细信息，请参阅 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>有关呼叫者的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“体验质量监控服务器协议规范”。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>有关被叫方的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“体验质量监控服务器协议规范”。</p></td>
</tr>
<tr class="even">
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>传输类型：0 是 UDP，1 是 TCP。</p></td>
</tr>
<tr class="odd">
<td><p>CallerIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>呼叫者的 IP 地址。这可能是 IPv4 或 IPv6 地址。</p></td>
</tr>
<tr class="even">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>呼叫者所使用的端口。</p></td>
</tr>
<tr class="odd">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>指示呼叫者是否位于间隔网络内部：1 表示呼叫者位于企业网络内部，0 表示呼叫者位于网络外部。</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>被叫方的 IP 地址。这可能是 IPv4 或 IPv6 地址。</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>被叫方所使用的端口。</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>指示被叫方是否位于间隔网络内部：1 表示被叫方位于企业网络内部，0 表示被叫方位于网络外部。</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserSite</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>呼叫者的站点名称。</p></td>
</tr>
<tr class="even">
<td><p>CallerRegion</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>呼叫者站点的国家/地区名称。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserSite</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>被叫方的站点名称。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>被叫方站点的国家/地区名称。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>呼叫者所使用的 A/V 边缘服务的 IP 地址。有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>呼叫者所使用的 A/V 边缘服务上使用的端口。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>被叫方所使用的 A/V 边缘服务的 IP 地址密钥。有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>被叫方所使用的 A/V 边缘服务上使用的端口。</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>呼叫者的捕获设备名称。</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>呼叫者的呈现设备名称。</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>呼叫者的捕获设备驱动程序名称。</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>呼叫者的呈现设备驱动程序名称。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>被叫方的捕获设备名称。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>被叫方的呈现设备名称。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>被叫方的捕获设备驱动程序名称。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>被叫方的呈现设备驱动程序名称。</p></td>
</tr>
<tr class="odd">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>呼叫者的网络连接类型：0 是有线，1 是无线。</p></td>
</tr>
<tr class="even">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>指示呼叫者是否通过虚拟专用网络连接：1 是虚拟专用网络 (VPN)，0 是非 VPN。</p></td>
</tr>
<tr class="odd">
<td><p>CallerLinkSpeed</p></td>
<td><p>decimal(18,0)</p></td>
<td><p>呼叫者终结点的网络链接速度（以 bps 为单位）。</p></td>
</tr>
<tr class="even">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>被叫方的网络连接类型：0 是有线，1 是无线。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>指示被叫方是否通过虚拟专用网络连接：1 是虚拟专用网络 (VPN)，0 是非 VPN。</p></td>
</tr>
<tr class="even">
<td><p>CalleeLinkSpeed</p></td>
<td><p>decimal(18,0)</p></td>
<td><p>被叫方终结点的网络链接速度（以 bps 为单位）。</p></td>
</tr>
<tr class="odd">
<td><p>ConversationalMOS</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>音频会话的窄带交谈 MOS（基于两个音频流）。</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>应用于指定发送端流指定的多种策略设置（TURN、API、SDP、策略服务器等）的实际带宽。不要将其与有效带宽混淆，因为根据带宽预估的不同，有效带宽可能会减少。这基本上是发送流可禁止带宽预估设定的限制的最大带宽</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>实时控制协议 (RTCP) 统计信息中的平均网络抖动。</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>呼叫期间的最大网络抖动。</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRate</p></td>
<td><p>decimal(5,4)</p></td>
<td><p>呼叫期间的平均数据包丢失率。</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRateMax</p></td>
<td><p>decimal(5,4)</p></td>
<td><p>呼叫期间观测到的数据包丢失最大值。</p></td>
</tr>
<tr class="odd">
<td><p>BurstDensity</p></td>
<td><p>decimal(9,4)</p></td>
<td><p>呼叫过程中出现间歇丢失期间数据包丢失的平均密度。</p></td>
</tr>
<tr class="even">
<td><p>BurstDuration</p></td>
<td><p>int</p></td>
<td><p>呼叫过程中出现间歇丢失期间数据包丢失的平均持续时间。</p></td>
</tr>
<tr class="odd">
<td><p>BurstGapDensity</p></td>
<td><p>decimal(9,4)</p></td>
<td><p>间歇的数据包丢失之间出现间隙期间数据包丢失的平均密度。</p></td>
</tr>
<tr class="even">
<td><p>BurstGapDuration</p></td>
<td><p>int</p></td>
<td><p>间歇的数据包丢失之间出现间隙的平均持续时间。</p></td>
</tr>
<tr class="odd">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>音频流的数据包计数。</p></td>
</tr>
<tr class="even">
<td><p>BandwidthEst</p></td>
<td><p>int</p></td>
<td><p>音频流的带宽预估。</p></td>
</tr>
<tr class="odd">
<td><p>DegradationAvg</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>全部呼叫的网络 MOS 性能降低。范围是 0.0 到 5.0。此指标显示因抖动和数据包丢失而降低的网络 MOS 值。为获得可接受的质量，它应小于 0.5。</p></td>
</tr>
<tr class="even">
<td><p>DegradationMax</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>呼叫期间的最大网络 MOS 性能降低。</p></td>
</tr>
<tr class="odd">
<td><p>DegradationJitterAvg</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>抖动导致的网络 MOS 性能降低。</p></td>
</tr>
<tr class="even">
<td><p>DegradationPacketLossAvg</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>数据包丢失导致的网络 MOS 性能降低。</p></td>
</tr>
<tr class="odd">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>用于呼叫的音频编解码器，引用自 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中的 PayloadDescription 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>AudioSampleRate</p></td>
<td><p>int</p></td>
<td><p>音频流的采样率。</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>呼叫者发送的音频的“模拟后增益控制”音频信号电平。该指标的单位为 dBmo。为获得可接受的质量，该值至少应为 30 dBmo。A/V 会议服务器或 IP 电话不会报告该指标。</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>呼叫者收到的音频的音频信号电平。该指标的单位为 dBmo。为获得可接受的质量，该值至少应为 30 dBmo。A/V 会议服务器或 IP 电话不会报告该指标。</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>呼叫者发送的音频的“模拟后增益控制”音频噪声电平。该指标的单位为 dBmo。为获得可接受的质量，该值应小于 35 dBmo。A/V 会议服务器或 IP 电话不会报告该指标。</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>呼叫者收到的音频的“模拟后增益控制”音频噪声电平。该指标的单位为 dBmo。为获得可接受的质量，该值应小于 35 dBmo。A/V 会议服务器或 IP 电话不会报告该指标。</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoReturn</p></td>
<td><p>int</p></td>
<td><p>呼叫者的“回声往返损耗增强”。该指标的单位为 dB。数值越小，代表回声越小。A/V 会议服务器或 IP 电话不会报告该指标。</p></td>
</tr>
<tr class="even">
<td><p>CallerSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>呼叫者的扬声器呈现音频时每五分钟出现的平均故障次数。为获得良好的质量，该值应低于每五分钟一次。A/V 会议服务器、中介服务器或 IP 电话不会报告该值。</p></td>
</tr>
<tr class="odd">
<td><p>CallerMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>呼叫者麦克风捕获音频时每五分钟出现的平均故障次数。为获得良好的质量，该值应低于每五分钟一次。A/V 会议服务器、中介服务器或 IP 电话不会报告该值。</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampDriftRateMic</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>呼叫者的麦克风设备时钟相对于 CPU 时钟的偏移率。</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampDriftRateSpk</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>呼叫者的扬声器设备时钟相对于 CPU 时钟的偏移率。</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampErrorMicMs</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>在呼叫的最后 20 秒内，麦克风捕获流量的平均时间戳错误（以毫秒计）。</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampErrorSpkMs</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>在呼叫的最后 20 秒内，呼叫者的麦克风呈现流量的平均时间戳错误（以毫秒计）。</p></td>
</tr>
<tr class="even">
<td><p>CallerVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>语音切换采用具有减少中断功能的半双工模式。有关详细信息，请参阅 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>呼叫者的回声事件的原因。有关详细信息，请参阅 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CallerEchoPercentMicIn</p></td>
<td><p>decimal(5,2)</p></td>
<td><p>在呼叫者的麦克风捕获流量中检测回声时的时间百分比。如果使用耳机，则该值应该较小。</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoPercentSend</p></td>
<td><p>decimal(5,2)</p></td>
<td><p>在呼叫者的发送流量中检测回声时的时间百分比。如果发送流量中的回声百分比值较高，则表明回声泄漏。</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>在中介服务器上收到的来自呼叫者音频网关的信号电平；该值仅适用于中介服务器。该指标的单位为 dBoV。为获得良好的质量，可接受的范围应为 -30 至 -18 dBoV。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>在中介服务器上收到的来自呼叫者音频网关的信号电平。该值仅适用于中介服务器。该指标的单位为 dBoV。为获得良好的质量，可接受的范围应小于 -50 dBoV。</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>应用到呼叫者音频的中介服务器方的自动增益控制 (AGC)。</p></td>
</tr>
<tr class="odd">
<td><p>CallerInitialSignalLevelRMS</p></td>
<td><p>float</p></td>
<td><p>呼叫（最多）前 30 秒钟至呼叫者的传入信号的均方根 (RMS)。</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>代表被叫方发送的音频的“模拟后增益控制”音频信号电平。该指标的单位为 dBmo。为获得可接受的质量，该值至少应为 30 dBmo。A/V 会议服务器或 IP 电话不会报告该指标。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>被叫方收到的音频的音频信号电平。该指标的单位为 dBmo。为获得可接受的质量，该值至少应为 30 dBmo。A/V 会议服务器或 IP 电话不会报告该指标。</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>被叫方发送的音频的“模拟后增益控制”音频噪声电平。该指标的单位为 dBmo。为获得可接受的质量，该值应低于 35 dBmo。A/V 会议服务器或 IP 电话不会报告该指标。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>被叫方收到的音频的“模拟后增益控制”音频噪声电平。该指标的单位为 dBmo。为获得可接受的质量，该值应低于 35 dBmo。A/V 会议服务器或 IP 电话不会报告该指标。</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoReturn</p></td>
<td><p>int</p></td>
<td><p>被叫方的“回声往返损耗增强”。该指标的单位为 dB。数值越小，代表回声越小。A/V 会议服务器或 IP 电话不会报告该指标。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>被叫方的扬声器呈现音频时每五分钟出现的平均故障次数。为获得良好的质量，该值应低于每五分钟一次。A/V 会议服务器、中介服务器或 IP 电话不会报告该值。</p></td>
</tr>
<tr class="even">
<td><p>CalleeMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>被叫方的麦克风捕获音频时每五分钟出现的平均故障次数。为获得良好的质量，该值应低于每五分钟一次。A/V 会议服务器、中介服务器或 IP 电话不会报告该值。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampDriftRateMic</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>被叫方的麦克风设备时钟相对于 CPU 时钟的偏移率。</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampDriftRateSpk</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>被叫方的扬声器设备时钟相对于 CPU 时钟的偏移率。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampErrorMicMs</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>在呼叫的最后 20 秒内，麦克风捕获流量的平均时间戳错误（以毫秒计）。</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampErrorSpkMs</p></td>
<td><p>decimal(9,2)</p></td>
<td><p>在呼叫的最后 20 秒内，被叫方的扬声器呈现流量的平均时间戳错误（以毫秒计）。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>语音切换采用具有减少中断功能的半双工模式。有关详细信息，请参阅 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>被叫方的回声事件的原因。有关详细信息，请参阅 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEchoPercentMicIn</p></td>
<td><p>decimal(5,2)</p></td>
<td><p>在被叫方的麦克风捕获流量中检测回声时的时间百分比。如果使用耳机，则该值应该较小。</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoPercentSend</p></td>
<td><p>decimal(5,2)</p></td>
<td><p>在被叫方发送流量中检测回声时的时间百分比。如果发送流量中的回声百分比值较高，则表明回声泄漏。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>在中介服务器上收到的来自被叫方音频网关的信号电平；该值仅适用于中介服务器。该指标的单位为 dBoV。为获得良好的质量，可接受的范围应为 [-30 至 -18] dBoV。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>在中介服务器上收到的来自被叫方音频网关的信号电平。该值仅适用于中介服务器。该指标的单位为 dBoV。为获得良好的质量，可接受的范围应小于 -50 dBoV。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>应用到被叫方音频的中介服务器方的自动增益控制 (AGC)。</p></td>
</tr>
<tr class="even">
<td><p>CalleeInitialSignalLevelRMS</p></td>
<td><p>float</p></td>
<td><p>呼叫（最多）前 30 秒钟至被叫方的传入信号的均方根 (RMS)。</p></td>
</tr>
<tr class="odd">
<td><p>RatioConcealedSamplesAvg</p></td>
<td><p>decimal(5,2)</p></td>
<td><p>典型样本数的音频修复生成的隐藏样本数的平均比率。</p></td>
</tr>
<tr class="even">
<td><p>RatioStretchedSamplesAvg</p></td>
<td><p>decimal(5,2)</p></td>
<td><p>典型样本数的音频修复生成的拉伸样本数的平均比率。</p></td>
</tr>
<tr class="odd">
<td><p>RatioCompressedSamplesAvg</p></td>
<td><p>decimal(5,2)</p></td>
<td><p>典型样本数的音频修复生成的压缩样本数的平均比率。</p></td>
</tr>
<tr class="even">
<td><p>RoundTrip</p></td>
<td><p>int</p></td>
<td><p>RTCP 统计信息中的来回行程时间。</p></td>
</tr>
<tr class="odd">
<td><p>RoundTripMax</p></td>
<td><p>int</p></td>
<td><p>音频流的最大来回行程时间。</p></td>
</tr>
<tr class="even">
<td><p>OverallAvgNetworkMOS</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>呼叫的平均宽带网络 MOS。此指标取决于数据包丢失、抖动和使用的编解码器。范围是 1.0 到 5.0。</p></td>
</tr>
<tr class="odd">
<td><p>OverallMinNetworkMOS</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>呼叫的最小宽带网络 MOS。</p></td>
</tr>
<tr class="even">
<td><p>SendListenMOS</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>已发送音频的平均预测宽带倾听 MOS 得分，包括语音级别、噪音级别和捕获设备特征。</p></td>
</tr>
<tr class="odd">
<td><p>SendListenMOSMin</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>呼叫的最小 SendListenMOS。</p></td>
</tr>
<tr class="even">
<td><p>RecvListenMOS</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>音频从网络接收的平均预测宽带倾听 MOS 得分，包括语音级别、噪音级别、编解码器、网络条件和捕获设备特征。</p></td>
</tr>
<tr class="odd">
<td><p>RecvListenMOSMin</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>呼叫的最小 RecvListenMOS。</p></td>
</tr>
<tr class="even">
<td><p>AudioFECUsed</p></td>
<td><p>bit</p></td>
<td><p>指示音频 FEC 是否已用于呼叫。</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>bit</p></td>
<td><p>指示 p 已断言标识信息的方向；1 表示流方向从呼叫者到被叫方；0 表示流方向从被叫方到呼叫者。</p></td>
</tr>
</tbody>
</table>

