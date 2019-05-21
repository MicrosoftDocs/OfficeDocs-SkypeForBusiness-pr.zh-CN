---
title: 在 Skype for Business 服务器中管理前端服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: '摘要: 了解如何在 Skype for Business 服务器中添加、删除、修补或更新前端服务器。'
ms.openlocfilehash: 13af9198dfb83d14ad1d86885419fc9add29e07d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34275155"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a>在 Skype for Business 服务器中管理前端服务器
 
本文介绍如何添加或删除前端服务器以及如何将升级或修补程序应用于前端服务器。

## <a name="add-or-remove-front-end-servers"></a>添加或删除前端服务器
  
将前端服务器添加到池中或从池中删除前端服务器时, 您需要重新启动池。 
  
> [!IMPORTANT]
> 当你向拓扑中的池添加服务器或从中删除服务器时，会导致池中的所有服务器同时重新启动。当服务器重新启动时，池处于脱机状态，这样会为连接到该池的用户中断服务。为防止用户服务中断，请计划于非工作时间在池中发布采用新服务器的拓扑。 
  
添加或删除前端服务器时, 可以使用以下过程。
  
> [!NOTE]
> 如果将新服务器添加到池，请将您的新池服务器更新为与池中的现有服务器相同的累积更新级别。 
  
### <a name="to-add-or-remove-front-end-servers"></a>添加或删除前端服务器

1. 如果您要删除任何前端服务器, 请首先停止与这些服务器的新连接。 为此，您可以使用以下 cmdlet：
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. 打开拓扑生成器, 然后添加或删除必要的服务器。 
    
3. 发布拓扑。
    
    > [!IMPORTANT]
    > 当你向拓扑中的池添加服务器或从中删除服务器时，会导致池中的所有服务器同时重新启动。当服务器重新启动时，池处于脱机状态，这样会为连接到该池的用户中断服务。为防止用户服务中断，请计划于非工作时间在池中发布采用新服务器的拓扑。 
  
  > [!NOTE]
> 此外, 当你在池中添加或删除服务器时, 必须在添加或删除的每台计算机上运行 Skype for Business Server 部署向导, 有关详细信息, 请参阅在[拓扑中的服务器上安装 skype For Business 服务器](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)
  
4. 如果你已使用以下任何方式更改了你的前端池中的服务器数, 则通过键入以下 cmdlet 重置池: Reset-CsPoolRegistrarState-ResetType FullReset-PoolFqdn 
    
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

当您修补前端池中的服务器时, 您一次可以执行一次服务器。 
  
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

    此 cmdlet 将所有服务移动到池中的其他前端服务器, 并使此服务器脱机。
    
3. 为此服务器应用升级或修补。
    
4. 在升级后的服务器上，运行以下 cmdlet：
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    服务器重新返回服务。
    
5. 对需要升级的每台服务器执行步骤 2-4。
    
