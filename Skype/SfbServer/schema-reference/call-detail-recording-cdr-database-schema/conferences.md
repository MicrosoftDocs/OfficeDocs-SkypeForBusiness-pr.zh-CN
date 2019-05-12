---
title: Conferences 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: 此表中的每条记录包含有关一个会议的呼叫详细信息。
ms.openlocfilehash: 3d8382316d17dfc13cd0d9cd2e98e79b3461951c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901364"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Conferences 表中的业务服务器 2015 Skype
 
此表中的每条记录包含有关一个会议的呼叫详细信息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |CDR 代理捕获的会议请求的时间。 仅作为主关键字用于唯一标识会议实例。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用，来唯一地标识会议实例。 * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外  <br/> |会议 URI。 请参阅[ConferenceUris 表中的业务服务器 2015 Skype](conferenceuris.md)的详细信息。 <br/> |
|**ConfInstance** <br/> |唯一标识符  <br/> | <br/> |可用于定期会议;定期会议的每个实例具有相同的**ConferenceUri**，但会**ConfInstance**不同。 <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |会议开始时间。  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |会议开始时间。  <br/> |
|**池 Id** <br/> |int  <br/> |外  <br/> |标识在其中捕获会议的池的 ID 号。 请参阅[Pools 表](pools.md)的详细信息。 <br/> |
|**OrganizerId** <br/> |Int  <br/> |外  <br/> |若要确定组织者的此会议 URI 的 ID 号。 请参阅[用户表](users.md)的详细信息。 <br/> |
|**标志** <br/> |smallint  <br/> || 包含会议属性的位掩码。 可能的值： <br/>  0X01 <br/>  综合 <br/>  事务 <br/> |
|**处理** <br/> |bit  <br/> ||使用的监控服务的内部字段。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供监控服务内部使用。  <br/> 为业务服务器 2015年在 Skype 引入了此字段。  <br/> |
   
\*对于大多数会话 SessionIdSeq 具有 1 的值。 如果两个会话的一个将为 1，同时完全，SessionIdSeq 启动，和的其他将为 2，依此类推。
  

