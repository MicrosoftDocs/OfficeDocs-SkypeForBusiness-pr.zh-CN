---
title: 设备日志配置编辑
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: 可以将设备日志配置添加到"编辑日志设置"页，该页确定在清除 日志文件 之前保留的最大日志缓存大小、最大 日志文件 大小或保留时间长度。 您可以根据组织的要求更改这些设置。
ms.openlocfilehash: a8d1ac8d85fa08461c8f43688e874371e6cb4f60
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386800"
---
# <a name="device-log-configuration-edit"></a>设备日志配置：编辑
 
可以将设备日志配置添加到"编辑日志设置"页，该页确定在清除 日志文件 之前保留的最大日志缓存大小、最大 日志文件 大小或保留的时间长度。 您可以根据组织的要求更改这些设置。
  
> [!CAUTION]
> 清除的文件将从文件系统中永久删除。清除文件后，将无法恢复。 
  
## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在"编辑日志设置"页上 **执行以下** 任务：
  
- 全局或为特定站点添加设备日志配置。
    
- 修改现有设备日志配置的选项。
    
## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。
  
- **范围** 标识设备 (配置) 全局或站点范围。
    
- **名称** 可以添加或修改设备日志配置的名称。
    
- **最大文件大小 (字节)** 可以指定在清除之前日志文件的最大大小。 默认值为 1，024，000 字节， (1 MB) 。
    
- **最大缓存大小 (字节)** 您可以指定在必须清除 () 数据并将数据写入 日志文件 之前，日志文件 缓存中可以保留的最大信息量（以字节日志文件）。 默认值为 512，000 字节 (0.5 MB) 。
    
- **刷新缓存的分钟数 (1-60)** 可以指定存储在缓存中日志文件信息写入实际缓存日志文件。 记录数据后，将清除缓存。 默认值为 5 分钟。
    
- **日志文件保留天数 (1-365)** 可以指定日志文件在清除之前保留的天数。 默认值为 10 天。
    
## <a name="see-also"></a>另请参阅

[设备日志配置](device-log-configuration.md)
