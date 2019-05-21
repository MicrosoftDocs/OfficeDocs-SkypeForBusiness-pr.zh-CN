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
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 表是一个静态表, 用于存储可能的调用优先级列表, 例如 "紧急"、"紧急" 或 "正常"。
ms.openlocfilehash: 6d324ce11b2e149378b6275441cb4a2467a641db
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296565"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>Skype for Business Server 2015 中的 CallPriorities 表
 
CallPriorities 表是一个静态表, 用于存储可能的调用优先级列表, 例如 "紧急"、"紧急" 或 "正常"。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**优先级** <br/> |nvarchar(256)  <br/> || 允许的值: <br/>  0-未知 <br/>  1-非紧急 <br/>  2-正常 <br/>  3-紧急 <br/>  4-紧急情况 <br/> |
   

