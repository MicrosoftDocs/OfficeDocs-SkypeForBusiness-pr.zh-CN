---
title: Lync Server 2013：CDR 表的列表
TOCTitle: CDR 表的列表
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398084(v=OCS.15)
ms:contentKeyID: 49311832
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中 CDR 表的列表

 

_**上一次修改主题：** 2015-03-09_

呼叫详细记录 (CDR) 数据库架构由以下表组成。

## 静态表


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 中的 CallPriorities 表</a></p></td>
<td><p>存储可能的呼叫优先级（例如紧急、紧迫、普通、非紧迫等）列表。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencejointimethresholds-table.md">Lync Server 2013 中的 ConferenceJoinTimeThresholds 表</a></p></td>
<td><p>存储会议加入时间摘要报表所使用的分类边界。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 中的 DeRegisterType 表</a></p></td>
<td><p>存储可能的用户注销原因（例如“客户端已启动”、“注册过期”、“客户端崩溃”等）列表。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialist-table.md">Lync Server 2013 中的 MediaList 表</a></p></td>
<td><p>存储可生成数据库条目的媒体类型（例如，IM、音频、视频和文件传输）列表。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table.md">Lync Server 2013 中的 PurgeSettings 表</a></p></td>
<td><p>存储指定是否（以及何时）从 CDR 数据库自动删除过时的呼叫详细记录的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-roles-table.md">Lync Server 2013 中的 Roles 表</a></p></td>
<td><p>存储可能的会议角色（例如，与会者和演示者）列表。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-sipresponsemetadata-table.md">Lync Server 2013 中的 SIPResponseMetaData 表</a></p></td>
<td><p>存储 SIP 响应代码列表以及每个代码的分类和定义。</p></td>
</tr>
</tbody>
</table>


## 支持表


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a></p></td>
<td><p>存储呼叫中涉及的每个客户端的客户端信息（客户端类型和版本号）以及在此数据库中捕获的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a></p></td>
<td><p>存储用于会议相关呼叫的 ConferenceURI 列表。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表</a></p></td>
<td><p>存储用于点对点呼叫和会议呼叫的会话初始协议 (SIP) 内容类型列表。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devices-table.md">Lync Server 2013 中的 Devices 表</a></p></td>
<td><p>存储设备列表，包括其制造商、硬件版本和 MAC 地址。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表</a></p></td>
<td><p>存储有关数据库中每个会话的对话 ID 的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a></p></td>
<td><p>存储用于外部呼叫的边缘服务器列表。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的 Gateways 表</a></p></td>
<td><p>存储用于 IP 语音 (VoIP) 呼叫的网关列表。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中的 HardwareVersions 表</a></p></td>
<td><p>存储设备（桌面电话）的硬件版本列表。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中的 Manufacturers 表</a></p></td>
<td><p>存储设备（桌面电话）的制造商列表。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-table.md">Lync Server 2013 中的 Mcus 表</a></p></td>
<td><p>存储有关各种 A/V 会议服务器及其 URI 的信息。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表</a></p></td>
<td><p>存储用于 VoIP 呼叫的中介服务器列表。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-phones-table.md">Lync Server 2013 中的 Phones 表</a></p></td>
<td><p>存储已存档的或已记录其呼叫详细信息的 VoIP 呼叫使用的所有电话号码。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 Pools 表</a></p></td>
<td><p>存储在其中捕获 IM 消息的池的名称。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 表</a></p></td>
<td><p>存储呼叫涉及的服务器的名称。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的 Tenants 表</a></p></td>
<td><p>存储当前部署支持的租户。其中包含企业用户、联盟用户、公共 IM 连接用户和匿名用户的某些内置租户。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a></p></td>
<td><p>将用户代理标识符映射到代理的描述性名称。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a></p></td>
<td><p>存储已参与此数据库中记录或存档的会话的用户的用户 URI。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-userstatistics-table.md">Lync Server 2013 中的 UserStatistics 表</a></p></td>
<td><p>存储有关单个用户的系统使用情况的信息。</p></td>
</tr>
</tbody>
</table>


## 特定于会议 CDR 记录的表


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferences-table.md">Lync Server 2013 中的 Conferences 表</a></p></td>
<td><p>存储有关已存档的或已记录其详细信息的所有会议的信息，包括 ConferenceURI 以及开始时间和结束时间。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-table.md">Lync Server 2013 中的 ConferenceSessionDetails 表</a></p></td>
<td><p>存储有关每个基于 SIP 的会议会话的信息，包括每个会话的开始时间和结束时间、用户 ID、响应代码以及诊断 ID。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-focusjoinsandleaves-table.md">Lync Server 2013 中的 FocusJoinsAndLeaves 表</a></p></td>
<td><p>存储有关会议加入和离开的信息，包括用户的角色和客户端版本。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcujoinsandleaves-table.md">Lync Server 2013 中的 McuJoinsAndLeaves 表</a></p></td>
<td><p>存储有关会议涉及的 A/V 会议服务器以及用户加入和离开时间的信息。</p></td>
</tr>
</tbody>
</table>


## IM 会议的消息表


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-conferencemessagecount-table.md">Lync Server 2013 中的 ConferenceMessageCount 表</a></p></td>
<td><p>对于每个 IM 会议，存储每个用户发送的消息数。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-imreportsummary-table.md">Lync Server 2013 中的 IMReportSummary 表</a></p></td>
<td><p>提供有关组织内进行的即时消息会话的全面报告。</p></td>
</tr>
</tbody>
</table>


## 点对点会话表


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 表</a></p></td>
<td><p>存储有关每个点对点会话的信息，包括每个用户的开始时间和结束时间、用户 ID、响应代码以及消息计数。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-filetransfers-table.md">Lync Server 2013 中的 FileTransfers 表</a></p></td>
<td><p>存储有关文件传输会话的信息，包括文件名和结果（接受、拒绝或取消）。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-table.md">Lync Server 2013 中的 Media 表</a></p></td>
<td><p>存储有关点对点会话涉及的不同媒体类型的信息。</p></td>
</tr>
</tbody>
</table>


## VoIP 呼叫详细信息表


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-voipdetails-table.md">Lync Server 2013 中的 VoipDetails 表</a></p></td>
<td><p>对于每个双方 VoIP/PSTN 呼叫，存储有关呼叫的信息，例如 VoIP 电话的电话 ID、使用的网关以及断开连接方。有关呼叫开始/结束时间和响应代码，请参阅 <a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 表</a>。</p>
<div>

> [!NOTE]  
> 如果呼叫的一方是 VoIP 用户，或者呼叫涉及中介服务器，则会在此表中创建一个记录。不涉及公用电话交换网 (PSTN) 电话的 VoIP/VoIP 呼叫信息会被捕获到 <a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 表</a>中。


</div></td>
</tr>
</tbody>
</table>


## E9-1-1 呼叫审核表


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-locations-table.md">Lync Server 2013 中的 Locations 表</a></p></td>
<td><p>对于每个紧急呼叫（例如增强型 9-1-1 (E9-1-1) 呼叫），存储有关该呼叫的位置信息。有关呼叫开始/结束时间和响应代码，请参阅 <a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 表</a>。</p>
<div>

> [!NOTE]  
> 该表仅包含 E9-1-1 呼叫的位置 blob。有关呼叫的其他详细信息，请参阅 SessionDetails 表。


</div></td>
</tr>
</tbody>
</table>


## 故障排除表


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="lync-server-2013-application-table.md">Lync Server 2013 中的 Application 表</a></p></td>
<td><p>存储有关 Lync Server 2013 中路由和连接涉及的各种进程的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-calltype-table.md">Lync Server 2013 中的 CallType 表</a></p></td>
<td><p>存储有关呼叫类型的信息，例如“音频”、“即时消息”、“音频和视频”以及“应用程序共享”。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorcategory-table.md">Lync Server 2013 中的 ErrorCategory 表</a></p></td>
<td><p>存储每个 Microsoft Lync Server 2013 诊断分类的友好名称。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-errordef-table.md">Lync Server 2013 中的 ErrorDef 表</a></p></td>
<td><p>存储有关错误类型及其定义的信息。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表</a></p></td>
<td><p>存储有关发生的错误的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-table.md">Lync Server 2013 中的 ProgressReport 表</a></p></td>
<td><p>存储有关 Lync Server 2013 进程涉及的各个步骤的进程报告的信息。</p></td>
</tr>
</tbody>
</table>


以下列表中的表供 Lync Server 内部使用。本文档不介绍其详细信息。

## 供 Lync Server 内部使用的表


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>表格</th>
<th>说明</th>
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
<td><p><strong>DbErrorMessage</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>FrontEnd 表</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MSMQProcessing 表</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>SummaryTableConfiguration</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Syndicators 表</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>SyndicatorsTenantMap 表</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>Task 表</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>UserStatistics</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>UsageSummary_UQ</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>UsageSummary</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>DaylightSavingYears</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>TimeZoneConfiguration</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>TimeZones</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>FailureSummary_UQ</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>FailureSummary</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="even">
<td><p><strong>ServerSummary</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
<tr class="odd">
<td><p><strong>MsDiagMetaData</strong></p></td>
<td><p>仅供内部使用。</p></td>
</tr>
</tbody>
</table>

