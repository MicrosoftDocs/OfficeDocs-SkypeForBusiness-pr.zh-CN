---
title: Skype for Business Server 2015 中的 DeRegisterType 表
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
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType 表是一个静态表，用于存储可能的用户注销类型（如"客户端已启动"、"注册已过期"或"客户端停止响应"）的列表。
ms.openlocfilehash: 388aebc1ac180e1298addd54859cff6759b28be0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816072"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 DeRegisterType 表
 
DeRegisterType 表是一个静态表，用于存储可能的用户注销类型（如"客户端已启动"、"注册已过期"或"客户端停止响应"）的列表。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |主  <br/> ||
|**DeRegisterReason** <br/> |nvarchar (256)   <br/> || 允许的值： <br/>  0 -- 未知 <br/>  1 -- 客户端启动的取消注册 <br/>  2 -- 注册过期 <br/>  3 - 客户端崩溃 <br/>  4 -- 用户属性已更改 <br/>  5 - 首选注册器已更改 <br/>  6 -- 旧客户端处于生存模式 <br/> |
   

