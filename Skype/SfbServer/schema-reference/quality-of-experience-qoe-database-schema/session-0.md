---
title: 会话视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: 会话视图存储在数据库中具有记录的会话的有关信息。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: 056067b0c0e06b3ce9eb862898345fe4c8ff131c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="session-view"></a>会话视图
 
会话视图存储在数据库中具有记录的会话的有关信息。 在 Microsoft Lync Server 2013 引入了此视图。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |从 MediaLine 表引用。  <br/> |
|ConferenceURI  <br/> |nvarchar(450)  <br/> |如果这是 DialogID 的会议，如果此 URI 会议是对等会话。  <br/> |
|相关  <br/> |varchar(max)  <br/> |关联的会话 ID。  <br/> |
|DialogCategory  <br/> |bit  <br/> |对话框的类别;0 是 Skype 业务服务器到中介服务器腿;1 到 PSTN 网关腿是中介服务器。  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |指示该调用被绕过。  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |此字段中，如果存在，表明为什么调用不会绕过即使旁路 Id 匹配。 Skype 业务服务器，定义一个值：  <br/> 0x0001-未知的旁路 ID 默认网络适配器  <br/> |
|开始时间  <br/> |datetime  <br/> |调用启动时间。  <br/> |
|结束时间  <br/> |datetime  <br/> |调用结束时间。  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |调用方池的 FQDN。  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |被调用方池的 FQDN。  <br/> |
|CallerPAI  <br/> |nvarchar(450)  <br/> |调用方的 p 断言标识的 URI。  <br/> |
|CalleePAI  <br/> |nvarchar(450)  <br/> |被调用方的 p 断言标识的 URI。  <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |调用方的端点名称。  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |调用方的端点名称。  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |调用方的用户代理字符串。  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |调用方的用户代理的类型。 [用户代理表](useragent.md)的详细信息，请参阅。 <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |调用方的用户代理的类别。 [UserAgentDef 表 (QoE)](useragentdef-qoe.md)的详细信息，请参阅。 <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |被调用方的用户代理字符串。  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |对于被调用方的用户代理的类型。 [用户代理表](useragent.md)的详细信息，请参阅。 <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |对于被调用方的用户代理类别。 [UserAgentDef 表 (QoE)](useragentdef-qoe.md)的详细信息，请参阅。 <br/> |
|CallerURI  <br/> |nvarchar(450)  <br/> |调用方的 URI。  <br/> |
|CalleeURI  <br/> |nvarchar(450)  <br/> |被调用方的 URI。  <br/> |
|CallPrioirty  <br/> |int  <br/> |调用的优先级。  <br/> |
   

