---
title: Skype for Business Server 2015 中的 CDR 表列表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: 呼叫详细记录（CDR）数据库架构由下表组成。
ms.openlocfilehash: a35636333366bbfd55d4337fadfec68af681db6f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815130"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 CDR 表列表
 
呼叫详细记录（CDR）数据库架构由下表组成。 
  
## <a name="static-tables"></a>静态表

|**表格**|**说明**|
|:-----|:-----|
|[Skype for Business Server 2015 中的 CallPriorities 表](callpriorities.md) <br/> |存储可能的通话优先级列表，例如紧急情况、紧急、普通、非紧急等。  <br/> |
|[Skype for Business Server 2015 中的 ConferenceJoinTimeThresholds 表](conferencejointimethresholds.md) <br/> |存储 "会议加入时间摘要" 报表使用的分类边界。  <br/> |
|[Skype for Business Server 2015 中的 DeRegisterType 表](deregistertype.md) <br/> |存储可能的用户取消注册原因的列表，例如 "客户端启动"、"注册已过期"、"客户端崩溃" 等。  <br/> |
|[MediaList 表](medialist.md) <br/> |存储可在数据库中生成条目的媒体类型列表（例如，IM、音频、视频和文件传输）。  <br/> |
|[PurgeSettings 表](purgesettings.md) <br/> |存储用于指定是否将过时的呼叫详细记录（以及何时）从 CDR 数据库中自动删除的信息。  <br/> |
|[Roles 表](roles.md) <br/> |存储可能的会议角色列表（例如，与会者和演示者）。  <br/> |
|[SIPResponseMetaData 表](sipresponsemetadata.md) <br/> |存储 SIP 响应代码的列表以及每个代码的分类和定义。  <br/> |
   
## <a name="supporting-tables"></a>支持表

|**表格**|**说明**|
|:-----|:-----|
|[Skype for Business Server 2015 中的 ClientVersions 表](clientversions.md) <br/> |使用在此数据库中捕获的信息存储呼叫中涉及的每个客户端的客户端（客户端类型和版本号）。  <br/> |
|[Skype for Business Server 2015 中的 ConferenceUris 表](conferenceuris.md) <br/> |存储与会议相关的通话中使用的 ConferenceURIs 列表。  <br/> |
|[Skype for Business Server 2015 中的 ContentTypes 表](contenttypes.md) <br/> |存储在对等呼叫和电话会议中使用的会话初始协议（SIP）内容类型的列表。  <br/> |
|[Skype for Business Server 2015 中的 "设备" 表](devices.md) <br/> |存储设备列表，包括制造商、硬件版本和 MAC 地址。  <br/> |
|[Skype for Business Server 2015 中的对话框表](dialogs.md) <br/> |存储有关数据库中每个会话的对话框 ID 的信息。  <br/> |
|[Skype for Business Server 2015 中的 EdgeServers 表](edgeservers.md) <br/> |存储用于外部呼叫的边缘服务器的列表。  <br/> |
|[Skype for Business Server 2015 中的网关表](gateways.md) <br/> |存储用于通过 Internet 协议（VoIP）呼叫进行语音通话的网关的列表。  <br/> |
|[Skype for Business Server 2015 中的 HardwareVersions 表](hardwareversions.md) <br/> |存储设备（桌面电话）的硬件版本的列表。  <br/> |
|[Skype for Business Server 2015 中的制造商表](manufacturers.md) <br/> |存储设备制造商（桌面电话）的列表。  <br/> |
|[Skype for Business Server 2015 中的 Mcus 表](mcus.md) <br/> |存储有关各种 A/V 会议服务器及其 Uri 的信息。  <br/> |
|[MediationServers 表](mediationservers.md) <br/> |存储用于 VoIP 呼叫的中介服务器的列表。  <br/> |
|[Phones 表](phones.md) <br/> |存储在已存档或已记录其通话详细信息的 VoIP 呼叫中使用的所有电话号码。  <br/> |
|[Pools 表](pools.md) <br/> |存储在其上捕获即时消息的池的名称。  <br/> |
|[Servers 表](servers.md) <br/> |存储通话中涉及的服务器的名称。  <br/> |
|[Tenants 表](tenants.md) <br/> |存储当前部署支持的租户。 企业用户、联合用户、公共 IM 连接用户和匿名用户有一些内置租户。  <br/> |
|[UserAgentDef 表](useragentdef.md) <br/> |将用户代理标识符映射到代理的描述性名称。  <br/> |
|[Users 表](users.md) <br/> |存储参与此数据库中记录或存档的会话的用户的用户 Uri。  <br/> |
|[UserStatistics 表](userstatistics.md) <br/> |存储有关个人用户对系统的使用情况的信息。  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>特定于会议 CDR 记录的表格

|**表格**|**说明**|
|:-----|:-----|
|[Skype for Business Server 2015 中的 "会议" 表](conferences.md) <br/> |存储有关已存档或记录其详细信息的所有会议的信息，包括 ConferenceURI 和开始时间和结束时间。  <br/> |
|[Skype for Business Server 2015 中的 ConferenceSessionDetails 表](conferencesessiondetails-0.md) <br/> |存储有关每个基于 SIP 的会议会话的信息，包括开始和结束时间、用户 ID、响应代码和每个会话的诊断 ID。  <br/> |
|[Skype for Business Server 2015 中的 FocusJoinsAndLeaves 表](focusjoinsandleaves.md) <br/> |存储有关会议加入和保留的信息，包括用户的角色和客户端版本。  <br/> |
|[Skype for Business Server 2015 中的 McuJoinsAndLeaves 表](mcujoinsandleaves.md) <br/> |存储有关会议和用户加入以及休假时间的 A/V 会议服务器的相关信息。  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>IM 会议中的消息表

|**表格**|**说明**|
|:-----|:-----|
|[Skype for Business Server 2015 中的 ConferenceMessageCount 表](conferencemessagecount.md) <br/> |对于每个 IM 会议，存储每个用户发送的邮件数。  <br/> |
|[Skype for Business Server 2015 中的 IMReportSummary 表](imreportsummary.md) <br/> |提供组织中保留的即时消息会话的整体报告。  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>对等会话的表

|**表格**|**说明**|
|:-----|:-----|
|[SessionDetails 表](sessiondetails.md) <br/> |存储每个对等会话的相关信息，包括开始和结束时间、用户 ID、响应代码和每个用户的邮件计数。  <br/> |
|[Skype for Business Server 2015 中的 FileTransfers 表](filetransfers-0.md) <br/> |存储有关文件传输会话的信息，包括文件名和结果（已接受、已拒绝或已取消）。  <br/> |
|[Media 表](media.md) <br/> |存储对等会话中涉及的不同媒体类型的相关信息。  <br/> |
   
## <a name="table-for-voip-call-details"></a>VoIP 呼叫详细信息表

|**表格**|**说明**|
|:-----|:-----|
|[VoipDetails 表](voipdetails-0.md) <br/> |对于每个两方 VoIP/PSTN 呼叫，存储有关呼叫的信息，例如 VoIP 电话的电话 ID、使用的网关以及哪一方断开连接。 指电话开始/结束时间和响应代码的[SessionDetails 表](sessiondetails.md)。 <br/> |
   
> [!NOTE]
> 如果呼叫中的一方是 VoIP 用户，或者在呼叫中涉及中介服务器，则会在此表中创建记录。 有关不涉及公共交换电话网络（PSTN）电话的 VoIP/VoIP 呼叫的信息在[SessionDetails 表](sessiondetails.md)中捕获。 
  
## <a name="table-for-e9-1-1-call-auditing"></a>E9 的表-1-1-通话审核

|**表格**|**说明**|
|:-----|:-----|
|[Skype for Business Server 2015 中的 "位置" 表](locations.md) <br/> |对于每个紧急呼叫（如增强的9-1-1 （E9-1-1）通话，存储有关呼叫的位置信息。 指电话开始/结束时间和响应代码的[SessionDetails 表](sessiondetails.md)。 <br/> |
   
> [!NOTE]
> 此表仅包含 E9-1-1 调用的位置 blob。 有关通话的其他详细信息，请参阅 SessionDetails 表。 
  
## <a name="tables-for-troubleshooting"></a>用于疑难解答的表

|**表格**|**说明**|
|:-----|:-----|
|[Skype for Business Server 2015 中的应用程序表](application.md) <br/> |存储有关在路由和连接中涉及的 Skype for Business Server 2015 中的各种流程的信息。  <br/> |
|[Skype for Business Server 2015 中的 CallType 表](calltype.md) <br/> |存储有关呼叫类型的信息，例如 "音频"、"即时消息"、"音频和视频" 和 "应用程序共享"。  <br/> |
|[Skype for Business Server 2015 中的 ErrorCategory 表](errorcategory.md) <br/> |存储每个 Skype for Business Server 2015 诊断分类的友好名称。  <br/> |
|[Skype for Business Server 2015 中的 ErrorDef 表](errordef.md) <br/> |存储有关错误类型及其定义的信息。  <br/> |
|[Skype for Business Server 2015 中的 ErrorReport 表](errorreport.md) <br/> |存储已发生的错误的相关信息。  <br/> |
|[ProgressReport 表](progressreport.md) <br/> |存储有关 Skype for Business Server 2015 过程中涉及的各种步骤的进度报告的信息。  <br/> |
   
以下列表中的表格由 Skype for Business Server 2015 内部使用。 本文档中未介绍其详细信息。
  
## <a name="tables-for-internal-use-by-lync-server"></a>Lync Server 供内部使用的表

|**表格**|**说明**|
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
   

