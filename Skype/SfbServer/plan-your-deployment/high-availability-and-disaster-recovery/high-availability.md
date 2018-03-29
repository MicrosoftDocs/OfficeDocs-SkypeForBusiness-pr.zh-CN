---
title: 前端池高可用性和管理
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 12/20/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 965041b7-3136-49f2-89c1-8b30417cb8ea
description: 了解如何在 Skype 业务服务器，包括管理池、 仲裁丢失和特殊的步骤只有两个前端服务器与池的前端池管理。
ms.openlocfilehash: f348fcc4fee6a48a41265da88fe432d9e4550b6c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="front-end-pool-high-availability-and-management"></a><span data-ttu-id="c6a82-103">前端池高可用性和管理</span><span class="sxs-lookup"><span data-stu-id="c6a82-103">Front End Pool high availability and management</span></span>
 
<span data-ttu-id="c6a82-104">了解如何在 Skype 业务服务器，包括管理池、 仲裁丢失和特殊的步骤只有两个前端服务器与池的前端池管理。</span><span class="sxs-lookup"><span data-stu-id="c6a82-104">Learn about Front End pool management in Skype for Business Server, including managing pools, quorum loss, and special steps for pools with only two Front End Servers.</span></span>
  
<span data-ttu-id="c6a82-105">在 Skype 业务服务器，前端池的体系结构与每个用户的数据保留在池中的三个前端服务器上使用的分布式的系统模型。</span><span class="sxs-lookup"><span data-stu-id="c6a82-105">In Skype for Business Server, the architecture of Front End pools uses a distributed systems model, with each user's data kept on as many as three Front End servers in the pool.</span></span> <span data-ttu-id="c6a82-106">我们建议所有的前端企业版池包括至少三个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="c6a82-106">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> 
  
## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="c6a82-107">规划前端池的管理</span><span class="sxs-lookup"><span data-stu-id="c6a82-107">Planning for the management of Front End pools</span></span>

 <span data-ttu-id="c6a82-108">Skype 业务服务器使用基于 Windows 结构的分布式的系统模型。</span><span class="sxs-lookup"><span data-stu-id="c6a82-108">Skype for Business Server uses a distributed systems model based on Windows Fabric.</span></span> <span data-ttu-id="c6a82-109">在此模型中，每个用户和会议的重要数据存储在三个前端服务器前端池中。</span><span class="sxs-lookup"><span data-stu-id="c6a82-109">In this model, important data for each user and conference is stored on three Front End Servers in a Front End pool.</span></span> <span data-ttu-id="c6a82-110">这些存储特定的数据集的三个服务器是 calledreplicas。</span><span class="sxs-lookup"><span data-stu-id="c6a82-110">These three servers storing a certain set of data are calledreplicas.</span></span>
  
<span data-ttu-id="c6a82-111">与前端池的分布式模型，某些数字的池的服务器必须运行池函数。</span><span class="sxs-lookup"><span data-stu-id="c6a82-111">With the distributed model for Front End pools, a certain numbers of a pool's servers must be running for the pool to function.</span></span> <span data-ttu-id="c6a82-112">有两个池损失模式。</span><span class="sxs-lookup"><span data-stu-id="c6a82-112">There are two loss modes for a pool.</span></span>
  
- <span data-ttu-id="c6a82-113">路由组级别仲裁丢失，由特定的路由组没有足够副本服务器。</span><span class="sxs-lookup"><span data-stu-id="c6a82-113">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="c6a82-114">路由组是指驻留在池中的一组用户。</span><span class="sxs-lookup"><span data-stu-id="c6a82-114">A routing group is a set of users homed in the pool.</span></span> <span data-ttu-id="c6a82-115">每个路由组在池中都有三个副本：一个主要副本和两个辅助副本。</span><span class="sxs-lookup"><span data-stu-id="c6a82-115">Each routing group has three replicas in the pool: one primary replica and two secondary replicas.</span></span>
    
- <span data-ttu-id="c6a82-116">池级仲裁丢失，导致没有足够的种子服务器都运行在池中。</span><span class="sxs-lookup"><span data-stu-id="c6a82-116">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span> 
    
### <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="c6a82-117">路由组级别仲裁丢失</span><span class="sxs-lookup"><span data-stu-id="c6a82-117">Routing Group Level quorum loss</span></span>

<span data-ttu-id="c6a82-p105">当您首次启动新的前端池时，务必确保有 85% 的服务器已启动且正在运行，如下表所示。如果正在运行的服务器数目较少，则服务可能会滞留在启动状态，而池可能无法启动。</span><span class="sxs-lookup"><span data-stu-id="c6a82-p105">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table. If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>
  
|<span data-ttu-id="c6a82-120">池中服务器的总数</span><span class="sxs-lookup"><span data-stu-id="c6a82-120">Total number of servers in the pool</span></span>  <br/> |<span data-ttu-id="c6a82-121">使池第一次启动所必须运行的服务器的数量</span><span class="sxs-lookup"><span data-stu-id="c6a82-121">Number of servers that must be running for the pool to be started the first time</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="c6a82-122">2</span><span class="sxs-lookup"><span data-stu-id="c6a82-122">2</span></span>  <br/> |<span data-ttu-id="c6a82-123">1</span><span class="sxs-lookup"><span data-stu-id="c6a82-123">1</span></span>  <br/> |
|<span data-ttu-id="c6a82-124">3</span><span class="sxs-lookup"><span data-stu-id="c6a82-124">3</span></span>  <br/> |<span data-ttu-id="c6a82-125">3</span><span class="sxs-lookup"><span data-stu-id="c6a82-125">3</span></span>  <br/> |
|<span data-ttu-id="c6a82-126">4</span><span class="sxs-lookup"><span data-stu-id="c6a82-126">4</span></span>  <br/> |<span data-ttu-id="c6a82-127">3</span><span class="sxs-lookup"><span data-stu-id="c6a82-127">3</span></span>  <br/> |
|<span data-ttu-id="c6a82-128">5</span><span class="sxs-lookup"><span data-stu-id="c6a82-128">5</span></span>  <br/> |<span data-ttu-id="c6a82-129">4</span><span class="sxs-lookup"><span data-stu-id="c6a82-129">4</span></span>  <br/> |
|<span data-ttu-id="c6a82-130">6</span><span class="sxs-lookup"><span data-stu-id="c6a82-130">6</span></span>  <br/> |<span data-ttu-id="c6a82-131">5</span><span class="sxs-lookup"><span data-stu-id="c6a82-131">5</span></span>  <br/> |
|<span data-ttu-id="c6a82-132">7</span><span class="sxs-lookup"><span data-stu-id="c6a82-132">7</span></span>  <br/> |<span data-ttu-id="c6a82-133">5</span><span class="sxs-lookup"><span data-stu-id="c6a82-133">5</span></span>  <br/> |
|<span data-ttu-id="c6a82-134">8</span><span class="sxs-lookup"><span data-stu-id="c6a82-134">8</span></span>  <br/> |<span data-ttu-id="c6a82-135">6</span><span class="sxs-lookup"><span data-stu-id="c6a82-135">6</span></span>  <br/> |
|<span data-ttu-id="c6a82-136">9</span><span class="sxs-lookup"><span data-stu-id="c6a82-136">9</span></span>  <br/> |<span data-ttu-id="c6a82-137">7</span><span class="sxs-lookup"><span data-stu-id="c6a82-137">7</span></span>  <br/> |
|<span data-ttu-id="c6a82-138">10</span><span class="sxs-lookup"><span data-stu-id="c6a82-138">10</span></span>  <br/> |<span data-ttu-id="c6a82-139">8</span><span class="sxs-lookup"><span data-stu-id="c6a82-139">8</span></span>  <br/> |
|<span data-ttu-id="c6a82-140">11</span><span class="sxs-lookup"><span data-stu-id="c6a82-140">11</span></span>  <br/> |<span data-ttu-id="c6a82-141">9</span><span class="sxs-lookup"><span data-stu-id="c6a82-141">9</span></span>  <br/> |
|<span data-ttu-id="c6a82-142">12</span><span class="sxs-lookup"><span data-stu-id="c6a82-142">12</span></span>  <br/> |<span data-ttu-id="c6a82-143">10</span><span class="sxs-lookup"><span data-stu-id="c6a82-143">10</span></span>  <br/> |
   
<span data-ttu-id="c6a82-144">以后每次启动池时，都应启动 85% 的服务器（如上表所示）。</span><span class="sxs-lookup"><span data-stu-id="c6a82-144">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="c6a82-145">如果不能启动此数目的服务器 （但足够的服务器可以启动，这样您就不在池级仲裁丢失），则可以使用`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery`cmdlet 以启用池从该路由组级仲裁丢失恢复并取得进展。</span><span class="sxs-lookup"><span data-stu-id="c6a82-145">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery` cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="c6a82-146">有关如何使用此 cmdlet 的详细信息，请参阅<link Reset-CsPoolRegistrarState>。</span><span class="sxs-lookup"><span data-stu-id="c6a82-146">For more information about how to use this cmdlet, see <link Reset-CsPoolRegistrarState>.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c6a82-147">在有偶数个服务器池，Skype 业务服务器使用作为见证主 SQL 数据库。</span><span class="sxs-lookup"><span data-stu-id="c6a82-147">In pools with an even number of servers, Skype for Business Server uses the Primary SQL database as Witness.</span></span> <span data-ttu-id="c6a82-148">在此池中，如果关闭主数据库并切换到镜像副本中，并且关闭足够的前端服务器，以便运行按照上表中，没有足够的整个池就会降低。</span><span class="sxs-lookup"><span data-stu-id="c6a82-148">In a pool like this, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="c6a82-149">有关详细信息，请参阅[数据库镜像见证](https://go.microsoft.com/fwlink/?LinkId=393672)。</span><span class="sxs-lookup"><span data-stu-id="c6a82-149">For more information, see [Database Mirroring Witness](https://go.microsoft.com/fwlink/?LinkId=393672).</span></span> 
  
#### <a name="pool-level-quorum-loss"></a><span data-ttu-id="c6a82-150">池级别仲裁丢失</span><span class="sxs-lookup"><span data-stu-id="c6a82-150">Pool-level quorum loss</span></span>

<span data-ttu-id="c6a82-151">函数在所有前端池，它不能在池级仲裁丢失。</span><span class="sxs-lookup"><span data-stu-id="c6a82-151">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="c6a82-152">如果正在运行的服务器数量低于下表所示的正常运作级别，则池中的其余服务器将停止所有 Skype for Business Server 服务。</span><span class="sxs-lookup"><span data-stu-id="c6a82-152">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Skype for Business Server services.</span></span> <span data-ttu-id="c6a82-153">注意下表中的数字假定在池中的后端服务器正在运行。</span><span class="sxs-lookup"><span data-stu-id="c6a82-153">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>
  
|<span data-ttu-id="c6a82-154">前端服务器的池中的总数</span><span class="sxs-lookup"><span data-stu-id="c6a82-154">Total number of Front End Servers in the pool</span></span>  <br/> |<span data-ttu-id="c6a82-155">使池发挥作用所必须运行的服务器的数量</span><span class="sxs-lookup"><span data-stu-id="c6a82-155">Number of servers that must be running for pool to be functional</span></span>  <br/> |
|:-----|:-----|
|<span data-ttu-id="c6a82-156">2</span><span class="sxs-lookup"><span data-stu-id="c6a82-156">2</span></span>  <br/> |<span data-ttu-id="c6a82-157">1</span><span class="sxs-lookup"><span data-stu-id="c6a82-157">1</span></span>  <br/> |
|<span data-ttu-id="c6a82-158">3-4</span><span class="sxs-lookup"><span data-stu-id="c6a82-158">3-4</span></span>  <br/> |<span data-ttu-id="c6a82-159">任意 2 台</span><span class="sxs-lookup"><span data-stu-id="c6a82-159">Any 2</span></span>  <br/> |
|<span data-ttu-id="c6a82-160">5-6</span><span class="sxs-lookup"><span data-stu-id="c6a82-160">5-6</span></span>  <br/> |<span data-ttu-id="c6a82-161">任意 3 台</span><span class="sxs-lookup"><span data-stu-id="c6a82-161">Any 3</span></span>  <br/> |
|<span data-ttu-id="c6a82-162">7</span><span class="sxs-lookup"><span data-stu-id="c6a82-162">7</span></span>  <br/> |<span data-ttu-id="c6a82-163">任意 4 台</span><span class="sxs-lookup"><span data-stu-id="c6a82-163">Any 4</span></span>  <br/> |
|<span data-ttu-id="c6a82-164">8-9</span><span class="sxs-lookup"><span data-stu-id="c6a82-164">8-9</span></span>  <br/> |<span data-ttu-id="c6a82-165">前 7 台服务器中的任意 4 台</span><span class="sxs-lookup"><span data-stu-id="c6a82-165">Any 4 of the first 7 servers</span></span>  <br/> |
|<span data-ttu-id="c6a82-166">10-12</span><span class="sxs-lookup"><span data-stu-id="c6a82-166">10-12</span></span>  <br/> |<span data-ttu-id="c6a82-167">前 9 台服务器中的任意 5 台</span><span class="sxs-lookup"><span data-stu-id="c6a82-167">Any 5 of the first 9 servers</span></span>  <br/> |
   
<span data-ttu-id="c6a82-168">在前面的表中，"第一个服务器"是其已提出第一次，按时间顺序，第一次启动时该池的服务器。</span><span class="sxs-lookup"><span data-stu-id="c6a82-168">In the preceding table, the "first servers" are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="c6a82-169">若要确定这些服务器，可以使用`Get-CsComputer`使用的 cmdlet` -PoolFqdn`选项。</span><span class="sxs-lookup"><span data-stu-id="c6a82-169">To determine these servers, you can use the  `Get-CsComputer` cmdlet with the ` -PoolFqdn` option.</span></span> <span data-ttu-id="c6a82-170">此 cmdlet 将按服务器在池中的出现顺序显示服务器，列表最上方的服务器就是前几台服务器。</span><span class="sxs-lookup"><span data-stu-id="c6a82-170">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>
  
#### <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="c6a82-171">确保池正常工作的其他步骤</span><span class="sxs-lookup"><span data-stu-id="c6a82-171">Additional steps to ensure pools are functional</span></span>

<span data-ttu-id="c6a82-172">您应注意其他几项因素，以确保您的前端池仍正常工作。</span><span class="sxs-lookup"><span data-stu-id="c6a82-172">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>
  
- <span data-ttu-id="c6a82-173">当您在第一次到池中移动用户时，请确保至少三个前端服务器正在运行。</span><span class="sxs-lookup"><span data-stu-id="c6a82-173">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>
    
- <span data-ttu-id="c6a82-174">如果您为灾难恢复的目的建立此池和另一池之间的一对关系，那么在建立此关系后，必须确保在某些时候此池具有三个同时运行的前端服务器以正确将数据与备份池同步。</span><span class="sxs-lookup"><span data-stu-id="c6a82-174">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="c6a82-175">池的配对和灾难恢复功能的详细信息，请参阅[规划高可用性和灾难恢复业务服务器 2015年的 Skype](high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="c6a82-175">For more information on pool pairing and disaster recovery features, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](high-availability-and-disaster-recovery.md).</span></span> 
    
## <a name="front-end-pool-with-two-front-end-servers"></a><span data-ttu-id="c6a82-176">带有两个前端服务器的前端池</span><span class="sxs-lookup"><span data-stu-id="c6a82-176">Front End pool with two Front End servers</span></span>

<span data-ttu-id="c6a82-177">我们不建议部署包含只有两个前端服务器的前端池。</span><span class="sxs-lookup"><span data-stu-id="c6a82-177">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="c6a82-178">这种小型池无法像更大的池一样提供强大的高可用性解决方案，同时还需要花费额外精力进行管理。</span><span class="sxs-lookup"><span data-stu-id="c6a82-178">This small pool will not provide a robust high-availability solution like a larger pool would, and needs extra care in managing.</span></span> <span data-ttu-id="c6a82-179">此外，如果两台服务器池的后端服务器发生故障，整个池本身很可能不久要向下也。</span><span class="sxs-lookup"><span data-stu-id="c6a82-179">Additionally, if the Back End Server of a two-server pool went down, the whole pool itself would likely soon go down as well.</span></span> <span data-ttu-id="c6a82-180">如果您要部署的业务服务器运行 Skype 的只是一个或两个服务器，我们建议将其部署为标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="c6a82-180">If you want to deploy just one or two servers running Skype for Business Server, we recommend you deploy them as Standard Edition servers.</span></span>
  
<span data-ttu-id="c6a82-181">如果您以往任何时候都需要部署两个前端服务器的池中，请遵循以下准则：</span><span class="sxs-lookup"><span data-stu-id="c6a82-181">If you do ever need to deploy a pool with two Front End Servers, follow these guidelines:</span></span>
  
- <span data-ttu-id="c6a82-182">如果一个两个前端服务器出现故障时，您应尝试备份将发生故障的服务器，就可以。</span><span class="sxs-lookup"><span data-stu-id="c6a82-182">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="c6a82-183">同样，如果需要升级两台服务器之一，升级完成后将其尽快联机。</span><span class="sxs-lookup"><span data-stu-id="c6a82-183">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>
    
- <span data-ttu-id="c6a82-184">如果因某些原因需要将两台服务器同时停机，当该池停机后执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="c6a82-184">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
  - <span data-ttu-id="c6a82-185">最好的做法是同时重新启动两个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="c6a82-185">The best practice is to restart both Front End Servers at the same time.</span></span> 
    
  - <span data-ttu-id="c6a82-186">如果无法同时重新启动两台服务器，则应该按其停机时的相反顺序来启动它们。</span><span class="sxs-lookup"><span data-stu-id="c6a82-186">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
  - <span data-ttu-id="c6a82-187">如果您不能备份使它们按顺序，然后使用以下 cmdlet 之前将备份的池：`Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span><span class="sxs-lookup"><span data-stu-id="c6a82-187">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:  `Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>`</span></span>
    
## <a name="front-end-pool-configuration-failures-and-changes"></a><span data-ttu-id="c6a82-188">前端池配置失败和更改</span><span class="sxs-lookup"><span data-stu-id="c6a82-188">Front End pool configuration failures and changes</span></span>

<span data-ttu-id="c6a82-p113">如果前端服务器失败，且在近期不可能替换，则从拓扑删除该服务器。当再次可用时向该拓扑添加新的前端服务器。</span><span class="sxs-lookup"><span data-stu-id="c6a82-p113">If a Front End server fails and is unlikely to be replaced for a few days or more, remove the server from the topology. Add the new Front End server to the topology when it is available again.</span></span>
  
<span data-ttu-id="c6a82-191">在您对前端池作出配置更改时（比如添加或删除服务器），您必须遵守以下准则：</span><span class="sxs-lookup"><span data-stu-id="c6a82-191">Whenever you make a configuration change to a Front End pool, such as adding or removing servers, you must follow these guidelines:</span></span>
  
- <span data-ttu-id="c6a82-p114">发布新拓扑后，必须在池中重新启动每个前端池。一次重新启动一个。</span><span class="sxs-lookup"><span data-stu-id="c6a82-p114">After the new topology has been published, you must restart each Front End server in the pool. Restart them one at a time.</span></span>
    
- <span data-ttu-id="c6a82-194">如果在更改配置过程中，整个池已关闭，然后运行以下 cmdlet 后发布新的拓扑：`Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span><span class="sxs-lookup"><span data-stu-id="c6a82-194">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:  `Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset`</span></span>
    

