---
title: 查看会议
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c0e5c4db-c135-401f-9296-e9a49f6499a1
description: 会议视图存储有关会议的信息。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: 98fbf972badeb6cf3b179c8fa408626f2224f5b3
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="conferences-view"></a>查看会议
 
会议视图存储有关会议的信息。 在 Microsoft Lync Server 2013 引入了此视图。
  
|**列**|**数据类型**|**详细信息**|
|:-----|:-----|:-----|
|**SessionIdTime** <br/> |datetime  <br/> |会议请求的时间。 与 SessionIdSeq 配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**SessionIdSeq** <br/> |int  <br/> |以标识会话的 ID 号。 与 SessionIdTime 配合使用，以唯一标识会话。 [对话框中业务服务器 2015年的 Skype 的表](dialogs.md)的详细信息，请参阅。 <br/> |
|**ConferenceUri** <br/> |nvarchar(450)  <br/> |参加大会的 URI。  <br/> |
|**ConferenceUriType** <br/> |nvarchar(256)  <br/> |URI 的会议的类型。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
|**ConfInstance** <br/> |唯一标识符  <br/> |用于定期会议。 定期举行的会议的每个实例具有相同但不同 ConfInstance ConferenceUri。  <br/> |
|**ConferenceStartTime** <br/> |datetime  <br/> |会议的开始时间。  <br/> |
|**ConferenceEndTime** <br/> |datetime  <br/> |会议的结束时间。  <br/> |
|**OrganizerUri** <br/> |nvarchar(450)  <br/> |URI 的用户的组织会议。  <br/> |
|**OrganizerType** <br/> |nvarchar(256)  <br/> |URI 的用户的组织会议的类型。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
|**OrganizerTenant** <br/> |nvarchar(256)  <br/> |客户端的用户的会议组织者。 [租户表](tenants.md)的详细信息，请参阅。 <br/> |
|**池** <br/> |nvarchar(256)  <br/> |主持会议的池的完全限定的域名。  <br/> |
|**标志** <br/> |smallint  <br/> |包含会议属性的位掩码。 可能的值：  <br/> 0X01 的综合事务  <br/> |
   

