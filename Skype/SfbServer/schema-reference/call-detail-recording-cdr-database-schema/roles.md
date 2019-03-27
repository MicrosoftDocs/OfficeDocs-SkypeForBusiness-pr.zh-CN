---
title: Roles 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: 角色表是一个静态表，用于存储可能的会议角色，如与会者和演示者列表。
ms.openlocfilehash: 2b7759cc600471a8bf1b989ce429f6b2a4149ee0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891711"
---
# <a name="roles-table"></a>Roles 表
 
角色表是一个静态表，用于存储可能的会议角色，如与会者和演示者列表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**角色** <br/> |nvarchar(256)  <br/> || 允许的值： <br/>  0-未知 <br/>  1-演示者 <br/>  2-与会者 <br/> |
   

