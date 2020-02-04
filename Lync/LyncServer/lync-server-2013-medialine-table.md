---
title: Lync Server 2013：MediaLine 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine table
ms:assetid: 414b1d63-ae97-4c27-bac0-c9ad0f808ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425920(v=OCS.15)
ms:contentKeyID: 48183956
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7488aa258fd30c2f9b519806dc84f9d897a08656
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758750"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-table-in-lync-server-2013"></a>Lync Server 2013 中的 MediaLine 表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2014-02-21_

每条记录表示一个媒体行。 （一个音频会话通常包含一个音频媒体行。 一个音频和视频（A/V）会话通常包含一个音频媒体线和一个视频媒体行，但如果使用了会议设备或使用了库视图，则该会话可能包含两个视频媒体线。


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
<td><p>Primary</p></td>
<td><p>从<a href="lync-server-2013-session-table.md">Lync Server 2013 中的会话表</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>SessionSeq</strong></p></td>
<td><p>int</p></td>
<td><p>Primary</p></td>
<td><p>从<a href="lync-server-2013-session-table.md">Lync Server 2013 中的会话表</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MediaLineLabel</strong></p></td>
<td><p>tinyint</p></td>
<td><p>Primary</p></td>
<td><p>0是主音频，1是主视频，2是全景视频，3是应用程序/桌面共享。 此标签在单个会话中必须是唯一的。</p></td>
</tr>
<tr class="even">
<td><p><strong>ConnectivityIce</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>此列存在，但未在 Microsoft Lync Server 2013 中使用。 在 "CallerConnectivityICE" 和 "CalleeConnectivityICE" 列中捕获有关用于媒体行的连接的信息。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>有关在 bits 标志中描述的交互式连接建立（ICE）流程的信息。 有关详细信息，请参阅可供下载的<em>体验质量监视服务器协议规范</em>。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIceWarningFlags</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>与 CallerIceWarningFlags 相同，但在被调用方。 有关详细信息，请参阅可供下载的<em>体验质量监视服务器协议规范</em>。</p></td>
</tr>
<tr class="odd">
<td><p><strong>安全性</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>正在使用的安全配置文件。 0为 NONE，1为 SRTP，2为 V1。</p></td>
</tr>
<tr class="even">
<td><p><strong>Transport</strong></p></td>
<td><p>tinyint</p></td>
<td><p> </p></td>
<td><p>0是 UDP，1是 TCP。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>呼叫方的 IP 地址。 有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>呼叫方使用的端口。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerSubnet</strong></p></td>
<td><p>int</p></td>
<td><p> 外表</p></td>
<td><p>呼叫方的子网。 有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerInside</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1表示呼叫方位于企业网络内，0表示呼叫方位于网络外部。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>呼叫者的 mac 地址，从<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 中的 MacAddress 表</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>呼叫者使用的 Lync Server A/V 边缘服务的 IP 地址。 有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>由呼叫者在 A/V 边缘服务上使用的端口。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>由呼叫者使用的捕获设备。 从<a href="lync-server-2013-device-table.md">Lync Server 2013 中的设备表</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>由呼叫者使用的渲染设备。 从<a href="lync-server-2013-device-table.md">Lync Server 2013 中的设备表</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>呼叫者捕获设备的驱动程序，从<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 中的 DeviceDriver 表</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerRenderDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>呼叫者的呈现设备的驱动程序，从<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 中的 DeviceDriver 表</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>外表</p></td>
<td><p>指示呼叫者如何连接到网络。 从<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表中</a>获取值。 用于 WiFi 连接的有线连接 "1" 的典型值为 0;对于以太网连接，请使用3。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerBssid</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>呼叫者的 BSSID （如果使用无线）。 从<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 中的 MacAddress 表</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerVPN</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>呼叫者的链接。 1是虚拟专用网络（VPN），0是非 VPN。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerLinkSpeed</strong></p></td>
<td><p>十进制（18，0）</p></td>
<td></td>
<td><p>呼叫方终结点的网络链接速度（以 bps 为的）。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>呼叫接收器的 IP 地址。 有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleePort</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>呼叫接收器使用的端口。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeSubnet</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>被调用的子网。 有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeInside</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>1表示呼叫接收器位于企业网络内，0表示呼叫接收器位于网络外部。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeMacAddress</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>被呼叫方 Mac 地址。 从<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 中的 MacAddress 表</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeRelayIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>呼叫接收器使用的 A/V 边缘服务的 IP 地址。 有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRelayPort</strong></p></td>
<td><p>int</p></td>
<td><p> </p></td>
<td><p>由呼叫接收器在 A/V 边缘服务上使用的端口。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDev</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>由呼叫接收器使用的捕获设备。 从<a href="lync-server-2013-device-table.md">Lync Server 2013 中的设备表</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDev</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>由呼叫接收器使用的呈现设备。 从<a href="lync-server-2013-device-table.md">Lync Server 2013 中的设备表</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeCaptureDevDriver</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>呼叫接收器的捕获设备的驱动程序。 从<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 中的 DeviceDriver 表</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeRenderDevDriver</strong></p></td>
<td><p>varchar （256）</p></td>
<td><p>外表</p></td>
<td><p>呼叫接收器的呈现设备的驱动程序。 从<a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 中的 DeviceDriver 表</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeNetworkConnectionType</strong></p></td>
<td><p>tinyint</p></td>
<td><p>外表</p></td>
<td><p>指明被呼叫方如何连接到网络。 从<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表中</a>获取值。 用于 WiFi 连接的有线连接 "1" 的典型值为 0;对于以太网连接，请使用3。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeBssid</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>如果使用无线，则被呼叫者的 BSSID。 从<a href="lync-server-2013-macaddress-table.md">Lync Server 2013 中的 MacAddress 表</a>引用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeVPN</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>呼叫接收器的链接;1是虚拟专用网络（VPN），0是非 VPN。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeLinkSpeed</strong></p></td>
<td><p>十进制（18，0）</p></td>
<td><p> </p></td>
<td><p>呼叫接收器终结点的网络链接速度（以 bps 为 bps）。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ConversationalMOS</strong></p></td>
<td><p>十进制（3，2）</p></td>
<td><p> </p></td>
<td><p>音频会话的 Narrowband 对话 MOS （基于两个音频流）。</p></td>
</tr>
<tr class="even">
<td><p><strong>AppliedBandwidthLimit</strong></p></td>
<td><p>int</p></td>
<td></td>
<td><p>这是在给定各种策略设置（TURN、API、SDP、策略服务器等）上应用到给定发送端流的实际带宽。 此操作不会与有效的带宽混淆，因为根据带宽估计，可能会有较低的有效带宽。 这基本上是发送流可以通过带宽估计限制限制的最大带宽。</p></td>
</tr>
<tr class="odd">
<td><p><strong>AppliedBandwidthSourceKey</strong></p></td>
<td><p>smallint</p></td>
<td></td>
<td><p>这是所强加的带宽上限的来源。 它介绍带宽限制的来源（"策略服务器"、"打开服务器"、"模态" 等）。 从<a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013 中的 AppliedBandwidthSource 表</a>引用。</p></td>
</tr>
<tr class="even">
<td><p><strong>呼叫者</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>指示是否收到来自呼叫方的指标;1为 "是"，null 值为 "否"。</p></td>
</tr>
<tr class="odd">
<td><p><strong>被叫方</strong></p></td>
<td><p>bit</p></td>
<td><p> </p></td>
<td><p>指示是否收到来自呼叫接收器的指标;1为 "是"，null 值为 "否"。</p></td>
</tr>
<tr class="even">
<td><p><strong>MidCallReport</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>指示报表是用于会话的一部分还是整个会话。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ClassifiedPoorCall</strong></p></td>
<td><p>bit</p></td>
<td></td>
<td><p>指示呼叫是否分类为不太好的通话（值为1）或正常呼叫（0）。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerConnectivityICE</strong></p></td>
<td><p>tinyInt</p></td>
<td></td>
<td><p>指示呼叫者是否使用 ICE 协议（Internet 连接建立）连接到网络。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeConnectivityICE</strong></p></td>
<td><p>tinyint</p></td>
<td></td>
<td><p>指示呼叫者是否使用 ICE 协议（Internet 连接建立）连接到网络。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>发出呼叫的用户的自身 IP 地址。 在使用 NAT （网络地址转换）的组织中，自身 IP 地址是代理服务器的 IP 地址。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallerWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>发出呼叫的用户所使用的 WiFi 驱动程序的设备说明。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>CallerWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>发出呼叫的用户所使用的 WiFi 驱动程序的版本号。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleReflexiveLocalIPAddr</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>接收呼叫的用户的自身 IP 地址。 在使用 NAT （网络地址转换）的组织中，自身 IP 地址是代理服务器的 IP 地址。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="even">
<td><p><strong>CalleeWiFiDriverDevicesDesc</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>接收呼叫的用户所使用的 WiFi 驱动程序的设备说明。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CalleeWiFiDriverVersion</strong></p></td>
<td><p>int</p></td>
<td><p>外表</p></td>
<td><p>接收呼叫的用户所使用的 WiFi 驱动程序的版本号。</p>
<p>此列已在 Microsoft Lync Server 2013 中引入。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

