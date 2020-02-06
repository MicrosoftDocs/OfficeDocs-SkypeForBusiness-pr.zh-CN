---
title: ConferenceMessageCount 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: ConferenceMessageCount 视图存储有关用户向会议发送的邮件数的信息。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: a766e63fbca5c30cec3c3891c9ccfc2355f16d2d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815380"
---
# <a name="conferencemessagecount-view"></a>ConferenceMessageCount 视图
 
ConferenceMessageCount 视图存储有关用户向会议发送的邮件数的信息。 此视图已在 Microsoft Lync Server 2013 中引入。
  
> [!NOTE]
> ConferenceMessageCount 视图包含[ConferenceSessionDetails 视图](conferencesessiondetails.md)中的所有列以及下面列出的列。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar （450）  <br/> |发送邮件的用户的 URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |发送邮件的用户的 URI 类型。 有关详细信息，请参阅[UriTypes 表](uritypes.md)。 <br/> |
|**UserTenant** <br/> |标识符  <br/> |发送消息的用户的租户。 有关详细信息，请参阅[租户表](tenants.md)。 <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |在会议会话期间用户发送的消息数。  <br/> |
   

