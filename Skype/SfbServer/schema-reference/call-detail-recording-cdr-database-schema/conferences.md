---
title: Skype for Business Server 2015 中的 "会议" 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 7/15/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c3da6271-b3c6-4898-894f-10456ec794d0
description: 此表中的每条记录包含有关一次会议的通话详细信息。
ms.openlocfilehash: 41a2a25e80b073b568152422defeee1ca3e2ac19
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296446"
---
# <a name="conferences-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 "会议" 表
 
此表中的每条记录包含有关一次会议的通话详细信息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |Primary  <br/> |由 CDR 代理捕获会议请求的时间。 仅用作主键以唯一标识会议实例。  <br/> |
|**SessionIdSeq** <br/> |int  <br/> |Primary  <br/> |标识会话的 ID 号。 与**SessionIdTime**结合使用以唯一标识会议实例。 * <br/> |
|**ConferenceUriId** <br/> |int  <br/> |外表  <br/> |会议 URI。 有关详细信息, 请参阅[Skype For Business Server 2015 中的 ConferenceUris 表](conferenceuris.md)。 <br/> |
|**ConfInstance** <br/> |标识符  <br/> | <br/> |适用于定期会议;定期会议的每个实例都具有相同的**ConferenceUri**, 但将具有不同的**ConfInstance**。 <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> | <br/> |会议开始时间。  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> | <br/> |会议开始时间。  <br/> |
|**PoolId** <br/> |int  <br/> |外表  <br/> |标识在其中捕获会议的池的 ID 号。 有关详细信息, 请参阅[pool 表](pools.md)。 <br/> |
|**OrganizerId** <br/> |整形  <br/> |外表  <br/> |标识此会议的组织者 URI 的 ID 号。 有关详细信息, 请参阅[用户表](users.md)。 <br/> |
|**旗** <br/> |smallint  <br/> || 包含会议属性的位掩码。 可能的值： <br/>  0X01 <br/>  合成 <br/>  事务 <br/> |
|**过** <br/> |bit  <br/> ||监视服务使用的内部字段。  <br/> 此字段是在 Microsoft Lync Server 2013 中引入的。  <br/> |
|**LastModifiedTime** <br/> |从中  <br/> ||供监视服务内部使用。  <br/> 此字段是在 Skype for Business Server 2015 中引入的。  <br/> |
   
\*对于大多数会话, SessionIdSeq 将具有值1。 如果两个会话的开始时间完全相同, 则一个会话的 SessionIdSeq 将为 1, 而另一个会话将为 2, 依此类推。
  

