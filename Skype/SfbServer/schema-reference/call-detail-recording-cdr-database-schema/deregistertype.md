---
title: DeRegisterType 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType 表是用户的一个静态表，用于存储可能列表取消注册类型，如客户端已启动、 注册过期或客户端停止响应。
ms.openlocfilehash: 958de5dd537f391ca75936ad86a84cb6fed0778d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901171"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>DeRegisterType 表中的业务服务器 2015 Skype
 
DeRegisterType 表是用户的一个静态表，用于存储可能列表取消注册类型，如客户端已启动、 注册过期或客户端停止响应。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || 允许的值： <br/>  0-未知 <br/>  1--客户端启动注销 <br/>  2--注册过期 <br/>  3-客户端崩溃 <br/>  4--用户属性已更改 <br/>  5 – 首选注册器已更改 <br/>  6--旧客户端处于生存模式 <br/> |
   

