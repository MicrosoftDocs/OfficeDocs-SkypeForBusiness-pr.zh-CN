---
title: Session 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: 每条记录代表一个会话，这会涉及音频或音频和视频。 它包含有关会话的总体信息。 会话定义为两个终结点之间的音频或视频会话初始协议 (SIP) 对话。
ms.openlocfilehash: 7a0ea3f9753529c22299ef46017b863c314319b5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212374"
---
# <a name="session-table"></a>Session 表
 
每条记录代表一个会话，这会涉及音频或音频和视频。 它包含有关会话的总体信息。 会话定义为两个终结点之间的音频或视频会话初始协议 (SIP) 对话。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |引用自[Dialog table](dialog.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |引用自[Dialog table](dialog.md)。  <br/> |
|**ConferenceKey** <br/> |int  <br/> |外  <br/> |会议密钥。 从[Conference 表](conference.md)引用。  <br/> |
|**CorrelationKey** <br/> |int  <br/> |外  <br/> |相关键。 从[SessionCorrelation 表](sessioncorrelation.md)引用。  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |对话类别;0 是 Skype 业务服务器到中介服务器线路;1 是中介服务器到 PSTN 网关线路。  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||标志指示绕过呼叫。  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||此字段中，如果存在此参数，指示为什么呼叫不绕过即使绕过 Id 匹配。 对于业务服务器 Skype，定义只有一个值。  <br/> 0x0001-默认网络适配器的未知绕过 ID。  <br/> |
|**StartTime** <br/> |datetime  <br/> | <br/> |呼叫开始时间。  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |呼叫结束时间。  <br/> |
|**CallerPool** <br/> |int  <br/> |外  <br/> |呼叫者的池。 从[池表](pool.md)引用。  <br/> |
|**CalleePool** <br/> |int  <br/> |外  <br/> |呼叫接收者的池。 从[池表](pool.md)引用。  <br/> |
|**CalleePAI** <br/> |int  <br/> |外  <br/> |在 SIP p 已断言标识 (PAI) 接收终结点中的 SIP URI。 从[用户表](user-0.md)引用。  <br/> |
|**CallerURI** <br/> |int  <br/> |外  <br/> |呼叫者的 URI。 从[用户表](user-0.md)引用。  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |外  <br/> |呼叫者终结点。 从[终结点表](endpoint.md)引用。  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |外  <br/> |呼叫者的用户代理。 从[UserAgent 表](useragent.md)引用。  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||此呼叫的优先级。  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||此列已被弃用，不用于 Skype 业务服务器。 相反，此信息报告-媒体行进制数。 引用[自 MediaLine table](medialine-0.md)的详细信息。 <br/> |
|**CallerPAI** <br/> |int  <br/> |外  <br/> |P-所宣称的标识的用户发出呼叫。 P 已断言标识 (PAI) 用于传达 true 发出呼叫的用户的标识。  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |外  <br/> |接收呼叫的终结点。  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |外  <br/> |用户代理的用户所使用接收呼叫。 用户代理表示客户端终结点设备。  <br/> |
|**CalleeUri** <br/> |int  <br/> |外  <br/> |接收呼叫的用户的 SIP URI。  <br/> |
   

