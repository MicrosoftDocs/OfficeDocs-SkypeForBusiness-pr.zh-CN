---
title: 规划高可用性和灾难恢复对于 Persistent Chat Server in Skype 业务服务器 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 5/17/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 摘要： 阅读本主题可了解如何规划高可用性和灾难恢复对于 Persistent Chat Server in Skype 业务服务器 2015年。
ms.openlocfilehash: 90f01de0ca7efef8fdcda4f03fa4bfaa28bd4fcc
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20971653"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="5f6ef-103">规划高可用性和灾难恢复对于 Persistent Chat Server in Skype 业务服务器 2015</span><span class="sxs-lookup"><span data-stu-id="5f6ef-103">Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5f6ef-104">**摘要：** 阅读本主题可了解如何规划高可用性和灾难恢复对于 Persistent Chat Server in Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-104">**Summary:** Read this topic to learn how to plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="5f6ef-105">高可用性和灾难恢复 for Persistent Chat Server 需要超出通常需要完整的操作的其他资源。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-105">High availability and disaster recovery for Persistent Chat Server require additional resources beyond what is typically needed for full operation.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="5f6ef-106">不支持为持久聊天服务器数据库使用 SQL AlwaysOn 高可用性组。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-106">Using SQL AlwaysOn Availability Groups is not supported with Persistent Chat Server databases.</span></span> 

> [!NOTE] 
> <span data-ttu-id="5f6ef-107">持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="5f6ef-108">中团队提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="5f6ef-109">有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-109">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="5f6ef-110">如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="resource-requirements"></a><span data-ttu-id="5f6ef-111">资源要求</span><span class="sxs-lookup"><span data-stu-id="5f6ef-111">Resource requirements</span></span>

<span data-ttu-id="5f6ef-112">配置持久聊天服务器的高可用性和灾难恢复之前, 确保您具有以下附加资源。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-112">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following additional resources.</span></span> 
  
- <span data-ttu-id="5f6ef-113">位于主页前端的持久聊天服务器服务所在的同一物理数据中心中的一个专用的数据库实例。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-113">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="5f6ef-114">此数据库可作为主持久聊天数据库的 SQL Server 镜像。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-114">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="5f6ef-115">（可选） 指定附加的 SQL Server 充当镜像见证，如果您希望自动故障转移到镜像数据库。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-115">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>
    
- <span data-ttu-id="5f6ef-116">一个位于其他物理数据中心的专用数据库实例。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-116">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="5f6ef-117">此数据库可作为主数据中心中的数据库的 SQL Server 日志传送辅助数据库。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-117">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>
    
- <span data-ttu-id="5f6ef-118">一个专用的数据库实例以用作辅助数据库的 SQL Server 镜像。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-118">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="5f6ef-119">（可选） 指定为镜像见证的服务器到其他 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-119">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="5f6ef-120">它们都必须位于辅助数据库所在的同一物理数据中心。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-120">Both of these must be located in the same physical data center as the secondary database.</span></span>
    
- <span data-ttu-id="5f6ef-121">如果启用持久聊天服务器合规性，则其他三个专用的数据库实例是必需的。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-121">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="5f6ef-122">其通讯组是前面介绍的持久聊天数据库相同。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-122">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="5f6ef-123">可能要共享与持久聊天数据库的同一 SQL Server 实例的合规性数据库时，建议使用的高可用性和灾难恢复的独立实例。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-123">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, standalone instances for high availability and disaster recovery are recommended.</span></span>
    
- <span data-ttu-id="5f6ef-124">必须创建并指定的 SQL Server 日志传送事务日志文件共享。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-124">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="5f6ef-125">运行持久聊天数据库这两个数据中心中的所有 SQL 服务器必须都具有对此文件共享的读/写访问。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-125">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="5f6ef-126">此共享不会定义为 FileStore 角色的一部分。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-126">This share is not defined as part of a FileStore role.</span></span>
    
- <span data-ttu-id="5f6ef-127">文件共享，用作从主服务器文件共享中复制的 SQL Server 事务日志的目标文件夹的辅助数据库服务器上。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-127">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>
    
## <a name="disaster-recovery-and-high-availability-solutions"></a><span data-ttu-id="5f6ef-128">灾难恢复和高可用性解决方案</span><span class="sxs-lookup"><span data-stu-id="5f6ef-128">Disaster recovery and high availability solutions</span></span>

<span data-ttu-id="5f6ef-129">Skype 业务服务器支持的后端服务器，包括数据库镜像高可用性的多个的模式。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-129">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="5f6ef-130">有关详细信息，请参阅[规划高可用性和灾难恢复的业务服务器 2015 Skype 中](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-130">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> 
  
<span data-ttu-id="5f6ef-131">本主题中描述的持久聊天服务器的灾难恢复解决方案是基于拉伸的持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-131">The disaster recovery solution for Persistent Chat Server described in this topic is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="5f6ef-132">这不要求具有扩展的虚拟局域网 (VLAN)。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-132">There is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="5f6ef-133">通过拉伸的持久聊天服务器池，在逻辑上，配置一个池拓扑中，但实际放置在两个不同数据中心中的库中的服务器。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-133">By stretching a Persistent Chat Server pool, you configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="5f6ef-134">你以相同方式为数据库配置 SQL Server 镜像，并在同一数据中心中部署数据库和镜像。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-134">You configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="5f6ef-135">需要在辅助数据中心中配置一个备份数据库（在灾难恢复期间，用可选镜像来提供高可用性）。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-135">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="5f6ef-136">这是在灾难恢复期间用于故障转移的备份数据库。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-136">This is the backup database used for failover during disaster recovery.</span></span> 
  
<span data-ttu-id="5f6ef-137">有关如何 for Persistent Chat Server 配置高可用性和灾难恢复的详细信息，请参阅[配置高可用性和灾难恢复对于 Persistent Chat Server in Skype 的业务服务器 2015年](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-137">For details about how to configure high availability and disaster recovery for Persistent Chat Server, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span> 
  
<span data-ttu-id="5f6ef-138">下图显示如何在两个不同的扩展的池拓扑中配置持久聊天服务器池：</span><span class="sxs-lookup"><span data-stu-id="5f6ef-138">The following figures show how the Persistent Chat Server pool can be configured in two different stretched pool topologies:</span></span>
  
- <span data-ttu-id="5f6ef-139">时的扩展持久聊天服务器池数据中心按地理位置分布的高带宽/低延迟。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-139">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>
    
- <span data-ttu-id="5f6ef-140">时的扩展持久聊天服务器池数据中心按地理位置分布的低带宽/高延迟。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-140">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>
    
<span data-ttu-id="5f6ef-141">图 1 显示了数据中心按地理位置分布的高带宽/低延迟的扩展持久聊天服务器池拓扑。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-141">Figure 1 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span> <span data-ttu-id="5f6ef-142">假设以下的逻辑和物理拓扑：</span><span class="sxs-lookup"><span data-stu-id="5f6ef-142">Assume the following for the logical and physical topologies:</span></span>
  
- <span data-ttu-id="5f6ef-143">逻辑拓扑包含以下组件：</span><span class="sxs-lookup"><span data-stu-id="5f6ef-143">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="5f6ef-144">跨站点 1 和 2 的持久聊天池，包含服务器 1 到 8。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-144">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="5f6ef-145">前端服务器池、 持久聊天数据库镜像的数据库，以及 （不在图表中所示） 见证数据库 （可选） 从物理上隔离驻留在站点 1 上。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-145">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="5f6ef-146">物理驻留在站点 2 上的第二个前端服务器池和一个备份数据库。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-146">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="5f6ef-147">物理拓扑结构组成网站 1 和 2，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5f6ef-147">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="5f6ef-148">站点 1 上的持久聊天池，包含服务器 1 到 4，两台活动，两台空闲。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-148">A Persistent Chat pool, containing servers 1 through 4, two active, two idle on Site 1.</span></span>
    
  - <span data-ttu-id="5f6ef-149">站点 5 上的持久聊天池，包含服务器 2 到 8，两台活动，两台空闲。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-149">A Persistent Chat pool, containing servers 5 through 8, two active, two idle on Site 2.</span></span>
    
  - <span data-ttu-id="5f6ef-150">前端服务器池、 持久聊天数据库镜像的数据库，和 （可选） 见证上的数据库 （不在图表中所示） 站点 1。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-150">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="5f6ef-151">站点 2 上的一个前端服务器池和一个备份数据库（作为 SQL 日志传送目标）。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-151">A Front End Server Pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="5f6ef-152">**数据中心按地理位置分布时的扩展持久聊天服务器池（高带宽/低延迟）**</span><span class="sxs-lookup"><span data-stu-id="5f6ef-152">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency**</span></span>

![持久聊天拉伸的池，含高带宽/低延迟](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
<span data-ttu-id="5f6ef-154">图 2 显示了数据中心按地理位置分布的低带宽/高延迟的扩展持久聊天服务器池拓扑。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-154">Figure 2 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>
  
- <span data-ttu-id="5f6ef-155">逻辑拓扑包含以下组件：</span><span class="sxs-lookup"><span data-stu-id="5f6ef-155">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="5f6ef-156">跨站点 1 和 2 的持久聊天池，包含服务器 1 到 8。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-156">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="5f6ef-157">前端服务器池、 持久聊天数据库镜像的数据库，以及 （不在图表中所示） 见证数据库 （可选） 从物理上隔离驻留在站点 1 上。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-157">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="5f6ef-158">物理驻留在站点 2 上的第二个前端服务器池和一个备份数据库。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-158">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="5f6ef-159">物理拓扑结构组成网站 1 和 2，如下所示：</span><span class="sxs-lookup"><span data-stu-id="5f6ef-159">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="5f6ef-160">站点 1 上的持久聊天池，包含服务器 1 到 4，全部处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-160">A Persistent Chat pool, containing servers 1 through 4, all active, on Site 1.</span></span>
    
  - <span data-ttu-id="5f6ef-161">站点 2 上的持久聊天池，包含服务器 5 到 8，全部处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-161">A Persistent Chat pool, containing servers 5 through 8, all idle, on Site 2.</span></span>
    
  - <span data-ttu-id="5f6ef-162">前端服务器池、 持久聊天数据库镜像的数据库，和 （可选） 见证上的数据库 （不在图表中所示） 站点 1。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-162">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="5f6ef-163">站点 2 上的一个前端服务器池和一个备份数据库（作为 SQL 日志传送目标）。</span><span class="sxs-lookup"><span data-stu-id="5f6ef-163">A Front End Server pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="5f6ef-164">**数据中心按地理位置分布时的扩展持久聊天服务器池（低带宽/高延迟）**</span><span class="sxs-lookup"><span data-stu-id="5f6ef-164">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency**</span></span>

![持久聊天拉伸的池，含低带宽/高延迟](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

