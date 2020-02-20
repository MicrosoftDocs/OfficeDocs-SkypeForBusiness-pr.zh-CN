---
title: Lync Server 2013： AudioStreamDetail 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b69cdbbe7a4635e60e5912e6f41d2f089612b30a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145481"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a>Lync Server 2013 中的 AudioStreamDetail 视图

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-03_

AudioStreamDetail 视图存储有关数据库中每个音频流的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。


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
<td><p><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</p></td>
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
<td><p>位</p></td>
<td><p>对话框类别：0是用于中介服务器腿的 Lync 服务器;1是中介服务器到 PSTN 网关腿。</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>位</p></td>
<td><p>指示是否绕过呼叫的标志。</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>如果存在，则指示即使绕过 Id 匹配也不会绕过呼叫。 仅定义了一个值：</p>
<p>0x0001 –默认网络适配器的绕过旁路 ID。</p></td>
</tr>
<tr class="odd">
<td><p>CallPriority</p></td>
<td><p>int</p></td>
<td><p>呼叫的优先级。</p></td>
</tr>
<tr class="even">
<td><p>CallerPool</p></td>
<td><p>nvarchar （256）</p></td>
<td><p>呼叫者池 FQDN。</p></td>
</tr>
<tr class="odd">
<td><p>CalleePool</p></td>
<td><p>nvarchar （256）</p></td>
<td><p>被叫方池 FQDN。</p></td>
</tr>
<tr class="even">
<td><p>Caller</p></td>
<td><p>nvarchar （450）</p></td>
<td><p>呼叫者的 URI。</p></td>
</tr>
<tr class="odd">
<td><p>约定</p></td>
<td><p>nvarchar （450）</p></td>
<td><p>被叫方的 URI。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar （256）</p></td>
<td><p>呼叫者的用户代理字符串。</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>呼叫者的用户代理的类型。 有关详细信息，请参阅<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar （64）</p></td>
<td><p>呼叫者的用户代理的类别。 有关详细信息，请参阅<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表（QoE）</a> 。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar （256）</p></td>
<td><p>被叫方的用户代理字符串。</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>被叫方的用户代理类型。 有关信息，请参阅<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar （64）</p></td>
<td><p>被叫方的用户代理类别。 有关信息，请参阅<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表（QoE）</a> 。</p></td>
</tr>
<tr class="even">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar （256）</p></td>
<td><p>呼叫者的终结点名称。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar （256）</p></td>
<td><p>被叫方的终结点名称。</p></td>
</tr>
<tr class="even">
<td><p>CallerOS</p></td>
<td><p>nvarchar</p></td>
<td><p>呼叫者终结点的操作系统 (OS)。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeOS</p></td>
<td><p>nvarchar</p></td>
<td><p>被叫方终结点的操作系统 (OS)。</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUName</p></td>
<td><p>nvarchar</p></td>
<td><p>呼叫者终结点的 CPU 名称。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUName</p></td>
<td><p>nvarchar</p></td>
<td><p>被叫方终结点的 CPU 名称。</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>呼叫者终结点中的 CPU 内核数。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>被叫方的终结点中的 CPU 内核数。</p></td>
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
<td><p>指示呼叫者的系统是否正在虚拟化环境中运行。 有关详细信息，请参阅<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的终结点表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>指示被叫方的系统是否正在虚拟化环境中运行。 有关详细信息，请参阅<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的终结点表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CorrelationKey</p></td>
<td></td>
<td><p>相关密钥。 <a href="lync-server-2013-sessioncorrelation-table.md">在 Lync Server 2013 中从 SessionCorrelation 表中</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>有关媒体路径的信息，例如 direct 或中继。 有关详细信息，请参阅<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>关于呼叫者的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“用户体验质量监控服务器协议规范”。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>关于被叫方的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“用户体验质量监控服务器协议规范”。</p></td>
</tr>
<tr class="even">
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>传输类型：0 是 UDP，1 是 TCP。</p></td>
</tr>
<tr class="odd">
<td><p>CallerIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>呼叫者的 IP 地址。 这可能是 IPv4 地址或 IPv6 地址。</p></td>
</tr>
<tr class="even">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>呼叫者使用的端口。</p></td>
</tr>
<tr class="odd">
<td><p>CallerInside</p></td>
<td><p>位</p></td>
<td><p>指示呼叫者是否在间隔网络内：1表示呼叫者位于企业网络内，0表示呼叫者在网络外部。</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>被叫方的 IP 地址。 这可能是 IPv4 或 IPv6 地址。</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>被叫方所使用的端口。</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>位</p></td>
<td><p>指示被叫方是否位于间隔网络内：1表示被呼叫者位于企业网络内，0表示被呼叫方位于网络外部。</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserSite</p></td>
<td><p>nvarchar</p></td>
<td><p>呼叫者的站点名称。</p></td>
</tr>
<tr class="even">
<td><p>CallerRegion</p></td>
<td><p>nvarchar</p></td>
<td><p>呼叫者站点的国家/地区名称。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserSite</p></td>
<td><p>nvarchar</p></td>
<td><p>被叫方的站点名称。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar</p></td>
<td><p>被叫方站点的国家/地区名称。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>呼叫者所使用的 A/V 边缘服务的 IP 地址。 有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>呼叫者在 A/V 边缘服务中使用的端口。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>被叫方所使用的 A/V 边缘服务的 IP 地址密钥。 有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>被叫方在 A/V 边缘服务中使用的端口。</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar （256）</p></td>
<td><p>呼叫者的捕获设备名称。</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>varchar （256）</p></td>
<td><p>呼叫者的呈现设备名称。</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar （256）</p></td>
<td><p>呼叫者的捕获设备驱动程序名称。</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDriver</p></td>
<td><p>varchar （256）</p></td>
<td><p>呼叫者的呈现设备驱动程序名称。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>varchar （256）</p></td>
<td><p>被叫方的捕获设备名称。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar （256）</p></td>
<td><p>被叫方的呈现设备名称。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>varchar （256）</p></td>
<td><p>被叫方的捕获设备驱动程序名称。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar （256）</p></td>
<td><p>被叫方的呈现设备驱动程序名称。</p></td>
</tr>
<tr class="odd">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>呼叫者的网络连接类型：0 是有线，1 是无线。</p></td>
</tr>
<tr class="even">
<td><p>CallerVPN</p></td>
<td><p>位</p></td>
<td><p>指示呼叫者是否通过虚拟专用网络连接：1是虚拟专用网络（VPN），0是非 VPN。</p></td>
</tr>
<tr class="odd">
<td><p>CallerLinkSpeed</p></td>
<td><p>小数（18，0）</p></td>
<td><p>呼叫者终结点的网络链接速度（以 bps 为单位）。</p></td>
</tr>
<tr class="even">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>被叫方的网络连接类型：0 是有线，1 是无线。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>位</p></td>
<td><p>指示呼叫者是否通过虚拟专用网络连接：1是虚拟专用网络（VPN），0是非 VPN。</p></td>
</tr>
<tr class="even">
<td><p>CalleeLinkSpeed</p></td>
<td><p>小数（18，0）</p></td>
<td><p>被呼叫方的终结点的网络链接速度（以 bps 为单位）。</p></td>
</tr>
<tr class="odd">
<td><p>ConversationalMOS</p></td>
<td><p>decimal （3，2）</p></td>
<td><p>音频会话的窄带交谈 MOS（基于两个音频流）。</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>应用于指定发送端流指定的多种策略设置（TURN、API、SDP、策略服务器等）的实际带宽。 不要将其与有效带宽混淆，因为根据带宽预估的不同，可能会降低带宽的有效性。 这基本上是发送流可以采用带宽估计设定限制的限制的最大带宽</p></td>
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
<td><p>decimal （5，4）</p></td>
<td><p>呼叫期间的平均数据包丢失率。</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRateMax</p></td>
<td><p>decimal （5，4）</p></td>
<td><p>呼叫期间观测到的数据包丢失最大值。</p></td>
</tr>
<tr class="odd">
<td><p>BurstDensity</p></td>
<td><p>小数（9，4）</p></td>
<td><p>呼叫期间出现猝发损失期间的数据包丢失的平均密度。</p></td>
</tr>
<tr class="even">
<td><p>BurstDuration</p></td>
<td><p>int</p></td>
<td><p>呼叫期间出现猝发损失期间的数据包丢失的平均持续时间。</p></td>
</tr>
<tr class="odd">
<td><p>BurstGapDensity</p></td>
<td><p>小数（9，4）</p></td>
<td><p>在出现猝发数据包丢失之间间隔期间的数据包丢失的平均密度。</p></td>
</tr>
<tr class="even">
<td><p>BurstGapDuration</p></td>
<td><p>int</p></td>
<td><p>猝发数据包丢失间隔的平均持续时间。</p></td>
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
<td><p>decimal （3，2）</p></td>
<td><p>整个呼叫的网络 MOS 降级。 范围是0.0 到5.0。 此指标显示由于抖动和数据包丢失而导致网络 MOS 减少的量。 对于可接受的质量，它应小于0.5。</p></td>
</tr>
<tr class="even">
<td><p>DegradationMax</p></td>
<td><p>decimal （3，2）</p></td>
<td><p>呼叫期间的最大网络 MOS 降级。</p></td>
</tr>
<tr class="odd">
<td><p>DegradationJitterAvg</p></td>
<td><p>decimal （3，2）</p></td>
<td><p>由抖动引起的网络 MOS 性能下降。</p></td>
</tr>
<tr class="even">
<td><p>DegradationPacketLossAvg</p></td>
<td><p>decimal （3，2）</p></td>
<td><p>因数据包丢失而导致的网络 MOS 降级。</p></td>
</tr>
<tr class="odd">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>用于呼叫的音频编解码器，从<a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中的 PayloadDescription 表中</a>引用。</p></td>
</tr>
<tr class="even">
<td><p>AudioSampleRate</p></td>
<td><p>int</p></td>
<td><p>音频流的采样率。</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>呼叫者发送的音频的后模拟增益控制音频信号级别。 此指标的单位为 dBmo。 为获得可接受的质量，至少应为 30 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>呼叫者收到的音频的音频信号级别。 此指标的单位为 dBmo。 为获得可接受的质量，至少应为 30 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>模拟声后，呼叫者发送的音频的音频噪音水平。 此指标的单位为 dBmo。 为获得可接受的质量，它应小于 35 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>呼叫者接收的音频的后模拟增益控制音频噪音水平。 此指标的单位为 dBmo。 为获得可接受的质量，它应小于 35 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoReturn</p></td>
<td><p>int</p></td>
<td><p>呼叫者的回显返回丢失增强功能。 此指标的单位为 dB。 值越低表示回显越少。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="even">
<td><p>CallerSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>呼叫者的扬声器呈现每5分钟的平均故障。 为了获得较高的质量，这应小于每五分钟一次。 不是由 A/V 会议服务器、中介服务器或 IP 电话报告。</p></td>
</tr>
<tr class="odd">
<td><p>CallerMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>呼叫者的麦克风捕获每5分钟的平均故障。 若要获得较高的质量，这应小于每5分钟一次。 不是由 A/V 会议服务器、中介服务器或 IP 电话报告。</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampDriftRateMic</p></td>
<td><p>小数（9，2）</p></td>
<td><p>呼叫者的麦克风设备时钟相对于 CPU 时钟的速度偏移速率。</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampDriftRateSpk</p></td>
<td><p>小数（9，2）</p></td>
<td><p>呼叫者的扬声器设备时钟相对于 CPU 时钟的速度偏移速率。</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampErrorMicMs</p></td>
<td><p>小数（9，2）</p></td>
<td><p>呼叫的最后20秒内的麦克风捕获流的平均时间戳错误（以毫秒为单位）。</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampErrorSpkMs</p></td>
<td><p>小数（9，2）</p></td>
<td><p>呼叫者的扬声器在最近20秒内呈现流时间戳错误的平均次数（以毫秒为单位）。</p></td>
</tr>
<tr class="even">
<td><p>CallerVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>Voice switch 是一个半双工模式，具有更低的中断能力。 有关详细信息，请参阅<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>调用方的 echo 事件的原因。 有关详细信息，请参阅<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CallerEchoPercentMicIn</p></td>
<td><p>decimal （5，2）</p></td>
<td><p>在呼叫者的麦克风捕获流中检测到回显的时间的百分比。 如果使用的是耳机，则该值应较低。</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoPercentSend</p></td>
<td><p>decimal （5，2）</p></td>
<td><p>在呼叫者的发送流中检测到回显的时间的百分比。 发送流中的高回显百分比指示回声泄漏。</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>从呼叫者音频的网关接收中介服务器上的信号级别;这仅适用于中介服务器。 此指标的单位为 dBoV。 为了获得良好的质量，可接受范围应为-30 到-18 dBoV。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>从呼叫者音频的网关接收中介服务器上的信号级别。 这仅适用于中介服务器。 此指标的单位为 dBoV。 为了获得良好的质量，可接受的范围应小于-50 dBoV。</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>将中介服务器端上的自动增益控制（AGC）应用于呼叫者的音频。</p></td>
</tr>
<tr class="odd">
<td><p>CallerInitialSignalLevelRMS</p></td>
<td><p>点数</p></td>
<td><p>到呼叫者的传入信号的根均值（RMS），最长为呼叫的前30秒。</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>表示被呼叫者发送的音频的反电后增益控制音频信号级别。 此指标的单位为 dBmo。 为获得可接受的质量，至少应为 30 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>被呼叫者收到的音频的音频信号级别。 此指标的单位为 dBmo。 为获得可接受的质量，至少应为 30 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>对被呼叫者发送的音频进行模拟后增益控制音频噪音级别。 此指标的单位为 dBmo。 为获得可接受的质量，它应小于 35 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>被呼叫者接收的音频的模拟后增益控制音频噪音水平。 此指标的单位为 dBmo。 为获得可接受的质量，它应小于 35 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoReturn</p></td>
<td><p>int</p></td>
<td><p>对被叫方的回显返回丢失增强。 此指标的单位为 dB。 值越低表示回显越少。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>被呼叫者的扬声器呈现每5分钟的平均故障。 为了获得较高的质量，这应小于每五分钟一次。 不是由 A/V 会议服务器、中介服务器或 IP 电话报告。</p></td>
</tr>
<tr class="even">
<td><p>CalleeMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>被呼叫者的麦克风捕获每5分钟的平均故障。 若要获得较高的质量，这应小于每5分钟一次。 不是由 A/V 会议服务器、中介服务器或 IP 电话报告。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampDriftRateMic</p></td>
<td><p>小数（9，2）</p></td>
<td><p>被叫方的麦克风设备时钟相对于 CPU 时钟的时钟偏移速度。</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampDriftRateSpk</p></td>
<td><p>小数（9，2）</p></td>
<td><p>被叫方的扬声器设备时钟相对于 CPU 时钟的时钟偏移速度。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampErrorMicMs</p></td>
<td><p>小数（9，2）</p></td>
<td><p>呼叫的最后20秒内的麦克风捕获流的平均时间戳错误（以毫秒为单位）。</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampErrorSpkMs</p></td>
<td><p>小数（9，2）</p></td>
<td><p>被呼叫者的发言人的平均呈现流时间戳错误（以毫秒为单位）在呼叫的最后20秒中。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>Voice switch 是一个半双工模式，具有更低的中断能力。 有关详细信息，请参阅<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>被调用方的 echo 事件的原因。 有关详细信息，请参阅<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEchoPercentMicIn</p></td>
<td><p>decimal （5，2）</p></td>
<td><p>在被呼叫者的麦克风捕获流中检测到回显的时间的百分比。 如果使用的是耳机，则该值应较低。</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoPercentSend</p></td>
<td><p>decimal （5，2）</p></td>
<td><p>在被呼叫方的已发送流中检测到回显的时间的百分比。 发送流中的高回显百分比指示回声泄漏。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>在中介服务器上从被呼叫者的音频的网关收到了信号级别;这仅适用于中介服务器。 此指标的单位为 dBoV。 为了获得良好的质量，可接受范围应为 [-30 至-18] dBoV。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>在中介服务器上从被呼叫者的音频的网关收到了信号级别。 这仅适用于中介服务器。 此指标的单位为 dBoV。 为了获得良好的质量，可接受的范围应小于-50 dBoV。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>在应用于被呼叫者的音频的中介服务器端上的自动增益控制（AGC）。</p></td>
</tr>
<tr class="even">
<td><p>CalleeInitialSignalLevelRMS</p></td>
<td><p>点数</p></td>
<td><p>最长为呼叫的前30秒内被呼叫者的传入信号的根均值（RMS）。</p></td>
</tr>
<tr class="odd">
<td><p>RatioConcealedSamplesAvg</p></td>
<td><p>decimal （5，2）</p></td>
<td><p>通过音频康复对典型示例生成的隐藏样本的平均比率。</p></td>
</tr>
<tr class="even">
<td><p>RatioStretchedSamplesAvg</p></td>
<td><p>decimal （5，2）</p></td>
<td><p>由音频康复生成的一般示例中的延伸样本的平均比率。</p></td>
</tr>
<tr class="odd">
<td><p>RatioCompressedSamplesAvg</p></td>
<td><p>decimal （5，2）</p></td>
<td><p>由音频康复生成的压缩样本的平均比率到典型示例。</p></td>
</tr>
<tr class="even">
<td><p>工程</p></td>
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
<td><p>decimal （3，2）</p></td>
<td><p>呼叫的平均宽带网络 MOS。 此指标取决于所使用的数据包丢失、抖动和编解码器。 范围是1.0 到5.0。</p></td>
</tr>
<tr class="odd">
<td><p>OverallMinNetworkMOS</p></td>
<td><p>decimal （3，2）</p></td>
<td><p>用于呼叫的最小宽带网络 MOS。</p></td>
</tr>
<tr class="even">
<td><p>SendListenMOS</p></td>
<td><p>decimal （3，2）</p></td>
<td><p>平均预测宽带侦听发送音频的 MOS 分数，包括语音级别、噪声级别和捕获设备特征。</p></td>
</tr>
<tr class="odd">
<td><p>SendListenMOSMin</p></td>
<td><p>decimal （3，2）</p></td>
<td><p>呼叫的最小 SendListenMOS。</p></td>
</tr>
<tr class="even">
<td><p>RecvListenMOS</p></td>
<td><p>decimal （3，2）</p></td>
<td><p>平均预测宽带侦听从网络接收的音频的 MOS 分数，包括语音级别、噪音级别、编解码器、网络状况和捕获设备特征。</p></td>
</tr>
<tr class="odd">
<td><p>RecvListenMOSMin</p></td>
<td><p>decimal （3，2）</p></td>
<td><p>呼叫的最小 RecvListenMOS。</p></td>
</tr>
<tr class="even">
<td><p>AudioFECUsed</p></td>
<td><p>位</p></td>
<td><p>指示是否对呼叫使用音频 FEC。</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>位</p></td>
<td><p>指示 p 声明的标识信息的方向;1表示流方向来自调用方的调用者;0表示流方向从被呼叫方到调用方。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

