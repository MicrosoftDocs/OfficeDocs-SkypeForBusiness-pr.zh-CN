---
title: Lync Server 2013：QoE 表的列表
TOCTitle: QoE 表的列表
ms:assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398236(v=OCS.15)
ms:contentKeyID: 49312121
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中 QoE 表的列表

 

_**上一次修改主题：** 2015-03-09_

数据库架构由以下表组成。

**支持表**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>表</strong></th>
<th><strong>说明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingmetricsthreshold-table.md">AppSharingMetricsThreshold 表</a></p></td>
<td><p>存储用于应用程序共享的用户体验质量指标的最佳值和可接受值。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表</a></p></td>
<td><p>将唯一的编解码器标识符映射到其对应的编解码器。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 IPAddress 表</a></p></td>
<td><p>将 IP 地址映射到在用户体验质量数据库中使用的唯一 IP 地址标识符。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-networkconnectiondetail-table.md">NetworkConnectionDetail 表</a></p></td>
<td><p>将网络连接类型映射到在用户体验质量数据库中的其他位置使用的网络连接标识符。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table-qoe.md">PurgeSettings 表 (QoE)</a></p></td>
<td><p>存储指定是否（以及何时）将从 QoE 数据库中自动删除过期的用户体验质量记录的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-traceroute-table.md">TraceRoute 表</a></p></td>
<td><p>存储用于呼叫的路由信息。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef 表 (QoE)</a></p></td>
<td><p>将用户代理标识符映射到代理的描述性名称。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videometricsthreshold-table.md">VideoMetricsThreshold 表</a></p></td>
<td><p>存储用于视频呼叫的用户体验质量指标的最佳值和可接受值。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a></p></td>
<td><p>存储音频和视频会话中使用的会话初始协议 (SIP) 用户代理 (UA) 字符串和 UA 类型。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-user-table.md">Lync Server 2013 中的 User 表</a></p></td>
<td><p>存储音频和视频会话中使用的用户、会议和电话 URI。</p></td>
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
<td><p>存储用于音频/视频呼叫的捕获设备和呈现设备。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devicedriver-table.md">Lync Server 2013 中的 DeviceDriver 表</a></p></td>
<td><p>存储用于音频/视频呼叫的捕获设备和呈现设备的驱动程序。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-conference-table.md">Lync Server 2013 中的 Conference 表</a></p></td>
<td><p>存储会议方案的会议 URI 或其他方案的 DialogID。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 中的 SessionCorrelation 表</a></p></td>
<td><p>存储 PSTN 呼叫的 CorrelationID。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中的 PayloadDescription 表</a></p></td>
<td><p>存储用于音频/视频呼叫的编解码器。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-appliedbandwidthsource-table.md">Lync Server 2013 中的 AppliedBandwidthSource 表</a></p></td>
<td><p>存储用于音频/视频呼叫的带宽源。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-macaddress-table.md">Lync Server 2013 中的 MacAddress 表</a></p></td>
<td><p>存储参与音频和视频会话的终结点的 MAC 地址。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-dialog-table.md">Lync Server 2013 中的 Dialog 表</a></p></td>
<td><p>存储音频和视频会话的对话 ID。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-region-table.md">Lync Server 2013 中的 Region 表</a></p></td>
<td><p>存储 NCS 设置中定义的网络区域。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-usersite-table.md">Lync Server 2013 中的 UserSite 表</a></p></td>
<td><p>存储 NCS 设置中定义的网络站点。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-subnet-table.md">Lync Server 2013 中的 Subnet 表</a></p></td>
<td><p>存储 NCS 设置中定义的子网。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-monitoredregionlink-table.md">Lync Server 2013 中的 MonitoredRegionLink 表</a></p></td>
<td><p>存储 NCS 设置中定义的区域链接。</p></td>
</tr>
<tr class="odd">
<td><p><a href="monitoredusersitelink-table.md">MonitoredUserSiteLink 表</a></p></td>
<td><p>存储 NCS 设置中定义的网络站点链接。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-endpointsubnet-table.md">Lync Server 2013 中的 EndpointSubnet 表</a></p></td>
<td><p>存储参与音频和视频会话的终结点的子网。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-server-table.md">Lync Server 2013 中的 Server 表</a></p></td>
<td><p>存储媒体通过的服务器的 FQDN 或 IP 地址。</p></td>
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
<th><strong>表</strong></th>
<th><strong>说明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-appsharingstream-table.md">AppSharingStream 表</a></p></td>
<td><p>存储用于应用程序共享的网络流的用户体验质量指标。用于应用程序共享的网络流的用户体验质量指标。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-session-table.md">Lync Server 2013 中的 Session 表</a></p></td>
<td><p>存储有关音频或音频/视频会话的总体信息。会话定义为两个终结点之间的音频或视频 SIP 对话。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a></p></td>
<td><p>存储有关会话中每个媒体行的信息。媒体行是一个或多个音频和视频流的集合。通常，一个媒体行具有两个流：音频或视频。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-audiostream-table.md">Lync Server 2013 中的 AudioStream 表</a></p></td>
<td><p>存储媒体行中每个音频流的音频媒体质量指标。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audiosignal-table.md">Lync Server 2013 中的 AudioSignal 表</a></p></td>
<td><p>存储媒体行中的音频媒体质量指标。其中包括回声抑制 (AEC) 和自动增益控制 (AGC) 指标。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videostream-table.md">Lync Server 2013 中的 VideoStream 表</a></p></td>
<td><p>存储媒体行中的每个音频流的视频媒体质量指标。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-audioclientevent-table.md">Lync Server 2013 中的 AudioClientEvent 表</a></p></td>
<td><p>存储从客户端事件中收集的音频媒体质量指标。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-videoclientevent-table.md">Lync Server 2013 中的 VideoClientEvent 表</a></p></td>
<td><p>存储从客户端事件中收集的视频媒体质量指标。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DiagnosticData 表</strong></p></td>
<td><p>存储仅供内部使用的诊断数据。</p></td>
</tr>
</tbody>
</table>


**摘要数据表**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>表</strong></th>
<th><strong>说明</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>ServerSummary 表</strong></p></td>
<td><p>存储服务器的摘要数据，这些数据仅用于用户体验质量 (QoE) 报告。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserSummary 表</strong></p></td>
<td><p>存储用户的摘要数据，这些数据仅用于 QoE 报告。</p></td>
</tr>
<tr class="odd">
<td><p><strong>CallTypeSummary 表</strong></p></td>
<td><p>存储呼叫类型的摘要数据，这些数据仅用于 QoE 报告。</p></td>
</tr>
</tbody>
</table>


**供监控服务器内部使用的表**


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><strong>表</strong></th>
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
<td><p><strong>FrontEnd 表</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>Task 表</strong></p></td>
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
<td><p><strong>TimeZones</strong></p></td>
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
<td><p><strong>Tenant 表</strong></p></td>
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

