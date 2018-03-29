---
title: 规划高可用性和灾难恢复持久聊天服务器在 Skype 业务服务器 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 5/17/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 摘要： 阅读本主题，了解如何实现高可用性和灾难恢复计划 Skype 的持久聊天服务器的业务服务器 2015年。
ms.openlocfilehash: 2730d72b47d02772bf2c5c59c819bbe23e8816db
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="c06e0-103">规划高可用性和灾难恢复持久聊天服务器在 Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="c06e0-103">Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c06e0-104">**摘要：**阅读本主题，了解如何实现高可用性和灾难恢复计划 Skype 的持久聊天服务器的业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="c06e0-104">**Summary:** Read this topic to learn how to plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="c06e0-105">高可用性和灾难恢复持久聊天服务器需要更多的资源，超出通常需要的完整的操作。</span><span class="sxs-lookup"><span data-stu-id="c06e0-105">High availability and disaster recovery for Persistent Chat Server require additional resources beyond what is typically needed for full operation.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c06e0-106">不支持为持久聊天服务器数据库使用 SQL AlwaysOn 高可用性组。</span><span class="sxs-lookup"><span data-stu-id="c06e0-106">Using SQL AlwaysOn Availability Groups is not supported with Persistent Chat Server databases.</span></span> 
  
## <a name="resource-requirements"></a><span data-ttu-id="c06e0-107">资源要求</span><span class="sxs-lookup"><span data-stu-id="c06e0-107">Resource requirements</span></span>

<span data-ttu-id="c06e0-108">在配置之前持续聊天服务器的高可用性和灾难恢复，请确保您具有以下附加资源。</span><span class="sxs-lookup"><span data-stu-id="c06e0-108">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following additional resources.</span></span> 
  
- <span data-ttu-id="c06e0-109">位于持久聊天服务器服务的家庭前端位于同一个物理数据中心的一个专用的数据库实例。</span><span class="sxs-lookup"><span data-stu-id="c06e0-109">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="c06e0-110">此数据库将作为持久聊天的主数据库的 SQL Server 镜像。</span><span class="sxs-lookup"><span data-stu-id="c06e0-110">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="c06e0-111">（可选） 指定其他 SQL Server 作为镜像见证，如果您希望自动故障转移到镜像数据库。</span><span class="sxs-lookup"><span data-stu-id="c06e0-111">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>
    
- <span data-ttu-id="c06e0-112">一个位于其他物理数据中心的专用数据库实例。</span><span class="sxs-lookup"><span data-stu-id="c06e0-112">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="c06e0-113">此数据库将用作 SQL Server 日志传送辅助数据库的主数据中心中的数据库。</span><span class="sxs-lookup"><span data-stu-id="c06e0-113">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>
    
- <span data-ttu-id="c06e0-114">要用作 SQL Server 辅助数据库镜像的一个专用的数据库实例。</span><span class="sxs-lookup"><span data-stu-id="c06e0-114">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="c06e0-115">（可选） 将到服务器的其他 SQL Server 指定为镜像的见证。</span><span class="sxs-lookup"><span data-stu-id="c06e0-115">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="c06e0-116">它们都必须位于辅助数据库所在的同一物理数据中心。</span><span class="sxs-lookup"><span data-stu-id="c06e0-116">Both of these must be located in the same physical data center as the secondary database.</span></span>
    
- <span data-ttu-id="c06e0-117">如果启用了持久聊天服务器的符合性，其他的三个专用的数据库实例是必需的。</span><span class="sxs-lookup"><span data-stu-id="c06e0-117">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="c06e0-118">及其分布是持久聊天数据库前面介绍的相同。</span><span class="sxs-lookup"><span data-stu-id="c06e0-118">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="c06e0-119">实现法规遵从性数据库共享同一个 SQL Server 实例作为持久聊天数据库时，建议使用具有高可用性和灾难恢复能力的独立实例。</span><span class="sxs-lookup"><span data-stu-id="c06e0-119">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, standalone instances for high availability and disaster recovery are recommended.</span></span>
    
- <span data-ttu-id="c06e0-120">必须创建并指派给 SQL Server 日志传送事务日志的文件共享。</span><span class="sxs-lookup"><span data-stu-id="c06e0-120">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="c06e0-121">运行数据库持久聊天这两个数据中心中的所有 SQL 服务器必须都具有访问该文件共享的读/写访问。</span><span class="sxs-lookup"><span data-stu-id="c06e0-121">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="c06e0-122">此共享不会定义为 FileStore 角色的一部分。</span><span class="sxs-lookup"><span data-stu-id="c06e0-122">This share is not defined as part of a FileStore role.</span></span>
    
- <span data-ttu-id="c06e0-123">文件共享辅助数据库服务器作为主服务器的文件共享复制 SQL Server 事务日志的目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="c06e0-123">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>
    
## <a name="disaster-recovery-and-high-availability-solutions"></a><span data-ttu-id="c06e0-124">灾难恢复和高可用性解决方案</span><span class="sxs-lookup"><span data-stu-id="c06e0-124">Disaster recovery and high availability solutions</span></span>

<span data-ttu-id="c06e0-125">Skype 业务服务器为后端服务器，包括数据库镜像支持高可用性的多个模式。</span><span class="sxs-lookup"><span data-stu-id="c06e0-125">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="c06e0-126">有关详细信息，请参阅[规划高可用性和灾难恢复业务服务器 2015年的 Skype](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="c06e0-126">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> 
  
<span data-ttu-id="c06e0-127">本主题中所述的永久性聊天服务器的灾难恢复解决方案构建在拉伸的持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="c06e0-127">The disaster recovery solution for Persistent Chat Server described in this topic is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="c06e0-128">这不要求具有扩展的虚拟局域网 (VLAN)。</span><span class="sxs-lookup"><span data-stu-id="c06e0-128">There is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="c06e0-129">通过拉伸永久聊天服务器池，在逻辑上，配置一个池拓扑中，但实际将服务器放在两个不同的数据中心中的池。</span><span class="sxs-lookup"><span data-stu-id="c06e0-129">By stretching a Persistent Chat Server pool, you configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="c06e0-130">你以相同方式为数据库配置 SQL Server 镜像，并在同一数据中心中部署数据库和镜像。</span><span class="sxs-lookup"><span data-stu-id="c06e0-130">You configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="c06e0-131">需要在辅助数据中心中配置一个备份数据库（在灾难恢复期间，用可选镜像来提供高可用性）。</span><span class="sxs-lookup"><span data-stu-id="c06e0-131">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="c06e0-132">这是在灾难恢复期间用于故障转移的备份数据库。</span><span class="sxs-lookup"><span data-stu-id="c06e0-132">This is the backup database used for failover during disaster recovery.</span></span> 
  
<span data-ttu-id="c06e0-133">有关如何配置持久聊天服务器的高可用性和灾难恢复的详细信息，请参阅[配置高可用性和业务服务器 2015年的 Skype 的持久聊天服务器的灾难恢复](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="c06e0-133">For details about how to configure high availability and disaster recovery for Persistent Chat Server, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span> 
  
<span data-ttu-id="c06e0-134">下图显示了如何在两个不同的拉伸的池拓扑配置持久聊天服务器池：</span><span class="sxs-lookup"><span data-stu-id="c06e0-134">The following figures show how the Persistent Chat Server pool can be configured in two different stretched pool topologies:</span></span>
  
- <span data-ttu-id="c06e0-135">拉伸永久聊天服务器池具有高的带宽低延迟地区位于数据中心时。</span><span class="sxs-lookup"><span data-stu-id="c06e0-135">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>
    
- <span data-ttu-id="c06e0-136">拉伸永久聊天服务器池地区位于较低的带宽高滞后时间与数据中心时。</span><span class="sxs-lookup"><span data-stu-id="c06e0-136">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>
    
<span data-ttu-id="c06e0-137">图 1 显示了数据中心是具有高的带宽低延迟地区位于拉伸的持久聊天服务器池拓扑。</span><span class="sxs-lookup"><span data-stu-id="c06e0-137">Figure 1 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span> <span data-ttu-id="c06e0-138">假设逻辑和物理拓扑的如下：</span><span class="sxs-lookup"><span data-stu-id="c06e0-138">Assume the following for the logical and physical topologies:</span></span>
  
- <span data-ttu-id="c06e0-139">逻辑拓扑包含以下组件：</span><span class="sxs-lookup"><span data-stu-id="c06e0-139">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="c06e0-140">跨站点 1 和 2 的持久聊天池，包含服务器 1 到 8。</span><span class="sxs-lookup"><span data-stu-id="c06e0-140">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="c06e0-141">前端服务器池、 持久聊天数据库镜像的数据库，并见证数据库 （图中未显示） （可选） 物理上位于站点 1。</span><span class="sxs-lookup"><span data-stu-id="c06e0-141">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="c06e0-142">物理驻留在站点 2 上的第二个前端服务器池和一个备份数据库。</span><span class="sxs-lookup"><span data-stu-id="c06e0-142">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="c06e0-143">物理拓扑包括站点 1 和 2，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c06e0-143">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="c06e0-144">站点 1 上的持久聊天池，包含服务器 1 到 4，两台活动，两台空闲。</span><span class="sxs-lookup"><span data-stu-id="c06e0-144">A Persistent Chat pool, containing servers 1 through 4, two active, two idle on Site 1.</span></span>
    
  - <span data-ttu-id="c06e0-145">站点 5 上的持久聊天池，包含服务器 2 到 8，两台活动，两台空闲。</span><span class="sxs-lookup"><span data-stu-id="c06e0-145">A Persistent Chat pool, containing servers 5 through 8, two active, two idle on Site 2.</span></span>
    
  - <span data-ttu-id="c06e0-146">前端服务器池、 持久聊天数据库镜像的数据库，并 （可选） 见证服务器上的数据库 （图中未显示） 站点 1。</span><span class="sxs-lookup"><span data-stu-id="c06e0-146">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="c06e0-147">站点 2 上的一个前端服务器池和一个备份数据库（作为 SQL 日志传送目标）。</span><span class="sxs-lookup"><span data-stu-id="c06e0-147">A Front End Server Pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="c06e0-148">**当数据中心地理位置，具有高的带宽低滞后时间的拉伸持久聊天服务器池**</span><span class="sxs-lookup"><span data-stu-id="c06e0-148">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency**</span></span>

![持久聊天拉伸的池，含高带宽/低延迟](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
<span data-ttu-id="c06e0-150">图 2 显示了数据中心是以较低的带宽高延迟地区位于拉伸的持久聊天服务器池拓扑。</span><span class="sxs-lookup"><span data-stu-id="c06e0-150">Figure 2 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>
  
- <span data-ttu-id="c06e0-151">逻辑拓扑包含以下组件：</span><span class="sxs-lookup"><span data-stu-id="c06e0-151">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="c06e0-152">跨站点 1 和 2 的持久聊天池，包含服务器 1 到 8。</span><span class="sxs-lookup"><span data-stu-id="c06e0-152">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="c06e0-153">前端服务器池、 持久聊天数据库镜像的数据库，并见证数据库 （图中未显示） （可选） 物理上位于站点 1。</span><span class="sxs-lookup"><span data-stu-id="c06e0-153">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="c06e0-154">物理驻留在站点 2 上的第二个前端服务器池和一个备份数据库。</span><span class="sxs-lookup"><span data-stu-id="c06e0-154">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="c06e0-155">物理拓扑包括站点 1 和 2，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c06e0-155">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="c06e0-156">站点 1 上的持久聊天池，包含服务器 1 到 4，全部处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="c06e0-156">A Persistent Chat pool, containing servers 1 through 4, all active, on Site 1.</span></span>
    
  - <span data-ttu-id="c06e0-157">站点 2 上的持久聊天池，包含服务器 5 到 8，全部处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="c06e0-157">A Persistent Chat pool, containing servers 5 through 8, all idle, on Site 2.</span></span>
    
  - <span data-ttu-id="c06e0-158">前端服务器池、 持久聊天数据库镜像的数据库，并 （可选） 见证服务器上的数据库 （图中未显示） 站点 1。</span><span class="sxs-lookup"><span data-stu-id="c06e0-158">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="c06e0-159">站点 2 上的一个前端服务器池和一个备份数据库（作为 SQL 日志传送目标）。</span><span class="sxs-lookup"><span data-stu-id="c06e0-159">A Front End Server pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="c06e0-160">**较低的带宽高滞后时间与地理定位数据中心时的拉伸持久聊天服务器池**</span><span class="sxs-lookup"><span data-stu-id="c06e0-160">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency**</span></span>

![持久聊天拉伸的池，含低带宽/高延迟](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

