---
title: 管理 Lync Server 灾难恢复、高可用性和备份服务
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
ms.openlocfilehash: d7adc4086ac8ac6b8e5ad33c2e4c1dc131d357e0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762070"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-lync-server-2013-disaster-recovery-high-availability-and-backup-service"></a><span data-ttu-id="6d9fe-102">管理 Lync Server 2013 灾难恢复、高可用性和备份服务</span><span class="sxs-lookup"><span data-stu-id="6d9fe-102">Managing Lync Server 2013 disaster recovery, high availability, and Backup Service</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6d9fe-103">_**主题上次修改时间：** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="6d9fe-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="6d9fe-104">本部分包含灾难恢复操作的过程，以及用于维护同步服务的过程，该备份服务将同步成对前端池内的数据。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-104">This section contains procedures for disaster recovery operations, as well as for maintaining the Backup Service which synchronizes the data in paired Front End pools.</span></span>

<span data-ttu-id="6d9fe-105">灾难恢复过程（故障转移和回切）是手动的。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-105">Disaster recovery procedures, both failover and failback, are manual.</span></span> <span data-ttu-id="6d9fe-106">如果发生灾难，管理员必须手动调用故障转移过程。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-106">If there is a disaster, the administrator must manually invoke the failover procedures.</span></span> <span data-ttu-id="6d9fe-107">修复完池后，故障回复也同样适用。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-107">The same applies to failback after the pool is repaired.</span></span>

<span data-ttu-id="6d9fe-108">本部分其余部分中的灾难恢复过程假设如下：</span><span class="sxs-lookup"><span data-stu-id="6d9fe-108">The disaster recovery procedures in the rest of this section assume the following:</span></span>

  - <span data-ttu-id="6d9fe-109">你的部署具有成对的前端池，位于不同的网站中，如在[Lync Server 2013 中规划高可用性和灾难恢复](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-109">You have a deployment with paired Front End pools, located in different sites, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="6d9fe-110">备份服务已在这些配对的池上运行，以使其保持同步。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-110">The Backup Service has been running on these paired pools to keep them synchronized.</span></span>

  - <span data-ttu-id="6d9fe-111">如果中央管理存储托管在任一池中，则会在这两个配对的池上安装和运行它，其中一个托管活动主机的池和另一个托管备用池的池。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-111">If the Central Management store is hosted on either pool, it is installed and running on both of the paired pools, with one of those pools hosting the active master and the other pool hosting the standby.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="6d9fe-112">在以下过程中， <EM>PoolFQDN</EM>参数是指受灾难影响的池的 FQDN，而不是对受影响的用户进行重定向的池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-112">In the following procedures, the <EM>PoolFQDN</EM> parameter refers to the FQDN of the pool that is affected by disaster, not the pool that affected users are being redirected from.</span></span> <span data-ttu-id="6d9fe-113">对于同一组受影响的用户，它指的是故障转移和故障回复 cmdlet 中的同一池（即，在故障转移之前首先驻留用户的池）。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-113">For the same set of affected users, it refers to the same pool in both failover and failback cmdlets (that is, the pool that first homed the users before the failover).</span></span><BR><span data-ttu-id="6d9fe-114">例如，假设驻留在池 P1 上的所有用户都已故障转移到备份池 P2 的情况。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-114">For example, assume a case in which all users homed on a pool P1 were failed over to the backup pool, P2.</span></span> <span data-ttu-id="6d9fe-115">如果管理员想要移动当前由 P2 服务的所有用户以供 P1 处理，管理员必须执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="6d9fe-115">If the administrator wants to move all the users currently serviced by P2 to be serviced by P1, the administrator must perform the following steps:</span></span> 
> <OL>
> <LI>
> <P><span data-ttu-id="6d9fe-116">使用故障回复 cmdlet，将原来位于 P1 中的所有用户从 P2 切换回 P1。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-116">Fail back all the users originally homed on P1 from P2 to P1 using the failback cmdlet.</span></span> <span data-ttu-id="6d9fe-117">在此情况下， <EM>PoolFQDN</EM>为 P1's FQDN。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-117">In this case, the <EM>PoolFQDN</EM> is P1’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="6d9fe-118">使用故障转移 cmdlet，将所有最初驻留在 P2 上的用户故障转移到 P1。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-118">Fail over all the users originally homed on P2 to P1 using the failover cmdlet.</span></span> <span data-ttu-id="6d9fe-119">在此情况下， <EM>PoolFQDN</EM>为 P2's FQDN。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-119">In this case, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P>
> <LI>
> <P><span data-ttu-id="6d9fe-120">如果管理员稍后希望将这些 P2 用户故障回复回 P2，则<EM>PoolFQDN</EM>为 P2's FQDN。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-120">If the administrator later wants to fail back those P2 users back to P2, the <EM>PoolFQDN</EM> is P2’s FQDN.</span></span></P></LI></OL><span data-ttu-id="6d9fe-121">请注意，上面的步骤1必须在步骤2之前执行，以保留池完整性。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-121">Note that step 1 above must be performed before step 2 to preserve pool integrity.</span></span> <span data-ttu-id="6d9fe-122">如果你在步骤1之前尝试步骤2，则步骤 2 cmdlet 将失败。</span><span class="sxs-lookup"><span data-stu-id="6d9fe-122">If you try step 2 before step 1, the step 2 cmdlet will fail.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="6d9fe-123">本节内容</span><span class="sxs-lookup"><span data-stu-id="6d9fe-123">In This Section</span></span>

  - [<span data-ttu-id="6d9fe-124">在 Lync Server 2013 中配置和监控备份服务</span><span class="sxs-lookup"><span data-stu-id="6d9fe-124">Configuring and monitoring the Backup Service in Lync Server 2013</span></span>](lync-server-2013-configuring-and-monitoring-the-backup-service.md)

  - [<span data-ttu-id="6d9fe-125">在 Lync Server 2013 中对池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="6d9fe-125">Failing over a pool in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-pool.md)

  - [<span data-ttu-id="6d9fe-126">在 Lync Server 2013 中对池进行故障回复</span><span class="sxs-lookup"><span data-stu-id="6d9fe-126">Failing back a pool in Lync Server 2013</span></span>](lync-server-2013-failing-back-a-pool.md)

  - [<span data-ttu-id="6d9fe-127">在 Lync Server 2013 中对镜像数据库进行故障转移</span><span class="sxs-lookup"><span data-stu-id="6d9fe-127">Failing over a mirrored database in Lync Server 2013</span></span>](lync-server-2013-failing-over-a-mirrored-database.md)

  - [<span data-ttu-id="6d9fe-128">在 Lync Server 2013 中对用于 Lync Server 联盟的边缘池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="6d9fe-128">Failing over the Edge pool used for Lync Server federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

  - [<span data-ttu-id="6d9fe-129">在 Lync Server 2013 中对用于 XMPP 联盟的边缘池进行故障转移</span><span class="sxs-lookup"><span data-stu-id="6d9fe-129">Failing over the Edge pool used for XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)

  - [<span data-ttu-id="6d9fe-130">在 Lync Server 2013 中对用于 Lync Server 联盟或 XMPP 联盟的边缘池进行故障回复</span><span class="sxs-lookup"><span data-stu-id="6d9fe-130">Failing back the Edge pool used for Lync Server federation or XMPP federation in Lync Server 2013</span></span>](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)

  - [<span data-ttu-id="6d9fe-131">在 Lync Server 2013 中更改与前端池关联的边缘池</span><span class="sxs-lookup"><span data-stu-id="6d9fe-131">Changing the Edge pool associated with a Front End pool in Lync Server 2013</span></span>](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)

  - [<span data-ttu-id="6d9fe-132">在 Lync Server 2013 中使用备份服务还原会议内容</span><span class="sxs-lookup"><span data-stu-id="6d9fe-132">Restoring conference contents using the Backup Service in Lync Server 2013</span></span>](lync-server-2013-restoring-conference-contents-using-the-backup-service.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6d9fe-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d9fe-133">See Also</span></span>


[<span data-ttu-id="6d9fe-134">在 Lync Server 2013 中规划高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="6d9fe-134">Planning for high availability and disaster recovery in Lync Server 2013</span></span>](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

