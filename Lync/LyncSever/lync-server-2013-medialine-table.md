---
title: Lync Server 2013：MediaLine 表
TOCTitle: MediaLine 表
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425920(v=OCS.15)
ms:contentKeyID: 49312652
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的 MediaLine 表

 

_**上一次修改主题：** 2015-03-09_

每条记录代表一个媒体行。（一个音频会话通常包含一个音频媒体行。一个音频与视频 (A/V) 会话通常包含一个音频媒体行和一个视频媒体行，但如果使用了会议设备或库视图，该会话可能包含两个视频媒体行。）


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>列</strong></th>
<th><strong>数据类型</strong></th>
<th><strong>键/索引</strong></th>
<th><strong>详细信息</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ConferenceDateTime</strong></p></td>
<td><p>datetime</p></td>
<td><p>主</p></td>
<td><p>引用自 <a href="lync-server-2013-session-table.md">Lync Server 2013 中的 Session 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>主</p></td>
<td><p>引用自 <a href="lync-server-2013-session-table.md">Lync Server 2013 中的 Session 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>主</p></td>
<td><p>0 是主要音频，1 是主要视频，2 是全景视频，3 是应用程序/桌面共享。此标签在单个会话中必须是唯一的。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectivityIce</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>此列存在但不用于 Microsoft Lync Server 2013 中。可在 CallerConnectivityICE 和 CalleeConnectivityICE 列中捕获用于媒体行的连接的相关信息。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>关于位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅可供下载的 <em>体验质量监控服务器协议规范</em> 。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>与 CallerIceWarningFlags 相同，但位于被叫方端。有关详细信息，请参阅可供下载的 <em>体验质量监控服务器协议规范</em> 。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Security</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>正在使用的安全配置文件。0 为 NONE，1 为 SRTP，2 为 V1。</p></td>
</tr>
<tr class="even">
<td><p><strong>传输</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>0 为 UDP，1 为 TCP。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫者的 IP 地址。有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>呼叫者使用的端口。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerSubnet</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫者的子网。有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerInside</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 表示呼叫者位于企业网络内部，0 表示呼叫者位于该网络外部。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫者的 MAC 地址，引用自 <a href="lync-server-2013-macaddress-table.md">Lync Server 2013 中的 MacAddress 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫者使用的 Lync Server A/V 边缘服务的 IP 地址。有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>呼叫者在 A/V 边缘服务中使用的端口。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫者使用的捕获设备。引用自 <a href="lync-server-2013-device-table.md">Lync Server 2013 中的 Device 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫者使用的呈现设备。引用自 <a href="lync-server-2013-device-table.md">Lync Server 2013 中的 Device 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫者捕获设备的驱动程序，引用自 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 中的 DeviceDriver 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫者呈现设备的驱动程序，引用自 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 中的 DeviceDriver 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>外</p></td>
<td><p>指示呼叫者如何连接到网络。值是从 <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail 表</a> 获得的。对于有线连接，典型值为 0；对于 WiFi 连接，典型值为 1；对于以太网连接，典型值为 3。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerBssid</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>使用无线时呼叫者的 BSSID。引用自 <a href="lync-server-2013-macaddress-table.md">Lync Server 2013 中的 MacAddress 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerVPN</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>呼叫者的链接。1 为虚拟专用网络 (VPN)，0 为非 VPN。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerLinkSpeed</strong></p></td>
<td><p>decimal(18.0)</p></td>
<td><p></p></td>
<td><p>呼叫者终结点的网络链接速度（以 bps 为单位）。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫接收者的 IP 地址。有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePort</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>呼叫接收者使用的端口。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeSubnet</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>被叫方的子网。有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeInside</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1 表示呼叫接收者位于企业网络内部，0 表示呼叫接收者位于该网络外部。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>被叫方 MAC 地址。引用自 <a href="lync-server-2013-macaddress-table.md">Lync Server 2013 中的 MacAddress 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫接收者使用的 A/V 边缘服务的 IP 地址。有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>呼叫接收者在 A/V 边缘服务中使用的端口。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫接收者使用的捕获设备。引用自 <a href="lync-server-2013-device-table.md">Lync Server 2013 中的 Device 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫接收者使用的呈现设备。引用自 <a href="lync-server-2013-device-table.md">Lync Server 2013 中的 Device 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>呼叫接收者的捕获设备的驱动程序。引用自 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 中的 DeviceDriver 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDevDriver</strong></p></td>
<td><p>varchar(256)</p></td>
<td><p>外</p></td>
<td><p>呼叫接收者的呈现设备的驱动程序。引用自 <a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 中的 DeviceDriver 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>外</p></td>
<td><p>指示被呼叫者如何连接到网络。值是从 <a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail 表</a> 获得的。对于有线连接，典型值为 0；对于 WiFi 连接，典型值为 1；对于以太网连接，典型值为 3。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeBssid</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>使用无线时被叫方的 BSSID。引用自 <a href="lync-server-2013-macaddress-table.md">Lync Server 2013 中的 MacAddress 表</a>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeVPN</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>呼叫接收者的链接；1 为虚拟专用网络 (VPN)，0 为非 VPN。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeLinkSpeed</strong></p></td>
<td><p>decimal(18.0)</p></td>
<td><p> </p></td>
<td><p>呼叫接收者的终结点的网络链接速度（以 bps 为单位）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConversationalMOS</strong></p></td>
<td><p>decimal(3.2)</p></td>
<td><p> </p></td>
<td><p>音频会话的窄带交谈 MOS（基于两个音频流）。</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimit</strong></p></td>
<td><p>int</p></td>
<td><p></p></td>
<td><p>这是应用于指定发送端流指定的多种策略设置（TURN、API、SDP、策略服务器等）的实际带宽。不要将其与有效带宽混淆，因为根据带宽预估的不同，有效带宽可能会减少。这基本上是发送流可禁止带宽预估设定的限制的最大带宽。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>smallint</p></td>
<td><p></p></td>
<td><p>这是所设定的带宽限制的来源。它说明带宽限制的来源（“Policy Server”、“TURN Server”、“Modality”等）。引用自 <a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013 中的 AppliedBandwidthSource 表</a>。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫者</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>指示是否已收到来自呼叫者的度量；1 为是，空值为否。</p></td>
</tr>
<tr class="odd">
<td><p><strong>被叫方</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>指示是否已收到来自呼叫接收者的度量；1 为是，空值为否。</p></td>
</tr>
<tr class="even">
<td><p><strong>MidCallReport</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>指示报告是针对会话的一部分还是整个会话。</p>
<p>此列是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>bit</p></td>
<td><p></p></td>
<td><p>指示呼叫是已归类为质量欠佳的呼叫（值 1）还是质量良好的呼叫 (0)。</p>
<p>此列是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerConnectivityICE</strong></p></td>
<td><p>tinyInt</p></td>
<td><p></p></td>
<td><p>指示呼叫者是否已连接到使用 ICE 协议（Internet 连接建立）的网络。</p>
<p>此列是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeConnectivityICE</strong></p></td>
<td><p>tinyint</p></td>
<td><p></p></td>
<td><p>指示呼叫者是否已连接到使用 ICE 协议（Internet 连接建立）的网络。</p>
<p>此列是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>发出呼叫的用户的反身 IP 地址。在使用 NAT（网络地址转换）的组织中，反身 IP 地址是代理服务器的 IP 地址。</p>
<p>此列是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>发出呼叫的用户所使用的 WiFi 驱动程序的设备描述。</p>
<p>此列是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>发出呼叫的用户所使用的 WiFi 驱动程序的版本号。</p>
<p>此列是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>收到呼叫的用户的反身 IP 地址。在使用 NAT（网络地址转换）的组织中，反身 IP 地址是代理服务器的 IP 地址。</p>
<p>此列是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>接收呼叫的用户所使用的 WiFi 驱动程序的设备描述。</p>
<p>此列是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>外</p></td>
<td><p>接收呼叫的用户所使用的 WiFi 驱动程序的版本号。</p>
<p>此列是在 Microsoft Lync Server 2013 中引入的。</p></td>
</tr>
</tbody>
</table>

