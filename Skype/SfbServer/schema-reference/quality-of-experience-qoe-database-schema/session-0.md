---
title: 会话视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: "\"会话\" 视图存储有关具有数据库中的记录的会话的信息。 此视图已在 Microsoft Lync Server 2013 中引入。"
ms.openlocfilehash: cd304123022e0d4d921ecb1cd2599c636aaa9013
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805900"
---
# <a name="session-view"></a>会话视图
 
"会话" 视图存储有关具有数据库中的记录的会话的信息。 此视图已在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |从 MediaLine 表中引用。  <br/> |
|ConferenceURI  <br/> |nvarchar （450）  <br/> |会议 URI （如果这是会议）或 DialogID （如果这是对等会话）。  <br/> |
|关系  <br/> |varchar （max）  <br/> |会话的相关 ID。  <br/> |
|DialogCategory  <br/> |bit  <br/> |对话框类别;0是 Skype for business 服务器，用于采集服务器腿;1是中介服务器到 PSTN 网关腿。  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |指示是否跳过呼叫。  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |此字段（如果存在）指示无法跳过呼叫的原因，即使旁路 Id 匹配也是如此。 对于 Skype for Business 服务器，仅定义了一个值：  <br/> 0x0001-默认网络适配器的旁路 ID 未知  <br/> |
|StartTime  <br/> |datetime  <br/> |通话开始时间。  <br/> |
|EndTime  <br/> |datetime  <br/> |通话结束时间。  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |呼叫方池 FQDN。  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |被调用池 FQDN。  <br/> |
|CallerPAI  <br/> |nvarchar （450）  <br/> |调用方的 p 声明标识 URI。  <br/> |
|CalleePAI  <br/> |nvarchar （450）  <br/> |被调用方的 p 声明标识 URI。  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |调用方的终结点名称。  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |调用方的终结点名称。  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |呼叫方的用户代理字符串。  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |呼叫方的用户代理的类型。 有关详细信息，请参阅[UserAgent 表](useragent.md)。 <br/> |
|CallerUserAgentCategory  <br/> |nvarchar （64）  <br/> |呼叫者的用户代理类别。 有关详细信息，请参阅[UserAgentDef 表（QoE）](useragentdef-qoe.md) 。 <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |被呼叫方的用户代理字符串。  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |被呼叫方的用户代理类型。 有关详细信息，请参阅[UserAgent 表](useragent.md)。 <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar （64）  <br/> |被呼叫方的用户代理类别。 有关详细信息，请参阅[UserAgentDef 表（QoE）](useragentdef-qoe.md) 。 <br/> |
|CallerURI  <br/> |nvarchar （450）  <br/> |调用方的 URI。  <br/> |
|CalleeURI  <br/> |nvarchar （450）  <br/> |被调用方的 URI。  <br/> |
|CallPrioirty  <br/> |int  <br/> |通话的优先级。  <br/> |
   

