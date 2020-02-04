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
ms.openlocfilehash: 5708212aa2eb30cfcc3c3d40894ca2340475bd8b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740132"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="back-end-server-high-availability-in-lync-server-2013"></a><span data-ttu-id="f0eed-102">Lync Server 2013 中的后端服务器高可用性</span><span class="sxs-lookup"><span data-stu-id="f0eed-102">Back End Server high availability in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0eed-103">_**主题上次修改时间：** 2013-08-12_</span><span class="sxs-lookup"><span data-stu-id="f0eed-103">_**Topic Last Modified:** 2013-08-12_</span></span>

<span data-ttu-id="f0eed-104">为确保后端服务器的高可用性，可以使用同步 SQL 镜像或 SQL 群集。</span><span class="sxs-lookup"><span data-stu-id="f0eed-104">To ensure high availability for your Back End Servers, you can use either synchronous SQL mirroring or SQL clustering.</span></span> <span data-ttu-id="f0eed-105">使用其中一个解决方案是可选的，但建议保持组织的业务连续性。</span><span class="sxs-lookup"><span data-stu-id="f0eed-105">Using one of these solutions optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="f0eed-106">Lync Server 2013 中的后端服务器高可用性不支持异步 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="f0eed-106">Asynchronous SQL mirroring is not supported for Back End Server high availability in Lync Server 2013.</span></span> <span data-ttu-id="f0eed-107">在本文档的其余部分中，SQL 镜像意味着同步 SQL 镜像，除非另有明确声明。</span><span class="sxs-lookup"><span data-stu-id="f0eed-107">In the rest of this document, SQL mirroring means synchronous SQL mirroring, unless otherwise explicitly stated.</span></span>

<span data-ttu-id="f0eed-108">你可以通过拓扑生成器轻松设置 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="f0eed-108">You can easily set up SQL mirroring with Topology Builder.</span></span> <span data-ttu-id="f0eed-109">对于 SQL 故障转移群集，您必须使用 SQL Server 进行设置。</span><span class="sxs-lookup"><span data-stu-id="f0eed-109">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="f0eed-110">如果在与用于灾难恢复的另一前端池配对的池中使用 SQL 镜像或 SQL 群集，则应在两个池中使用相同的后端高可用性解决方案。</span><span class="sxs-lookup"><span data-stu-id="f0eed-110">If you use either SQL mirroring or SQL clustering in a pool which is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> <span data-ttu-id="f0eed-111">不应使用 sql 群集和池将 SQL 镜像与池配对。</span><span class="sxs-lookup"><span data-stu-id="f0eed-111">You should not pair a pool using SQL mirroring with a pool using SQL clustering.</span></span>

<span data-ttu-id="f0eed-112">当你部署 SQL 镜像时，池中的所有 Lync Server 数据库都将被镜像，包括中央管理存储（如果它位于此池中）以及响应组应用数据库和调用寄存应用程序数据库（如果这些应用程序正在池中运行。</span><span class="sxs-lookup"><span data-stu-id="f0eed-112">When you deploy SQL mirroring, all Lync Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span>

<span data-ttu-id="f0eed-113">使用 SQL 镜像，无需为服务器使用共享存储。</span><span class="sxs-lookup"><span data-stu-id="f0eed-113">With SQL mirroring, you do not need to use shared storage for the servers.</span></span> <span data-ttu-id="f0eed-114">每台服务器将其数据库副本保留在本地存储上。</span><span class="sxs-lookup"><span data-stu-id="f0eed-114">Each server keeps its copy of the databases in local storage.</span></span>

<span data-ttu-id="f0eed-115">你可以选择使用或不使用见证部署 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="f0eed-115">You may choose to deploy SQL mirroring with or without a witness.</span></span> <span data-ttu-id="f0eed-116">我们建议使用见证服务器，因为见证服务器可实现后端服务器的故障转移的自动化。</span><span class="sxs-lookup"><span data-stu-id="f0eed-116">We recommend using a witness because it enables failover of the Back End Server to be automatic.</span></span> <span data-ttu-id="f0eed-117">否则，管理员必须手动调用故障转移。</span><span class="sxs-lookup"><span data-stu-id="f0eed-117">Otherwise, an administrator must manually invoke failover.</span></span> <span data-ttu-id="f0eed-118">请注意，即使部署了见证服务器，管理员也可手动调用后端服务器故障转移（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="f0eed-118">Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>

<span data-ttu-id="f0eed-p106">如果您使用见证服务器，则可对多对后端服务器使用一个见证服务器。见证服务器和后端服务器对之间没有严格的 1:1 对应关系。对多对后端服务器使用一个见证服务器的部署不如为每对后端服务器使用单独的见证服务器的拓扑有弹性。</span><span class="sxs-lookup"><span data-stu-id="f0eed-p106">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span>

<span data-ttu-id="f0eed-122">有关 SQL 群集支持的详细信息，请参阅[Lync Server 2013 中的数据库软件支持](lync-server-2013-database-software-support.md)。</span><span class="sxs-lookup"><span data-stu-id="f0eed-122">For more information about SQL clustering support, see [Database software support in Lync Server 2013](lync-server-2013-database-software-support.md).</span></span> <span data-ttu-id="f0eed-123">有关部署 SQL 群集的详细信息，请参阅[配置 Lync server 2013 的 SQL Server 群集](lync-server-2013-configure-sql-server-clustering.md)。</span><span class="sxs-lookup"><span data-stu-id="f0eed-123">For details on deploying SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<div>

## <a name="recovery-time-for-automatic-back-end-server-failover-with-sql-mirroring"></a><span data-ttu-id="f0eed-124">利用 SQL 镜像自动后端服务器故障转移的恢复时间</span><span class="sxs-lookup"><span data-stu-id="f0eed-124">Recovery Time for Automatic Back End Server Failover with SQL Mirroring</span></span>

<span data-ttu-id="f0eed-125">对于具有 SQL 镜像的自动后端故障切换，针对恢复时间目标（RTO）的工程目标是5分钟。</span><span class="sxs-lookup"><span data-stu-id="f0eed-125">For automatic Back End failover with SQL mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="f0eed-126">由于同步 SQL 镜像，我们不会在回退服务器故障期间预计数据丢失，但当前端服务器和后端服务器在服务器之间移动数据时，很少发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="f0eed-126">Because of the synchronous SQL mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="f0eed-127">恢复点目标 (RPO) 的设计目标为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="f0eed-127">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>

</div>

<div>

## <a name="user-experience-during-back-end-server-failure-with-sql-mirroring"></a><span data-ttu-id="f0eed-128">SQL 镜像后端服务器出现故障期间的用户体验</span><span class="sxs-lookup"><span data-stu-id="f0eed-128">User Experience During Back End Server Failure with SQL Mirroring</span></span>

<span data-ttu-id="f0eed-129">失败期间的用户体验取决于失败的性质和拓扑。</span><span class="sxs-lookup"><span data-stu-id="f0eed-129">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>

<span data-ttu-id="f0eed-130">如果你使用 SQL 镜像并配置了见证，则主体失败，后端服务器故障转移会自动快速进行。</span><span class="sxs-lookup"><span data-stu-id="f0eed-130">If you use SQL mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="f0eed-131">活动用户应该不太会注意到正在进行的会话出现中断。</span><span class="sxs-lookup"><span data-stu-id="f0eed-131">Active users should not notice much interruption to their ongoing sessions.</span></span>

<span data-ttu-id="f0eed-132">如果未配置见证服务器，则管理员手动调用故障转移需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="f0eed-132">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="f0eed-133">在这段时间内，活动用户可能会受到影响。</span><span class="sxs-lookup"><span data-stu-id="f0eed-133">During that time, active users may be affected.</span></span> <span data-ttu-id="f0eed-134">他们将继续大约 30 分钟的正常会话。</span><span class="sxs-lookup"><span data-stu-id="f0eed-134">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="f0eed-135">如果主服务器仍未还原，或者管理员未故障转移到备份，则用户将切换到复原模式，这意味着他们无法执行需要在 Lync Server 上永久更改的任务（如添加联系人）。</span><span class="sxs-lookup"><span data-stu-id="f0eed-135">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>

<span data-ttu-id="f0eed-p111">如果主体和镜像后端服务器均失败，或者其中一台服务器和见证服务器失败，则后端服务器将变得不可用（即使它是仍在工作的主体）。在此情况下，活动用户将在一段时间之后切换至恢复能力模式。</span><span class="sxs-lookup"><span data-stu-id="f0eed-p111">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

