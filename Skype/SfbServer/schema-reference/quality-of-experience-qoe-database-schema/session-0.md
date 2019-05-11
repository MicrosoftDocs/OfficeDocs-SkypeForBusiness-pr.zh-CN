---
title: 会话视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: 会话视图存储有关数据库中包含记录的会话的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: e30bdb31457e9e70984b66bef75c898cadd9aeb1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33919996"
---
# <a name="session-view"></a>会话视图
 
会话视图存储有关数据库中包含记录的会话的信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |引用自 MediaLine table。  <br/> |
|ConferenceURI  <br/> |nvarchar(450)  <br/> |会议 URI 如果这是 dialogid 会议，如果它是对等会话。  <br/> |
|互联  <br/> |varchar(max)  <br/> |会话的关联 ID。  <br/> |
|DialogCategory  <br/> |bit  <br/> |对话类别;0 是 Skype 业务服务器到中介服务器线路;1 是中介服务器到 PSTN 网关线路。  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |指示旁路了呼叫。  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |此字段中，如果存在此参数，指示为什么呼叫不绕过即使绕过 Id 匹配。 为业务服务器 Skype，定义只有一个值：  <br/> 0x0001-默认网络适配器的未知绕过 ID  <br/> |
|StartTime  <br/> |datetime  <br/> |呼叫开始时间。  <br/> |
|EndTime  <br/> |datetime  <br/> |呼叫结束时间。  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |呼叫者池 FQDN。  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |被叫方池 FQDN。  <br/> |
|CallerPAI  <br/> |nvarchar(450)  <br/> |呼叫者的 p 已断言标识 URI。  <br/> |
|CalleePAI  <br/> |nvarchar(450)  <br/> |被叫方的 p 已断言标识 URI。  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |呼叫者的终结点名称。  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |呼叫者的终结点名称。  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |呼叫者的用户代理字符串。  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |呼叫者的用户代理的类型。 请参阅[UserAgent 表](useragent.md)的详细信息。 <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |呼叫者的用户代理的类别。 请参阅[UserAgentDef 表 (QoE)](useragentdef-qoe.md)的详细信息。 <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |被叫方的用户代理字符串。  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |被叫方的用户代理的类型。 请参阅[UserAgent 表](useragent.md)的详细信息。 <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |被叫方用户代理类别。 请参阅[UserAgentDef 表 (QoE)](useragentdef-qoe.md)的详细信息。 <br/> |
|CallerURI  <br/> |nvarchar(450)  <br/> |呼叫者的 URI。  <br/> |
|CalleeURI  <br/> |nvarchar(450)  <br/> |被叫方的 URI。  <br/> |
|CallPrioirty  <br/> |int  <br/> |呼叫的优先级。  <br/> |
   

