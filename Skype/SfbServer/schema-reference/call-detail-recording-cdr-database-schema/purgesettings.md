---
title: PurgeSettings 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: 'PurgeSettings 表包含指定是否 (和何时) 过期的呼叫详细记录将从 CDR 数据库中自动删除的信息。 请注意, 通过运行以下命令, 还可以从 Skype for Business Server 2015 中获取清除相关信息:'
ms.openlocfilehash: 6aac92555dda6875f23a177bb09384f453369846
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295921"
---
# <a name="purgesettings-table"></a>PurgeSettings 表
 
PurgeSettings 表包含指定是否 (和何时) 过期的呼叫详细记录将从 CDR 数据库中自动删除的信息。 请注意, 通过运行以下命令, 还可以从 Skype for Business Server 2015 中获取清除相关信息:
  
```
Get-CsCdrConfiguration
```

管理员应将 PurgeSettings 表视为只读: 仅应使用[新的-CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)或[CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 进行对呼叫详细信息清除设置的更改。
  
此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**标识号** <br/> |int  <br/> |Primary  <br/> |CDR 清除设置集合的唯一标识符。  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||设置为 True (1) Skype for Business Server 2015 将定期从 CDR 数据库中清除过时的记录。 将在 PurgeHour 设置指定的圣多美中每天进行清除。 如果设置为 False (0), 将不会从数据库中自动清除记录。 默认值为 True。  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||指定将从数据库中清除的 CDR 记录的保留时间 (以天为单位): 如果启用清除, 则早于此值的 CDR 记录将从数据库中删除。 默认值为60天。  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||指定将从数据库中清除的错误报告记录的保留时间 (以天为单位): 如果启用清除, 则早于此值的错误报告记录将从数据库中删除。 默认值为60天。  <br/> |
|**PurgeHour** <br/> |int  <br/> ||指定每天执行数据库清除的本地时间。 该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。 请注意, 你只能指定一天中的小时数: 值 10 (表示 10:00 am) 是允许的值, 但不允许值 10.5 10:30 (表示 10:30 am)。 默认值为 2 (2:00 AM)。  <br/> |
   

