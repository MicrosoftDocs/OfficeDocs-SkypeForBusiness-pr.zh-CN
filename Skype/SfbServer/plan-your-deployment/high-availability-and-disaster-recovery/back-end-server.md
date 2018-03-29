---
title: Skype for Business Server 2015 中的后端服务器高可用性
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 3/20/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c559aacb-4e1d-4e78-9582-41f966ad418d
description: 了解有关支持 Skype 业务服务器，包括 AlwaysOn 可用性组、 AlwaysOn 故障转移群集实例、 数据库镜像、 和 SQL 故障切换群集的后端服务器高可用性选项。
ms.openlocfilehash: f0831ffb757d04e954ece8a1874dffad9e6e74d0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="back-end-server-high-availability-in-skype-for-business-server-2015"></a><span data-ttu-id="8dee4-103">Skype for Business Server 2015 中的后端服务器高可用性</span><span class="sxs-lookup"><span data-stu-id="8dee4-103">Back End Server high availability in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8dee4-104">了解有关支持 Skype 业务服务器，包括 AlwaysOn 可用性组、 AlwaysOn 故障转移群集实例、 数据库镜像、 和 SQL 故障切换群集的后端服务器高可用性选项。</span><span class="sxs-lookup"><span data-stu-id="8dee4-104">Learn about the Back End Server high availability options supported in Skype for Business Server, including AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances, database mirroring, and SQL failover clustering.</span></span>
  
<span data-ttu-id="8dee4-105">为提高后端服务器的高可用性，你有四个选项：</span><span class="sxs-lookup"><span data-stu-id="8dee4-105">To enhance high availability for your Back End Servers, you have four options:</span></span>
  
- <span data-ttu-id="8dee4-106">数据库镜像</span><span class="sxs-lookup"><span data-stu-id="8dee4-106">Database mirroring</span></span>
    
- <span data-ttu-id="8dee4-107">AlwaysOn 可用性组</span><span class="sxs-lookup"><span data-stu-id="8dee4-107">AlwaysOn Availability Groups</span></span>
    
- <span data-ttu-id="8dee4-108">AlwaysOn 故障转移群集实例 (FCI)</span><span class="sxs-lookup"><span data-stu-id="8dee4-108">AlwaysOn Failover Cluster Instances (FCI)</span></span>
    
- <span data-ttu-id="8dee4-109">SQL 故障转移群集</span><span class="sxs-lookup"><span data-stu-id="8dee4-109">SQL failover clustering</span></span>
    
<span data-ttu-id="8dee4-110">可以选择使用上述任何一个解决方案，但建议保持组织的业务连续性。</span><span class="sxs-lookup"><span data-stu-id="8dee4-110">Using one of these solutions is optional, but is recommended to maintain your organization's business continuity.</span></span> <span data-ttu-id="8dee4-111">否则，具有向下转单数据库服务器可能会导致重大 Skype 业务服务器数据的丢失。</span><span class="sxs-lookup"><span data-stu-id="8dee4-111">Otherwise, having a single database server go down could cause the loss of significant Skype for Business Server data.</span></span> 
  
<span data-ttu-id="8dee4-112">您可以设置数据库镜像使用仅拓扑生成器。</span><span class="sxs-lookup"><span data-stu-id="8dee4-112">You can set up database mirroring using only Topology Builder.</span></span> <span data-ttu-id="8dee4-113">AlwaysOn 可用性组、 AlwaysOn 故障转移群集实例，或 SQL 故障转移群集，您使用 SQL Server 创建高可用性解决方案中，然后您可以使用拓扑生成器来将它与前端池相关联。</span><span class="sxs-lookup"><span data-stu-id="8dee4-113">For AlwaysOn Availability Groups, AlwaysOn Failover Cluster Instances,or SQL failover clustering, you use SQL Server to create the high availability solution, then you can use Topology Builder to associate it with a Front End pool.</span></span>
  
<span data-ttu-id="8dee4-114">如果使用另一个用于灾难恢复的前端池与配对的前端池后端服务器的高可用性，则应在这两个池中使用同一后端高可用性解决方案。</span><span class="sxs-lookup"><span data-stu-id="8dee4-114">If you use Back End Server high availability on a Front End pool that is paired with another Front End pool for disaster recovery, you should use the same Back End high availability solution in both pools.</span></span> 
  
## <a name="database-mirroring"></a><span data-ttu-id="8dee4-115">数据库镜像</span><span class="sxs-lookup"><span data-stu-id="8dee4-115">Database mirroring</span></span>

<span data-ttu-id="8dee4-116">Skype 业务服务器支持以下数据库软件镜像：</span><span class="sxs-lookup"><span data-stu-id="8dee4-116">Skype for Business Server supports mirroring with the following database software:</span></span>
  
- <span data-ttu-id="8dee4-117">SQL Server 2014 年企业版和标准版</span><span class="sxs-lookup"><span data-stu-id="8dee4-117">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="8dee4-118">SQL Server 2012 SP2 和 CU2，企业版和标准版</span><span class="sxs-lookup"><span data-stu-id="8dee4-118">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="8dee4-119">SQL Server 2008 R2 SP2，企业版和标准版</span><span class="sxs-lookup"><span data-stu-id="8dee4-119">SQL Server 2008 R2 SP2, both Enterprise Edition and Standard Edition</span></span>
    
<span data-ttu-id="8dee4-120">异步数据库镜像是服务器不支持 Skype 在后端服务器高可用性的业务。</span><span class="sxs-lookup"><span data-stu-id="8dee4-120">Asynchronous database mirroring is not supported for Back End Server high availability in Skype for Business Server.</span></span> <span data-ttu-id="8dee4-121">在本文档的后续部分中，除非另有说明，否则数据库镜像即表示同步数据库镜像。</span><span class="sxs-lookup"><span data-stu-id="8dee4-121">In the rest of this document, database mirroring means synchronous database mirroring, unless otherwise explicitly stated.</span></span> 
  
<span data-ttu-id="8dee4-122">当您部署数据库镜像在前端池中时，所有 Skype 业务服务器中的数据库池进行都镜像，包括中央管理存储中，如果位于此池中，以及响应组应用数据库和调用公园应用数据库，如果这些应用程序池中运行。</span><span class="sxs-lookup"><span data-stu-id="8dee4-122">When you deploy database mirroring in a Front End pool, all Skype for Business Server databases in the pool are mirrored, including the Central Management store, if it is located in this pool, as well as the Response Group application database and the Call Park application database, if those applications are running in the pool.</span></span> 
  
<span data-ttu-id="8dee4-p104">通过使用数据库镜像，您无需对服务器使用共享存储。每台服务器将其数据库副本保留在本地存储上。</span><span class="sxs-lookup"><span data-stu-id="8dee4-p104">With database mirroring, you do not need to use shared storage for the servers. Each server keeps its copy of the databases in local storage.</span></span> 
  
<span data-ttu-id="8dee4-p105">您可选择使用或不使用见证服务器部署数据库镜像。我们建议使用见证服务器，因为见证服务器可实现后端服务器的故障转移的自动化。否则，管理员必须手动调用故障转移。请注意，即使部署了见证服务器，管理员也可手动调用后端服务器故障转移（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="8dee4-p105">You may choose to deploy database mirroring with or without a witness. We recommend using a witness because it enables failover of the Back End Server to be automatic. Otherwise, an administrator must manually invoke failover. Note that even if a witness is deployed, an administrator can manually invoke Back End Server failover, if necessary.</span></span>
  
<span data-ttu-id="8dee4-p106">如果您使用见证服务器，则可对多对后端服务器使用一个见证服务器。见证服务器和后端服务器对之间没有严格的 1:1 对应关系。对多对后端服务器使用一个见证服务器的部署不如为每对后端服务器使用单独的见证服务器的拓扑有弹性。</span><span class="sxs-lookup"><span data-stu-id="8dee4-p106">If you use a witness, you can use a single witness for multiple pairs of Back End Servers. There is no strict 1:1 correspondence between witnesses and pairs of Back End Servers. Deployments that use a single witness for multiple pairs of Back End Servers are not quite as resilient as topologies with a separate witness for each Back End Server pair.</span></span> 
  
### <a name="guidelines-for-planning-back-end-server-mirroring"></a><span data-ttu-id="8dee4-132">适用于计划后端服务器镜像的准则</span><span class="sxs-lookup"><span data-stu-id="8dee4-132">Guidelines for planning Back End Server mirroring</span></span>

<span data-ttu-id="8dee4-133">通常，在两台具有见证的后端服务器之间设置 SQL 镜像需要满足以下条件：</span><span class="sxs-lookup"><span data-stu-id="8dee4-133">In general, setting up SQL mirroring between the two Back End Servers with a witness requires the following:</span></span>
  
- <span data-ttu-id="8dee4-134">主服务器的 SQL Server 版本必须支持 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="8dee4-134">The primary server's version of SQL Server must support SQL mirroring.</span></span>
    
- <span data-ttu-id="8dee4-135">主、镜像和见证（如果部署）必须具有同一版本的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="8dee4-135">The primary, mirror, and the witness (if deployed) must have the same version of SQL Server.</span></span> 
    
- <span data-ttu-id="8dee4-p107">主和镜像必须具有同一版本的 SQL Server。见证可以具有不同版本。</span><span class="sxs-lookup"><span data-stu-id="8dee4-p107">The primary and the mirror must have the same edition of SQL Server. The witness may have a different edition.</span></span>
    
<span data-ttu-id="8dee4-138">SQL 在见证服务器角色支持哪些 SQL 版本方面的最佳做法，请参阅 MSDN 库中的["数据库镜像见证"](https://go.microsoft.com/fwlink/p/?LinkId=247345) 。</span><span class="sxs-lookup"><span data-stu-id="8dee4-138">For SQL best practices in terms of what SQL versions are supported for a Witness role, see  ["Database Mirroring Witness"](https://go.microsoft.com/fwlink/p/?LinkId=247345) in the MSDN Library.</span></span>
  
<span data-ttu-id="8dee4-139">配置服务器镜像之前，必须先正确设置 SQL 数据库权限。</span><span class="sxs-lookup"><span data-stu-id="8dee4-139">Before configuring server mirroring, you must first set up SQL database permissions correctly.</span></span> <span data-ttu-id="8dee4-140">有关详细信息，请参阅["设置为数据库镜像或 AlwaysOn 可用性组 (SQL Server) 的登录帐户"](https://go.microsoft.com/fwlink/p/?LinkId=268454)。</span><span class="sxs-lookup"><span data-stu-id="8dee4-140">For details, see  ["Set Up Login Accounts for Database Mirroring or AlwaysOn Availability Groups (SQL Server)"](https://go.microsoft.com/fwlink/p/?LinkId=268454).</span></span>
  
<span data-ttu-id="8dee4-p109">对于 SQL 镜像，数据库恢复模式始终设置为“**完全**”，这意味着你必须密切监控事务日志大小并定期备份事务日志以避免后端服务器上的磁盘空间不足。事务日志备份频率取决于日志增长速率，反过来，日志增长速率又取决于前端池上的用户活动所触发的数据库事务数。建议你确定你的 Lync 部署工作负载所需的事务日志增长程度，以便进行适当的规划。下列文章提供了有关 SQL 备份和日志管理的其他信息：</span><span class="sxs-lookup"><span data-stu-id="8dee4-p109">With SQL mirroring, database recovery mode is always set to **Full**, which means you must closely monitor transaction log size and back up transaction logs on a regular basis to avoid running out of disk space on the Back End Servers. The frequency of transaction log backups depends on the log growth rate, which in turn depends on database transactions incurred by user activities on the Front End pool. We recommend that you determine how much transaction log growth is expected for your Lync deployment workload so that you can do the planning accordingly. The following articles provide additional information on SQL backup and log management:</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8dee4-145">使用拓扑生成器或 cmdlet 来设置和删除 SQL 镜像仅在主服务器、 镜像和 （如果需要） 见证服务器所有属于相同的域时，才支持。</span><span class="sxs-lookup"><span data-stu-id="8dee4-145">Using Topology Builder or cmdlets to set up and remove SQL mirroring is supported only when the primary, mirror, and witness (if desired) servers all belong to the same domain.</span></span> <span data-ttu-id="8dee4-146">如果您需要在不同域中的服务器之间设置 SQL 镜像，请参阅 SQL Server 文档。</span><span class="sxs-lookup"><span data-stu-id="8dee4-146">If you want to set up SQL mirroring among servers in different domains, see your SQL Server documentation.</span></span> 
  
### <a name="recovery-time-for-automatic-back-end-server-failover-with-database-mirroring"></a><span data-ttu-id="8dee4-147">通过数据库镜像实施自动后端服务器故障转移的恢复时间</span><span class="sxs-lookup"><span data-stu-id="8dee4-147">Recovery time for automatic Back End Server failover with database mirroring</span></span>

<span data-ttu-id="8dee4-p111">对于通过数据库镜像实施自动后端故障转移，恢复时间目标 (RTO) 的设计目标为 5 分钟。由于使用了同步的数据库镜像，我们在后端服务器失败期间无需考虑数据丢失（除了在服务器间移动数据期间前端服务器和后端服务器同时宕机的罕见情况）。恢复点目标 (RPO) 的设计目标为 5 分钟。</span><span class="sxs-lookup"><span data-stu-id="8dee4-p111">For automatic Back End failover with database mirroring, the engineering target for recovery time objective (RTO) is 5 minutes. Because of the synchronous database mirroring, we do not anticipate data loss during Back End Server failures except in rare occasions when both the Front End Servers and the Back End Server go down simultaneously while data is being moved between the servers. The engineering target for recovery point objective (RPO) is 5 minutes.</span></span>
  
### <a name="user-experience-during-back-end-server-failure-with-database-mirroring"></a><span data-ttu-id="8dee4-151">使用数据库镜像的后端服务器失败期间的用户体验</span><span class="sxs-lookup"><span data-stu-id="8dee4-151">User experience during Back End Server failure with database mirroring</span></span>

<span data-ttu-id="8dee4-152">失败期间的用户体验取决于失败的性质和拓扑。</span><span class="sxs-lookup"><span data-stu-id="8dee4-152">User experience during a failure depends on the nature of the failure, and on your topology.</span></span>
  
<span data-ttu-id="8dee4-p112">如果您使用数据库镜像并且配置了见证服务器，则当主体失败时，后端服务器故障转移将自动快速地发生。活动用户应该不太会注意到正在进行的会话出现中断。</span><span class="sxs-lookup"><span data-stu-id="8dee4-p112">If you use database mirroring and have a witness configured, and the principal fails, Back End Server failover happens automatically and quickly. Active users should not notice much interruption to their ongoing sessions.</span></span>
  
<span data-ttu-id="8dee4-155">如果未配置见证服务器，则管理员手动调用故障转移需要一些时间。</span><span class="sxs-lookup"><span data-stu-id="8dee4-155">If there is no witness configured, it will take some time for the administrator to manually invoke the failover.</span></span> <span data-ttu-id="8dee4-156">在这段时间内，活动用户可能会受到影响。</span><span class="sxs-lookup"><span data-stu-id="8dee4-156">During that time, active users may be affected.</span></span> <span data-ttu-id="8dee4-157">他们将继续大约 30 分钟的正常会话。</span><span class="sxs-lookup"><span data-stu-id="8dee4-157">They will continue their sessions as normal for about 30 minutes.</span></span> <span data-ttu-id="8dee4-158">如果主仍未恢复，或管理员未故障切换到备份，然后用户切换到恢复模式下，意味着他们不能执行需要永久性 Lync 服务器上的更改 （如添加联系人） 的任务。</span><span class="sxs-lookup"><span data-stu-id="8dee4-158">If the primary is still not restored, or an administrator has not failed over to the backup, then users are switched to Resiliency mode, meaning that they are unable to perform tasks that require a persistent change on Lync Server (such as adding a contact).</span></span>
  
<span data-ttu-id="8dee4-p114">如果主体和镜像后端服务器均失败，或者其中一台服务器和见证服务器失败，则后端服务器将变得不可用（即使它是仍在工作的主体）。在此情况下，活动用户将在一段时间之后切换至恢复能力模式。</span><span class="sxs-lookup"><span data-stu-id="8dee4-p114">If both the principal and the mirror Back End Servers fail, or if one of those servers and the witness fails, the Back End Server will become unavailable (even if it is the principal that is still working). In this case, active users are switched to Resiliency mode after some time.</span></span>
  
## <a name="alwayson-availability-groups-and-alwayson-failover-cluster-instances"></a><span data-ttu-id="8dee4-161">AlwaysOn 可用性组和 AlwaysOn 故障转移群集实例</span><span class="sxs-lookup"><span data-stu-id="8dee4-161">AlwaysOn Availability Groups and AlwaysOn Failover Cluster Instances</span></span>

<span data-ttu-id="8dee4-162">仅在 SQL Server 2014年企业版和 SQL Server 2012年企业版支持 AlwaysOn 可用性组和 AlwaysOn 故障转移群集实例。</span><span class="sxs-lookup"><span data-stu-id="8dee4-162">AlwaysOn Availability Groups and AlwaysOn Failover Cluster Instances are supported only on SQL Server 2014 Enterprise Edition and SQL Server 2012 Enterprise Edition.</span></span> <span data-ttu-id="8dee4-163">Skype 业务服务器仅为主动/被动，不主动/主动支持 AlwaysOn 可用性组。</span><span class="sxs-lookup"><span data-stu-id="8dee4-163">Skype for Business Server supports AlwaysOn Availability Groups only as active/passive, not active/active.</span></span> 
  
<span data-ttu-id="8dee4-164">若要使用 AlwaysOn 可用性组或 AlwaysOn 故障转移群集实例，您首先使用 SQL Server 进行设置和配置的高可用性解决方案。</span><span class="sxs-lookup"><span data-stu-id="8dee4-164">To use AlwaysOn Availability Groups or AlwaysOn Failover Cluster Instances, you first use SQL Server to set up and configure the high availability solution.</span></span> <span data-ttu-id="8dee4-165">然后可以使用拓扑生成器来将它与前端池相关联。</span><span class="sxs-lookup"><span data-stu-id="8dee4-165">You can then use Topology Builder to associate it with a Front End pool.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8dee4-166">AlwaysOn 可用性组的多个实例的实例名称必须相同。</span><span class="sxs-lookup"><span data-stu-id="8dee4-166">Instance names for multiple AlwaysOn Availability Group instances must be the same.</span></span> 
  
<span data-ttu-id="8dee4-167">AlwaysOn 可用性组部署的步骤，请参阅[部署业务服务器 2015年的 Skype 在后端服务器上的 AlwaysOn 可用性组](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md)。</span><span class="sxs-lookup"><span data-stu-id="8dee4-167">For steps for deploying AlwaysOn Availability Groups, see [Deploy an AlwaysOn Availability Group on a Back End Server in Skype for Business Server 2015](../../deploy/deploy-high-availability-and-disaster-recovery/alwayson-availability-group.md).</span></span>
  
## <a name="sql-server-failover-clustering"></a><span data-ttu-id="8dee4-168">SQL Server 故障转移群集</span><span class="sxs-lookup"><span data-stu-id="8dee4-168">SQL Server Failover Clustering</span></span>

<span data-ttu-id="8dee4-169">Skype 业务服务器支持 SQL Server 故障转移群集使用下列数据库软件：</span><span class="sxs-lookup"><span data-stu-id="8dee4-169">Skype for Business Server supports SQL Server failover clustering with the following database software:</span></span>
  
- <span data-ttu-id="8dee4-170">SQL Server 2014 年企业版和标准版</span><span class="sxs-lookup"><span data-stu-id="8dee4-170">SQL Server 2014, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="8dee4-171">SQL Server 2012 SP2 和 CU2，企业版和标准版</span><span class="sxs-lookup"><span data-stu-id="8dee4-171">SQL Server 2012 SP2 and CU2, both Enterprise Edition and Standard Edition</span></span>
    
- <span data-ttu-id="8dee4-172">SQL Server 2008 R2 SP2，企业版和标准版</span><span class="sxs-lookup"><span data-stu-id="8dee4-172">SQL Server 2008 R2 SP2, both Enterprise Edition and Standard Edition</span></span>
    
<span data-ttu-id="8dee4-173">若要使用 SQL 故障切换群集，应首先设置和部署前端池之前配置 SQL Server 群集。</span><span class="sxs-lookup"><span data-stu-id="8dee4-173">To use SQL failover clustering, you should first set up and configure the SQL Server cluster before deploying your Front End pool.</span></span> <span data-ttu-id="8dee4-174">最佳做法和故障转移群集 SQL Server 2012 的安装说明，请参阅[https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8dee4-174">For best practices and setup instructions for failover clustering in SQL Server 2012, see [https://technet.microsoft.com/en-us/library/hh231721.aspx](https://technet.microsoft.com/en-us/library/hh231721.aspx).</span></span> <span data-ttu-id="8dee4-175">有关故障转移群集 SQL Server 2008年中，请参阅[https://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="8dee4-175">For failover clustering in SQL Server 2008, see [https://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx](https://technet.microsoft.com/en-us/library/ms189134%28v=sql.105%29.aspx).</span></span>
  
<span data-ttu-id="8dee4-p118">安装 SQL Server 时，应安装 SQL Server Management Studio 来管理数据库位置和日志文件位置。安装 SQL Server 时，SQL Server Management Studio 将作为可选组件安装。</span><span class="sxs-lookup"><span data-stu-id="8dee4-p118">When you install SQL Server, you should install SQL Server Management Studio to manage the locations for database and log file locations. SQL Server Management Studio is installed as an optional component when you install SQL Server.</span></span>
  

