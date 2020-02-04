---
title: Lync Server 2013：适用于前端服务器、即时消息和状态的拓扑和组件
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for Front End Servers, instant messaging, and presence
ms:assetid: f08ce7a1-d14e-4a54-9771-a82c870658bf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412996(v=OCS.15)
ms:contentKeyID: 48185763
ms.date: 10/24/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 181ae682ec5ee1352c5d4f4280b4164fbbcd91f2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="2a2fb-102">Lync Server 2013 中适用于前端服务器、即时消息和状态的拓扑和组件</span><span class="sxs-lookup"><span data-stu-id="2a2fb-102">Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2a2fb-103">_**主题上次修改时间：** 2014-10-24_</span><span class="sxs-lookup"><span data-stu-id="2a2fb-103">_**Topic Last Modified:** 2014-10-24_</span></span>

<span data-ttu-id="2a2fb-104">即时消息 (IM) 和状态所需的唯一组件是：</span><span class="sxs-lookup"><span data-stu-id="2a2fb-104">The only components required for instant messaging (IM) and presence are:</span></span>

  - <span data-ttu-id="2a2fb-105">您的组织的前端服务器或标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-105">Your organization’s Front End Servers or Standard Edition servers.</span></span> <span data-ttu-id="2a2fb-106">将始终在这些服务器上启用 IM 和状态功能。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-106">IM and presence capabilities are always enabled on these servers.</span></span>

  - <span data-ttu-id="2a2fb-107">负载平衡器（如果您拥有 Enterprise Edition 前端池）。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-107">A load balancer, if you have an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="2a2fb-108">有关详细信息，请参阅[Lync Server 2013 的负载平衡要求](lync-server-2013-load-balancing-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-108">For more information, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a><span data-ttu-id="2a2fb-109">规划前端池的部署</span><span class="sxs-lookup"><span data-stu-id="2a2fb-109">Planning for the Deployment of Front End Pools</span></span>

<span data-ttu-id="2a2fb-110">在 Lync Server 2013 中，前端池体系结构已更改，这些更改将影响你应如何计划和维护你的前端池。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-110">In Lync Server 2013, Front End pool architecture has changed, and these changes affect how you should plan and maintain your Front End pools.</span></span>

<span data-ttu-id="2a2fb-111">我们建议你的所有企业版前端池至少包括三个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-111">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> <span data-ttu-id="2a2fb-112">在 Lync Server 中，前端池的体系结构使用分布式系统模型，每个用户的数据都保存在池中的三个前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-112">In Lync Server, the architecture of Front End pools uses a distributed systems model, with each user’s data kept on three Front End servers in the pool.</span></span> <span data-ttu-id="2a2fb-113">有关此新体系结构的详细信息，请参阅[Lync Server 2013 中的拓扑更改](lync-server-2013-topology-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-113">For more information about this new architecture, see [Topology changes in Lync Server 2013](lync-server-2013-topology-changes.md).</span></span>

<span data-ttu-id="2a2fb-114">如果你不想部署三个企业版前端服务器并需要灾难恢复，我们建议你使用 Lync Server 标准版并创建具有配对备份关系的两个池。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-114">If you do not want to deploy three Enterprise Edition Front End Servers and want disaster recovery, we recommend you use Lync Server Standard Edition and create two pools with a paired backup relationship.</span></span> <span data-ttu-id="2a2fb-115">这将提供仅包含两台服务器的灾难恢复解决方案。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-115">This will provide a disaster recovery solution with only two servers.</span></span> <span data-ttu-id="2a2fb-116">有关详细信息，请参阅高可用性和灾难恢复拓扑和功能，请参阅[在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-116">For more information, on high availability and disaster recovery topologies and features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="2a2fb-117">规划前端池的管理</span><span class="sxs-lookup"><span data-stu-id="2a2fb-117">Planning for the Management of Front End Pools</span></span>

<span data-ttu-id="2a2fb-118">对于前端池，请按照本部分中的指南操作。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-118">For Front End pools, follow the guidelines in this section.</span></span>

<div>

## <a name="ensuring-that-pools-are-functional"></a><span data-ttu-id="2a2fb-119">确保池正常运行</span><span class="sxs-lookup"><span data-stu-id="2a2fb-119">Ensuring That Pools are Functional</span></span>

<span data-ttu-id="2a2fb-120">对于前端池的新分布式模型，必须运行一些池服务器的特定号码才能使池正常工作。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-120">With the new distributed model for Front End pools, certain numbers of a pool’s servers must be running for the pool to function.</span></span> <span data-ttu-id="2a2fb-121">池有两种丢失模式</span><span class="sxs-lookup"><span data-stu-id="2a2fb-121">There are two loss modes for a pool</span></span>

  - <span data-ttu-id="2a2fb-122">路由组级别仲裁丢失，是由于特定路由组的副本服务器不足引起的。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-122">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="2a2fb-123">路由组是驻留在池中的一组用户的聚合。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-123">A routing group is an aggregation of a set of users homed in the pool.</span></span> <span data-ttu-id="2a2fb-124">每个路由组在池中有三个副本：一个主副本和两个辅助副本。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-124">Each routing group has three replicas in the pool: one primary and two secondaries.</span></span>

  - <span data-ttu-id="2a2fb-125">池级别仲裁丢失，当池中运行的种子服务器不足时导致的。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-125">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span>

<div>

## <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="2a2fb-126">路由组级别仲裁丢失</span><span class="sxs-lookup"><span data-stu-id="2a2fb-126">Routing Group Level quorum loss</span></span>

<span data-ttu-id="2a2fb-p107">当您首次启动新的前端池时，务必确保有 85% 的服务器已启动且正在运行，如下表所示。如果正在运行的服务器数目较少，则服务可能会滞留在启动状态，而池可能无法启动。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-p107">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table. If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a2fb-129">池中服务器的总数</span><span class="sxs-lookup"><span data-stu-id="2a2fb-129">Total number of servers in the pool</span></span></th>
<th><span data-ttu-id="2a2fb-130">使池第一次启动所必须运行的服务器的数量</span><span class="sxs-lookup"><span data-stu-id="2a2fb-130">Number of servers that must be running for the pool to be started the first time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a2fb-131">ppls-2</span><span class="sxs-lookup"><span data-stu-id="2a2fb-131">2</span></span></p></td>
<td><p><span data-ttu-id="2a2fb-132">1</span><span class="sxs-lookup"><span data-stu-id="2a2fb-132">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a2fb-133">3</span><span class="sxs-lookup"><span data-stu-id="2a2fb-133">3</span></span></p></td>
<td><p><span data-ttu-id="2a2fb-134">3</span><span class="sxs-lookup"><span data-stu-id="2a2fb-134">3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a2fb-135">4</span><span class="sxs-lookup"><span data-stu-id="2a2fb-135">4</span></span></p></td>
<td><p><span data-ttu-id="2a2fb-136">3</span><span class="sxs-lookup"><span data-stu-id="2a2fb-136">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a2fb-137">5</span><span class="sxs-lookup"><span data-stu-id="2a2fb-137">5</span></span></p></td>
<td><p><span data-ttu-id="2a2fb-138">4</span><span class="sxs-lookup"><span data-stu-id="2a2fb-138">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a2fb-139">6</span><span class="sxs-lookup"><span data-stu-id="2a2fb-139">6</span></span></p></td>
<td><p><span data-ttu-id="2a2fb-140">5</span><span class="sxs-lookup"><span data-stu-id="2a2fb-140">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a2fb-141">7</span><span class="sxs-lookup"><span data-stu-id="2a2fb-141">7</span></span></p></td>
<td><p><span data-ttu-id="2a2fb-142">5</span><span class="sxs-lookup"><span data-stu-id="2a2fb-142">5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a2fb-143">个</span><span class="sxs-lookup"><span data-stu-id="2a2fb-143">8</span></span></p></td>
<td><p><span data-ttu-id="2a2fb-144">6</span><span class="sxs-lookup"><span data-stu-id="2a2fb-144">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a2fb-145">db-9</span><span class="sxs-lookup"><span data-stu-id="2a2fb-145">9</span></span></p></td>
<td><p><span data-ttu-id="2a2fb-146">7</span><span class="sxs-lookup"><span data-stu-id="2a2fb-146">7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a2fb-147">10</span><span class="sxs-lookup"><span data-stu-id="2a2fb-147">10</span></span></p></td>
<td><p><span data-ttu-id="2a2fb-148">个</span><span class="sxs-lookup"><span data-stu-id="2a2fb-148">8</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a2fb-149">11</span><span class="sxs-lookup"><span data-stu-id="2a2fb-149">11</span></span></p></td>
<td><p><span data-ttu-id="2a2fb-150">db-9</span><span class="sxs-lookup"><span data-stu-id="2a2fb-150">9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a2fb-151">至</span><span class="sxs-lookup"><span data-stu-id="2a2fb-151">12</span></span></p></td>
<td><p><span data-ttu-id="2a2fb-152">10</span><span class="sxs-lookup"><span data-stu-id="2a2fb-152">10</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2a2fb-153">以后每次启动池时，都应启动 85% 的服务器（如上表所示）。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-153">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="2a2fb-154">如果无法启动此数量的服务器（但是可以启动足够数量的服务器来避免遭遇池级别仲裁丢失），那么您可以使用 **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery**  cmdlet 来使池从此路由组级别仲裁丢失中恢复，然后继续操作。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-154">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="2a2fb-155">有关如何使用此 cmdlet 的详细信息，请参阅[Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState)。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-155">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2a2fb-156">由于 Lync Server 使用主 SQL 数据库作为见证，因此如果关闭主数据库并切换到镜像副本，并关闭足够的前端服务器，以便根据前面的表运行时，整个池将停止运行。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-156">Because Lync Server uses the Primary SQL database as Witness, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End Servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="2a2fb-157">有关详细信息，请参阅<A href="http://go.microsoft.com/fwlink/?linkid=393672">数据库镜像见证</A>。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-157">For more information, see <A href="http://go.microsoft.com/fwlink/?linkid=393672">Database Mirroring Witness</A>.</span></span>



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a><span data-ttu-id="2a2fb-158">池级别仲裁丢失</span><span class="sxs-lookup"><span data-stu-id="2a2fb-158">Pool-level quorum loss</span></span>

<span data-ttu-id="2a2fb-159">要使前端池完全正常工作，它不能处于池级别仲裁损失。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-159">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="2a2fb-160">如果运行的服务器数低于功能级别，如下表所示，则池中剩余的服务器将停止所有 Lync Server 服务。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-160">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Lync Server services.</span></span> <span data-ttu-id="2a2fb-161">请注意，下表中的数字假定池中的后端服务器正在运行。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-161">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2a2fb-162">池中的前端服务器总数</span><span class="sxs-lookup"><span data-stu-id="2a2fb-162">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="2a2fb-163">使池发挥作用所必须运行的服务器的数量</span><span class="sxs-lookup"><span data-stu-id="2a2fb-163">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2a2fb-164">ppls-2</span><span class="sxs-lookup"><span data-stu-id="2a2fb-164">2</span></span></p></td>
<td><p><span data-ttu-id="2a2fb-165">1</span><span class="sxs-lookup"><span data-stu-id="2a2fb-165">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a2fb-166">3-4</span><span class="sxs-lookup"><span data-stu-id="2a2fb-166">3-4</span></span></p></td>
<td><p><span data-ttu-id="2a2fb-167">任意 2 台</span><span class="sxs-lookup"><span data-stu-id="2a2fb-167">Any 2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a2fb-168">5-6</span><span class="sxs-lookup"><span data-stu-id="2a2fb-168">5-6</span></span></p></td>
<td><p><span data-ttu-id="2a2fb-169">任意 3 台</span><span class="sxs-lookup"><span data-stu-id="2a2fb-169">Any 3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a2fb-170">7</span><span class="sxs-lookup"><span data-stu-id="2a2fb-170">7</span></span></p></td>
<td><p><span data-ttu-id="2a2fb-171">任意 4 台</span><span class="sxs-lookup"><span data-stu-id="2a2fb-171">Any 4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2a2fb-172">8-9</span><span class="sxs-lookup"><span data-stu-id="2a2fb-172">8-9</span></span></p></td>
<td><p><span data-ttu-id="2a2fb-173">前 7 台服务器中的任意 4 台</span><span class="sxs-lookup"><span data-stu-id="2a2fb-173">Any 4 of the first 7 servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2a2fb-174">10-12</span><span class="sxs-lookup"><span data-stu-id="2a2fb-174">10-12</span></span></p></td>
<td><p><span data-ttu-id="2a2fb-175">前 9 台服务器中的任意 5 台</span><span class="sxs-lookup"><span data-stu-id="2a2fb-175">Any 5 of the first 9 servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="2a2fb-176">在上表中，“前几台服务器”是指自首次启动池起按时间顺序靠前显示的服务器。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-176">In the preceding table, the “first servers” are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="2a2fb-177">若要确定这些服务器，你可以将**CsComputer** cmdlet 与 **-PoolFqdn**选项结合使用。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-177">To determine these servers, you can use the **Get-CsComputer** cmdlet with the **–PoolFqdn** option.</span></span> <span data-ttu-id="2a2fb-178">此 cmdlet 将按服务器在池中的出现顺序显示服务器，列表最上方的服务器就是前几台服务器。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-178">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a><span data-ttu-id="2a2fb-179">具有两个前端服务器的前端池</span><span class="sxs-lookup"><span data-stu-id="2a2fb-179">Front End Pools with Two Front End Servers</span></span>

<span data-ttu-id="2a2fb-180">我们不建议部署仅包含两个前端服务器的前端池。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-180">We do not recommend deploying a Front End pool that contains only two Front End Servers.</span></span> <span data-ttu-id="2a2fb-181">如果您确实需要部署此类池，请遵循以下指南：</span><span class="sxs-lookup"><span data-stu-id="2a2fb-181">If you do ever need to deploy such a pool, follow these guidelines:</span></span>

  - <span data-ttu-id="2a2fb-182">如果这两个前端服务器之一出现故障，您应尽可能快地尝试让故障服务器恢复正常状态。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-182">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can.</span></span> <span data-ttu-id="2a2fb-183">同样，如果需要升级两台服务器之一，升级完成后将其尽快联机。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-183">Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>

  - <span data-ttu-id="2a2fb-184">如果因某些原因需要将两台服务器同时停机，当该池停机后执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="2a2fb-184">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
      - <span data-ttu-id="2a2fb-185">最佳做法是同时重新启动这两个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-185">The best practice is to restart both Front End Servers at the same time.</span></span>
    
      - <span data-ttu-id="2a2fb-186">如果无法同时重新启动两台服务器，则应该按其停机时的相反顺序来启动它们。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-186">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
      - <span data-ttu-id="2a2fb-187">如果不能按该顺序恢复它们，请在重新启动池之前使用以下 cmdlet：。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-187">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:.</span></span>
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="2a2fb-188">确保池正常运行的其他步骤</span><span class="sxs-lookup"><span data-stu-id="2a2fb-188">Additional Steps to Ensure Pools are Functional</span></span>

<span data-ttu-id="2a2fb-189">您应注意其他几项因素，以确保您的前端池仍正常工作。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-189">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>

  - <span data-ttu-id="2a2fb-190">首次将用户移动到池时，请确保至少有三个前端服务器正在运行。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-190">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>

  - <span data-ttu-id="2a2fb-191">如果您在此池和另一个池之间建立了一个配对关系以用于灾难恢复，那么在建立该关系之后，必须确保此池在一定时间同时运行三台前端服务器才能正确同步带有备份池的数据。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-191">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End Servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="2a2fb-192">有关池配对和灾难恢复功能的详细信息，请参阅[在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-192">For more information on pool pairing and disaster recovery features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a><span data-ttu-id="2a2fb-193">提高池升级的可靠性</span><span class="sxs-lookup"><span data-stu-id="2a2fb-193">Improving the Reliability of Pool Upgrades</span></span>

<span data-ttu-id="2a2fb-194">当你需要升级或修补前端池中的服务器时，请按照[升级或更新 Lync Server 2013 中的前端服务器](lync-server-2013-upgrade-or-update-front-end-servers.md)中所示的工作流和以下指南操作：</span><span class="sxs-lookup"><span data-stu-id="2a2fb-194">When you need to upgrade or patch the servers in a Front End pool, follow the workflow shown in [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), and the following guidelines:</span></span>

  - <span data-ttu-id="2a2fb-195">从一个升级域移动到另一个升级域进行升级时（在[升级或更新 Lync Server 2013 中的前端服务器](lync-server-2013-upgrade-or-update-front-end-servers.md)时），你将使用**CsPoolUpgradeReadinessState** Cmdlet 并检查 "准备就绪状态"。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-195">When you move from one upgrade domain to another for upgrades (following the workflow at [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), you will use the **Get-CsPoolUpgradeReadinessState** cmdlet and check for Ready state.</span></span> <span data-ttu-id="2a2fb-196">在每个升级域达到 "就绪" 后，每个升级域之间添加20分钟的等待时间将使升级更加可靠。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-196">Adding a 20-minute wait between each upgrade domain after it reaches “Ready” will make the upgrades more reliable.</span></span> <span data-ttu-id="2a2fb-197">如果在此20分钟内**未准备就绪**，请重新启动20分钟计时器。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-197">If it becomes **Not Ready** during this 20 minutes, restart the 20-minute timer.</span></span> <span data-ttu-id="2a2fb-198">此外，你还可以在启动20分钟间隔之前和之后运行**CsPoolFabricState** cmdlet，确保不会对路由组的 primaries 和辅助映像进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-198">Also, you can run the **Get-CsPoolFabricState** cmdlet before and after starting the 20-minute interval and make sure there are no changes to the primaries and secondaries of routing groups.</span></span>

  - <span data-ttu-id="2a2fb-199">如果上次修补的升级域中的任何服务器堵塞或未重新启动，请不要转到下一个升级域。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-199">Do not move on to the next upgrade domain if any of the servers in the last patched upgrade domain are stuck or not restarted.</span></span> <span data-ttu-id="2a2fb-200">这也适用于升级中的任何服务器无法启动的情况。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-200">This also applies if any of the servers within an upgrade cannot start.</span></span> <span data-ttu-id="2a2fb-201">运行**CsPoolFabricState**以确保所有路由组都有一个主要和至少一个辅助数据库;这将确认所有用户是否都拥有服务。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-201">Run **Get-CsPoolFabricState** to make sure all of the routing groups have a primary and at least one secondary; this will confirm whether all users have service.</span></span>

  - <span data-ttu-id="2a2fb-202">如果某些用户拥有服务，而其他用户没有服务，请运行**CsPoolFabricState** ，使用-Verbose 选项检查缺少副本的路由组。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-202">If some users have service and others do not, run **Get-CsPoolFabricState** with the –Verbose option to check for routing groups that have missing replicas.</span></span> <span data-ttu-id="2a2fb-203">不要作为第一步疑难解答步骤重启整个池。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-203">Do not restart the entire pool as the first troubleshooting step.</span></span> <span data-ttu-id="2a2fb-204">有关此 cmdlet 的详细信息，请参阅[CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState)。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-204">For more information on this cmdlet, see [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span></span>

  - <span data-ttu-id="2a2fb-205">确保已关闭 "事件查看器" 或 "性能监视器" 窗口的所有实例，以便 windows fabric 安装/卸载。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-205">Make sure that all instances of the Event Viewer or Performance Monitor windows are closed for windows fabric installs/uninstalls.</span></span>

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a><span data-ttu-id="2a2fb-206">更改前端池的配置</span><span class="sxs-lookup"><span data-stu-id="2a2fb-206">Changing a Front End Pool’s Configuration</span></span>

<span data-ttu-id="2a2fb-207">每当你将前端服务器添加到池，或者从池中删除它们，然后发布新拓扑时，请遵循以下指南：</span><span class="sxs-lookup"><span data-stu-id="2a2fb-207">Whenever you add Front End Servers to a pool, or remove them from the pool, and then publish the new topology, follow these guidelines:</span></span>

  - <span data-ttu-id="2a2fb-208">发布新拓扑后，必须重新启动池中的每个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-208">After the new topology has been published, you must restart each Front End Server in the pool.</span></span> <span data-ttu-id="2a2fb-209">一次重新启动一个。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-209">Restart them one at a time.</span></span>

  - <span data-ttu-id="2a2fb-210">如果在配置更改期间整个池已停机，则在发布新拓扑后运行以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="2a2fb-210">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:</span></span>
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

<span data-ttu-id="2a2fb-211">如果前端服务器出现故障且不太可能被替换几天或更长时间，请从拓扑结构中删除服务器。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-211">If a Front End Server fails and is unlikely to be replaced for a few days or more, remove the server from the topology.</span></span> <span data-ttu-id="2a2fb-212">将新的前端服务器添加到拓扑中（当它再次可用时）。</span><span class="sxs-lookup"><span data-stu-id="2a2fb-212">Add the new Front End Server to the topology when it is available again.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

