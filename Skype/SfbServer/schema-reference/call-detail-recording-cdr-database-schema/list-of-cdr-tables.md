---
title: Skype for Business Server 2015 中的 CDR 表列表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: 呼叫详细信息记录 (CDR) 数据库架构由以下表组成。
ms.openlocfilehash: 7bd76a4cf374e72582c585908309605c4845454e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827592"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 CDR 表列表
 
呼叫详细信息记录 (CDR) 数据库架构由以下表组成。 
  
## <a name="static-tables"></a>静态表

|**Table**|**说明**|
|:-----|:-----|
|[Skype for Business Server 2015 中的 CallPriorities 表](callpriorities.md) <br/> |存储可能的呼叫优先级（例如紧急、紧迫、普通、非紧迫等）列表。  <br/> |
|[Skype for Business Server 2015 中的 ConferenceJoinTimeThresholds 表](conferencejointimethresholds.md) <br/> |存储会议加入时间摘要报表所使用的分类边界。  <br/> |
|[Skype for Business Server 2015 中的 DeRegisterType 表](deregistertype.md) <br/> |存储可能的用户注销原因（例如“客户端已启动”、“注册过期”、“客户端崩溃”等）列表。  <br/> |
|[MediaList 表](medialist.md) <br/> |存储可生成数据库条目的媒体类型（例如，IM、音频、视频和文件传输）列表。  <br/> |
|[PurgeSettings 表](purgesettings.md) <br/> |存储指定是否（以及何时）从 CDR 数据库自动删除过时的呼叫详细信息记录的信息。  <br/> |
|[Roles 表](roles.md) <br/> |存储可能的会议角色（例如，与会者和演示者）列表。  <br/> |
|[SIPResponseMetaData 表](sipresponsemetadata.md) <br/> |存储 SIP 响应代码列表以及每个代码的分类和定义。  <br/> |
   
## <a name="supporting-tables"></a>支持表

|**Table**|**说明**|
|:-----|:-----|
|[Skype for Business Server 2015 中的 ClientVersions 表](clientversions.md) <br/> |存储呼叫中涉及的每个客户端的客户端信息（客户端类型和版本号）以及在此数据库中捕获的信息。  <br/> |
|[Skype for Business Server 2015 中的 ConferenceUris 表](conferenceuris.md) <br/> |存储用于会议相关呼叫的 ConferenceURI 列表。  <br/> |
|[Skype for Business Server 2015 中的 ContentTypes 表](contenttypes.md) <br/> |存储用于点对点呼叫和会议呼叫的会话初始协议 (SIP) 内容类型列表。  <br/> |
|[Skype for Business Server 2015 中的 Devices 表](devices.md) <br/> |存储设备列表，包括其制造商、硬件版本和 MAC 地址。  <br/> |
|[Skype for Business Server 2015 中的 Dialogs 表](dialogs.md) <br/> |存储有关数据库中每个会话的对话 ID 的信息。  <br/> |
|[Skype for Business Server 2015 中的 EdgeServers 表](edgeservers.md) <br/> |存储用于外部呼叫的边缘服务器列表。  <br/> |
|[Skype for Business Server 2015 中的 Gateways 表](gateways.md) <br/> |存储用于 IP 语音 (VoIP) 呼叫的网关列表。  <br/> |
|[Skype for Business Server 2015 中的 HardwareVersions 表](hardwareversions.md) <br/> |存储设备（桌面电话）的硬件版本列表。  <br/> |
|[Skype for Business Server 2015 中的 Manufacturers 表](manufacturers.md) <br/> |存储设备（桌面电话）的制造商列表。  <br/> |
|[Skype for Business Server 2015 中的 Mcus 表](mcus.md) <br/> |存储有关各种 A/V 会议服务器及其 URI 的信息。  <br/> |
|[MediationServers 表](mediationservers.md) <br/> |存储用于 VoIP 呼叫的中介服务器列表。  <br/> |
|[Phones 表](phones.md) <br/> |存储已存档的或已记录其呼叫详细信息的 VoIP 呼叫使用的所有电话号码。  <br/> |
|[Pools 表](pools.md) <br/> |存储在其中捕获 IM 消息的池的名称。  <br/> |
|[Servers 表](servers.md) <br/> |存储呼叫涉及的服务器的名称。  <br/> |
|[Tenants 表](tenants.md) <br/> |存储当前部署支持的租户。 其中包含企业用户、联盟用户、公共 IM 连接用户和匿名用户的某些内置租户。  <br/> |
|[UserAgentDef 表](useragentdef.md) <br/> |将用户代理标识符映射到代理的描述性名称。  <br/> |
|[Users 表](users.md) <br/> |存储已参与此数据库中记录或存档的会话的用户的用户 URI。  <br/> |
|[UserStatistics 表](userstatistics.md) <br/> |存储有关单个用户对系统使用情况的信息。  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>特定于会议 CDR 记录的表

|**Table**|**说明**|
|:-----|:-----|
|[Skype for Business Server 2015 中的 Conferences 表](conferences.md) <br/> |存储有关已存档的或已记录其详细信息的所有会议的信息，包括 ConferenceURI 以及开始时间和结束时间。  <br/> |
|[Skype for Business Server 2015 中的 ConferenceSessionDetails 表](conferencesessiondetails-0.md) <br/> |存储有关每个基于 SIP 的会议会话的信息，包括每个会话的开始时间和结束时间、用户 ID、响应代码以及诊断 ID。  <br/> |
|[Skype for Business Server 2015 中的 FocusJoinsAndLeaves 表](focusjoinsandleaves.md) <br/> |存储有关会议加入和离开的信息，包括用户的角色和客户端版本。  <br/> |
|[Skype for Business Server 2015 中的 McuJoinsAndLeaves 表](mcujoinsandleaves.md) <br/> |存储有关会议涉及的 A/V 会议服务器以及用户加入和离开时间的信息。  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>IM 会议的消息表

|**Table**|**说明**|
|:-----|:-----|
|[Skype for Business Server 2015 中的 ConferenceMessageCount 表](conferencemessagecount.md) <br/> |对于每个 IM 会议，存储每个用户发送的消息数。  <br/> |
|[Skype for Business Server 2015 中的 IMReportSummary 表](imreportsummary.md) <br/> |提供有关组织内进行的即时消息会话的全面报告。  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>点对点会话表

|**Table**|**说明**|
|:-----|:-----|
|[SessionDetails 表](sessiondetails.md) <br/> |存储有关每个点对点会话的信息，包括每个用户的开始时间和结束时间、用户 ID、响应代码以及消息计数。  <br/> |
|[Skype for Business Server 2015 中的 FileTransfers 表](filetransfers-0.md) <br/> |存储有关文件传输会话的信息，包括文件名和结果（接受、拒绝或取消）。  <br/> |
|[Media 表](media.md) <br/> |存储有关点对点会话涉及的不同媒体类型的信息。  <br/> |
   
## <a name="table-for-voip-call-details"></a>VoIP 呼叫详细信息表

|**Table**|**说明**|
|:-----|:-----|
|[VoipDetails 表](voipdetails-0.md) <br/> |对于每个双方 VoIP/PSTN 呼叫，存储有关呼叫的信息，例如 VoIP 电话的电话 ID、使用的网关以及断开连接方。 有关呼叫开始/结束时间以及响应代码，请参阅 [SessionDetails](sessiondetails.md) 表。 <br/> |
   
> [!NOTE]
> 如果呼叫的一方是 VoIP 用户，或者呼叫涉及中介服务器，则会在此表中创建一个记录。 [SessionDetails](sessiondetails.md)表中捕获了与 PSTN 电话 (电话交换网) VoIP/VoIP 呼叫的信息。 
  
## <a name="table-for-e9-1-1-call-auditing"></a>E9-1-1 呼叫审核表

|**Table**|**说明**|
|:-----|:-----|
|[Skype for Business Server 2015 中的位置表](locations.md) <br/> |对于每个紧急呼叫（例如增强型 9-1-1 (E9-1-1) 呼叫），存储有关该呼叫的位置信息。 有关呼叫开始/结束时间以及响应代码，请参阅 [SessionDetails](sessiondetails.md) 表。 <br/> |
   
> [!NOTE]
> 该表仅包含 E9-1-1 呼叫的位置 blob。有关呼叫的其他详细信息，请参阅 SessionDetails 表。 
  
## <a name="tables-for-troubleshooting"></a>故障排除表

|**Table**|**说明**|
|:-----|:-----|
|[Skype for Business Server 2015 中的 Application 表](application.md) <br/> |存储有关 Skype for Business Server 2015 中路由和连接所涉及的各种进程的信息。  <br/> |
|[Skype for Business Server 2015 中的 CallType 表](calltype.md) <br/> |存储有关呼叫类型的信息，例如"音频"、"即时消息"、"音频和视频"和"应用程序共享"。  <br/> |
|[Skype for Business Server 2015 中的 ErrorCategory 表](errorcategory.md) <br/> |存储每个 Skype for Business Server 2015 诊断分类的友好名称。  <br/> |
|[Skype for Business Server 2015 中的 ErrorDef 表](errordef.md) <br/> |存储有关错误类型及其定义的信息。  <br/> |
|[Skype for Business Server 2015 中的 ErrorReport 表](errorreport.md) <br/> |存储有关发生的错误的信息。  <br/> |
|[ProgressReport 表](progressreport.md) <br/> |存储有关 Skype for Business Server 2015 进程中涉及的各个步骤的进度报告的信息。  <br/> |
   
以下列表中的表供 Skype for Business Server 2015 内部使用。 本文档不介绍其详细信息。
  
## <a name="tables-for-internal-use-by-lync-server"></a>供 Lync Server 内部使用的表

|**Table**|**说明**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |仅供内部使用。  <br/> |
|**DbConfigInt** <br/> |仅供内部使用。  <br/> |
|**DbErrorMessage** <br/> |仅供内部使用。  <br/> |
|**FrontEnd 表** <br/> |仅供内部使用。  <br/> |
|**MSMQProcessing 表** <br/> |仅供内部使用。  <br/> |
|**SummaryTableConfiguration** <br/> |仅供内部使用。  <br/> |
|**Syndicators 表** <br/> |仅供内部使用。  <br/> |
|**SyndicatorsTenantMap 表** <br/> |仅供内部使用。  <br/> |
|**任务表** <br/> |仅供内部使用。  <br/> |
|**UserStatistics** <br/> |仅供内部使用。  <br/> |
|**UsageSummary_UQ** <br/> |仅供内部使用。  <br/> |
|**UsageSummary** <br/> |仅供内部使用。  <br/> |
|**DaylightSavingYears** <br/> |仅供内部使用。  <br/> |
|**TimeZoneConfiguration** <br/> |仅供内部使用。  <br/> |
|**TimeZones** <br/> |仅供内部使用。  <br/> |
|**FailureSummary_UQ** <br/> |仅供内部使用。  <br/> |
|**FailureSummary** <br/> |仅供内部使用。  <br/> |
|**ServerSummary** <br/> |仅供内部使用。  <br/> |
|**MsDiagMetaData** <br/> |仅供内部使用。  <br/> |
   

