---
title: Skype for Business Server 2015 中的 DeRegisterType 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType 表是一个静态表, 用于存储可能的用户取消注册类型的列表, 例如 "客户端启动"、"注册过期" 或 "客户端已停止响应"。
ms.openlocfilehash: 794f8f98ffe20cd69b63fd2084fee38ed055d40f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296348"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 DeRegisterType 表
 
DeRegisterType 表是一个静态表, 用于存储可能的用户取消注册类型的列表, 例如 "客户端启动"、"注册过期" 或 "客户端已停止响应"。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || 允许的值: <br/>  0--未知 <br/>  1--客户发起的取消注册 <br/>  2--注册已过期 <br/>  3-客户端崩溃 <br/>  4--用户属性已更改 <br/>  5-首选注册机构已更改 <br/>  6--处于生存模式的旧客户端 <br/> |
   

