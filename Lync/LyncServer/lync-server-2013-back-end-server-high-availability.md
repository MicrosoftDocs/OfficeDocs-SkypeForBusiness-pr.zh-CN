---
title: Lync Server 2013：后端服务器高可用性
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Back End Server high availability
ms:assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205248(v=OCS.15)
ms:contentKeyID: 48185358
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7abdbfef9aefb556646c8221ee54e699e3f46e3b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145441"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="cb219-102">Lync Server 2013 中的后端服务器高可用性</span><span class="sxs-lookup"><span data-stu-id="cb219-102">Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb219-103">_**上次修改的主题：** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="cb219-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="cb219-104">若要确保后端服务器具有高可用性，可以使用同步 SQL 镜像或 SQL 群集。</span><span class="sxs-lookup"><span data-stu-id="cb219-104">To ensure high availability for your Back End Servers, you can use either synchronous SQL mirroring or SQL clustering.</span></span> <span data-ttu-id="cb219-105">使用其中一种解决方案是可选的，但建议维护贵组织的业务连续性。</span><span class="sxs-lookup"><span data-stu-id="cb219-105">Using one of these solutions optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="cb219-106">Lync Server 2013 中的后端服务器高可用性不支持异步 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="cb219-106">Asynchronous SQL mirroring is not supported for Back End Server high availability in Lync Server 2013.</span></span> <span data-ttu-id="cb219-107">在本文档剩下的部分中，除非另外明确规定，否则 SQL 镜像是指同步的 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="cb219-107">In the rest of this document, SQL mirroring means synchronous SQL mirroring, unless otherwise explicitly stated.</span></span>

<span data-ttu-id="cb219-108">您可以使用拓扑生成器轻松设置 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="cb219-108">You can easily set up SQL mirroring with Topology Builder.</span></span> <span data-ttu-id="cb219-109">对于 SQL 故障转移群集，必须使用 SQL Server 进行安装。</span><span class="sxs-lookup"><span data-stu-id="cb219-109">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="cb219-110">如果在与用于灾难恢复的另一个前端池配对的池中使用 SQL 镜像或 SQL 群集，则应在两个池中使用相同的后端高可用性解决方案。</span><span class="sxs-lookup"><span data-stu-id="cb219-110">If you use either SQL mirroring or SQL clustering in a pool which is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> <span data-ttu-id="cb219-111">不应使用 sql 群集将 SQL 镜像与池进行配对。</span><span class="sxs-lookup"><span data-stu-id="cb219-111">You should not pair a pool using SQL mirroring with a pool using SQL clustering.</span></span>

<span data-ttu-id="cb219-112">在部署 SQL 镜像时，池中的所有 Lync Server 数据库都将进行镜像，其中包括中央管理存储（如果位于此池中）以及响应组应用程序数据库和呼叫寄存应用程序数据库（如果这些应用程序在池中运行。</span><span class="sxs-lookup"><span data-stu-id="cb219-112">When you deploy SQL mirroring, all Lync Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span>

<span data-ttu-id="cb219-p104">通过使用 SQL 镜像，您无需对服务器使用共享存储。每台服务器将其数据库副本保留在本地存储上。</span><span class="sxs-lookup"><span data-stu-id="cb219-p104">With SQL mirroring, you do not need to use shared storage for the servers. Each server keeps its copy of the databases in local storage.</span></span>

<span data-ttu-id="cb219-p105">您可选择使用或不使用见证服务器部署 SQL 镜像。我们建议使用见证服务器，因为见证服务器可实现后端服务器的故障转移的自动化。否则，管理员必须手动调用故障转移。请注意，即使部署了见证服务器，管理员也可手动调用后端服务器故障转移（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="cb219-p105">You may choose to deploy SQL mirroring with or without a witness. We recommend using a witness because it enables failover of the Back End Server to be automatic. Otherwise, an administrator must manually invoke failover. Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>

<span data-ttu-id="cb219-p106">如果您使用见证服务器，则可对多对后端服务器使用一个见证服务器。见证服务器和后端服务器对之间没有严格的 1:1 对应关系。对多对后端服务器使用一个见证服务器的部署不如为每对后端服务器使用单独的见证服务器的拓扑有弹性。</span><span class="sxs-lookup"><span data-stu-id="cb219-p106">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span>

<span data-ttu-id="cb219-122">有关 SQL 群集支持的详细信息，请参阅[Lync Server 2013 中的数据库软件支持](lync-server-2013-database-software-support.md)。</span><span class="sxs-lookup"><span data-stu-id="cb219-122">For more information about SQL clustering support, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="cb219-123">有关部署 SQL 群集的详细信息，请参阅[CONFIGURE SQL Server 集群 For Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)。</span><span class="sxs-lookup"><span data-stu-id="cb219-123">For details on deploying SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a><span data-ttu-id="cb219-124">使用 SQL 镜像自动后端服务器故障转移的恢复时间</span><span class="sxs-lookup"><span data-stu-id="cb219-124">Recovery Time for Automatic Back End Server Failover with SQL Mirroring</span></span>

<span data-ttu-id="cb219-125">对于 SQL 镜像的自动后端故障转移，用于恢复时间目标（RTO）的工程目标为5分钟。</span><span class="sxs-lookup"><span data-stu-id="cb219-125">For automatic Back End failover with SQL mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="cb219-126">由于使用了同步的 SQL 镜像，我们在后端服务器失败期间无需考虑数据丢失（除了在服务器间移动数据期间前端服务器和后端服务器同时宕机的罕见情况）。</span><span class="sxs-lookup"><span data-stu-id="cb219-126">Because of the synchronous SQL mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="cb219-127">恢复点目标 (RPO) 的设计目标为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="cb219-127">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a><span data-ttu-id="cb219-128">在后端服务器出现故障时使用 SQL 镜像的用户体验</span><span class="sxs-lookup"><span data-stu-id="cb219-128">User Experience During Back End Server Failure with SQL Mirroring</span></span>

<span data-ttu-id="cb219-129">失败期间的用户体验取决于失败的性质和拓扑。</span><span class="sxs-lookup"><span data-stu-id="cb219-129">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>

<span data-ttu-id="cb219-130">如果使用 SQL 镜像并配置了见证服务器，并且主体发生故障，后端服务器故障转移会自动快速地进行。</span><span class="sxs-lookup"><span data-stu-id="cb219-130">If you use SQL mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="cb219-131">活动用户应该不太会注意到正在进行的会话出现中断。</span><span class="sxs-lookup"><span data-stu-id="cb219-131">Active users should not notice much interruption to their ongoing sessions.</span></span>

<span data-ttu-id="cb219-132">如果未配置见证服务器，则管理员手动调用故障转移需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="cb219-132">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="cb219-133">在这段时间内，活动用户可能会受到影响。</span><span class="sxs-lookup"><span data-stu-id="cb219-133">During that time, active users may be affected.</span></span> <span data-ttu-id="cb219-134">他们将继续大约 30 分钟的正常会话。</span><span class="sxs-lookup"><span data-stu-id="cb219-134">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="cb219-135">如果仍未还原主主服务器，或者管理员尚未故障转移到备份，则用户将切换到弹性模式，这意味着他们无法在 Lync Server 上执行需要永久更改的任务（如添加联系人）。</span><span class="sxs-lookup"><span data-stu-id="cb219-135">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>

<span data-ttu-id="cb219-p111">如果主体和镜像后端服务器均失败，或者其中一台服务器和见证服务器失败，则后端服务器将变得不可用（即使它是仍在工作的主体）。在此情况下，活动用户将在一段时间之后切换至恢复能力模式。</span><span class="sxs-lookup"><span data-stu-id="cb219-p111">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

