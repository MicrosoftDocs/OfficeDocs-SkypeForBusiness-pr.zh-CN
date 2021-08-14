---
title: 会议视图
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: “会议”视图会存储有关会议的信息。 此视图在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: b7cf9300ca574773b4ffb08a8c32108155a18786d8fec3ae80ddc77398d41ccc
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54351302"
---
# <a name="conferences-view"></a>会议视图
 
“会议”视图会存储有关会议的信息。 此视图在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会话请求的时间。 与 SessionIdSeq 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |用于标识会话的 ID 号。 与 SessionIdTime 结合使用来唯一地标识会话。 有关详细信息，请参阅[Skype for Business Server 2015](dialogs.md)中的 Dialogs 表。 <br/> |
|**ConferenceUri** <br/> |nvarchar (450)   <br/> |会议的 URI。  <br/> |
|**ConferenceUriType** <br/> |nvarchar (256)   <br/> |会议 URI 的类型。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
|**ConfInstance** <br/> |uniqueidentifier  <br/> |用于定期会议。定期会议的每个实例都具有相同的 ConferenceUri，但 ConfInstance 不同。  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |会议的开始时间。  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |会议的结束时间。  <br/> |
|**OrganizerUri** <br/> |nvarchar (450)   <br/> |组织会议的用户的 URI。  <br/> |
|**OrganizerType** <br/> |nvarchar (256)   <br/> |组织会议的用户的 URI 类型。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
|**OrganizerTenant** <br/> |nvarchar (256)   <br/> |组织会议的用户的租户。 有关详细信息 [，请参阅租户](tenants.md) 表。 <br/> |
|**Pool** <br/> |nvarchar (256)   <br/> |承载会议的池的完全限定域名。  <br/> |
|**Flag** <br/> |smallint  <br/> |包含会议属性的位掩码。可能的值包括：  <br/> 0X01 - 综合事务  <br/> |
   

