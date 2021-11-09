---
title: Skype for Business Server 2015 中的 CallPriorities 表
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
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 表是一个静态表，用于存储可能的呼叫优先级列表，例如"紧急"、"紧急"或"正常"。
ms.openlocfilehash: ed31d55852f0b685429bd7fbf70cff1bf81d63ae
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60845135"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 CallPriorities 表
 
CallPriorities 表是一个静态表，用于存储可能的呼叫优先级列表，例如"紧急"、"紧急"或"正常"。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |主  <br/> ||
|**优先级** <br/> |nvarchar (256)   <br/> || 允许的值： <br/>  0 -- 未知 <br/>  1 - 非紧急 <br/>  2 – 普通 <br/>  3 – 紧急 <br/>  4 – 紧迫 <br/> |
   

