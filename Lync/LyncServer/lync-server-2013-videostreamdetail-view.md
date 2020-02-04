---
title: Lync Server 2013： VideoStreamDetail 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfa754fbcc24377b07bab3b13473adb1c5e953ea
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a>Lync Server 2013 中的 VideoStreamDetail 视图

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-03_

VideoStreamDetail 视图存储有关数据库中每个视频流的信息。 此视图已在 Microsoft Lync Server 2013 中引入。


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
<td><p>从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p>MediaLineLabel</p></td>
<td><p>tinyint</p></td>
<td><p>从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</p></td>
</tr>
<tr class="even">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>媒体行内的唯一 ID。</p></td>
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
<td><p>呼叫者的用户代理类别。 有关详细信息，请参阅<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表（QoE）</a> 。</p></td>
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
<td><p>呼叫方终结点的 CPU 内核数。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>被调用方终结点的 CPU 内核数。</p></td>
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
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>有关媒体路径（如直接或中继）的信息。 有关详细信息，请参阅<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>有关在呼叫者的位标志中描述的交互式连接建立（ICE）流程的信息。 有关详细信息，请参阅体验质量监视服务器协议规范。</p></td>
</tr>
<tr class="even">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>有关被调用方的位标志中所述的交互式连接建立（ICE）流程的信息。 有关详细信息，请参阅体验质量监视服务器协议规范。</p></td>
</tr>
<tr class="odd">
<td><p>Transport</p></td>
<td><p>int</p></td>
<td><p>传输类型：0是 UDP，1是 TCP。</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>呼叫方的 IP 地址。 这可能是 IPv4 地址或 IPv6 地址。</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>呼叫方使用的端口。</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>指示呼叫者是否在组织网络内。 1表示呼叫方位于企业网络内，0表示呼叫方位于网络外部。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>被呼叫方的 IP 地址。 这可能是 IPv4 地址或 IPv6 地址。</p></td>
</tr>
<tr class="even">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>被呼叫方使用的端口。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>指示呼叫者是否在组织网络内。1表示被呼叫方位于企业网络内，0表示被呼叫方在网络外部。</p></td>
</tr>
<tr class="even">
<td><p>CallerUserSite</p></td>
<td><p>nvarchar</p></td>
<td><p>呼叫者站点的名称。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRegion</p></td>
<td><p>nvarchar</p></td>
<td><p>呼叫方网站的国家/地区的名称。</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserSite</p></td>
<td><p>nvarchar</p></td>
<td><p>被调用方的网站的名称。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar</p></td>
<td><p>被呼叫方网站的国家/地区的名称。</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>呼叫方使用的 A/V 边缘服务的 IP 地址。 有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>呼叫方使用的 A/V 边缘服务上的端口。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>被呼叫方使用的 A/V 边缘服务的 IP 地址密钥。 有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>被呼叫方使用的 A/V 边缘服务上的端口。</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar （256）</p></td>
<td><p>呼叫方的捕获设备名称。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDev</p></td>
<td><p>varchar （256）</p></td>
<td><p>调用方的呈现设备名称。</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar （256）</p></td>
<td><p>呼叫方的捕获设备驱动程序名称。</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDevDriver</p></td>
<td><p>varchar （256）</p></td>
<td><p>呼叫方的呈现设备驱动程序名称。</p></td>
</tr>
<tr class="even">
<td><p>CalleeCaptureDev</p></td>
<td><p>varchar （256）</p></td>
<td><p>被调用方的捕获设备名称。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar （256）</p></td>
<td><p>被调用方的呈现设备名称。</p></td>
</tr>
<tr class="even">
<td><p>CalleCaptureDevDriver</p></td>
<td><p>varchar （256）</p></td>
<td><p>被调用方的捕获设备驱动程序名称。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar （256）</p></td>
<td><p>被调用方的呈现设备驱动程序名称。</p></td>
</tr>
<tr class="even">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>呼叫者的网络连接类型：0是 "有线"，1是 "无线"。</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>指示呼叫者是否通过虚拟专用网络连接。 1是虚拟专用网络（VPN），0是非 VPN。</p></td>
</tr>
<tr class="even">
<td><p>CallerLinkSpeed</p></td>
<td><p>十进制（18，）</p></td>
<td><p>呼叫方终结点的网络链接速度（以 bps 为实现）。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>被呼叫方的网络连接类型：0是 "有线"，1是 "无线"。</p></td>
</tr>
<tr class="even">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>指示被呼叫方是否通过虚拟专用网络进行连接。 1是虚拟专用网络（VPN），0是非 VPN。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeLinkSpeed</p></td>
<td><p>十进制（18，0）</p></td>
<td><p>被调用方终结点的网络链接速度（以 bps 为 bps）。</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>十进制（3，2）</p></td>
<td><p>音频会话的 Narrowband 对话 MOS （基于两个音频流）。</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>在给定各种策略设置（TURN、API、SDP、策略服务器等）的情况下，应用到给定发送端流的实际带宽。 此操作不会与有效的带宽混淆，因为根据带宽估计，可能会有较低的有效带宽。 这基本上是发送流可以通过带宽估计限制限制的最大带宽。</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>实时控制协议（RTCP）统计信息的平均网络抖动。</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>通话期间网络抖动的最大值。</p></td>
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
<td><p>PacketLossRate</p></td>
<td><p>十进制（5，4）</p></td>
<td><p>通话期间平均数据包丢失速率。</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRateMax</p></td>
<td><p>十进制（5，4）</p></td>
<td><p>通话过程中观察到的最大数据包丢失。</p></td>
</tr>
<tr class="even">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>视频流的数据包计数（实时传输协议、RTP）。</p></td>
</tr>
<tr class="odd">
<td><p>BandwidthEst</p></td>
<td><p>int</p></td>
<td><p>音频流的带宽估计。</p></td>
</tr>
<tr class="even">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>用于呼叫的音频编解码器，从<a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中的 PayloadDescription 表</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p>VideoResolution</p></td>
<td><p>char （9）</p></td>
<td><p>以像素为单位的视频分辨率（以像素为单位）乘以像素高度。 报告为字符串。</p></td>
</tr>
<tr class="even">
<td><p>VideoBitRateAvg</p></td>
<td><p>int</p></td>
<td><p>视频流的平均比特率。</p></td>
</tr>
<tr class="odd">
<td><p>InboundVideoFrameRateAvg</p></td>
<td><p>十进制（9，4）</p></td>
<td><p>收到的视频的帧速率。</p></td>
</tr>
<tr class="even">
<td><p>OutboundVideoFrameRateAvg</p></td>
<td><p>十进制（9，4）</p></td>
<td><p>已发送视频的帧速率。</p></td>
</tr>
<tr class="odd">
<td><p>ViideoBitRateMax</p></td>
<td><p>int</p></td>
<td><p>视频会话期间的最大视频比特率。</p></td>
</tr>
<tr class="even">
<td><p>VideoPacketLossRate</p></td>
<td><p>十进制（9，4）</p></td>
<td><p>视频数据包丢失的速率。</p></td>
</tr>
<tr class="odd">
<td><p>VideoFrameLossRate</p></td>
<td><p>十进制（9.4）</p></td>
<td><p>丢失的视频帧总数的百分比。</p></td>
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
<td><p>十进制（9.4）</p></td>
<td><p>丢失的视频帧总数的百分比。</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>bit</p></td>
<td><p>P 声明的标识信息的流方向。 1表示流方向从调用方到被调用方;0表示流方向来自被调用方的调用方。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

