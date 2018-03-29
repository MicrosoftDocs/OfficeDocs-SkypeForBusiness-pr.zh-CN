---
title: Users 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: 用户表是支持表。 表中的每条记录存储调用或数据库中具有记录的会话中涉及的一个用户有关的信息。
ms.openlocfilehash: b14350d060485a57b4af42cbfe26db729872f6f8
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="users-table"></a>Users 表
 
用户表是支持表。 表中的每条记录存储调用或数据库中具有记录的会话中涉及的一个用户有关的信息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||供内部使用的时间戳。  <br/> |
|**用户 Id** <br/> |int  <br/> |Primary  <br/> |识别该用户的唯一号码。  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |用户的 URI。  <br/> |
|**TenantId** <br/> |int  <br/> |外  <br/> |此用户的租户 id。 [租户表](tenants.md)的详细信息，请参阅。 <br/> |
|**UriTypeId** <br/> |int  <br/> |外  <br/> |此用户的 URI 类型。 [UriTypes 表](uritypes.md)的详细信息，请参阅。 <br/> |
   

