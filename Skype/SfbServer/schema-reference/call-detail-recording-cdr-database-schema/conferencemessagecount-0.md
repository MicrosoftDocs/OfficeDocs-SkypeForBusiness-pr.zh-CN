---
title: ConferenceMessageCount 视图
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: ConferenceMessageCount 视图存储有关多少邮件由用户发送会议信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: f2290eef7d2738831ed3ce72c794a36659858b8b
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874072"
---
# <a name="conferencemessagecount-view"></a>ConferenceMessageCount 视图
 
ConferenceMessageCount 视图存储有关多少邮件由用户发送会议信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
> [!NOTE]
> ConferenceMessageCount 视图包含[ConferenceSessionDetails 视图](conferencesessiondetails.md)中的列中所有下面列出的列。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar(450)  <br/> |发送邮件的用户的 URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |发送邮件的用户的 URI 的类型。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
|**UserTenant** <br/> |唯一标识符  <br/> |用户的租户，发送邮件。 请参阅[Tenants 表](tenants.md)的详细信息。 <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |在会议会话期间发送的用户的消息数。  <br/> |
   

