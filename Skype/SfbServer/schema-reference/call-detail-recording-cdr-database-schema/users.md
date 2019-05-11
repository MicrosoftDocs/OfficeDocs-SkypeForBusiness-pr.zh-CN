---
title: Users 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a8d71373-4b57-4245-9f02-f7fc0d9fcd3c
description: Users 表是一个支持表。 表中的每条记录存储呼叫或在数据库中包含记录的会话所涉及的一个用户的信息。
ms.openlocfilehash: fbe3ff7d2570f78cdf3b3418629fb9fd6209d944
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929985"
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
   

