---
title: 会议视图
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: 会议视图存储有关会议信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 42bdbed9cceb8d50e2de8ddbe29ba406e4a0a2f5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213268"
---
# <a name="conferences-view"></a>会议视图
 
会议视图存储有关会议信息。 此视图是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会话请求的时间。 与 SessionIdSeq 结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |标识会话的 ID 号。 与 SessionIdTime 结合使用，来唯一地标识会话。 [Dialogs 表中的业务服务器 2015 Skype](dialogs.md)的详细信息，请参阅。 <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |会议的 URI。  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |会议 URI 的类型。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
|**ConfInstance** <br/> |唯一标识符  <br/> |用于定期会议。 定期会议的每个实例具有相同的 ConferenceUri，但不同 ConfInstance。  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |用于会议的开始时间。  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |用于会议的结束时间。  <br/> |
|**OrganizerUri** <br/> |nvarchar(450)  <br/> |组织会议的用户的 URI。  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |组织会议的用户的 URI 的类型。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |会议组织者租户的用户。 请参阅[Tenants 表](tenants.md)的详细信息。 <br/> |
|**Pool** <br/> |nvarchar(256)  <br/> |承载会议的池的完全限定的域名。  <br/> |
|**标志** <br/> |smallint  <br/> |包含会议属性的位掩码。 可能的值：  <br/> 0X01-综合事务  <br/> |
   

