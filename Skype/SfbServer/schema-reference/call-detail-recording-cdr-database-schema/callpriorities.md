---
title: CallPriorities 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 043b63ae-2d64-4f38-a0df-18aa08d6caf5
description: CallPriorities 表是一个静态表，用于存储可能的呼叫优先级，例如紧急、 紧迫或正常列表。
ms.openlocfilehash: aac21073e98d7c1ef8d137a736445b62e4fb9878
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901527"
---
# <a name="callpriorities-table-in-skype-for-business-server-2015"></a>CallPriorities 表中的业务服务器 2015 Skype
 
CallPriorities 表是一个静态表，用于存储可能的呼叫优先级，例如紧急、 紧迫或正常列表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**PriorityId** <br/> |tinyint  <br/> |Primary  <br/> ||
|**优先级** <br/> |nvarchar(256)  <br/> || 允许的值： <br/>  0-未知 <br/>  1-非紧迫 <br/>  2-普通 <br/>  3-紧急 <br/>  4-紧急 <br/> |
   

