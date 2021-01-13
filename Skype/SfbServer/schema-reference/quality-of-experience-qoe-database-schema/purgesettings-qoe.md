---
title: 'QoE (PurgeSettings) '
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: PurgeSettings 表包含指定是否（以及何时）将过时的用户体验质量记录从 QoE 数据库中自动删除。 请注意，通过运行以下命令，还可以从 Skype for Business Server 命令行管理程序 内获取与清除有关的信息：
ms.openlocfilehash: eef723298b04aecf633368d767623488a53ac6ce
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815802"
---
# <a name="purgesettings-table-qoe"></a>QoE (PurgeSettings) 
 
PurgeSettings 表包含指定是否（以及何时）将过时的用户体验质量记录从 QoE 数据库中自动删除。 请注意，通过运行以下命令，还可以从 Skype for Business Server 命令行管理程序 内获取与清除有关的信息：
  
```PowerShell
Get-CsQoEConfiguration
```

此表在 Microsoft Lync Server 2013 中引入。
  
|**列**|**数据类型**|**键/索引**|**Details**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |主  <br/> |QoE 清除设置集合的唯一标识符。  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||设置为 True (1 时) Microsoft Lync Server 2013 将定期清除 QoE 数据库中的过时记录。 将每天在 PurgeHour 设置所指定的时间执行清除。 如果设置为 False (0)，则不会从数据库中自动清除记录。 默认值为 True。  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||指定将从数据库中清除的 QoE 记录的保留时间（以天为单位）：如果启用了清除，将从数据库中移除高于此值的 QoE 记录。默认值为 60 天。  <br/> |
|**PurgeHour** <br/> |int  <br/> ||指定将执行数据库清除的本地时间。将采用 24 小时制指定时间，其中 0 表示午夜 (12:00 AM)，23 表示 11:00 PM。请注意，您只能指定小时：允许值 10（指示 10:00 AM），但不允许值 10:30（即 10.5）（指示 10:30 AM）。默认值为 1 (1:00 AM)。  <br/> |
   

