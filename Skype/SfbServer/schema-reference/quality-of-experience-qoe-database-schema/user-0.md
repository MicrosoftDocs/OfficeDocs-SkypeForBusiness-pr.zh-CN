---
title: User 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: 用户表是一个支持的表来存储各种参加会话记录在数据库中的用户的列表。 每个表中的记录表示一个用户。
ms.openlocfilehash: 3261133b8c36fe96fd847c075dce0be2a903c417
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="user-table"></a>User 表
 
用户表是一个支持的表来存储各种参加会话记录在数据库中的用户的列表。 每个表中的记录表示一个用户。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Primary  <br/> |识别该用户的唯一号码。  <br/> |
|**URI** <br/> |nvarchar(450)  <br/> |唯一  <br/> |URI 字符串。  <br/> |
|**URIType** <br/> |int  <br/> ||1 是 URI 类型未知。  <br/> 2 是用户的 URI。  <br/> 4 是 URI 的会议。  <br/> 8 是电话 URI。  <br/> |
|**TenantKey** <br/> |int  <br/> |外  <br/> |客户端的用户，从租户表引用。  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||最新时间戳时用户有较差的音频呼叫。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||仅供内部使用。  <br/> |
   

