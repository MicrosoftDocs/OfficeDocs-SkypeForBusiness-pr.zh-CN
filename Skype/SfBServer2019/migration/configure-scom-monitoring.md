---
title: 配置 SCOM 监控
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 迁移到 Microsoft Skype for Business Server 2019 之后，您必须完成几项任务才能配置的业务服务器 2019 以使用 System Center Operations Manager 的 Skype。
ms.openlocfilehash: 80ef737c57006550111331db7f46fd607f7cf1ed
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32238721"
---
# <a name="configure-scom-monitoring"></a>配置 SCOM 监控

迁移到 Skype for Business Server 2019 之后，您必须完成几项任务才能配置的业务服务器 2019 以使用 System Center Operations Manager 的 Skype。
  
- 更新应用于选择用来管理中央发现逻辑的服务器。
    
- 更新中央发现候选服务器注册表项。
    
- 主 System Center Operations Manager 管理服务器配置为覆盖候选中央发现节点。
    
下面提供了有关执行上述各项任务的说明。
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>更新应用于选择用来管理中央发现逻辑的服务器。

1. 选择具有 System Center Operations Manager 代理文件安装并配置为候选发现节点的服务器。 
    
2. 更新应用于该服务器。 请参阅主题[应用更新](apply-updates.md)。
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>更新中央发现候选服务器注册表项。

1. 在选择用来管理中央发现逻辑服务器上，打开 Windows PowerShell 命令窗口。 
    
2. 在命令行中键入：
    
   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > 只要编辑注册表，可能会遇到错误的命令失败如果注册表项已存在。 如果您遇到此，您可以放心地忽略错误。 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>主 System Center Operations Manager 管理服务器配置为覆盖候选中央发现观察程序节点。

1. 在计算机上已安装 System Center Operations Manager 控制台，展开**管理包对象**，然后选择**对象发现**。
    
2. 单击**更改范围**
    
3. 从**范围管理包对象**页上，选择**LS 发现候选**。
    
4. 重写**LS 发现候选有效值**为与前一过程中选定的候选服务器的名称。 
    
要完成所做的更改，重新启动 System Center Operations Manager 根管理服务器上的运行状况服务。
  

