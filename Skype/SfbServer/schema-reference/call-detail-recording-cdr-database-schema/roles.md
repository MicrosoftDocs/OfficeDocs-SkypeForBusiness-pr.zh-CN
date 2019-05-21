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
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: Roles 表是一个静态表, 它存储了可能的会议角色 (如与会者和演示者) 的列表。
ms.openlocfilehash: 2cf1fb22230d92951df0b3b8e18a5bd666c73519
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295893"
---
# <a name="roles-table"></a>Roles 表
 
Roles 表是一个静态表, 它存储了可能的会议角色 (如与会者和演示者) 的列表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**角色** <br/> |nvarchar(256)  <br/> || 允许的值: <br/>  0-未知 <br/>  1-演示者 <br/>  2-与会者 <br/> |
   

