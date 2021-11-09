---
title: ConferenceMessageCount 视图
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: ConferenceMessageCount 视图存储有关用户已向会议中发送的消息数的信息。 此视图在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 1308b0e9aeb8954df8010d0c1d55036eff1a3dac
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60856519"
---
# <a name="conferencemessagecount-view"></a>ConferenceMessageCount 视图
 
ConferenceMessageCount 视图存储有关用户已向会议中发送的消息数的信息。 此视图在 Microsoft Lync Server 2013 中引入。
  
> [!NOTE]
> ConferenceMessageCount 视图包含 [ConferenceSessionDetails](conferencesessiondetails.md) 视图中的所有列以及下面列出的列。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**UserUri** <br/> |nvarchar (450)   <br/> |发送消息的用户的 URI。  <br/> |
|**UserUriType** <br/> |nvarchar (256)   <br/> |发送消息的用户的 URI 类型。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
|**UserTenant** <br/> |uniqueidentifier  <br/> |发送消息的用户的租户。 有关详细信息 [，请参阅租户](tenants.md) 表。 <br/> |
|**UserMessageCount** <br/> |smallint  <br/> |用户在会议会话期间发送的消息数。  <br/> |
   

