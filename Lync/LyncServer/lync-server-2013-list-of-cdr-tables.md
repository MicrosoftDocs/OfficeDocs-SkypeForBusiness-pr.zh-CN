---
title: Lync Server 2013：CDR 表的列表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of CDR tables
ms:assetid: 031843fd-c7ff-4534-9b02-8847aad70807
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398084(v=OCS.15)
ms:contentKeyID: 48183254
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1ac043d144e73d8e1b40ca717e278619e053fdc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829949"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-tables-in-lync-server-2013"></a>Lync Server 2013 中 CDR 表的列表

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-18_

呼叫详细记录 (CDR) 数据库架构由下表组成。

<div>

## <a name="static-tables"></a>静态表


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
<td><p>存储可能的通话优先级列表, 例如紧急情况、紧急、普通、非紧急等。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencejointimethresholds-table.md">Lync Server 2013 中的 ConferenceJoinTimeThresholds 表</a></p></td>
<td><p>存储 "会议加入时间摘要" 报表使用的分类边界。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-deregistertype-table.md">Lync Server 2013 中的 DeRegisterType 表</a></p></td>
<td><p>存储可能的用户取消注册原因&quot;的列表, 例如客户端启动、&quot; &quot;注册过期、&quot; &quot;客户端崩溃&quot;等。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-medialist-table.md">Lync Server 2013 中的 MediaList 表</a></p></td>
<td><p>存储可在数据库中生成条目的媒体类型列表 (例如, IM、音频、视频和文件传输)。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-purgesettings-table.md">Lync Server 2013 中的 PurgeSettings 表</a></p></td>
<td><p>存储用于指定是否将过时的呼叫详细记录 (以及何时) 从 CDR 数据库中自动删除的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-roles-table.md">Lync Server 2013 中的 Roles 表</a></p></td>
<td><p>存储可能的会议角色列表 (例如, 与会者和演示者)。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-sipresponsemetadata-table.md">Lync Server 2013 中的 SIPResponseMetaData 表</a></p></td>
<td><p>存储 SIP 响应代码的列表以及每个代码的分类和定义。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="supporting-tables"></a>支持表


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
<td><p>使用在此数据库中捕获的信息存储呼叫中涉及的每个客户端的客户端 (客户端类型和版本号)。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a></p></td>
<td><p>存储与会议相关的通话中使用的 ConferenceURIs 列表。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表</a></p></td>
<td><p>存储在对等呼叫和电话会议中使用的会话初始协议 (SIP) 内容类型的列表。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-devices-table.md">Lync Server 2013 中的 Devices 表</a></p></td>
<td><p>存储设备列表, 包括制造商、硬件版本和 MAC 地址。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的 Dialogs 表</a></p></td>
<td><p>存储有关数据库中每个会话的对话框 ID 的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a></p></td>
<td><p>存储用于外部呼叫的边缘服务器的列表。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的 Gateways 表</a></p></td>
<td><p>存储用于通过 Internet 协议 (VoIP) 呼叫进行语音通话的网关的列表。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-hardwareversions-table.md">Lync Server 2013 中的 HardwareVersions 表</a></p></td>
<td><p>存储设备 (桌面电话) 的硬件版本的列表。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-manufacturers-table.md">Lync Server 2013 中的 Manufacturers 表</a></p></td>
<td><p>存储设备制造商 (桌面电话) 的列表。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcus-table.md">Lync Server 2013 中的 Mcus 表</a></p></td>
<td><p>存储有关各种 A/V 会议服务器及其 Uri 的信息。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表</a></p></td>
<td><p>存储用于 VoIP 呼叫的中介服务器的列表。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-phones-table.md">Lync Server 2013 中的 Phones 表</a></p></td>
<td><p>存储在已存档或已记录其通话详细信息的 VoIP 呼叫中使用的所有电话号码。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 Pools 表</a></p></td>
<td><p>存储在其上捕获即时消息的池的名称。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 表</a></p></td>
<td><p>存储通话中涉及的服务器的名称。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的 Tenants 表</a></p></td>
<td><p>存储当前部署支持的租户。 企业用户、联合用户、公共 IM 连接用户和匿名用户有一些内置租户。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a></p></td>
<td><p>将用户代理标识符映射到代理的描述性名称。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a></p></td>
<td><p>存储参与此数据库中记录或存档的会话的用户的用户 Uri。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-userstatistics-table.md">Lync Server 2013 中的 UserStatistics 表</a></p></td>
<td><p>存储有关个人用户对系统的使用情况的信息。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-specific-to-conference-cdr-records"></a>特定于会议 CDR 记录的表格


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
<td><p>存储有关已存档或记录其详细信息的所有会议的信息, 包括 ConferenceURI 和开始时间和结束时间。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-conferencesessiondetails-table.md">Lync Server 2013 中的 ConferenceSessionDetails 表</a></p></td>
<td><p>存储有关每个基于 SIP 的会议会话的信息, 包括开始和结束时间、用户 ID、响应代码和每个会话的诊断 ID。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-focusjoinsandleaves-table.md">Lync Server 2013 中的 FocusJoinsAndLeaves 表</a></p></td>
<td><p>存储有关会议加入和保留的信息, 包括用户的角色和客户端版本。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-mcujoinsandleaves-table.md">Lync Server 2013 中的 McuJoinsAndLeaves 表</a></p></td>
<td><p>存储有关会议和用户加入以及休假时间的 A/V 会议服务器的相关信息。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-messages-in-im-conferences"></a>IM 会议中的消息表


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
<td><p>对于每个 IM 会议, 存储每个用户发送的邮件数。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-imreportsummary-table.md">Lync Server 2013 中的 IMReportSummary 表</a></p></td>
<td><p>提供组织中保留的即时消息会话的整体报告。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-peer-to-peer-sessions"></a>对等会话的表


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
<td><p>存储每个对等会话的相关信息, 包括开始和结束时间、用户 ID、响应代码和每个用户的邮件计数。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-filetransfers-table.md">Lync Server 2013 中的 FileTransfers 表</a></p></td>
<td><p>存储有关文件传输会话的信息, 包括文件名和结果 (已接受、已拒绝或已取消)。</p></td>
</tr>
<tr class="odd">
<td><p><a href="lync-server-2013-media-table.md">Lync Server 2013 中的 Media 表</a></p></td>
<td><p>存储对等会话中涉及的不同媒体类型的相关信息。</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-voip-call-details"></a>VoIP 呼叫详细信息表


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
<td><p>对于每个两方 VoIP/PSTN 呼叫, 存储有关呼叫的信息, 例如 VoIP 电话的电话 ID、使用的网关以及哪一方断开连接。 指<a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 表</a>, 用于呼叫开始/结束时间和响应代码。</p>
<div>

> [!NOTE]  
> 如果呼叫中的一方是 VoIP 用户, 或者在呼叫中涉及中介服务器, 则会在此表中创建记录。 <A href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 表</A>中捕获不涉及公共交换电话网络 (PSTN) 电话的 VoIP/voip 呼叫的信息。


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="table-for-e9-1-1-call-auditing"></a>E9 的表-1-1-通话审核


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
<td><p>对于每个紧急呼叫 (如增强的 9-1-1 (E9-1-1) 通话, 存储有关呼叫的位置信息。 指<a href="lync-server-2013-sessiondetails-table.md">Lync Server 2013 中的 SessionDetails 表</a>, 用于呼叫开始/结束时间和响应代码。</p>
<div>

> [!NOTE]  
> 此表仅包含 E9-1-1 调用的位置 blob。 有关通话的其他详细信息, 请参阅 SessionDetails 表。


</div></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="tables-for-troubleshooting"></a>用于疑难解答的表


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
<td><p>存储有关在路由和连接中涉及的 Lync Server 2013 中的各种进程的信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-calltype-table.md">Lync Server 2013 中的 CallType 表</a></p></td>
<td><p>存储有关呼叫类型的信息, 例如 "音频"、"即时消息"、"音频和视频" 和 "应用程序共享"。</p></td>
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
<td><p>存储已发生的错误的相关信息。</p></td>
</tr>
<tr class="even">
<td><p><a href="lync-server-2013-progressreport-table.md">Lync Server 2013 中的 ProgressReport 表</a></p></td>
<td><p>存储有关 Lync Server 2013 进程中涉及的各种步骤的进度报告的信息。</p></td>
</tr>
</tbody>
</table>


以下列表中的表由 Lync Server 内部使用。 本文档中未介绍其详细信息。

</div>

<div>

## <a name="tables-for-internal-use-by-lync-server"></a>Lync Server 供内部使用的表


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
<td><p><strong>前端表</strong></p></td>
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
<td><p><strong>任务表</strong></p></td>
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
<td><p><strong>时区</strong></p></td>
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


</div>

</div>

<span> </span>

</div>

</div>

</div>

