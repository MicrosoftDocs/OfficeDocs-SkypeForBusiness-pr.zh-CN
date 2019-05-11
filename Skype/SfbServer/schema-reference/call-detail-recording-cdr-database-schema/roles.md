---
title: Roles 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: 角色表是一个静态表，用于存储可能的会议角色，如与会者和演示者列表。
ms.openlocfilehash: e0088d059d6e4ed536e5f52e1290211377438889
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930302"
---
# <a name="roles-table"></a>Roles 表
 
角色表是一个静态表，用于存储可能的会议角色，如与会者和演示者列表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**RoleId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**角色** <br/> |nvarchar(256)  <br/> || 允许的值： <br/>  0-未知 <br/>  1-演示者 <br/>  2-与会者 <br/> |
   

