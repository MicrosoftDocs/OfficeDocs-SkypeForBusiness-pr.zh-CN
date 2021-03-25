---
title: Skype for Business Server 中的后端服务器高可用性
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: 了解 Skype for Business Server 中支持的后端服务器高可用性选项，包括 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例、数据库镜像和SQL群集。
ms.openlocfilehash: 31ec37d898bd1f04c07142de1849928656f3238e
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119371"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a><span data-ttu-id="86b5a-103">Skype for Business Server 中的后端服务器高可用性</span><span class="sxs-lookup"><span data-stu-id="86b5a-103">Back End Server high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="86b5a-104">了解 Skype for Business Server 中支持的后端服务器高可用性选项，包括 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例、数据库镜像和SQL群集。</span><span class="sxs-lookup"><span data-stu-id="86b5a-104">Learn about the Back End Server high availability options supported in Skype for Business Server, including AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances, database mirroring, and SQL failover clustering.</span></span>
  
<span data-ttu-id="86b5a-105">若要增强后端服务器的高可用性，有四个选项：</span><span class="sxs-lookup"><span data-stu-id="86b5a-105">To enhance high availability for your Back End Servers, you have four options:</span></span>
  
- <span data-ttu-id="86b5a-106">数据库镜像</span><span class="sxs-lookup"><span data-stu-id="86b5a-106">Database mirroring</span></span>
    
- <span data-ttu-id="86b5a-107">AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="86b5a-107">AlwaysOn Availability Groups</span></span>
    
- <span data-ttu-id="86b5a-108">AlwaysOn 故障转移群集实例 (FCI) </span><span class="sxs-lookup"><span data-stu-id="86b5a-108">AlwaysOn Failover Cluster Instances (FCI)</span></span>
    
- <span data-ttu-id="86b5a-109">SQL故障转移群集</span><span class="sxs-lookup"><span data-stu-id="86b5a-109">SQL failover clustering</span></span>
    
<span data-ttu-id="86b5a-110">可以选择使用其中一个解决方案，但建议保留组织的业务连续性。</span><span class="sxs-lookup"><span data-stu-id="86b5a-110">Using one of these solutions is optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="86b5a-111">否则，如果数据库服务器一次，可能会导致大量 Skype for Business Server 数据丢失。</span><span class="sxs-lookup"><span data-stu-id="86b5a-111">Otherwise, having a single database server go down could cause the loss of significant Skype for Business Server data.</span></span> 
  
<span data-ttu-id="86b5a-112">只能使用拓扑生成器设置数据库镜像。</span><span class="sxs-lookup"><span data-stu-id="86b5a-112">You can set up database mirroring using only Topology Builder.</span></span> <span data-ttu-id="86b5a-113">对于 AlwaysOn 可用性组、AlwaysOn 故障转移群集实例或 SQL 故障转移群集，可以使用 SQL Server 创建高可用性解决方案，然后可以使用拓扑生成器将其与前端池关联。</span><span class="sxs-lookup"><span data-stu-id="86b5a-113">For AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances,or SQL failover clustering, you use SQL Server to create the high availability solution, then you can use Topology Builder to associate it with a Front End pool.</span></span>
  
<span data-ttu-id="86b5a-114">如果在与另一个前端池配对的前端池上使用后端服务器高可用性，则应该在两个池中使用相同的后端高可用性解决方案。</span><span class="sxs-lookup"><span data-stu-id="86b5a-114">If you use Back End Server high availability on a Front End pool that is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> 
  
## <a name="database-mirroring"></a><span data-ttu-id="86b5a-115">数据库镜像</span><span class="sxs-lookup"><span data-stu-id="86b5a-115">Database mirroring</span></span>

<span data-ttu-id="86b5a-116">Skype for Business Server 支持通过以下数据库软件进行镜像：</span><span class="sxs-lookup"><span data-stu-id="86b5a-116">Skype for Business Server supports mirroring with the following database software:</span></span>
  
- <span data-ttu-id="86b5a-117">SQL Server 2019，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86b5a-117">SQL Server 2019, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="86b5a-118">SQL Server 2017，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86b5a-118">SQL Server 2017, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="86b5a-119">SQL Server 2016，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86b5a-119">SQL Server 2016, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="86b5a-120">SQL Server 2014，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86b5a-120">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="86b5a-121">SQL Server 2012 SP2 和 CU2，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86b5a-121">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>
    

> [!NOTE]
> <span data-ttu-id="86b5a-122">SQL镜像在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="86b5a-122">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="86b5a-123">AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法是 Skype for Business Server 2019 唯一受支持的选项。</span><span class="sxs-lookup"><span data-stu-id="86b5a-123">The AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are the only supported options with Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="86b5a-124">Skype for Business Server 中的后端服务器高可用性不支持异步数据库镜像。</span><span class="sxs-lookup"><span data-stu-id="86b5a-124">Asynchronous database mirroring is not supported for Back End Server high availability in Skype for Business Server.</span></span> <span data-ttu-id="86b5a-125">在本文档的其余部分中，除非另有说明，否则数据库镜像是指同步数据库镜像。</span><span class="sxs-lookup"><span data-stu-id="86b5a-125">In the rest of this document, database mirroring means synchronous database mirroring, unless otherwise explicitly stated.</span></span> 
  
<span data-ttu-id="86b5a-126">在前端池中部署数据库镜像时，将镜像池中的所有 Skype for Business Server 数据库，包括中央管理存储（如果它位于该池中）以及响应组 应用数据库 和呼叫库 应用数据库（如果这些应用程序正在池中运行）。</span><span class="sxs-lookup"><span data-stu-id="86b5a-126">When you deploy database mirroring in a Front End pool, all Skype for Business Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span> 
  
<span data-ttu-id="86b5a-127">使用数据库镜像时，无需对服务器使用共享存储。</span><span class="sxs-lookup"><span data-stu-id="86b5a-127">With database mirroring, you do not need to use shared storage for the servers.</span></span> <span data-ttu-id="86b5a-128">每台服务器将其数据库副本保留在本地存储上。</span><span class="sxs-lookup"><span data-stu-id="86b5a-128">Each server keeps its copy of the databases in local storage.</span></span> 
  
<span data-ttu-id="86b5a-129">可以选择部署带见证的数据库镜像，也可以不部署见证服务器。</span><span class="sxs-lookup"><span data-stu-id="86b5a-129">You may choose to deploy database mirroring with or without a witness.</span></span> <span data-ttu-id="86b5a-130">我们建议使用见证服务器，因为见证服务器可实现后端服务器的故障转移的自动化。</span><span class="sxs-lookup"><span data-stu-id="86b5a-130">We recommend using a witness because it enables failover of the Back End Server to be automatic.</span></span> <span data-ttu-id="86b5a-131">否则，管理员必须手动调用故障转移。</span><span class="sxs-lookup"><span data-stu-id="86b5a-131">Otherwise, an administrator must manually invoke failover.</span></span> <span data-ttu-id="86b5a-132">请注意，即使部署了见证服务器，管理员也可手动调用后端服务器故障转移（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="86b5a-132">Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>
  
<span data-ttu-id="86b5a-p107">如果您使用见证服务器，则可对多对后端服务器使用一个见证服务器。见证服务器和后端服务器对之间没有严格的 1:1 对应关系。对多对后端服务器使用一个见证服务器的部署不如为每对后端服务器使用单独的见证服务器的拓扑有弹性。</span><span class="sxs-lookup"><span data-stu-id="86b5a-p107">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span> 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a><span data-ttu-id="86b5a-136">规划后端服务器镜像的指南</span><span class="sxs-lookup"><span data-stu-id="86b5a-136">Guidelines for planning Back End Server mirroring</span></span>

<span data-ttu-id="86b5a-137">通常，在两台具有见证的后端服务器之间设置 SQL 镜像需要满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="86b5a-137">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>
  
- <span data-ttu-id="86b5a-138">主服务器的版本必须支持SQL Server镜像SQL版本。</span><span class="sxs-lookup"><span data-stu-id="86b5a-138">The primary server's version of SQL Server must support SQL mirroring.</span></span>
    
- <span data-ttu-id="86b5a-139">主、镜像和见证（如果部署）必须具有同一版本的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="86b5a-139">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span> 
    
- <span data-ttu-id="86b5a-p108">主和镜像必须具有同一版本的 SQL Server。见证可以具有不同版本。</span><span class="sxs-lookup"><span data-stu-id="86b5a-p108">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>
    
<span data-ttu-id="86b5a-142">有关SQL角色支持哪些SQL的最佳实践，请参阅 MSDN 库中的"数据库  [镜像](/sql/database-engine/database-mirroring/database-mirroring-witness) 见证"。</span><span class="sxs-lookup"><span data-stu-id="86b5a-142">For SQL best practices in terms of what SQL versions are supported for a Witness role, see  ["Database Mirroring Witness"](/sql/database-engine/database-mirroring/database-mirroring-witness) in the MSDN Library.</span></span>
  
<span data-ttu-id="86b5a-143">配置服务器镜像之前，必须先正确设置SQL数据库权限。</span><span class="sxs-lookup"><span data-stu-id="86b5a-143">Before configuring server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="86b5a-144">有关详细信息，请参阅"为数据库镜像或 AlwaysOn 可用性组设置登录[ (SQL Server) "。](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability)</span><span class="sxs-lookup"><span data-stu-id="86b5a-144">For details, see  ["Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)"](/sql/database-engine/database-mirroring/set-up-login-accounts-database-mirroring-always-on-availability).</span></span>
  
<span data-ttu-id="86b5a-p110">对于 SQL 镜像，数据库恢复模式始终设置为“完全”，这意味着您必须密切监控事务日志大小并定期备份事务日志以避免后端服务器上的磁盘空间不足。事务日志备份频率取决于日志增长速率，反过来，日志增长速率又取决于前端池上的用户活动所触发的数据库事务数。建议您确定您的 Lync 部署工作负载所需的事务日志增长程度，以便进行适当的规划。下列文章提供了有关 SQL 备份和日志管理的其他信息：</span><span class="sxs-lookup"><span data-stu-id="86b5a-p110">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="86b5a-149">只有在主服务器、镜像服务器和见证服务器SQL需要时，才支持使用拓扑生成器或 cmdlet 设置和删除 (镜像) 服务器都属于同一个域。</span><span class="sxs-lookup"><span data-stu-id="86b5a-149">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="86b5a-150">如果您需要在不同域中的服务器之间设置 SQL 镜像，请参阅 SQL Server 文档。</span><span class="sxs-lookup"><span data-stu-id="86b5a-150">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span> 

> [!NOTE]
> <span data-ttu-id="86b5a-151">SQL镜像在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="86b5a-151">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="86b5a-152">AlwaysOn 可用性组、AlwaysOn 故障转移群集实例 (FCI) 和 SQL 故障转移群集方法在 Skype for Business Server 2019 中是首选。</span><span class="sxs-lookup"><span data-stu-id="86b5a-152">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a><span data-ttu-id="86b5a-153">使用数据库镜像进行自动后端服务器故障转移的恢复时间</span><span class="sxs-lookup"><span data-stu-id="86b5a-153">Recovery time for automatic Back End Server failover with database mirroring</span></span>

<span data-ttu-id="86b5a-154">对于使用数据库镜像的自动后端故障转移，RTO (恢复) 目标为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="86b5a-154">For automatic Back End failover with database mirroring, the engineering target for recovery time objective (RTO) is 5 minutes.</span></span> <span data-ttu-id="86b5a-155">由于同步数据库镜像，我们预计后端服务器故障期间会丢失数据，除非在服务器之间移动数据的同时，前端服务器和后端服务器同时出现故障的极少数情况除外。</span><span class="sxs-lookup"><span data-stu-id="86b5a-155">Because of the synchronous database mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers.</span></span> <span data-ttu-id="86b5a-156">恢复点目标 (RPO) 的设计目标为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="86b5a-156">The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a><span data-ttu-id="86b5a-157">使用数据库镜像的后端服务器故障期间用户体验</span><span class="sxs-lookup"><span data-stu-id="86b5a-157">User experience during Back End Server failure with database mirroring</span></span>

<span data-ttu-id="86b5a-158">失败期间的用户体验取决于失败的性质和拓扑。</span><span class="sxs-lookup"><span data-stu-id="86b5a-158">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>
  
<span data-ttu-id="86b5a-159">如果使用数据库镜像并配置了见证服务器，并且主体出现故障，后端服务器故障转移将自动快速地发生。</span><span class="sxs-lookup"><span data-stu-id="86b5a-159">If you use database mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly.</span></span> <span data-ttu-id="86b5a-160">活动用户应该不太会注意到正在进行的会话出现中断。</span><span class="sxs-lookup"><span data-stu-id="86b5a-160">Active users should not notice much interruption to their ongoing sessions.</span></span>
  
<span data-ttu-id="86b5a-161">如果未配置见证服务器，则管理员手动调用故障转移需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="86b5a-161">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="86b5a-162">在这段时间内，活动用户可能会受到影响。</span><span class="sxs-lookup"><span data-stu-id="86b5a-162">During that time, active users may be affected.</span></span> <span data-ttu-id="86b5a-163">他们将继续大约 30 分钟的正常会话。</span><span class="sxs-lookup"><span data-stu-id="86b5a-163">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="86b5a-164">如果主服务器仍未还原，或者管理员尚未对备份进行故障切换，则用户会切换到恢复能力模式，这意味着他们无法执行需要在 Lync Server (上进行永久性更改的任务，例如添加联系人) 。</span><span class="sxs-lookup"><span data-stu-id="86b5a-164">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>
  
<span data-ttu-id="86b5a-p116">如果主体和镜像后端服务器均失败，或者其中一台服务器和见证服务器失败，则后端服务器将变得不可用（即使它是仍在工作的主体）。在此情况下，活动用户将在一段时间之后切换至恢复能力模式。</span><span class="sxs-lookup"><span data-stu-id="86b5a-p116">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a><span data-ttu-id="86b5a-167">AlwaysOn 可用性组和 AlwaysOn 故障转移群集实例</span><span class="sxs-lookup"><span data-stu-id="86b5a-167">AlwaysOn Availability Groups and AlwaysOn Failover Cluster Instances</span></span>

<span data-ttu-id="86b5a-168">Skype for Business Server 仅支持 AlwaysOn 可用性组作为主动/被动，而非主动/主动。</span><span class="sxs-lookup"><span data-stu-id="86b5a-168">Skype for Business Server supports AlwaysOn Availability Groups only as active/passive, not active/active.</span></span> 
  
<span data-ttu-id="86b5a-169">若要使用 AlwaysOn 可用性组或 AlwaysOn 故障转移群集实例，首先SQL Server设置和配置高可用性解决方案。</span><span class="sxs-lookup"><span data-stu-id="86b5a-169">To use AlwaysOn Availability Groups or AlwaysOn Failover Cluster Instances, you first use SQL Server to set up and configure the high availability solution.</span></span> <span data-ttu-id="86b5a-170">然后，可以使用拓扑生成器将其与前端池关联。</span><span class="sxs-lookup"><span data-stu-id="86b5a-170">You can then use Topology Builder to associate it with a Front End pool.</span></span>

<span data-ttu-id="86b5a-171">Skype for Business Server 通过以下数据库软件支持 AlwaysOn：</span><span class="sxs-lookup"><span data-stu-id="86b5a-171">Skype for Business Server supports AlwaysOn with the following database software:</span></span>

- <span data-ttu-id="86b5a-172">SQL Server 2019 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="86b5a-172">SQL Server 2019 Enterprise Edition</span></span>

- <span data-ttu-id="86b5a-173">SQL Server 2019 Standard Edition（有限制）请参阅下面的说明</span><span class="sxs-lookup"><span data-stu-id="86b5a-173">SQL Server 2019 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="86b5a-174">SQL Server 2017 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="86b5a-174">SQL Server 2017 Enterprise Edition</span></span>

- <span data-ttu-id="86b5a-175">SQL Server 2017 Standard Edition（有限制）请参阅下面的说明</span><span class="sxs-lookup"><span data-stu-id="86b5a-175">SQL Server 2017 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="86b5a-176">SQL Server 2016 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="86b5a-176">SQL Server 2016 Enterprise Edition</span></span>

- <span data-ttu-id="86b5a-177">SQL Server 2016 Standard Edition（有限制）请参阅下面的说明</span><span class="sxs-lookup"><span data-stu-id="86b5a-177">SQL Server 2016 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="86b5a-178">SQL Server 2014 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="86b5a-178">SQL Server 2014 Enterprise Edition</span></span>
    
- <span data-ttu-id="86b5a-179">SQL Server 2012 SP2 和 CU2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="86b5a-179">SQL Server 2012 SP2 and CU2 Enterprise Edition</span></span>

> [!NOTE]
> <span data-ttu-id="86b5a-180">SQL Server 2019、2017 和 2016 是唯一受 Skype for Business Server 2019 支持的版本。</span><span class="sxs-lookup"><span data-stu-id="86b5a-180">SQL Server 2019, 2017, and 2016 are the only versions supported by Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="86b5a-181">Always On 可用性组 **在** SQL 2016、2017 和 2019 Standard Edition 中不受支持，但您可以使用 Always On 故障转移群集实例。</span><span class="sxs-lookup"><span data-stu-id="86b5a-181">Always On Availability Groups is **not** supported in SQL 2016, 2017, and 2019 Standard Editions but you can use Always On Failover Cluster Instances.</span></span> <span data-ttu-id="86b5a-182">有关详细信息 [，请参阅 SQL Server 2016](/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) 版本和支持的功能。</span><span class="sxs-lookup"><span data-stu-id="86b5a-182">See [Editions and supported features of SQL Server 2016](/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) to learn more.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="86b5a-183">多个 AlwaysOn 可用性组实例的实例名称必须相同。</span><span class="sxs-lookup"><span data-stu-id="86b5a-183">Instance names for multiple AlwaysOn Availability Group instances must be the same.</span></span> 
  
<span data-ttu-id="86b5a-184">有关部署 AlwaysOn 可用性组的步骤，请参阅在 Skype for Business Server 的后端服务器上部署 [AlwaysOn 可用性组](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)。</span><span class="sxs-lookup"><span data-stu-id="86b5a-184">For steps for deploying AlwaysOn Availability Groups, see [Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).</span></span>
  
## <a name="sql-server-failover-clustering"></a><span data-ttu-id="86b5a-185">SQL Server故障转移群集</span><span class="sxs-lookup"><span data-stu-id="86b5a-185">SQL Server Failover Clustering</span></span>

<span data-ttu-id="86b5a-186">Skype for Business Server 支持SQL Server数据库软件进行故障转移群集：</span><span class="sxs-lookup"><span data-stu-id="86b5a-186">Skype for Business Server supports SQL Server failover clustering with the following database software:</span></span>
  
- <span data-ttu-id="86b5a-187">SQL Server 2019，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86b5a-187">SQL Server 2019, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="86b5a-188">SQL Server 2017，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86b5a-188">SQL Server 2017, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="86b5a-189">SQL Server 2016，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86b5a-189">SQL Server 2016, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="86b5a-190">SQL Server 2014，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86b5a-190">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="86b5a-191">SQL Server 2012 SP2 和 CU2，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="86b5a-191">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>

<span data-ttu-id="86b5a-192">若要SQL故障转移群集，应首先设置和配置SQL Server群集，然后再部署前端池。</span><span class="sxs-lookup"><span data-stu-id="86b5a-192">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="86b5a-193">有关 2012 年 3 月故障转移群集的最佳实践SQL Server说明，请参阅 [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) 。</span><span class="sxs-lookup"><span data-stu-id="86b5a-193">For best practices and setup instructions for failover clustering in SQL Server 2012, see [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation).</span></span>

> [!NOTE]
> <span data-ttu-id="86b5a-194">SQL Server 2019、2017 和 SQL Server 2016 是唯一受 Skype for Business Server 2019 支持的版本。</span><span class="sxs-lookup"><span data-stu-id="86b5a-194">SQL Server 2019, 2017, and SQL Server 2016 are the only versions supported by Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="86b5a-195">若要SQL故障转移群集，应首先设置和配置SQL Server群集，然后再部署前端池。</span><span class="sxs-lookup"><span data-stu-id="86b5a-195">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="86b5a-196">有关在 2014 和 2016 SQL Server故障转移群集的最佳实践和设置说明，请参阅 [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation) 。</span><span class="sxs-lookup"><span data-stu-id="86b5a-196">For best practices and setup instructions for failover clustering in SQL Server 2014 and 2016, see [https://technet.microsoft.com/library/hh231721.aspx](/sql/sql-server/failover-clusters/install/sql-server-failover-cluster-installation).</span></span> <span data-ttu-id="86b5a-197">有关 SQL Server 2008 中的故障转移群集，请参阅 [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105)) 。</span><span class="sxs-lookup"><span data-stu-id="86b5a-197">For failover clustering in SQL Server 2008, see [https://technet.microsoft.com/library/ms189134(v=sql.105).aspx](/previous-versions/sql/sql-server-2008-r2/ms189134(v=sql.105)).</span></span>
  
<span data-ttu-id="86b5a-198">安装 SQL Server 时，应安装 SQL Server Management Studio 来管理数据库位置和日志文件位置。</span><span class="sxs-lookup"><span data-stu-id="86b5a-198">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations.</span></span> <span data-ttu-id="86b5a-199">安装 SQL Server 时，SQL Server Management Studio 将作为可选组件安装。</span><span class="sxs-lookup"><span data-stu-id="86b5a-199">SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>
