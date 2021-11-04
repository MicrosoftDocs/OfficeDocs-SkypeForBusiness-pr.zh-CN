---
title: PurgeSettings 表
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9ff2c8fc-4ae8-4f22-96a8-1f4d5eecbf2d
description: PurgeSettings 表包括用于指定是否（以及何时）自动从 CDR 数据库中删除过时的呼叫详细信息记录的信息。 请注意，通过运行以下命令，也可以从 Skype for Business Server 2015 内获取清除相关信息：
ms.openlocfilehash: a2b5bc874f6145a121cfb8a43702ab55ab0a5e1d
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60763310"
---
# <a name="purgesettings-table"></a>PurgeSettings 表
 
PurgeSettings 表包括用于指定是否（以及何时）自动从 CDR 数据库中删除过时的呼叫详细信息记录的信息。 请注意，通过运行以下命令，也可以从 Skype for Business Server 2015 内获取清除相关信息：
  
```PowerShell
Get-CsCdrConfiguration
```

管理员应将 PurgeSettings 表视为只读：只能使用 [New-CsCdrConfiguration](/powershell/module/skype/new-cscdrconfiguration?view=skype-ps) 或 [Set-CsCdrConfiguration](/powershell/module/skype/set-cscdrconfiguration?view=skype-ps) cmdlet 更改呼叫详细信息清除设置。
  
此表在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**Id** <br/> |int  <br/> |主  <br/> |CDR 清除设置集的唯一标识符。  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||设置为 True 时 (1) Skype for Business Server 2015 将定期清除 CDR 数据库中的过时记录。 将每天在 PurgeHour 设置所指定的时间执行清除。 如果设置为 False (0)，则不会从数据库中自动清除记录。 默认值为 True。  <br/> |
|**KeepCallDetailForDays** <br/> |int  <br/> ||指定将从数据库中清除的 CDR 记录的时限（以天为单位）：如果启用清除，则将从数据库中清除时限超过此值的 CDR 记录。默认值为 60 天。  <br/> |
|**KeepErrorReportForDays** <br/> |int  <br/> ||指定将从数据库中清除的错误报告记录的时限（以天为单位）：如果启用清除，则将从数据库中清除时限超过此值的错误报告记录。默认值为 60 天。  <br/> |
|**PurgeHour** <br/> |int  <br/> ||指定将执行数据库清除的本地时间。时间以 24 小时制的形式指定，0 表示午夜 (12:00 AM)，23 表示 11:00 PM。请注意，您只能指定小时时间：允许值 10（指示 10:00 AM），但不允许值 10.5（指示 10:30 AM）。默认值为 2 (2:00 AM)。  <br/> |
