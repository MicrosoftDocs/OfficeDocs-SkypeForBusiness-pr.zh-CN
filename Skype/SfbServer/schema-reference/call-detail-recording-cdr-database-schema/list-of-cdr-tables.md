---
title: CDR 中的表列表 Skype 的业务服务器 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: 呼叫详细记录 (CDR) 数据库架构包含，以下各表。
ms.openlocfilehash: 7e224b8170ec078cafaec2fe3cbf4cf9819eba41
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>CDR 中的表列表 Skype 的业务服务器 2015
 
呼叫详细记录 (CDR) 数据库架构包含，以下各表。 
  
## <a name="static-tables"></a>静态表

|**表**|**说明**|
|:-----|:-----|
|[在业务服务器 2015年的 Skype 的 CallPriorities 表](callpriorities.md) <br/> |存储可能调用优先级，紧急情况下，紧急的、 普通的、 非紧急，例如列表和详细信息。  <br/> |
|[在业务服务器 2015年的 Skype 的 ConferenceJoinTimeThresholds 表](conferencejointimethresholds.md) <br/> |存储分类边界使用会议加入时间摘要报告。  <br/> |
|[在业务服务器 2015年的 Skype 的 DeRegisterType 表](deregistertype.md) <br/> |列表中可能的用户取消注册原因，例如"客户端开始，"商店"注册已过期，""客户端崩溃，"等等。  <br/> |
|[MediaList 表](medialist.md) <br/> |存储的媒体类型，可以在数据库中生成条目列表 （例如，IM，音频，视频和文件传输）。  <br/> |
|[PurgeSettings 表](purgesettings.md) <br/> |如果 （并且当） 指定的存储信息过时的明细数据记录将自动为从数据库中删除 CDR 的调用。  <br/> |
|[角色表](roles.md) <br/> |存储可能会议角色 （例如，与会者和演示者） 的列表。  <br/> |
|[SIPResponseMetaData 表](sipresponsemetadata.md) <br/> |SIP 响应代码的分类和定义，这些代码的每个列表进行存储。  <br/> |
   
## <a name="supporting-tables"></a>支持表

|**表**|**说明**|
|:-----|:-----|
|[在业务服务器 2015年的 Skype 的 ClientVersions 表](clientversions.md) <br/> |在此数据库中捕获的信息存储在调用所涉及的每个客户端的客户端 （这两种客户端类型和版本编号）。  <br/> |
|[在业务服务器 2015年的 Skype 的 ConferenceUris 表](conferenceuris.md) <br/> |在会议中使用的 ConferenceURIs 的列表存储相关的调用。  <br/> |
|[在业务服务器 2015年的 Skype 的内容类型表](contenttypes.md) <br/> |在对等的电话和电话会议中存储会话启动协议 (SIP) 所使用的内容类型的列表。  <br/> |
|[在 Skype 的业务服务器 2015年设备表](devices.md) <br/> |存储设备列表，包括制造商、 硬件版本和 MAC 地址。  <br/> |
|[在业务服务器 2015年的 Skype 的对话表](dialogs.md) <br/> |在数据库中存储有关对话框 ID 为每个会话的信息。  <br/> |
|[在业务服务器 2015年的 Skype 的 EdgeServers 表](edgeservers.md) <br/> |存储用于外部调用的边缘服务器的列表。  <br/> |
|[在业务服务器 2015年的 Skype 的网关表](gateways.md) <br/> |存储用于语音 (Voip) 电话上的网关列表。  <br/> |
|[在业务服务器 2015年的 Skype 的 HardwareVersions 表](hardwareversions.md) <br/> |存储设备 （桌面电话） 的硬件版本的列表。  <br/> |
|[在业务服务器 2015年的 Skype 的制造商表](manufacturers.md) <br/> |存储设备 （桌面电话） 的制造商的列表。  <br/> |
|[在业务服务器 2015年的 Skype 的 Mcu 表](mcus.md) <br/> |存储信息的各种 A / V 会议服务器和其 Uri。  <br/> |
|[MediationServers 表](mediationservers.md) <br/> |存储用于 VoIP 电话的中介服务器的列表。  <br/> |
|[电话表](phones.md) <br/> |存储使用 VoIP 电话的存档或其呼叫的详细记录中的所有电话号码。  <br/> |
|[池表](pools.md) <br/> |存储的池的 IM 消息捕获的名称。  <br/> |
|[服务器表](servers.md) <br/> |存储在调用中涉及的服务器的名称。  <br/> |
|[租户表](tenants.md) <br/> |存储当前部署支持承租人。 那里一些企业用户、 联合用户、 公共 IM 连接用户和匿名用户生成中的承租人。  <br/> |
|[UserAgentDef 表](useragentdef.md) <br/> |将用户代理标识符映射到代理的描述性名称。  <br/> |
|[用户表](users.md) <br/> |在此数据库中存储的用户 Uri 的用户的会话中参与过记录或存档。  <br/> |
|[UserStatistics 表](userstatistics.md) <br/> |存储系统的单个用户的使用情况有关的信息。  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>表特有的 CDR 会议记录

|**表**|**说明**|
|:-----|:-----|
|[在业务服务器 2015年的 Skype 会议表](conferences.md) <br/> |存储的所有会议，进行存档或记录的详细信息，包括 ConferenceURI，以及开始和结束时间的信息。  <br/> |
|[在业务服务器 2015年的 Skype 的 ConferenceSessionDetails 表](conferencesessiondetails-0.md) <br/> |存储有关每个基于 SIP 的会议会话，包括为每个会话的开始和结束时间、 用户 ID、 响应代码和诊断 ID 信息。  <br/> |
|[在业务服务器 2015年的 Skype 的 FocusJoinsAndLeaves 表](focusjoinsandleaves.md) <br/> |存储有关大会的信息加入和离开，包括用户的角色和客户端版本。  <br/> |
|[在业务服务器 2015年的 Skype 的 McuJoinsAndLeaves 表](mcujoinsandleaves.md) <br/> |存储有关 A / V 会议服务器涉及会议和用户的加入和离开时间。  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>在 IM 会议消息的表

|**表**|**说明**|
|:-----|:-----|
|[在业务服务器 2015年的 Skype 的 ConferenceMessageCount 表](conferencemessagecount.md) <br/> |每个即时消息的会议，将存储每个用户发送的邮件数。  <br/> |
|[在业务服务器 2015年的 Skype 的 IMReportSummary 表](imreportsummary.md) <br/> |提供即时消息会话保存在一个组织的总体报告。  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>对于对等会话表

|**表**|**说明**|
|:-----|:-----|
|[SessionDetails 表](sessiondetails.md) <br/> |存储有关每个对等会话，包括开始和结束时间、 用户 ID、 响应代码，以及为每个用户的邮件计数信息。  <br/> |
|[在业务服务器 2015年的 Skype 的 FileTransfers 表](filetransfers-0.md) <br/> |存储信息文件传输会话，包括文件名称和结果 （接受、 拒绝或取消）。  <br/> |
|[媒体表](media.md) <br/> |存储有关对等会话中涉及的不同的媒体类型信息。  <br/> |
   
## <a name="table-for-voip-call-details"></a>VoIP 呼叫详细信息表

|**表**|**说明**|
|:-----|:-----|
|[VoipDetails 表](voipdetails-0.md) <br/> |对于每个两方 VoIP/PSTN 呼叫，存储关于调用，如电话 ID 的 VoIP 电话的信息、 使用，网关和哪些当事方已断开连接。 调用的开始/结束时间和响应代码是指[SessionDetails 表](sessiondetails.md)。 <br/> |
   
> [!NOTE]
> 如果呼叫的一方是 VoIP 用户或者如果在调用中涉及中介服务器，将在此表中创建记录。 有关不涉及公用交换的电话网络 (PSTN) 电话[SessionDetails 表](sessiondetails.md)中被捕获的 VoIP/VoIP 电话的信息。 
  
## <a name="table-for-e9-1-1-call-auditing"></a>E9-1-1 调用审核表

|**表**|**说明**|
|:-----|:-----|
|[在业务服务器 2015年的 Skype 的位置表](locations.md) <br/> |每次紧急调用，如增强 9-1-1 (E9-1-1) 调用将存储关于调用的位置信息。 调用的开始/结束时间和响应代码是指[SessionDetails 表](sessiondetails.md)。 <br/> |
   
> [!NOTE]
> 此表仅包含 E9-1-1 呼叫位置 blob。 指的是关于调用的其他详细信息的 SessionDetails 表。 
  
## <a name="tables-for-troubleshooting"></a>表的疑难解答

|**表**|**说明**|
|:-----|:-----|
|[在业务服务器 2015年的 Skype 应用程序表](application.md) <br/> |将为所涉及的业务服务器 2015 Skype 内各种进程的信息存储在路由和连接。  <br/> |
|[在业务服务器 2015年的 Skype 的 CallType 表](calltype.md) <br/> |存储的信息类型的呼叫，例如，"音频"、"即时消息"、"音频和视频"和"应用程序共享"。  <br/> |
|[在业务服务器 2015年的 Skype 的 ErrorCategory 表](errorcategory.md) <br/> |存储每个 Skype 业务服务器 2015年诊断分类的友好名称。  <br/> |
|[在业务服务器 2015年的 Skype 的 ErrorDef 表](errordef.md) <br/> |存储有关错误及其定义的类型的信息。  <br/> |
|[在业务服务器 2015年的 Skype 的 ErrorReport 表](errorreport.md) <br/> |存储有关已发生的错误的信息。  <br/> |
|[ProgressReport 表](progressreport.md) <br/> |存储在 Skype 业务服务器 2015年进程所涉及的各种步骤的进度报告的有关信息。  <br/> |
   
下面的列表中的表用于内部通过 Skype 业务服务器 2015年。 本文档中未介绍它们的详细信息。
  
## <a name="tables-for-internal-use-by-lync-server"></a>供内部使用 Lync Server 表

|**表**|**说明**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |仅供内部使用。  <br/> |
|**DbConfigInt** <br/> |仅供内部使用。  <br/> |
|**DbErrorMessage** <br/> |仅供内部使用。  <br/> |
|**前端表** <br/> |仅供内部使用。  <br/> |
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
|**时区** <br/> |仅供内部使用。  <br/> |
|**FailureSummary_UQ** <br/> |仅供内部使用。  <br/> |
|**FailureSummary** <br/> |仅供内部使用。  <br/> |
|**ServerSummary** <br/> |仅供内部使用。  <br/> |
|**MsDiagMetaData** <br/> |仅供内部使用。  <br/> |
   

