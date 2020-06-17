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
localization_priority: Normal
description: 迁移到 Microsoft Skype for Business Server 2019 后，必须完成几个任务以配置 Skype for Business Server 2019，才能与 System Center Operations Manager 配合使用。
ms.openlocfilehash: ef40890cb3ac01d8223c4b9a9cd0c4712e544376
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754042"
---
# <a name="configure-scom-monitoring"></a>配置 SCOM 监控

迁移到 Skype for business Server 2019 后，您必须完成几个任务来配置 Skype for Business Server 2019 以使用 System Center Operations Manager。
  
- 将更新应用到选择的服务器以管理中央发现逻辑。
    
- 更新中央发现候选服务器注册表项。
    
- 将主 System Center Operations Manager 管理服务器配置为覆盖候选中央发现节点。
    
下面提供了有关执行所有这些任务的说明。
  
### <a name="apply-updates-to-a-server-elected-to-manage-the-central-discovery-logic"></a>将更新应用到选择的服务器以管理中央发现逻辑。

1. 选择安装了 System Center Operations Manager 代理文件且配置为候选发现节点的服务器。 
    
2. 将更新应用到此服务器。 请参阅[应用更新](apply-updates.md)中的主题。
    
### <a name="update-the-central-discovery-candidate-server-registry-key"></a>更新中央发现候选服务器注册表项。

1. 在选择了管理中央发现逻辑的服务器上，打开 Windows PowerShell 命令窗口。 
    
2. 在命令行中键入：
    
   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health"
   ```

   ```PowerShell
   New-Item -Path "HKLM:\Software\Microsoft\Real-Time Communications\Health\CentralDiscoveryCandidate"
   ```

    > [!NOTE]
    > Whenever you edit the registry, you may experience an error that the command failed if the registry key already exists. If you experience this, you can safely ignore the error. 
  
### <a name="configure-your-primary-system-center-operations-manager-management-server-to-override-the-candidate-central-discovery-watcher-node"></a>将您的主 System Center Operations Manager 管理服务器配置为覆盖候选中央发现观察程序节点。

1. 在已安装 System Center Operations Manager 控制台的计算机上，展开“管理包对象”****，然后选择“对象发现”****。
    
2. 单击 "**更改范围**"
    
3. 从“范围管理包对象”**** 页中，选择“LS 发现候选”****。
    
4. 将“LS 发现候选有效值”**** 覆盖为在之前的过程中选定的候选服务器的名称。 
    
若要完成所做的更改，请重新启动 System Center Operations Manager 根管理服务器上的运行状况服务。
  

