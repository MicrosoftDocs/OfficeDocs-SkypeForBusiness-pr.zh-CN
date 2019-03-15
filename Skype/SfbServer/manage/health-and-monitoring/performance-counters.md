---
title: Skype 业务服务器中的移动性能计数器
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
description: 摘要： 了解可用于监视服务器运行统一通信 Web API (UCWA) 和 Skype 业务服务器 Mcx Mobility Service 的性能计数器。
ms.openlocfilehash: dc2f414dce47442d50018c4a800a0c91279068c8
ms.sourcegitcommit: 27f1ecb730355dcfac2f4be3f5642f383d5532ad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2019
ms.locfileid: "21226993"
---
# <a name="mobility-performance-counters-in-skype-for-business-server"></a>Skype 业务服务器中的移动性能计数器
 
**摘要：** 了解可用于监视服务器运行统一通信 Web API (UCWA) 和 Skype 业务服务器 Mcx Mobility Service 的性能计数器。
  
下表列出的名称和说明可用于监视服务器运行统一通信 Web API (UCWA) 和 Skype 业务服务器 Mcx Mobility Service 的性能计数器。 
  
UCWA 表中的计数器的类别名称是**LS:WEB-UCWA**。
  
Mcx Mobility Service 表中计数器的类别名称为 **LS:WEB - Mobile Communication Service**。

> [!NOTE]
> MCX (Mobility Service) 支持旧的移动客户端的不再可用的业务服务器 2019 Skype 中。 业务移动客户端的所有当前 Skype 已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、 状态和联系人。 与使用 MCX 的旧客户端的用户需要升级到当前客户端。
  
## <a name="performance-counters-for-ucwa"></a>UCWA 性能计数器

|计数器|描述|
|:-----|:-----|
|Active Application Count  <br/> |当前应用程序数目  <br/> |
|Active Application Sharing Modality Count  <br/> |当前应用程序共享形式数目  <br/> |
|Active Audio Modality Count  <br/> |当前音频形式数目  <br/> |
|Active Data Collaboration Modality Count  <br/> |当前数据协作形式数目  <br/> |
|Active Directory Photo Get Latency (ms)  <br/> |此计数器显示从 Active Directory 检索照片所花的平均时间（以毫秒为单位）  <br/> |
|Active Messaging Modality Count  <br/> |当前消息传递形式数目  <br/> |
|Active Panoramic Video Modality Count  <br/> |当前全景视频形式数目  <br/> |
|Active Pending Get Count  <br/> |当前活动待处理项数；与服务器长期保持连接  <br/> |
|Active Session Count  <br/> |当前在 UCWA 中按应用程序注册的终结点数和总数  <br/> |
|Active User Instance Count  <br/> |当前用户实例数  <br/> |
|Active User Instances without Application  <br/> |当前用户实例数（无应用程序）  <br/> |
|Active Video Modality Count  <br/> |当前视频形式数目  <br/> |
|Application Creation Requests Received/Second  <br/> |应用程序创建请求的每秒接收速率  <br/> |
|AS MCU Join Failures  <br/> |AS MCU 联接失败数  <br/> |
|AV MCU Join Failures  <br/> |AV MCU 联接失败数  <br/> |
|Average Application Startup Time (ms)  <br/> |应用程序平均启动时间（以毫秒为单位）  <br/> |
|Average Lifetime for Session (ms)  <br/> |会话的平均生存时间（以毫秒为单位）  <br/> |
|Data MCU Join Failures  <br/> |Data MCU 联接失败数  <br/> |
|Exchange Contact Search Latency (ms)  <br/> |此计数器显示在 Exchange 中搜索联系人所花的平均时间（以毫秒为单位）  <br/> |
|Exchange HD Photo Get Latency (ms)  <br/> |此计数器显示从 Exchange 中检索照片所花的平均时间（以毫秒为单位）  <br/> |
|HTTP 4xx Responses/Second  <br/> |HTTP 4xx 代码的每秒响应速率  <br/> |
|HTTP 5xx Responses/Second  <br/> |HTTP 5xx 代码的每秒响应速率  <br/> |
|IM MCU Join Failures  <br/> |IM MCU 联接失败数  <br/> |
|Number of Active Directory Photo Get Failures  <br/> |从 Active Directory 中检索照片的总失败次数  <br/> |
|Number of Contact Search failures  <br/> |在 Exchange 中搜索联系人的总失败次数  <br/> |
|Number of Deserialization Failures  <br/> |反序列化的总失败次数  <br/> |
|高清照片 Get 失败的次数  <br/> |从 Exchange 中检索 HD 照片的总失败次数  <br/> |
|Over The Maximum Subscriptions Per Application  <br/> |允许的每应用程序最大订阅请求数  <br/> |
|Over The Maximum Subscriptions Per Batch  <br/> |允许的每批次最大订阅请求数  <br/> |
|Presence Subscription Failures  <br/> |订阅状态失败次数  <br/> |
|Registering Endpoint Failures  <br/> |注册终结点的失败次数  <br/> |
|Requests Received/Second  <br/> |每秒收到的请求数  <br/> |
|Requests Succeeded/Second  <br/> |每秒的成功请求数（HTTP 2xx/3xx 响应代码）  <br/> |
|Succeeded Create Application Requests/Second  <br/> |成功应用程序创建请求的每秒接收速率  <br/> |
|Timed Out Pending Get Count  <br/> |超时的待处理项数  <br/> |
|Total Application Creation Requests Received  <br/> |自启动服务以来收到的应用程序创建请求总数  <br/> |
|Total HTTP 4xx Responses  <br/> |HTTP 4xx 响应总数  <br/> |
|Total HTTP 5xx Responses  <br/> |HTTP 5xx 响应总数  <br/> |
|Total Requests Received on the Command Channel  <br/> |命令通道上收到的请求总数  <br/> |
|Total Requests Succeeded  <br/> |成功的请求总数  <br/> |
|Total Sessions Initiated  <br/> |自启动服务以来启动的会话总数  <br/> |
|Total Sessions Terminated Because of Idle Timeout  <br/> |因用户空闲超时终止的会话总数  <br/> |
|Total Throttled Applications  <br/> |阻止的应用程序数  <br/> |
   
**Mcx Mobility Service 性能计数器**

|**计数器**|**说明**|
|:-----|:-----|
|Average Lifetime for a Session in Milliseconds  <br/> |会话的平均生存时间（以毫秒为单位）  <br/> |
|Current Push Notification Subscriptions  <br/> |当前推送通知订阅数。此数目与 Currently Active Session Count 结合在一起表示为 Windows Mobile 或 iPhone 设备注册的当前活动会话的子集。  <br/> |
|Currently Active Network Timeout Poll Count  <br/> |超时的网络投票数  <br/> |
|Currently Active Poll Count  <br/> |当前活动投票数（与服务器的长期连接）  <br/> |
|Currently Active Session Count  <br/> |当前注册到 Mobility Service 中的终结点的数目  <br/> |
|Currently Active Session Count with Active Presence Subscriptions  <br/> |包含活动状态订阅的当前活动会话的数目  <br/> |
|Push Notification Requests Failed/Second  <br/> |每秒失败的推送通知数  <br/> |
|Push Notification Requests Succeeded/Second  <br/> |每秒成功的推送通知数  <br/> |
|Push Notification Requests Throttled/Second  <br/> |每秒阻止的推送通知数  <br/> |
|Push Notification Requests/Second  <br/> |每秒发送的推送通知数  <br/> |
|Requests Failed/Second  <br/> |每秒失败的请求数  <br/> |
|Requests Received/Second  <br/> |每秒收到的请求数  <br/> |
|Requests Rejected/Second  <br/> |每秒拒绝的请求数  <br/> |
|Requests Succeeded/Second  <br/> |每秒成功的请求数  <br/> |
|Succeeded Initiate Session Requests/Second  <br/> |每秒成功的 Get Location 请求数。启动会话的请求占用了服务器上大部分 CPU。支持的峰值负载为 12/秒。可持续性依赖于服务器上的其他负载。启动会话通常意味着用户登录已注销很长一段时间。  <br/> |
|Total Declined Inbound Voice Calls  <br/> |拒绝的入站语音呼叫总数  <br/> |
|Total Failed Inbound Voice Calls  <br/> |失败的入站语音呼叫总数  <br/> |
|Total Failed Outbound Voice Calls  <br/> |失败的出站语音呼叫总数  <br/> |
|Total number of sessions terminated by user  <br/> |用户终止的会话总数  <br/> |
|Total Push Notification Requests  <br/> |推送通知请求总数  <br/> |
|Total Push Notification Requests Failed  <br/> |失败的推送通知请求总数  <br/> |
|Total Push Notification Requests Succeeded  <br/> |成功的推送通知请求总数  <br/> |
|Total Push Notification Requests Throttled  <br/> |阻止的推送通知请求总数  <br/> |
|Total Requests Failed  <br/> |失败的请求总数  <br/> |
|Total Requests received on the Command Channel  <br/> |命令通道上收到的请求总数  <br/> |
|Total Requests Rejected  <br/> |拒绝的请求总数  <br/> |
|Total Requests Succeeded  <br/> |成功发送给 Mobility Service 的请求总数  <br/> |
|Total Session Initiated Count  <br/> |自启动 Mobility Service 后启动的会话总数  <br/> |
|Total Sessions Terminated Because of User Idle Timeout  <br/> |因用户空闲超时终止的会话总数  <br/> |
|Total Successful Inbound Voice Calls  <br/> |成功的入站语音呼叫总数  <br/> |
|Total Successful Outbound Voice Calls  <br/> |成功的出站语音呼叫总数  <br/> |
   
> [!NOTE]
> MCX (Mobility Service) 支持旧的移动客户端的不再可用的业务服务器 2019 Skype 中。 业务移动客户端的所有当前 Skype 已使用统一通信 Web API (UCWA) 来支持即时消息 (IM)、 状态和联系人。 与使用 MCX 的旧客户端的用户需要升级到当前客户端。
