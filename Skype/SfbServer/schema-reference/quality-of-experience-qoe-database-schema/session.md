---
title: 会话表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: 每条记录表示一个涉及音频或音频和视频的会话。 它包含有关会话的总体信息。 会话定义为两个终结点之间的 SIP (对话) 音频或视频会话初始协议。
ms.openlocfilehash: cdf639e7360248e02378c66eb68a60d49acb9749
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802672"
---
# <a name="session-table"></a>会话表
 
每条记录表示一个涉及音频或音频和视频的会话。 它包含有关会话的总体信息。 会话定义为两个终结点之间的 SIP (对话) 音频或视频会话初始协议。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |主  <br/> |从 Dialog 表 [引用](dialog.md)。  <br/> |
|**SessionSeq** <br/> |int  <br/> |主  <br/> |从 Dialog 表 [引用](dialog.md)。  <br/> |
|**ConferenceKey** <br/> |int  <br/> |Foreign  <br/> |会议密钥。 从会议表 [引用](conference.md)。  <br/> |
|**CorrelationKey** <br/> |int  <br/> |Foreign  <br/> |相关键。 从 [SessionCorrelation 表引用](sessioncorrelation.md)。  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |对话框类别;0 表示 Skype for Business Server 到中介服务器;1 是中介服务器到 PSTN 网关的通道。  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||指示呼叫是否绕过的标志。  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||如果存在，此字段指示即使绕过 ID 相匹配也没有绕过呼叫的原因。 对于 Skype for Business Server，只定义了一个值。  <br/> 0x0001 - 默认网络适配器的未知绕过 ID。  <br/> |
|**StartTime** <br/> |datetime  <br/> | <br/> |呼叫开始时间。  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |呼叫结束时间。  <br/> |
|**CallerPool** <br/> |int  <br/> |Foreign  <br/> |呼叫者的池。 从 Pool 表 [引用](pool.md)。  <br/> |
|**CalleePool** <br/> |int  <br/> |Foreign  <br/> |呼叫接收器的池。 从 Pool 表 [引用](pool.md)。  <br/> |
|**CalleePAI** <br/> |int  <br/> |Foreign  <br/> |接收终结点的 SIP p 断言标识 (PAI) SIP URI。 从用户表 [引用](user-0.md)。  <br/> |
|**CallerURI** <br/> |int  <br/> |Foreign  <br/> |呼叫者的 URI。 从用户表 [引用](user-0.md)。  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |Foreign  <br/> |呼叫者的终结点。 从 Endpoint 表 [引用](endpoint.md)。  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |Foreign  <br/> |呼叫者的用户代理。 从 [UserAgent 表引用](useragent.md)。  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||此调用的优先级。  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||此列已被弃用，未在 Skype for Business Server 中使用。 相反，此信息基于每媒体行进行报告。 有关详细信息， [请参阅 MediaLine](medialine-0.md) 表。 <br/> |
|**CallerPAI** <br/> |int  <br/> |Foreign  <br/> |拨打呼叫的用户的 P-Asserted-Identity。 P-Asserted-Identity (PAI) 用于传达拨打呼叫的用户的真实身份。  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |Foreign  <br/> |收到呼叫的终结点。  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |Foreign  <br/> |接收呼叫的用户使用的用户代理。 用户代理表示客户端终结点设备。  <br/> |
|**CalleeUri** <br/> |int  <br/> |Foreign  <br/> |收到呼叫的用户的 SIP URI。  <br/> |
   

