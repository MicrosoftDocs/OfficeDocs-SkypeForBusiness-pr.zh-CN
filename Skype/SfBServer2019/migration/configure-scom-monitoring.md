---
title: 配置 SCOM 监控
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 迁移到 Microsoft Skype for Business Server 2019 后，必须完成一些任务来配置 Skype for business Server 2019，才能使用 System Center Operations Manager。
ms.openlocfilehash: aa782f2ef51e3397d465b1cd0f914783d371eded
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989587"
---
# <a name="configure-scom-monitoring"></a>配置 SCOM 监控

迁移到 Skype for business Server 2019 后，您必须完成一些任务来配置 Skype for Business Server 2019，才能使用 System Center Operations Manager。
  
- 将更新应用到选择的服务器以管理集中发现逻辑。
    
- 更新中央发现候选服务器注册表项。
    
- 将您的主 System Center Operations Manager 管理服务器配置为替代候选中央发现节点。
    
下面提供了有关执行其中每项任务的说明。
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>将更新应用到选择的服务器以管理集中发现逻辑。

1. 选择安装了 System Center Operations Manager 代理文件的服务器，并将其配置为候选发现节点。 
    
2. 将更新应用到此服务器。 请参阅主题[应用更新](apply-updates.md)。
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>更新中央发现候选服务器注册表项。

1. 在选择了管理中心发现逻辑的服务器上，打开 Windows PowerShell 命令窗口。 
    
2. 在命令行中键入：
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > 编辑注册表时，如果注册表项已存在，则可能会遇到错误：命令失败。 如果遇到这种情况，您可以安全地忽略该错误。 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>将您的主 System Center Operations Manager 管理服务器配置为替代候选中央发现观察程序节点。

1. 在已安装 System Center Operations Manager 控制台的计算机上，展开 "**管理包对象**"，然后选择 "**对象发现**"。
    
2. 单击 "**更改范围**"
    
3. 从 "**作用域管理包对象**" 页面中，选择 "**搜索候选**项"。
    
4. 将 "**发现候选**项" 的有效值替换为前面过程中所选择的候选服务器的名称。 
    
若要完成更改，请重新启动 System Center Operations Manager 根管理服务器上的运行状况服务。
  

