---
title: Lync Server 2013：前端服务器、即时消息和状态的拓扑和组件
description: Lync Server 2013：前端服务器、即时消息和状态的拓扑和组件。
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
ms.openlocfilehash: 474911ef0e60d57151aa778688cf2e6a8e1bfcf7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550288"
---
# <a name="topologies-and-components-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="eccdf-103">Lync Server 2013 中的前端服务器、即时消息和状态的拓扑和组件</span><span class="sxs-lookup"><span data-stu-id="eccdf-103">Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="eccdf-104">_**上次修改的主题：** 2014-10-24_</span><span class="sxs-lookup"><span data-stu-id="eccdf-104">_**Topic Last Modified:** 2014-10-24_</span></span>

<span data-ttu-id="eccdf-105">即时消息 (IM) 和状态所需的唯一组件是：</span><span class="sxs-lookup"><span data-stu-id="eccdf-105">The only components required for instant messaging (IM) and presence are:</span></span>

  - <span data-ttu-id="eccdf-p101">组织的前端服务器或 Standard Edition Server。这些服务器中始终启用 IM 和状态功能。</span><span class="sxs-lookup"><span data-stu-id="eccdf-p101">Your organization’s Front End Servers or Standard Edition servers. IM and presence capabilities are always enabled on these servers.</span></span>

  - <span data-ttu-id="eccdf-108">负载平衡器（如果有一个 Enterprise Edition 前端池）。</span><span class="sxs-lookup"><span data-stu-id="eccdf-108">A load balancer, if you have an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="eccdf-109">有关详细信息，请参阅 [Lync Server 2013 的负载平衡要求](lync-server-2013-load-balancing-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="eccdf-109">For more information, see [Load balancing requirements for Lync Server 2013](lync-server-2013-load-balancing-requirements.md).</span></span>

<div>

## <a name="planning-for-the-deployment-of-front-end-pools"></a><span data-ttu-id="eccdf-110">规划部署前端池</span><span class="sxs-lookup"><span data-stu-id="eccdf-110">Planning for the Deployment of Front End Pools</span></span>

<span data-ttu-id="eccdf-111">在 Lync Server 2013 中，前端池体系结构已更改，这些更改将影响您应如何规划和维护前端池。</span><span class="sxs-lookup"><span data-stu-id="eccdf-111">In Lync Server 2013, Front End pool architecture has changed, and these changes affect how you should plan and maintain your Front End pools.</span></span>

<span data-ttu-id="eccdf-112">我们建议您的所有 Enterprise Edition 前端池至少包含三台前端服务器。</span><span class="sxs-lookup"><span data-stu-id="eccdf-112">We recommend that all your Enterprise Edition Front End pools include at least three Front End Servers.</span></span> <span data-ttu-id="eccdf-113">在 Lync Server 中，前端池的体系结构使用分布式系统模型，每个用户的数据都保存在池中的三台前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="eccdf-113">In Lync Server, the architecture of Front End pools uses a distributed systems model, with each user’s data kept on three Front End servers in the pool.</span></span> <span data-ttu-id="eccdf-114">有关此新体系结构的详细信息，请参阅 [Lync Server 2013 中的拓扑更改](lync-server-2013-topology-changes.md)。</span><span class="sxs-lookup"><span data-stu-id="eccdf-114">For more information about this new architecture, see [Topology changes in Lync Server 2013](lync-server-2013-topology-changes.md).</span></span>

<span data-ttu-id="eccdf-115">如果您不想部署三个 Enterprise Edition 前端服务器并希望进行灾难恢复，我们建议使用 Lync Server Standard Edition 并创建具有配对备份关系的两个池。</span><span class="sxs-lookup"><span data-stu-id="eccdf-115">If you do not want to deploy three Enterprise Edition Front End Servers and want disaster recovery, we recommend you use Lync Server Standard Edition and create two pools with a paired backup relationship.</span></span> <span data-ttu-id="eccdf-116">这将提供仅包含两台服务器的灾难恢复解决方案。</span><span class="sxs-lookup"><span data-stu-id="eccdf-116">This will provide a disaster recovery solution with only two servers.</span></span> <span data-ttu-id="eccdf-117">有关详细信息，请参阅高可用性和灾难恢复拓扑和功能，请参阅在 [Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="eccdf-117">For more information, on high availability and disaster recovery topologies and features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

<div>

## <a name="planning-for-the-management-of-front-end-pools"></a><span data-ttu-id="eccdf-118">规划管理前端池</span><span class="sxs-lookup"><span data-stu-id="eccdf-118">Planning for the Management of Front End Pools</span></span>

<span data-ttu-id="eccdf-119">对于前端池，请遵循本节中的指南。</span><span class="sxs-lookup"><span data-stu-id="eccdf-119">For Front End pools, follow the guidelines in this section.</span></span>

<div>

## <a name="ensuring-that-pools-are-functional"></a><span data-ttu-id="eccdf-120">确保池正常运行</span><span class="sxs-lookup"><span data-stu-id="eccdf-120">Ensuring That Pools are Functional</span></span>

<span data-ttu-id="eccdf-121">使用新的分布式模型进行前端池时，池服务器的某些号码必须运行，池才能正常工作。</span><span class="sxs-lookup"><span data-stu-id="eccdf-121">With the new distributed model for Front End pools, certain numbers of a pool’s servers must be running for the pool to function.</span></span> <span data-ttu-id="eccdf-122">池有两个丢失模式</span><span class="sxs-lookup"><span data-stu-id="eccdf-122">There are two loss modes for a pool</span></span>

  - <span data-ttu-id="eccdf-123">路由组级别仲裁丢失，因特定路由组的副本服务器不足而导致。</span><span class="sxs-lookup"><span data-stu-id="eccdf-123">Routing Group Level quorum loss, caused by not enough replica servers for a particular routing group.</span></span> <span data-ttu-id="eccdf-124">路由组是驻留在池中的一组用户的聚合。</span><span class="sxs-lookup"><span data-stu-id="eccdf-124">A routing group is an aggregation of a set of users homed in the pool.</span></span> <span data-ttu-id="eccdf-125">每个路由组在池中都有三个副本：一个主副本和两个辅助副本。</span><span class="sxs-lookup"><span data-stu-id="eccdf-125">Each routing group has three replicas in the pool: one primary and two secondaries.</span></span>

  - <span data-ttu-id="eccdf-126">池级别仲裁丢失，在池中没有足够的种子服务器运行时导致。</span><span class="sxs-lookup"><span data-stu-id="eccdf-126">Pool Level quorum loss, caused when not enough seed servers are running in the pool.</span></span>

<div>

## <a name="routing-group-level-quorum-loss"></a><span data-ttu-id="eccdf-127">路由组级别仲裁丢失</span><span class="sxs-lookup"><span data-stu-id="eccdf-127">Routing Group Level quorum loss</span></span>

<span data-ttu-id="eccdf-128">首次启动新的前端池时，有85% 的服务器已启动并且正在运行，这一点非常重要，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="eccdf-128">The first time you start a new Front End pool, it is essential that 85% of the servers are up and running, as shown in the following table.</span></span> <span data-ttu-id="eccdf-129">如果运行较少的服务器，服务可能会处于 "启动" 状态，并且池可能无法启动。</span><span class="sxs-lookup"><span data-stu-id="eccdf-129">If fewer servers are running, the services might be stuck in the starting state and the pool might not start.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eccdf-130">池中的服务器总数</span><span class="sxs-lookup"><span data-stu-id="eccdf-130">Total number of servers in the pool</span></span></th>
<th><span data-ttu-id="eccdf-131">在首次启动池时必须运行的服务器的数量</span><span class="sxs-lookup"><span data-stu-id="eccdf-131">Number of servers that must be running for the pool to be started the first time</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eccdf-132">双面</span><span class="sxs-lookup"><span data-stu-id="eccdf-132">2</span></span></p></td>
<td><p><span data-ttu-id="eccdf-133">1</span><span class="sxs-lookup"><span data-stu-id="eccdf-133">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eccdf-134">第三章</span><span class="sxs-lookup"><span data-stu-id="eccdf-134">3</span></span></p></td>
<td><p><span data-ttu-id="eccdf-135">第三章</span><span class="sxs-lookup"><span data-stu-id="eccdf-135">3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eccdf-136">4 </span><span class="sxs-lookup"><span data-stu-id="eccdf-136">4</span></span></p></td>
<td><p><span data-ttu-id="eccdf-137">第三章</span><span class="sxs-lookup"><span data-stu-id="eccdf-137">3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eccdf-138">5 </span><span class="sxs-lookup"><span data-stu-id="eccdf-138">5</span></span></p></td>
<td><p><span data-ttu-id="eccdf-139">4 </span><span class="sxs-lookup"><span data-stu-id="eccdf-139">4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eccdf-140">6 </span><span class="sxs-lookup"><span data-stu-id="eccdf-140">6</span></span></p></td>
<td><p><span data-ttu-id="eccdf-141">5 </span><span class="sxs-lookup"><span data-stu-id="eccdf-141">5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eccdf-142">7 </span><span class="sxs-lookup"><span data-stu-id="eccdf-142">7</span></span></p></td>
<td><p><span data-ttu-id="eccdf-143">5 </span><span class="sxs-lookup"><span data-stu-id="eccdf-143">5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eccdf-144">8 </span><span class="sxs-lookup"><span data-stu-id="eccdf-144">8</span></span></p></td>
<td><p><span data-ttu-id="eccdf-145">6 </span><span class="sxs-lookup"><span data-stu-id="eccdf-145">6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eccdf-146">9 </span><span class="sxs-lookup"><span data-stu-id="eccdf-146">9</span></span></p></td>
<td><p><span data-ttu-id="eccdf-147">7 </span><span class="sxs-lookup"><span data-stu-id="eccdf-147">7</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eccdf-148">10  </span><span class="sxs-lookup"><span data-stu-id="eccdf-148">10</span></span></p></td>
<td><p><span data-ttu-id="eccdf-149">8 </span><span class="sxs-lookup"><span data-stu-id="eccdf-149">8</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eccdf-150">11x17</span><span class="sxs-lookup"><span data-stu-id="eccdf-150">11</span></span></p></td>
<td><p><span data-ttu-id="eccdf-151">9 </span><span class="sxs-lookup"><span data-stu-id="eccdf-151">9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eccdf-152">12 </span><span class="sxs-lookup"><span data-stu-id="eccdf-152">12</span></span></p></td>
<td><p><span data-ttu-id="eccdf-153">10  </span><span class="sxs-lookup"><span data-stu-id="eccdf-153">10</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="eccdf-154">每次启动池时，应启动85% 的服务器 (，如上表中所示) 。</span><span class="sxs-lookup"><span data-stu-id="eccdf-154">Every subsequent time the pool is started, 85% of the servers should be started (as shown in the preceding table).</span></span> <span data-ttu-id="eccdf-155">如果无法启动此数量的服务器 (但可以启动足够的服务器以使您不会处于池级别的仲裁丢失) ，则可以使用 **ResetType QuorumLossRecovery** cmdlet 使池能够从此路由组级别仲裁丢失恢复并进行操作。</span><span class="sxs-lookup"><span data-stu-id="eccdf-155">If this number of servers cannot be started (but enough servers can be started so that you are not at pool-level quorum loss), you can use the **Reset-CsPoolRegistrarState –ResetType QuorumLossRecovery** cmdlet to enable the pool to recover from this routing group level quorum loss and make progress.</span></span> <span data-ttu-id="eccdf-156">有关如何使用此 cmdlet 的详细信息，请参阅 [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState)。</span><span class="sxs-lookup"><span data-stu-id="eccdf-156">For more information about how to use this cmdlet, see [Reset-CsPoolRegistrarState](https://docs.microsoft.com/powershell/module/skype/Reset-CsPoolRegistrarState).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="eccdf-157">由于 Lync Server 使用主 SQL 数据库作为见证，如果关闭主数据库并切换到镜像副本，并且关闭了足够的前端服务器，以便根据前面的表运行，则整个池将会停止运行。</span><span class="sxs-lookup"><span data-stu-id="eccdf-157">Because Lync Server uses the Primary SQL database as Witness, if you shut down the primary database and switch to the Mirror copy, and shut down enough Front End Servers so that not enough are running according to the preceding table, the entire pool will go down.</span></span> <span data-ttu-id="eccdf-158">有关详细信息，请参阅 <A href="https://go.microsoft.com/fwlink/?linkid=393672">数据库镜像见证</A>。</span><span class="sxs-lookup"><span data-stu-id="eccdf-158">For more information, see <A href="https://go.microsoft.com/fwlink/?linkid=393672">Database Mirroring Witness</A>.</span></span>



</div>

</div>

<div>

## <a name="pool-level-quorum-loss"></a><span data-ttu-id="eccdf-159">池级别仲裁丢失</span><span class="sxs-lookup"><span data-stu-id="eccdf-159">Pool-level quorum loss</span></span>

<span data-ttu-id="eccdf-160">为了让前端池能够正常运行，它不能处于池级别仲裁丢失。</span><span class="sxs-lookup"><span data-stu-id="eccdf-160">For a Front End pool to function at all, it cannot be in pool-level quorum loss.</span></span> <span data-ttu-id="eccdf-161">如果运行的服务器数低于功能级别，如下表所示，池中的其余服务器将停止所有 Lync Server 服务。</span><span class="sxs-lookup"><span data-stu-id="eccdf-161">If the number of servers running falls below the functional level as shown in the following table, the remaining servers in the pool will stop all Lync Server services.</span></span> <span data-ttu-id="eccdf-162">请注意，下表中的数字假定池中的后端服务器正在运行。</span><span class="sxs-lookup"><span data-stu-id="eccdf-162">Note that the numbers in the following table assume that the Back End Servers in the pool are running.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="eccdf-163">池中的前端服务器总数</span><span class="sxs-lookup"><span data-stu-id="eccdf-163">Total number of Front End Servers in the pool</span></span></th>
<th><span data-ttu-id="eccdf-164">要使池正常工作所必须运行的服务器的数目</span><span class="sxs-lookup"><span data-stu-id="eccdf-164">Number of servers that must be running for pool to be functional</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="eccdf-165">双面</span><span class="sxs-lookup"><span data-stu-id="eccdf-165">2</span></span></p></td>
<td><p><span data-ttu-id="eccdf-166">1</span><span class="sxs-lookup"><span data-stu-id="eccdf-166">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eccdf-167">3-4</span><span class="sxs-lookup"><span data-stu-id="eccdf-167">3-4</span></span></p></td>
<td><p><span data-ttu-id="eccdf-168">任意2</span><span class="sxs-lookup"><span data-stu-id="eccdf-168">Any 2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eccdf-169">5-6</span><span class="sxs-lookup"><span data-stu-id="eccdf-169">5-6</span></span></p></td>
<td><p><span data-ttu-id="eccdf-170">任意3</span><span class="sxs-lookup"><span data-stu-id="eccdf-170">Any 3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eccdf-171">7 </span><span class="sxs-lookup"><span data-stu-id="eccdf-171">7</span></span></p></td>
<td><p><span data-ttu-id="eccdf-172">任意4</span><span class="sxs-lookup"><span data-stu-id="eccdf-172">Any 4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="eccdf-173">8-9</span><span class="sxs-lookup"><span data-stu-id="eccdf-173">8-9</span></span></p></td>
<td><p><span data-ttu-id="eccdf-174">前7台服务器中的任意4个</span><span class="sxs-lookup"><span data-stu-id="eccdf-174">Any 4 of the first 7 servers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="eccdf-175">10-12</span><span class="sxs-lookup"><span data-stu-id="eccdf-175">10-12</span></span></p></td>
<td><p><span data-ttu-id="eccdf-176">前9个服务器中的任何5个</span><span class="sxs-lookup"><span data-stu-id="eccdf-176">Any 5 of the first 9 servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="eccdf-177">在上表中，"第一台服务器" 是第一次启动池时的服务器。</span><span class="sxs-lookup"><span data-stu-id="eccdf-177">In the preceding table, the “first servers” are the servers which were brought up first, chronologically, when the pool was started for the first time.</span></span> <span data-ttu-id="eccdf-178">若要确定这些服务器，可以结合使用 **CsComputer** cmdlet 和 **– PoolFqdn** 选项。</span><span class="sxs-lookup"><span data-stu-id="eccdf-178">To determine these servers, you can use the **Get-CsComputer** cmdlet with the **–PoolFqdn** option.</span></span> <span data-ttu-id="eccdf-179">此 cmdlet 将按其在拓扑中出现的顺序显示服务器，列表顶部的服务器是第一台服务器。</span><span class="sxs-lookup"><span data-stu-id="eccdf-179">This cmdlet will show the servers in the order that they appear in the topology, and the ones at the top of the list are the first servers.</span></span>

</div>

<div>

## <a name="front-end-pools-with-two-front-end-servers"></a><span data-ttu-id="eccdf-180">带有两个前端服务器的前端池</span><span class="sxs-lookup"><span data-stu-id="eccdf-180">Front End Pools with Two Front End Servers</span></span>

<span data-ttu-id="eccdf-p112">建议不要部署仅包含两台前端服务器的前端池。如果您确实需要这样的池，请遵循以下指导原则：</span><span class="sxs-lookup"><span data-stu-id="eccdf-p112">We do not recommend deploying a Front End pool that contains only two Front End Servers. If you do ever need to deploy such a pool, follow these guidelines:</span></span>

  - <span data-ttu-id="eccdf-p113">如果两个前端服务器之一停机，您应尝试将该失败的服务器尽快恢复运行。同样，如果需要升级两台服务器之一，升级完成后将其尽快联机。</span><span class="sxs-lookup"><span data-stu-id="eccdf-p113">If one of the two Front End Servers goes down, you should try to bring the failed server back up as soon as you can. Similarly, if you need to upgrade one of the two servers, bring it back online as soon as the upgrade is finished.</span></span>

  - <span data-ttu-id="eccdf-185">如果因某些原因需要将两台服务器同时停机，当该池停机后执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="eccdf-185">If for some reason you need to bring both servers down at the same time, do the following when the downtime for the pool is finished:</span></span>
    
      - <span data-ttu-id="eccdf-186">最佳做法是同时重新启动这两个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="eccdf-186">The best practice is to restart both Front End Servers at the same time.</span></span>
    
      - <span data-ttu-id="eccdf-187">如果无法同时重新启动两台服务器，则应该按其停机时的相反顺序来启动它们。</span><span class="sxs-lookup"><span data-stu-id="eccdf-187">If the two servers cannot be restarted at the same time, you should bring them back up in the reverse order of the order they went down.</span></span>
    
      - <span data-ttu-id="eccdf-188">如果按此顺序无活使其启动，则在启动该池前使用以下 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="eccdf-188">If you cannot bring them back up in that order, then use the following cmdlet before bringing the pool back up:.</span></span>
        
            Reset-CsPoolRegistrarState -ResetType QuorumLossRecovery -PoolFQDN <FQDN>

</div>

<div>

## <a name="additional-steps-to-ensure-pools-are-functional"></a><span data-ttu-id="eccdf-189">确保池正常运行的其他步骤</span><span class="sxs-lookup"><span data-stu-id="eccdf-189">Additional Steps to Ensure Pools are Functional</span></span>

<span data-ttu-id="eccdf-190">您应观看几个其他因素，以确保前端池保持正常运行。</span><span class="sxs-lookup"><span data-stu-id="eccdf-190">You should watch for a couple of other factors to ensure that your Front End pools remain functional.</span></span>

  - <span data-ttu-id="eccdf-191">当第一次将用户移动到池时，确保至少运行三个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="eccdf-191">When you move users to the pool for the first time, be sure at least three of the Front End Servers are running.</span></span>

  - <span data-ttu-id="eccdf-192">如果您为灾难恢复的目的建立此池和另一池之间的一对关系，那么在建立此关系后，必须确保在某些时候此池具有三个同时运行的前端服务器以正确将数据与备份池同步。</span><span class="sxs-lookup"><span data-stu-id="eccdf-192">If you establish a pairing relationship between this pool and another pool for disaster recovery purposes, then after establishing that relationship you must be sure this pool has three Front End Servers running simultaneously at some time to properly synchronize data with the backup pool.</span></span> <span data-ttu-id="eccdf-193">有关池配对和灾难恢复功能的详细信息，请参阅 [在 Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="eccdf-193">For more information on pool pairing and disaster recovery features, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

</div>

</div>

<div>

## <a name="improving-the-reliability-of-pool-upgrades"></a><span data-ttu-id="eccdf-194">改进池升级的可靠性</span><span class="sxs-lookup"><span data-stu-id="eccdf-194">Improving the Reliability of Pool Upgrades</span></span>

<span data-ttu-id="eccdf-195">当您需要升级或修补前端池中的服务器时，请遵循在 [Lync Server 2013 中的升级或更新前端服务器](lync-server-2013-upgrade-or-update-front-end-servers.md)中显示的工作流和以下指南：</span><span class="sxs-lookup"><span data-stu-id="eccdf-195">When you need to upgrade or patch the servers in a Front End pool, follow the workflow shown in [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md), and the following guidelines:</span></span>

  - <span data-ttu-id="eccdf-196">当您从一个升级域迁移到另一个升级域进行升级时 (在 [升级或更新前端服务器的 Lync Server 2013) 中](lync-server-2013-upgrade-or-update-front-end-servers.md) ，请使用 **CsPoolUpgradeReadinessState** Cmdlet 并检查 "就绪" 状态。</span><span class="sxs-lookup"><span data-stu-id="eccdf-196">When you move from one upgrade domain to another for upgrades (following the workflow at [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)), you will use the **Get-CsPoolUpgradeReadinessState** cmdlet and check for Ready state.</span></span> <span data-ttu-id="eccdf-197">在每个升级域达到 "就绪" 时，在每个升级域之间添加20分钟等待可提高升级的可靠性。</span><span class="sxs-lookup"><span data-stu-id="eccdf-197">Adding a 20-minute wait between each upgrade domain after it reaches “Ready” will make the upgrades more reliable.</span></span> <span data-ttu-id="eccdf-198">如果在此20分钟内 **未准备就绪** ，请重新启动20分钟计时器。</span><span class="sxs-lookup"><span data-stu-id="eccdf-198">If it becomes **Not Ready** during this 20 minutes, restart the 20-minute timer.</span></span> <span data-ttu-id="eccdf-199">此外，还可以在启动20分钟间隔之前和之后运行 **CsPoolFabricState** cmdlet，并确保不会对路由组的 primaries 和辅助映像进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="eccdf-199">Also, you can run the **Get-CsPoolFabricState** cmdlet before and after starting the 20-minute interval and make sure there are no changes to the primaries and secondaries of routing groups.</span></span>

  - <span data-ttu-id="eccdf-200">如果上一次修补的升级域中的任何服务器被卡住或没有重新启动，请不要移动到下一个升级域。</span><span class="sxs-lookup"><span data-stu-id="eccdf-200">Do not move on to the next upgrade domain if any of the servers in the last patched upgrade domain are stuck or not restarted.</span></span> <span data-ttu-id="eccdf-201">如果升级中的任何服务器无法启动，也会应用此规则。</span><span class="sxs-lookup"><span data-stu-id="eccdf-201">This also applies if any of the servers within an upgrade cannot start.</span></span> <span data-ttu-id="eccdf-202">运行 **CsPoolFabricState** 以确保所有路由组都有主和至少一个辅助数据库;这将确认是否所有用户都有服务。</span><span class="sxs-lookup"><span data-stu-id="eccdf-202">Run **Get-CsPoolFabricState** to make sure all of the routing groups have a primary and at least one secondary; this will confirm whether all users have service.</span></span>

  - <span data-ttu-id="eccdf-203">如果某些用户具有服务，而其他用户没有，请运行 **CsPoolFabricState** 和– Verbose 选项，以检查包含丢失副本的路由组。</span><span class="sxs-lookup"><span data-stu-id="eccdf-203">If some users have service and others do not, run **Get-CsPoolFabricState** with the –Verbose option to check for routing groups that have missing replicas.</span></span> <span data-ttu-id="eccdf-204">请勿将整个池重新启动为第一个故障排除步骤。</span><span class="sxs-lookup"><span data-stu-id="eccdf-204">Do not restart the entire pool as the first troubleshooting step.</span></span> <span data-ttu-id="eccdf-205">有关此 cmdlet 的详细信息，请参阅 [CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState)。</span><span class="sxs-lookup"><span data-stu-id="eccdf-205">For more information on this cmdlet, see [Get-CsPoolFabricState](https://docs.microsoft.com/powershell/module/skype/Get-CsPoolFabricState).</span></span>

  - <span data-ttu-id="eccdf-206">确保已关闭事件查看器或性能监视器窗口的所有实例，以供 windows fabric 安装/卸载。</span><span class="sxs-lookup"><span data-stu-id="eccdf-206">Make sure that all instances of the Event Viewer or Performance Monitor windows are closed for windows fabric installs/uninstalls.</span></span>

</div>

<div>

## <a name="changing-a-front-end-pools-configuration"></a><span data-ttu-id="eccdf-207">更改前端池的配置</span><span class="sxs-lookup"><span data-stu-id="eccdf-207">Changing a Front End Pool’s Configuration</span></span>

<span data-ttu-id="eccdf-208">每当将前端服务器添加到池，或从池将其删除，然后发布新拓扑时，请遵循以下指导原则：</span><span class="sxs-lookup"><span data-stu-id="eccdf-208">Whenever you add Front End Servers to a pool, or remove them from the pool, and then publish the new topology, follow these guidelines:</span></span>

  - <span data-ttu-id="eccdf-209">发布新拓扑后，必须重新启动池中的每台前端服务器。</span><span class="sxs-lookup"><span data-stu-id="eccdf-209">After the new topology has been published, you must restart each Front End Server in the pool.</span></span> <span data-ttu-id="eccdf-210">一次重新启动一个。</span><span class="sxs-lookup"><span data-stu-id="eccdf-210">Restart them one at a time.</span></span>

  - <span data-ttu-id="eccdf-211">如果在配置更改期间整个池已关闭，则在发布新拓扑后运行下列 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="eccdf-211">If the entire pool has been down during the configuration change, then run the following cmdlet after the new topology is published:</span></span>
    
        Reset-CsPoolRegistrarState -PoolFQDN <PoolFQDN> -ResetType ServiceReset

<span data-ttu-id="eccdf-p119">如果前端服务器失败，且在近期不可能替换，则从拓扑删除该服务器。当再次可用时向该拓扑添加新的前端服务器。</span><span class="sxs-lookup"><span data-stu-id="eccdf-p119">If a Front End Server fails and is unlikely to be replaced for a few days or more, remove the server from the topology. Add the new Front End Server to the topology when it is available again.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

