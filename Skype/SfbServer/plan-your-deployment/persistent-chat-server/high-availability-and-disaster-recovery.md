---
title: 为 Skype for business Server 2015 中的持久聊天服务器规划高可用性和灾难恢复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 摘要：阅读本主题，了解如何为 Skype for business Server 2015 中的持久聊天服务器规划高可用性和灾难恢复。
ms.openlocfilehash: 08b025b09acc4b4db5f26ae67761412a96c0339c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815740"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="3d041-103">为 Skype for business Server 2015 中的持久聊天服务器规划高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="3d041-103">Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="3d041-104">**摘要：** 阅读本主题，了解如何在 Skype for business Server 2015 中规划持久聊天服务器的高可用性和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="3d041-104">**Summary:** Read this topic to learn how to plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="3d041-105">持久聊天服务器的高可用性和灾难恢复需要更多资源，而不是完全操作所需的资源。</span><span class="sxs-lookup"><span data-stu-id="3d041-105">High availability and disaster recovery for Persistent Chat Server require additional resources beyond what is typically needed for full operation.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="3d041-106">不支持为持久聊天服务器数据库使用 SQL AlwaysOn 高可用性组。</span><span class="sxs-lookup"><span data-stu-id="3d041-106">Using SQL AlwaysOn Availability Groups is not supported with Persistent Chat Server databases.</span></span> 

> [!NOTE] 
> <span data-ttu-id="3d041-107">Skype for business Server 2015 中提供了持久聊天，但 Skype for business Server 2019 不再支持此功能。</span><span class="sxs-lookup"><span data-stu-id="3d041-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="3d041-108">团队中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="3d041-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="3d041-109">有关详细信息，请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。</span><span class="sxs-lookup"><span data-stu-id="3d041-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="3d041-110">如果需要使用持久聊天，您可以选择将需要此功能的用户迁移到团队，或继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="3d041-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="resource-requirements"></a><span data-ttu-id="3d041-111">资源要求</span><span class="sxs-lookup"><span data-stu-id="3d041-111">Resource requirements</span></span>

<span data-ttu-id="3d041-112">在为高可用性和灾难恢复配置持久聊天服务器之前，请确保你具有以下其他资源。</span><span class="sxs-lookup"><span data-stu-id="3d041-112">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following additional resources.</span></span> 
  
- <span data-ttu-id="3d041-113">一个专用数据库实例，位于永久聊天服务器服务的主前端所在的同一物理数据中心。</span><span class="sxs-lookup"><span data-stu-id="3d041-113">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="3d041-114">此数据库将用作主持久聊天数据库的 SQL Server 镜像。</span><span class="sxs-lookup"><span data-stu-id="3d041-114">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="3d041-115">（可选）如果希望自动故障转移到镜像数据库，请指定要用作镜像见证的其他 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="3d041-115">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>
    
- <span data-ttu-id="3d041-116">一个位于其他物理数据中心的专用数据库实例。</span><span class="sxs-lookup"><span data-stu-id="3d041-116">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="3d041-117">此数据库将用作主数据中心中数据库的 SQL Server 日志传送辅助数据库。</span><span class="sxs-lookup"><span data-stu-id="3d041-117">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>
    
- <span data-ttu-id="3d041-118">一个专用数据库实例用作辅助数据库的 SQL Server 镜像。</span><span class="sxs-lookup"><span data-stu-id="3d041-118">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="3d041-119">（可选）将其他 SQL Server 指定为镜像见证服务器。</span><span class="sxs-lookup"><span data-stu-id="3d041-119">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="3d041-120">它们都必须位于辅助数据库所在的同一物理数据中心。</span><span class="sxs-lookup"><span data-stu-id="3d041-120">Both of these must be located in the same physical data center as the secondary database.</span></span>
    
- <span data-ttu-id="3d041-121">如果启用了持久聊天服务器合规性，则需要另外三个专用数据库实例。</span><span class="sxs-lookup"><span data-stu-id="3d041-121">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="3d041-122">其分布与以前为持久聊天数据库所概括的一样。</span><span class="sxs-lookup"><span data-stu-id="3d041-122">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="3d041-123">虽然合规性数据库可能与持久聊天数据库共享相同的 SQL Server 实例，但我们建议使用独立实例进行高可用性和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="3d041-123">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, standalone instances for high availability and disaster recovery are recommended.</span></span>
    
- <span data-ttu-id="3d041-124">必须为 SQL Server 日志传送事务日志创建和指定文件共享。</span><span class="sxs-lookup"><span data-stu-id="3d041-124">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="3d041-125">运行持久聊天数据库的两个数据中心中的所有 SQL 服务器都必须具有对此文件共享的读/写访问权限。</span><span class="sxs-lookup"><span data-stu-id="3d041-125">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="3d041-126">此共享不会定义为 FileStore 角色的一部分。</span><span class="sxs-lookup"><span data-stu-id="3d041-126">This share is not defined as part of a FileStore role.</span></span>
    
- <span data-ttu-id="3d041-127">辅助数据库服务器上的文件共享，用作从主服务器文件共享复制的 SQL Server 事务日志的目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="3d041-127">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>
    
## <a name="disaster-recovery-and-high-availability-solutions"></a><span data-ttu-id="3d041-128">灾难恢复和高可用性解决方案</span><span class="sxs-lookup"><span data-stu-id="3d041-128">Disaster recovery and high availability solutions</span></span>

<span data-ttu-id="3d041-129">Skype for Business 服务器支持对后端服务器的多个高可用性模式，包括数据库镜像。</span><span class="sxs-lookup"><span data-stu-id="3d041-129">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="3d041-130">有关详细信息，请参阅[Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md)。</span><span class="sxs-lookup"><span data-stu-id="3d041-130">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> 
  
<span data-ttu-id="3d041-131">本主题中介绍的持久聊天服务器的灾难恢复解决方案是在永久的持久聊天服务器池中构建的。</span><span class="sxs-lookup"><span data-stu-id="3d041-131">The disaster recovery solution for Persistent Chat Server described in this topic is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="3d041-132">这不要求具有扩展的虚拟局域网 (VLAN)。</span><span class="sxs-lookup"><span data-stu-id="3d041-132">There is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="3d041-133">通过拉伸持久聊天服务器池，可以在拓扑中对一个池进行逻辑配置，但实际将服务器放在两个不同数据中心的池中。</span><span class="sxs-lookup"><span data-stu-id="3d041-133">By stretching a Persistent Chat Server pool, you configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="3d041-134">你以相同方式为数据库配置 SQL Server 镜像，并在同一数据中心中部署数据库和镜像。</span><span class="sxs-lookup"><span data-stu-id="3d041-134">You configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="3d041-135">需要在辅助数据中心中配置一个备份数据库（在灾难恢复期间，用可选镜像来提供高可用性）。</span><span class="sxs-lookup"><span data-stu-id="3d041-135">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="3d041-136">这是在灾难恢复期间用于故障转移的备份数据库。</span><span class="sxs-lookup"><span data-stu-id="3d041-136">This is the backup database used for failover during disaster recovery.</span></span> 
  
<span data-ttu-id="3d041-137">有关如何配置持久聊天服务器的高可用性和灾难恢复的详细信息，请参阅[在 Skype for Business server 2015 中配置持久聊天服务器的高可用性和灾难恢复](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="3d041-137">For details about how to configure high availability and disaster recovery for Persistent Chat Server, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span> 
  
<span data-ttu-id="3d041-138">下图显示了如何在两个不同的延伸池拓扑中配置持久聊天服务器池：</span><span class="sxs-lookup"><span data-stu-id="3d041-138">The following figures show how the Persistent Chat Server pool can be configured in two different stretched pool topologies:</span></span>
  
- <span data-ttu-id="3d041-139">延长的持久聊天服务器池当数据中心位于具有高带宽/低延迟的地域时。</span><span class="sxs-lookup"><span data-stu-id="3d041-139">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>
    
- <span data-ttu-id="3d041-140">延长的持久聊天服务器池，在数据中心位于具有低带宽/高延迟的地域时。</span><span class="sxs-lookup"><span data-stu-id="3d041-140">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>
    
<span data-ttu-id="3d041-141">图1显示了一个持续持续的持久聊天服务器池拓扑，其中数据中心具有高带宽/低延迟的地理位置。</span><span class="sxs-lookup"><span data-stu-id="3d041-141">Figure 1 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span> <span data-ttu-id="3d041-142">假设以下内容适用于逻辑和物理拓扑：</span><span class="sxs-lookup"><span data-stu-id="3d041-142">Assume the following for the logical and physical topologies:</span></span>
  
- <span data-ttu-id="3d041-143">逻辑拓扑包含以下组件：</span><span class="sxs-lookup"><span data-stu-id="3d041-143">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="3d041-144">跨站点 1 和 2 的持久聊天池，包含服务器 1 到 8。</span><span class="sxs-lookup"><span data-stu-id="3d041-144">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="3d041-145">前端服务器池、持久聊天数据库、镜像数据库以及（可选）驻留在站点1上的物理上的见证数据库（不显示在图表中）。</span><span class="sxs-lookup"><span data-stu-id="3d041-145">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="3d041-146">物理驻留在站点 2 上的第二个前端服务器池和一个备份数据库。</span><span class="sxs-lookup"><span data-stu-id="3d041-146">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="3d041-147">物理拓扑包括站点1和2，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3d041-147">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="3d041-148">站点 1 上的持久聊天池，包含服务器 1 到 4，两台活动，两台空闲。</span><span class="sxs-lookup"><span data-stu-id="3d041-148">A Persistent Chat pool, containing servers 1 through 4, two active, two idle on Site 1.</span></span>
    
  - <span data-ttu-id="3d041-149">站点 5 上的持久聊天池，包含服务器 2 到 8，两台活动，两台空闲。</span><span class="sxs-lookup"><span data-stu-id="3d041-149">A Persistent Chat pool, containing servers 5 through 8, two active, two idle on Site 2.</span></span>
    
  - <span data-ttu-id="3d041-150">前端服务器池、持久聊天数据库、镜像数据库，以及（可选）站点1上的见证数据库（不显示在图表中）。</span><span class="sxs-lookup"><span data-stu-id="3d041-150">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="3d041-151">站点 2 上的一个前端服务器池和一个备份数据库（作为 SQL 日志传送目标）。</span><span class="sxs-lookup"><span data-stu-id="3d041-151">A Front End Server Pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="3d041-152">**数据中心按地理位置分布时的扩展持久聊天服务器池（高带宽/低延迟）**</span><span class="sxs-lookup"><span data-stu-id="3d041-152">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency**</span></span>

![持久聊天拉伸的池，含高带宽/低延迟](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
<span data-ttu-id="3d041-154">图2显示了一个持续持续的持久聊天服务器池拓扑，其中数据中心具有较低带宽/高延迟的地理位置。</span><span class="sxs-lookup"><span data-stu-id="3d041-154">Figure 2 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>
  
- <span data-ttu-id="3d041-155">逻辑拓扑包含以下组件：</span><span class="sxs-lookup"><span data-stu-id="3d041-155">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="3d041-156">跨站点 1 和 2 的持久聊天池，包含服务器 1 到 8。</span><span class="sxs-lookup"><span data-stu-id="3d041-156">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="3d041-157">前端服务器池、持久聊天数据库、镜像数据库以及（可选）驻留在站点1上的物理上的见证数据库（不显示在图表中）。</span><span class="sxs-lookup"><span data-stu-id="3d041-157">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="3d041-158">物理驻留在站点 2 上的第二个前端服务器池和一个备份数据库。</span><span class="sxs-lookup"><span data-stu-id="3d041-158">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="3d041-159">物理拓扑包括站点1和2，如下所示：</span><span class="sxs-lookup"><span data-stu-id="3d041-159">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="3d041-160">站点 1 上的持久聊天池，包含服务器 1 到 4，全部处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="3d041-160">A Persistent Chat pool, containing servers 1 through 4, all active, on Site 1.</span></span>
    
  - <span data-ttu-id="3d041-161">站点 2 上的持久聊天池，包含服务器 5 到 8，全部处于空闲状态。</span><span class="sxs-lookup"><span data-stu-id="3d041-161">A Persistent Chat pool, containing servers 5 through 8, all idle, on Site 2.</span></span>
    
  - <span data-ttu-id="3d041-162">前端服务器池、持久聊天数据库、镜像数据库，以及（可选）站点1上的见证数据库（不显示在图表中）。</span><span class="sxs-lookup"><span data-stu-id="3d041-162">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="3d041-163">站点 2 上的一个前端服务器池和一个备份数据库（作为 SQL 日志传送目标）。</span><span class="sxs-lookup"><span data-stu-id="3d041-163">A Front End Server pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="3d041-164">**数据中心按地理位置分布时的扩展持久聊天服务器池（低带宽/高延迟）**</span><span class="sxs-lookup"><span data-stu-id="3d041-164">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency**</span></span>

![持久聊天拉伸的池，含低带宽/高延迟](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

