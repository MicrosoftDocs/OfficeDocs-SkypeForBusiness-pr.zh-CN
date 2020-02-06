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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: "\"用户\" 表是支持表。 表中的每条记录存储有关在数据库中具有记录的通话或会话中涉及的一个用户的信息。"
ms.openlocfilehash: 21d03dc2214ac74188094c10a7b53ec84b8a51a9
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814800"
---
# <a name="users-table"></a>Users 表
 
"用户" 表是支持表。 表中的每条记录存储有关在数据库中具有记录的通话或会话中涉及的一个用户的信息。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||供内部使用的时间戳。  <br/> |
|**UserId** <br/> |int  <br/> |Primary  <br/> |标识此用户的唯一号码。  <br/> |
|**UserUri** <br/> |nvarchar （450）  <br/> | <br/> |用户 URI。  <br/> |
|**TenantId** <br/> |int  <br/> |外表  <br/> |此用户的租户 ID。 有关详细信息，请参阅[租户表](tenants.md)。 <br/> |
|**UriTypeId** <br/> |int  <br/> |外表  <br/> |此用户的 URI 类型。 有关详细信息，请参阅[UriTypes 表](uritypes.md)。 <br/> |
   

