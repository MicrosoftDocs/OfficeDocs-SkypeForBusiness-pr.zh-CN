---
title: Users 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Users 表是一个支持表。 表中的每条记录存储呼叫或在数据库中包含记录的会话所涉及的一个用户的信息。
ms.openlocfilehash: 3929ba33737c107ee60ec1e31beebb1addbb2e3f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885559"
---
# <a name="users-table"></a>Users 表
 
Users 表是一个支持表。 表中的每条记录存储呼叫或在数据库中包含记录的会话所涉及的一个用户的信息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||供内部使用的时间戳。  <br/> |
|**用户 Id** <br/> |int  <br/> |Primary  <br/> |标识此用户的唯一编号。  <br/> |
|**UserUri** <br/> |nvarchar(450)  <br/> | <br/> |用户 URI。  <br/> |
|**TenantId** <br/> |int  <br/> |外  <br/> |此用户的租户 id。 请参阅[Tenants 表](tenants.md)的详细信息。 <br/> |
|**UriTypeId** <br/> |int  <br/> |外  <br/> |此用户的 URI 类型。 请参阅[UriTypes 表](uritypes.md)的详细信息。 <br/> |
   

