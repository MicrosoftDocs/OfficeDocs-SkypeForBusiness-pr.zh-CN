---
title: PurgeSettings 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: PurgeSettings 表中的信息，如果 （并且当） 指定将自动从 CDR 数据库中删除过时的呼叫详细记录。 请注意，清除相关信息也可以获得从在 Skype 的业务服务器 2015年通过运行以下命令：
ms.openlocfilehash: a28ac592fb1d5d2001e7f297f37fdc1938f25643
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="purgesettings-table"></a>PurgeSettings 表
 
PurgeSettings 表中的信息，如果 （并且当） 指定将自动从 CDR 数据库中删除过时的呼叫详细记录。 请注意，清除相关信息也可以获得从在 Skype 的业务服务器 2015年通过运行以下命令：
  
```
Get-CsCdrConfiguration
```

管理员应以只读方式处理 PurgeSettings 表： 只应使用[New CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)或[设置 CsCdrConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 进行呼叫细节清除设置的更改。
  
在 Microsoft Lync Server 2013 引入了此表。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**标识** <br/> |int  <br/> |Primary  <br/> |唯一标识符集合的 CDR 清除设置。  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||如果设置为 True (1) Skype 的业务服务器 2015年将定期清除过时的 CDR 数据库中的记录。 清除操作会在圣多美 PurgeHour 设置所指定的每一天。 如果设置为 False (0) 然后记录将不会自动清除数据库中。 默认值为 True。  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||指定的时间 （以天为单位） 将从数据库中清除的 CDR 记录： 如果启用了清除，将从数据库中删除早于此值的 CDR 记录。 默认值为 60 天。  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||指定将从数据库中清除的错误报告记录 （以天为单位） 的年龄： 如果启用了清除，将从数据库中删除早于此值的错误报告记录。 默认值为 60 天。  <br/> |
|**PurgeHour** <br/> |int  <br/> ||指定当数据库清除将会发生一天的当地时间。 该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。 请注意，您可以只指定一天中的小时： 允许值 （指示上午 10:00） 10，但不是允许的值为 10:30 的 10.5 （指明上午 10:30）。 默认值为 2 (2:00 AM)。  <br/> |
   

