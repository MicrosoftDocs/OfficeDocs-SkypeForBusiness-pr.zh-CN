---
title: ConferenceMessageCount 视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: ConferenceMessageCount 视图存储多少邮件用户发送到会议有关的信息。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: f0206145217f63e4530d2eac39c7c6533dcf154e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="conferencemessagecount-view"></a>ConferenceMessageCount 视图
 
ConferenceMessageCount 视图存储多少邮件用户发送到会议有关的信息。 在 Microsoft Lync Server 2013 引入了此视图。
  
> [!NOTE]
> ConferenceMessageCount 视图它包含[ConferenceSessionDetails 视图](conferencesessiondetails.md)中的列的所有除了下面列出的列。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar(450)  <br/> |发送消息的用户的 URI。  <br/> |
|**UserUriType** <br/> |nvarchar(256)  <br/> |URI 的用户发送的消息的类型。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
|**UserTenant** <br/> |唯一标识符  <br/> |客户端的用户发送邮件的人。 [租户表](tenants.md)的详细信息，请参阅。 <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |会议会话过程中由用户发送的消息数。  <br/> |
   

