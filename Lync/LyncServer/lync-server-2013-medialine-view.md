---
title: Lync Server 2013： MediaLine 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: MediaLine view
ms:assetid: 132eca13-8913-4218-9eff-4960ced8c3dc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687972(v=OCS.15)
ms:contentKeyID: 49733560
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aebd16d8bd2efaf8deeb6752deeb199411ab125
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763000"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="medialine-view-in-lync-server-2013"></a>Lync Server 2013 中的 MediaLine 视图

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-03_

MediaLine 视图存储有关数据库中每个媒体行的信息。 一个音频会话通常包含一个音频媒体行。 一个音频和视频（A/V）会话通常包含一个音频媒体线和一个视频媒体行;但是，如果使用了会议设备或使用了库视图，则会话可能包含两个视频媒体线。 此视图已在 Microsoft Lync Server 2013 中引入。


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
<th>更多信息</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ConferenceDateTime</p></td>
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
<td><p>安全性</p></td>
<td><p>tinyint</p></td>
<td><p>安全配置文件正在使用。 0为 NONE，1为 SRTP，2为 V1。</p></td>
</tr>
<tr class="odd">
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>传输类型。 0是 UDP，1是 TCP。</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>呼叫方的 IP 地址。 这可以是 IPv4 地址或 IPv6 地址。</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>呼叫方使用的端口。</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>bit</p></td>
<td><p>指示呼叫者是否在组织网络内。 1表示呼叫方位于企业网络内。 0表示呼叫方位于网络外部。</p></td>
</tr>
<tr class="odd">
<td><p>CallerMacAddress</p></td>
<td><p>varchar （256）</p></td>
<td><p>呼叫方使用的网络接口的 MAC 地址。</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>呼叫方使用的 A/V 边缘服务的 IP 地址。 有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>由呼叫方使用的 A/V 边缘服务使用的端口。</p></td>
</tr>
<tr class="even">
<td><p>CallerReflexiveIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>由 A/V 边缘服务报告的呼叫者的 IP 地址。 如果客户端位于 NAT 后面，则该地址可能与 CallerIPAddr 不同，例如。</p></td>
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
<td><p>CallerRenderDevDriver</p></td>
<td><p>varchar （256）</p></td>
<td><p>呼叫方的呈现设备驱动程序名称。</p></td>
</tr>
<tr class="odd">
<td><p>CallerWifiDriverDeviceDesc</p></td>
<td><p>varchar （256</p></td>
<td><p>呼叫方的 Wifi 驱动程序说明。</p></td>
</tr>
<tr class="even">
<td><p>CallerWifiDriverVersion</p></td>
<td><p>varchar （256）</p></td>
<td><p>呼叫方的 Wifi 驱动程序版本。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar （256）</p></td>
<td><p>呼叫方网络连接的详细信息。 有关详细信息，请参阅<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CallerBssid</p></td>
<td><p>varchar （256）</p></td>
<td><p>呼叫方 WiFi 连接使用的基本服务设置标识符。</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>bit</p></td>
<td><p>指示呼叫者是否通过虚拟专用网络连接。 1是虚拟专用网络（VPN），0是非 VPN。</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>被呼叫方的 IP 地址。 这可以是 IPv4 地址或 IPv6 地址。</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>被呼叫方使用的端口。</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>bit</p></td>
<td><p>指示被调用方是否位于企业网络内。 1表示被呼叫方位于企业网络内，0表示被呼叫方位于网络外部。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeMacAddress</p></td>
<td><p>varchar （256）</p></td>
<td><p>被呼叫方使用的网络接口的 MAC 地址。</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>被呼叫方使用的 A/V 边缘服务的 IP 地址。 有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>用于由被呼叫方使用的 A/V 边缘服务的端口。</p></td>
</tr>
<tr class="even">
<td><p>CalleeReflexiveIPAddr</p></td>
<td><p>var （50）</p></td>
<td><p>由 A/V 边缘服务报告的被呼叫方的 IP 地址。 如果客户端位于 NAT 后面，则该地址可能与 CalleeIPAddr 不同，例如。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>var （50）</p></td>
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
<td><p>CalleeWifiDriverDeviceDesc</p></td>
<td><p>varchar （256）</p></td>
<td><p>被呼叫方的 Wifi 驱动程序说明。</p></td>
</tr>
<tr class="even">
<td><p>CalleeWifiDriverVersion</p></td>
<td><p>varchar （256</p></td>
<td><p>被呼叫方的 Wifi 驱动程序版本。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionDetail</p></td>
<td><p>varchar （256）</p></td>
<td><p>被呼叫方的网络连接的详细信息。 有关详细信息，请参阅<a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表</a>。</p></td>
</tr>
<tr class="even">
<td><p>CalleeBssid</p></td>
<td><p>varchar （256）</p></td>
<td><p>被呼叫方的 WiFi 连接使用的基本服务设置标识符。</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>bit</p></td>
<td><p>指示被调用方是否通过虚拟专用网络进行连接。 1是虚拟专用网络（VPN），0是非 VPN。</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>十进制（3，2）</p></td>
<td><p>音频会话的 Narrowband 对话 MOS （基于两个音频流）。</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>这是在给定各种策略设置（TURN、API、SDP、策略服务器等）上应用到给定发送端流的实际带宽。 不要将这一点与有效的带宽混淆，因为它可以根据带宽估计值降低较低的有效带宽。 这基本上是发送流可以通过带宽估计限制限制的最大带宽。</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthSource</p></td>
<td><p>varchar （256）</p></td>
<td><p>所强加带宽上限的来源。 它介绍带宽限制的来源（例如，"策略服务器"、"转换服务器" 或 "模态"）。</p></td>
</tr>
<tr class="odd">
<td><p>呼叫者</p></td>
<td><p>bit</p></td>
<td><p>指示是否收到来自呼叫方的指标;1为 "是"，0为 "否"。</p></td>
</tr>
<tr class="even">
<td><p>被叫方</p></td>
<td><p>bit</p></td>
<td><p>指示是否收到来自呼叫接收器的指标;1为 "是"，0为 "否"。</p></td>
</tr>
<tr class="odd">
<td><p>MidCallReport</p></td>
<td><p>bit</p></td>
<td><p>指示报表是用于部分通话还是完整通话。</p></td>
</tr>
<tr class="even">
<td><p>ClassifiedPoorCall</p></td>
<td><p>bit</p></td>
<td><p>指示呼叫是否分类为差通话（1）或正常呼叫（0）。</p></td>
</tr>
<tr class="odd">
<td><p>CallerConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>指示呼叫者是否使用 ICE 协议（Internet 连接建立）连接到网络。</p></td>
</tr>
<tr class="even">
<td><p>CalleeConnectivityICE</p></td>
<td><p>tinyint</p></td>
<td><p>指示用户是否使用 ICE 协议（Internet 连接建立）连接到网络。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

