---
title: 在业务服务器 2015年的 Skype 的 DeRegisterType 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: DeRegisterType 表则存储可能的用户列表的静态表取消注册类型，例如客户机启动的、 注册过期，或客户端停止响应。
ms.openlocfilehash: 97b342a8d0175da0517aa36e0fea477e32df4dd9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a>在业务服务器 2015年的 Skype 的 DeRegisterType 表
 
DeRegisterType 表则存储可能的用户列表的静态表取消注册类型，例如客户机启动的、 注册过期，或客户端停止响应。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**DeRegisterTypeId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**DeRegisterReason** <br/> |nvarchar(256)  <br/> || 允许的值： <br/>  0--未知 <br/>  1-客户机启动注销 <br/>  2-注册过期 <br/>  3-客户端崩溃 <br/>  4-用户属性已更改 <br/>  5-首选注册器更改 <br/>  在生存模式下 6-旧客户端 <br/> |
   

