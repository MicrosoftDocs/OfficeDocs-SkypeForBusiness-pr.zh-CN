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
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="602e9-103">管理 Skype for Business Server 中的前端服务器</span><span class="sxs-lookup"><span data-stu-id="602e9-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="602e9-104">本文介绍如何添加或删除前端服务器，以及如何向前端服务器应用升级或修补程序。</span><span class="sxs-lookup"><span data-stu-id="602e9-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

  > [!NOTE]
> <span data-ttu-id="602e9-105">Skype for Business Server 2019 不支持使用两台前端服务器的 Enterprise Edition 前端池，并且不允许在该方案中发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="602e9-105">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="602e9-106">添加或删除前端服务器</span><span class="sxs-lookup"><span data-stu-id="602e9-106">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="602e9-107">将前端服务器添加到池，或者从池中删除前端服务器时，您需要重新启动池。</span><span class="sxs-lookup"><span data-stu-id="602e9-107">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="602e9-108">将服务器添加或删除到拓扑中的池中并发布更新后的拓扑时，将导致池中的所有服务器同时重新启动。</span><span class="sxs-lookup"><span data-stu-id="602e9-108">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="602e9-109">在服务器重新启动时，池处于脱机状态，这将中断连接到该池的用户的服务。</span><span class="sxs-lookup"><span data-stu-id="602e9-109">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="602e9-110">若要阻止向用户提供任何服务中断，请计划在非工作时间将拓扑发布到池中的新服务器。</span><span class="sxs-lookup"><span data-stu-id="602e9-110">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="602e9-111">在添加或删除前端服务器时，可以使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="602e9-111">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="602e9-112">如果要将新服务器添加到池，请将新的池服务器更新为与池中现有服务器相同的累积更新级别。</span><span class="sxs-lookup"><span data-stu-id="602e9-112">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="602e9-113">添加或删除前端服务器</span><span class="sxs-lookup"><span data-stu-id="602e9-113">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="602e9-p102">如果要删除任何前端服务器，请首先停止与这些服务器的新连接。为此，您可以使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="602e9-p102">If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:</span></span>
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="602e9-116">打开拓扑生成器，然后添加或删除所需的服务器。</span><span class="sxs-lookup"><span data-stu-id="602e9-116">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="602e9-117">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="602e9-117">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="602e9-118">将服务器添加或删除到拓扑中的池中并发布更新后的拓扑时，将导致池中的所有服务器同时重新启动。</span><span class="sxs-lookup"><span data-stu-id="602e9-118">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="602e9-119">在服务器重新启动时，池处于脱机状态，这将中断连接到该池的用户的服务。</span><span class="sxs-lookup"><span data-stu-id="602e9-119">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="602e9-120">若要阻止向用户提供任何服务中断，请计划在非工作时间将拓扑发布到池中的新服务器。</span><span class="sxs-lookup"><span data-stu-id="602e9-120">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="602e9-121">此外，在将服务器添加或删除到池时，您必须在添加或删除的每台计算机上运行 Skype for Business Server 部署向导。有关详细信息，请参阅在[拓扑中的服务器上安装 skype For Business server](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="602e9-121">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="602e9-122">如果您已通过以下任何方式更改了前端池中的服务器数，请通过键入以下 cmdlet 重置池： Reset-CsPoolRegistrarState-ResetType FullReset-PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="602e9-122">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="602e9-123">2到任何</span><span class="sxs-lookup"><span data-stu-id="602e9-123">2 to any</span></span>
    
     - <span data-ttu-id="602e9-124">任意到2</span><span class="sxs-lookup"><span data-stu-id="602e9-124">Any to 2</span></span>
    
     - <span data-ttu-id="602e9-125">3到任何</span><span class="sxs-lookup"><span data-stu-id="602e9-125">3 to any</span></span>
    
     - <span data-ttu-id="602e9-126">任意到3</span><span class="sxs-lookup"><span data-stu-id="602e9-126">Any to 3</span></span>
    
5. <span data-ttu-id="602e9-127">通过键入以下 cmdlet 重新启动池</span><span class="sxs-lookup"><span data-stu-id="602e9-127">Restart the pool by typing the following cmdlet</span></span>
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="602e9-128">修补或更新前端服务器</span><span class="sxs-lookup"><span data-stu-id="602e9-128">Patch or update Front End Servers</span></span>

<span data-ttu-id="602e9-129">当您修补前端池中的服务器时，您一次只能在一台服务器上执行此操作。</span><span class="sxs-lookup"><span data-stu-id="602e9-129">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="602e9-130">将升级应用到池中的前端服务器</span><span class="sxs-lookup"><span data-stu-id="602e9-130">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="602e9-131">键入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="602e9-131">Type the following cmdlet:</span></span>
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="602e9-132">如果此 cmdlet 显示任何丢失的副本，则在应用任何修补程序之前运行以下 cmdlet 来恢复池。</span><span class="sxs-lookup"><span data-stu-id="602e9-132">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="602e9-133">在要修补的第一台服务器上，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="602e9-133">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="602e9-134">此 cmdlet 将所有服务移动到池中的其他前端服务器，并使此服务器脱机。</span><span class="sxs-lookup"><span data-stu-id="602e9-134">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="602e9-135">对此服务器应用升级或修补程序。</span><span class="sxs-lookup"><span data-stu-id="602e9-135">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="602e9-136">在升级后的服务器上，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="602e9-136">On the upgraded server, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="602e9-137">服务器返回到服务。</span><span class="sxs-lookup"><span data-stu-id="602e9-137">The server is returned to service.</span></span>
    
5. <span data-ttu-id="602e9-138">对需要升级的每台服务器重复步骤2-4。</span><span class="sxs-lookup"><span data-stu-id="602e9-138">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
