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
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: 角色表是一个静态表，用于存储可能的会议角色（如与者会和演示者）的列表。
ms.openlocfilehash: 56582f5f90693f4156f050ff20558a2bac440b8f531f8ee0076b258755f0fa26
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54302266"
---
# <a name="roles-table"></a>角色表
 
角色表是一个静态表，用于存储可能的会议角色（如与者会和演示者）的列表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |主  <br/> ||
|**角色** <br/> |nvarchar (256)   <br/> || 允许的值： <br/>  0 -- 未知 <br/>  1 -- 演示者 <br/>  2 -- 与会者 <br/> |
   

