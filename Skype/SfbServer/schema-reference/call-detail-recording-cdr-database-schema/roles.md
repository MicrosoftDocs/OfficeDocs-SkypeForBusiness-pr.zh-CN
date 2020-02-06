---
title: Roles 表
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Roles 表是一个静态表，它存储了可能的会议角色（如与会者和演示者）的列表。
ms.openlocfilehash: 8ebd01bc9cc51b33d28f87aa85be1473a6397201
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814930"
---
# <a name="roles-table"></a>Roles 表
 
Roles 表是一个静态表，它存储了可能的会议角色（如与会者和演示者）的列表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**角色** <br/> |nvarchar(256)  <br/> || 允许的值： <br/>  0-未知 <br/>  1-演示者 <br/>  2-与会者 <br/> |
   

