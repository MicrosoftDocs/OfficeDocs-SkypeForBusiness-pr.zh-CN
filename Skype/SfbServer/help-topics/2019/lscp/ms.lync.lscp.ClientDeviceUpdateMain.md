---
title: 设备更新
ms.author: laurawi
author: LauraWi
manager: serdars
ms.date: 3/23/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.ClientDeviceUpdateMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6f6b7f73-f8f5-41dc-9e2a-727baaaa828b
description: Microsoft 会定期会的 Skype 的一组新的设备固件更新业务 Phone edition，您可以导入到您的服务器，并将分发给用户发布。 您可以通过 Microsoft 网站上转到帮助和支持页上，并搜索 forPhone Edition.Download 的最新的更新程序包获取最新的设备更新规则集，并将文件提取到的文件夹的计算机上，更新要上载。 在提取文件后，可以使用 Import-csdeviceupdate cmdlet 导入设备更新规则中提取找到。CAB 文件 （后者会名称 UCUpdates.cab）。 有关详细信息，请参阅 Import-csdeviceupdate。
ms.openlocfilehash: 584c04e8169eec4621c91c469127b99388f4820a
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="device-update"></a>设备更新
 
Microsoft 会定期会的 Skype 的一组新的设备固件更新业务 Phone edition，您可以导入到您的服务器，并将分发给用户发布。 可通过转至 Microsoft 网站上的帮助和支持页并搜索“Phone Edition”来获取一组最新的设备更新规则。 下载最新的更新包，并将文件解压缩到计算机上要从中上载更新的文件夹。 解压缩文件后，可以使用 **Import-CsDeviceUpdate** cmdlet 导入解压缩后的 .CAB 文件（其名称为 UCUpdates.cab）中包含的设备更新规则。 有关详细信息，请参阅[Import-csdeviceupdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)。
  
已导入设备更新规则之后，您可以使用**设备更新**页上查看和管理组织的设备的各个规则。
  
> [!TIP]
> 您可以测试固件更新，然后将更新提供给组织中使用的所有相关设备（假定测试成功）。 
  
## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**设备更新**”页上执行以下任务：
  
- 批准列表中的设备更新。
    
- 取消或恢复挂起的设备更新。
    
- 从列表删除设备更新。
    
## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。
  
- **编辑**您可以使用此选项可执行下列操作：
    
  - **选择全部**此选项可选择列表中所有设备更新。
    
  - **删除**此选项可删除所有选定的设备更新。
    
- **操作**您可以在列表中选择一个或多个更新并执行以下操作：
    
  - **取消挂起更新**此选项阻止向组织设备部署所选的更新。
    
  - **批准**此选项允许向组织设备部署所选的更新。
    
  - **还原**此选项允许向组织设备部署之前批准的更新
    
- **刷新**您可以刷新列表以验证所有设备更新的状态。
    
有关设备更新 Web 服务的详细信息，请参阅规划文档中的[View Software Updates for Devices in Your Organization](http://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx) 。
## <a name="see-also"></a>另请参阅

#### 

[Import-csdeviceupdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)

