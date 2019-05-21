---
title: PurgeSettings table (QoE)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: 'PurgeSettings 表包含用于指定是否会自动从 QoE 数据库中删除过时的体验记录质量的信息。 请注意, 通过运行以下命令, 还可以从 Skype for Business 服务器管理外壳程序内获取清除相关信息:'
ms.openlocfilehash: ec957a445c59020e8909beeb8cb3dcd12f662d68
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294773"
---
# <a name="purgesettings-table-qoe"></a>PurgeSettings table (QoE)
 
PurgeSettings 表包含用于指定是否会自动从 QoE 数据库中删除过时的体验记录质量的信息。 请注意, 通过运行以下命令, 还可以从 Skype for Business 服务器管理外壳程序内获取清除相关信息:
  
```
Get-CsQoEConfiguration
```

此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primary  <br/> |QoE 清除设置集合的唯一标识符。  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||当设置为 True (1) 时, Microsoft Lync Server 2013 将定期从 QoE 数据库中清除过时的记录。 将在 PurgeHour 设置指定的圣多美中每天进行清除。 如果设置为 False (0), 将不会从数据库中自动清除记录。 默认值为 True。  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||指定将从数据库中清除的 QoE 记录的期限 (以天为单位): 如果启用清除, 将从数据库中删除早于此值的 QoE 记录。 默认值为60天。  <br/> |
|**PurgeHour** <br/> |int  <br/> ||指定每天执行数据库清除的本地时间。 该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。 请注意, 你只能指定一天中的小时数: 值 10 (表示 10:00 am) 是允许的值, 但不允许值 10.5 10:30 (表示 10:30 am)。 默认值为 1 (1:00 AM)。 指定每天执行数据库清除的本地时间。 该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。 请注意, 你只能指定一天中的小时数: 值 10 (表示 10:00 am) 是允许的值, 但不允许值 10.5 10:30 (表示 10:30 am)。 默认值为 1 (1:00 AM)。  <br/> |
   

