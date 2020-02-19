---
title: 使用用户模型的 Lync Server 2013 容量规划
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Capacity planning using the user models
ms:assetid: 902ab23e-94d6-482a-9d6e-c0b28dc3e03d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615015(v=OCS.15)
ms:contentKeyID: 49733733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 664091baee67d0ddf953d8a114370fdb875eef29
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135539"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a><span data-ttu-id="bd912-102">使用用户模型对 Lync Server 2013 进行容量规划</span><span class="sxs-lookup"><span data-stu-id="bd912-102">Capacity planning for Lync Server 2013 using the user models</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd912-103">_**上次修改的主题：** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="bd912-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="bd912-104">本节根据在[Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)中所述的使用情况，为网站上的用户数提供有关网站上所需的服务器数量的指南。</span><span class="sxs-lookup"><span data-stu-id="bd912-104">This section provides guidance on how many servers you need at a site for the number of users at that site, according to the usage described in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<div>

## <a name="tested-hardware-platform"></a><span data-ttu-id="bd912-105">测试的硬件平台</span><span class="sxs-lookup"><span data-stu-id="bd912-105">Tested Hardware Platform</span></span>

<span data-ttu-id="bd912-106">本节中的所有性能结果和部署建议都基于运行下表中所述的硬件的服务器上的性能测试。</span><span class="sxs-lookup"><span data-stu-id="bd912-106">All the performance results and deployment recommendations in this section are based on performance testing on servers running the hardware described in the following table.</span></span> <span data-ttu-id="bd912-107">建议使用类似的硬件。</span><span class="sxs-lookup"><span data-stu-id="bd912-107">We recommend that you use similar hardware.</span></span> <span data-ttu-id="bd912-108">如果使用性能不足的硬件，可能会遇到功能问题或性能下降。</span><span class="sxs-lookup"><span data-stu-id="bd912-108">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="bd912-109">请注意，这些硬件建议高于早期版本的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="bd912-109">Note that these hardware recommendations are higher than those of previous versions of Lync Server.</span></span>

### <a name="hardware-used-in-performance-testing"></a><span data-ttu-id="bd912-110">性能测试中使用的硬件</span><span class="sxs-lookup"><span data-stu-id="bd912-110">Hardware Used in Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd912-111">硬件组件</span><span class="sxs-lookup"><span data-stu-id="bd912-111">Hardware component</span></span></th>
<th><span data-ttu-id="bd912-112">建议</span><span class="sxs-lookup"><span data-stu-id="bd912-112">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd912-113">CPU</span><span class="sxs-lookup"><span data-stu-id="bd912-113">CPU</span></span></p></td>
<td><p><span data-ttu-id="bd912-114">64 位双处理器、六核、2.26 GHz 或更快</span><span class="sxs-lookup"><span data-stu-id="bd912-114">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p>
<p><span data-ttu-id="bd912-115">Lync Server 服务器角色不支持 Intel Itanium 处理器。</span><span class="sxs-lookup"><span data-stu-id="bd912-115">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd912-116">内存</span><span class="sxs-lookup"><span data-stu-id="bd912-116">Memory</span></span></p></td>
<td><p><span data-ttu-id="bd912-117">32 GB</span><span class="sxs-lookup"><span data-stu-id="bd912-117">32 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd912-118">磁盘</span><span class="sxs-lookup"><span data-stu-id="bd912-118">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="bd912-119">8个或更多的 10000 RPM 硬盘，至少有 72 GB 的可用磁盘空间。</span><span class="sxs-lookup"><span data-stu-id="bd912-119">8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="bd912-120">其中两个磁盘驱动器应使用 RAID 1，另外六个磁盘驱动器应使用 RAID 10。</span><span class="sxs-lookup"><span data-stu-id="bd912-120">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="bd912-121">-和</span><span class="sxs-lookup"><span data-stu-id="bd912-121">- OR -</span></span></p></li>
<li><p><span data-ttu-id="bd912-122">性能类似于 8 个 10,000 RPM 机械磁盘驱动器的固态驱动器 (SSD)</span><span class="sxs-lookup"><span data-stu-id="bd912-122">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd912-123">网络</span><span class="sxs-lookup"><span data-stu-id="bd912-123">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="bd912-124">1 个双端口网络适配器，1 Gbps 或更高（建议为 2 Gbps，这要求与一个 MAC 地址和一个 IP 地址结合使用）</span><span class="sxs-lookup"><span data-stu-id="bd912-124">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a><span data-ttu-id="bd912-125">结果摘要</span><span class="sxs-lookup"><span data-stu-id="bd912-125">Summary of Results</span></span>

<span data-ttu-id="bd912-126">下表总结了这些建议。</span><span class="sxs-lookup"><span data-stu-id="bd912-126">The following table summarizes these recommendations.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd912-127">服务器角色</span><span class="sxs-lookup"><span data-stu-id="bd912-127">Server role</span></span></th>
<th><span data-ttu-id="bd912-128">受支持的最大用户数</span><span class="sxs-lookup"><span data-stu-id="bd912-128">Maximum number of users supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd912-129">前端池具有十二个前端服务器和一台后端服务器或一对后端服务器。</span><span class="sxs-lookup"><span data-stu-id="bd912-129">Front End pool with twelve Front End Servers and one Back End Server or a mirrored pair of Back End Servers.</span></span></p></td>
<td><p><span data-ttu-id="bd912-130">80000唯一用户同时登录，再加上50% 的状态点（MPOP），代表非移动实例，加上40% 的用户为移动计算总的152000终结点而启用的用户数。</span><span class="sxs-lookup"><span data-stu-id="bd912-130">80,000 unique users simultaneously logged in, plus 50% multiple points of presence (MPOP) representing non-mobile instances, plus 40% of users enabled for Mobility for a total of 152,000 endpoints.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd912-131">A/V 会议</span><span class="sxs-lookup"><span data-stu-id="bd912-131">A/V Conferencing</span></span></p></td>
<td><p><span data-ttu-id="bd912-132">前端池提供的 A/V 会议服务支持池的会议，假定最大会议大小为250个用户，并且一次仅运行一个这样的大型会议。</span><span class="sxs-lookup"><span data-stu-id="bd912-132">The A/V Conferencing service provided by a Front End pool supports the pool’s conferences assuming a maximum conference size of 250 users, and only one such large conference running at a time.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="bd912-133">此外，可以通过部署单独的前端池和两台前端服务器来托管大型会议，从而支持250和1000用户之间的大型会议。</span><span class="sxs-lookup"><span data-stu-id="bd912-133">Additionally, you can support large conferences of between 250 and 1000 users by deploying a separate Front End pool with two Front End Servers to host the large conferences.</span></span> <span data-ttu-id="bd912-134">有关详细信息，请参阅<A href="lync-server-2013-supporting-large-meetings.md">使用 Lync Server 2013 支持大型会议</A>。</span><span class="sxs-lookup"><span data-stu-id="bd912-134">For details, see <A href="lync-server-2013-supporting-large-meetings.md">Supporting large meetings using Lync Server 2013</A>.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd912-135">一台边缘服务器</span><span class="sxs-lookup"><span data-stu-id="bd912-135">One Edge Server</span></span></p></td>
<td><p><span data-ttu-id="bd912-136">12000并发远程用户</span><span class="sxs-lookup"><span data-stu-id="bd912-136">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd912-137">一台控制器</span><span class="sxs-lookup"><span data-stu-id="bd912-137">One Director</span></span></p></td>
<td><p><span data-ttu-id="bd912-138">12000并发远程用户</span><span class="sxs-lookup"><span data-stu-id="bd912-138">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd912-139">监控和存档</span><span class="sxs-lookup"><span data-stu-id="bd912-139">Monitoring and Archiving</span></span></p></td>
<td><p><span data-ttu-id="bd912-140">在 Lync Server 2013 中，监视和存档前端服务现在在每台前端服务器上运行，而不是在单独的服务器角色上运行。</span><span class="sxs-lookup"><span data-stu-id="bd912-140">In Lync Server 2013, the Monitoring and Archiving front end services now run on each Front End Server, instead of on separate server roles.</span></span></p>
<p><span data-ttu-id="bd912-141">监视和存档每个仍需要自己的数据库存储。</span><span class="sxs-lookup"><span data-stu-id="bd912-141">Monitoring and Archiving each still require their own database stores.</span></span> <span data-ttu-id="bd912-142">如果还运行 Exchange 2013，则可以将存档数据保存在 Exchange 中，而不是保存在专用 SQL 数据库中。</span><span class="sxs-lookup"><span data-stu-id="bd912-142">If you also run Exchange 2013, you can keep your Archiving data in Exchange, rather than in a dedicated SQL database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd912-143">一台中介服务器</span><span class="sxs-lookup"><span data-stu-id="bd912-143">One Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="bd912-144">使用前端服务器的中介服务器并置在池中的每台前端服务器上运行，并且应为池中的用户提供足够的容量。</span><span class="sxs-lookup"><span data-stu-id="bd912-144">Mediation Server collocated with Front End Server runs on every Front End Server in a pool, and should provide enough capacity for the users in the pool.</span></span> <span data-ttu-id="bd912-145">对于独立的中介服务器，请参阅本主题后面的 "中介服务器" 一节。</span><span class="sxs-lookup"><span data-stu-id="bd912-145">For stand-alone Mediation Server, see the “Mediation Server” section later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd912-146">一台 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="bd912-146">One Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="bd912-147">强烈建议如果您使用 Standard Edition 服务器来托管用户，则始终使用两台服务器，并使用在<a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Lync Server 2013 中规划高可用性和灾难恢复中</a>的建议进行配对。</span><span class="sxs-lookup"><span data-stu-id="bd912-147">We strongly recommend that if you use Standard Edition servers to host users, you always use two servers, paired using the recommendations in <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planning for high availability and disaster recovery in Lync Server 2013</a>.</span></span> <span data-ttu-id="bd912-148">对中的每台服务器都可以承载多达2500个用户，如果一台服务器发生故障，则其他服务器可以在故障转移方案中支持5000用户。</span><span class="sxs-lookup"><span data-stu-id="bd912-148">Each server in the pair can host up to 2,500 users, and if one server fails the remaining server can support 5,000 users in a failover scenario.</span></span></p>
<p><span data-ttu-id="bd912-149">如果您的部署包括大量的音频或视频流量，则服务器性能可能会受到每台服务器超过2500个用户的影响。</span><span class="sxs-lookup"><span data-stu-id="bd912-149">If your deployment includes a significant amount of audio or video traffic, server performance may suffer with more than 2,500 users per server.</span></span> <span data-ttu-id="bd912-150">在这种情况下，应考虑添加更多 Standard Edition 服务器或移动到 Lync Server Enterprise Edition。</span><span class="sxs-lookup"><span data-stu-id="bd912-150">In this case, you should consider adding more Standard Edition servers or moving to Lync Server Enterprise Edition.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a><span data-ttu-id="bd912-151">Front End Server － 前端服务器</span><span class="sxs-lookup"><span data-stu-id="bd912-151">Front End Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bd912-152">此服务器角色不支持延伸池。</span><span class="sxs-lookup"><span data-stu-id="bd912-152">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="bd912-153">在前端池中，应为驻留在池中的每个6660用户安装一个前端服务器，假设池中的所有服务器上都启用了超线程，并且服务器硬件满足[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的建议。</span><span class="sxs-lookup"><span data-stu-id="bd912-153">In a Front End pool, you should have one Front End Server for every 6,660 users homed in the pool, assuming that hyper-threading is enabled on all servers in the pool, and that the server hardware meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span> <span data-ttu-id="bd912-154">一个前端池中的最大用户数为80000，假定在池中的所有服务器上启用了超线程。</span><span class="sxs-lookup"><span data-stu-id="bd912-154">The maximum number of users in one Front End pool is 80,000, assuming that hyper-threading is enabled on all the servers in the pool.</span></span> <span data-ttu-id="bd912-155">如果站点上的用户数超过 80,000，则可部署多个前端池。</span><span class="sxs-lookup"><span data-stu-id="bd912-155">If you have more than 80,000 users at a site, you can deploy more than one Front End pool.</span></span>

<span data-ttu-id="bd912-156">在计算前端池中的用户数时，请将分支机构中与此前端池关联的 Survivable Branch Appliance 和 Survivable Branch Server 上驻留的用户包括在内。</span><span class="sxs-lookup"><span data-stu-id="bd912-156">When you account for the number of users in a Front End pool, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with this Front End pool.</span></span>

<span data-ttu-id="bd912-157">活动服务器不可用时，其连接会自动转接给池中的其他服务器。</span><span class="sxs-lookup"><span data-stu-id="bd912-157">When an active server is unavailable, its connections are transferred automatically to the other servers in the pool.</span></span> <span data-ttu-id="bd912-158">例如，如果您有30000个用户和五台前端服务器，那么，如果一台服务器不可用，则需要将6000用户的连接转移到其他四台服务器。</span><span class="sxs-lookup"><span data-stu-id="bd912-158">For example, if you have 30,000 users and five Front End Servers, then if one server is unavailable, the connections of 6000 users need to be transferred to the other four servers.</span></span> <span data-ttu-id="bd912-159">其余四台服务器每个都有7500个用户，这比建议的数量更大。</span><span class="sxs-lookup"><span data-stu-id="bd912-159">The remaining four servers will each have 7500 users, which is a larger number than recommended.</span></span>

<span data-ttu-id="bd912-160">如果您已开始为30000用户使用6台前端服务器，并且后来的服务器变得不可用，则总共5000个用户将移至其余的5台服务器。</span><span class="sxs-lookup"><span data-stu-id="bd912-160">If instead you had started with six Front End Servers for your 30,000 users and subsequently one became unavailable, a total of 5000 users will be moved to the remaining five servers.</span></span> <span data-ttu-id="bd912-161">这五台服务器将每台主机6000用户，在建议的范围内。</span><span class="sxs-lookup"><span data-stu-id="bd912-161">These five servers will each host 6000 users, which is in the recommended range.</span></span>

<span data-ttu-id="bd912-162">前端池的最大用户数是 80,000。</span><span class="sxs-lookup"><span data-stu-id="bd912-162">The maximum number of users in a Front End pool is 80,000.</span></span> <span data-ttu-id="bd912-163">池中的最大前端服务器数为12个。</span><span class="sxs-lookup"><span data-stu-id="bd912-163">The maximum number of Front End Servers in a pool is 12.</span></span>

<span data-ttu-id="bd912-164">对于80000用户的前端池，在采用[Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)的典型部署中，12前端服务器的性能就足够了。</span><span class="sxs-lookup"><span data-stu-id="bd912-164">For a Front End pool with 80,000 users, twelve Front End Servers is sufficient for performance, in typical deployments that follow the [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span> <span data-ttu-id="bd912-165">旨在支持灾难恢复故障转移的部署假定在两个配对的前端池中最多可以托管40000个用户，其中每个池都有足够的前端服务器以适应两个池中的用户，而一个池需要发生故障转移到另一个。</span><span class="sxs-lookup"><span data-stu-id="bd912-165">Deployments designed to support disaster recovery failover assume that a maximum of 40,000 users can be hosted in each of two paired Front End pools, in which each pool has enough Front End Servers to accommodate the users in both pools should one pool need to be failed over to the other.</span></span>

<span data-ttu-id="bd912-166">因特定前端池而支持的用户数与这些数字不同，原因可能有以下几种：</span><span class="sxs-lookup"><span data-stu-id="bd912-166">The number of users supported with good performance by a particular Front End pool may differ from these numbers for the following reasons:</span></span>

  - <span data-ttu-id="bd912-167">前端服务器的硬件不符合[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的建议。</span><span class="sxs-lookup"><span data-stu-id="bd912-167">The hardware for your Front End Servers does not meet the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

  - <span data-ttu-id="bd912-168">组织的用法与用户模型明显不同，如明显具有更多的会议流量。</span><span class="sxs-lookup"><span data-stu-id="bd912-168">Your organization’s usage differs significantly from the user models, such as significantly more conferencing traffic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="bd912-169">在 Lync Server 2013 中，状态数据库现在托管在前端服务器上，而不是驻留在后端服务器上的 Lync Server 2010 中。</span><span class="sxs-lookup"><span data-stu-id="bd912-169">In Lync Server 2013, the presence databases are now hosted on Front End Servers, unlike in Lync Server 2010 where they were hosted on the Back End Server.</span></span> <span data-ttu-id="bd912-170">这意味着，无论前端服务器托管的用户数如何，您的前端服务器的磁盘性能和容量不应从本部分前面列出的建议中和在<A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 的服务器硬件平台</A>中受到损害。</span><span class="sxs-lookup"><span data-stu-id="bd912-170">This means that the disk performance and capacity of your Front End Servers should not be compromised from the recommendations listed earlier in this section and in <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>, regardless of the number of users hosted by your Front End Servers.</span></span>



</div>

<span data-ttu-id="bd912-171">下表显示了在给定用户模型（在[Lync Server 2013 的用户模型](lync-server-2013-user-models.md)中定义）的 IM 和状态的平均带宽。</span><span class="sxs-lookup"><span data-stu-id="bd912-171">The following table shows the average bandwidth for IM and presence, given the user model, as defined in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd912-172">每个用户的平均带宽</span><span class="sxs-lookup"><span data-stu-id="bd912-172">Average bandwidth per user</span></span></th>
<th><span data-ttu-id="bd912-173">每个具有6660用户的前端服务器的带宽要求</span><span class="sxs-lookup"><span data-stu-id="bd912-173">Bandwidth requirements per Front End Server with 6,660 users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd912-174">1.3 Kpbs</span><span class="sxs-lookup"><span data-stu-id="bd912-174">1.3 Kpbs</span></span></p></td>
<td><p><span data-ttu-id="bd912-175">13 Mbps</span><span class="sxs-lookup"><span data-stu-id="bd912-175">13 Mbps</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="bd912-176">若要改善在前端服务器上归置的 A/V 会议和中介服务器功能的媒体性能，应在前端服务器上的网络适配器上启用接收方缩放（RSS）。</span><span class="sxs-lookup"><span data-stu-id="bd912-176">To improve the media performance of the co-located A/V Conferencing and Mediation Server functionality on your Front End Servers, you should enable receive-side scaling (RSS) on the network adapters on your Front End Servers.</span></span> <span data-ttu-id="bd912-177">通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。</span><span class="sxs-lookup"><span data-stu-id="bd912-177">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="bd912-178">有关详细信息，请参阅中的 "在<A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>Windows Server 2008 中接收端扩展功能增强"。</span><span class="sxs-lookup"><span data-stu-id="bd912-178">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="bd912-179">有关如何启用 RSS 的详细信息，请参阅网络适配器文档。</span><span class="sxs-lookup"><span data-stu-id="bd912-179">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="conferencing-maximums"></a><span data-ttu-id="bd912-180">会议最大值</span><span class="sxs-lookup"><span data-stu-id="bd912-180">Conferencing Maximums</span></span>

<span data-ttu-id="bd912-181">假定用户模型为池中 5% 的用户可能会在任何时候参加会议，则拥有 80,000 个用户的池一次可能会有大约 4,000 个用户参加会议。</span><span class="sxs-lookup"><span data-stu-id="bd912-181">Given the user model that 5% of users in a pool may be in a conference at any one time, a pool of 80,000 users could have about 4,000 users in conferences at one time.</span></span> <span data-ttu-id="bd912-182">这些会议可能混合多种媒体（如一些仅含 IM、一些含有 IM 和音频、一些含有音频/视频）并拥有大量参与者。</span><span class="sxs-lookup"><span data-stu-id="bd912-182">These conferences are expected to be a mix of media (some IM-only, some IM with audio, some audio/video, for example) and number of participants.</span></span> <span data-ttu-id="bd912-183">允许的实际会议数没有硬限制，但实际用法决定了实际性能。</span><span class="sxs-lookup"><span data-stu-id="bd912-183">There is no hard limit for the actual number of conferences allowed, and actual usage determines the actual performance.</span></span> <span data-ttu-id="bd912-184">例如，如果组织中具有的混合模式会议的数量多于用户模型中假定的混合模式会议的数量，则可能需要部署的前端服务器或 A/V 会议服务器的数量会多于本文档中推荐的数量。</span><span class="sxs-lookup"><span data-stu-id="bd912-184">For example, if your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers or A/V Conferencing Servers than the recommendations in this document.</span></span> <span data-ttu-id="bd912-185">有关用户模型中的假设的详细信息，请参阅[Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)。</span><span class="sxs-lookup"><span data-stu-id="bd912-185">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="bd912-186">由常规 Lync Server 2013 前端池托管的受支持的最大会议大小（也承载用户）是250参与者。</span><span class="sxs-lookup"><span data-stu-id="bd912-186">The maximum supported conference size hosted by a regular Lync Server 2013 Front End pool which also hosts users is 250 participants.</span></span> <span data-ttu-id="bd912-187">当发生 250-用户会议时，该池仍支持其他会议，从而使总池用户数达5% 的池用户处于并发会议中。</span><span class="sxs-lookup"><span data-stu-id="bd912-187">While a 250-user conference is happening, the pool still supports other conferences as well, such that a total of 5% of pool users are in concurrent conferences.</span></span> <span data-ttu-id="bd912-188">例如，在12台前端服务器和80000用户的池中，当 250-用户会议发生时，Lync Server 支持对参与小型会议的其他用户进行3750。</span><span class="sxs-lookup"><span data-stu-id="bd912-188">For example, in a pool of twelve Front End Servers and 80,000 users, while the 250-user conference is happening, Lync Server supports 3,750 other users participating in smaller conferences.</span></span>

<span data-ttu-id="bd912-189">无论驻留在前端池或 Standard Edition 服务器上的用户数是多少，Lync Server 至少支持125在承载250用户会议的同一池或服务器上参与小型会议的其他用户。</span><span class="sxs-lookup"><span data-stu-id="bd912-189">Regardless of the number of users homed on the Front End pool or Standard Edition server, Lync Server supports a minimum of 125 other users participating in smaller conferences on the same pool or server which is hosting a 250-user conference.</span></span>

<span data-ttu-id="bd912-190">若要启用介于250和1000用户之间的会议，您可以设置单独的前端池，只需承载这些会议即可。</span><span class="sxs-lookup"><span data-stu-id="bd912-190">To enable conferences with between 250 and 1000 users, you can set up a separate Front End pool just to host those conferences.</span></span> <span data-ttu-id="bd912-191">此前端池不会承载任何用户。</span><span class="sxs-lookup"><span data-stu-id="bd912-191">This Front End pool will not host any users.</span></span> <span data-ttu-id="bd912-192">有关详细信息，请参阅[使用 Lync Server 2013 支持大型会议](lync-server-2013-supporting-large-meetings.md)。</span><span class="sxs-lookup"><span data-stu-id="bd912-192">For details, see [Supporting large meetings using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span></span>

<span data-ttu-id="bd912-193">如果您的组织的混合模式会议比用户模型中的假设多，则可能需要部署比本文档中的建议更多的前端服务器（最多为12个 FEs）。</span><span class="sxs-lookup"><span data-stu-id="bd912-193">If your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers than the recommendations in this document (up to a limit of 12 FEs).</span></span> <span data-ttu-id="bd912-194">有关用户模型中的假设的详细信息，请参阅[Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)。</span><span class="sxs-lookup"><span data-stu-id="bd912-194">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="bd912-195">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="bd912-195">Edge Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bd912-196">此服务器角色不支持延伸池。</span><span class="sxs-lookup"><span data-stu-id="bd912-196">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="bd912-197">应为将同时访问网站的每个12000远程用户部署一台边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="bd912-197">You should deploy one Edge Server for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="bd912-198">为实现高可用性，建议至少部署两台边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="bd912-198">At a minimum we recommend two Edge Servers for high availability.</span></span> <span data-ttu-id="bd912-199">这些建议假定您的边缘服务器的硬件满足[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的建议。</span><span class="sxs-lookup"><span data-stu-id="bd912-199">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="bd912-200">在计算边缘服务器的用户数时，请将分支机构中与此站点的前端池关联的 Survivable Branch Appliance 和 Survivable Branch Server 上驻留的用户包括在内。</span><span class="sxs-lookup"><span data-stu-id="bd912-200">When you account for the number of users for the Edge Servers, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bd912-201">要提高边缘服务器上的 A/V 会议边缘服务的性能，应在边缘服务器的网络适配器上启用接收方缩放 (RSS)。</span><span class="sxs-lookup"><span data-stu-id="bd912-201">To improve the performance of the A/V Conferencing Edge service on your Edge Servers, you should enable receive-side scaling (RSS) on the network adapters on your Edge Servers.</span></span> <span data-ttu-id="bd912-202">通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。</span><span class="sxs-lookup"><span data-stu-id="bd912-202">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="bd912-203">有关详细信息，请参阅中的 "在<A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>Windows Server 2008 中接收端扩展功能增强"。</span><span class="sxs-lookup"><span data-stu-id="bd912-203">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="bd912-204">有关如何启用 RSS 的详细信息，请参阅网络适配器文档。</span><span class="sxs-lookup"><span data-stu-id="bd912-204">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="director"></a><span data-ttu-id="bd912-205">控制器</span><span class="sxs-lookup"><span data-stu-id="bd912-205">Director</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bd912-206">此服务器角色不支持延伸池。</span><span class="sxs-lookup"><span data-stu-id="bd912-206">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="bd912-207">如果部署控制器服务器角色，建议您为将同时访问网站的每个12000远程用户部署一个控制器。</span><span class="sxs-lookup"><span data-stu-id="bd912-207">If you deploy the Director server role we recommend that you deploy one Director for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="bd912-208">为实现高可用性，建议至少部署两台控制器。</span><span class="sxs-lookup"><span data-stu-id="bd912-208">At a minimum we recommend two Directors for high availability.</span></span> <span data-ttu-id="bd912-209">这些建议假定您的边缘服务器的硬件满足[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的建议。</span><span class="sxs-lookup"><span data-stu-id="bd912-209">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="bd912-210">在计算控制器的用户数时，请将分支机构中与此站点的前端池关联的 Survivable Branch Appliance 和 Survivable Branch Server 上驻留的用户包括在内。</span><span class="sxs-lookup"><span data-stu-id="bd912-210">When you account for the number of users for the Directors, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="bd912-211">中介服务器</span><span class="sxs-lookup"><span data-stu-id="bd912-211">Mediation Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="bd912-212">此服务器角色不支持延伸池。</span><span class="sxs-lookup"><span data-stu-id="bd912-212">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="bd912-213">如果您并置中介服务器与前端服务器，中介服务器将在池中的每台前端服务器上运行，并应为池中的用户提供足够的容量。</span><span class="sxs-lookup"><span data-stu-id="bd912-213">If you collocate Mediation Server with Front End Server, Mediation Server runs on every Front End Server in the pool, and should provide enough capacity for the users in the pool.</span></span>

<span data-ttu-id="bd912-214">如果您部署独立的中介服务器池，则要部署多少个中介服务器取决于许多因素，包括用于中介服务器的硬件、您拥有的 VoIP 用户数、每个中介服务器池的网关对等端数。控件、通过这些网关的繁忙小时流量，以及绕过中介服务器的媒体调用的百分比。</span><span class="sxs-lookup"><span data-stu-id="bd912-214">If you deploy a stand-alone Mediation Server pool, then how many Mediation Servers to deploy depends on many factors, including the hardware used for Mediation Server, the number of VoIP users you have, the number of gateway peers that each Mediation Server pool controls, the busy hour traffic through those gateways, and the percentage of calls with media that bypasses the Mediation Server.</span></span>

<span data-ttu-id="bd912-215">下表提供了对中介服务器可以处理的并发呼叫数的指导，假定中介服务器的硬件满足[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的要求，并且启用了超线程。</span><span class="sxs-lookup"><span data-stu-id="bd912-215">The following tables provide a guideline for how many concurrent calls a Mediation Server can handle, assuming that the hardware for the Mediation Servers meets the requirements in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) and that hyper-threading is enabled.</span></span> <span data-ttu-id="bd912-216">有关中介服务器可伸缩性的详细信息，请参阅[在 Lync server 2013 中](lync-server-2013-deployment-guidelines-for-mediation-server.md)[估计适用于 lync server 2013 的语音使用情况和流量](lync-server-2013-estimating-voice-usage-and-traffic.md)和中介服务器的部署指南。</span><span class="sxs-lookup"><span data-stu-id="bd912-216">For details about Mediation Server scalability, see [Estimating voice usage and traffic for Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) and [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="bd912-217">下表假定[Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)中汇总了使用率。</span><span class="sxs-lookup"><span data-stu-id="bd912-217">All the following tables assume usage as summarized in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a><span data-ttu-id="bd912-218">独立中介服务器容量：70% 内部用户，30% 外部用户（中介服务器执行的媒体转码），无绕过呼叫容量</span><span class="sxs-lookup"><span data-stu-id="bd912-218">Stand-alone Mediation Server Capacity: 70% Internal Users, 30% External users with non-bypass call capacity (media transcoding performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd912-219">服务器硬件</span><span class="sxs-lookup"><span data-stu-id="bd912-219">Server hardware</span></span></th>
<th><span data-ttu-id="bd912-220">最大呼叫数</span><span class="sxs-lookup"><span data-stu-id="bd912-220">Maximum number of calls</span></span></th>
<th><span data-ttu-id="bd912-221">最大 T1 线路数</span><span class="sxs-lookup"><span data-stu-id="bd912-221">Maximum number of T1 lines</span></span></th>
<th><span data-ttu-id="bd912-222">最大 E1 线路数</span><span class="sxs-lookup"><span data-stu-id="bd912-222">Maximum number of E1 lines</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd912-223">双处理器，hex core，2.26 GHz 超线程 CPU，<strong>禁用超线程</strong>，使用 32 GB 内存和一个双端口网络适配器卡。</span><span class="sxs-lookup"><span data-stu-id="bd912-223">Dual processor, hex core, 2.26 GHz hyper-threaded CPU <strong>with hyper-threading disabled</strong>, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="bd912-224">1100</span><span class="sxs-lookup"><span data-stu-id="bd912-224">1100</span></span></p></td>
<td><p><span data-ttu-id="bd912-225">46</span><span class="sxs-lookup"><span data-stu-id="bd912-225">46</span></span></p></td>
<td><p><span data-ttu-id="bd912-226">35</span><span class="sxs-lookup"><span data-stu-id="bd912-226">35</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd912-227">双处理器，十六核，2.26 GHz 超线程 CPU，带 32 GB 内存和一个双端口网络适配器卡。</span><span class="sxs-lookup"><span data-stu-id="bd912-227">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="bd912-228">1500</span><span class="sxs-lookup"><span data-stu-id="bd912-228">1500</span></span></p></td>
<td><p><span data-ttu-id="bd912-229">63</span><span class="sxs-lookup"><span data-stu-id="bd912-229">63</span></span></p></td>
<td><p><span data-ttu-id="bd912-230">47</span><span class="sxs-lookup"><span data-stu-id="bd912-230">47</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="bd912-231">虽然性能测试使用的是内存为 32 GB 的服务器，但内存为 16 GB 的服务器也可用作独立中介服务器，并且足以提供此表中显示的性能。</span><span class="sxs-lookup"><span data-stu-id="bd912-231">Although servers with 32 GB of memory were used for performance testing, servers with 16 GB of memory are supported for stand-alone Mediation Server, and are sufficient to provide the performance shown in this table.</span></span>



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a><span data-ttu-id="bd912-232">中介服务器容量（中介服务器并置与前端服务器）70% 内部用户，30% 外部用户，无绕过呼叫容量（由中介服务器执行的媒体处理）</span><span class="sxs-lookup"><span data-stu-id="bd912-232">Mediation Server Capacity (Mediation Server Collocated with Front End Server) 70% Internal Users, 30% External Users, Non-Bypass Call Capacity (Media Processing Performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd912-233">服务器硬件</span><span class="sxs-lookup"><span data-stu-id="bd912-233">Server hardware</span></span></th>
<th><span data-ttu-id="bd912-234">最大呼叫数</span><span class="sxs-lookup"><span data-stu-id="bd912-234">Maximum number of calls</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd912-235">双处理器，十六核，2.26 GHz 超线程 CPU，含 32 GB 内存和2个1GB 网络适配器卡。</span><span class="sxs-lookup"><span data-stu-id="bd912-235">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and 2 1GB network adapter cards.</span></span></p></td>
<td><p><span data-ttu-id="bd912-236">150</span><span class="sxs-lookup"><span data-stu-id="bd912-236">150</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="bd912-237">此数字比独立中介服务器的编号要小得多，因为前端服务器除了语音呼叫所需的转码之外，还必须为驻留在其上的6600用户处理其他特性和功能。</span><span class="sxs-lookup"><span data-stu-id="bd912-237">This number is much smaller than the numbers for the stand-alone Mediation Server because the Front End Server has to handle other features and functions for the 6600 users homed on it, in addition to the transcoding needed for voice calls.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="bd912-238">若要提高中介服务器的性能，应在中介服务器上的网络适配器上启用接收方缩放（RSS）。</span><span class="sxs-lookup"><span data-stu-id="bd912-238">To improve the performance of the Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on your Mediation Servers.</span></span> <span data-ttu-id="bd912-239">通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。</span><span class="sxs-lookup"><span data-stu-id="bd912-239">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="bd912-240">有关详细信息，请参阅中的 "在<A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>Windows Server 2008 中接收端扩展功能增强"。</span><span class="sxs-lookup"><span data-stu-id="bd912-240">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="https://go.microsoft.com/fwlink/p/?linkid=268731">https://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="bd912-241">有关如何启用 RSS 的详细信息，请参阅网络适配器文档。</span><span class="sxs-lookup"><span data-stu-id="bd912-241">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="back-end-server"></a><span data-ttu-id="bd912-242">后端服务器</span><span class="sxs-lookup"><span data-stu-id="bd912-242">Back End Server</span></span>

<span data-ttu-id="bd912-243">在 Lync Server 2013 中，状态数据库位于前端服务器上，而不是位于后端服务器上。</span><span class="sxs-lookup"><span data-stu-id="bd912-243">In Lync Server 2013, the presence databases are located on the Front End Servers instead of the Back End Server.</span></span> <span data-ttu-id="bd912-244">这为 Lync Server 2013 中的每台后端服务器带来了更简单的要求，相当于前端服务器的硬件要求。</span><span class="sxs-lookup"><span data-stu-id="bd912-244">This has resulted in a much simpler requirement for each Back End Server in Lync Server 2013, equivalent to the hardware requirement for the Front End Server.</span></span> <span data-ttu-id="bd912-245">与 Lync Server 2010 相比，需要将后端服务器设为具有25个磁盘的更高等级服务器。</span><span class="sxs-lookup"><span data-stu-id="bd912-245">Contrast this to Lync Server 2010, where the Back End Server was required to be a much higher grade server with 25 disks.</span></span> <span data-ttu-id="bd912-246">但是，后端服务器的工作负荷仍为无法满足本部分以及[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中列出的硬件建议。</span><span class="sxs-lookup"><span data-stu-id="bd912-246">However, the workload of Back End Servers is still such that you should not fail to meet the hardware recommendations listed earlier in this section and in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="bd912-247">若要提供您的后端服务器的高可用性，建议部署服务器镜像。</span><span class="sxs-lookup"><span data-stu-id="bd912-247">To provide high availability of your Back End Server, we recommend deploying server mirroring.</span></span> <span data-ttu-id="bd912-248">有关详细信息，请参阅[Lync server 2013 中的后端服务器高可用性](lync-server-2013-back-end-server-high-availability.md)。</span><span class="sxs-lookup"><span data-stu-id="bd912-248">For more information, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span>

</div>

<div>

## <a name="monitoring-and-archiving"></a><span data-ttu-id="bd912-249">监控和存档</span><span class="sxs-lookup"><span data-stu-id="bd912-249">Monitoring and Archiving</span></span>

<span data-ttu-id="bd912-250">在 Lync Server 2013 中，如果您部署监控或存档，这些服务的前端功能将在前端服务器上运行，而不是在单独的服务器角色上运行。</span><span class="sxs-lookup"><span data-stu-id="bd912-250">In Lync Server 2013, if you deploy Monitoring or Archiving, the front end functionality of these services runs on the Front End Servers, instead of on separate server roles.</span></span> <span data-ttu-id="bd912-251">监视和存档每个仍使用自己的数据库存储，与后端存储分开。</span><span class="sxs-lookup"><span data-stu-id="bd912-251">Monitoring and Archiving each still use their own database store, separate from the Back End store.</span></span> <span data-ttu-id="bd912-252">或者，如果部署了 Exchange 2013，则可以在 Exchange 中（而不是在专用的 SQL 存储中）存储即时消息存档数据。</span><span class="sxs-lookup"><span data-stu-id="bd912-252">Alternatively, if you have Exchange 2013 deployed, you can store instant message Archiving data in Exchange instead of in a dedicated SQL store.</span></span>

<span data-ttu-id="bd912-253">下表指出了每个用户每天需要多少数据库存储来监视和存档数据。</span><span class="sxs-lookup"><span data-stu-id="bd912-253">The following table indicates approximately how much database storage is required per user per day for Monitoring and Archiving data.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="bd912-254"><strong>CDR （监控）</strong></span><span class="sxs-lookup"><span data-stu-id="bd912-254"><strong>CDR (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="bd912-255"><strong>QoE （监控）</strong></span><span class="sxs-lookup"><span data-stu-id="bd912-255"><strong>QoE (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="bd912-256"><strong>存档</strong></span><span class="sxs-lookup"><span data-stu-id="bd912-256"><strong>Archiving</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd912-257">每个用户每天所需的磁盘空间</span><span class="sxs-lookup"><span data-stu-id="bd912-257">Disk space required per user per day</span></span></p></td>
<td><p><span data-ttu-id="bd912-258">49 KB</span><span class="sxs-lookup"><span data-stu-id="bd912-258">49 KB</span></span></p></td>
<td><p><span data-ttu-id="bd912-259">28 KB</span><span class="sxs-lookup"><span data-stu-id="bd912-259">28 KB</span></span></p></td>
<td><p><span data-ttu-id="bd912-260">57 KB</span><span class="sxs-lookup"><span data-stu-id="bd912-260">57 KB</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bd912-261">Microsoft 将下表中的硬件用于数据库服务器，以便在其性能测试期间进行监控和存档。</span><span class="sxs-lookup"><span data-stu-id="bd912-261">Microsoft used the hardware in the following table for the database server for Monitoring and Archiving during its performance testing.</span></span> <span data-ttu-id="bd912-262">测试收集了两个前端池的数据，其中每个都包含80000个用户。</span><span class="sxs-lookup"><span data-stu-id="bd912-262">The testing collected the data of two Front End pools, each of which contained 80,000 users.</span></span>

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a><span data-ttu-id="bd912-263">监控和存档性能测试中使用的硬件</span><span class="sxs-lookup"><span data-stu-id="bd912-263">Hardware Used in Monitoring and Archiving Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bd912-264">硬件组件</span><span class="sxs-lookup"><span data-stu-id="bd912-264">Hardware component</span></span></th>
<th><span data-ttu-id="bd912-265">建议</span><span class="sxs-lookup"><span data-stu-id="bd912-265">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd912-266">CPU</span><span class="sxs-lookup"><span data-stu-id="bd912-266">CPU</span></span></p></td>
<td><p><span data-ttu-id="bd912-267">64 位双处理器、六核、2.26 GHz 或更快</span><span class="sxs-lookup"><span data-stu-id="bd912-267">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd912-268">内存</span><span class="sxs-lookup"><span data-stu-id="bd912-268">Memory</span></span></p></td>
<td><p><span data-ttu-id="bd912-269">48千兆字节（GB）</span><span class="sxs-lookup"><span data-stu-id="bd912-269">48 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd912-270">磁盘</span><span class="sxs-lookup"><span data-stu-id="bd912-270">Disk</span></span></p></td>
<td><p><span data-ttu-id="bd912-271">每个磁盘上有 300 GB 的 25 10000-RPM 硬盘，使用以下配置</span><span class="sxs-lookup"><span data-stu-id="bd912-271">25 10,000-RPM hard disk drives with 300 GB on each disk, with the following configuration</span></span></p>
<h3 id="section-3"> </h3>
<div>
<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bd912-272"><strong>Drive</strong></span><span class="sxs-lookup"><span data-stu-id="bd912-272"><strong>Drive</strong></span></span></p></td>
<td><p><span data-ttu-id="bd912-273"><strong>RAID 配置</strong></span><span class="sxs-lookup"><span data-stu-id="bd912-273"><strong>RAID Configuration</strong></span></span></p></td>
<td><p><span data-ttu-id="bd912-274"><strong>磁盘数</strong></span><span class="sxs-lookup"><span data-stu-id="bd912-274"><strong>Number of disks</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd912-275">单个驱动器上的 CDR、QoE 和存档数据库数据文件</span><span class="sxs-lookup"><span data-stu-id="bd912-275">CDR, QoE, and Archiving database data files, on a single drive</span></span></p></td>
<td><p><span data-ttu-id="bd912-276">1 + 0</span><span class="sxs-lookup"><span data-stu-id="bd912-276">1+0</span></span></p></td>
<td><p><span data-ttu-id="bd912-277">16 </span><span class="sxs-lookup"><span data-stu-id="bd912-277">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd912-278">CDR 数据库日志文件</span><span class="sxs-lookup"><span data-stu-id="bd912-278">CDR database log file</span></span></p></td>
<td><p><span data-ttu-id="bd912-279">1</span><span class="sxs-lookup"><span data-stu-id="bd912-279">1</span></span></p></td>
<td><p><span data-ttu-id="bd912-280">双面</span><span class="sxs-lookup"><span data-stu-id="bd912-280">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd912-281">QoE 数据库日志文件</span><span class="sxs-lookup"><span data-stu-id="bd912-281">QoE database log file</span></span></p></td>
<td><p><span data-ttu-id="bd912-282">1</span><span class="sxs-lookup"><span data-stu-id="bd912-282">1</span></span></p></td>
<td><p><span data-ttu-id="bd912-283">双面</span><span class="sxs-lookup"><span data-stu-id="bd912-283">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bd912-284">存档数据库日志文件</span><span class="sxs-lookup"><span data-stu-id="bd912-284">Archiving database log file</span></span></p></td>
<td><p><span data-ttu-id="bd912-285">1</span><span class="sxs-lookup"><span data-stu-id="bd912-285">1</span></span></p></td>
<td><p><span data-ttu-id="bd912-286">双面</span><span class="sxs-lookup"><span data-stu-id="bd912-286">2</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bd912-287">网络</span><span class="sxs-lookup"><span data-stu-id="bd912-287">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="bd912-288">1 个双端口网络适配器，1 Gbps 或更高（建议为 2 Gbps，这要求与一个 MAC 地址和一个 IP 地址结合使用）</span><span class="sxs-lookup"><span data-stu-id="bd912-288">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="bd912-289">本部分内容</span><span class="sxs-lookup"><span data-stu-id="bd912-289">In This Section</span></span>

  - [<span data-ttu-id="bd912-290">估计 Lync Server 2013 的语音使用和流量</span><span class="sxs-lookup"><span data-stu-id="bd912-290">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="bd912-291">Lync Server 2013 中的中介服务器的部署指南</span><span class="sxs-lookup"><span data-stu-id="bd912-291">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

