---
title: 管理 Skype for Business Server 中的前端服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 摘要：了解如何在 Skype for Business Server 中添加、删除、修补或更新前端服务器。
ms.openlocfilehash: 3d2298711e707ed897b26939fd383dbedcfb3957
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098410"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>管理 Skype for Business Server 中的前端服务器
 
本文介绍如何添加或删除前端服务器，以及如何向前端服务器应用升级或修补程序。

  > [!NOTE]
> Skype for Business Server 2019 不支持使用两台前端服务器的 Enterprise Edition 前端池，并且不允许在该方案中发布拓扑。

## <a name="add-or-remove-front-end-servers"></a>添加或删除前端服务器
  
将前端服务器添加到池，或者从池中删除前端服务器时，您需要重新启动池。 
  
> [!IMPORTANT]
> 将服务器添加或删除到拓扑中的池中并发布更新后的拓扑时，将导致池中的所有服务器同时重新启动。 在服务器重新启动时，池处于脱机状态，这将中断连接到该池的用户的服务。 若要阻止向用户提供任何服务中断，请计划在非工作时间将拓扑发布到池中的新服务器。 
  
在添加或删除前端服务器时，可以使用以下过程。
  
> [!NOTE]
> 如果要将新服务器添加到池，请将新的池服务器更新为与池中现有服务器相同的累积更新级别。 
  
### <a name="to-add-or-remove-front-end-servers"></a>添加或删除前端服务器

1. If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. 打开拓扑生成器，然后添加或删除所需的服务器。 
    
3. 发布拓扑。
    
    > [!IMPORTANT]
    > 将服务器添加或删除到拓扑中的池中并发布更新后的拓扑时，将导致池中的所有服务器同时重新启动。 在服务器重新启动时，池处于脱机状态，这将中断连接到该池的用户的服务。 若要阻止向用户提供任何服务中断，请计划在非工作时间将拓扑发布到池中的新服务器。 
  
  > [!NOTE]
> 此外，在将服务器添加或删除到池时，您必须在添加或删除的每台计算机上运行 Skype for Business Server 部署向导。有关详细信息，请参阅在[拓扑中的服务器上安装 skype For Business server](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)
  
4. 如果您已通过以下任何方式更改了前端池中的服务器数，请通过键入以下 cmdlet 重置池： Reset-CsPoolRegistrarState-ResetType FullReset-PoolFqdn 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2到任何
    
     - 任意到2
    
     - 3到任何
    
     - 任意到3
    
5. 通过键入以下 cmdlet 重新启动池
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>修补或更新前端服务器

当您修补前端池中的服务器时，您一次只能在一台服务器上执行此操作。 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>将升级应用到池中的前端服务器

1. 键入以下 cmdlet：
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     如果此 cmdlet 显示任何丢失的副本，则在应用任何修补程序之前运行以下 cmdlet 来恢复池。
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. 在要修补的第一台服务器上，运行以下 cmdlet：
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    此 cmdlet 将所有服务移动到池中的其他前端服务器，并使此服务器脱机。
    
3. 对此服务器应用升级或修补程序。
    
4. 在升级后的服务器上，运行以下 cmdlet：
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    服务器返回到服务。
    
5. 对需要升级的每台服务器重复步骤2-4。
    
