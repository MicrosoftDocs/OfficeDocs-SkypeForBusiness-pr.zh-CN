---
title: 角色表
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
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: 角色表是一个静态表，用于存储可能的会议角色（如与者会和演示者）的列表。
ms.openlocfilehash: 037197d12a83c5b79de22c0b7faef435d365da41
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635876"
---
# <a name="roles-table"></a>角色表
 
角色表是一个静态表，用于存储可能的会议角色（如与者会和演示者）的列表。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |主  <br/> ||
|**角色** <br/> |nvarchar (256)   <br/> || 允许的值： <br/>  0 -- 未知 <br/>  1 -- 演示者 <br/>  2 -- 与会者 <br/> |
   

