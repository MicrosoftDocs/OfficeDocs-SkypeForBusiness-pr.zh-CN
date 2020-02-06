---
title: Skype for Business Server 2015 中的 CallPriorities 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 表是一个静态表，用于存储可能的调用优先级列表，例如 "紧急"、"紧急" 或 "正常"。
ms.openlocfilehash: 57ab4c2b190b14d26a7f8be1791eb70473f1eb3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815440"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 CallPriorities 表
 
CallPriorities 表是一个静态表，用于存储可能的调用优先级列表，例如 "紧急"、"紧急" 或 "正常"。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**优先级** <br/> |nvarchar(256)  <br/> || 允许的值： <br/>  0-未知 <br/>  1-非紧急 <br/>  2-正常 <br/>  3-紧急 <br/>  4-紧急情况 <br/> |
   

