---
title: MediaLine 视图
TOCTitle: MediaLine 视图
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49888306
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# MediaLine 视图

 

_**上一次修改主题：** 2015-03-09_

媒体行视图存储有关数据库中每个媒体行的信息。一个音频会话通常包含一个音频媒体行。一个音频和视频 (A/V) 会话通常包含一个音频媒体行和一个视频媒体行；但是，如果使用会议设备或使用库视图，则该会话可能包含两个视频媒体行。此视图是在 Microsoft Lync Server 2013 中引入的。


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
<td><p>ConferenceDateTime</p></td>
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
<td><p>Security</p></td>
<td><p>tinyint</p></td>
<td><p>正在使用的安全配置文件。0 为无，1 为 SRTP，2 为 V1。</p></td>
</tr>
<tr class="odd">
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>传输类型。0 为 UDP，1 为 TCP。</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>呼叫者的 IP 地址。可为 IPv4 或 IPv6 地址。</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>呼叫者使用的端口。</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>指示呼叫者是否在组织网络内。1 表示呼叫者在企业网络内。0 表示呼叫者在网络外。</p></td>
</tr>
<tr class="odd">
<td><p>CallerMacAddress</p></td>
<td><p>varchar(256)</p></td>
<td><p>呼叫者使用的网络接口的 MAC 地址。</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>呼叫者使用的 A/V 边缘服务的 IP 地址。有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>呼叫者在 A/V 边缘服务中使用的端口。</p></td>
</tr>
<tr class="even">
<td><p>CallerReflexiveIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>A/V 边缘服务报告的呼叫者的 IP 地址。如果客户端位于 NAT 之后，则此地址可能与 CallerIPAddr 不同。</p></td>
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
<td><p>CallerRenderDevDriver</p></td>
<td><p>varchar(256)</p></td>
<td><p>呼叫者的呈现设备驱动程序名称。</p></td>
</tr>
<tr class="odd">
<td><p>CallerWifiDriverDeviceDesc</p></td>
<td><p>varchar(256)</p></td>
<td><p>呼叫者的 Wifi 驱动程序描述。</p></td>
</tr>
<tr class="even">
<td><p>CallerWiFiDriverVersion</p></td>
<td><p>varchar(256)</p></td>
<td><p>呼叫者的 Wifi 驱动程序版本。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar(256)</p></td>
<td><p>呼叫者的网络连接的详细信息。有关详细信息，请参阅 <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CallerBssid</p></td>
<td><p>varchar(256)</p></td>
<td><p>呼叫者 WiFi 连接使用的基本服务集标识符。</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>指示呼叫者是否通过虚拟专用网连接。1 是虚拟专用网 (VPN)，0 是非 VPN。</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>被叫方的 IP 地址。可为 IPv4 或 IPv6 地址。</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>被叫方使用的端口。</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>指示被叫方是否在企业网络内。1 表示被叫方在企业网络内，0 表示被叫方在该网络外。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeMacAddress</p></td>
<td><p>varchar(256)</p></td>
<td><p>被叫方使用的网络接口的 MAC 地址。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>被叫方使用的 A/V 边缘服务的 IP 地址。有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>被叫方在 A/V 边缘服务中使用的端口。</p></td>
</tr>
<tr class="even">
<td><p>CalleeReflexiveIPAddr</p></td>
<td><p>var(50)</p></td>
<td><p>A/V 边缘服务报告的被叫方的 IP 地址。如果客户端位于 NAT 之后，则此地址可能与 CalleeIPAddr 不同。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>var(50)</p></td>
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
<td><p>CalleeWifiDriverDeviceDesc</p></td>
<td><p>varchar(256)</p></td>
<td><p>被叫方的 Wifi 驱动程序描述。</p></td>
</tr>
<tr class="even">
<td><p>CalleeWiFiDriverVersion</p></td>
<td><p>varchar(256)</p></td>
<td><p>被叫方的 Wifi 驱动程序版本。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar(256)</p></td>
<td><p>被叫方的网络连接的详细信息。有关详细信息，请参阅 <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CalleeBssid</p></td>
<td><p>varchar(256)</p></td>
<td><p>被叫方 WiFi 连接使用的基本服务集标识符。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>指示被叫方是否通过虚拟专用网连接。1 是虚拟专用网 (VPN)，0 是非 VPN。</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>decimal(3.2)</p></td>
<td><p>音频会话的窄带交谈 MOS（基于两个音频流）。</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>这是应用于指定发送端流指定的多种策略设置（TURN、API、SDP、策略服务器等）的实际带宽。不应将其与有效带宽混淆，因为根据带宽预估的不同，有效带宽可能会减少。这基本上是发送流可禁止带宽预估设定的限制的最大带宽。</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthSource</p></td>
<td><p>varchar(256)</p></td>
<td><p>所设定的带宽限制的来源。它描述带宽限制源自的位置（例如，“策略服务器”、“TURN 服务器”或“形式”）。</p></td>
</tr>
<tr class="odd">
<td><p>Caller</p></td>
<td><p>bit</p></td>
<td><p>指示是否已收到来自呼叫者的度量；1 为是，0 为否。</p></td>
</tr>
<tr class="even">
<td><p>Callee</p></td>
<td><p>bit</p></td>
<td><p>指示是否已收到来自呼叫接收者的度量；1 为是，0 为否。</p></td>
</tr>
<tr class="odd">
<td><p>MidCallReport</p></td>
<td><p>bit</p></td>
<td><p>指示报告用于呼叫的一部分还是用于整个呼叫。</p></td>
</tr>
<tr class="even">
<td><p>ClassifiedPoorCall</p></td>
<td><p>bit</p></td>
<td><p>指示呼叫被分类为质量欠佳的呼叫 (1) 还是质量良好的呼叫 (0)。</p></td>
</tr>
<tr class="odd">
<td><p>CallerConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>指示呼叫者是否使用 ICE 协议（Internet 连接建立）连接至网络。</p></td>
</tr>
<tr class="even">
<td><p>CalleeConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>指示被呼叫的用户是否使用 ICE 协议（Internet 连接建立）连接至网络。</p></td>
</tr>
</tbody>
</table>

