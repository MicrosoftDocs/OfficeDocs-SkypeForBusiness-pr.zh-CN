---
title: 管理业务服务器中 Skype 的前端服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 摘要： 了解如何添加、 删除修补程序，或更新业务服务器 Skype 在前端服务器。
ms.openlocfilehash: cac824de5747291a735ce36d624dad66fb32e10e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33911796"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="86a7b-103">管理业务服务器中 Skype 的前端服务器</span><span class="sxs-lookup"><span data-stu-id="86a7b-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="86a7b-104">本文说明如何添加或删除前端服务器和如何应用升级或修补程序到前端服务器。</span><span class="sxs-lookup"><span data-stu-id="86a7b-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="86a7b-105">添加或删除前端服务器</span><span class="sxs-lookup"><span data-stu-id="86a7b-105">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="86a7b-106">当您向池中添加前端服务器，或从池中删除前端服务器时，然后需要重新启动池。</span><span class="sxs-lookup"><span data-stu-id="86a7b-106">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="86a7b-p101">当你向拓扑中的池添加服务器或从中删除服务器时，会导致池中的所有服务器同时重新启动。当服务器重新启动时，池处于脱机状态，这样会为连接到该池的用户中断服务。为防止用户服务中断，请计划于非工作时间在池中发布采用新服务器的拓扑。</span><span class="sxs-lookup"><span data-stu-id="86a7b-p101">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="86a7b-110">您可以使用以下过程时添加或删除前端服务器。</span><span class="sxs-lookup"><span data-stu-id="86a7b-110">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="86a7b-111">如果将新服务器添加到池，请将您的新池服务器更新为与池中的现有服务器相同的累积更新级别。</span><span class="sxs-lookup"><span data-stu-id="86a7b-111">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="86a7b-112">添加或删除前端服务器</span><span class="sxs-lookup"><span data-stu-id="86a7b-112">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="86a7b-113">如果要移除任何前端服务器，首先停止这些服务器的新连接。</span><span class="sxs-lookup"><span data-stu-id="86a7b-113">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="86a7b-114">为此，您可以使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="86a7b-114">To do so, you can use the following cmdlet:</span></span>
    
   ```
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="86a7b-115">打开拓扑生成器，以及添加或删除所需的服务器。</span><span class="sxs-lookup"><span data-stu-id="86a7b-115">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="86a7b-116">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="86a7b-116">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="86a7b-p103">当你向拓扑中的池添加服务器或从中删除服务器时，会导致池中的所有服务器同时重新启动。当服务器重新启动时，池处于脱机状态，这样会为连接到该池的用户中断服务。为防止用户服务中断，请计划于非工作时间在池中发布采用新服务器的拓扑。</span><span class="sxs-lookup"><span data-stu-id="86a7b-p103">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="86a7b-120">此外，当您添加或删除服务器添加到池，您必须业务 Server 部署向导添加的每台计算机上运行 Skype 或删除，有关详细信息，请参阅[安装的企业服务器拓扑中的服务器上的 Skype](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="86a7b-120">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="86a7b-121">如果您更改了服务器数量的在前端池中任意通过以下方式中，然后通过重置池与键入以下 cmdlet: Reset-cspoolregistrarstate ResetType FullReset-PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="86a7b-121">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="86a7b-122">2 到任意</span><span class="sxs-lookup"><span data-stu-id="86a7b-122">2 to any</span></span>
    
     - <span data-ttu-id="86a7b-123">任意到 2</span><span class="sxs-lookup"><span data-stu-id="86a7b-123">Any to 2</span></span>
    
     - <span data-ttu-id="86a7b-124">3 到任意</span><span class="sxs-lookup"><span data-stu-id="86a7b-124">3 to any</span></span>
    
     - <span data-ttu-id="86a7b-125">任意到 3</span><span class="sxs-lookup"><span data-stu-id="86a7b-125">Any to 3</span></span>
    
5. <span data-ttu-id="86a7b-126">键入以下 cmdlet 以重新启动该池</span><span class="sxs-lookup"><span data-stu-id="86a7b-126">Restart the pool by typing the following cmdlet</span></span>
    
   ```
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="86a7b-127">修补或更新前端服务器</span><span class="sxs-lookup"><span data-stu-id="86a7b-127">Patch or update Front End Servers</span></span>

<span data-ttu-id="86a7b-128">修补程序在前端池中的服务器时，您一次执行因此一台服务器。</span><span class="sxs-lookup"><span data-stu-id="86a7b-128">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="86a7b-129">对池中的前端服务器应用升级</span><span class="sxs-lookup"><span data-stu-id="86a7b-129">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="86a7b-130">键入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="86a7b-130">Type the following cmdlet:</span></span>
    
   ```
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="86a7b-131">如果此 cmdlet 显示存在任何丢失副本，请运行以下 cmdlet 以恢复池，然后才能应用修补程序。</span><span class="sxs-lookup"><span data-stu-id="86a7b-131">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="86a7b-132">在要修补的第一台服务器上，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="86a7b-132">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="86a7b-133">此 cmdlet 将所有服务都移动到其他前端服务器池中，并使此服务器脱机。</span><span class="sxs-lookup"><span data-stu-id="86a7b-133">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="86a7b-134">为此服务器应用升级或修补。</span><span class="sxs-lookup"><span data-stu-id="86a7b-134">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="86a7b-135">在升级后的服务器上，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="86a7b-135">On the upgraded server, run the following cmdlet:</span></span>
    
   ```
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="86a7b-136">服务器重新返回服务。</span><span class="sxs-lookup"><span data-stu-id="86a7b-136">The server is returned to service.</span></span>
    
5. <span data-ttu-id="86a7b-137">对需要升级的每台服务器执行步骤 2-4。</span><span class="sxs-lookup"><span data-stu-id="86a7b-137">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
