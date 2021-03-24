---
title: 在 Skype for Business Server 中管理前端服务器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ab748733-6bad-4c93-8dda-db8d5271653d
description: 摘要：了解如何在 Skype for Business Server 中添加、删除、修补或更新前端服务器。
ms.openlocfilehash: 24527a5f973b21c35e386f0565ac6deb69e15070
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103188"
---
# <a name="manage-front-end-servers-in-skype-for-business-server"></a><span data-ttu-id="017e6-103">在 Skype for Business Server 中管理前端服务器</span><span class="sxs-lookup"><span data-stu-id="017e6-103">Manage Front End Servers in Skype for Business Server</span></span>
 
<span data-ttu-id="017e6-104">本文介绍如何添加或删除前端服务器以及如何将升级或修补程序应用到前端服务器。</span><span class="sxs-lookup"><span data-stu-id="017e6-104">This article explains how to add or remove Front End Servers and how to apply upgrades or patches to Front End Servers.</span></span>

  > [!NOTE]
> <span data-ttu-id="017e6-105">Skype for Business Server 2019 不支持具有两台前端服务器的 Enterprise Edition 前端池，并且不允许在该方案中发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="017e6-105">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>

## <a name="add-or-remove-front-end-servers"></a><span data-ttu-id="017e6-106">添加或删除前端服务器</span><span class="sxs-lookup"><span data-stu-id="017e6-106">Add or remove Front End Servers</span></span>
  
<span data-ttu-id="017e6-107">将前端服务器添加到池，或者从池中删除前端服务器时，您需要重新启动池。</span><span class="sxs-lookup"><span data-stu-id="017e6-107">When you add a Front End Server to a pool, or remove a Front End Server from a pool, you then need to restart the pool.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="017e6-108">当您向拓扑中的池添加或删除服务器，然后发布更新的拓扑时，将导致池中的所有服务器同时重新启动。</span><span class="sxs-lookup"><span data-stu-id="017e6-108">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="017e6-109">当服务器重新启动池时，该池处于脱机状态，这将中断连接到该池的用户的服务。</span><span class="sxs-lookup"><span data-stu-id="017e6-109">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="017e6-110">为了防止给用户服务中断，请计划在非营业时间发布包含池中新服务器的拓扑。</span><span class="sxs-lookup"><span data-stu-id="017e6-110">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
<span data-ttu-id="017e6-111">添加或删除前端服务器时，可以使用以下过程。</span><span class="sxs-lookup"><span data-stu-id="017e6-111">You can use the following procedure when adding or removing a Front End Server.</span></span>
  
> [!NOTE]
> <span data-ttu-id="017e6-112">如果要向池中添加新服务器，请更新新池服务器，以与池中的现有服务器处于相同的累积更新级别。</span><span class="sxs-lookup"><span data-stu-id="017e6-112">If you're adding new servers to the pool, update your new pool servers to be at the same Cumulative Update level as the existing servers in the Pool.</span></span> 
  
### <a name="to-add-or-remove-front-end-servers"></a><span data-ttu-id="017e6-113">添加或删除前端服务器</span><span class="sxs-lookup"><span data-stu-id="017e6-113">To add or remove Front End Servers</span></span>

1. <span data-ttu-id="017e6-p102">如果要删除任何前端服务器，请首先停止与这些服务器的新连接。为此，您可以使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="017e6-p102">If you are removing any Front End Servers, first stop new connections to those servers. To do so, you can use the following cmdlet:</span></span>
    
   ```PowerShell
   Stop-CsWindowsService -Graceful
   ```

2. <span data-ttu-id="017e6-116">打开拓扑生成器，然后添加或删除所需的服务器。</span><span class="sxs-lookup"><span data-stu-id="017e6-116">Open Topology Builder, and add or remove the necessary servers.</span></span> 
    
3. <span data-ttu-id="017e6-117">发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="017e6-117">Publish the topology.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="017e6-118">当您向拓扑中的池添加或删除服务器，然后发布更新的拓扑时，将导致池中的所有服务器同时重新启动。</span><span class="sxs-lookup"><span data-stu-id="017e6-118">When you add or remove a server to the pool in your topology and then publish the updated topology, it will cause all of the servers in the pool to restart at the same time.</span></span> <span data-ttu-id="017e6-119">当服务器重新启动池时，该池处于脱机状态，这将中断连接到该池的用户的服务。</span><span class="sxs-lookup"><span data-stu-id="017e6-119">While the servers are restarting the pool is offline, which will interrupt service for your users connected to that pool.</span></span> <span data-ttu-id="017e6-120">为了防止给用户服务中断，请计划在非营业时间发布包含池中新服务器的拓扑。</span><span class="sxs-lookup"><span data-stu-id="017e6-120">To prevent any interruption of service to users, plan to publish the topology with the new server in the pool during non-business hours.</span></span> 
  
  > [!NOTE]
> <span data-ttu-id="017e6-121">此外，在池中添加或删除服务器时，必须在添加或删除的每台计算机中运行 Skype for Business Server 部署向导，有关详细信息，请参阅在拓扑中的服务器上安装 [Skype for Business Server](../../deploy/install/install-skype-for-business-server.md)</span><span class="sxs-lookup"><span data-stu-id="017e6-121">Also, when you add or remove a server to the pool, you must run the Skype for Business Server Deployment Wizard on each computer added or removed, for more information, see [Install Skype for Business Server on servers in the topology](../../deploy/install/install-skype-for-business-server.md)</span></span>
  
4. <span data-ttu-id="017e6-122">如果通过以下任一方式更改了前端池中的服务器数量，请通过键入以下 cmdlet 重置池：Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span><span class="sxs-lookup"><span data-stu-id="017e6-122">If you have changed the number of servers in your Front End pool in any of the following ways, then reset the pool with by typing the following cmdlet: Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn</span></span> 
    
   ```PowerShell
    Reset-CsPoolRegistrarState -ResetType FullReset -PoolFqdn  <PoolFQDN>
   ```

     - <span data-ttu-id="017e6-123">2 到任意</span><span class="sxs-lookup"><span data-stu-id="017e6-123">2 to any</span></span>
    
     - <span data-ttu-id="017e6-124">任意到 2</span><span class="sxs-lookup"><span data-stu-id="017e6-124">Any to 2</span></span>
    
     - <span data-ttu-id="017e6-125">3 到任意</span><span class="sxs-lookup"><span data-stu-id="017e6-125">3 to any</span></span>
    
     - <span data-ttu-id="017e6-126">任意到 3</span><span class="sxs-lookup"><span data-stu-id="017e6-126">Any to 3</span></span>
    
5. <span data-ttu-id="017e6-127">通过键入以下 cmdlet 重新启动池</span><span class="sxs-lookup"><span data-stu-id="017e6-127">Restart the pool by typing the following cmdlet</span></span>
    
   ```PowerShell
   Start-CsPool
   ```

## <a name="patch-or-update-front-end-servers"></a><span data-ttu-id="017e6-128">修补或更新前端服务器</span><span class="sxs-lookup"><span data-stu-id="017e6-128">Patch or update Front End Servers</span></span>

<span data-ttu-id="017e6-129">修补前端池中的服务器时，一次修补一台服务器。</span><span class="sxs-lookup"><span data-stu-id="017e6-129">When you patch the servers in a Front End pool, you do so one server at a time.</span></span> 
  
### <a name="to-apply-an-upgrade-to-the-front-end-servers-in-a-pool"></a><span data-ttu-id="017e6-130">对池中的前端服务器应用升级</span><span class="sxs-lookup"><span data-stu-id="017e6-130">To apply an upgrade to the Front End servers in a pool</span></span>

1. <span data-ttu-id="017e6-131">键入以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="017e6-131">Type the following cmdlet:</span></span>
    
   ```PowerShell
   Get-CsPoolFabricState -PoolFqdn <PoolFQDN>
   ```

     <span data-ttu-id="017e6-132">如果此 cmdlet 显示任何丢失的副本，则运行以下 cmdlet 恢复池，然后再应用任何修补程序。</span><span class="sxs-lookup"><span data-stu-id="017e6-132">If this cmdlet shows any missing replicas, then run the following cmdlet to recover the pool before you apply any patches.</span></span>
    
   ```PowerShell
   Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery
   ```

2. <span data-ttu-id="017e6-133">在要修补的第一台服务器上，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="017e6-133">On the first server you want to patch, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailOver -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="017e6-134">此 cmdlet 会将所有服务移动到池中的其他前端服务器，并使此服务器脱机。</span><span class="sxs-lookup"><span data-stu-id="017e6-134">This cmdlet moves all services to other Front End Servers in the pool, and takes this server offline.</span></span>
    
3. <span data-ttu-id="017e6-135">将升级或修补程序应用到此服务器。</span><span class="sxs-lookup"><span data-stu-id="017e6-135">Apply the upgrade or patch to this server.</span></span>
    
4. <span data-ttu-id="017e6-136">在升级的服务器上，运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="017e6-136">On the upgraded server, run the following cmdlet:</span></span>
    
   ```PowerShell
   Invoke-CsComputerFailBack -ComputerName <Front End Server to be patched>
   ```

    <span data-ttu-id="017e6-137">服务器将返回到服务。</span><span class="sxs-lookup"><span data-stu-id="017e6-137">The server is returned to service.</span></span>
    
5. <span data-ttu-id="017e6-138">对需要升级的每台服务器重复步骤 2-4。</span><span class="sxs-lookup"><span data-stu-id="017e6-138">Repeat Steps 2-4 for each server that needs to be upgraded.</span></span>
