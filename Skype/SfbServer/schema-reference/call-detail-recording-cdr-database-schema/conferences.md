---
title: Skype for Business Server 2015 中的 Conferences 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: 此表中的每条记录都包含有关一个会议的呼叫详细信息。
ms.openlocfilehash: dfc1c12908e60c7a5b205c154e30175168871ceb
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635206"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 Conferences 表
 
此表中的每条记录都包含有关一个会议的呼叫详细信息。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |主  <br/> |CDR 代理捕获会议请求的时间。 仅用于唯一标识会议实例的主键。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |主  <br/> |用于标识会话的 ID 号。 与 **SessionIdTime 结合使用** 来唯一地标识会议实例。 * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |Foreign  <br/> |会议 URI。 有关详细信息，[请参阅 Skype for Business Server 2015 中的 ConferenceUris](conferenceuris.md)表。 <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> | <br/> |对于定期会议非常有用;定期会议的每个实例具有相同的 **ConferenceUri，** 但将具有不同的 **ConfInstance**。 <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |会议开始时间。  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |会议开始时间。  <br/> |
|**PoolId** <br/> |int  <br/> |Foreign  <br/> |用于标识捕获会议的池的 ID 号。 有关详细信息 [，请参阅 Pools](pools.md) 表。 <br/> |
|**OrganizerId** <br/> |Int  <br/> |Foreign  <br/> |用于标识此会议的组织者 URI 的 ID 号。 有关详细信息 [，请参阅 Users](users.md) 表。 <br/> |
|**Flag** <br/> |smallint  <br/> || 包含会议属性的位掩码。 可能的值是： <br/>  0X01 <br/>  综合 <br/>  事务 <br/> |
|**已处理** <br/> |bit  <br/> ||监控服务使用的内部字段。  <br/> 此字段在 Microsoft Lync Server 2013 中引入。  <br/> |
|**LastModifiedTime** <br/> |Datetime  <br/> ||供监控服务内部使用。  <br/> 此字段在 2015 年 Skype for Business Server引入。  <br/> |
   
\* 对于大多数会话，SessionIdSeq 的值为 1。 如果两个会话完全同时启动，则一个会话的 SessionIdSeq 将为 1，另一个会话的 SessionIdSeq 将为 2，以此类比。
  

