---
title: 在业务服务器 2015年的 Skype 会议表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: 此表中的每条记录包含有关一个会议呼叫详细信息。
ms.openlocfilehash: f0d90f7abb99bce012e864fa2485386c335de409
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>在业务服务器 2015年的 Skype 会议表
 
此表中的每条记录包含有关一个会议呼叫详细信息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |会议请求通过 CDR 代理被捕获的时间。 只用作主键来唯一标识的会议实例。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |以标识会话的 ID 号。 与**SessionIdTime**配合使用，以唯一标识的会议实例。 * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外  <br/> |会议的 URI。 [业务服务器 2015年的 Skype 在 ConferenceUris 表](conferenceuris.md)的详细信息，请参阅。 <br/> |
|**ConfInstance** <br/> |唯一标识符  <br/> | <br/> |用于定期会议;定期举行的会议的每个实例具有相同的**ConferenceUri**中，但将具有不同的**ConfInstance**。 <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |会议的开始时间。  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |会议的开始时间。  <br/> |
|**池 Id** <br/> |int  <br/> |外  <br/> |ID 号来标识会议被捕获时所在的池。 [池表](pools.md)的详细信息，请参阅。 <br/> |
|**OrganizerId** <br/> |Int  <br/> |外  <br/> |ID 号来标识 URI 的这次会议的组织者。 [（Users） 表格](users.md)的详细信息，请参阅。 <br/> |
|**标志** <br/> |smallint  <br/> || 包含会议属性的位掩码。 可能的值： <br/>  0X01 <br/>  综合 <br/>  交易记录 <br/> |
|**处理** <br/> |bit  <br/> ||监视服务所使用的内部字段。  <br/> 在 Microsoft Lync Server 2013 引入了此字段。  <br/> |
|**LastModifiedTime** <br/> |日期时间  <br/> ||供内部使用监视服务。  <br/> 为业务服务器 2015年在 Skype 引入了此字段。  <br/> |
   
\*对于大多数会话，SessionIdSeq 的值都为 1。 如果两个会话开始时完全相同，SessionIdSeq 为一个将为 1，并且对于其他将为 2，依次类推。
  

