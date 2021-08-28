---
title: 会话视图
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
description: 会话视图存储有关在数据库中具有记录的会话的信息。 此视图在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: e39f6c744280e96a6f0fd33c28125196f90ed7cc
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593346"
---
# <a name="session-view"></a>会话视图
 
会话视图存储有关在数据库中具有记录的会话的信息。 此视图在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**Details**|
|:-----|:-----|:-----|
|ConferenceDateTime  <br/> |datetime  <br/> |引用自 MediaLine 表。  <br/> |
|ConferenceURI  <br/> |nvarchar (450)   <br/> |如果是会议，则是会议 URI；如果是点对点会话，则是 DialogID。  <br/> |
|相关性  <br/> |varchar (max)   <br/> |会话的关联 ID。  <br/> |
|DialogCategory  <br/> |bit  <br/> |对话框类别;0 表示Skype for Business Server到中介服务器;1 是中介服务器到 PSTN 网关的通道。  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |指示是否旁路了呼叫。  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |如果存在，此字段指示即使绕过 ID 相匹配也没有绕过呼叫的原因。 对于Skype for Business Server，仅定义一个值：  <br/> 0x0001 - 默认网络适配器的未知绕过 ID  <br/> |
|StartTime  <br/> |datetime  <br/> |呼叫开始时间。  <br/> |
|EndTime  <br/> |datetime  <br/> |呼叫结束时间。  <br/> |
|CallerPool  <br/> |nvarchar (256)   <br/> |呼叫者池 FQDN。  <br/> |
|CalleePool  <br/> |nvarchar (256)   <br/> |被叫方池 FQDN。  <br/> |
|CallerPAI  <br/> |nvarchar (450)   <br/> |呼叫者的 p 断言标识 URI。  <br/> |
|CalleePAI  <br/> |nvarchar (450)   <br/> |被叫方 p 断言的标识 URI。  <br/> |
|CallerEndpoint  <br/> |nvarchar (256)   <br/> |呼叫者的终结点名称。  <br/> |
|CalleeEndpoint  <br/> |nvarchar (256)   <br/> |呼叫者的终结点名称。  <br/> |
|CallerUserAgent  <br/> |nvarchar (256)   <br/> |呼叫者的用户代理字符串。  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |呼叫者的用户代理的类型。 有关详细信息， [请参阅 UserAgent](useragent.md) 表。 <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |呼叫者的用户代理的类别。 有关详细信息，请参阅 [QoE (UserAgentDef) ](useragentdef-qoe.md) 表。 <br/> |
|CalleeUserAgent  <br/> |nvarchar (256)   <br/> |被叫方的用户代理字符串。  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |被叫方的用户代理的类型。 有关详细信息， [请参阅 UserAgent](useragent.md) 表。 <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |被叫方的用户代理类别。 有关详细信息，请参阅 [QoE (UserAgentDef) ](useragentdef-qoe.md) 表。 <br/> |
|CallerURI  <br/> |nvarchar (450)   <br/> |呼叫者的 URI。  <br/> |
|CalleeURI  <br/> |nvarchar (450)   <br/> |被叫方 URI。  <br/> |
|CallPrioirty  <br/> |int  <br/> |呼叫的优先级。  <br/> |
   

