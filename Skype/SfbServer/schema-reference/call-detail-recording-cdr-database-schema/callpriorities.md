---
title: 在业务服务器 2015年的 Skype 的 CallPriorities 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 表是一个静态的表来存储可能调用优先级，如紧急的紧急或标准列表。
ms.openlocfilehash: ccd92857015e865e36cbef4147c4355369263e90
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>在业务服务器 2015年的 Skype 的 CallPriorities 表
 
CallPriorities 表是一个静态的表来存储可能调用优先级，如紧急的紧急或标准列表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**优先级** <br/> |nvarchar(256)  <br/> || 允许的值： <br/>  0-未知 <br/>  1-非紧急 <br/>  2-正常 <br/>  3-紧急 <br/>  4-紧急情况 <br/> |
   

