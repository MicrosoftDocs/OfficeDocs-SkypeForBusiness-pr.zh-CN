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
ms.openlocfilehash: 77cebcd47d735f1779396c0272877c0ec64a6189
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a>Lync Server 2013 中的 AudioStreamDetail 视图

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-03_

AudioStreamDetail 视图存储有关数据库中每个音频流的信息。 此视图已在 Microsoft Lync Server 2013 中引入。


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
<td><p>从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>媒体行内的唯一 ID。</p></td>
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
<td><p>对话框类别：0是 Lync 服务器，用于采集服务器腿;1是中介服务器到 PSTN 网关腿。</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>bit</p></td>
<td><p>指示是否已绕过呼叫的标志。</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>如果存在，则指示未跳过呼叫的原因，即使旁路 Id 匹配也是如此。 仅定义了一个值：</p>
<p>0x0001-默认网络适配器的旁路 ID 未知。</p></td>
</tr>
<tr class="odd">
<td><p>CallPriority</p></td>
<td><p>int</p></td>
<td><p>通话的优先级。</p></td>
</tr>
<tr class="even">
<td><p>CallerPool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>呼叫方池 FQDN。</p></td>
</tr>
<tr class="odd">
<td><p>CalleePool</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>被调用池 FQDN。</p></td>
</tr>
<tr class="even">
<td><p>呼叫者</p></td>
<td><p>nvarchar （450）</p></td>
<td><p>调用方的 URI。</p></td>
</tr>
<tr class="odd">
<td><p>被叫方</p></td>
<td><p>nvarchar （450）</p></td>
<td><p>被调用方的 URI。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>呼叫方的用户代理字符串。</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>呼叫方的用户代理的类型。 有关详细信息，请参阅<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar （64）</p></td>
<td><p>呼叫方的用户代理类别。 有关详细信息，请参阅<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表（QoE）</a> 。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>被呼叫方的用户代理字符串。</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>被调用方的用户代理的类型。 有关信息，请参阅<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar （64）</p></td>
<td><p>被呼叫方的用户代理类别。 有关信息，请参阅<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表（QoE）</a> 。</p></td>
</tr>
<tr class="even">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>调用方的终结点名称。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar(256)</p></td>
<td><p>被调用方的终结点名称。</p></td>
</tr>
<tr class="even">
<td><p>CallerOS</p></td>
<td><p>nvarchar</p></td>
<td><p>呼叫方终结点的操作系统（OS）。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeOS</p></td>
<td><p>nvarchar</p></td>
<td><p>被调用方终结点的操作系统（OS）。</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUName</p></td>
<td><p>nvarchar</p></td>
<td><p>呼叫方终结点的 CPU 名称。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUName</p></td>
<td><p>nvarchar</p></td>
<td><p>被调用方终结点的 CPU 名称。</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>呼叫方终结点中的 CPU 内核数。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>被调用方的终结点中的 CPU 内核数。</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>呼叫方终结点的 CPU 处理器速度。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>被调用方终结点的 CPU 处理器速度。</p></td>
</tr>
<tr class="even">
<td><p>CallerVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>指示呼叫者的系统是否在虚拟化环境中运行。 有关详细信息，请参阅<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的终结点表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>指示被调用方的系统是否在虚拟化环境中运行。 有关详细信息，请参阅<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的终结点表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CorrelationKey</p></td>
<td></td>
<td><p>相关密钥。 从<a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 中的 SessionCorrelation 表</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>有关媒体路径（如直接或中继）的信息。 有关详细信息，请参阅<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>有关在呼叫者的位标志中描述的交互式连接建立（ICE）流程的信息。 有关详细信息，请参阅体验质量监视服务器协议规范。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>有关被调用方的位标志中所述的交互式连接建立（ICE）流程的信息。 有关详细信息，请参阅体验质量监视服务器协议规范。</p></td>
</tr>
<tr class="even">
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>传输类型：0是 UDP，1是 TCP。</p></td>
</tr>
<tr class="odd">
<td><p>CallerIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>呼叫方的 IP 地址。 这可能是 IPv4 地址或 IPv6 地址。</p></td>
</tr>
<tr class="even">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>呼叫方使用的端口。</p></td>
</tr>
<tr class="odd">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>指示呼叫者是否在间隔网络内：1表示呼叫方位于企业网络内，0表示呼叫方位于网络外部。</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>被呼叫方的 IP 地址。 这可能是 IPv4 地址或 IPv6 地址。</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>被呼叫方使用的端口。</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>指示被调用方是否在间隔网络内：1表示被呼叫方位于企业网络内，0表示被呼叫方位于网络外部。</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserSite</p></td>
<td><p>nvarchar</p></td>
<td><p>呼叫者站点的名称。</p></td>
</tr>
<tr class="even">
<td><p>CallerRegion</p></td>
<td><p>nvarchar</p></td>
<td><p>呼叫方网站的国家/地区的名称。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserSite</p></td>
<td><p>nvarchar</p></td>
<td><p>被调用方的网站的名称。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar</p></td>
<td><p>被呼叫方网站的国家/地区的名称。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>呼叫方使用的 A/V 边缘服务的 IP 地址。 有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>由呼叫方使用的 A/V 边缘服务使用的端口。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>被呼叫方使用的 A/V 边缘服务的 IP 地址密钥。 有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>用于由被呼叫方使用的 A/V 边缘服务的端口。</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar （256）</p></td>
<td><p>呼叫方的捕获设备名称。</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>varchar （256）</p></td>
<td><p>调用方的呈现设备名称。</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar （256）</p></td>
<td><p>呼叫方的捕获设备驱动程序名称。</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDriver</p></td>
<td><p>varchar （256）</p></td>
<td><p>呼叫方的呈现设备驱动程序名称。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>varchar （256）</p></td>
<td><p>被调用方的捕获设备名称。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar （256）</p></td>
<td><p>被调用方的呈现设备名称。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>varchar （256）</p></td>
<td><p>被调用方的捕获设备驱动程序名称。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar （256）</p></td>
<td><p>被调用方的呈现设备驱动程序名称。</p></td>
</tr>
<tr class="odd">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>呼叫者的网络连接类型：0是 "有线"，1是 "无线"。</p></td>
</tr>
<tr class="even">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>指示呼叫者是否通过虚拟专用网络连接：1是虚拟专用网（VPN），0是非 VPN。</p></td>
</tr>
<tr class="odd">
<td><p>CallerLinkSpeed</p></td>
<td><p>十进制（18，0）</p></td>
<td><p>呼叫方终结点的网络链接速度（以 bps 为实现）。</p></td>
</tr>
<tr class="even">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>被呼叫方的网络连接类型：0是 "有线"，1是 "无线"。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>指示呼叫者是否通过虚拟专用网络连接：1是虚拟专用网（VPN），0是非 VPN。</p></td>
</tr>
<tr class="even">
<td><p>CalleeLinkSpeed</p></td>
<td><p>十进制（18，0）</p></td>
<td><p>被呼叫方终结点的网络链接速度，以 bps 为限。</p></td>
</tr>
<tr class="odd">
<td><p>ConversationalMOS</p></td>
<td><p>十进制（3，2）</p></td>
<td><p>音频会话的 Narrowband 对话 MOS （基于两个音频流）。</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>在给定各种策略设置（TURN、API、SDP、策略服务器等）的情况下，应用到给定发送端流的实际带宽。 此操作不会与有效的带宽混淆，因为根据带宽估计，可能会有较低的有效带宽。 这基本上是发送流对带宽估计所施加限制限制的最大带宽</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>实时控制协议（RTCP）统计信息的平均网络抖动。</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>通话期间网络抖动的最大值。</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRate</p></td>
<td><p>十进制（5，4）</p></td>
<td><p>通话期间平均数据包丢失速率。</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRateMax</p></td>
<td><p>十进制（5，4）</p></td>
<td><p>通话过程中观察到的最大数据包丢失。</p></td>
</tr>
<tr class="odd">
<td><p>BurstDensity</p></td>
<td><p>十进制（9，4）</p></td>
<td><p>通话期间出现猝发损失期间的数据包丢失的平均密度。</p></td>
</tr>
<tr class="even">
<td><p>BurstDuration</p></td>
<td><p>int</p></td>
<td><p>通话期间出现猝发损失期间的数据包丢失的平均持续时间。</p></td>
</tr>
<tr class="odd">
<td><p>BurstGapDensity</p></td>
<td><p>十进制（9，4）</p></td>
<td><p>出现猝发数据包丢失之间的平均数据包损失的平均密度。</p></td>
</tr>
<tr class="even">
<td><p>BurstGapDuration</p></td>
<td><p>int</p></td>
<td><p>爆发数据包损失之间的平均持续时间。</p></td>
</tr>
<tr class="odd">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>音频流的数据包计数。</p></td>
</tr>
<tr class="even">
<td><p>BandwidthEst</p></td>
<td><p>int</p></td>
<td><p>音频流的带宽估计。</p></td>
</tr>
<tr class="odd">
<td><p>DegradationAvg</p></td>
<td><p>十进制（3，2）</p></td>
<td><p>整个通话的网络 MOS 降级。 范围为0.0 到5.0。 此指标显示由于抖动和数据包丢失，网络 MOS 的减少量。 对于可接受的质量，它应小于0.5。</p></td>
</tr>
<tr class="even">
<td><p>DegradationMax</p></td>
<td><p>十进制（3，2）</p></td>
<td><p>通话期间最大网络 MOS 性能下降。</p></td>
</tr>
<tr class="odd">
<td><p>DegradationJitterAvg</p></td>
<td><p>十进制（3，2）</p></td>
<td><p>由抖动导致的网络 MOS 性能下降。</p></td>
</tr>
<tr class="even">
<td><p>DegradationPacketLossAvg</p></td>
<td><p>十进制（3，2）</p></td>
<td><p>由于数据包丢失导致网络 MOS 性能下降。</p></td>
</tr>
<tr class="odd">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>用于呼叫的音频编解码器，从<a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中的 PayloadDescription 表</a>引用。</p></td>
</tr>
<tr class="even">
<td><p>AudioSampleRate</p></td>
<td><p>int</p></td>
<td><p>音频流的采样率。</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>呼叫者发送的音频的模拟增益控制音频信号级别。 此指标的单位为 dBmo。 为获得可接受的质量，它至少应为 30 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>呼叫者收到的音频的音频信号级别。 此指标的单位为 dBmo。 为获得可接受的质量，它至少应为 30 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>为呼叫者发送的音频的模拟后增益控制音频噪音级别。 此指标的单位为 dBmo。 为获得可接受的质量，它应小于 35 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>呼叫者收到的音频的后模拟增益控制音频噪音级别。 此指标的单位为 dBmo。 为获得可接受的质量，它应小于 35 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoReturn</p></td>
<td><p>int</p></td>
<td><p>呼叫方的回音返回损失增强。 此指标的单位为 dB。 较低的值表示较少的回声。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="even">
<td><p>CallerSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>呼叫者的扬声器呈现每五分钟的平均故障。 为了获得良好的质量，这应该小于每五分钟一次。 不由 A/V 式会议服务器、中介服务器或 IP 电话报告。</p></td>
</tr>
<tr class="odd">
<td><p>CallerMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>呼叫者的麦克风捕获每五分钟的平均故障。 为了获得良好的质量，这应该小于每五分钟一次。 不由 A/V 式会议服务器、中介服务器或 IP 电话报告。</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampDriftRateMic</p></td>
<td><p>十进制（9，2）</p></td>
<td><p>呼叫者的麦克风设备时钟偏移速率，相对于 CPU 时钟。</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampDriftRateSpk</p></td>
<td><p>十进制（9，2）</p></td>
<td><p>呼叫者的扬声器设备时钟偏移率（相对于 CPU 时钟）。</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampErrorMicMs</p></td>
<td><p>十进制（9，2）</p></td>
<td><p>在呼叫的最后20秒内，麦克风捕获流时间戳的平均时间戳错误（以毫秒为单位）。</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampErrorSpkMs</p></td>
<td><p>十进制（9，2）</p></td>
<td><p>呼叫者最近20秒内呼叫者的扬声器渲染流时间戳错误的平均值。</p></td>
</tr>
<tr class="even">
<td><p>CallerVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>语音开关是一种具有更低中断能力的半双工模式。 有关详细信息，请参阅<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>呼叫方的 echo 事件的原因。 有关详细信息，请参阅<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CallerEchoPercentMicIn</p></td>
<td><p>十进制（5，2）</p></td>
<td><p>在呼叫者的麦克风捕获流中检测到回声的时间的百分比。 如果使用耳机，则该值应较低。</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoPercentSend</p></td>
<td><p>十进制（5，2）</p></td>
<td><p>在呼叫方的发送流中检测到回显的时间的百分比。 发送流中的高回显百分比表示回声泄漏。</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>在中介服务器上收到来自呼叫者音频的网关的信号级别;这仅适用于中介服务器。 此指标的单位为 dBoV。 为了获得优质，可接受范围应为-30 至-18 dBoV。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>在中介服务器上从呼叫方音频的网关接收的信号级别。 这仅适用于中介服务器。 此指标的单位为 dBoV。 为了获得优质，可接受范围应小于-50 dBoV。</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>在中介服务器端应用于呼叫方音频的自动增益控制（AGC）。</p></td>
</tr>
<tr class="odd">
<td><p>CallerInitialSignalLevelRMS</p></td>
<td><p>float</p></td>
<td><p>呼叫方的传入信号的根平均值平方（RMS），最多可拨出前30秒。</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>表示被呼叫者发送的音频的后模拟增益控制音频信号级别。 此指标的单位为 dBmo。 为获得可接受的质量，它至少应为 30 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>被呼叫方收到的音频的音频信号级别。 此指标的单位为 dBmo。 为获得可接受的质量，它至少应为 30 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>对被呼叫者发送的音频进行模拟提升控制音频噪音级别。 此指标的单位为 dBmo。 为获得可接受的质量，它应小于 35 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>被呼叫方接收的音频的模拟后增益控制音频噪音级别。 此指标的单位为 dBmo。 为获得可接受的质量，它应小于 35 dBmo。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoReturn</p></td>
<td><p>int</p></td>
<td><p>被调用方的回音返回损失增强。 此指标的单位为 dB。 较低的值表示较少的回声。 A/V 会议服务器或 IP 电话不报告此指标。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>被调用方的扬声器呈现每五分钟的平均故障。 为了获得良好的质量，这应该小于每五分钟一次。 不由 A/V 式会议服务器、中介服务器或 IP 电话报告。</p></td>
</tr>
<tr class="even">
<td><p>CalleeMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>被呼叫者的麦克风捕获每五分钟的平均故障。 为了获得良好的质量，这应该小于每五分钟一次。 不由 A/V 式会议服务器、中介服务器或 IP 电话报告。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampDriftRateMic</p></td>
<td><p>十进制（9，2）</p></td>
<td><p>被呼叫者的麦克风设备时钟偏移速率，相对于 CPU 时钟。</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampDriftRateSpk</p></td>
<td><p>十进制（9，2）</p></td>
<td><p>被呼叫者的扬声器设备时钟偏移速率，相对于 CPU 时钟。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampErrorMicMs</p></td>
<td><p>十进制（9，2）</p></td>
<td><p>在呼叫的最后20秒内，麦克风捕获流时间戳的平均时间戳错误（以毫秒为单位）。</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampErrorSpkMs</p></td>
<td><p>十进制（9，2）</p></td>
<td><p>在呼叫的最后20秒内，被调用方的扬声器的平均呈现流时间戳错误（以毫秒为单位）。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>语音开关是一种具有更低中断能力的半双工模式。 有关详细信息，请参阅<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>被调用方的 echo 事件的原因。 有关详细信息，请参阅<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEchoPercentMicIn</p></td>
<td><p>十进制（5，2）</p></td>
<td><p>在被呼叫者的麦克风捕获流中检测到回显的时间百分比。 如果使用耳机，则该值应较低。</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoPercentSend</p></td>
<td><p>十进制（5，2）</p></td>
<td><p>在被调用方的发送流中检测到回显的时间的百分比。 发送流中的高回显百分比表示回声泄漏。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>在中介服务器上从被呼叫方的音频的网关接收的信号级别;这仅适用于中介服务器。 此指标的单位为 dBoV。 为了获得良好的质量，可接受的范围应为 [-30 至-18] dBoV。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>在中介服务器上从被呼叫方的音频的网关接收的信号级别。 这仅适用于中介服务器。 此指标的单位为 dBoV。 为了获得优质，可接受范围应小于-50 dBoV。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>在中介服务器端应用于被呼叫方的音频的自动增益控制（AGC）。</p></td>
</tr>
<tr class="even">
<td><p>CalleeInitialSignalLevelRMS</p></td>
<td><p>float</p></td>
<td><p>到达呼叫的前30秒内被呼叫方的传入信号的根平均值方块（RMS）。</p></td>
</tr>
<tr class="odd">
<td><p>RatioConcealedSamplesAvg</p></td>
<td><p>十进制（5，2）</p></td>
<td><p>通过音频康复为典型示例生成的隐藏样本的平均比率。</p></td>
</tr>
<tr class="even">
<td><p>RatioStretchedSamplesAvg</p></td>
<td><p>十进制（5，2）</p></td>
<td><p>通过音频康复为典型示例生成的拉伸样本的平均比率。</p></td>
</tr>
<tr class="odd">
<td><p>RatioCompressedSamplesAvg</p></td>
<td><p>十进制（5，2）</p></td>
<td><p>从音频修复到典型示例生成的压缩样本的平均比率。</p></td>
</tr>
<tr class="even">
<td><p>RoundTrip</p></td>
<td><p>int</p></td>
<td><p>从 RTCP 统计数据往返的时间。</p></td>
</tr>
<tr class="odd">
<td><p>RoundTripMax</p></td>
<td><p>int</p></td>
<td><p>音频流的最大往返行程时间。</p></td>
</tr>
<tr class="even">
<td><p>OverallAvgNetworkMOS</p></td>
<td><p>十进制（3，2）</p></td>
<td><p>通话的平均宽带网络 MOS。 此指标取决于所使用的数据包丢失、抖动和编解码器。 范围为1.0 到5.0。</p></td>
</tr>
<tr class="odd">
<td><p>OverallMinNetworkMOS</p></td>
<td><p>十进制（3，2）</p></td>
<td><p>通话最少宽带网络 MOS。</p></td>
</tr>
<tr class="even">
<td><p>SendListenMOS</p></td>
<td><p>十进制（3，2）</p></td>
<td><p>平均预测宽带为已发送音频的 MOS 分数，包括语音级别、噪声级别和捕获设备特征。</p></td>
</tr>
<tr class="odd">
<td><p>SendListenMOSMin</p></td>
<td><p>十进制（3，2）</p></td>
<td><p>通话的最低 SendListenMOS。</p></td>
</tr>
<tr class="even">
<td><p>RecvListenMOS</p></td>
<td><p>十进制（3，2）</p></td>
<td><p>平均预测宽带从网络接收的音频的 MOS 分数，包括语音级别、噪音级别、编解码器、网络条件和捕获设备特征。</p></td>
</tr>
<tr class="odd">
<td><p>RecvListenMOSMin</p></td>
<td><p>十进制（3，2）</p></td>
<td><p>通话的最低 RecvListenMOS。</p></td>
</tr>
<tr class="even">
<td><p>AudioFECUsed</p></td>
<td><p>bit</p></td>
<td><p>指示是否已将音频 FEC 用于呼叫。</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>bit</p></td>
<td><p>指示 p 声明的标识信息的方向;1表示流方向从调用方到被调用方;0表示流方向来自被调用方的调用方。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

