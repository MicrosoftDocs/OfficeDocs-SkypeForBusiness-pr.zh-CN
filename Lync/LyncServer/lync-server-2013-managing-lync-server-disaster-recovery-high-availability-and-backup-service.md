---
title: 管理 Lync Server 灾难恢复、高可用性和备份服务
description: 管理 Lync Server 灾难恢复、高可用性和备份服务。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Lync Server disaster recovery, high availability, and Backup Service
ms:assetid: f4cd36fb-ffd6-48fa-b761-e11b3bcff91a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721939(v=OCS.15)
ms:contentKeyID: 49733876
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e440c8c72ab5e66d27a86dfce963368dff804bc
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569408"
---
# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="e01b1-103">管理 Lync Server 2013 灾难恢复、高可用性和备份服务</span><span class="sxs-lookup"><span data-stu-id="e01b1-103">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e01b1-104">_**上次修改的主题：** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="e01b1-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="e01b1-105">本节包含灾难恢复操作以及维护同步配对前端池中数据的备份服务的过程。</span><span class="sxs-lookup"><span data-stu-id="e01b1-105">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="e01b1-p101">灾难恢复过程（故障转移和故障回复）都是手动的操作。如果出现灾难，管理员必须手动调用故障转移过程。在修复池之后，此规则同样适用于故障回复。</span><span class="sxs-lookup"><span data-stu-id="e01b1-p101">Disaster recovery procedures, both failover and failback, are manual. If there is a disaster, the administrator must manually invoke the failover procedures. The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="e01b1-109">本节其余部分中的灾难恢复过程假定以下内容：</span><span class="sxs-lookup"><span data-stu-id="e01b1-109">The disaster recovery procedures in the rest of this section assume the following:</span></span>

  - <span data-ttu-id="e01b1-110">您有一个具有成对前端池的部署，这些池位于不同的站点中，如在 [Lync Server 2013 中规划高可用性和灾难恢复中](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)所述。</span><span class="sxs-lookup"><span data-stu-id="e01b1-110">You have a deployment with paired Front End pools, located in different sites, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="e01b1-111">这些配对池中一直运行备份服务，以使其保持同步。</span><span class="sxs-lookup"><span data-stu-id="e01b1-111">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="e01b1-112">如果中央管理存储托管在任一池上，则会在这两个配对的池上安装和运行它，其中一个托管活动主机的池和承载备用的其他池。</span><span class="sxs-lookup"><span data-stu-id="e01b1-112">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="e01b1-p103">在下面的过程中，<EM>PoolFQDN</EM> 参数表示受灾难影响的池而不是受影响的用户从中重定向的池的 FQDN。对于同一组受影响的用户，它在故障转移和故障回复 cmdlet 中表示同一个池（即，在故障转移之前先承载用户的池）。</span><span class="sxs-lookup"><span data-stu-id="e01b1-p103">In the following procedures, the <EM>PoolFQDN</EM> parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from. For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><span data-ttu-id="e01b1-p104">例如，假定这样一种情况，其中驻留在池 P1 中的所有用户都故障转移到备份池 P2。如果管理员要将当前由 P2 服务的所有用户都移动为由 P1 服务，则管理员必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e01b1-p104">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2. If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="e01b1-p105">使用故障回复 cmdlet 将最初驻留在 P1 上的所有用户从 P2 故障回复到 P1。在此情况下，<EM>PoolFQDN</EM> 为 P1 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e01b1-p105">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet. In this case, the <EM>PoolFQDN</EM> is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="e01b1-p106">使用故障转移 cmdlet 将最初驻留在 P2 上的所有用户故障转移到 P1。在此情况下，<EM>PoolFQDN</EM> 为 P2 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e01b1-p106">Fail over all the users originally homed on P2 to P1 using the failover cmdlet. In this case, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="e01b1-121">如果稍后管理员要将这些 P2 用户故障回复到 P2，则 <EM>PoolFQDN</EM> 为 P2 的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e01b1-121">If the administrator later wants to fail back those P2 users back to P2, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P></LI></OL><span data-ttu-id="e01b1-122">请注意，上面的步骤 1 必须在步骤 2 之前执行，才能保留池完整性。</span><span class="sxs-lookup"><span data-stu-id="e01b1-122">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="e01b1-123">如果在步骤 1 之前尝试步骤 2，则步骤 2 cmdlet 将失败。</span><span class="sxs-lookup"><span data-stu-id="e01b1-123">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e01b1-124">本部分内容</span><span class="sxs-lookup"><span data-stu-id="e01b1-124">In This Section</span></span>

  - [<span data-ttu-id="e01b1-125">在 Lync Server 2013 中配置和监控备份服务</span><span class="sxs-lookup"><span data-stu-id="e01b1-125">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [<span data-ttu-id="e01b1-126">在 Lync Server 2013 中对池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="e01b1-126">Failing over a pool in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-pool.md)

  - [<span data-ttu-id="e01b1-127">在 Lync Server 2013 中对池进行故障回复</span><span class="sxs-lookup"><span data-stu-id="e01b1-127">Failing back a pool in Lync Server 2013</span></span>](lync-server-2013-failing-back-a-pool.md)

  - [<span data-ttu-id="e01b1-128">在 Lync Server 2013 中对镜像数据库进行故障转移</span><span class="sxs-lookup"><span data-stu-id="e01b1-128">Failing over a mirrored database in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-mirrored-database.md)

  - [<span data-ttu-id="e01b1-129">在 Lync Server 2013 中对用于 Lync Server 联盟的边缘池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="e01b1-129">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [<span data-ttu-id="e01b1-130">在 Lync Server 2013 中对用于 XMPP 联盟的边缘池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="e01b1-130">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [<span data-ttu-id="e01b1-131">在 Lync Server 2013 中对用于 Lync Server 联盟或 XMPP 联盟的边缘池进行故障回复</span><span class="sxs-lookup"><span data-stu-id="e01b1-131">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [<span data-ttu-id="e01b1-132">在 Lync Server 2013 中更改与前端池关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="e01b1-132">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [<span data-ttu-id="e01b1-133">在 Lync Server 2013 中使用备份服务还原会议内容</span><span class="sxs-lookup"><span data-stu-id="e01b1-133">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e01b1-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e01b1-134">See Also</span></span>


[<span data-ttu-id="e01b1-135">在 Lync Server 2013 中规划高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="e01b1-135">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

