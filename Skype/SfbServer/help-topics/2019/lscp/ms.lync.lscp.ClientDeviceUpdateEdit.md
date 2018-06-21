---
title: 设备日志配置编辑
ms.author: SerdarS
author: SerdarSoysal
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e534e6a5-fb3e-40b1-a189-fce64c42f512
description: 您可以向编辑日志设置页上，确定最大日志缓存大小、 最大日志文件大小或在被清除之前保留日志文件的时间长度添加设备日志配置。 您可以更改这些设置根据贵组织的要求。
ms.openlocfilehash: 712ba87ab19d2b69792ba720e984d64dd4aac478
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/20/2018
ms.locfileid: "19972327"
---
# <a name="device-log-configuration-edit"></a>设备日志配置： 编辑
 
您可以向**编辑日志设置**页上，确定最大日志缓存大小、 最大日志文件大小或在被清除之前保留日志文件的时间长度添加设备日志配置。 您可以更改这些设置根据贵组织的要求。
  
> [!CAUTION]
> 清除的文件将从文件系统中永久删除。清除文件后，将无法恢复。 
  
## <a name="tasks-you-can-perform"></a>可执行的任务

在**编辑日志设置**页上，可以执行以下任务：
  
- 在全局范围或针对特定站点添加设备日志配置。
    
- 修改现有设备日志配置的选项。
    
## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。
  
- **范围**标识设备日志配置的范围 （全局或站点）。
    
- **名称**您可以添加或修改设备日志配置的名称。
    
- **最大文件大小 （字节）** 您可以指定日志文件在被清除之前可以成为的最大大小。 默认值为 1,024,000 字节 (1 MB)。
    
- **最大缓存大小 （字节）** 您可以指定的最大量 （以字节为单位） 必须清除缓存和数据写入到日志文件可以之前日志文件缓存中保留的信息。 默认值为 512,000 字节 (0.5 MB)。
    
- **分钟时间来刷新缓存 (1-60)** 您可以指定频率存储在日志文件缓存的信息写入实际的日志文件。 数据记录后，将清除缓存。 默认值为 5 分钟。
    
- **天数保留日志文件 (1-365)** 您可以指定清除之前保留的日志文件的天数。 默认值为 10 天。
    
## <a name="see-also"></a>另请参阅

[设备日志配置](ms.lync.lscp.ClientDeviceCfgMain.md)