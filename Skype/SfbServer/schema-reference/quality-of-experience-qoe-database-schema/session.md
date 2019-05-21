---
title: Session 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
description: 每条记录表示一个包含音频或音频和视频的会话。 它包含有关会话的整体信息。 会话在两个终结点之间定义为音频或视频会话初始协议 (SIP) 对话框。
ms.openlocfilehash: e0cd6a4523b09d8bcb7f74d6c796b46bf99ece8e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294668"
---
# <a name="session-table"></a>Session 表
 
每条记录表示一个包含音频或音频和视频的会话。 它包含有关会话的整体信息。 会话在两个终结点之间定义为音频或视频会话初始协议 (SIP) 对话框。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primary  <br/> |从[对话框表](dialog.md)中引用。  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primary  <br/> |从[对话框表](dialog.md)中引用。  <br/> |
|**ConferenceKey** <br/> |int  <br/> |外表  <br/> |会议密钥。 从[会议表](conference.md)中引用。  <br/> |
|**CorrelationKey** <br/> |int  <br/> |外表  <br/> |相关密钥。 从[SessionCorrelation 表](sessioncorrelation.md)中引用。  <br/> |
|**DialogCategory** <br/> |bit  <br/> | <br/> |对话框类别;0是 Skype for business 服务器, 用于采集服务器腿;1是中介服务器到 PSTN 网关腿。  <br/> |
|**MediationServerBypassFlag** <br/> |bit  <br/> ||指示是否已绕过呼叫的标志。  <br/> |
|**MediaBypassWarningFlag** <br/> |int  <br/> ||此字段 (如果存在) 指示无法跳过呼叫的原因, 即使旁路 Id 匹配也是如此。 对于 Skype for Business 服务器, 仅定义了一个值。  <br/> 0x0001-默认网络适配器的旁路 ID 未知。  <br/> |
|**StartTime** <br/> |datetime  <br/> | <br/> |通话开始时间。  <br/> |
|**EndTime** <br/> |datetime  <br/> | <br/> |通话结束时间。  <br/> |
|**CallerPool** <br/> |int  <br/> |外表  <br/> |呼叫方的池。 从[Pool 表](pool.md)中引用。  <br/> |
|**CalleePool** <br/> |int  <br/> |外表  <br/> |呼叫接收器的池。 从[Pool 表](pool.md)中引用。  <br/> |
|**CalleePAI** <br/> |int  <br/> |外表  <br/> |接收终结点的 SIP p 声明标识 (PAI) 中的 SIP URI。 从[用户表](user-0.md)中引用。  <br/> |
|**CallerURI** <br/> |int  <br/> |外表  <br/> |调用方的 URI。 从[用户表](user-0.md)中引用。  <br/> |
|**CallerEndpoint** <br/> |int  <br/> |外表  <br/> |调用方的终结点。 从[终结点表](endpoint.md)中引用。  <br/> |
|**CallerUserAgent** <br/> |bit  <br/> |外表  <br/> |呼叫方的用户代理。 从[UserAgent 表](useragent.md)中引用。  <br/> |
|**CallPriority** <br/> |smallint  <br/> ||此通话的优先级。  <br/> |
|**ClassifiedPoorCall** <br/> |bit  <br/> ||此列已弃用, 并且不在 Skype for Business 服务器中使用。 而是报告每个媒体行基础上的此信息。 有关详细信息, 请参阅[MediaLine 表](medialine-0.md)。 <br/> |
|**CallerPAI** <br/> |int  <br/> |外表  <br/> |P-声明-发出呼叫的用户的标识。 P 声明的标识 (PAI) 用于传达发出呼叫的用户的真实标识。  <br/> |
|**CalleeEndpoint** <br/> |int  <br/> |外表  <br/> |接收呼叫的终结点。  <br/> |
|**CalleeUserAgent** <br/> |int  <br/> |外表  <br/> |接收呼叫的用户所使用的用户代理。 用户代理代表客户端终结点设备。  <br/> |
|**CalleeUri** <br/> |int  <br/> |外表  <br/> |接收呼叫的用户的 SIP URI。  <br/> |
   

