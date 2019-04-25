---
title: 为业务服务器部署已配对的前端池 Skype 中的灾难恢复
ms.reviewer: ''
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2f12467c-8b90-43e6-831b-a0b096427f17
description: 你可以决定使用配对的前端池来提供灾难恢复保护，但这并不是必需满足的要求。
ms.openlocfilehash: 028e0b4966a15b81b3e6e5627e63261207835f1f
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225537"
---
# <a name="deploy-paired-front-end-pools-for-disaster-recovery-in-skype-for-business-server"></a>为业务服务器部署已配对的前端池 Skype 中的灾难恢复
 
你可以决定使用配对的前端池来提供灾难恢复保护，但这并不是必需满足的要求。
  
您可以轻松部署已配对前端池使用拓扑生成器的灾难恢复拓扑。 
  
## <a name="to-deploy-a-pair-of-front-end-pools"></a>部署配对前端池

1. 如果是新池并且尚未定义，请使用拓扑生成器创建这些池。
    
2. 在拓扑生成器中，右键单击两个池之一，然后单击**编辑属性**。
    
3. 在左侧窗格中单击“**复原**”，然后在右侧窗格中选择“**关联的备份池**”。
    
4. 在“**关联的备份池**”下方的框中，选择要与该池配对的池。仅可以选择尚未与其他池配对的现有池。
    
5. 选择“**语音的自动故障转移和故障回复**”，然后单击“**确定**”。
    
    当你查看该池的详细信息时，此时关联的池显示在“**复原**”下的右窗格中。 
    
6. 使用拓扑生成器发布拓扑。
    
7. 如果尚未部署两个池，请立即部署它们，配置随即完成。你可以跳过此过程的最后两步。
    
    但是，如果在定义配对关系之前已部署池，那么必须完成以下两个最终步骤。
    
8. 在两个池的每个前端服务器上，运行以下命令：
    
   ```
   <system drive>\Program Files\Skype for Business Server 2015\Deployment\Bootstrapper.exe 
   ```

    这将配置确保备份配对正常运行所需的其他服务。
    
9. 从 Skype 的业务 Server 命令行管理程序命令提示符处，运行以下命令： 
    
   ```
   Start-CsWindowsService -Name LYNCBACKUP
   ```

10. 使用以下 cmdlet 强制两个池的用户和会议数据相互同步：
    
    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN>
    ```

    同步数据可能需要一些时间。你可以使用以下 cmdlet 检查同步状态。确保两个方向的状态均保持稳定。
    
    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool1 FQDN>
    ```

    ```
    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN>
    ```

> [!NOTE]
> **自动故障转移和故障回复语音**选项和拓扑生成器中的关联的时间间隔仅适用于 Lync Server 中引入的语音恢复能力功能。 选择此选项并不意味着会自动执行本文档中讨论的池故障转移。 池故障转移和故障回复始终需要管理员手动且分别调用故障转移和故障回复 cmdlet。
  
## <a name="see-also"></a>另请参阅

[为业务 Server 前端中 Skype 的最终池灾难恢复](../../plan-your-deployment/high-availability-and-disaster-recovery/disaster-recovery.md)
