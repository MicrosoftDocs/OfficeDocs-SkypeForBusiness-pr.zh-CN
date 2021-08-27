---
title: 配置 SCOM 监控
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: 迁移到 Microsoft Skype for Business Server 2019 后，必须完成一些任务，将 Skype for Business Server 2019 配置为使用 System Center Operations Manager。
ms.openlocfilehash: 756e83ad0a8c964954f43518dc8603802d45c40d
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58590656"
---
# <a name="configure-scom-monitoring"></a>配置 SCOM 监控

迁移到 2019 Skype for Business Server 2019 后，必须完成一些任务，将 Skype for Business Server 2019 配置为使用 System Center Operations Manager。
  
- 对选择用于管理中央发现逻辑的服务器应用更新。
    
- 更新中央发现候选服务器注册表项。
    
- 配置主System Center Operations Manager 管理服务器以覆盖候选中央发现节点。
    
下面提供了有关执行所有这些任务的说明。
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>对选择用于管理中央发现逻辑的服务器应用更新。

1. 选择安装了 System Center Operations Manager 代理文件且配置为候选发现节点的服务器。 
    
2. 对此服务器应用更新。 请参阅主题应用 [更新](apply-updates.md)。
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>更新中央发现候选服务器注册表项。

1. 在选择管理中央发现逻辑的服务器上，打开Windows PowerShell命令窗口。 
    
2. 在命令行中键入：
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > 在您编辑注册表时，如果已存在注册表项，则您可能会遇到一个指示命令失败的错误。如果遇到此错误，可以安全地将其忽略。 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>配置主System Center Operations Manager 管理服务器以覆盖候选中心发现观察程序节点。

1. 在已安装 System Center Operations Manager 控制台的计算机上，展开“管理包对象”，然后选择“对象发现”。
    
2. 单击" **更改范围"**
    
3. 从“范围管理包对象”页中，选择“LS 发现候选”。
    
4. 将“LS 发现候选有效值”覆盖为在之前的过程中选定的候选服务器的名称。 
    
若要完成更改，请重新启动 System Center Operations Manager 根管理服务器上运行状况服务。
  

