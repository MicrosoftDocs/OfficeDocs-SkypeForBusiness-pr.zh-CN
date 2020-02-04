---
title: Lync Server 2013：QoE 表的列表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of QoE tables
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398236(v=OCS.15)
ms:contentKeyID: 48183512
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c3161415b65c8e85ace7968ab29d86c0d0c5387a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765390"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-qoe-tables-in-lync-server-2013"></a>Lync Server 2013 中 QoE 表的列表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-02_

数据库架构由下表组成。

**支持表**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>表格</strong></th>
<th><strong>说明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingmetricsthreshold-table.md">Lync Server 2013 中的 AppSharingMetricsThreshold 表</a></p></td>
<td><p>存储用于应用程序共享的体验质量指标的最佳值和可接受值。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表</a></p></td>
<td><p>将唯一的编解码器标识符映射到相应的编解码器。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表</a></p></td>
<td><p>将 IP 地址映射到 "体验质量" 数据库中其他位置使用的唯一 IP 地址标识符。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-networkconnectiondetail-table.md">Lync Server 2013 中的 NetworkConnectionDetail 表</a></p></td>
<td><p>将网络连接类型映射到 "体验质量" 数据库中其他位置使用的网络连接标识符。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table-qoe.md">Lync Server 2013 中的 PurgeSettings 表（QoE）</a></p></td>
<td><p>存储用于指定是否会自动从 QoE 数据库中删除过时的体验记录质量的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-traceroute-table.md">Lync Server 2013 中的 TraceRoute 表</a></p></td>
<td><p>存储呼叫的路由信息。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表（QoE）</a></p></td>
<td><p>将用户代理标识符映射到代理的描述性名称。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videometricsthreshold-table.md">Lync Server 2013 中的 VideoMetricsThreshold 表</a></p></td>
<td><p>存储与视频通话一起使用的体验质量指标的最佳和可接受的值。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a></p></td>
<td><p>存储会话初始协议（SIP）用户代理（UA）字符串和音频和视频会话中使用的 UA 类型。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-user-table.md">Lync Server 2013 中的 User 表</a></p></td>
<td><p>存储在音频和视频会话中使用的用户、会议和电话 Uri。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的 Endpoint 表</a></p></td>
<td><p>存储参与音频和视频会话的终结点的 FQDN 计算机名称。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-pool-table.md">Lync Server 2013 中的 Pool 表</a></p></td>
<td><p>存储指标数据所属的池的名称。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-device-table.md">Lync Server 2013 中的 Device 表</a></p></td>
<td><p>存储捕获设备和呈现在音频/视频呼叫中使用的设备。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 中的 DeviceDriver 表</a></p></td>
<td><p>存储用于音频/视频通话的捕获设备和呈现设备的驱动程序。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conference-table.md">Lync Server 2013 中的 Conference 表</a></p></td>
<td><p>存储适用于其他方案的会议方案或 DialogID 的会议 Uri。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 中的 SessionCorrelation 表</a></p></td>
<td><p>存储 PSTN 呼叫的 CorrelationID。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中的 PayloadDescription 表</a></p></td>
<td><p>存储用于音频/视频通话的编解码器。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013 中的 AppliedBandwidthSource 表</a></p></td>
<td><p>存储音频/视频通话中使用的带宽源。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-macaddress-table.md">Lync Server 2013 中的 MacAddress 表</a></p></td>
<td><p>存储参与音频和视频会话的终结点的 MAC 地址。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-dialog-table.md">Lync Server 2013 中的 Dialog 表</a></p></td>
<td><p>存储音频和视频会话的对话框 ID。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-region-table.md">Lync Server 2013 中的 Region 表</a></p></td>
<td><p>存储在 NCS 设置中定义的网络区域。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-usersite-table.md">Lync Server 2013 中的 UserSite 表</a></p></td>
<td><p>存储在 NCS 设置中定义的 network 网站。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-subnet-table.md">Lync Server 2013 中的 Subnet 表</a></p></td>
<td><p>存储在 NCS 设置中定义的子网。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-monitoredregionlink-table.md">Lync Server 2013 中的 MonitoredRegionLink 表</a></p></td>
<td><p>存储在 NCS 设置中定义的区域链接。</p></td>
</tr>
<tr class="odd">
<td><p><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink 表</a></p></td>
<td><p>存储在 NCS 设置中定义的网络网站链接。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-endpointsubnet-table.md">Lync Server 2013 中的 EndpointSubnet 表</a></p></td>
<td><p>存储参与音频和视频会话的终结点的子网。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-table.md">Lync Server 2013 中的 Server  表</a></p></td>
<td><p>存储媒体所经历的服务器的 FQDN 或 IP 地址。</p></td>
</tr>
</tbody>
</table>


**指标数据表**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>表格</strong></th>
<th><strong>说明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingstream-table.md">Lync Server 2013 中的 AppSharingStream 表</a></p></td>
<td><p>存储用于应用程序共享的网络流的体验质量指标。 用于应用程序共享的网络流的体验质量指标。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-table.md">Lync Server 2013 中的 Session 表</a></p></td>
<td><p>存储有关音频或音频/视频会话的整体信息。 会话在两个终结点之间定义为音频或视频 SIP 对话框。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a></p></td>
<td><p>存储有关会话中每个媒体行的信息。 媒体线是一个或多个音频和视频流的集合。 通常，单个媒体线路将有两个流，即音频或视频。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-audiostream-table.md">Lync Server 2013 中的 AudioStream 表</a></p></td>
<td><p>存储媒体行中每个音频流的音频媒体质量指标。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audiosignal-table.md">Lync Server 2013 中的 AudioSignal 表</a></p></td>
<td><p>将音频媒体质量指标存储在媒体行中。 这包括音频回声取消（AEC）和自动增益控制（AGC）指标。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostream-table.md">Lync Server 2013 中的 VideoStream 表</a></p></td>
<td><p>存储媒体行中每个音频流的视频媒体质量指标。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audioclientevent-table.md">Lync Server 2013 中的 AudioClientEvent 表</a></p></td>
<td><p>存储从客户端事件收集的音频媒体质量指标。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videoclientevent-table.md">Lync Server 2013 中的 VideoClientEvent 表</a></p></td>
<td><p>存储从客户端事件收集的视频媒体质量指标。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticData 表</strong></p></td>
<td><p>存储仅供内部使用的诊断数据。</p></td>
</tr>
</tbody>
</table>


**汇总数据表**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>表格</strong></th>
<th><strong>说明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ServerSummary 表</strong></p></td>
<td><p>存储服务器的汇总数据，这些数据仅用于体验质量（QoE）报告。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSummary 表</strong></p></td>
<td><p>存储用户的汇总数据，这些数据仅用于 QoE 报告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallTypeSummary 表</strong></p></td>
<td><p>存储通话类型的汇总数据，这些数据仅用于 QoE 报告。</p></td>
</tr>
</tbody>
</table>


**监视服务器供内部使用的表**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>表格</strong></th>
<th><strong>说明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DbConfigDateTime</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>DbConfigInt</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>前端表</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>任务表</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MetricsThreshold</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>时区</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallSummary 表</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>DeviceCallSumary 表</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>租户表</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>VideoCallSummaryTable</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>ASCallSummaryTable</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

