---
title: QoE 表的列表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: 数据库架构由以下表组成。
ms.openlocfilehash: c3ab045e67f38082910f5a2870d4e8c0c8e595b4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212219"
---
# <a name="list-of-qoe-tables"></a>QoE 表的列表
 
数据库架构由以下表组成。 
  
**支持表**

|**表格**|**说明**|
|:-----|:-----|
|[AppSharingMetricsThreshold 表](appsharingmetricsthreshold.md) <br/> |存储用于应用程序共享的用户体验质量指标的最佳和可接受值。  <br/> |
|[CodecDescription 表](codecdescription.md) <br/> |将唯一的编解码器标识符映射到其对应的编解码器。  <br/> |
|[IPAddress 表](ipaddress.md) <br/> |将 IP 地址映射到其他位置的用户体验质量数据库中使用的唯一的 IP 地址标识符。  <br/> |
|[NetworkConnectionDetail 表](networkconnectiondetail.md) <br/> |将网络连接类型映射到其他位置的用户体验质量数据库中使用的网络连接标识符。  <br/> |
|[PurgeSettings 表 (QoE)](purgesettings-qoe.md) <br/> |指定是否 （以及何时） 的存储信息过时的用户体验质量将自动从 QoE 数据库中删除记录。  <br/> |
|[TraceRoute 表](traceroute.md) <br/> |存储路由呼叫的信息。  <br/> |
|[UserAgentDef 表 (QoE)](useragentdef-qoe.md) <br/> |将用户代理标识符映射到代理的描述性名称。  <br/> |
|[VideoMetricsThreshold 表](videometricsthreshold.md) <br/> |存储用于视频呼叫的用户体验质量指标的最佳和可接受值。  <br/> |
|[UserAgent 表](useragent.md) <br/> |存储会话初始协议 (SIP) 用户代理 (UA) 字符串和 UA 类型音频和视频会话中使用。  <br/> |
|[User 表](user-0.md) <br/> |存储用户、 会议和电话 Uri 音频和视频会话中使用。  <br/> |
|[Endpoint 表](endpoint.md) <br/> |存储参与音频和视频会话的终结点的 FQDN 计算机名称。  <br/> |
|[Pool 表](pool.md) <br/> |存储指标数据所属的池的名称。  <br/> |
|[Device 表](device.md) <br/> |存储捕获设备和呈现设备用于音频/视频呼叫。  <br/> |
|[DeviceDriver 表](devicedriver.md) <br/> |用于捕获设备和呈现设备的音频/视频呼叫中使用的存储驱动程序。  <br/> |
|[Conference 表](conference.md) <br/> |存储会议方案其他方案的 dialogid 的会议 Uri。  <br/> |
|[SessionCorrelation 表](sessioncorrelation.md) <br/> |存储 PSTN 呼叫的 CorrelationID。  <br/> |
|[PayloadDescription 表](payloaddescription.md) <br/> |存储用于音频/视频呼叫的编解码器。  <br/> |
|[AppliedBandwidthSource 表](appliedbandwidthsource.md) <br/> |存储用于音频/视频呼叫的带宽源。  <br/> |
|[MacAddress 表](macaddress.md) <br/> |存储参与音频和视频会话的终结点的 MAC 地址。  <br/> |
|[Dialog 表](dialog.md) <br/> |存储音频和视频会话的对话 ID。  <br/> |
|[Region 表](region.md) <br/> |存储 NCS 设置中定义的网络区域。  <br/> |
|[UserSite 表](usersite.md) <br/> |存储 NCS 设置中定义的网络站点。  <br/> |
|[Subnet 表](subnet.md) <br/> |存储 NCS 设置中定义的子网。  <br/> |
|[MonitoredRegionLink 表](monitoredregionlink.md) <br/> |存储 NCS 设置中定义的区域链接。  <br/> |
|[MonitoredUserSiteLink 表](monitoredusersitelink.md) <br/> |存储 NCS 设置中定义的网络站点链接。  <br/> |
|[EndpointSubnet 表](endpointsubnet.md) <br/> |存储参与音频和视频会话的终结点的子网。  <br/> |
|[Server 表](server.md) <br/> |存储媒体通过的服务器的 FQDN 或 IP 地址。  <br/> |
   
**指标数据表**

|**表格**|**说明**|
|:-----|:-----|
|[AppSharingStream 表](appsharingstream.md) <br/> |存储用于应用程序共享的网络流的用户体验质量指标。 用于应用程序共享的网络流的用户体验指标的质量。  <br/> |
|[Session 表](session.md) <br/> |存储有关音频或音频/视频会话的总体信息。 会话被定义为两个终结点之间的音频或视频的 SIP 对话。  <br/> |
|[MediaLine 表](medialine-0.md) <br/> |在会话中存储有关每个媒体行的信息。 媒体行是一个或多个音频和视频流的集合。 通常，单个媒体行将有两个流音频或视频。  <br/> |
|[AudioStream 表](audiostream.md) <br/> |存储媒体行中的每个音频流的音频媒体质量指标。  <br/> |
|[AudioSignal 表](audiosignal.md) <br/> |存储媒体行中的音频媒体质量指标。 这包括回声抑制 (AEC) 和自动增益控制 (AGC) 指标。  <br/> |
|[VideoStream 表](videostream.md) <br/> |存储媒体行中的每个音频流的视频媒体质量指标。  <br/> |
|[AudioClientEvent 表](audioclientevent.md) <br/> |从客户端事件中收集存储音频媒体质量指标。  <br/> |
|[VideoClientEvent 表](videoclientevent.md) <br/> |从客户端事件中收集存储视频媒体质量指标。  <br/> |
|**DiagnosticData 表** <br/> |存储仅供内部使用的诊断数据。  <br/> |
   
**摘要数据表**

|**表格**|**说明**|
|:-----|:-----|
|**ServerSummary 表** <br/> |存储的服务器，这些数据的摘要数据用于用户体验质量 (QoE) 仅报告。  <br/> |
|**UserSummary 表** <br/> |存储用户，这些数据的摘要数据用于 QoE 报告仅。  <br/> |
|**CallTypeSummary 表** <br/> |存储呼叫类型，这些数据的摘要数据用于 QoE 报告仅。  <br/> |
   
**供监控服务器的内部使用的表**

|**表格**|**说明**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |仅供内部使用。  <br/> |
|**DbConfigInt** <br/> |仅供内部使用。  <br/> |
|**FrontEnd 表** <br/> |仅供内部使用。  <br/> |
|**任务表** <br/> |仅供内部使用。  <br/> |
|**SummaryTableConfiguration** <br/> |仅供内部使用。  <br/> |
|**DbErrorMessage** <br/> |仅供内部使用。  <br/> |
|**MetricsThreshold** <br/> |仅供内部使用。  <br/> |
|**DaylightSavingYears** <br/> |仅供内部使用。  <br/> |
|**TimeZoneConfiguration** <br/> |仅供内部使用。  <br/> |
|**TimeZones** <br/> |仅供内部使用。  <br/> |
|**CallSummary 表** <br/> |仅供内部使用。  <br/> |
|**DeviceCallSumary 表** <br/> |仅供内部使用。  <br/> |
|**Tenant 表** <br/> |仅供内部使用。  <br/> |
|**VideoCallSummaryTable** <br/> |仅供内部使用。  <br/> |
|**ASCallSummaryTable** <br/> |仅供内部使用。  <br/> |
   

