---
title: PurgeSettings 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: PurgeSettings 表包含用于指定是否 （以及何时） 的信息将自动从 CDR 数据库中删除过时的呼叫详细记录。 请注意，清除相关的信息也可以获得从 Skype 内的业务服务器 2015年通过运行以下命令：
ms.openlocfilehash: f1e982d50ab029ec2756e8fb4a92f5c01dc327b8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930719"
---
# <a name="purgesettings-table"></a>PurgeSettings 表
 
PurgeSettings 表包含用于指定是否 （以及何时） 的信息将自动从 CDR 数据库中删除过时的呼叫详细记录。 请注意，清除相关的信息也可以获得从 Skype 内的业务服务器 2015年通过运行以下命令：
  
```
Get-CsCdrConfiguration
```

管理员应将 PurgeSettings 表视为只读： 仅应使用[New-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscdrconfiguration?view=skype-ps)或[Set-cscdrconfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 进行更改呼叫详细信息清除设置。
  
此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**Id** <br/> |int  <br/> |Primary  <br/> |清除设置集合的 CDR 的唯一标识符。  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||当设置为 True (1) 的 Skype 业务服务器 2015年将定期清除过时的 CDR 数据库中的记录。 清除会发生在圣多美 PurgeHour 设置所指定的每一天。 如果设置为 False (0) 然后记录不会自动清除从数据库中。 默认值为 True。  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||指定将从数据库清除的 CDR 记录 （以天为单位） 的期限： 如果启用清除，则将从数据库中删除 CDR 记录超过此值。 默认值为 60 天。  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||指定将从数据库清除的错误报告记录 （以天为单位） 的期限： 如果启用清除，则将从数据库中删除错误报告记录超过此值。 默认值为 60 天。  <br/> |
|**PurgeHour** <br/> |int  <br/> ||指定当数据库清除将进行本地时间。 该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。 请注意，您可以仅指定一天的： 允许的值为 10 （指示上午 10:00），但不是允许的值为 10:30 的 10.5 （指示上午 10:30）。 默认值为 2 (2:00 AM)。  <br/> |
   

