---
title: 设备日志配置
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceCfgMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c9b81f20-ce8c-40f1-8bed-50775cc35e58
description: 设备更新 Web 服务会自动创建记录设备更新活动的日志文件。 作为您的组织的数据管理策略的一部分，您可以对日志数据的高速缓存大小、 日志文件大小或的日志文件在被清除之前的保留的时间长度设置阈值。 您可以更改这些设置，根据您的组织的要求。 如果不希望设备更新 Web 服务自动清除日志文件，可以根据需要进行手动清除。 可以在全局范围或针对每个站点更改日志设置。
ms.openlocfilehash: e5a88c7437b654846fd464133b953465cd5d3e2a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="device-log-configuration"></a>设备日志配置
 
设备更新 Web 服务会自动创建记录设备更新活动的日志文件。 作为您的组织的数据管理策略的一部分，您可以对日志数据的高速缓存大小、 日志文件大小或的日志文件在被清除之前的保留的时间长度设置阈值。 您可以更改这些设置，根据您的组织的要求。 如果不希望设备更新 Web 服务自动清除日志文件，可以根据需要进行手动清除。 可以在全局范围或针对每个站点更改日志设置。
  
> [!NOTE]
> 您还可以配置某个时间您配置要保留日志文件 （默认情况下，即是 10 天以前的日志文件） 的服务时所需设备更新 Web 服务来自动删除早于天数的日志文件的一天。 不能使用 Skype 业务服务器控件面板修改此设置。 相反，您必须使用业务服务器管理外壳 Skype。 若要指定一天中删除过期的日志文件的时间，请用-LogCleanUpTimeOfDay 参数使用**New CsDeviceUpdateConfiguration** cmdlet。 有关详细信息，请参阅[新建 CsDeviceUpdateConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csdeviceupdateconfiguration?view=skype-ps)。 
  
> [!CAUTION]
> 清除的文件将从文件系统中永久删除。清除文件后，将无法恢复。 
  
## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**设备日志配置**”页上执行以下任务：
  
- 在全局范围或针对特定站点或池添加设备日志配置。
    
- 修改现有设备日志配置的选项。
    
## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。
  
- **新**您可以添加新的设备日志配置具有以下作用：
    
  - 全局
    
  - 站点
    
- **编辑**您可以更改设备日志配置列表中的选项。 使用此选项，可以执行以下操作：
    
  - **显示详细信息**此选项将打开一个对话框，您可以在其中更改设备日志配置的选项。
    
  - **选择全部**此选项在列表中选择所有设备日志配置。
    
  - **删除**此选项将删除所有选定的设备日志配置。
    
- **刷新**您可以刷新设备日志配置列表来验证所有设备日志配置选项的状态。
    
## <a name="see-also"></a>另请参阅

#### 

[修改设备更新活动的日志文件的设置](http://technet.microsoft.com/library/9b57f126-1853-43b3-bbd4-06401e6498bd.aspx)

