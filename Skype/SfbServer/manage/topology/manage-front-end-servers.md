---
title: 管理业务服务器中 Skype 的前端服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 摘要： 了解如何添加、 删除修补程序，或更新业务服务器 Skype 在前端服务器。
ms.openlocfilehash: c7ccaee0ee70c10b855053fb63c39cfead148f4e
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30875220"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>管理业务服务器中 Skype 的前端服务器
 
本文说明如何添加或删除前端服务器和如何应用升级或修补程序到前端服务器。

## <a name="add-or-remove-front-end-servers"></a>添加或删除前端服务器
  
当您向池中添加前端服务器，或从池中删除前端服务器时，然后需要重新启动池。 
  
> [!IMPORTANT]
> 当你向拓扑中的池添加服务器或从中删除服务器时，会导致池中的所有服务器同时重新启动。当服务器重新启动时，池处于脱机状态，这样会为连接到该池的用户中断服务。为防止用户服务中断，请计划于非工作时间在池中发布采用新服务器的拓扑。 
  
您可以使用以下过程时添加或删除前端服务器。
  
> [!NOTE]
> 如果将新服务器添加到池，请将您的新池服务器更新为与池中的现有服务器相同的累积更新级别。 
  
### <a name="to-add-or-remove-front-end-servers"></a>添加或删除前端服务器

1. 如果要移除任何前端服务器，首先停止这些服务器的新连接。 为此，您可以使用以下 cmdlet：
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. 打开拓扑生成器，以及添加或删除所需的服务器。 
    
3. 发布拓扑。
    
    > [!IMPORTANT]
    > 当你向拓扑中的池添加服务器或从中删除服务器时，会导致池中的所有服务器同时重新启动。当服务器重新启动时，池处于脱机状态，这样会为连接到该池的用户中断服务。为防止用户服务中断，请计划于非工作时间在池中发布采用新服务器的拓扑。 
  
4. 如果您更改了服务器数量的在前端池中任意通过以下方式中，然后通过重置池与键入以下 cmdlet: Reset-cspoolregistrarstate ResetType FullReset-PoolFqdn 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 到任意
    
     - 任意到 2
    
     - 3 到任意
    
     - 任意到 3
    
5. 键入以下 cmdlet 以重新启动该池
    
   ```
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>修补或更新前端服务器

修补程序在前端池中的服务器时，您一次执行因此一台服务器。 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>对池中的前端服务器应用升级

1. 键入以下 cmdlet：
    
   ```
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     如果此 cmdlet 显示存在任何丢失副本，请运行以下 cmdlet 以恢复池，然后才能应用修补程序。
    
   ```
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. 在要修补的第一台服务器上，运行以下 cmdlet：
    
   ```
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    此 cmdlet 将所有服务都移动到其他前端服务器池中，并使此服务器脱机。
    
3. 为此服务器应用升级或修补。
    
4. 在升级后的服务器上，运行以下 cmdlet：
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    服务器重新返回服务。
    
5. 对需要升级的每台服务器执行步骤 2-4。
    
