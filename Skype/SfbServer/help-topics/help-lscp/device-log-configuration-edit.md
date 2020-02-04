---
title: 设备日志配置编辑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: 你可以将设备日志配置添加到 "编辑日志" 设置页面，该页面确定日志文件的最大日志大小、最大日志文件大小或在清除之前保留日志文件的时间长度。 您可以根据组织的要求更改这些设置。
ms.openlocfilehash: 069548626972f8daf73f1863ec08f302bf20e082
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41700307"
---
# <a name="device-log-configuration-edit"></a>设备日志配置：编辑
 
你可以将设备日志配置添加到 "**编辑日志" 设置**页面，该页面确定日志文件的最大日志大小、最大日志文件大小或在清除之前保留日志文件的时间长度。 您可以根据组织的要求更改这些设置。
  
> [!CAUTION]
> 清除的文件将从文件系统中永久删除。清除文件后，将无法恢复。 
  
## <a name="tasks-you-can-perform"></a>可执行的任务

可以在 "**编辑日志设置**" 页面上执行以下任务：
  
- 全局或特定网站添加设备日志配置。
    
- 修改现有设备日志配置的选项。
    
## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。
  
- **范围**标识设备日志配置的作用域（全局或网站）。
    
- **名称**你可以添加或修改设备日志配置的名称。
    
- **最大文件大小（字节）** 你可以指定日志文件在清除之前可以达到的最大大小。 默认值为1024000字节（1 MB）。
    
- **最大缓存大小（字节）** 你可以指定必须在日志文件缓存中保留的最大信息量（以字节为单位），然后才能在该缓存中清除，并将数据写入日志文件。 默认值为512000字节（0.5 MB）。
    
- **刷新缓存的分钟数（1-60）** 你可以指定日志文件缓存中存储的信息写入实际日志文件的频率。 记录数据后，将清除缓存。 默认值为5分钟。
    
- **保留日志文件的天数（1-365）** 你可以指定在清除日志文件之前保留日志文件的天数。 默认值为10天。
    
## <a name="see-also"></a>另请参阅

[设备日志配置](device-log-configuration.md)
