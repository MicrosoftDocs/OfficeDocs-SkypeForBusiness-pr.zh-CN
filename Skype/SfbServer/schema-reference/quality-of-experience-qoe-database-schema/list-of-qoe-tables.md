---
title: QoE 表列表
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: 数据库架构由以下表组成。
ms.openlocfilehash: 7b97746b3f8a490da7fb06d903ca6f7676f2d6b5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60849585"
---
# <a name="list-of-qoe-tables"></a>QoE 表列表
 
数据库架构由以下表组成。 
  
**支持表**

|**Table**|**说明**|
|:-----|:-----|
|[AppSharingMetricsThreshold 表](appsharingmetricsthreshold.md) <br/> |存储用于应用程序共享的用户体验质量指标的最佳值和可接受值。  <br/> |
|[CodecDescription 表](codecdescription.md) <br/> |将唯一的编解码器标识符映射到其对应的编解码器。  <br/> |
|[IPAddress 表](ipaddress.md) <br/> |将 IP 地址映射到在用户体验质量数据库中使用的唯一 IP 地址标识符。  <br/> |
|[NetworkConnectionDetail 表](networkconnectiondetail.md) <br/> |将网络连接类型映射到在用户体验质量数据库中的其他位置使用的网络连接标识符。  <br/> |
|[QoE (PurgeSettings) ](purgesettings-qoe.md) <br/> |存储指定是否（以及何时）将从 QoE 数据库中自动删除过期的用户体验质量记录的信息。  <br/> |
|[TraceRoute 表](traceroute.md) <br/> |存储用于呼叫的路由信息。  <br/> |
|[QoE (UserAgentDef) ](useragentdef-qoe.md) <br/> |地图用户代理标识符复制到代理的描述性名称。  <br/> |
|[VideoMetricsThreshold 表](videometricsthreshold.md) <br/> |存储用于视频呼叫的用户体验质量指标的最佳值和可接受值。  <br/> |
|[UserAgent 表](useragent.md) <br/> |存储音频和视频会话中使用的会话初始协议 (SIP) 用户代理 (UA) 字符串和 UA 类型。  <br/> |
|[用户表](user-0.md) <br/> |存储音频和视频会话中使用的用户、会议和电话 URI。  <br/> |
|[Endpoint 表](endpoint.md) <br/> |存储参与音频和视频会话的终结点的 FQDN 计算机名称。  <br/> |
|[Pool 表](pool.md) <br/> |存储指标数据所属的池的名称。  <br/> |
|[设备表](device.md) <br/> |存储用于音频/视频呼叫的捕获设备和呈现设备。  <br/> |
|[DeviceDriver 表](devicedriver.md) <br/> |存储用于音频/视频呼叫的捕获设备和呈现设备的驱动程序。  <br/> |
|[Conference 表](conference.md) <br/> |存储会议方案的会议 URI 或其他方案的 DialogID。  <br/> |
|[SessionCorrelation 表](sessioncorrelation.md) <br/> |存储 PSTN 呼叫的 CorrelationID。  <br/> |
|[PayloadDescription 表](payloaddescription.md) <br/> |存储用于音频/视频呼叫的编解码器。  <br/> |
|[AppliedBandwidthSource 表](appliedbandwidthsource.md) <br/> |存储用于音频/视频呼叫的带宽源。  <br/> |
|[MacAddress 表](macaddress.md) <br/> |存储参与音频和视频会话的终结点的 MAC 地址。  <br/> |
|[对话框表](dialog.md) <br/> |存储音频和视频会话的对话 ID。  <br/> |
|[Region 表](region.md) <br/> |存储 NCS 设置中定义的网络区域。  <br/> |
|[UserSite 表](usersite.md) <br/> |存储 NCS 设置中定义的网络站点。  <br/> |
|[Subnet 表](subnet.md) <br/> |存储 NCS 设置中定义的子网。  <br/> |
|[MonitoredRegionLink 表](monitoredregionlink.md) <br/> |存储 NCS 设置中定义的区域链接。  <br/> |
|[MonitoredUserSiteLink 表](monitoredusersitelink.md) <br/> |存储 NCS 设置中定义的网络站点链接。  <br/> |
|[EndpointSubnet 表](endpointsubnet.md) <br/> |存储参与音频和视频会话的终结点的子网。  <br/> |
|[服务器表](server.md) <br/> |存储媒体通过的服务器的 FQDN 或 IP 地址。  <br/> |
   
**指标数据表**

|**Table**|**说明**|
|:-----|:-----|
|[AppSharingStream 表](appsharingstream.md) <br/> |存储用于应用程序共享的网络流的用户体验质量指标。用于应用程序共享的网络流的用户体验质量指标。  <br/> |
|[会话表](session.md) <br/> |存储有关音频或音频/视频会话的总体信息。会话定义为两个终结点之间的音频或视频 SIP 对话。  <br/> |
|[MediaLine 表](medialine-0.md) <br/> |存储有关会话中每个媒体行的信息。媒体行是一个或多个音频和视频流的集合。通常，一个媒体行具有两个流：音频或视频。  <br/> |
|[AudioStream 表](audiostream.md) <br/> |存储媒体行中每个音频流的音频媒体质量指标。  <br/> |
|[AudioSignal 表](audiosignal.md) <br/> |存储媒体行中的音频媒体质量指标。其中包括回声抑制 (AEC) 和自动增益控制 (AGC) 指标。  <br/> |
|[VideoStream 表](videostream.md) <br/> |存储媒体行中的每个音频流的视频媒体质量指标。  <br/> |
|[AudioClientEvent 表](audioclientevent.md) <br/> |存储从客户端事件中收集的音频媒体质量指标。  <br/> |
|[VideoClientEvent 表](videoclientevent.md) <br/> |存储从客户端事件中收集的视频媒体质量指标。  <br/> |
|**DiagnosticData 表** <br/> |存储仅供内部使用的诊断数据。  <br/> |
   
**摘要数据表**

|**Table**|**说明**|
|:-----|:-----|
|**ServerSummary 表** <br/> |存储服务器的摘要数据，这些数据仅用于用户体验质量 (QoE) 报告。  <br/> |
|**UserSummary 表** <br/> |存储用户的摘要数据，这些数据仅用于 QoE 报告。  <br/> |
|**CallTypeSummary 表** <br/> |存储呼叫类型的摘要数据，这些数据仅用于 QoE 报告。  <br/> |
   
**供监控服务器内部使用的表**

|**Table**|**说明**|
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
   

