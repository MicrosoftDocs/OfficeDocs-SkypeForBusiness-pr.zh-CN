---
title: 设备配置编辑日志
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: 确定最大日志高速缓存大小、 最大的日志文件大小或日志文件在被清除之前的保留的时间长度的编辑日志设置页，您可以添加设备日志配置。 您可以更改这些设置，根据您的组织的要求。
ms.openlocfilehash: 8003014f7b94824d0ef36a8d1328c6430e98d894
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="device-log-configuration-edit"></a>设备日志配置： 编辑
 
确定最大日志高速缓存大小、 最大的日志文件大小或日志文件在被清除之前的保留的时间长度的**编辑日志设置**页，您可以添加设备日志配置。 您可以更改这些设置，根据您的组织的要求。
  
> [!CAUTION]
> 清除的文件将从文件系统中永久删除。清除文件后，将无法恢复。 
  
## <a name="tasks-you-can-perform"></a>可执行的任务

在**编辑日志设置**页上，可以执行以下任务：
  
- 在全局范围内或针对某一特定站点添加设备日志配置。
    
- 修改现有设备日志配置的选项。
    
## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。
  
- **作用域**标识设备日志配置的范围 （全局或站点）。
    
- **名称**您可以添加或修改日志配置，设备的名称。
    
- **最大文件大小 （字节）**您可以指定日志文件可能会在被清除之前的最大大小。 默认值为 1,024,000 字节 (1 MB)。
    
- **最大高速缓存大小 （字节）**您可以指定的最大金额中可以保存日志文件缓存之前，必须清除缓存并将数据写入到日志文件的信息 （以字节为单位）。 默认值为 512,000 字节 (0.5 MB)。
    
- **分钟的时间来刷新缓存 (1-60)**您可以指定频率日志文件缓存中所存储的信息写入实际的日志文件。 数据记录后，缓存将被清除。 默认值为 5 分钟。
    
- **天若要保留日志文件 (1-365)**您可以指定清除之前，日志文件将保留的天数。 默认值是 10 天。
    
## <a name="see-also"></a>另请参阅

#### 

[设备日志配置](device-log-configuration.md)

