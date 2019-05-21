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
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: ConferenceMessageCount 视图存储有关用户向会议发送的邮件数的信息。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 890a5912c6f828f614fbff89627c94c4e12ba7e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296488"
---
# <a name="conferencemessagecount-view"></a>ConferenceMessageCount 视图
 
ConferenceMessageCount 视图存储有关用户向会议发送的邮件数的信息。 此视图已在 Microsoft Lync Server 2013 中引入。
  
> [!NOTE]
> ConferenceMessageCount 视图包含[ConferenceSessionDetails 视图](conferencesessiondetails.md)中的所有列以及下面列出的列。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar (450)  <br/> |发送邮件的用户的 URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |发送邮件的用户的 URI 类型。 有关详细信息, 请参阅[UriTypes 表](uritypes.md)。 <br/> |
|**UserTenant** <br/> |标识符  <br/> |发送消息的用户的租户。 有关详细信息, 请参阅[租户表](tenants.md)。 <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |在会议会话期间用户发送的消息数。  <br/> |
   

