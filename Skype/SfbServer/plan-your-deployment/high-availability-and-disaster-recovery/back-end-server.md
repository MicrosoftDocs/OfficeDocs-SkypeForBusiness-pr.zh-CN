---
title: 后端服务器高可用性 Skype 业务服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: 了解业务服务器，包括 AlwaysOn 可用性组、 AlwaysOn 故障转移集群实例、 数据库镜像，和 SQL 故障转移群集 Skype 中支持的后端服务器高可用性选项。
ms.openlocfilehash: c200596ac43099d92b7fd37e850a524cf92a24ce
ms.sourcegitcommit: ee05fe02fe68b5bd6ee38dd4a3ad69da3d37c492
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/17/2019
ms.locfileid: "34106297"
---
# <a name="back-end-server-high-availability-in-skype-for-business-server"></a><span data-ttu-id="321a7-103">后端服务器高可用性 Skype 业务服务器</span><span class="sxs-lookup"><span data-stu-id="321a7-103">Back End Server high availability in Skype for Business Server</span></span>
 
<span data-ttu-id="321a7-104">了解业务服务器，包括 AlwaysOn 可用性组、 AlwaysOn 故障转移集群实例、 数据库镜像，和 SQL 故障转移群集 Skype 中支持的后端服务器高可用性选项。</span><span class="sxs-lookup"><span data-stu-id="321a7-104">Learn about the Back End Server high availability options supported in Skype for Business Server, including AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances, database mirroring, and SQL failover clustering.</span></span>
  
<span data-ttu-id="321a7-105">为提高后端服务器的高可用性，你有四个选项：</span><span class="sxs-lookup"><span data-stu-id="321a7-105">To enhance high availability for your Back End Servers, you have four options:</span></span>
  
- <span data-ttu-id="321a7-106">数据库镜像</span><span class="sxs-lookup"><span data-stu-id="321a7-106">Database mirroring</span></span>
    
- <span data-ttu-id="321a7-107">AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="321a7-107">AlwaysOn Availability Groups</span></span>
    
- <span data-ttu-id="321a7-108">AlwaysOn 故障转移集群实例 (FCI)</span><span class="sxs-lookup"><span data-stu-id="321a7-108">AlwaysOn Failover Cluster Instances (FCI)</span></span>
    
- <span data-ttu-id="321a7-109">SQL 故障转移群集</span><span class="sxs-lookup"><span data-stu-id="321a7-109">SQL failover clustering</span></span>
    
<span data-ttu-id="321a7-110">可以选择使用上述任何一个解决方案，但建议保持组织的业务连续性。</span><span class="sxs-lookup"><span data-stu-id="321a7-110">Using one of these solutions is optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="321a7-111">否则，具有下移一台数据库服务器，这种情况可能会导致重要 Skype Business Server 数据丢失。</span><span class="sxs-lookup"><span data-stu-id="321a7-111">Otherwise, having a single database server go down could cause the loss of significant Skype for Business Server data.</span></span> 
  
<span data-ttu-id="321a7-112">您可以设置数据库镜像使用仅拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="321a7-112">You can set up database mirroring using only Topology Builder.</span></span> <span data-ttu-id="321a7-113">AlwaysOn 可用性组、 AlwaysOn 故障转移群集实例或 SQL 故障转移群集，您使用 SQL Server 创建高可用性解决方案，然后您可以使用拓扑生成器以将其与前端池关联。</span><span class="sxs-lookup"><span data-stu-id="321a7-113">For AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances,or SQL failover clustering, you use SQL Server to create the high availability solution, then you can use Topology Builder to associate it with a Front End pool.</span></span>
  
<span data-ttu-id="321a7-114">如果您使用后端服务器高可用性与灾难恢复的另一个前端池配对前端池上时，您应在这两个池中使用相同的后端高可用性解决方案。</span><span class="sxs-lookup"><span data-stu-id="321a7-114">If you use Back End Server high availability on a Front End pool that is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> 
  
## <a name="database-mirroring"></a><span data-ttu-id="321a7-115">数据库镜像</span><span class="sxs-lookup"><span data-stu-id="321a7-115">Database mirroring</span></span>

<span data-ttu-id="321a7-116">Skype 业务服务器支持与以下数据库软件镜像：</span><span class="sxs-lookup"><span data-stu-id="321a7-116">Skype for Business Server supports mirroring with the following database software:</span></span>
  
- <span data-ttu-id="321a7-117">SQL Server 2017，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="321a7-117">SQL Server 2017, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="321a7-118">SQL Server 2016，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="321a7-118">SQL Server 2016, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="321a7-119">SQL Server Enterprise Edition 和 Standard Edition 2014 年</span><span class="sxs-lookup"><span data-stu-id="321a7-119">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="321a7-120">SQL Server 2012 SP2 和 CU2，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="321a7-120">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>
    

> [!NOTE]
> <span data-ttu-id="321a7-121">SQL 镜像的业务服务器 2015 Skype 中可用，但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="321a7-121">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="321a7-122">AlwaysOn 可用性组、 AlwaysOn 故障转移群集实例 (FCI)，和 SQL 故障转移群集方法是首选与 Skype 的业务服务器 2019年。</span><span class="sxs-lookup"><span data-stu-id="321a7-122">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="321a7-123">异步数据库镜像不支持的后端服务器高可用性 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="321a7-123">Asynchronous database mirroring is not supported for Back End Server high availability in Skype for Business Server.</span></span> <span data-ttu-id="321a7-124">在本文档的后续部分中，除非另有说明，否则数据库镜像即表示同步数据库镜像。</span><span class="sxs-lookup"><span data-stu-id="321a7-124">In the rest of this document, database mirroring means synchronous database mirroring, unless otherwise explicitly stated.</span></span> 
  
<span data-ttu-id="321a7-125">当您部署在前端池数据库镜像时，镜像 Business Server 数据库在池中的所有 Skype，包括中央管理存储中，如果它位于此池中，以及响应组应用程序数据库和呼叫寄存应用程序数据库，如果在池中运行这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="321a7-125">When you deploy database mirroring in a Front End pool, all Skype for Business Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span> 
  
<span data-ttu-id="321a7-p105">通过使用数据库镜像，您无需对服务器使用共享存储。每台服务器将其数据库副本保留在本地存储上。</span><span class="sxs-lookup"><span data-stu-id="321a7-p105">With database mirroring, you do not need to use shared storage for the servers. Each server keeps its copy of the databases in local storage.</span></span> 
  
<span data-ttu-id="321a7-p106">您可选择使用或不使用见证服务器部署数据库镜像。我们建议使用见证服务器，因为见证服务器可实现后端服务器的故障转移的自动化。否则，管理员必须手动调用故障转移。请注意，即使部署了见证服务器，管理员也可手动调用后端服务器故障转移（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="321a7-p106">You may choose to deploy database mirroring with or without a witness. We recommend using a witness because it enables failover of the Back End Server to be automatic. Otherwise, an administrator must manually invoke failover. Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>
  
<span data-ttu-id="321a7-p107">如果您使用见证服务器，则可对多对后端服务器使用一个见证服务器。见证服务器和后端服务器对之间没有严格的 1:1 对应关系。对多对后端服务器使用一个见证服务器的部署不如为每对后端服务器使用单独的见证服务器的拓扑有弹性。</span><span class="sxs-lookup"><span data-stu-id="321a7-p107">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span> 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a><span data-ttu-id="321a7-135">适用于计划后端服务器镜像的准则</span><span class="sxs-lookup"><span data-stu-id="321a7-135">Guidelines for planning Back End Server mirroring</span></span>

<span data-ttu-id="321a7-136">通常，在两台具有见证的后端服务器之间设置 SQL 镜像需要满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="321a7-136">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>
  
- <span data-ttu-id="321a7-137">SQL server 的主服务器的版本必须支持 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="321a7-137">The primary server's version of SQL Server must support SQL mirroring.</span></span>
    
- <span data-ttu-id="321a7-138">主、镜像和见证（如果部署）必须具有同一版本的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="321a7-138">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span> 
    
- <span data-ttu-id="321a7-p108">主和镜像必须具有同一版本的 SQL Server。见证可以具有不同版本。</span><span class="sxs-lookup"><span data-stu-id="321a7-p108">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>
    
<span data-ttu-id="321a7-141">有关见证角色支持的 SQL 版本的 SQL 最佳实践，请参阅 MSDN 库中的["数据库镜像见证"](https://go.microsoft.com/fwlink/p/?LinkId=247345) 。</span><span class="sxs-lookup"><span data-stu-id="321a7-141">For SQL best practices in terms of what SQL versions are supported for a Witness role, see  ["Database Mirroring Witness"](https://go.microsoft.com/fwlink/p/?LinkId=247345) in the MSDN Library.</span></span>
  
<span data-ttu-id="321a7-142">配置服务器镜像之前，必须先正确设置 SQL 数据库权限。</span><span class="sxs-lookup"><span data-stu-id="321a7-142">Before configuring server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="321a7-143">有关详细信息，请参阅["设置数据库镜像或 AlwaysOn 可用性组 (SQL Server) 的登录帐户"](https://go.microsoft.com/fwlink/p/?LinkId=268454)。</span><span class="sxs-lookup"><span data-stu-id="321a7-143">For details, see  ["Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span></span>
  
<span data-ttu-id="321a7-p110">对于 SQL 镜像，数据库恢复模式始终设置为“**完全**”，这意味着你必须密切监控事务日志大小并定期备份事务日志以避免后端服务器上的磁盘空间不足。事务日志备份频率取决于日志增长速率，反过来，日志增长速率又取决于前端池上的用户活动所触发的数据库事务数。建议你确定你的 Lync 部署工作负载所需的事务日志增长程度，以便进行适当的规划。下列文章提供了有关 SQL 备份和日志管理的其他信息：</span><span class="sxs-lookup"><span data-stu-id="321a7-p110">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="321a7-148">使用拓扑生成器或 cmdlet 来设置和删除 SQL 镜像仅当主、 镜像和见证 （如果需要） 服务器所有属于同一域时，才支持。</span><span class="sxs-lookup"><span data-stu-id="321a7-148">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="321a7-149">如果您需要在不同域中的服务器之间设置 SQL 镜像，请参阅 SQL Server 文档。</span><span class="sxs-lookup"><span data-stu-id="321a7-149">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span> 

> [!NOTE]
> <span data-ttu-id="321a7-150">SQL 镜像的业务服务器 2015 Skype 中可用，但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="321a7-150">SQL Mirroring is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="321a7-151">AlwaysOn 可用性组、 AlwaysOn 故障转移群集实例 (FCI)，和 SQL 故障转移群集方法是首选与 Skype 的业务服务器 2019年。</span><span class="sxs-lookup"><span data-stu-id="321a7-151">The  AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances (FCI), and SQL failover clustering methods are preferred with Skype for Business Server 2019.</span></span>
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a><span data-ttu-id="321a7-152">通过数据库镜像实施自动后端服务器故障转移的恢复时间</span><span class="sxs-lookup"><span data-stu-id="321a7-152">Recovery time for automatic Back End Server failover with database mirroring</span></span>

<span data-ttu-id="321a7-p113">对于通过数据库镜像实施自动后端故障转移，恢复时间目标 (RTO) 的设计目标为 5 分钟。由于使用了同步的数据库镜像，我们在后端服务器失败期间无需考虑数据丢失（除了在服务器间移动数据期间前端服务器和后端服务器同时宕机的罕见情况）。恢复点目标 (RPO) 的设计目标为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="321a7-p113">For automatic Back End failover with database mirroring, the engineering target for recovery time objective (RTO) is 5 minutes. Because of the synchronous database mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers. The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a><span data-ttu-id="321a7-156">使用数据库镜像的后端服务器失败期间的用户体验</span><span class="sxs-lookup"><span data-stu-id="321a7-156">User experience during Back End Server failure with database mirroring</span></span>

<span data-ttu-id="321a7-157">失败期间的用户体验取决于失败的性质和拓扑。</span><span class="sxs-lookup"><span data-stu-id="321a7-157">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>
  
<span data-ttu-id="321a7-p114">如果您使用数据库镜像并且配置了见证服务器，则当主体失败时，后端服务器故障转移将自动快速地发生。活动用户应该不太会注意到正在进行的会话出现中断。</span><span class="sxs-lookup"><span data-stu-id="321a7-p114">If you use database mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly. Active users should not notice much interruption to their ongoing sessions.</span></span>
  
<span data-ttu-id="321a7-160">如果未配置见证服务器，则管理员手动调用故障转移需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="321a7-160">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="321a7-161">在这段时间内，活动用户可能会受到影响。</span><span class="sxs-lookup"><span data-stu-id="321a7-161">During that time, active users may be affected.</span></span> <span data-ttu-id="321a7-162">他们将继续大约 30 分钟的正常会话。</span><span class="sxs-lookup"><span data-stu-id="321a7-162">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="321a7-163">如果仍然不还原主，或管理员具有不故障转移到备份，然后用户切换到恢复能力模式，这意味着他们不能执行 （例如添加联系人） 需要永久性更改 Lync Server 上的任务。</span><span class="sxs-lookup"><span data-stu-id="321a7-163">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>
  
<span data-ttu-id="321a7-p116">如果主体和镜像后端服务器均失败，或者其中一台服务器和见证服务器失败，则后端服务器将变得不可用（即使它是仍在工作的主体）。在此情况下，活动用户将在一段时间之后切换至恢复能力模式。</span><span class="sxs-lookup"><span data-stu-id="321a7-p116">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a><span data-ttu-id="321a7-166">AlwaysOn 可用性组和 AlwaysOn 故障转移群集实例</span><span class="sxs-lookup"><span data-stu-id="321a7-166">AlwaysOn Availability Groups and AlwaysOn Failover Cluster Instances</span></span>

<span data-ttu-id="321a7-167">Skype 业务服务器只能作为主动/被动群集，未主动/主动支持 AlwaysOn 可用性组。</span><span class="sxs-lookup"><span data-stu-id="321a7-167">Skype for Business Server supports AlwaysOn Availability Groups only as active/passive, not active/active.</span></span> 
  
<span data-ttu-id="321a7-168">若要使用 AlwaysOn 可用性组或 AlwaysOn 故障转移集群实例，您首先使用 SQL Server 设置和配置高可用性解决方案。</span><span class="sxs-lookup"><span data-stu-id="321a7-168">To use AlwaysOn Availability Groups or AlwaysOn Failover Cluster Instances, you first use SQL Server to set up and configure the high availability solution.</span></span> <span data-ttu-id="321a7-169">然后，您可以使用拓扑生成器以将其与前端池关联。</span><span class="sxs-lookup"><span data-stu-id="321a7-169">You can then use Topology Builder to associate it with a Front End pool.</span></span>

<span data-ttu-id="321a7-170">Skype 业务服务器使用的以下数据库软件支持 AlwaysOn:</span><span class="sxs-lookup"><span data-stu-id="321a7-170">Skype for Business Server supports AlwaysOn with the following database software:</span></span>

- <span data-ttu-id="321a7-171">SQL Server 2017 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="321a7-171">SQL Server 2017 Enterprise Edition</span></span>

- <span data-ttu-id="321a7-172">SQL Server 2017 Standard Edition 的限制，请参阅下面的注释</span><span class="sxs-lookup"><span data-stu-id="321a7-172">SQL Server 2017 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="321a7-173">SQL Server 2016 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="321a7-173">SQL Server 2016 Enterprise Edition</span></span>

- <span data-ttu-id="321a7-174">SQL Server 2016 Standard Edition 的限制，请参阅下面的注释</span><span class="sxs-lookup"><span data-stu-id="321a7-174">SQL Server 2016 Standard Edition with limitations, see note below</span></span>

- <span data-ttu-id="321a7-175">SQL Server 2014 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="321a7-175">SQL Server 2014 Enterprise Edition</span></span>
    
- <span data-ttu-id="321a7-176">SQL Server 2012 SP2 和 CU2 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="321a7-176">SQL Server 2012 SP2 and CU2 Enterprise Edition</span></span>

> [!NOTE]
> <span data-ttu-id="321a7-177">SQL Server 2017 和 SQL Server 2016 是支持的业务服务器 2019 Skype 的唯一版本。</span><span class="sxs-lookup"><span data-stu-id="321a7-177">SQL Server 2017 and SQL Server 2016 are the only versions supported by Skype for Business Server 2019.</span></span>

> [!NOTE]
> <span data-ttu-id="321a7-178">**不**支持 SQL 2016 和 2017年标准版本中，但您可以使用始终在故障转移群集实例，始终在可用性组。</span><span class="sxs-lookup"><span data-stu-id="321a7-178">Always On Availability Groups is **not** supported in SQL 2016 and 2017 Standard Editions but you can use Always On Failover Cluster Instances.</span></span> <span data-ttu-id="321a7-179">请参阅[版本和支持的功能的 SQL Server 2016](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017)以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="321a7-179">See [Editions and supported features of SQL Server 2016](https://docs.microsoft.com/sql/sql-server/editions-and-components-of-sql-server-2016?view=sql-server-2017) to learn more.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="321a7-180">多个 AlwaysOn 可用性组实例的实例名称必须相同。</span><span class="sxs-lookup"><span data-stu-id="321a7-180">Instance names for multiple AlwaysOn Availability Group instances must be the same.</span></span> 
  
<span data-ttu-id="321a7-181">有关部署 AlwaysOn 可用性组的步骤，请参阅[Deploy AlwaysOn 可用性组中的业务服务器 Skype 后端服务器上](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)。</span><span class="sxs-lookup"><span data-stu-id="321a7-181">For steps for deploying AlwaysOn Availability Groups, see [Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).</span></span>
  
## <a name="sql-server-failover-clustering"></a><span data-ttu-id="321a7-182">SQL Server 故障转移群集</span><span class="sxs-lookup"><span data-stu-id="321a7-182">SQL Server Failover Clustering</span></span>

<span data-ttu-id="321a7-183">Skype 业务服务器支持 SQL Server 故障转移群集与以下数据库软件：</span><span class="sxs-lookup"><span data-stu-id="321a7-183">Skype for Business Server supports SQL Server failover clustering with the following database software:</span></span>
  
- <span data-ttu-id="321a7-184">SQL Server 2017，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="321a7-184">SQL Server 2017, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="321a7-185">SQL Server 2016，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="321a7-185">SQL Server 2016, both Enterprise Edition and Standard Edition</span></span>

- <span data-ttu-id="321a7-186">SQL Server Enterprise Edition 和 Standard Edition 2014 年</span><span class="sxs-lookup"><span data-stu-id="321a7-186">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="321a7-187">SQL Server 2012 SP2 和 CU2，Enterprise Edition 和 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="321a7-187">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>

<span data-ttu-id="321a7-188">若要使用 SQL 故障转移群集，应首先设置，并部署前端池之前配置 SQL Server 群集。</span><span class="sxs-lookup"><span data-stu-id="321a7-188">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="321a7-189">最佳实践和故障转移群集在 SQL Server 2012 中的安装说明，请参阅[https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx)。</span><span class="sxs-lookup"><span data-stu-id="321a7-189">For best practices and setup instructions for failover clustering in SQL Server 2012, see [https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx).</span></span>

> [!NOTE]
> <span data-ttu-id="321a7-190">SQL Server 2017 和 SQL Server 2016 是支持的业务服务器 2019 Skype 的唯一版本。</span><span class="sxs-lookup"><span data-stu-id="321a7-190">SQL Server 2017 and SQL Server 2016 are the only versions supported by Skype for Business Server 2019.</span></span>
    
<span data-ttu-id="321a7-191">若要使用 SQL 故障转移群集，应首先设置，并部署前端池之前配置 SQL Server 群集。</span><span class="sxs-lookup"><span data-stu-id="321a7-191">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="321a7-192">最佳实践和故障转移群集 SQL Server 2014 和 2016年中的安装说明，请参阅[https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx)。</span><span class="sxs-lookup"><span data-stu-id="321a7-192">For best practices and setup instructions for failover clustering in SQL Server 2014 and 2016, see [https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx).</span></span> <span data-ttu-id="321a7-193">有关故障转移群集在 SQL Server 2008 中，请参阅[https://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="321a7-193">For failover clustering in SQL Server 2008, see [https://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx).</span></span>
  
<span data-ttu-id="321a7-p121">安装 SQL Server 时，应安装 SQL Server Management Studio 来管理数据库位置和日志文件位置。安装 SQL Server 时，SQL Server Management Studio 将作为可选组件安装。</span><span class="sxs-lookup"><span data-stu-id="321a7-p121">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations. SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>
  

