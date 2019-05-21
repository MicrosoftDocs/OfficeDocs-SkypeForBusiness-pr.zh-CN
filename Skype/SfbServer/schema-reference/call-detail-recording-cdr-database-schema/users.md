---
title: Users 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: "\"用户\" 表是支持表。 表中的每条记录存储有关在数据库中具有记录的通话或会话中涉及的一个用户的信息。"
ms.openlocfilehash: 0dcc2fda73305be2bbe6a7a5c546dac0b05f8273
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295697"
---
# <a name="users-table"></a>Users 表
 
"用户" 表是支持表。 表中的每条记录存储有关在数据库中具有记录的通话或会话中涉及的一个用户的信息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||供内部使用的时间戳。  <br/> |
|**UserId** <br/> |int  <br/> |Primary  <br/> |标识此用户的唯一号码。  <br/> |
|**UserUri** <br/> |nvarchar (450)  <br/> | <br/> |用户 URI。  <br/> |
|**TenantId** <br/> |int  <br/> |外表  <br/> |此用户的租户 ID。 有关详细信息, 请参阅[租户表](tenants.md)。 <br/> |
|**UriTypeId** <br/> |int  <br/> |外表  <br/> |此用户的 URI 类型。 有关详细信息, 请参阅[UriTypes 表](uritypes.md)。 <br/> |
   

