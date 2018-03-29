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
description: Microsoft 会定期会对 Skype 的一套新的设备的固件更新业务电话版中，您可以导入到您的服务器并向用户分发发布。 可以通过在 Microsoft 网站上转到帮助和支持页面，搜索 forPhone Edition.Download 最新的更新软件包获得最新的一套设备更新规则，并将文件提取到一个文件夹在计算机上更新将要上载。 在提取文件后，可以使用导入 CsDeviceUpdate cmdlet 导入中所提取的设备更新规则。CAB 文件 （它们将具有 UCUpdates.cab 的名称）。 有关详细信息，请参阅导入 CsDeviceUpdate。
ms.openlocfilehash: 584c04e8169eec4621c91c469127b99388f4820a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="device-update"></a>设备更新
 
Microsoft 会定期会对 Skype 的一套新的设备的固件更新业务电话版中，您可以导入到您的服务器并向用户分发发布。 可通过转至 Microsoft 网站上的帮助和支持页并搜索“Phone Edition”来获取一组最新的设备更新规则。 下载最新的更新包，并将文件解压缩到计算机上要从中上载更新的文件夹。 解压缩文件后，可以使用 **Import-CsDeviceUpdate** cmdlet 导入解压缩后的 .CAB 文件（其名称为 UCUpdates.cab）中包含的设备更新规则。 有关详细信息，请参阅[导入 CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)。
  
已导入设备更新规则后，可以使用**设备更新**页可以查看和管理这些规则为您的组织的设备。
  
> [!TIP]
> 您可以测试固件更新，然后将更新提供给组织中使用的所有相关设备（假定测试成功）。 
  
## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**设备更新**”页上执行以下任务：
  
- 批准列表中的设备更新。
    
- 取消或恢复挂起的设备更新。
    
- 从列表删除设备更新。
    
## <a name="ui-reference"></a>用户界面参考

下表介绍了该页上的菜单、命令、字段和属性。
  
- **编辑**可以使用此选项，请执行下列操作：
    
  - **选择全部**此选项在列表中选择设备的所有更新。
    
  - **删除**此选项将删除所有选定的设备更新。
    
- **操作**您可以从列表中选择一个或多个更新并执行以下操作：
    
  - **取消挂起的更新**此选项可防止所选的更新部署到您的组织的设备。
    
  - **批准**此选项允许所选的更新部署到您的组织的设备。
    
  - **还原**此选项允许在将其部署到您的组织的设备以前批准的更新
    
- **刷新**您可以刷新列表来验证所有设备更新的状态。
    
设备更新 Web 服务的详细信息，请参阅规划文档中[查看软件更新您组织中的设备](http://technet.microsoft.com/library/d2cca12b-ed43-4e1f-90ab-d14bca8b482c.aspx)。
## <a name="see-also"></a>另请参阅

#### 

[导入 CsDeviceUpdate](https://docs.microsoft.com/powershell/module/skype/import-csdeviceupdate?view=skype-ps)

