---
title: 角色表
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
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
ms.openlocfilehash: 67faf16a478a8ca1f4c2f3bc21bd5d4a6f28909f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60842644"
---
# <a name="roles-table"></a>角色表
 
角色表是一个静态表，用于存储可能的会议角色（如与者会和演示者）的列表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |主  <br/> ||
|**角色** <br/> |nvarchar (256)   <br/> || 允许的值： <br/>  0 -- 未知 <br/>  1 -- 演示者 <br/>  2 -- 与会者 <br/> |
   

