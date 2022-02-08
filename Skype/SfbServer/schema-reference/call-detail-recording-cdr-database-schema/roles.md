---
title: 角色表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: 角色表是一个静态表，用于存储可能的会议角色（如与者会和演示者）的列表。
ms.openlocfilehash: 38999dd3d90dc39ac2afea9c667224f73da7208c
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62394864"
---
# <a name="roles-table"></a>角色表
 
角色表是一个静态表，用于存储可能的会议角色（如与者会和演示者）的列表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |主  <br/> ||
|**角色** <br/> |nvarchar (256)   <br/> || 允许的值： <br/>  0 -- 未知 <br/>  1 -- 演示者 <br/>  2 -- 与会者 <br/> |
   

