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
ms.openlocfilehash: cd9b3861e4c84b8df7585ad5cfbdfd5a82359282
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736983"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="capacity-planning-for-lync-server-2013-using-the-user-models"></a><span data-ttu-id="c7a31-102">使用用户模型对 Lync Server 2013 进行容量规划</span><span class="sxs-lookup"><span data-stu-id="c7a31-102">Capacity planning for Lync Server 2013 using the user models</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c7a31-103">_**主题上次修改时间：** 2014-01-14_</span><span class="sxs-lookup"><span data-stu-id="c7a31-103">_**Topic Last Modified:** 2014-01-14_</span></span>

<span data-ttu-id="c7a31-104">本部分根据[Lync Server 2013 的用户模式](lync-server-2013-user-models.md)中所述的使用情况，为网站上的用户数提供了有关在网站上所需的服务器数的指南。</span><span class="sxs-lookup"><span data-stu-id="c7a31-104">This section provides guidance on how many servers you need at a site for the number of users at that site, according to the usage described in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<div>

## <a name="tested-hardware-platform"></a><span data-ttu-id="c7a31-105">受测试的硬件平台</span><span class="sxs-lookup"><span data-stu-id="c7a31-105">Tested Hardware Platform</span></span>

<span data-ttu-id="c7a31-106">本部分中的所有性能结果和部署建议都基于运行下表中所述硬件的服务器上的性能测试。</span><span class="sxs-lookup"><span data-stu-id="c7a31-106">All the performance results and deployment recommendations in this section are based on performance testing on servers running the hardware described in the following table.</span></span> <span data-ttu-id="c7a31-107">我们建议你使用类似的硬件。</span><span class="sxs-lookup"><span data-stu-id="c7a31-107">We recommend that you use similar hardware.</span></span> <span data-ttu-id="c7a31-108">如果使用性能不足的硬件，可能会遇到功能问题或性能下降。</span><span class="sxs-lookup"><span data-stu-id="c7a31-108">If you use less powerful hardware, you may experience functionality problems or poor performance.</span></span> <span data-ttu-id="c7a31-109">请注意，这些硬件建议高于以前版本的 Lync Server。</span><span class="sxs-lookup"><span data-stu-id="c7a31-109">Note that these hardware recommendations are higher than those of previous versions of Lync Server.</span></span>

### <a name="hardware-used-in-performance-testing"></a><span data-ttu-id="c7a31-110">性能测试中使用的硬件</span><span class="sxs-lookup"><span data-stu-id="c7a31-110">Hardware Used in Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7a31-111">硬件组件</span><span class="sxs-lookup"><span data-stu-id="c7a31-111">Hardware component</span></span></th>
<th><span data-ttu-id="c7a31-112">推荐</span><span class="sxs-lookup"><span data-stu-id="c7a31-112">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-113">CPU</span><span class="sxs-lookup"><span data-stu-id="c7a31-113">CPU</span></span></p></td>
<td><p><span data-ttu-id="c7a31-114">64 位双处理器、六核、2.26 GHz 或更快</span><span class="sxs-lookup"><span data-stu-id="c7a31-114">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p>
<p><span data-ttu-id="c7a31-115">Lync Server 服务器角色不支持英特尔安腾处理器。</span><span class="sxs-lookup"><span data-stu-id="c7a31-115">Intel Itanium processors are not supported for Lync Server server roles.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-116">内存</span><span class="sxs-lookup"><span data-stu-id="c7a31-116">Memory</span></span></p></td>
<td><p><span data-ttu-id="c7a31-117">32 GB</span><span class="sxs-lookup"><span data-stu-id="c7a31-117">32 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-118">磁盘</span><span class="sxs-lookup"><span data-stu-id="c7a31-118">Disk</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c7a31-119">8 个或 8 个以上具有至少 72 GB 可用磁盘空间的 10,000 RPM 硬盘驱动器。</span><span class="sxs-lookup"><span data-stu-id="c7a31-119">8 or more 10,000-RPM hard disk drives with at least 72 GB free disk space.</span></span></p>
<p><span data-ttu-id="c7a31-120">其中两个磁盘驱动器应使用 RAID 1，另外六个磁盘驱动器应使用 RAID 10。</span><span class="sxs-lookup"><span data-stu-id="c7a31-120">Two of the disks should use RAID 1, and six should use RAID 10.</span></span></p>
<p><span data-ttu-id="c7a31-121">-或</span><span class="sxs-lookup"><span data-stu-id="c7a31-121">- OR -</span></span></p></li>
<li><p><span data-ttu-id="c7a31-122">性能类似于 8 个 10,000 RPM 机械磁盘驱动器的固态驱动器 (SSD)</span><span class="sxs-lookup"><span data-stu-id="c7a31-122">Solid state drives (SSDs) which provide performance similar to 8 10,000-RPM mechanical disk drives.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-123">网络</span><span class="sxs-lookup"><span data-stu-id="c7a31-123">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c7a31-124">1 个双端口网络适配器，1 Gbps 或更高（建议为 2 Gbps，这要求与一个 MAC 地址和一个 IP 地址结合使用）</span><span class="sxs-lookup"><span data-stu-id="c7a31-124">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="summary-of-results"></a><span data-ttu-id="c7a31-125">结果摘要</span><span class="sxs-lookup"><span data-stu-id="c7a31-125">Summary of Results</span></span>

<span data-ttu-id="c7a31-126">下表总结了这些建议。</span><span class="sxs-lookup"><span data-stu-id="c7a31-126">The following table summarizes these recommendations.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7a31-127">服务器角色</span><span class="sxs-lookup"><span data-stu-id="c7a31-127">Server role</span></span></th>
<th><span data-ttu-id="c7a31-128">受支持的最大用户数</span><span class="sxs-lookup"><span data-stu-id="c7a31-128">Maximum number of users supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-129">带有十二个前端服务器和一台后端服务器的前端池，或一对后端服务器的镜像对。</span><span class="sxs-lookup"><span data-stu-id="c7a31-129">Front End pool with twelve Front End Servers and one Back End Server or a mirrored pair of Back End Servers.</span></span></p></td>
<td><p><span data-ttu-id="c7a31-130">80,000 个同时登录的唯一用户、表示非移动实例的 50% 多点登录 (MPOP) 以及为 Mobility 启用的 40% 的用户，共 152,000 个终结点。</span><span class="sxs-lookup"><span data-stu-id="c7a31-130">80,000 unique users simultaneously logged in, plus 50% multiple points of presence (MPOP) representing non-mobile instances, plus 40% of users enabled for Mobility for a total of 152,000 endpoints.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-131">A/V 会议</span><span class="sxs-lookup"><span data-stu-id="c7a31-131">A/V Conferencing</span></span></p></td>
<td><p><span data-ttu-id="c7a31-132">由前端池提供的 A/V 会议服务支持池中的会议，其会议最大为250用户，并且一次仅运行一个这样的大型会议。</span><span class="sxs-lookup"><span data-stu-id="c7a31-132">The A/V Conferencing service provided by a Front End pool supports the pool’s conferences assuming a maximum conference size of 250 users, and only one such large conference running at a time.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="c7a31-133">此外，你可以通过部署一个单独的前端池和两个前端服务器来支持250和1000用户之间的大型会议，从而托管大型会议。</span><span class="sxs-lookup"><span data-stu-id="c7a31-133">Additionally, you can support large conferences of between 250 and 1000 users by deploying a separate Front End pool with two Front End Servers to host the large conferences.</span></span> <span data-ttu-id="c7a31-134">有关详细信息，请参阅<A href="lync-server-2013-supporting-large-meetings.md">使用 Lync Server 2013 支持大型会议</A>。</span><span class="sxs-lookup"><span data-stu-id="c7a31-134">For details, see <A href="lync-server-2013-supporting-large-meetings.md">Supporting large meetings using Lync Server 2013</A>.</span></span>


</div></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-135">一台边缘服务器</span><span class="sxs-lookup"><span data-stu-id="c7a31-135">One Edge Server</span></span></p></td>
<td><p><span data-ttu-id="c7a31-136">12000并发远程用户</span><span class="sxs-lookup"><span data-stu-id="c7a31-136">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-137">一个控制器</span><span class="sxs-lookup"><span data-stu-id="c7a31-137">One Director</span></span></p></td>
<td><p><span data-ttu-id="c7a31-138">12000并发远程用户</span><span class="sxs-lookup"><span data-stu-id="c7a31-138">12,000 concurrent remote users</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-139">监控和存档</span><span class="sxs-lookup"><span data-stu-id="c7a31-139">Monitoring and Archiving</span></span></p></td>
<td><p><span data-ttu-id="c7a31-140">在 Lync Server 2013 中，监视和存档前端服务现在在每个前端服务器上运行，而不是在单独的服务器角色上运行。</span><span class="sxs-lookup"><span data-stu-id="c7a31-140">In Lync Server 2013, the Monitoring and Archiving front end services now run on each Front End Server, instead of on separate server roles.</span></span></p>
<p><span data-ttu-id="c7a31-141">监控和存档仍需要其自己各自的数据库存储。</span><span class="sxs-lookup"><span data-stu-id="c7a31-141">Monitoring and Archiving each still require their own database stores.</span></span> <span data-ttu-id="c7a31-142">如果您还运行 Exchange 2013，则可以在 Exchange 中保留存档数据，而不是在专用 SQL 数据库中。</span><span class="sxs-lookup"><span data-stu-id="c7a31-142">If you also run Exchange 2013, you can keep your Archiving data in Exchange, rather than in a dedicated SQL database.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-143">一个中介服务器</span><span class="sxs-lookup"><span data-stu-id="c7a31-143">One Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="c7a31-144">使用前端服务器的中介服务器 collocated 在池中的每个前端服务器上运行，并且应该为池中的用户提供足够的容量。</span><span class="sxs-lookup"><span data-stu-id="c7a31-144">Mediation Server collocated with Front End Server runs on every Front End Server in a pool, and should provide enough capacity for the users in the pool.</span></span> <span data-ttu-id="c7a31-145">对于独立的中介服务器，请参阅本主题后面的 "中介服务器" 一节。</span><span class="sxs-lookup"><span data-stu-id="c7a31-145">For stand-alone Mediation Server, see the “Mediation Server” section later in this topic.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-146">一个标准版服务器</span><span class="sxs-lookup"><span data-stu-id="c7a31-146">One Standard Edition server</span></span></p></td>
<td><p><span data-ttu-id="c7a31-147">我们强烈建议，如果您使用标准版服务器托管用户，则始终使用两台服务器，并使用在<a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Lync Server 2013 中规划高可用性和灾难恢复</a>的建议进行配对。</span><span class="sxs-lookup"><span data-stu-id="c7a31-147">We strongly recommend that if you use Standard Edition servers to host users, you always use two servers, paired using the recommendations in <a href="lync-server-2013-planning-for-high-availability-and-disaster-recovery.md">Planning for high availability and disaster recovery in Lync Server 2013</a>.</span></span> <span data-ttu-id="c7a31-148">服务器对中的每台服务器最多可承载 2,500 个用户，如果一台服务器出现故障，则另一台服务器在进行故障转移时可支持 5,000 个用户。</span><span class="sxs-lookup"><span data-stu-id="c7a31-148">Each server in the pair can host up to 2,500 users, and if one server fails the remaining server can support 5,000 users in a failover scenario.</span></span></p>
<p><span data-ttu-id="c7a31-149">如果您的部署包含大量音频或视频流量，当每台服务器用户数超过 2,500 个时，服务器性能可能下降。</span><span class="sxs-lookup"><span data-stu-id="c7a31-149">If your deployment includes a significant amount of audio or video traffic, server performance may suffer with more than 2,500 users per server.</span></span> <span data-ttu-id="c7a31-150">在这种情况下，应考虑添加更多标准版服务器或迁移到 Lync Server 企业版。</span><span class="sxs-lookup"><span data-stu-id="c7a31-150">In this case, you should consider adding more Standard Edition servers or moving to Lync Server Enterprise Edition.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-server"></a><span data-ttu-id="c7a31-151">前端服务器</span><span class="sxs-lookup"><span data-stu-id="c7a31-151">Front End Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7a31-152">此服务器角色不支持延伸池。</span><span class="sxs-lookup"><span data-stu-id="c7a31-152">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="c7a31-153">在前端池中，假设在池中的所有服务器上都启用了超线程，并且服务器硬件满足[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的建议，则可以为驻留在池中的每个6660用户安装一个前端服务器。</span><span class="sxs-lookup"><span data-stu-id="c7a31-153">In a Front End pool, you should have one Front End Server for every 6,660 users homed in the pool, assuming that hyper-threading is enabled on all servers in the pool, and that the server hardware meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span> <span data-ttu-id="c7a31-154">一个前端池中的最大用户数为80000，假设在池中的所有服务器上启用了超线程。</span><span class="sxs-lookup"><span data-stu-id="c7a31-154">The maximum number of users in one Front End pool is 80,000, assuming that hyper-threading is enabled on all the servers in the pool.</span></span> <span data-ttu-id="c7a31-155">如果网站上有超过80000的用户，则可以部署多个前端池。</span><span class="sxs-lookup"><span data-stu-id="c7a31-155">If you have more than 80,000 users at a site, you can deploy more than one Front End pool.</span></span>

<span data-ttu-id="c7a31-156">当你考虑前端池中的用户数时，请将驻留在 Survivable 分支装置和 Survivable 分支机构的用户包括在与此前端池关联的分支机构。</span><span class="sxs-lookup"><span data-stu-id="c7a31-156">When you account for the number of users in a Front End pool, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with this Front End pool.</span></span>

<span data-ttu-id="c7a31-157">活动服务器不可用时，其连接会自动转接给池中的其他服务器。</span><span class="sxs-lookup"><span data-stu-id="c7a31-157">When an active server is unavailable, its connections are transferred automatically to the other servers in the pool.</span></span> <span data-ttu-id="c7a31-158">例如，如果您有30000用户和5个前端服务器，则如果一台服务器不可用，则6000用户的连接需要转移到其他四台服务器。</span><span class="sxs-lookup"><span data-stu-id="c7a31-158">For example, if you have 30,000 users and five Front End Servers, then if one server is unavailable, the connections of 6000 users need to be transferred to the other four servers.</span></span> <span data-ttu-id="c7a31-159">其余四台服务器每个都有7500用户，这比推荐的数量更大。</span><span class="sxs-lookup"><span data-stu-id="c7a31-159">The remaining four servers will each have 7500 users, which is a larger number than recommended.</span></span>

<span data-ttu-id="c7a31-160">如果您已开始对30000用户使用6个前端服务器，随后一个服务器变为不可用，则共5000个用户将被移到其余的五台服务器。</span><span class="sxs-lookup"><span data-stu-id="c7a31-160">If instead you had started with six Front End Servers for your 30,000 users and subsequently one became unavailable, a total of 5000 users will be moved to the remaining five servers.</span></span> <span data-ttu-id="c7a31-161">这五台服务器将每台主机6000用户，该用户位于推荐的范围内。</span><span class="sxs-lookup"><span data-stu-id="c7a31-161">These five servers will each host 6000 users, which is in the recommended range.</span></span>

<span data-ttu-id="c7a31-162">前端池中的最大用户数是80000。</span><span class="sxs-lookup"><span data-stu-id="c7a31-162">The maximum number of users in a Front End pool is 80,000.</span></span> <span data-ttu-id="c7a31-163">池中的最大前端服务器数是12。</span><span class="sxs-lookup"><span data-stu-id="c7a31-163">The maximum number of Front End Servers in a pool is 12.</span></span>

<span data-ttu-id="c7a31-164">对于80000用户的前端池，在[Lync Server 2013 中遵循用户模型](lync-server-2013-user-models.md)的典型部署中，12前端服务器的性能就足够了。</span><span class="sxs-lookup"><span data-stu-id="c7a31-164">For a Front End pool with 80,000 users, twelve Front End Servers is sufficient for performance, in typical deployments that follow the [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span> <span data-ttu-id="c7a31-165">为支持灾难恢复故障转移而设计的部署假设最多可以在两个配对的前端池中托管每个用户，其中每个池都有足够40000的前端服务器以容纳两个池中的用户，因此一个池需要失败转移到另一个。</span><span class="sxs-lookup"><span data-stu-id="c7a31-165">Deployments designed to support disaster recovery failover assume that a maximum of 40,000 users can be hosted in each of two paired Front End pools, in which each pool has enough Front End Servers to accommodate the users in both pools should one pool need to be failed over to the other.</span></span>

<span data-ttu-id="c7a31-166">由于以下原因，特定前端池支持的具有良好性能的用户数可能与这些数字不同：</span><span class="sxs-lookup"><span data-stu-id="c7a31-166">The number of users supported with good performance by a particular Front End pool may differ from these numbers for the following reasons:</span></span>

  - <span data-ttu-id="c7a31-167">前端服务器的硬件不符合[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的建议。</span><span class="sxs-lookup"><span data-stu-id="c7a31-167">The hardware for your Front End Servers does not meet the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

  - <span data-ttu-id="c7a31-168">你的组织的使用情况与用户模型显著不同，如更大的会议流量。</span><span class="sxs-lookup"><span data-stu-id="c7a31-168">Your organization’s usage differs significantly from the user models, such as significantly more conferencing traffic.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c7a31-169">在 Lync Server 2013 中，状态数据库现在托管在前端服务器上，而不是在 Lync Server 2010 中托管在后端服务器上。</span><span class="sxs-lookup"><span data-stu-id="c7a31-169">In Lync Server 2013, the presence databases are now hosted on Front End Servers, unlike in Lync Server 2010 where they were hosted on the Back End Server.</span></span> <span data-ttu-id="c7a31-170">这意味着，无论前端服务器托管的用户数如何，你的前端服务器的磁盘性能和容量不应受到本部分前面列出的建议以及<A href="lync-server-2013-server-hardware-platforms.md">Lync server 2013 的服务器硬件平台</A>中列出的建议。</span><span class="sxs-lookup"><span data-stu-id="c7a31-170">This means that the disk performance and capacity of your Front End Servers should not be compromised from the recommendations listed earlier in this section and in <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A>, regardless of the number of users hosted by your Front End Servers.</span></span>



</div>

<span data-ttu-id="c7a31-171">下表显示了根据用户模型（在[Lync Server 2013 中的用户](lync-server-2013-user-models.md)模型中定义）提供的 IM 和状态的平均带宽。</span><span class="sxs-lookup"><span data-stu-id="c7a31-171">The following table shows the average bandwidth for IM and presence, given the user model, as defined in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7a31-172">每个用户的平均带宽</span><span class="sxs-lookup"><span data-stu-id="c7a31-172">Average bandwidth per user</span></span></th>
<th><span data-ttu-id="c7a31-173">每个具有6660用户的前端服务器的带宽要求</span><span class="sxs-lookup"><span data-stu-id="c7a31-173">Bandwidth requirements per Front End Server with 6,660 users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-174">1.3 Kpbs</span><span class="sxs-lookup"><span data-stu-id="c7a31-174">1.3 Kpbs</span></span></p></td>
<td><p><span data-ttu-id="c7a31-175">13 Mbps</span><span class="sxs-lookup"><span data-stu-id="c7a31-175">13 Mbps</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c7a31-176">若要提高前端服务器上归置的 A/V 式会议和中介服务器功能的媒体性能，应在前端服务器上的网络适配器上启用接收端缩放（RSS）。</span><span class="sxs-lookup"><span data-stu-id="c7a31-176">To improve the media performance of the co-located A/V Conferencing and Mediation Server functionality on your Front End Servers, you should enable receive-side scaling (RSS) on the network adapters on your Front End Servers.</span></span> <span data-ttu-id="c7a31-177">通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。</span><span class="sxs-lookup"><span data-stu-id="c7a31-177">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="c7a31-178">有关详细信息，请参阅中的 "Windows Server 2008 中的接收端<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>缩放增强功能"。</span><span class="sxs-lookup"><span data-stu-id="c7a31-178">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="c7a31-179">有关如何启用 RSS 的详细信息，请参阅网络适配器文档。</span><span class="sxs-lookup"><span data-stu-id="c7a31-179">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="conferencing-maximums"></a><span data-ttu-id="c7a31-180">会议最大值</span><span class="sxs-lookup"><span data-stu-id="c7a31-180">Conferencing Maximums</span></span>

<span data-ttu-id="c7a31-181">如果用户模型中有5% 的用户在一次会议中可能处于会议中，则80000用户一次可以在会议中拥有4000用户。</span><span class="sxs-lookup"><span data-stu-id="c7a31-181">Given the user model that 5% of users in a pool may be in a conference at any one time, a pool of 80,000 users could have about 4,000 users in conferences at one time.</span></span> <span data-ttu-id="c7a31-182">这些会议可能混合多种媒体（如一些仅含 IM、一些含有 IM 和音频、一些含有音频/视频）并拥有大量参与者。</span><span class="sxs-lookup"><span data-stu-id="c7a31-182">These conferences are expected to be a mix of media (some IM-only, some IM with audio, some audio/video, for example) and number of participants.</span></span> <span data-ttu-id="c7a31-183">实际使用的会议数没有硬性限制，实际使用情况确定实际性能。</span><span class="sxs-lookup"><span data-stu-id="c7a31-183">There is no hard limit for the actual number of conferences allowed, and actual usage determines the actual performance.</span></span> <span data-ttu-id="c7a31-184">例如，如果您的组织具有的混合模式会议的数量比用户模型中假定的多，则您可能需要部署更多的前端服务器或 A/V 会议服务器，而不是本文档中的建议。</span><span class="sxs-lookup"><span data-stu-id="c7a31-184">For example, if your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers or A/V Conferencing Servers than the recommendations in this document.</span></span> <span data-ttu-id="c7a31-185">有关用户模型中的假设的详细信息，请参阅[Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)。</span><span class="sxs-lookup"><span data-stu-id="c7a31-185">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="c7a31-186">由常规 Lync Server 2013 前端池托管的最大受支持的会议大小也是250参与者。</span><span class="sxs-lookup"><span data-stu-id="c7a31-186">The maximum supported conference size hosted by a regular Lync Server 2013 Front End pool which also hosts users is 250 participants.</span></span> <span data-ttu-id="c7a31-187">在进行拥有 250 个用户的会议时，该池同时还可支持其他会议，从而使总数为 5% 的池用户参加并发会议。</span><span class="sxs-lookup"><span data-stu-id="c7a31-187">While a 250-user conference is happening, the pool still supports other conferences as well, such that a total of 5% of pool users are in concurrent conferences.</span></span> <span data-ttu-id="c7a31-188">例如，在一个由十二个前端服务器和80000用户组成的池中，当 250-用户的会议发生时，Lync Server 支持3750其他参与小型会议的用户。</span><span class="sxs-lookup"><span data-stu-id="c7a31-188">For example, in a pool of twelve Front End Servers and 80,000 users, while the 250-user conference is happening, Lync Server supports 3,750 other users participating in smaller conferences.</span></span>

<span data-ttu-id="c7a31-189">无论驻留在前端池或标准版服务器上的用户数如何，Lync Server 至少支持125在托管250用户会议的同一池或服务器上参与小型会议的其他用户。</span><span class="sxs-lookup"><span data-stu-id="c7a31-189">Regardless of the number of users homed on the Front End pool or Standard Edition server, Lync Server supports a minimum of 125 other users participating in smaller conferences on the same pool or server which is hosting a 250-user conference.</span></span>

<span data-ttu-id="c7a31-190">若要启用与250和1000用户之间的会议，您可以设置单独的前端池，只需托管这些会议。</span><span class="sxs-lookup"><span data-stu-id="c7a31-190">To enable conferences with between 250 and 1000 users, you can set up a separate Front End pool just to host those conferences.</span></span> <span data-ttu-id="c7a31-191">此前端池不会托管任何用户。</span><span class="sxs-lookup"><span data-stu-id="c7a31-191">This Front End pool will not host any users.</span></span> <span data-ttu-id="c7a31-192">有关详细信息，请参阅[使用 Lync Server 2013 支持大型会议](lync-server-2013-supporting-large-meetings.md)。</span><span class="sxs-lookup"><span data-stu-id="c7a31-192">For details, see [Supporting large meetings using Lync Server 2013](lync-server-2013-supporting-large-meetings.md).</span></span>

<span data-ttu-id="c7a31-193">如果您的组织具有的混合模式会议的数量比用户模型中假定的多，则您可能需要部署比本文档中的建议更多的前端服务器（最大限制为 12 FEs）。</span><span class="sxs-lookup"><span data-stu-id="c7a31-193">If your organization has many more mixed-mode conferences than are assumed in the user model, you might need to deploy more Front End Servers than the recommendations in this document (up to a limit of 12 FEs).</span></span> <span data-ttu-id="c7a31-194">有关用户模型中的假设的详细信息，请参阅[Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)。</span><span class="sxs-lookup"><span data-stu-id="c7a31-194">For details about the assumptions in the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

</div>

<div>

## <a name="edge-server"></a><span data-ttu-id="c7a31-195">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="c7a31-195">Edge Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7a31-196">此服务器角色不支持延伸池。</span><span class="sxs-lookup"><span data-stu-id="c7a31-196">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="c7a31-197">你应该为将同时访问网站的每个12000远程用户部署一个 Edge 服务器。</span><span class="sxs-lookup"><span data-stu-id="c7a31-197">You should deploy one Edge Server for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="c7a31-198">至少我们建议使用两个边缘服务器来实现高可用性。</span><span class="sxs-lookup"><span data-stu-id="c7a31-198">At a minimum we recommend two Edge Servers for high availability.</span></span> <span data-ttu-id="c7a31-199">这些建议假定你的 Edge 服务器的硬件满足[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的建议。</span><span class="sxs-lookup"><span data-stu-id="c7a31-199">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="c7a31-200">当你考虑 Edge 服务器的用户数时，请将驻留在 Survivable 分支装置和 Survivable 分支机构的用户包括在与此站点上的前端池关联的分支机构。</span><span class="sxs-lookup"><span data-stu-id="c7a31-200">When you account for the number of users for the Edge Servers, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7a31-201">若要提高边缘服务器上的 A/V 会议边缘服务的性能，应在边缘服务器上的网络适配器上启用接收端缩放（RSS）。</span><span class="sxs-lookup"><span data-stu-id="c7a31-201">To improve the performance of the A/V Conferencing Edge service on your Edge Servers, you should enable receive-side scaling (RSS) on the network adapters on your Edge Servers.</span></span> <span data-ttu-id="c7a31-202">通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。</span><span class="sxs-lookup"><span data-stu-id="c7a31-202">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="c7a31-203">有关详细信息，请参阅中的 "Windows Server 2008 中的接收端<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>缩放增强功能"。</span><span class="sxs-lookup"><span data-stu-id="c7a31-203">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="c7a31-204">有关如何启用 RSS 的详细信息，请参阅网络适配器文档。</span><span class="sxs-lookup"><span data-stu-id="c7a31-204">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="director"></a><span data-ttu-id="c7a31-205">控制器</span><span class="sxs-lookup"><span data-stu-id="c7a31-205">Director</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7a31-206">此服务器角色不支持延伸池。</span><span class="sxs-lookup"><span data-stu-id="c7a31-206">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="c7a31-207">如果你部署 Director 服务器角色，建议你为将同时访问网站的每个12000远程用户部署一个 Director。</span><span class="sxs-lookup"><span data-stu-id="c7a31-207">If you deploy the Director server role we recommend that you deploy one Director for every 12,000 remote users who will access a site concurrently.</span></span> <span data-ttu-id="c7a31-208">至少我们建议使用两个控制器来实现高可用性。</span><span class="sxs-lookup"><span data-stu-id="c7a31-208">At a minimum we recommend two Directors for high availability.</span></span> <span data-ttu-id="c7a31-209">这些建议假定你的 Edge 服务器的硬件满足[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中的建议。</span><span class="sxs-lookup"><span data-stu-id="c7a31-209">These recommendations assume that the hardware for your Edge Servers meets the recommendations in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="c7a31-210">当你考虑控制器的用户数时，请将驻留在 Survivable 分支机构和 Survivable 分支机构的用户包括在与此站点上的前端池关联的分支机构。</span><span class="sxs-lookup"><span data-stu-id="c7a31-210">When you account for the number of users for the Directors, include the users homed on Survivable Branch Appliances and Survivable Branch Servers at branch offices that are associated with a Front End pool at this site.</span></span>

</div>

<div>

## <a name="mediation-server"></a><span data-ttu-id="c7a31-211">中介服务器</span><span class="sxs-lookup"><span data-stu-id="c7a31-211">Mediation Server</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c7a31-212">此服务器角色不支持延伸池。</span><span class="sxs-lookup"><span data-stu-id="c7a31-212">Stretched pools are not supported for this server role.</span></span>



</div>

<span data-ttu-id="c7a31-213">如果您 collocate 中介服务器与前端服务器，则中介服务器在池中的每个前端服务器上运行，并且应该为池中的用户提供足够的容量。</span><span class="sxs-lookup"><span data-stu-id="c7a31-213">If you collocate Mediation Server with Front End Server, Mediation Server runs on every Front End Server in the pool, and should provide enough capacity for the users in the pool.</span></span>

<span data-ttu-id="c7a31-214">如果你部署独立的中介服务器池，则要部署多少个中介服务器取决于多个因素，包括用于中介服务器的硬件、你拥有的 VoIP 用户数、每个中介服务器池的网关对等数量控件、通过这些网关的繁忙工时流量以及绕过中介服务器的媒体的通话百分比。</span><span class="sxs-lookup"><span data-stu-id="c7a31-214">If you deploy a stand-alone Mediation Server pool, then how many Mediation Servers to deploy depends on many factors, including the hardware used for Mediation Server, the number of VoIP users you have, the number of gateway peers that each Mediation Server pool controls, the busy hour traffic through those gateways, and the percentage of calls with media that bypasses the Mediation Server.</span></span>

<span data-ttu-id="c7a31-215">下表提供了一种指导，即中介服务器可以处理的并发调用数（假定中介服务器的硬件满足[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)要求），并且启用了超线程。</span><span class="sxs-lookup"><span data-stu-id="c7a31-215">The following tables provide a guideline for how many concurrent calls a Mediation Server can handle, assuming that the hardware for the Mediation Servers meets the requirements in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md) and that hyper-threading is enabled.</span></span> <span data-ttu-id="c7a31-216">有关中介服务器可伸缩性的详细信息，请参阅在 Lync server 2013 中[估计 lync server 2013 的语音使用情况和流量](lync-server-2013-estimating-voice-usage-and-traffic.md)以及[中介服务器的部署指南](lync-server-2013-deployment-guidelines-for-mediation-server.md)。</span><span class="sxs-lookup"><span data-stu-id="c7a31-216">For details about Mediation Server scalability, see [Estimating voice usage and traffic for Lync Server 2013](lync-server-2013-estimating-voice-usage-and-traffic.md) and [Deployment guidelines for Mediation Server in Lync Server 2013](lync-server-2013-deployment-guidelines-for-mediation-server.md).</span></span>

<span data-ttu-id="c7a31-217">下表假设使用的是[Lync Server 2013 中的用户模型](lync-server-2013-user-models.md)中汇总的用法。</span><span class="sxs-lookup"><span data-stu-id="c7a31-217">All the following tables assume usage as summarized in [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

### <a name="stand-alone-mediation-server-capacity-70-internal-users-30-external-users-with-non-bypass-call-capacity-media-transcoding-performed-by-mediation-server"></a><span data-ttu-id="c7a31-218">独立中介服务器容量：70% 内部用户，具有非绕过呼叫容量的30% 外部用户（由中介服务器执行的媒体转码）</span><span class="sxs-lookup"><span data-stu-id="c7a31-218">Stand-alone Mediation Server Capacity: 70% Internal Users, 30% External users with non-bypass call capacity (media transcoding performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7a31-219">服务器硬件</span><span class="sxs-lookup"><span data-stu-id="c7a31-219">Server hardware</span></span></th>
<th><span data-ttu-id="c7a31-220">最大呼叫数</span><span class="sxs-lookup"><span data-stu-id="c7a31-220">Maximum number of calls</span></span></th>
<th><span data-ttu-id="c7a31-221">最大 T1 线路数</span><span class="sxs-lookup"><span data-stu-id="c7a31-221">Maximum number of T1 lines</span></span></th>
<th><span data-ttu-id="c7a31-222">最大 E1 线路数</span><span class="sxs-lookup"><span data-stu-id="c7a31-222">Maximum number of E1 lines</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-223">双处理器，十六核，<strong>禁用超线程的</strong> 2.26 GHz 超线程 CPU，带 32 GB 内存和 1 个双端口网络适配器卡。</span><span class="sxs-lookup"><span data-stu-id="c7a31-223">Dual processor, hex core, 2.26 GHz hyper-threaded CPU <strong>with hyper-threading disabled</strong>, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="c7a31-224">1100</span><span class="sxs-lookup"><span data-stu-id="c7a31-224">1100</span></span></p></td>
<td><p><span data-ttu-id="c7a31-225">46</span><span class="sxs-lookup"><span data-stu-id="c7a31-225">46</span></span></p></td>
<td><p><span data-ttu-id="c7a31-226">35</span><span class="sxs-lookup"><span data-stu-id="c7a31-226">35</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-227">双处理器，十六核，2.26 GHz 超线程 CPU，带 32 GB 内存和 1 个双端口网络适配器卡。</span><span class="sxs-lookup"><span data-stu-id="c7a31-227">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and one dual-port network adapter card.</span></span></p></td>
<td><p><span data-ttu-id="c7a31-228">1500</span><span class="sxs-lookup"><span data-stu-id="c7a31-228">1500</span></span></p></td>
<td><p><span data-ttu-id="c7a31-229">63</span><span class="sxs-lookup"><span data-stu-id="c7a31-229">63</span></span></p></td>
<td><p><span data-ttu-id="c7a31-230">47</span><span class="sxs-lookup"><span data-stu-id="c7a31-230">47</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c7a31-231">尽管使用 32 GB 内存的服务器用于性能测试，但具有 16 GB 内存的服务器对于独立的中介服务器受支持，并且足以提供此表中所示的性能。</span><span class="sxs-lookup"><span data-stu-id="c7a31-231">Although servers with 32 GB of memory were used for performance testing, servers with 16 GB of memory are supported for stand-alone Mediation Server, and are sufficient to provide the performance shown in this table.</span></span>



</div>

### <a name="mediation-server-capacity-mediation-server-collocated-with-front-end-server-70-internal-users-30-external-users-non-bypass-call-capacity-media-processing-performed-by-mediation-server"></a><span data-ttu-id="c7a31-232">中介服务器容量（中介服务器 Collocated 前端服务器）70% 内部用户、30% 外部用户、非绕过呼叫容量（由中介服务器执行的媒体处理）</span><span class="sxs-lookup"><span data-stu-id="c7a31-232">Mediation Server Capacity (Mediation Server Collocated with Front End Server) 70% Internal Users, 30% External Users, Non-Bypass Call Capacity (Media Processing Performed by Mediation Server)</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7a31-233">服务器硬件</span><span class="sxs-lookup"><span data-stu-id="c7a31-233">Server hardware</span></span></th>
<th><span data-ttu-id="c7a31-234">最大呼叫数</span><span class="sxs-lookup"><span data-stu-id="c7a31-234">Maximum number of calls</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-235">双处理器，十六核，2.26 GHz 超线程 CPU，带 32 GB 内存和 2 个 1GB 网络适配器卡。</span><span class="sxs-lookup"><span data-stu-id="c7a31-235">Dual processor, hex core, 2.26 GHz hyper-threaded CPU, with 32 GB memory and 2 1GB network adapter cards.</span></span></p></td>
<td><p><span data-ttu-id="c7a31-236">150</span><span class="sxs-lookup"><span data-stu-id="c7a31-236">150</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="c7a31-237">此数字比独立中介服务器的编号小得多，因为前端服务器除了语音通话所需的转换代码外，还必须处理其他6600用户的功能和功能。</span><span class="sxs-lookup"><span data-stu-id="c7a31-237">This number is much smaller than the numbers for the stand-alone Mediation Server because the Front End Server has to handle other features and functions for the 6600 users homed on it, in addition to the transcoding needed for voice calls.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c7a31-238">若要提高中介服务器的性能，应在中介服务器上的网络适配器上启用接收端缩放（RSS）。</span><span class="sxs-lookup"><span data-stu-id="c7a31-238">To improve the performance of the Mediation Server, you should enable receive-side scaling (RSS) on the network adapters on your Mediation Servers.</span></span> <span data-ttu-id="c7a31-239">通过启用 RSS，服务器上的多个处理器能够以并行方式处理传入数据包。</span><span class="sxs-lookup"><span data-stu-id="c7a31-239">RSS enables incoming packets to be handled in parallel by multiple processors on the server.</span></span> <span data-ttu-id="c7a31-240">有关详细信息，请参阅中的 "Windows Server 2008 中的接收端<A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>缩放增强功能"。</span><span class="sxs-lookup"><span data-stu-id="c7a31-240">For details, see "Receive-Side Scaling Enhancements in Windows Server 2008" at <A href="http://go.microsoft.com/fwlink/p/?linkid=268731">http://go.microsoft.com/fwlink/p/?linkId=268731</A>.</span></span> <span data-ttu-id="c7a31-241">有关如何启用 RSS 的详细信息，请参阅网络适配器文档。</span><span class="sxs-lookup"><span data-stu-id="c7a31-241">For details about how to enable RSS, see your network adapter documentation.</span></span>



</div>

</div>

<div>

## <a name="back-end-server"></a><span data-ttu-id="c7a31-242">后端服务器</span><span class="sxs-lookup"><span data-stu-id="c7a31-242">Back End Server</span></span>

<span data-ttu-id="c7a31-243">在 Lync Server 2013 中，状态数据库位于前端服务器上，而不是在后端服务器上。</span><span class="sxs-lookup"><span data-stu-id="c7a31-243">In Lync Server 2013, the presence databases are located on the Front End Servers instead of the Back End Server.</span></span> <span data-ttu-id="c7a31-244">这使得 Lync Server 2013 中的每台后端服务器的要求比前端服务器的硬件要求更简单。</span><span class="sxs-lookup"><span data-stu-id="c7a31-244">This has resulted in a much simpler requirement for each Back End Server in Lync Server 2013, equivalent to the hardware requirement for the Front End Server.</span></span> <span data-ttu-id="c7a31-245">将其与 Lync Server 2010 进行比较，在这种情况下，需要将后端服务器用作高达25个磁盘的服务器级别。</span><span class="sxs-lookup"><span data-stu-id="c7a31-245">Contrast this to Lync Server 2010, where the Back End Server was required to be a much higher grade server with 25 disks.</span></span> <span data-ttu-id="c7a31-246">但是，后端服务器的工作负荷仍使您不能满足本部分和[Lync server 2013 的服务器硬件平台](lync-server-2013-server-hardware-platforms.md)中列出的硬件建议。</span><span class="sxs-lookup"><span data-stu-id="c7a31-246">However, the workload of Back End Servers is still such that you should not fail to meet the hardware recommendations listed earlier in this section and in [Server hardware platforms for Lync Server 2013](lync-server-2013-server-hardware-platforms.md).</span></span>

<span data-ttu-id="c7a31-247">为了提供您的后端服务器的高可用性，我们建议部署服务器镜像。</span><span class="sxs-lookup"><span data-stu-id="c7a31-247">To provide high availability of your Back End Server, we recommend deploying server mirroring.</span></span> <span data-ttu-id="c7a31-248">有关详细信息，请参阅[Lync server 2013 中的后端服务器高可用性](lync-server-2013-back-end-server-high-availability.md)。</span><span class="sxs-lookup"><span data-stu-id="c7a31-248">For more information, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span>

</div>

<div>

## <a name="monitoring-and-archiving"></a><span data-ttu-id="c7a31-249">监控和存档</span><span class="sxs-lookup"><span data-stu-id="c7a31-249">Monitoring and Archiving</span></span>

<span data-ttu-id="c7a31-250">在 Lync Server 2013 中，如果你部署监视或存档，这些服务的前端功能将在前端服务器上运行，而不是在单独的服务器角色上运行。</span><span class="sxs-lookup"><span data-stu-id="c7a31-250">In Lync Server 2013, if you deploy Monitoring or Archiving, the front end functionality of these services runs on the Front End Servers, instead of on separate server roles.</span></span> <span data-ttu-id="c7a31-251">监视和存档每个仍使用其自己的数据库存储，与后端存储分开。</span><span class="sxs-lookup"><span data-stu-id="c7a31-251">Monitoring and Archiving each still use their own database store, separate from the Back End store.</span></span> <span data-ttu-id="c7a31-252">或者，如果已部署 Exchange 2013，则可以在 Exchange 中（而不是在专用的 SQL 应用商店中）存储即时消息存档数据。</span><span class="sxs-lookup"><span data-stu-id="c7a31-252">Alternatively, if you have Exchange 2013 deployed, you can store instant message Archiving data in Exchange instead of in a dedicated SQL store.</span></span>

<span data-ttu-id="c7a31-253">下表说明了每个用户每天监控和存档数据所需的数据库存储的大致数量。</span><span class="sxs-lookup"><span data-stu-id="c7a31-253">The following table indicates approximately how much database storage is required per user per day for Monitoring and Archiving data.</span></span>


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
<td><p><span data-ttu-id="c7a31-254"><strong>CDR（监控）</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-254"><strong>CDR (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-255"><strong>QoE（监控）</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-255"><strong>QoE (Monitoring)</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-256"><strong>存档</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-256"><strong>Archiving</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-257">每个用户每天所需的磁盘空间</span><span class="sxs-lookup"><span data-stu-id="c7a31-257">Disk space required per user per day</span></span></p></td>
<td><p><span data-ttu-id="c7a31-258">49 KB</span><span class="sxs-lookup"><span data-stu-id="c7a31-258">49 KB</span></span></p></td>
<td><p><span data-ttu-id="c7a31-259">28 KB</span><span class="sxs-lookup"><span data-stu-id="c7a31-259">28 KB</span></span></p></td>
<td><p><span data-ttu-id="c7a31-260">57 KB</span><span class="sxs-lookup"><span data-stu-id="c7a31-260">57 KB</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c7a31-261">Microsoft 在其性能测试期间对用于监控和存档的数据库服务器使用了下表中的硬件。</span><span class="sxs-lookup"><span data-stu-id="c7a31-261">Microsoft used the hardware in the following table for the database server for Monitoring and Archiving during its performance testing.</span></span> <span data-ttu-id="c7a31-262">测试收集了两个前端池的数据，每个池包含80000用户。</span><span class="sxs-lookup"><span data-stu-id="c7a31-262">The testing collected the data of two Front End pools, each of which contained 80,000 users.</span></span>

### <a name="hardware-used-in-monitoring-and-archiving-performance-testing"></a><span data-ttu-id="c7a31-263">监控和存档性能测试中使用的硬件</span><span class="sxs-lookup"><span data-stu-id="c7a31-263">Hardware Used in Monitoring and Archiving Performance Testing</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c7a31-264">硬件组件</span><span class="sxs-lookup"><span data-stu-id="c7a31-264">Hardware component</span></span></th>
<th><span data-ttu-id="c7a31-265">推荐</span><span class="sxs-lookup"><span data-stu-id="c7a31-265">Recommended</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-266">CPU</span><span class="sxs-lookup"><span data-stu-id="c7a31-266">CPU</span></span></p></td>
<td><p><span data-ttu-id="c7a31-267">64 位双处理器、六核、2.26 GHz 或更快</span><span class="sxs-lookup"><span data-stu-id="c7a31-267">64-bit dual processor, hex-core, 2.26 gigahertz (GHz) or higher</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-268">内存</span><span class="sxs-lookup"><span data-stu-id="c7a31-268">Memory</span></span></p></td>
<td><p><span data-ttu-id="c7a31-269">48 GB</span><span class="sxs-lookup"><span data-stu-id="c7a31-269">48 gigabytes (GB)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-270">磁盘</span><span class="sxs-lookup"><span data-stu-id="c7a31-270">Disk</span></span></p></td>
<td><p><span data-ttu-id="c7a31-271">25 个 10,000 RPM 硬盘驱动器，每个磁盘具有 300 GB 的内存，配置如下</span><span class="sxs-lookup"><span data-stu-id="c7a31-271">25 10,000-RPM hard disk drives with 300 GB on each disk, with the following configuration</span></span></p>
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
<td><p><span data-ttu-id="c7a31-272"><strong>驱动器</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-272"><strong>Drive</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-273"><strong>RAID 配置</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-273"><strong>RAID Configuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c7a31-274"><strong>磁盘数</strong></span><span class="sxs-lookup"><span data-stu-id="c7a31-274"><strong>Number of disks</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-275">单个驱动器上的 CDR、QoE 和存档数据库数据文件</span><span class="sxs-lookup"><span data-stu-id="c7a31-275">CDR, QoE, and Archiving database data files, on a single drive</span></span></p></td>
<td><p><span data-ttu-id="c7a31-276">1+0</span><span class="sxs-lookup"><span data-stu-id="c7a31-276">1+0</span></span></p></td>
<td><p><span data-ttu-id="c7a31-277">utf-16</span><span class="sxs-lookup"><span data-stu-id="c7a31-277">16</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-278">CDR 数据库日志文件</span><span class="sxs-lookup"><span data-stu-id="c7a31-278">CDR database log file</span></span></p></td>
<td><p><span data-ttu-id="c7a31-279">1</span><span class="sxs-lookup"><span data-stu-id="c7a31-279">1</span></span></p></td>
<td><p><span data-ttu-id="c7a31-280">ppls-2</span><span class="sxs-lookup"><span data-stu-id="c7a31-280">2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-281">QoE 数据库日志文件</span><span class="sxs-lookup"><span data-stu-id="c7a31-281">QoE database log file</span></span></p></td>
<td><p><span data-ttu-id="c7a31-282">1</span><span class="sxs-lookup"><span data-stu-id="c7a31-282">1</span></span></p></td>
<td><p><span data-ttu-id="c7a31-283">ppls-2</span><span class="sxs-lookup"><span data-stu-id="c7a31-283">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c7a31-284">存档数据库日志文件</span><span class="sxs-lookup"><span data-stu-id="c7a31-284">Archiving database log file</span></span></p></td>
<td><p><span data-ttu-id="c7a31-285">1</span><span class="sxs-lookup"><span data-stu-id="c7a31-285">1</span></span></p></td>
<td><p><span data-ttu-id="c7a31-286">ppls-2</span><span class="sxs-lookup"><span data-stu-id="c7a31-286">2</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c7a31-287">网络</span><span class="sxs-lookup"><span data-stu-id="c7a31-287">Network</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="c7a31-288">1 个双端口网络适配器，1 Gbps 或更高（建议为 2 Gbps，这要求与一个 MAC 地址和一个 IP 地址结合使用）</span><span class="sxs-lookup"><span data-stu-id="c7a31-288">1 dual-port network adapter, 1 Gbps or higher (2 recommended, which requires teaming with a single MAC address and single IP address)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c7a31-289">本节内容</span><span class="sxs-lookup"><span data-stu-id="c7a31-289">In This Section</span></span>

  - [<span data-ttu-id="c7a31-290">估计 Lync Server 2013 的语音使用和流量</span><span class="sxs-lookup"><span data-stu-id="c7a31-290">Estimating voice usage and traffic for Lync Server 2013</span></span>](lync-server-2013-estimating-voice-usage-and-traffic.md)

  - [<span data-ttu-id="c7a31-291">Lync Server 2013 中的中介服务器部署指南</span><span class="sxs-lookup"><span data-stu-id="c7a31-291">Deployment guidelines for Mediation Server in Lync Server 2013</span></span>](lync-server-2013-deployment-guidelines-for-mediation-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

