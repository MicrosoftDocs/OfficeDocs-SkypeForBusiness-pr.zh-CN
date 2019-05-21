---
title: QoE 表的列表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: 数据库架构由下表组成。
ms.openlocfilehash: ba6f439d97692a40fd485a2c550da079092d7365
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294913"
---
# <a name="list-of-qoe-tables"></a>QoE 表的列表
 
数据库架构由下表组成。 
  
**支持表**

|**表格**|**说明**|
|:-----|:-----|
|[AppSharingMetricsThreshold 表](appsharingmetricsthreshold.md) <br/> |存储用于应用程序共享的体验质量指标的最佳值和可接受值。  <br/> |
|[CodecDescription 表](codecdescription.md) <br/> |将唯一的编解码器标识符映射到相应的编解码器。  <br/> |
|[IPAddress 表](ipaddress.md) <br/> |将 IP 地址映射到 "体验质量" 数据库中其他位置使用的唯一 IP 地址标识符。  <br/> |
|[NetworkConnectionDetail 表](networkconnectiondetail.md) <br/> |将网络连接类型映射到 "体验质量" 数据库中其他位置使用的网络连接标识符。  <br/> |
|[PurgeSettings table (QoE)](purgesettings-qoe.md) <br/> |存储用于指定是否会自动从 QoE 数据库中删除过时的体验记录质量的信息。  <br/> |
|[TraceRoute 表](traceroute.md) <br/> |存储呼叫的路由信息。  <br/> |
|[UserAgentDef table (QoE)](useragentdef-qoe.md) <br/> |将用户代理标识符映射到代理的描述性名称。  <br/> |
|[VideoMetricsThreshold 表](videometricsthreshold.md) <br/> |存储与视频通话一起使用的体验质量指标的最佳和可接受的值。  <br/> |
|[UserAgent 表](useragent.md) <br/> |存储会话初始协议 (SIP) 用户代理 (UA) 字符串和音频和视频会话中使用的 UA 类型。  <br/> |
|[User 表](user-0.md) <br/> |存储在音频和视频会话中使用的用户、会议和电话 Uri。  <br/> |
|[Endpoint 表](endpoint.md) <br/> |存储参与音频和视频会话的终结点的 FQDN 计算机名称。  <br/> |
|[Pool 表](pool.md) <br/> |存储指标数据所属的池的名称。  <br/> |
|[Device 表](device.md) <br/> |存储捕获设备和呈现在音频/视频呼叫中使用的设备。  <br/> |
|[DeviceDriver 表](devicedriver.md) <br/> |存储用于音频/视频通话的捕获设备和呈现设备的驱动程序。  <br/> |
|[Conference 表](conference.md) <br/> |存储适用于其他方案的会议方案或 DialogID 的会议 Uri。  <br/> |
|[SessionCorrelation 表](sessioncorrelation.md) <br/> |存储 PSTN 呼叫的 CorrelationID。  <br/> |
|[PayloadDescription 表](payloaddescription.md) <br/> |存储用于音频/视频通话的编解码器。  <br/> |
|[AppliedBandwidthSource 表](appliedbandwidthsource.md) <br/> |存储音频/视频通话中使用的带宽源。  <br/> |
|[MacAddress 表](macaddress.md) <br/> |存储参与音频和视频会话的终结点的 MAC 地址。  <br/> |
|[Dialog 表](dialog.md) <br/> |存储音频和视频会话的对话框 ID。  <br/> |
|[Region 表](region.md) <br/> |存储在 NCS 设置中定义的网络区域。  <br/> |
|[UserSite 表](usersite.md) <br/> |存储在 NCS 设置中定义的 network 网站。  <br/> |
|[Subnet 表](subnet.md) <br/> |存储在 NCS 设置中定义的子网。  <br/> |
|[MonitoredRegionLink 表](monitoredregionlink.md) <br/> |存储在 NCS 设置中定义的区域链接。  <br/> |
|[MonitoredUserSiteLink 表](monitoredusersitelink.md) <br/> |存储在 NCS 设置中定义的网络网站链接。  <br/> |
|[EndpointSubnet 表](endpointsubnet.md) <br/> |存储参与音频和视频会话的终结点的子网。  <br/> |
|[Server 表](server.md) <br/> |存储媒体所经历的服务器的 FQDN 或 IP 地址。  <br/> |
   
**指标数据表**

|**表格**|**说明**|
|:-----|:-----|
|[AppSharingStream 表](appsharingstream.md) <br/> |存储用于应用程序共享的网络流的体验质量指标。 用于应用程序共享的网络流的体验质量指标。  <br/> |
|[Session 表](session.md) <br/> |存储有关音频或音频/视频会话的整体信息。 会话在两个终结点之间定义为音频或视频 SIP 对话框。  <br/> |
|[MediaLine 表](medialine-0.md) <br/> |存储有关会话中每个媒体行的信息。 媒体线是一个或多个音频和视频流的集合。 通常, 单个媒体线路将有两个流, 即音频或视频。  <br/> |
|[AudioStream 表](audiostream.md) <br/> |存储媒体行中每个音频流的音频媒体质量指标。  <br/> |
|[AudioSignal 表](audiosignal.md) <br/> |将音频媒体质量指标存储在媒体行中。 这包括音频回声取消 (AEC) 和自动增益控制 (AGC) 指标。  <br/> |
|[VideoStream 表](videostream.md) <br/> |存储媒体行中每个音频流的视频媒体质量指标。  <br/> |
|[AudioClientEvent 表](audioclientevent.md) <br/> |存储从客户端事件收集的音频媒体质量指标。  <br/> |
|[VideoClientEvent 表](videoclientevent.md) <br/> |存储从客户端事件收集的视频媒体质量指标。  <br/> |
|**DiagnosticData 表** <br/> |存储仅供内部使用的诊断数据。  <br/> |
   
**汇总数据表**

|**表格**|**说明**|
|:-----|:-----|
|**ServerSummary 表** <br/> |存储服务器的汇总数据, 这些数据仅用于体验质量 (QoE) 报告。  <br/> |
|**UserSummary 表** <br/> |存储用户的汇总数据, 这些数据仅用于 QoE 报告。  <br/> |
|**CallTypeSummary 表** <br/> |存储通话类型的汇总数据, 这些数据仅用于 QoE 报告。  <br/> |
   
**监视服务器供内部使用的表**

|**表格**|**说明**|
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
   

