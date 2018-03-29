---
title: QoE 表的列表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: 下表包含数据库架构。
ms.openlocfilehash: 5f8957bfa4bbe2da75073082132468bff748c712
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="list-of-qoe-tables"></a>QoE 表的列表
 
下表包含数据库架构。 
  
**支持表**

|**表**|**说明**|
|:-----|:-----|
|[AppSharingMetricsThreshold 表](appsharingmetricsthreshold.md) <br/> |将使用应用程序共享体验质量指标的最佳状态，并且可接受值存储。  <br/> |
|[CodecDescription 表](codecdescription.md) <br/> |映射到其相应的编解码器的编解码器的唯一标识符。  <br/> |
|[Ip 地址表](ipaddress.md) <br/> |将 IP 地址映射到体验质量数据库中的其他位置使用唯一 IP 地址标识。  <br/> |
|[NetworkConnectionDetail 表](networkconnectiondetail.md) <br/> |网络连接类型映射到体验质量数据库中的其他位置使用的网络连接标识符。  <br/> |
|[PurgeSettings 表 (QoE)](purgesettings-qoe.md) <br/> |如果 （并且当） 指定的存储信息过时的记录将自动为从数据库中删除 QoE 体验的质量。  <br/> |
|[路由追踪表](traceroute.md) <br/> |存储路由信息的电话。  <br/> |
|[UserAgentDef 表 (QoE)](useragentdef-qoe.md) <br/> |将用户代理标识符映射到代理的描述性名称。  <br/> |
|[VideoMetricsThreshold 表](videometricsthreshold.md) <br/> |存储使用视频呼叫体验质量指标的最佳状态，并且可接受值。  <br/> |
|[用户代理表](useragent.md) <br/> |存储会话启动协议 (SIP) 用户代理 (UA) 字符串和 UA 音频和视频会话中使用的类型。  <br/> |
|[用户表](user-0.md) <br/> |存储用户、 会议和电话 Uri 用于音频和视频会话。  <br/> |
|[终结点表](endpoint.md) <br/> |存储的参与中音频和视频会话的终结点的 FQDN 的计算机名称。  <br/> |
|[池表](pool.md) <br/> |存储的数据属于哪个指标的池的名称。  <br/> |
|[设备表](device.md) <br/> |存储捕获设备和呈现音频/视频调用使用了这些设备。  <br/> |
|[DeviceDriver 表](devicedriver.md) <br/> |用于捕获设备和呈现设备的音频/视频调用中使用的存储驱动程序。  <br/> |
|[会议桌](conference.md) <br/> |会议方案或其他方案的 DialogID 存储会议 Uri。  <br/> |
|[SessionCorrelation 表](sessioncorrelation.md) <br/> |PSTN 呼叫的商店都会。  <br/> |
|[PayloadDescription 表](payloaddescription.md) <br/> |存储音频/视频调用中使用的编码解码器。  <br/> |
|[AppliedBandwidthSource 表](appliedbandwidthsource.md) <br/> |存储使用音频/视频呼叫的带宽源。  <br/> |
|[MacAddress 表](macaddress.md) <br/> |存储参与音频和视频会话的终结点的 MAC 地址。  <br/> |
|[对话框表](dialog.md) <br/> |存储音频和视频会话的对话框 ID。  <br/> |
|[区域表](region.md) <br/> |存储在 NCS 设置中定义的网络区域。  <br/> |
|[UserSite 表](usersite.md) <br/> |存储在 NCS 设置中定义的网络站点。  <br/> |
|[子网表](subnet.md) <br/> |存储在 NCS 设置中定义的子网。  <br/> |
|[MonitoredRegionLink 表](monitoredregionlink.md) <br/> |存储在 NCS 设置定义的区域链接。  <br/> |
|[MonitoredUserSiteLink 表](monitoredusersitelink.md) <br/> |存储在 NCS 设置中定义的网络站点链接。  <br/> |
|[EndpointSubnet 表](endpointsubnet.md) <br/> |将存储终结点加入音频和视频会话的子网。  <br/> |
|[服务器表](server.md) <br/> |存储介质所经历的服务器的 FQDN 或 IP 地址。  <br/> |
   
**度量数据的表**

|**表**|**说明**|
|:-----|:-----|
|[AppSharingStream 表](appsharingstream.md) <br/> |存储用于应用程序共享的网络流的体验质量指标。 用于应用程序共享的网络流的经验指标的质量。  <br/> |
|[会话列表](session.md) <br/> |存储有关音频或音频/视频会话的整体信息。 会话定义为两个端点之间的音频或视频的 SIP 对话。  <br/> |
|[MediaLine 表](medialine-0.md) <br/> |在会话中存储有关每个媒体行的信息。 媒体线路是集合的一个或多个音频流和视频流。 通常情况下，单个媒体连线将有两个流音频或视频。  <br/> |
|[AudioStream 表](audiostream.md) <br/> |在媒体行中存储每个音频流媒体音频质量标准。  <br/> |
|[AudioSignal 表](audiosignal.md) <br/> |在媒体行存储音频媒体质量标准。 这包括声音回声抵消 (AEC) 和自动增益控制 (AGC) 指标。  <br/> |
|[VideoStream 表](videostream.md) <br/> |在媒体行中存储每个音频流媒体视频质量标准。  <br/> |
|[AudioClientEvent 表](audioclientevent.md) <br/> |从客户端事件收集存储音频媒体质量标准。  <br/> |
|[VideoClientEvent 表](videoclientevent.md) <br/> |从客户端事件收集存储视频媒体质量标准。  <br/> |
|**DiagnosticData 表** <br/> |存储这是仅供内部使用的诊断数据。  <br/> |
   
**汇总数据的表**

|**表**|**说明**|
|:-----|:-----|
|**ServerSummary 表** <br/> |将汇总数据存储服务器，这些数据将用于体验质量 (QoE) 仅报告。  <br/> |
|**UserSummary 表** <br/> |将汇总数据存储的用户，这些数据将用于 QoE 仅报告。  <br/> |
|**CallTypeSummary 表** <br/> |对于调用类型，这些数据存储摘要数据用于 QoE 仅报告。  <br/> |
   
**通过监视服务器内部使用的表**

|**表**|**说明**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |仅供内部使用。  <br/> |
|**DbConfigInt** <br/> |仅供内部使用。  <br/> |
|**前端表** <br/> |仅供内部使用。  <br/> |
|**任务表** <br/> |仅供内部使用。  <br/> |
|**SummaryTableConfiguration** <br/> |仅供内部使用。  <br/> |
|**DbErrorMessage** <br/> |仅供内部使用。  <br/> |
|**MetricsThreshold** <br/> |仅供内部使用。  <br/> |
|**DaylightSavingYears** <br/> |仅供内部使用。  <br/> |
|**TimeZoneConfiguration** <br/> |仅供内部使用。  <br/> |
|**时区** <br/> |仅供内部使用。  <br/> |
|**CallSummary 表** <br/> |仅供内部使用。  <br/> |
|**DeviceCallSumary 表** <br/> |仅供内部使用。  <br/> |
|**租户表** <br/> |仅供内部使用。  <br/> |
|**VideoCallSummaryTable** <br/> |仅供内部使用。  <br/> |
|**ASCallSummaryTable** <br/> |仅供内部使用。  <br/> |
   

