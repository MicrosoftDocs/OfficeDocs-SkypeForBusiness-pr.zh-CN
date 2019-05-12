---
title: PurgeSettings 表 (QoE)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 31b85d1c-3f32-4f67-94bf-9389cdd282c5
description: PurgeSettings 表包含用于指定是否 （以及何时） 的信息将自动从 QoE 数据库中删除过时的用户体验质量记录。 请注意，清除相关的信息也可以获得从 Skype 内的业务 Server 命令行管理程序通过运行以下命令：
ms.openlocfilehash: 2b78f066907d6d0763fab7faa9d378e51f3715fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924785"
---
# <a name="purgesettings-table-qoe"></a>PurgeSettings 表 (QoE)
 
PurgeSettings 表包含用于指定是否 （以及何时） 的信息将自动从 QoE 数据库中删除过时的用户体验质量记录。 请注意，清除相关的信息也可以获得从 Skype 内的业务 Server 命令行管理程序通过运行以下命令：
  
```
Get-CsQoEConfiguration
```

此表是在 Microsoft Lync Server 2013 中引入的。
  
|**列**|**数据类型**|**键/索引**|**详细信息**|
|:-----|:-----|:-----|:-----|
|**ID** <br/> |int  <br/> |Primary  <br/> |唯一标识符集合的 QoE 清除设置。  <br/> |
|**EnablePurge** <br/> |bit  <br/> ||当设置为 True （1) Microsoft Lync Server 2013 定期将从 QoE 数据库清除过期的记录。 清除会发生在圣多美 PurgeHour 设置所指定的每一天。 如果设置为 False (0) 然后记录不会自动清除从数据库中。 默认值为 True。  <br/> |
|**KeepQoEDataForDays** <br/> |int  <br/> ||指定将从数据库清除的 QoE 记录 （以天为单位） 的期限： 如果启用清除，则将从数据库中删除早于此值的 QoE 记录。 默认值为 60 天。  <br/> |
|**PurgeHour** <br/> |int  <br/> ||指定当数据库清除将进行本地时间。 该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。 请注意，您可以仅指定一天的： 允许的值为 10 （指示上午 10:00），但不是允许的值为 10:30 的 10.5 （指示上午 10:30）。 默认值为 1 (1:00)。 指定当数据库清除将进行本地时间。 该时间使用 24 小时制格式指定，0 表示午夜（晚上 12:00），23 表示晚上 11:00。 请注意，您可以仅指定一天的： 允许的值为 10 （指示上午 10:00），但不是允许的值为 10:30 的 10.5 （指示上午 10:30）。 默认值为 1 (1:00)。  <br/> |
   

