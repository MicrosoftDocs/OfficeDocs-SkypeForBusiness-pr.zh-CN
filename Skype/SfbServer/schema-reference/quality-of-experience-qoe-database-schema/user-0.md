---
title: User 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6b52047e-286d-47ab-b7bc-a9b266f62d82
description: 用户表是一个支持表，用于存储已参与记录数据库中的会话的不同用户列表。 表中的每条记录代表一个用户。
ms.openlocfilehash: fcdc8682b86432613af79d5e4d2abbdb248fef0f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881672"
---
# <a name="user-table"></a>User 表
 
用户表是一个支持表，用于存储已参与记录数据库中的会话的不同用户列表。 表中的每条记录代表一个用户。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**UserKey** <br/> |int  <br/> |Primary  <br/> |标识此用户的唯一编号。  <br/> |
|**URI** <br/> |nvarchar(450)  <br/> |唯一  <br/> |URI 字符串。  <br/> |
|**URIType** <br/> |int  <br/> ||1 是未知的 URI 类型。  <br/> 2 是用户 URI。  <br/> 4 是会议 URI。  <br/> 8 是电话 URI。  <br/> |
|**TenantKey** <br/> |int  <br/> |外  <br/> |租户的用户，被 tenant 表引用。  <br/> |
|**LastPoorCallTime** <br/> |datetime  <br/> ||最新时间戳时用户具有较差音频呼叫。  <br/> |
|**NextUpdateTS** <br/> |datetime  <br/> ||仅供内部使用。  <br/> |
   

