---
title: Skype for Business Server 2015 中的 CallPriorities 表
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
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 表是一个静态表，用于存储可能的呼叫优先级列表，例如"紧急"、"紧急"或"正常"。
ms.openlocfilehash: 0538af29f73c5e01d67dd61fe2ff304cd45f82ce
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58635926"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 CallPriorities 表
 
CallPriorities 表是一个静态表，用于存储可能的呼叫优先级列表，例如"紧急"、"紧急"或"正常"。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |主  <br/> ||
|**优先级** <br/> |nvarchar (256)   <br/> || 允许的值： <br/>  0 -- 未知 <br/>  1 - 非紧急 <br/>  2 – 普通 <br/>  3 – 紧急 <br/>  4 – 紧迫 <br/> |
   

