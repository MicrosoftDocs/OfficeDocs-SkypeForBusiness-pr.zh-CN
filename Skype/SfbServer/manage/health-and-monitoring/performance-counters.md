---
title: 移动性能计数器Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: d18ed85a-673d-4695-aa3f-ac83a38ab90a
description: 摘要：了解可用于监视运行统一通信 Web API (UCWA) 和 Skype for Business Server Mcx Mobility Service 的服务器的性能计数器。
ms.openlocfilehash: 4ea7ba3f7c4d9685fe01c64157324a64f823c5bc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58578776"
---
# <a name="mobility-performance-counters-in-skype-for-business-server"></a>移动性能计数器Skype for Business Server
 
**摘要：** 了解可用于监视运行统一通信 Web API (UCWA) 和 Skype for Business Server Mcx Mobility Service 的服务器的性能计数器。
  
下表列出了可用于监视运行统一通信 Web API (UCWA) 和 Skype for Business Server Mcx Mobility Service 的服务器的性能计数器的名称和说明。 
  
UCWA 表中计数器的类别名称是 **LS：WEB - UCWA**。
  
Mcx Mobility Service 表中计数器的类别名称为 **LS：WEB - Mobile Communication Service**。

> [!NOTE]
> MCX (Mobility Service) 2019 年不再提供对旧版移动客户端Skype for Business Server支持。 所有当前Skype for Business客户端已使用统一通信 Web API (UCWA) 支持即时消息 (IM) 、状态和联系人。 使用 MCX 的旧客户端的用户将需要升级到当前客户端。
  
## <a name="performance-counters-for-ucwa"></a>UCWA 的性能计数器

|计数器|说明|
|:-----|:-----|
|活动应用程序计数  <br/> |当前应用程序数  <br/> |
|活动应用程序共享形式计数  <br/> |当前应用程序共享形式的数量  <br/> |
|Active Audio Modality Count  <br/> |当前音频形式数  <br/> |
|活动数据协作形式计数  <br/> |当前数据协作形式的数量  <br/> |
|Active Directory 照片获取延迟 (ms)   <br/> |此计数器显示从 active directory (照片) 的平均时间（以毫秒为单位）  <br/> |
|Active Messaging Modality Count  <br/> |当前消息传递形式的数量  <br/> |
|活动全景视频形式计数  <br/> |全景视频形式的当前数量  <br/> |
|Active Pending Get Count  <br/> |当前处于活动状态的待处理获取数;与服务器的长期连接  <br/> |
|活动会话计数  <br/> |每个应用程序在 UCWA 中注册的当前终结点数和总数  <br/> |
|活动用户实例计数  <br/> |当前用户实例数  <br/> |
|没有应用程序的活动用户实例  <br/> |当前没有应用程序的用户实例数  <br/> |
|活动视频形式计数  <br/> |当前视频形式数量  <br/> |
|Application Creation Requests Received/Second  <br/> |每秒收到的应用程序创建请求数  <br/> |
|AS MCU 联接失败  <br/> |AS MCU 联接失败数  <br/> |
|AV MCU 联接失败  <br/> |AV MCU 联接失败数  <br/> |
|Average Application Startup Time (ms)   <br/> |应用程序启动平均时间（以毫秒为单位）  <br/> |
|会话会话的平均 (毫秒)   <br/> |会话的平均生存时间（以毫秒为单位）  <br/> |
|Data MCU Join Failures  <br/> |Data MCU Join Failures 的数量  <br/> |
|Exchange联系人搜索延迟 (毫秒)   <br/> |此计数器显示搜索联系人 (的平均) 毫秒Exchange  <br/> |
|ExchangeHD Photo Get Latency (ms)   <br/> |此计数器显示从用户 (照片) 的平均时间（以毫秒Exchange  <br/> |
|HTTP 4xx 响应/秒  <br/> |HTTP 4xx 代码的每秒响应速率  <br/> |
|HTTP 5xx 响应/秒  <br/> |HTTP 5xx 代码的每秒响应速率  <br/> |
|IM MCU Join Failures  <br/> |IM MCU Join Failures 的数量  <br/> |
|Active Directory 照片获取失败次数  <br/> |从 Active Directory 检索照片的总失败次数  <br/> |
|联系人搜索失败次数  <br/> |搜索联系人失败的总次数Exchange  <br/> |
|反序列化失败次数  <br/> |反序列化失败总数  <br/> |
|HD 照片获取失败次数  <br/> |从设备中检索 HD 照片的失败Exchange  <br/> |
|超过每个应用程序的最大订阅数  <br/> |每个应用程序允许的最大订阅请求数  <br/> |
|超过每个批次的最大订阅数  <br/> |超过每个批次允许的最大订阅请求数  <br/> |
|状态订阅失败  <br/> |订阅状态失败次数  <br/> |
|注册终结点故障  <br/> |注册终结点的失败次数  <br/> |
|Requests Received/Second  <br/> |每秒收到的请求数  <br/> |
|Requests Succeeded/Second  <br/> |HTTP 2xx/3xx 响应代码 (每秒成功的请求数)   <br/> |
|已成功创建应用程序请求/秒  <br/> |每秒成功的应用程序创建请求数  <br/> |
|Timed Out Pending Get Count  <br/> |挂起的已暂停数目  <br/> |
|收到的应用程序创建请求总数  <br/> |自服务启动以来收到的应用程序创建请求总数  <br/> |
|HTTP 4xx 响应总数  <br/> |HTTP 4xx 响应总数  <br/> |
|HTTP 5xx 响应总数  <br/> |HTTP 5xx 响应总数  <br/> |
|在命令通道上收到的请求总数  <br/> |命令通道上收到的请求总数  <br/> |
|Total Requests Succeeded  <br/> |成功的请求总数  <br/> |
|启动会话总数  <br/> |自服务启动以来启动的会话总数  <br/> |
|Total Sessions Terminated Because of Idle Timeout  <br/> |因用户空闲超时终止的会话总数  <br/> |
|Total Throttled Applications  <br/> |限制的应用程序数  <br/> |
   
**Mcx Mobility Service 的性能计数器**

|**计数器**|**描述**|
|:-----|:-----|
|Average Lifetime for a Session in Milliseconds  <br/> |会话的平均生存时间（以毫秒为单位）  <br/> |
|Current Push Notification Subscriptions  <br/> |当前推送通知订阅数。 此数字与 Currently Active Session Count 一起使用表示为移动设备或移动设备注册Windows活动iPhone子集。  <br/> |
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
> MCX (Mobility Service) 2019 年不再提供对旧版移动客户端Skype for Business Server支持。 所有当前Skype for Business客户端已使用统一通信 Web API (UCWA) 支持即时消息 (IM) 、状态和联系人。 使用 MCX 的旧客户端的用户将需要升级到当前客户端。
