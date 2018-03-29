---
title: Session 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: 每个记录表示一个会话涉及音频或音频和视频。 它包含有关该会话的整体信息。 会话定义为两个端点之间的音频或视频会话启动协议 (SIP) 对话框。
ms.openlocfilehash: 24acf23d2dab2dbc4b6586e40aa49cba632d6a68
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="session-table"></a>Session 表
 
每个记录表示一个会话涉及音频或音频和视频。 它包含有关该会话的整体信息。 会话定义为两个端点之间的音频或视频会话启动协议 (SIP) 对话框。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |从[对话框表](dialog.md)引用。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |从[对话框表](dialog.md)引用。  <br/> |
|**ConferenceKey** <br/> |int  <br/> |外  <br/> |会议密钥。 从[会议表](conference.md)引用。  <br/> |
|**CorrelationKey** <br/> |int  <br/> |外  <br/> |关联的键。 从[SessionCorrelation 表](sessioncorrelation.md)引用。  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |对话框的类别;0 是 Skype 业务服务器到中介服务器腿;1 到 PSTN 网关腿是中介服务器。  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||该标志指明如果呼叫被绕过或不。  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||此字段中，如果存在，表明为什么调用不会绕过即使旁路 Id 匹配。 Skype 业务服务器，定义一个值。  <br/> 0x0001-未知绕过默认的网络适配器的 ID。  <br/> |
|**开始时间** <br/> |datetime  <br/> | <br/> |调用启动时间。  <br/> |
|**结束时间** <br/> |datetime  <br/> | <br/> |调用结束时间。  <br/> |
|**CallerPool** <br/> |int  <br/> |外  <br/> |调用方的池。 从[池表](pool.md)引用。  <br/> |
|**CalleePool** <br/> |int  <br/> |外  <br/> |调用接收器的池。 从[池表](pool.md)引用。  <br/> |
|**CalleePAI** <br/> |int  <br/> |外  <br/> |在 SIP p 断言标识 (PAI) 接收端点的 SIP URI。 从[用户表](user-0.md)引用。  <br/> |
|**CallerURI** <br/> |int  <br/> |外  <br/> |调用方的 URI。 从[用户表](user-0.md)引用。  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |外  <br/> |调用方的端点。 从[终结点表](endpoint.md)引用。  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |外  <br/> |调用方的用户代理。 从[用户代理表](useragent.md)引用。  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||此调用的优先级。  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||此列已否决，并不用于在 Skype 业务服务器。 相反，每个媒体行基上报告此信息。 请参阅[MediaLine 表](medialine-0.md)的详细信息。 <br/> |
|**CallerPAI** <br/> |int  <br/> |外  <br/> |P-断言的用户标识发出调用。 P 断言标识 (PAI) 用于传达真正发出调用的用户的身份。  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |外  <br/> |接收呼叫的终结点。  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |外  <br/> |用户由用户负责代理接收到呼叫。 用户代理代表客户端终结点设备。  <br/> |
|**CalleeUri** <br/> |int  <br/> |外  <br/> |接收呼叫的用户的 SIP URI。  <br/> |
   

