---
title: 部署配对的前端池，以在 Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: 您可以决定使用配对的前端池来提供灾难恢复保护，但这不是一项要求。
ms.openlocfilehash: 27909f44f0d86cac3100437f7df094b5f72ba1be
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60855096"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a>部署配对的前端池，以在 Skype for Business Server
 
您可以决定使用配对的前端池来提供灾难恢复保护，但这不是一项要求。
  
您可以使用拓扑生成器轻松部署配对前端池的灾难恢复拓扑。 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a>部署配对前端池

1. 如果池是新的且尚未定义，请使用拓扑生成器创建池。
    
2. 在拓扑生成器中，右键单击两个池之一，然后单击"编辑 **属性"。**
    
3. 在左侧窗格中单击“复原”，然后在右侧窗格中选择“关联的备份池”。
    
4. 在“关联的备份池”下方的框中，选择要与该池配对的池。仅可以选择尚未与其他池配对的现有池。
    
5. 选择“语音的自动故障转移和故障回复”，然后单击“确定”。
    
    当您查看该池的详细信息时，关联的池现在显示在“复原”下的右窗格中。 
    
6. 使用拓扑生成器发布拓扑。
    
7. 如果尚未部署两个池，请立即部署它们，配置随即完成。 可以跳过此过程的最后步骤。
    
    但是，如果在定义配对关系之前已部署池，则必须完成以下最终步骤。
    
8. 在两个池的每个前端服务器上，运行以下命令：
    
   ```powershell
   <system drive>\Program Files\Skype for Business Server 2019\Deployment\Bootstrapper.exe 
   ```

    这将配置确保备份配对正常运行所需的其他服务。
    
9. 一旦引导程序在两个池中的前端服务器上完成安装备份配对所需的组件后，请确保重新应用之前在两个池中的这些前端服务器上应用的任何现有累积更新，然后继续执行下一步。

10. 从命令行Skype for Business Server命令行管理程序命令提示符中，运行以下命令： 
    
   ```powershell
   Start-CsWindowsService -Name LYNCBACKUP
   ```

11. 通过以下 cmdlet 强制两个池的用户和会议数据相互同步：
    
    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    同步数据可能需要一些时间。 您可以使用以下 cmdlet 检查同步状态。 确保两个方向的状态均稳定。
    
    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```powershell
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> " **语音的** 自动故障转移和故障回复"选项以及拓扑生成器中的关联时间间隔仅适用于 Lync Server 中引入的语音恢复能力功能。 选择此选项并不意味着本文档中讨论的池故障转移将自动执行。 池故障转移和故障回复始终需要管理员手动且分别调用故障转移和故障回复 cmdlet。
  
## <a name="see-also"></a>另请参阅

[前端池中的Skype for Business Server](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
