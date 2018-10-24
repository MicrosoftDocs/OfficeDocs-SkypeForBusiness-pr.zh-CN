---
title: VideoStreamDetail 视图
TOCTitle: VideoStreamDetail 视图
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49888672
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# VideoStreamDetail 视图

 

_**上一次修改主题：** 2015-03-09_

VideoStreamDetail 视图存储有关每个数据库中视频流的信息。此视图在 Microsoft Lync Server 2013 中引入。


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
<th>说明</th>
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
<td><p>MediaLineLabel</p></td>
<td><p>tinyint</p></td>
<td><p>引用自 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>媒体行中的唯一 ID。</p></td>
</tr>
<tr class="odd">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>会话的开始时间。</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>会话的结束时间。</p></td>
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
<td><p>呼叫者</p></td>
<td><p>nvarchar(450)</p></td>
<td><p>呼叫者的 URI。</p></td>
</tr>
<tr class="odd">
<td><p>被叫方</p></td>
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
<td><p>呼叫者的用户代理类型。有关详细信息，请参阅<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar(64)</p></td>
<td><p>呼叫者的用户代理类别。有关详细信息，请参阅<a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef 表 (QoE)</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>被叫方的用户代理字符串。</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>被叫方的用户代理类型。有关信息，请参阅<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar(64)</p></td>
<td><p>被叫方的用户代理类别。有关信息，请参阅<a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef 表 (QoE)</a>。</p></td>
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
<td><p>呼叫者的终结点的 CPU 内核数。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>被叫方的终结点的 CPU 内核数。</p></td>
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
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>有关媒体路径的信息，例如直接或中继。有关详细信息，请参阅 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>关于呼叫者的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“用户体验质量监控服务器协议规范”。</p></td>
</tr>
<tr class="even">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>关于被叫方的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“用户体验质量监控服务器协议规范”。</p></td>
</tr>
<tr class="odd">
<td><p>传输</p></td>
<td><p>int</p></td>
<td><p>传输类型：0 是 UDP，1 是 TCP。</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>呼叫者的 IP 地址。这可能是 IPv4 或 IPv6 地址。</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>呼叫者使用的端口。</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>指示呼叫者是否位于组织网络的内部。1 表示呼叫者位于企业网络内部，0 表示呼叫者位于该网络外部。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>被叫方的 IP 地址。这可能是 IPv4 或 IPv6 地址。</p></td>
</tr>
<tr class="even">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>被叫方所使用的端口。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>指示呼叫者是否位于组织网络的内部。1 表示被叫方位于企业网络内部，0 表示被叫方位于该网络外部。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserSite</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>呼叫者的站点名称。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRegion</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>呼叫者站点的国家/地区名称。</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserSite</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>被叫方的站点名称。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar(128)</p></td>
<td><p>被叫方站点的国家/地区名称。</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>呼叫者所使用的 A/V 边缘服务的 IP 地址。有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>呼叫者使用的 A/V 边缘服务上的端口。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var(50)</p>
<p></p></td>
<td><p>被叫方所使用的 A/V 边缘服务的 IP 地址密钥。有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>被叫方使用的 A/V 边缘服务上的端口。</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>呼叫者的捕获设备名称。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>呼叫者的呈现设备名称。</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>呼叫者的捕获设备驱动程序名称。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>呼叫者的呈现设备驱动程序名称。</p></td>
</tr>
<tr class="even">
<td><p>CalleeCaptureDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>被叫方的捕获设备名称。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar(256)</p></td>
<td><p>被叫方的呈现设备名称。</p></td>
</tr>
<tr class="even">
<td><p>CalleCaptureDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>被叫方的捕获设备驱动程序名称。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>被叫方的呈现设备驱动程序名称。</p></td>
</tr>
<tr class="even">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>呼叫者的网络连接类型：0 是有线，1 是无线。</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>指示呼叫者是否通过虚拟专用网络连接：1 是虚拟专用网络 (VPN)，0 是非 VPN。</p></td>
</tr>
<tr class="even">
<td><p>CallerLinkSpeed</p></td>
<td><p>decimal(18,)</p></td>
<td><p>呼叫者终结点的网络链接速度（以 bps 为单位）。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>被叫方的网络连接类型：0 是有线，1 是无线。</p></td>
</tr>
<tr class="even">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>指示被叫方是否通过虚拟专用网络连接：1 是虚拟专用网络 (VPN)，0 是非 VPN。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeLinkSpeed</p></td>
<td><p>decimal(18,0)</p></td>
<td><p>被叫方终结点的网络链接速度（以 bps 为单位）。</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>decimal(3,2)</p></td>
<td><p>音频会话的窄带交谈 MOS（基于两个音频流）。</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>应用于指定发送端流指定的多种策略设置（TURN、API、SDP、策略服务器等）的实际带宽。不要将其与有效带宽混淆，因为根据带宽预估的不同，可能会降低带宽的有效性。这基本上是发送流可禁止带宽预估设定的限制的最大带宽。</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>实时控制协议 (RTCP) 统计信息中的平均网络抖动。</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>呼叫期间的最大网络抖动。</p></td>
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
<td><p>PacketLossRate</p></td>
<td><p>decimal(5,4)</p></td>
<td><p>呼叫期间的平均数据包丢失率。</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRateMax</p></td>
<td><p>decimal(5,4)</p></td>
<td><p>呼叫期间观测到的数据包丢失最大值。</p></td>
</tr>
<tr class="even">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>视频流的数据包计数（实时传输协议，RTP）。</p></td>
</tr>
<tr class="odd">
<td><p>BandwidthEst</p></td>
<td><p>int</p></td>
<td><p>音频流的带宽预估。</p></td>
</tr>
<tr class="even">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>用于呼叫的音频编解码器，引用自 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中的 PayloadDescription 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>VideoResolution</p></td>
<td><p>char(9)</p></td>
<td><p>视频的分辨率（像素宽乘以像素高）。报告为字符串。</p></td>
</tr>
<tr class="even">
<td><p>VideoBitRateAvg</p></td>
<td><p>int</p></td>
<td><p>视频流的平均比特率。</p></td>
</tr>
<tr class="odd">
<td><p>InboundVideoFrameRateAvg</p></td>
<td><p>decimal(9,4)</p></td>
<td><p>接收的视频帧速率。</p></td>
</tr>
<tr class="even">
<td><p>OutboundVideoFrameRateAvg</p></td>
<td><p>decimal(9,4)</p></td>
<td><p>发送的视频帧速率。</p></td>
</tr>
<tr class="odd">
<td><p>ViideoBitRateMax</p></td>
<td><p>int</p></td>
<td><p>视频会话期间的最大视频比特率。</p></td>
</tr>
<tr class="even">
<td><p>VideoPacketLossRate</p></td>
<td><p>decimal(9,4)</p></td>
<td><p>视频数据包丢失的比特率。</p></td>
</tr>
<tr class="odd">
<td><p>VideoFrameLossRate</p></td>
<td><p>decimal(9.4)</p></td>
<td><p>丢失的全部视频帧的百分比。</p></td>
</tr>
<tr class="even">
<td><p>VideoFEC</p></td>
<td><p>bit</p></td>
<td><p>未使用。</p></td>
</tr>
<tr class="odd">
<td><p>VideoAllocateBWAvg</p></td>
<td><p>int</p></td>
<td><p>为视频分配的平均带宽量。</p></td>
</tr>
<tr class="even">
<td><p>VideoLocalFrameLossPercentageAvg</p></td>
<td><p>decimal(9.4)</p></td>
<td><p>丢失的全部视频帧的百分比。</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>bit</p></td>
<td><p>已断言标识信息的流方向。1 表示流方向从呼叫者到被叫方；0 表示流方向从被叫方到呼叫者。</p></td>
</tr>
</tbody>
</table>

