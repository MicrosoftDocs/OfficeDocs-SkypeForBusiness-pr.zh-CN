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
description: 摘要：了解如何在 Skype for Business 服务器中添加、删除、修补或更新前端服务器。
ms.openlocfilehash: 3689b869ba715f431ebcf0b537b4106a66177c62
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991527"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="49046-103">在 Skype for Business 服务器中管理前端服务器</span><span class="sxs-lookup"><span data-stu-id="49046-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="49046-104">本文介绍如何添加或删除前端服务器以及如何将升级或修补程序应用于前端服务器。</span><span class="sxs-lookup"><span data-stu-id="49046-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="49046-105">添加或删除前端服务器</span><span class="sxs-lookup"><span data-stu-id="49046-105">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="49046-106">将前端服务器添加到池中或从池中删除前端服务器时，您需要重新启动池。</span><span class="sxs-lookup"><span data-stu-id="49046-106">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="49046-p101">当你向拓扑中的池添加服务器或从中删除服务器时，会导致池中的所有服务器同时重新启动。当服务器重新启动时，池处于脱机状态，这样会为连接到该池的用户中断服务。为防止用户服务中断，请计划于非工作时间在池中发布采用新服务器的拓扑。</span><span class="sxs-lookup"><span data-stu-id="49046-p101">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="49046-110">添加或删除前端服务器时，可以使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="49046-110">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="49046-111">如果将新服务器添加到池，请将您的新池服务器更新为与池中的现有服务器相同的累积更新级别。</span><span class="sxs-lookup"><span data-stu-id="49046-111">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="49046-112">添加或删除前端服务器</span><span class="sxs-lookup"><span data-stu-id="49046-112">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="49046-113">如果您要删除任何前端服务器，请首先停止与这些服务器的新连接。</span><span class="sxs-lookup"><span data-stu-id="49046-113">If you are removing any Front End Servers, first stop new connections to those servers.</span></span> <span data-ttu-id="49046-114">为此，您可以使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="49046-114">To do so, you can use the following cmdlet:</span></span>
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="49046-115">打开拓扑生成器，然后添加或删除必要的服务器。</span><span class="sxs-lookup"><span data-stu-id="49046-115">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="49046-116">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="49046-116">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="49046-p103">当你向拓扑中的池添加服务器或从中删除服务器时，会导致池中的所有服务器同时重新启动。当服务器重新启动时，池处于脱机状态，这样会为连接到该池的用户中断服务。为防止用户服务中断，请计划于非工作时间在池中发布采用新服务器的拓扑。</span><span class="sxs-lookup"><span data-stu-id="49046-p103">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time. While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool. To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="49046-120">此外，当你在池中添加或删除服务器时，必须在添加或删除的每台计算机上运行 Skype for Business Server 部署向导，有关详细信息，请参阅在[拓扑中的服务器上安装 skype For Business 服务器](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span><span class="sxs-lookup"><span data-stu-id="49046-120">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](https://docs.microsoft.com/skypeforbusiness/deploy/install/install-skype-for-business-server)</span></span>
  
4. <span data-ttu-id="49046-121">如果你已使用以下任何方式更改了你的前端池中的服务器数，则通过键入以下 cmdlet 重置池： Reset-CsPoolRegistrarState-ResetType FullReset-PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="49046-121">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="49046-122">2 到任意</span><span class="sxs-lookup"><span data-stu-id="49046-122">2 to any</span></span>
    
     - <span data-ttu-id="49046-123">任意到 2</span><span class="sxs-lookup"><span data-stu-id="49046-123">Any to 2</span></span>
    
     - <span data-ttu-id="49046-124">3 到任意</span><span class="sxs-lookup"><span data-stu-id="49046-124">3 to any</span></span>
    
     - <span data-ttu-id="49046-125">任意到 3</span><span class="sxs-lookup"><span data-stu-id="49046-125">Any to 3</span></span>
    
5. <span data-ttu-id="49046-126">键入以下 cmdlet 以重新启动该池</span><span class="sxs-lookup"><span data-stu-id="49046-126">Restart the pool by typing the following cmdlet</span></span>
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="49046-127">修补或更新前端服务器</span><span class="sxs-lookup"><span data-stu-id="49046-127">Patch or update Front End Servers</span></span>

<span data-ttu-id="49046-128">当您修补前端池中的服务器时，您一次可以执行一次服务器。</span><span class="sxs-lookup"><span data-stu-id="49046-128">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="49046-129">对池中的前端服务器应用升级</span><span class="sxs-lookup"><span data-stu-id="49046-129">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="49046-130">键入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="49046-130">Type the following cmdlet:</span></span>
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="49046-131">如果此 cmdlet 显示存在任何丢失副本，请运行以下 cmdlet 以恢复池，然后才能应用修补程序。</span><span class="sxs-lookup"><span data-stu-id="49046-131">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="49046-132">在要修补的第一台服务器上，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="49046-132">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="49046-133">此 cmdlet 将所有服务移动到池中的其他前端服务器，并使此服务器脱机。</span><span class="sxs-lookup"><span data-stu-id="49046-133">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="49046-134">为此服务器应用升级或修补。</span><span class="sxs-lookup"><span data-stu-id="49046-134">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="49046-135">在升级后的服务器上，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="49046-135">On the upgraded server, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="49046-136">服务器重新返回服务。</span><span class="sxs-lookup"><span data-stu-id="49046-136">The server is returned to service.</span></span>
    
5. <span data-ttu-id="49046-137">对需要升级的每台服务器执行步骤 2-4。</span><span class="sxs-lookup"><span data-stu-id="49046-137">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
    
