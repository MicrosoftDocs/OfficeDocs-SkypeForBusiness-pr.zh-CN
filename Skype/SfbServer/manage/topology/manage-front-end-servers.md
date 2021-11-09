---
title: 管理前端服务器Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 摘要：了解如何在服务器中添加、删除、修补或更新Skype for Business Server。
ms.openlocfilehash: daa56be66a09d0969c193021aa3b847fc5972413
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837524"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>管理前端服务器Skype for Business Server
 
本文介绍如何添加或删除前端服务器以及如何将升级或修补程序应用到前端服务器。

  > [!NOTE]
> Skype for Business Server 2019 不支持Enterprise Edition两台前端服务器的前端池，并且不允许在该方案中发布拓扑。

## <a name="add-or-remove-front-end-servers"></a>添加或删除前端服务器
  
将前端服务器添加到池，或者从池中删除前端服务器时，您需要重新启动池。 
  
> [!IMPORTANT]
> 在拓扑中的池中添加或删除服务器，然后发布更新的拓扑时，将导致池中的所有服务器同时重新启动。 当服务器重新启动池时，该池处于脱机状态，这将中断连接到该池的用户的服务。 为了防止给用户服务中断，请计划在非营业时间发布包含池中新服务器的拓扑。 
  
添加或删除前端服务器时，可以使用以下过程。
  
> [!NOTE]
> 如果要向池中添加新服务器，请更新新的池服务器，以与池中的现有服务器处于相同的累积更新级别。 
  
### <a name="to-add-or-remove-front-end-servers"></a>添加或删除前端服务器

1. 如果要删除任何前端服务器，请首先停止与这些服务器的新连接。为此，您可以使用以下 cmdlet：
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. 打开拓扑生成器，然后添加或删除所需的服务器。 
    
3. 发布拓扑。
    
    > [!IMPORTANT]
    > 在拓扑中的池中添加或删除服务器，然后发布更新的拓扑时，将导致池中的所有服务器同时重新启动。 当服务器重新启动池时，该池处于脱机状态，这将中断连接到该池的用户的服务。 为了防止给用户服务中断，请计划在非营业时间发布包含池中新服务器的拓扑。 
  
  > [!NOTE]
> 此外，在池中添加或删除服务器时，必须在添加或删除的每台计算机中运行 Skype for Business Server 部署向导，有关详细信息，请参阅在拓扑中的服务器上安装[Skype for Business Server](../../deploy/install/install-skype-for-business-server.md)
  
4. 如果您通过以下任一方式更改了前端池中的服务器数量，则通过键入以下 cmdlet 重置池：Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - 2 到任意
    
     - 任意到 2
    
     - 3 到任意
    
     - 任意到 3
    
5. 通过键入以下 cmdlet 重新启动池
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a>修补或更新前端服务器

修补前端池中的服务器时，一次修补一台服务器。 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a>对池中的前端服务器应用升级

1. 键入以下 cmdlet：
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     如果此 cmdlet 显示任何丢失的副本，则运行以下 cmdlet 恢复池，然后再应用任何修补程序。
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. 在要修补的第一台服务器上，运行以下 cmdlet：
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    此 cmdlet 会将所有服务移动到池中的其他前端服务器，并使此服务器脱机。
    
3. 将升级或修补程序应用到此服务器。
    
4. 在升级的服务器上，运行以下 cmdlet：
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    服务器将返回到服务。
    
5. 对需要升级的每台服务器重复步骤 2-4。
