---
title: 前端池高可用性和管理
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: 了解业务服务器，包括管理池、 仲裁丢失和特殊的步骤，只有两个前端服务器与池的前端池管理 Skype 中。
ms.openlocfilehash: ba15e090829256188763a0e7791cebb29f097422
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21005244"
---
# <a name="front-end-pool-high-availability-and-management"></a><span data-ttu-id="7312b-103">前端池高可用性和管理</span><span class="sxs-lookup"><span data-stu-id="7312b-103">Front End Pool high availability and management</span></span>
 
<span data-ttu-id="7312b-104">了解业务服务器，包括管理池、 仲裁丢失和特殊的步骤，只有两个前端服务器与池的前端池管理 Skype 中。</span><span class="sxs-lookup"><span data-stu-id="7312b-104">Learn about Front End pool management in Skype for Business Server, including managing pools, quorum loss, and special steps for pools with only two Front End Servers.</span></span>
  
<span data-ttu-id="7312b-105">Skype 业务服务器，在前端池的体系结构与每个用户的数据保留在池中的三个前端服务器上使用分布式的系统模型。</span><span class="sxs-lookup"><span data-stu-id="7312b-105">In Skype for Business Server, the architecture of Front End pools uses a distributed systems model, with each user's data kept on as many as three Front End servers in the pool.</span></span> <span data-ttu-id="7312b-106">我们建议您的所有 Enterprise Edition 前端池都包括至少使用三个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="7312b-106">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> 
  
## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="7312b-107">规划前端池的管理</span><span class="sxs-lookup"><span data-stu-id="7312b-107">Planning for the management of Front End pools</span></span>

 <span data-ttu-id="7312b-108">Skype 业务服务器使用基于 Windows Fabric 的分布式的系统模型。</span><span class="sxs-lookup"><span data-stu-id="7312b-108">Skype for Business Server uses a distributed systems model based on Windows Fabric.</span></span> <span data-ttu-id="7312b-109">该模型中，为每个用户和会议的重要数据存储三个前端服务器上的前端池。</span><span class="sxs-lookup"><span data-stu-id="7312b-109">In this model, important data for each user and conference is stored on three Front End Servers in a Front End pool.</span></span> <span data-ttu-id="7312b-110">这些存储特定的数据集的三个服务器是 calledreplicas。</span><span class="sxs-lookup"><span data-stu-id="7312b-110">These three servers storing a certain set of data are calledreplicas.</span></span>
  
<span data-ttu-id="7312b-111">与前端池的分布式模型，某些号码的池的服务器必须运行该池的函数。</span><span class="sxs-lookup"><span data-stu-id="7312b-111">With the distributed model for Front End pools, a certain numbers of a pool's servers must be running for the pool to function.</span></span> <span data-ttu-id="7312b-112">有两种丢失模式的池。</span><span class="sxs-lookup"><span data-stu-id="7312b-112">There are two loss modes for a pool.</span></span>
  
- <span data-ttu-id="7312b-p104">路由组级别仲裁丢失，是由于特定路由组的副本服务器不足引起的。路由组是指驻留在池中的一组用户。每个路由组在池中都有三个副本：一个主要副本和两个辅助副本。</span><span class="sxs-lookup"><span data-stu-id="7312b-p104">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group. A routing group is a set of users homed in the pool. Each routing group has three replicas in the pool: one primary replica and two secondary replicas.</span></span>
    
- <span data-ttu-id="7312b-116">池级别仲裁丢失，当池中运行的种子服务器不足时导致的。</span><span class="sxs-lookup"><span data-stu-id="7312b-116">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span> 
    
### <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="7312b-117">路由组级别仲裁丢失</span><span class="sxs-lookup"><span data-stu-id="7312b-117">Routing Group Level quorum loss</span></span>

<span data-ttu-id="7312b-p105">当您首次启动新的前端池时，务必确保有 85% 的服务器已启动且正在运行，如下表所示。如果正在运行的服务器数目较少，则服务可能会滞留在启动状态，而池可能无法启动。</span><span class="sxs-lookup"><span data-stu-id="7312b-p105">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table. If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>
  
|<span data-ttu-id="7312b-120">池中服务器的总数</span><span class="sxs-lookup"><span data-stu-id="7312b-120">Total number of servers in the pool</span></span>  <br/> |<span data-ttu-id="7312b-121">使池第一次启动所必须运行的服务器的数量</span><span class="sxs-lookup"><span data-stu-id="7312b-121">Number of servers that must be running for the pool to be started the first time</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="7312b-122">2</span><span class="sxs-lookup"><span data-stu-id="7312b-122">2</span></span>  <br/> |<span data-ttu-id="7312b-123">1</span><span class="sxs-lookup"><span data-stu-id="7312b-123">1</span></span>  <br/> |
|<span data-ttu-id="7312b-124">3</span><span class="sxs-lookup"><span data-stu-id="7312b-124">3</span></span>  <br/> |<span data-ttu-id="7312b-125">3</span><span class="sxs-lookup"><span data-stu-id="7312b-125">3</span></span>  <br/> |
|<span data-ttu-id="7312b-126">4</span><span class="sxs-lookup"><span data-stu-id="7312b-126">4</span></span>  <br/> |<span data-ttu-id="7312b-127">3</span><span class="sxs-lookup"><span data-stu-id="7312b-127">3</span></span>  <br/> |
|<span data-ttu-id="7312b-128">5</span><span class="sxs-lookup"><span data-stu-id="7312b-128">5</span></span>  <br/> |<span data-ttu-id="7312b-129">4</span><span class="sxs-lookup"><span data-stu-id="7312b-129">4</span></span>  <br/> |
|<span data-ttu-id="7312b-130">6</span><span class="sxs-lookup"><span data-stu-id="7312b-130">6</span></span>  <br/> |<span data-ttu-id="7312b-131">5</span><span class="sxs-lookup"><span data-stu-id="7312b-131">5</span></span>  <br/> |
|<span data-ttu-id="7312b-132">7</span><span class="sxs-lookup"><span data-stu-id="7312b-132">7</span></span>  <br/> |<span data-ttu-id="7312b-133">5</span><span class="sxs-lookup"><span data-stu-id="7312b-133">5</span></span>  <br/> |
|<span data-ttu-id="7312b-134">8</span><span class="sxs-lookup"><span data-stu-id="7312b-134">8</span></span>  <br/> |<span data-ttu-id="7312b-135">6</span><span class="sxs-lookup"><span data-stu-id="7312b-135">6</span></span>  <br/> |
|<span data-ttu-id="7312b-136">9</span><span class="sxs-lookup"><span data-stu-id="7312b-136">9</span></span>  <br/> |<span data-ttu-id="7312b-137">7</span><span class="sxs-lookup"><span data-stu-id="7312b-137">7</span></span>  <br/> |
|<span data-ttu-id="7312b-138">10</span><span class="sxs-lookup"><span data-stu-id="7312b-138">10</span></span>  <br/> |<span data-ttu-id="7312b-139">8</span><span class="sxs-lookup"><span data-stu-id="7312b-139">8</span></span>  <br/> |
|<span data-ttu-id="7312b-140">11</span><span class="sxs-lookup"><span data-stu-id="7312b-140">11</span></span>  <br/> |<span data-ttu-id="7312b-141">9</span><span class="sxs-lookup"><span data-stu-id="7312b-141">9</span></span>  <br/> |
|<span data-ttu-id="7312b-142">12</span><span class="sxs-lookup"><span data-stu-id="7312b-142">12</span></span>  <br/> |<span data-ttu-id="7312b-143">10</span><span class="sxs-lookup"><span data-stu-id="7312b-143">10</span></span>  <br/> |
   
<span data-ttu-id="7312b-144">以后每次启动池时，都应启动 85% 的服务器（如上表所示）。</span><span class="sxs-lookup"><span data-stu-id="7312b-144">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="7312b-145">如果无法启动此服务器的数量 （但可以启动足够的服务器，以便不在池级别仲裁丢失），则可以使用`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery`cmdlet 来启用要恢复此路由组级别仲裁丢失，并使进度的池。</span><span class="sxs-lookup"><span data-stu-id="7312b-145">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="7312b-146">有关如何使用此 cmdlet 的详细信息，请参阅<link Reset-CsPoolRegistrarState>。</span><span class="sxs-lookup"><span data-stu-id="7312b-146">For more information about how to use this cmdlet, see <link Reset-CsPoolRegistrarState>.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7312b-147">在服务器为偶数的池，Skype 业务服务器使用作为见证主 SQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="7312b-147">In pools with an even number of servers, Skype for Business Server uses the Primary SQL database as Witness.</span></span> <span data-ttu-id="7312b-148">在类似池中，如果关闭主数据库和切换到镜像副本，并关闭足够的前端服务器，以便根据前面的表中，运行没有足够的整个池就会降低。</span><span class="sxs-lookup"><span data-stu-id="7312b-148">In a pool like this, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="7312b-149">有关详细信息，请参阅[数据库镜像见证](https://go.microsoft.com/fwlink/?LinkId=393672)。</span><span class="sxs-lookup"><span data-stu-id="7312b-149">For more information, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/?LinkId=393672).</span></span> 
  
#### <a name="pool-level-quorum-loss"></a><span data-ttu-id="7312b-150">池级别仲裁丢失</span><span class="sxs-lookup"><span data-stu-id="7312b-150">Pool-level quorum loss</span></span>

<span data-ttu-id="7312b-151">对于在所有运行的前端池，它不能在池级别仲裁丢失。</span><span class="sxs-lookup"><span data-stu-id="7312b-151">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="7312b-152">如果正在运行的服务器数量低于下表所示的正常运作级别，则池中的其余服务器将停止所有 Skype for Business Server 服务。</span><span class="sxs-lookup"><span data-stu-id="7312b-152">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Skype for Business Server services.</span></span> <span data-ttu-id="7312b-153">请注意下表中的数字假定运行后端服务器池中。</span><span class="sxs-lookup"><span data-stu-id="7312b-153">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>
  
|<span data-ttu-id="7312b-154">池中前端服务器的总数</span><span class="sxs-lookup"><span data-stu-id="7312b-154">Total number of Front End Servers in the pool</span></span>  <br/> |<span data-ttu-id="7312b-155">使池发挥作用所必须运行的服务器的数量</span><span class="sxs-lookup"><span data-stu-id="7312b-155">Number of servers that must be running for pool to be functional</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="7312b-156">2</span><span class="sxs-lookup"><span data-stu-id="7312b-156">2</span></span>  <br/> |<span data-ttu-id="7312b-157">1</span><span class="sxs-lookup"><span data-stu-id="7312b-157">1</span></span>  <br/> |
|<span data-ttu-id="7312b-158">3-4</span><span class="sxs-lookup"><span data-stu-id="7312b-158">3-4</span></span>  <br/> |<span data-ttu-id="7312b-159">任意 2 台</span><span class="sxs-lookup"><span data-stu-id="7312b-159">Any 2</span></span>  <br/> |
|<span data-ttu-id="7312b-160">5-6</span><span class="sxs-lookup"><span data-stu-id="7312b-160">5-6</span></span>  <br/> |<span data-ttu-id="7312b-161">任意 3 台</span><span class="sxs-lookup"><span data-stu-id="7312b-161">Any 3</span></span>  <br/> |
|<span data-ttu-id="7312b-162">7</span><span class="sxs-lookup"><span data-stu-id="7312b-162">7</span></span>  <br/> |<span data-ttu-id="7312b-163">任意 4 台</span><span class="sxs-lookup"><span data-stu-id="7312b-163">Any 4</span></span>  <br/> |
|<span data-ttu-id="7312b-164">8-9</span><span class="sxs-lookup"><span data-stu-id="7312b-164">8-9</span></span>  <br/> |<span data-ttu-id="7312b-165">前 7 台服务器中的任意 4 台</span><span class="sxs-lookup"><span data-stu-id="7312b-165">Any 4 of the first 7 servers</span></span>  <br/> |
|<span data-ttu-id="7312b-166">10-12</span><span class="sxs-lookup"><span data-stu-id="7312b-166">10-12</span></span>  <br/> |<span data-ttu-id="7312b-167">前 9 台服务器中的任意 5 台</span><span class="sxs-lookup"><span data-stu-id="7312b-167">Any 5 of the first 9 servers</span></span>  <br/> |
   
<span data-ttu-id="7312b-168">在前面的表中，"第一个服务器"是其已提出第一次、 排序，首次启动池时的服务器。</span><span class="sxs-lookup"><span data-stu-id="7312b-168">In the preceding table, the "first servers" are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="7312b-169">若要确定这些服务器，您可以使用`Get-CsComputer`cmdlet 与` -PoolFqdn`选项。</span><span class="sxs-lookup"><span data-stu-id="7312b-169">To determine these servers, you can use the  `Get-CsComputer` cmdlet with the ` -PoolFqdn` option.</span></span> <span data-ttu-id="7312b-170">此 cmdlet 将按服务器在池中的出现顺序显示服务器，列表最上方的服务器就是前几台服务器。</span><span class="sxs-lookup"><span data-stu-id="7312b-170">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>
  
#### <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="7312b-171">确保池正常工作的其他步骤</span><span class="sxs-lookup"><span data-stu-id="7312b-171">Additional steps to ensure pools are functional</span></span>

<span data-ttu-id="7312b-172">您应注意其他几项因素，以确保您的前端池仍正常工作。</span><span class="sxs-lookup"><span data-stu-id="7312b-172">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>
  
- <span data-ttu-id="7312b-173">当您在首次向池中移动用户时，请确保至少运行三个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="7312b-173">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>
    
- <span data-ttu-id="7312b-174">如果您为灾难恢复的目的建立此池和另一池之间的一对关系，那么在建立此关系后，必须确保在某些时候此池具有三个同时运行的前端服务器以正确将数据与备份池同步。</span><span class="sxs-lookup"><span data-stu-id="7312b-174">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="7312b-175">有关池配对和灾难恢复功能的详细信息，请参阅[规划高可用性和灾难恢复 Skype 业务服务器中](high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="7312b-175">For more information on pool pairing and disaster recovery features, see [Plan for high availability and disaster recovery in Skype for Business Server](high-availability-and-disaster-recovery.md).</span></span> 
    
## <a name="front-end-pool-with-two-front-end-servers"></a><span data-ttu-id="7312b-176">带有两个前端服务器的前端池</span><span class="sxs-lookup"><span data-stu-id="7312b-176">Front End pool with two Front End servers</span></span>

<span data-ttu-id="7312b-177">建议不要部署包含只有两个前端服务器的前端池。</span><span class="sxs-lookup"><span data-stu-id="7312b-177">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="7312b-178">这种小型池无法像更大的池一样提供强大的高可用性解决方案，同时还需要花费额外精力进行管理。</span><span class="sxs-lookup"><span data-stu-id="7312b-178">This small pool will not provide a robust high-availability solution like a larger pool would, and needs extra care in managing.</span></span> <span data-ttu-id="7312b-179">此外，如果两个服务器池的后端服务器发生故障，整个池本身可能很快会向下以及。</span><span class="sxs-lookup"><span data-stu-id="7312b-179">Additionally, if the Back End Server of a two-server pool went down, the whole pool itself would likely soon go down as well.</span></span> <span data-ttu-id="7312b-180">如果您想要部署运行 Business Server Skype 的只是一个或两个服务器，我们建议您将其部署为 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="7312b-180">If you want to deploy just one or two servers running Skype for Business Server, we recommend you deploy them as Standard Edition servers.</span></span>
  
<span data-ttu-id="7312b-181">如果您的确需要部署具有两个前端服务器池，请遵循以下准则：</span><span class="sxs-lookup"><span data-stu-id="7312b-181">If you do ever need to deploy a pool with two Front End Servers, follow these guidelines:</span></span>
  
- <span data-ttu-id="7312b-182">如果一个两个前端服务器不可用，应尝试只要您可以备份使服务器出现故障。</span><span class="sxs-lookup"><span data-stu-id="7312b-182">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="7312b-183">同样，如果需要升级两台服务器之一，升级完成后将其尽快联机。</span><span class="sxs-lookup"><span data-stu-id="7312b-183">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>
    
- <span data-ttu-id="7312b-184">如果因某些原因需要将两台服务器同时停机，当该池停机后执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="7312b-184">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
  - <span data-ttu-id="7312b-185">最佳做法是同时重新启动两个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="7312b-185">The best practice is to restart both Front End Servers at the same time.</span></span> 
    
  - <span data-ttu-id="7312b-186">如果无法同时重新启动两台服务器，则应该按其停机时的相反顺序来启动它们。</span><span class="sxs-lookup"><span data-stu-id="7312b-186">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
  - <span data-ttu-id="7312b-187">如果您无法备份使它们的顺序，然后将备份池前使用以下 cmdlet:`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span><span class="sxs-lookup"><span data-stu-id="7312b-187">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span></span>
    
## <a name="front-end-pool-configuration-failures-and-changes"></a><span data-ttu-id="7312b-188">前端池配置失败和更改</span><span class="sxs-lookup"><span data-stu-id="7312b-188">Front End pool configuration failures and changes</span></span>

<span data-ttu-id="7312b-p113">如果前端服务器失败，且在近期不可能替换，则从拓扑删除该服务器。当再次可用时向该拓扑添加新的前端服务器。</span><span class="sxs-lookup"><span data-stu-id="7312b-p113">If a Front End server fails and is unlikely to be replaced for a few days or more, remove the server from the topology. Add the new Front End server to the topology when it is available again.</span></span>
  
<span data-ttu-id="7312b-191">在您对前端池作出配置更改时（比如添加或删除服务器），您必须遵守以下准则：</span><span class="sxs-lookup"><span data-stu-id="7312b-191">Whenever you make a configuration change to a Front End pool, such as adding or removing servers, you must follow these guidelines:</span></span>
  
- <span data-ttu-id="7312b-p114">发布新拓扑后，必须在池中重新启动每个前端池。一次重新启动一个。</span><span class="sxs-lookup"><span data-stu-id="7312b-p114">After the new topology has been published, you must restart each Front End server in the pool. Restart them one at a time.</span></span>
    
- <span data-ttu-id="7312b-194">如果在配置更改期间，整个池已关闭，然后发布新拓扑后运行以下 cmdlet:`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span><span class="sxs-lookup"><span data-stu-id="7312b-194">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span></span>
    

