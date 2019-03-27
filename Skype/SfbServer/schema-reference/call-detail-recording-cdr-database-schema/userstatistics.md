---
title: UserStatistics 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: UserStatistics 表是一个支持表。 每个表中的记录存储有关单个用户的使用情况的系统的信息。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 45f34a1e8905d19b5ce48d94824591f25ec1ef28
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30883593"
---
# <a name="userstatistics-table"></a>UserStatistics 表
 
UserStatistics 表是一个支持表。 每个表中的记录存储有关单个用户的使用情况的系统的信息。 此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**用户 Id** <br/> |int  <br/> |Primary  <br/> |标识此用户的唯一编号。  <br/> |
|**LastLogInTime** <br/> |datetime  <br/> ||最后一次用户身份登录。  <br/> |
|**LastConfOrganizedTime** <br/> |datetime  <br/> ||最后一次用户组织会议。  <br/> |
|**LastCallOrganizerCallFailureTime** <br/> |datetime  <br/> ||最后一次用户遇到呼叫失败。  <br/> |
|**LastConfOrganizerCallFailureTime** <br/> |datetime  <br/> ||最后一次用户作为会议组织者遇到呼叫失败。  <br/> |
   

