---
title: 前端池高可用性和管理
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: 了解 Skype for Business Server 中的前端池管理，包括管理池、仲裁丢失和仅包含两台前端服务器的池的特殊步骤。
ms.openlocfilehash: 47e4b2157961a2856256e3d96a0676dd86d3f996
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093070"
---
# <a name="front-end-pool-high-availability-and-management"></a><span data-ttu-id="2ba6f-103">前端池高可用性和管理</span><span class="sxs-lookup"><span data-stu-id="2ba6f-103">Front End Pool high availability and management</span></span>
 
<span data-ttu-id="2ba6f-104">了解 Skype for Business Server 中的前端池管理，包括管理池、仲裁丢失和仅包含两台前端服务器的池的特殊步骤。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-104">Learn about Front End pool management in Skype for Business Server, including managing pools, quorum loss, and special steps for pools with only two Front End Servers.</span></span>
  
<span data-ttu-id="2ba6f-105">在 Skype for Business Server 中，前端池的体系结构使用分布式系统模型，每个用户的数据在池中的三个前端服务器上保留。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-105">In Skype for Business Server, the architecture of Front End pools uses a distributed systems model, with each user's data kept on as many as three Front End Servers in the pool.</span></span> <span data-ttu-id="2ba6f-106">我们建议所有 Enterprise Edition 前端池包括至少三台前端服务器。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-106">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span>

> [!NOTE]
> <span data-ttu-id="2ba6f-107">Skype for Business Server 2019 不支持具有两台前端服务器的 Enterprise Edition 前端池，并且不允许在该方案中发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-107">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>
  
## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="2ba6f-108">规划前端池的管理</span><span class="sxs-lookup"><span data-stu-id="2ba6f-108">Planning for the management of Front End pools</span></span>

 <span data-ttu-id="2ba6f-109">Skype for Business Server 使用基于 Windows Fabric 的分布式系统模型。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-109">Skype for Business Server uses a distributed systems model based on Windows Fabric.</span></span> <span data-ttu-id="2ba6f-110">在此模型中，每个用户和会议的重要数据存储在前端池中的三台前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-110">In this model, important data for each user and conference is stored on three Front End Servers in a Front End pool.</span></span> <span data-ttu-id="2ba6f-111">这三个存储特定数据集的服务器称为replicas。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-111">These three servers storing a certain set of data are calledreplicas.</span></span>
  
<span data-ttu-id="2ba6f-112">使用前端池的分布式模型，必须运行一定数量的池服务器，池正常运行。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-112">With the distributed model for Front End pools, a certain numbers of a pool's servers must be running for the pool to function.</span></span> <span data-ttu-id="2ba6f-113">池有两种丢失模式。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-113">There are two loss modes for a pool.</span></span>
  
- <span data-ttu-id="2ba6f-114">路由组级别仲裁丢失，由特定路由组的副本服务器不足导致。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-114">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="2ba6f-115">路由组是池中的一组用户。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-115">A routing group is a set of users homed in the pool.</span></span> <span data-ttu-id="2ba6f-116">每个路由组在池中有三个副本：一个主要副本和两个辅助副本。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-116">Each routing group has three replicas in the pool: one primary replica and two secondary replicas.</span></span>
    
- <span data-ttu-id="2ba6f-117">池级别仲裁丢失，在池中运行种子服务器不足时导致。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-117">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span> 
    
### <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="2ba6f-118">路由组级别仲裁丢失</span><span class="sxs-lookup"><span data-stu-id="2ba6f-118">Routing Group Level quorum loss</span></span>

<span data-ttu-id="2ba6f-119">首次启动新的前端池时，85% 的服务器必须启动并运行，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-119">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table.</span></span> <span data-ttu-id="2ba6f-120">如果正在运行的服务器较少，则服务可能卡在启动状态，并且池可能无法启动。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-120">If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>
  
|<span data-ttu-id="2ba6f-121">池中的服务器总数</span><span class="sxs-lookup"><span data-stu-id="2ba6f-121">Total number of servers in the pool</span></span>  <br/> |<span data-ttu-id="2ba6f-122">首次启动池时必须运行的服务器数</span><span class="sxs-lookup"><span data-stu-id="2ba6f-122">Number of servers that must be running for the pool to be started the first time</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="2ba6f-123">2</span><span class="sxs-lookup"><span data-stu-id="2ba6f-123">2</span></span>  <br/> |<span data-ttu-id="2ba6f-124">1</span><span class="sxs-lookup"><span data-stu-id="2ba6f-124">1</span></span>  <br/> |
|<span data-ttu-id="2ba6f-125">3</span><span class="sxs-lookup"><span data-stu-id="2ba6f-125">3</span></span>  <br/> |<span data-ttu-id="2ba6f-126">3</span><span class="sxs-lookup"><span data-stu-id="2ba6f-126">3</span></span>  <br/> |
|<span data-ttu-id="2ba6f-127">4 </span><span class="sxs-lookup"><span data-stu-id="2ba6f-127">4</span></span>  <br/> |<span data-ttu-id="2ba6f-128">3</span><span class="sxs-lookup"><span data-stu-id="2ba6f-128">3</span></span>  <br/> |
|<span data-ttu-id="2ba6f-129">5 </span><span class="sxs-lookup"><span data-stu-id="2ba6f-129">5</span></span>  <br/> |<span data-ttu-id="2ba6f-130">4 </span><span class="sxs-lookup"><span data-stu-id="2ba6f-130">4</span></span>  <br/> |
|<span data-ttu-id="2ba6f-131">6 </span><span class="sxs-lookup"><span data-stu-id="2ba6f-131">6</span></span>  <br/> |<span data-ttu-id="2ba6f-132">5 </span><span class="sxs-lookup"><span data-stu-id="2ba6f-132">5</span></span>  <br/> |
|<span data-ttu-id="2ba6f-133">7 </span><span class="sxs-lookup"><span data-stu-id="2ba6f-133">7</span></span>  <br/> |<span data-ttu-id="2ba6f-134">5 </span><span class="sxs-lookup"><span data-stu-id="2ba6f-134">5</span></span>  <br/> |
|<span data-ttu-id="2ba6f-135">8 </span><span class="sxs-lookup"><span data-stu-id="2ba6f-135">8</span></span>  <br/> |<span data-ttu-id="2ba6f-136">6 </span><span class="sxs-lookup"><span data-stu-id="2ba6f-136">6</span></span>  <br/> |
|<span data-ttu-id="2ba6f-137">9 </span><span class="sxs-lookup"><span data-stu-id="2ba6f-137">9</span></span>  <br/> |<span data-ttu-id="2ba6f-138">7 </span><span class="sxs-lookup"><span data-stu-id="2ba6f-138">7</span></span>  <br/> |
|<span data-ttu-id="2ba6f-139">10  </span><span class="sxs-lookup"><span data-stu-id="2ba6f-139">10</span></span>  <br/> |<span data-ttu-id="2ba6f-140">8 </span><span class="sxs-lookup"><span data-stu-id="2ba6f-140">8</span></span>  <br/> |
|<span data-ttu-id="2ba6f-141">11</span><span class="sxs-lookup"><span data-stu-id="2ba6f-141">11</span></span>  <br/> |<span data-ttu-id="2ba6f-142">9 </span><span class="sxs-lookup"><span data-stu-id="2ba6f-142">9</span></span>  <br/> |
|<span data-ttu-id="2ba6f-143">12 </span><span class="sxs-lookup"><span data-stu-id="2ba6f-143">12</span></span>  <br/> |<span data-ttu-id="2ba6f-144">10  </span><span class="sxs-lookup"><span data-stu-id="2ba6f-144">10</span></span>  <br/> |
|<span data-ttu-id="2ba6f-145">16 **For Skype for Business Server 2019**</span><span class="sxs-lookup"><span data-stu-id="2ba6f-145">16 **For Skype for Business Server 2019**</span></span> <br/> |<span data-ttu-id="2ba6f-146">12 </span><span class="sxs-lookup"><span data-stu-id="2ba6f-146">12</span></span>  <br/> |


   
<span data-ttu-id="2ba6f-147">每次启动池时，都应启动 85% 的服务器 (如上表所示) 。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-147">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="2ba6f-148">如果无法启动此数量的服务器 (但可以启动足够的服务器，以便不处于池级别的仲裁丢失) ，您可以使用 cmdlet 使池从此路由组级别仲裁丢失中恢复并推进。 `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery`</span><span class="sxs-lookup"><span data-stu-id="2ba6f-148">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="2ba6f-149">有关如何使用此 cmdlet 的信息，请参阅 [Reset-CsPoolRegistrarState](/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-149">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="2ba6f-150">在服务器数量为等多的池中，Skype for Business Server 使用主SQL数据库作为见证。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-150">In pools with an even number of servers, Skype for Business Server uses the Primary SQL database as Witness.</span></span> <span data-ttu-id="2ba6f-151">在此类池中，如果关闭主数据库并切换到镜像副本，并关闭足够的前端服务器，以便根据上表运行不足，整个池将停机。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-151">In a pool like this, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="2ba6f-152">有关详细信息，请参阅数据库 [镜像见证](/sql/database-engine/database-mirroring/database-mirroring-witness)。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-152">For more information, see [Database Mirroring Witness](/sql/database-engine/database-mirroring/database-mirroring-witness).</span></span> 
  
#### <a name="pool-level-quorum-loss"></a><span data-ttu-id="2ba6f-153">池级别仲裁丢失</span><span class="sxs-lookup"><span data-stu-id="2ba6f-153">Pool-level quorum loss</span></span>

<span data-ttu-id="2ba6f-154">前端池可以正常工作，它不能处于池级别仲裁丢失状态。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-154">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="2ba6f-155">如果正在运行的服务器数量低于下表所示的功能级别，则池中的其余服务器将停止所有 Skype for Business Server 服务。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-155">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Skype for Business Server services.</span></span> <span data-ttu-id="2ba6f-156">请注意，下表中的数字假定池中的后端服务器正在运行。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-156">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>
  
|<span data-ttu-id="2ba6f-157">池中的前端服务器总数</span><span class="sxs-lookup"><span data-stu-id="2ba6f-157">Total number of Front End Servers in the pool</span></span>  <br/> |<span data-ttu-id="2ba6f-158">要使池正常工作所必须运行的服务器的数目</span><span class="sxs-lookup"><span data-stu-id="2ba6f-158">Number of servers that must be running for pool to be functional</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="2ba6f-159">2</span><span class="sxs-lookup"><span data-stu-id="2ba6f-159">2</span></span>  <br/> |<span data-ttu-id="2ba6f-160">1</span><span class="sxs-lookup"><span data-stu-id="2ba6f-160">1</span></span>  <br/> |
|<span data-ttu-id="2ba6f-161">3-4</span><span class="sxs-lookup"><span data-stu-id="2ba6f-161">3-4</span></span>  <br/> |<span data-ttu-id="2ba6f-162">任意 2 个</span><span class="sxs-lookup"><span data-stu-id="2ba6f-162">Any 2</span></span>  <br/> |
|<span data-ttu-id="2ba6f-163">5-6</span><span class="sxs-lookup"><span data-stu-id="2ba6f-163">5-6</span></span>  <br/> |<span data-ttu-id="2ba6f-164">任意 3 个</span><span class="sxs-lookup"><span data-stu-id="2ba6f-164">Any 3</span></span>  <br/> |
|<span data-ttu-id="2ba6f-165">7 </span><span class="sxs-lookup"><span data-stu-id="2ba6f-165">7</span></span>  <br/> |<span data-ttu-id="2ba6f-166">任意 4 个</span><span class="sxs-lookup"><span data-stu-id="2ba6f-166">Any 4</span></span>  <br/> |
|<span data-ttu-id="2ba6f-167">8-9</span><span class="sxs-lookup"><span data-stu-id="2ba6f-167">8-9</span></span>  <br/> |<span data-ttu-id="2ba6f-168">前 7 台服务器中的任意 4 台</span><span class="sxs-lookup"><span data-stu-id="2ba6f-168">Any 4 of the first 7 servers</span></span>  <br/> |
|<span data-ttu-id="2ba6f-169">10-12</span><span class="sxs-lookup"><span data-stu-id="2ba6f-169">10-12</span></span>  <br/> |<span data-ttu-id="2ba6f-170">前 9 台服务器中的任意 5 台</span><span class="sxs-lookup"><span data-stu-id="2ba6f-170">Any 5 of the first 9 servers</span></span>  <br/> |
|<span data-ttu-id="2ba6f-171">12-16  **for Skype for Business Server 2019**</span><span class="sxs-lookup"><span data-stu-id="2ba6f-171">12-16  **For Skype for Business Server 2019**</span></span>  <br/> |<span data-ttu-id="2ba6f-172">前 12 台服务器中的任意 7 台</span><span class="sxs-lookup"><span data-stu-id="2ba6f-172">Any 7 of the first 12 servers</span></span>  <br/> |
   
<span data-ttu-id="2ba6f-173">在上表中，"第一台服务器"是首次启动池时按时间顺序首先启动的服务器。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-173">In the preceding table, the "first servers" are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="2ba6f-174">若要确定这些服务器，可以将  `Get-CsComputer` cmdlet 与 `-PoolFqdn` 选项一同使用。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-174">To determine these servers, you can use the  `Get-CsComputer` cmdlet with the `-PoolFqdn` option.</span></span> <span data-ttu-id="2ba6f-175">此 cmdlet 将按服务器在拓扑中的显示顺序显示服务器，列表顶部的服务器是第一批服务器。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-175">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2ba6f-176">[在 Skype for Business Server 2019](../../../SfBServer2019/plan/user-model-2019.md)中，前端服务器的最大数量已增加到 16 台</span><span class="sxs-lookup"><span data-stu-id="2ba6f-176">The maximum number of front end servers has been increased to 16 in [Skype for Business Server 2019](../../../SfBServer2019/plan/user-model-2019.md)</span></span>
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="2ba6f-177">确保池正常工作的其他步骤</span><span class="sxs-lookup"><span data-stu-id="2ba6f-177">Additional steps to ensure pools are functional</span></span>

<span data-ttu-id="2ba6f-178">应留意一些其他因素，以确保前端池继续正常工作。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-178">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>
  
- <span data-ttu-id="2ba6f-179">当第一次将用户移动到池时，确保至少运行三个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-179">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>
    
- <span data-ttu-id="2ba6f-180">如果出于灾难恢复目的在此池与其他池之间建立了配对关系，则建立此关系后，必须确保该池有三个前端服务器同时运行，以便正确将数据与备份池同步。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-180">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="2ba6f-181">有关池配对和灾难恢复功能详细信息，请参阅 Plan [for high availability and disaster recovery in Skype for Business Server。](high-availability-and-disaster-recovery.md)</span><span class="sxs-lookup"><span data-stu-id="2ba6f-181">For more information on pool pairing and disaster recovery features, see [Plan for high availability and disaster recovery in Skype for Business Server](high-availability-and-disaster-recovery.md).</span></span> 
    
## <a name="front-end-pool-with-two-front-end-servers"></a><span data-ttu-id="2ba6f-182">具有两台前端服务器的前端池</span><span class="sxs-lookup"><span data-stu-id="2ba6f-182">Front End pool with two Front End servers</span></span>

<span data-ttu-id="2ba6f-183">建议不要部署仅包含两台前端服务器的前端池。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-183">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="2ba6f-184">此小型池不会像大型池那样提供可靠的高可用性解决方案，并且需要额外注意管理。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-184">This small pool will not provide a robust high-availability solution like a larger pool would, and needs extra care in managing.</span></span> <span data-ttu-id="2ba6f-185">此外，如果双服务器池的后端服务器关闭，则整个池本身可能很快也会关闭。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-185">Additionally, if the Back End Server of a two-server pool went down, the whole pool itself would likely soon go down as well.</span></span> <span data-ttu-id="2ba6f-186">如果你只想部署一台或两台运行 Skype for Business Server 的服务器，建议将它们部署为 Standard Edition Server。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-186">If you want to deploy just one or two servers running Skype for Business Server, we recommend you deploy them as Standard Edition servers.</span></span>
  
<span data-ttu-id="2ba6f-187">如果您曾经需要部署具有两台前端服务器的池，请遵循以下指南：</span><span class="sxs-lookup"><span data-stu-id="2ba6f-187">If you do ever need to deploy a pool with two Front End Servers, follow these guidelines:</span></span>
  
- <span data-ttu-id="2ba6f-p112">如果两个前端服务器之一停机，您应尝试将该失败的服务器尽快恢复运行。同样，如果需要升级两台服务器之一，升级完成后将其尽快联机。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-p112">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can. Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>
    
- <span data-ttu-id="2ba6f-190">如果因某些原因需要将两台服务器同时停机，当该池停机后执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="2ba6f-190">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
  - <span data-ttu-id="2ba6f-191">最佳做法是同时重新启动两台前端服务器。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-191">The best practice is to restart both Front End Servers at the same time.</span></span> 
    
  - <span data-ttu-id="2ba6f-192">如果无法同时重新启动两台服务器，则应该按其停机时的相反顺序来启动它们。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-192">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
  - <span data-ttu-id="2ba6f-193">如果无法按此顺序进行备份，则先使用以下 cmdlet，然后再备份池：  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span><span class="sxs-lookup"><span data-stu-id="2ba6f-193">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span></span>
    
## <a name="front-end-pool-configuration-failures-and-changes"></a><span data-ttu-id="2ba6f-194">前端池配置失败和更改</span><span class="sxs-lookup"><span data-stu-id="2ba6f-194">Front End pool configuration failures and changes</span></span>

<span data-ttu-id="2ba6f-195">如果前端服务器出现故障，且在几天或几天内不太可能替换，请从拓扑中删除该服务器。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-195">If a Front End server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="2ba6f-196">当新的前端服务器再次可用时，将新前端服务器添加到拓扑中。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-196">Add the new Front End server to the topology when it is available again.</span></span>
  
<span data-ttu-id="2ba6f-197">每当对前端池进行配置更改（如添加或删除服务器）时，都必须遵循以下准则：</span><span class="sxs-lookup"><span data-stu-id="2ba6f-197">Whenever you make a configuration change to a Front End pool, such as adding or removing servers, you must follow these guidelines:</span></span>
  
- <span data-ttu-id="2ba6f-198">发布新拓扑后，必须重新启动池中的每个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-198">After the new topology has been published, you must restart each Front End server in the pool.</span></span> <span data-ttu-id="2ba6f-199">一次重新启动一个。</span><span class="sxs-lookup"><span data-stu-id="2ba6f-199">Restart them one at a time.</span></span>
    
- <span data-ttu-id="2ba6f-200">如果在配置更改期间整个池已关闭，则发布新拓扑后运行以下 cmdlet：  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span><span class="sxs-lookup"><span data-stu-id="2ba6f-200">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span></span>
