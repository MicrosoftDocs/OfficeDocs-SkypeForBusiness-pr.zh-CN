---
title: 业务服务器 2015年中 Skype CDR 表的列表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: 呼叫详细记录 (CDR) 数据库架构由以下表组成。
ms.openlocfilehash: 977c48b58c5b1d1c0f21fbac07a28ec6efb0bfd6
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213013"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>业务服务器 2015年中 Skype CDR 表的列表
 
呼叫详细记录 (CDR) 数据库架构由以下表组成。 
  
## <a name="static-tables"></a>静态表

|**表格**|**说明**|
|:-----|:-----|
|[CallPriorities 表中的业务服务器 2015 Skype](callpriorities.md) <br/> |存储可能的呼叫优先级，例如紧急、 紧迫、 普通、 非紧迫列表等。  <br/> |
|[ConferenceJoinTimeThresholds 表中的业务服务器 2015 Skype](conferencejointimethresholds.md) <br/> |存储会议加入时间摘要报表所使用的分类边界。  <br/> |
|[DeRegisterType 表中的业务服务器 2015 Skype](deregistertype.md) <br/> |存储可能的用户列表取消注册的原因，例如"客户端启动，""注册过期、"客户端崩溃"等。  <br/> |
|[MediaList 表](medialist.md) <br/> |存储在数据库中可以生成条目的媒体类型的列表 （例如，IM、 音频、 视频和文件传输）。  <br/> |
|[PurgeSettings 表](purgesettings.md) <br/> |指定是否 （以及何时） 的存储信息过时的呼叫将自动从 CDR 数据库中删除详细信息记录。  <br/> |
|[Roles 表](roles.md) <br/> |存储可能的会议角色 （例如，与会者和演示者） 列表。  <br/> |
|[SIPResponseMetaData 表](sipresponsemetadata.md) <br/> |存储 SIP 响应代码的分类和定义的每个代码的列表。  <br/> |
   
## <a name="supporting-tables"></a>支持表

|**表格**|**说明**|
|:-----|:-----|
|[请参阅 ClientVersions table 中的业务服务器 2015 Skype](clientversions.md) <br/> |此数据库中捕获的信息存储呼叫中涉及的每个客户端的客户端 （这两个客户端类型和版本数）。  <br/> |
|[ConferenceUris 表中的业务服务器 2015 Skype](conferenceuris.md) <br/> |存储会议中使用的 Conferenceuri 列表相关的呼叫。  <br/> |
|[ContentTypes 表中的业务服务器 2015 Skype](contenttypes.md) <br/> |存储对等呼叫和会议呼叫中使用的会话初始协议 (SIP) 内容类型的列表。  <br/> |
|[Devices 表中的业务服务器 2015 Skype](devices.md) <br/> |存储设备，包括其制造商、 硬件版本和 MAC 地址的列表。  <br/> |
|[Dialogs 表中的业务服务器 2015 Skype](dialogs.md) <br/> |在数据库中存储每个会话的对话 ID 信息。  <br/> |
|[EdgeServers 表中的业务服务器 2015 Skype](edgeservers.md) <br/> |存储用于外部呼叫的边缘服务器的列表。  <br/> |
|[Gateways 表中的业务服务器 2015 Skype](gateways.md) <br/> |存储用于语音 (Voip) 呼叫的网关的列表。  <br/> |
|[HardwareVersions 表中的业务服务器 2015 Skype](hardwareversions.md) <br/> |存储设备 （桌面电话） 的硬件版本列表。  <br/> |
|[Manufacturers 表中的业务服务器 2015 Skype](manufacturers.md) <br/> |存储设备 （桌面电话） 的制造商列表。  <br/> |
|[Mcus 表中的业务服务器 2015 Skype](mcus.md) <br/> |存储有关各种 A / V 会议服务器和这些用户的 Uri。  <br/> |
|[MediationServers 表](mediationservers.md) <br/> |存储用于 VoIP 呼叫的中介服务器的列表。  <br/> |
|[Phones 表](phones.md) <br/> |存储已存档的或已记录其呼叫详细信息的 VoIP 呼叫中使用的所有电话号码。  <br/> |
|[Pools 表](pools.md) <br/> |存储的 im 消息捕获的池的名称。  <br/> |
|[Servers 表](servers.md) <br/> |存储呼叫涉及的服务器的名称。  <br/> |
|[Tenants 表](tenants.md) <br/> |存储支持当前部署的租户。 那里一些内置租户的企业用户、 联盟用户、 公共 IM 连接用户和匿名用户。  <br/> |
|[UserAgentDef 表](useragentdef.md) <br/> |将用户代理标识符映射到代理的描述性名称。  <br/> |
|[Users 表](users.md) <br/> |此数据库中存储已参与会话的用户的 Uri 记录或存档的用户。  <br/> |
|[UserStatistics 表](userstatistics.md) <br/> |存储有关单个用户的使用情况的系统的信息。  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>表特定于会议 CDR 记录

|**表格**|**说明**|
|:-----|:-----|
|[Conferences 表中的业务服务器 2015 Skype](conferences.md) <br/> |存储有关已存档的或已记录其详细信息，包括 ConferenceURI 以及开始和结束时间的所有会议信息。  <br/> |
|[ConferenceSessionDetails 表中的业务服务器 2015 Skype](conferencesessiondetails-0.md) <br/> |存储有关每个基于 SIP 的会议会话，包括开始和结束时间、 用户 ID、 响应代码和诊断 ID 的每个会话的信息。  <br/> |
|[FocusJoinsAndLeaves 表中的业务服务器 2015 Skype](focusjoinsandleaves.md) <br/> |存储有关会议加入和信息离开，包括用户的角色和客户端版本。  <br/> |
|[McuJoinsAndLeaves 表中的业务服务器 2015 Skype](mcujoinsandleaves.md) <br/> |存储有关 A / V 会议服务器的过程所涉及的会议和用户加入和离开时间。  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>IM 会议中的邮件的表

|**表格**|**说明**|
|:-----|:-----|
|[ConferenceMessageCount 表中的业务服务器 2015 Skype](conferencemessagecount.md) <br/> |每个 IM 会议，存储每个用户发送的消息数。  <br/> |
|[IMReportSummary 表中的业务服务器 2015 Skype](imreportsummary.md) <br/> |在即时消息会话保留在组织中提供的全面报告。  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>对等会话的表

|**表格**|**说明**|
|:-----|:-----|
|[SessionDetails 表](sessiondetails.md) <br/> |存储有关每个对等会话，包括开始和结束时间、 用户 ID、 响应代码和消息计数为每个用户的信息。  <br/> |
|[FileTransfers 表中的业务服务器 2015 Skype](filetransfers-0.md) <br/> |存储有关文件传输会话，包括文件的文件名和结果 （接受、 拒绝还是取消此事件） 的信息。  <br/> |
|[Media 表](media.md) <br/> |存储有关对等会话中涉及的不同媒体类型的信息。  <br/> |
   
## <a name="table-for-voip-call-details"></a>VoIP 呼叫详细信息表

|**表格**|**说明**|
|:-----|:-----|
|[VoipDetails 表](voipdetails-0.md) <br/> |每个两方 VoIP/PSTN 呼叫，存储有关呼叫，如电话 ID 的 VoIP 电话信息、 使用，网关和哪些方断开连接。 [SessionDetails 表](sessiondetails.md)引用的呼叫开始/结束时间和响应代码。 <br/> |
   
> [!NOTE]
> 如果是 VoIP 用户的呼叫的一方或中介服务器已在呼叫中涉及的如果将此表中创建一条记录。 有关不涉及公用电话交换网 (pstn) 电话[SessionDetails 表](sessiondetails.md)中捕获的 VoIP/VoIP 呼叫的信息。 
  
## <a name="table-for-e9-1-1-call-auditing"></a>E9-1-1 呼叫审核表

|**表格**|**说明**|
|:-----|:-----|
|[Locations 表中的业务服务器 2015 Skype](locations.md) <br/> |对于每个紧急呼叫，增强型 9-1-1 (E9-1-1) 呼叫，如存储呼叫的位置信息。 [SessionDetails 表](sessiondetails.md)引用的呼叫开始/结束时间和响应代码。 <br/> |
   
> [!NOTE]
> 此表仅包含位置 blob E9-1-1 呼叫。 指的 SessionDetails 表中的呼叫的其他详细信息。 
  
## <a name="tables-for-troubleshooting"></a>故障排除表

|**表格**|**说明**|
|:-----|:-----|
|[应用程序表中的业务服务器 2015 Skype](application.md) <br/> |存储路由和连接涉及的业务服务器 2015年有关 Skype 内的各种进程的信息。  <br/> |
|[CallType 表中的业务服务器 2015 Skype](calltype.md) <br/> |存储信息类型的呼叫，例如"音频"、"即时消息"、"音频和视频"和"应用程序共享"。  <br/> |
|[ErrorCategory 表中的业务服务器 2015 Skype](errorcategory.md) <br/> |存储每个 Skype 的业务服务器 2015年诊断分类的友好名称。  <br/> |
|[ErrorDef 表中的业务服务器 2015 Skype](errordef.md) <br/> |存储有关错误及其定义的类型信息。  <br/> |
|[ErrorReport 表中的业务服务器 2015 Skype](errorreport.md) <br/> |存储有关发生的错误的信息。  <br/> |
|[ProgressReport 表](progressreport.md) <br/> |存储有关进度报告的业务服务器 2015年过程涉及 Skype 的各个步骤的信息。  <br/> |
   
以下列表中的表由在内部使用 Skype 的业务服务器 2015年。 本文档中未介绍及其详细信息。
  
## <a name="tables-for-internal-use-by-lync-server"></a>Lync Server 供内部使用的表

|**表格**|**说明**|
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
   

