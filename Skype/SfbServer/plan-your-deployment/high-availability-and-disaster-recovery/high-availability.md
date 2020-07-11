---
title: 前端池高可用性和管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: 了解 Skype for Business Server 中的前端池管理，包括管理池、仲裁丢失以及仅有两个前端服务器的池的特殊步骤。
ms.openlocfilehash: 2982e2da0e7a103b5b598019baa7403a73da826d
ms.sourcegitcommit: 397c4840fb053238de24b8b24ae75588b33b693d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2020
ms.locfileid: "45098430"
---
# <a name="front-end-pool-high-availability-and-management"></a><span data-ttu-id="ea5a5-103">前端池高可用性和管理</span><span class="sxs-lookup"><span data-stu-id="ea5a5-103">Front End Pool high availability and management</span></span>
 
<span data-ttu-id="ea5a5-104">了解 Skype for Business Server 中的前端池管理，包括管理池、仲裁丢失以及仅有两个前端服务器的池的特殊步骤。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-104">Learn about Front End pool management in Skype for Business Server, including managing pools, quorum loss, and special steps for pools with only two Front End Servers.</span></span>
  
<span data-ttu-id="ea5a5-105">在 Skype for Business Server 中，前端池的体系结构使用分布式系统模型，每个用户的数据在池中的多个前端服务器上保留为多达三台的前端服务器。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-105">In Skype for Business Server, the architecture of Front End pools uses a distributed systems model, with each user's data kept on as many as three Front End Servers in the pool.</span></span> <span data-ttu-id="ea5a5-106">我们建议您的所有 Enterprise Edition 前端池至少包含三台前端服务器。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-106">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span>

> [!NOTE]
> <span data-ttu-id="ea5a5-107">Skype for Business Server 2019 不支持使用两台前端服务器的 Enterprise Edition 前端池，并且不允许在该方案中发布拓扑。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-107">Skype for Business Server 2019 does not support Enterprise Edition Front End pools with two Front End Servers, and will not allow the topology to be published in that scenario.</span></span>
  
## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="ea5a5-108">规划前端池的管理</span><span class="sxs-lookup"><span data-stu-id="ea5a5-108">Planning for the management of Front End pools</span></span>

 <span data-ttu-id="ea5a5-109">Skype for Business Server 使用基于 Windows Fabric 的分布式系统模型。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-109">Skype for Business Server uses a distributed systems model based on Windows Fabric.</span></span> <span data-ttu-id="ea5a5-110">在此模型中，每个用户和会议的重要数据存储在前端池中的三台前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-110">In this model, important data for each user and conference is stored on three Front End Servers in a Front End pool.</span></span> <span data-ttu-id="ea5a5-111">这三个服务器存储一组特定的数据是 calledreplicas。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-111">These three servers storing a certain set of data are calledreplicas.</span></span>
  
<span data-ttu-id="ea5a5-112">对于前端池的分布式模型，池服务器的一定数量的服务器必须运行，以便池能够正常工作。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-112">With the distributed model for Front End pools, a certain numbers of a pool's servers must be running for the pool to function.</span></span> <span data-ttu-id="ea5a5-113">池有两种丢失模式。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-113">There are two loss modes for a pool.</span></span>
  
- <span data-ttu-id="ea5a5-114">路由组级别仲裁丢失，因特定路由组的副本服务器不足而导致。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-114">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="ea5a5-115">路由组是驻留在池中的一组用户。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-115">A routing group is a set of users homed in the pool.</span></span> <span data-ttu-id="ea5a5-116">每个路由组在池中都有三个副本：一个主副本和两个辅助副本。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-116">Each routing group has three replicas in the pool: one primary replica and two secondary replicas.</span></span>
    
- <span data-ttu-id="ea5a5-117">池级别仲裁丢失，在池中没有足够的种子服务器运行时导致。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-117">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span> 
    
### <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="ea5a5-118">路由组级别仲裁丢失</span><span class="sxs-lookup"><span data-stu-id="ea5a5-118">Routing Group Level quorum loss</span></span>

<span data-ttu-id="ea5a5-119">首次启动新的前端池时，有85% 的服务器已启动并且正在运行，这一点非常重要，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-119">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table.</span></span> <span data-ttu-id="ea5a5-120">如果运行较少的服务器，服务可能会处于 "启动" 状态，并且池可能无法启动。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-120">If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>
  
|<span data-ttu-id="ea5a5-121">池中的服务器总数</span><span class="sxs-lookup"><span data-stu-id="ea5a5-121">Total number of servers in the pool</span></span>  <br/> |<span data-ttu-id="ea5a5-122">在首次启动池时必须运行的服务器的数量</span><span class="sxs-lookup"><span data-stu-id="ea5a5-122">Number of servers that must be running for the pool to be started the first time</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="ea5a5-123">2 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-123">2</span></span>  <br/> |<span data-ttu-id="ea5a5-124">1 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-124">1</span></span>  <br/> |
|<span data-ttu-id="ea5a5-125">3 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-125">3</span></span>  <br/> |<span data-ttu-id="ea5a5-126">3 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-126">3</span></span>  <br/> |
|<span data-ttu-id="ea5a5-127">4 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-127">4</span></span>  <br/> |<span data-ttu-id="ea5a5-128">3 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-128">3</span></span>  <br/> |
|<span data-ttu-id="ea5a5-129">5 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-129">5</span></span>  <br/> |<span data-ttu-id="ea5a5-130">4 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-130">4</span></span>  <br/> |
|<span data-ttu-id="ea5a5-131">6 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-131">6</span></span>  <br/> |<span data-ttu-id="ea5a5-132">5 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-132">5</span></span>  <br/> |
|<span data-ttu-id="ea5a5-133">7 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-133">7</span></span>  <br/> |<span data-ttu-id="ea5a5-134">5 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-134">5</span></span>  <br/> |
|<span data-ttu-id="ea5a5-135">8 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-135">8</span></span>  <br/> |<span data-ttu-id="ea5a5-136">6 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-136">6</span></span>  <br/> |
|<span data-ttu-id="ea5a5-137">9 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-137">9</span></span>  <br/> |<span data-ttu-id="ea5a5-138">7 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-138">7</span></span>  <br/> |
|<span data-ttu-id="ea5a5-139">10 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-139">10</span></span>  <br/> |<span data-ttu-id="ea5a5-140">8 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-140">8</span></span>  <br/> |
|<span data-ttu-id="ea5a5-141">11 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-141">11</span></span>  <br/> |<span data-ttu-id="ea5a5-142">9 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-142">9</span></span>  <br/> |
|<span data-ttu-id="ea5a5-143">12 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-143">12</span></span>  <br/> |<span data-ttu-id="ea5a5-144">10 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-144">10</span></span>  <br/> |
|<span data-ttu-id="ea5a5-145">16 **（适用于 Skype for Business Server 2019** ）</span><span class="sxs-lookup"><span data-stu-id="ea5a5-145">16 **For Skype for Business Server 2019**</span></span> <br/> |<span data-ttu-id="ea5a5-146">12 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-146">12</span></span>  <br/> |


   
<span data-ttu-id="ea5a5-147">每次启动池时，应启动85% 的服务器 (，如上表中所示) 。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-147">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="ea5a5-148">如果无法启动此数量的服务器 (但可以启动足够的服务器，以便不会) 池级别的仲裁丢失，则可以使用 `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet 使池能够从该路由组级别仲裁丢失恢复并进行操作。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-148">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="ea5a5-149">有关如何使用此 cmdlet 的详细信息，请参阅[Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps)。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-149">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/reset-cspoolregistrarstate?view=skype-ps).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ea5a5-150">在具有偶数台服务器的池中，Skype for Business Server 使用主 SQL 数据库作为见证。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-150">In pools with an even number of servers, Skype for Business Server uses the Primary SQL database as Witness.</span></span> <span data-ttu-id="ea5a5-151">在这种情况下，如果关闭主数据库并切换到镜像副本，并关闭足够的前端服务器，以便根据前面的表运行，则整个池将会停止运行。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-151">In a pool like this, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="ea5a5-152">有关详细信息，请参阅[数据库镜像见证](https://go.microsoft.com/fwlink/?LinkId=393672)。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-152">For more information, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/?LinkId=393672).</span></span> 
  
#### <a name="pool-level-quorum-loss"></a><span data-ttu-id="ea5a5-153">池级别仲裁丢失</span><span class="sxs-lookup"><span data-stu-id="ea5a5-153">Pool-level quorum loss</span></span>

<span data-ttu-id="ea5a5-154">为了让前端池能够正常运行，它不能处于池级别仲裁丢失。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-154">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="ea5a5-155">如果运行的服务器数低于功能级别，如下表所示，池中的其余服务器将停止所有 Skype for Business Server 服务。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-155">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Skype for Business Server services.</span></span> <span data-ttu-id="ea5a5-156">请注意，下表中的数字假定池中的后端服务器正在运行。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-156">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>
  
|<span data-ttu-id="ea5a5-157">池中的前端服务器总数</span><span class="sxs-lookup"><span data-stu-id="ea5a5-157">Total number of Front End Servers in the pool</span></span>  <br/> |<span data-ttu-id="ea5a5-158">要使池正常工作所必须运行的服务器的数目</span><span class="sxs-lookup"><span data-stu-id="ea5a5-158">Number of servers that must be running for pool to be functional</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="ea5a5-159">2 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-159">2</span></span>  <br/> |<span data-ttu-id="ea5a5-160">1 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-160">1</span></span>  <br/> |
|<span data-ttu-id="ea5a5-161">3-4</span><span class="sxs-lookup"><span data-stu-id="ea5a5-161">3-4</span></span>  <br/> |<span data-ttu-id="ea5a5-162">任意2</span><span class="sxs-lookup"><span data-stu-id="ea5a5-162">Any 2</span></span>  <br/> |
|<span data-ttu-id="ea5a5-163">5-6</span><span class="sxs-lookup"><span data-stu-id="ea5a5-163">5-6</span></span>  <br/> |<span data-ttu-id="ea5a5-164">任意3</span><span class="sxs-lookup"><span data-stu-id="ea5a5-164">Any 3</span></span>  <br/> |
|<span data-ttu-id="ea5a5-165">7 </span><span class="sxs-lookup"><span data-stu-id="ea5a5-165">7</span></span>  <br/> |<span data-ttu-id="ea5a5-166">任意4</span><span class="sxs-lookup"><span data-stu-id="ea5a5-166">Any 4</span></span>  <br/> |
|<span data-ttu-id="ea5a5-167">8-9</span><span class="sxs-lookup"><span data-stu-id="ea5a5-167">8-9</span></span>  <br/> |<span data-ttu-id="ea5a5-168">前7台服务器中的任意4个</span><span class="sxs-lookup"><span data-stu-id="ea5a5-168">Any 4 of the first 7 servers</span></span>  <br/> |
|<span data-ttu-id="ea5a5-169">10-12</span><span class="sxs-lookup"><span data-stu-id="ea5a5-169">10-12</span></span>  <br/> |<span data-ttu-id="ea5a5-170">前9个服务器中的任何5个</span><span class="sxs-lookup"><span data-stu-id="ea5a5-170">Any 5 of the first 9 servers</span></span>  <br/> |
|<span data-ttu-id="ea5a5-171">**适用于 Skype For Business Server 2019 的**12-16</span><span class="sxs-lookup"><span data-stu-id="ea5a5-171">12-16  **For Skype for Business Server 2019**</span></span>  <br/> |<span data-ttu-id="ea5a5-172">前12个服务器中的任何7个</span><span class="sxs-lookup"><span data-stu-id="ea5a5-172">Any 7 of the first 12 servers</span></span>  <br/> |
   
<span data-ttu-id="ea5a5-173">在上表中，"第一台服务器" 是第一次启动池时的服务器。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-173">In the preceding table, the "first servers" are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="ea5a5-174">若要确定这些服务器，可以将 `Get-CsComputer` cmdlet 与选项一起使用 `-PoolFqdn` 。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-174">To determine these servers, you can use the  `Get-CsComputer` cmdlet with the `-PoolFqdn` option.</span></span> <span data-ttu-id="ea5a5-175">此 cmdlet 将按其在拓扑中出现的顺序显示服务器，列表顶部的服务器是第一台服务器。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-175">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ea5a5-176">[Skype For Business Server 2019](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019)中已将最大前端服务器数增加到16个</span><span class="sxs-lookup"><span data-stu-id="ea5a5-176">The maximum number of front end servers has been increased to 16 in [Skype for Business Server 2019](https://docs.microsoft.com/skypeforbusiness/plan/user-model-2019)</span></span>
> 
#### <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="ea5a5-177">确保池正常运行的其他步骤</span><span class="sxs-lookup"><span data-stu-id="ea5a5-177">Additional steps to ensure pools are functional</span></span>

<span data-ttu-id="ea5a5-178">您应观看几个其他因素，以确保前端池保持正常运行。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-178">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>
  
- <span data-ttu-id="ea5a5-179">当第一次将用户移动到池时，确保至少运行三个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-179">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>
    
- <span data-ttu-id="ea5a5-180">如果在此池与另一个池之间建立了配对关系以用于灾难恢复目的，则必须确保该池在一段时间内同时运行三台前端服务器，以便正确地将数据与备份池同步。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-180">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="ea5a5-181">有关池配对和灾难恢复功能的详细信息，请参阅[在 Skype For Business Server 中规划高可用性和灾难恢复](high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-181">For more information on pool pairing and disaster recovery features, see [Plan for high availability and disaster recovery in Skype for Business Server](high-availability-and-disaster-recovery.md).</span></span> 
    
## <a name="front-end-pool-with-two-front-end-servers"></a><span data-ttu-id="ea5a5-182">具有两个前端服务器的前端池</span><span class="sxs-lookup"><span data-stu-id="ea5a5-182">Front End pool with two Front End servers</span></span>

<span data-ttu-id="ea5a5-183">建议不要部署仅包含两台前端服务器的前端池。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-183">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="ea5a5-184">此小型池不会提供强大的高可用性解决方案，如更大的池，并且在管理时需要格外小心。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-184">This small pool will not provide a robust high-availability solution like a larger pool would, and needs extra care in managing.</span></span> <span data-ttu-id="ea5a5-185">此外，如果两个服务器池的后端服务器停止运行，则整个池本身可能也会发生故障。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-185">Additionally, if the Back End Server of a two-server pool went down, the whole pool itself would likely soon go down as well.</span></span> <span data-ttu-id="ea5a5-186">如果要仅部署一个或两个运行 Skype for Business Server 的服务器，建议将它们作为 Standard Edition 服务器进行部署。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-186">If you want to deploy just one or two servers running Skype for Business Server, we recommend you deploy them as Standard Edition servers.</span></span>
  
<span data-ttu-id="ea5a5-187">如果您需要部署两台前端服务器的池，请遵循以下准则：</span><span class="sxs-lookup"><span data-stu-id="ea5a5-187">If you do ever need to deploy a pool with two Front End Servers, follow these guidelines:</span></span>
  
- <span data-ttu-id="ea5a5-188">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span><span class="sxs-lookup"><span data-stu-id="ea5a5-188">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="ea5a5-189">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span><span class="sxs-lookup"><span data-stu-id="ea5a5-189">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>
    
- <span data-ttu-id="ea5a5-190">如果因某些原因需要将两台服务器同时停机，当该池停机后执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="ea5a5-190">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
  - <span data-ttu-id="ea5a5-191">最佳做法是同时重新启动这两个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-191">The best practice is to restart both Front End Servers at the same time.</span></span> 
    
  - <span data-ttu-id="ea5a5-192">如果无法同时重新启动两台服务器，则应该按其停机时的相反顺序来启动它们。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-192">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
  - <span data-ttu-id="ea5a5-193">如果不能按该顺序备份，请使用以下 cmdlet，然后再使池恢复：`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span><span class="sxs-lookup"><span data-stu-id="ea5a5-193">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span></span>
    
## <a name="front-end-pool-configuration-failures-and-changes"></a><span data-ttu-id="ea5a5-194">前端池配置失败和更改</span><span class="sxs-lookup"><span data-stu-id="ea5a5-194">Front End pool configuration failures and changes</span></span>

<span data-ttu-id="ea5a5-195">如果前端服务器出现故障且不太可能被替换几天或更多时间，请从拓扑中删除该服务器。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-195">If a Front End server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="ea5a5-196">将新的前端服务器添加到拓扑中（当它再次可用时）。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-196">Add the new Front End server to the topology when it is available again.</span></span>
  
<span data-ttu-id="ea5a5-197">无论何时对前端池进行配置更改（如添加或删除服务器），都必须遵循以下准则：</span><span class="sxs-lookup"><span data-stu-id="ea5a5-197">Whenever you make a configuration change to a Front End pool, such as adding or removing servers, you must follow these guidelines:</span></span>
  
- <span data-ttu-id="ea5a5-198">发布新拓扑后，必须重新启动池中的每台前端服务器。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-198">After the new topology has been published, you must restart each Front End server in the pool.</span></span> <span data-ttu-id="ea5a5-199">一次重新启动一个。</span><span class="sxs-lookup"><span data-stu-id="ea5a5-199">Restart them one at a time.</span></span>
    
- <span data-ttu-id="ea5a5-200">如果在配置更改过程中整个池已关闭，则在发布新拓扑后，请运行以下 cmdlet：`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span><span class="sxs-lookup"><span data-stu-id="ea5a5-200">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span></span>
    

