---
title: Users 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Users 表是一个支持表。 表中的每条记录都存储有关数据库中具有记录的呼叫或会话中涉及的一个用户的信息。
ms.openlocfilehash: b2f7dad297a085d3fb5b8dc77c86feb07b094e7e
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58598626"
---
# <a name="users-table"></a>Users 表
 
Users 表是一个支持表。 表中的每条记录都存储有关数据库中具有记录的呼叫或会话中涉及的一个用户的信息。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**NextUpdateTS** <br/> |datetime  <br/> ||供内部使用的时间戳。  <br/> |
|**UserId** <br/> |int  <br/> |主  <br/> |用于标识此用户的唯一编号。  <br/> |
|**UserUri** <br/> |nvarchar (450)   <br/> | <br/> |用户 URI。  <br/> |
|**TenantId** <br/> |int  <br/> |Foreign  <br/> |此用户的租户 ID。 有关详细信息 [，请参阅租户](tenants.md) 表。 <br/> |
|**UriTypeId** <br/> |int  <br/> |Foreign  <br/> |此用户的 URI 类型。 有关详细信息， [请参阅 UriTypes](uritypes.md) 表。 <br/> |
   

