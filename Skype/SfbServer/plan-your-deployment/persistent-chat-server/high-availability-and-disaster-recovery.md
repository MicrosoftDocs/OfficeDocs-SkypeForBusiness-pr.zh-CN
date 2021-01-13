---
title: 在 Skype for Business Server 2015 中规划持久聊天服务器的高可用性和灾难恢复
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d9aa622a-95a3-4d8e-8d49-cbfe183f25bf
description: 摘要：阅读本主题，了解如何在 Skype for Business Server 2015 中规划持久聊天服务器的高可用性和灾难恢复。
ms.openlocfilehash: d29271b314981f3de0eb7bd0b963637c554fb26f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832352"
---
# <a name="plan-for-high-availability-and-disaster-recovery-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="127d6-103">在 Skype for Business Server 2015 中规划持久聊天服务器的高可用性和灾难恢复</span><span class="sxs-lookup"><span data-stu-id="127d6-103">Plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="127d6-104">**摘要：** 阅读本主题，了解如何在 Skype for Business Server 2015 中规划持久聊天服务器的高可用性和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="127d6-104">**Summary:** Read this topic to learn how to plan for high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="127d6-105">持久聊天服务器的高可用性和灾难恢复需要除完整操作通常所需的额外资源外的其他资源。</span><span class="sxs-lookup"><span data-stu-id="127d6-105">High availability and disaster recovery for Persistent Chat Server require additional resources beyond what is typically needed for full operation.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="127d6-106">SQL持久聊天服务器数据库不支持使用 AlwaysOn 可用性组。</span><span class="sxs-lookup"><span data-stu-id="127d6-106">Using SQL AlwaysOn Availability Groups is not supported with Persistent Chat Server databases.</span></span> 

> [!NOTE] 
> <span data-ttu-id="127d6-107">持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="127d6-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="127d6-108">Teams 中也提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="127d6-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="127d6-109">有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。</span><span class="sxs-lookup"><span data-stu-id="127d6-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="127d6-110">如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="127d6-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="resource-requirements"></a><span data-ttu-id="127d6-111">资源要求</span><span class="sxs-lookup"><span data-stu-id="127d6-111">Resource requirements</span></span>

<span data-ttu-id="127d6-112">在将持久聊天服务器配置为高可用性和灾难恢复之前，请确保您具有以下其他资源。</span><span class="sxs-lookup"><span data-stu-id="127d6-112">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following additional resources.</span></span> 
  
- <span data-ttu-id="127d6-113">一个专用数据库实例，位于持久聊天服务器服务主前端所在的同一物理数据中心。</span><span class="sxs-lookup"><span data-stu-id="127d6-113">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="127d6-114">此数据库将充当SQL Server持久聊天数据库的镜像。</span><span class="sxs-lookup"><span data-stu-id="127d6-114">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="127d6-115">如果需要自动故障转移到镜像SQL Server，也可以指定其他服务器作为镜像见证。</span><span class="sxs-lookup"><span data-stu-id="127d6-115">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>
    
- <span data-ttu-id="127d6-116">一个位于其他物理数据中心的专用数据库实例。</span><span class="sxs-lookup"><span data-stu-id="127d6-116">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="127d6-117">此数据库将作为主SQL Server数据库的日志传输辅助数据库。</span><span class="sxs-lookup"><span data-stu-id="127d6-117">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>
    
- <span data-ttu-id="127d6-118">一个专用数据库实例，用作SQL Server数据库的镜像。</span><span class="sxs-lookup"><span data-stu-id="127d6-118">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="127d6-119">（可选）将SQL Server服务器指定为镜像见证。</span><span class="sxs-lookup"><span data-stu-id="127d6-119">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="127d6-120">它们都必须位于辅助数据库所在的同一物理数据中心。</span><span class="sxs-lookup"><span data-stu-id="127d6-120">Both of these must be located in the same physical data center as the secondary database.</span></span>
    
- <span data-ttu-id="127d6-121">如果启用持久聊天服务器合规性，则还需要另外三个专用数据库实例。</span><span class="sxs-lookup"><span data-stu-id="127d6-121">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="127d6-122">它们的分布与之前为持久聊天数据库列出的分布相同。</span><span class="sxs-lookup"><span data-stu-id="127d6-122">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="127d6-123">虽然合规性数据库可以与持久聊天SQL Server共享同一实例，但建议使用用于高可用性和灾难恢复的独立实例。</span><span class="sxs-lookup"><span data-stu-id="127d6-123">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, standalone instances for high availability and disaster recovery are recommended.</span></span>
    
- <span data-ttu-id="127d6-124">必须为日志传输事务日志创建和SQL Server文件共享。</span><span class="sxs-lookup"><span data-stu-id="127d6-124">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="127d6-125">两SQL持久聊天数据库的两个数据中心内的所有服务器都必须具有对此文件共享的读/写权限。</span><span class="sxs-lookup"><span data-stu-id="127d6-125">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="127d6-126">此共享不会定义为 FileStore 角色的一部分。</span><span class="sxs-lookup"><span data-stu-id="127d6-126">This share is not defined as part of a FileStore role.</span></span>
    
- <span data-ttu-id="127d6-127">辅助数据库上的文件共享数据库服务器用作从主服务器文件共享复制SQL Server事务日志的目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="127d6-127">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>
    
## <a name="disaster-recovery-and-high-availability-solutions"></a><span data-ttu-id="127d6-128">灾难恢复和高可用性解决方案</span><span class="sxs-lookup"><span data-stu-id="127d6-128">Disaster recovery and high availability solutions</span></span>

<span data-ttu-id="127d6-129">Skype for Business Server 支持后端服务器的多种高可用性模式，包括数据库镜像。</span><span class="sxs-lookup"><span data-stu-id="127d6-129">Skype for Business Server supports multiple modes of high availability for your Back End Servers, including database mirroring.</span></span> <span data-ttu-id="127d6-130">有关详细信息，请参阅 [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="127d6-130">For more information, see [Plan for high availability and disaster recovery in Skype for Business Server 2015](../../plan-your-deployment/high-availability-and-disaster-recovery/high-availability-and-disaster-recovery.md).</span></span> 
  
<span data-ttu-id="127d6-131">本主题中介绍的持久聊天服务器的灾难恢复解决方案基于拉伸的持久聊天服务器池构建。</span><span class="sxs-lookup"><span data-stu-id="127d6-131">The disaster recovery solution for Persistent Chat Server described in this topic is built on a stretched Persistent Chat Server pool.</span></span> <span data-ttu-id="127d6-132">VLAN 中不需要扩展的虚拟 (区域) 。</span><span class="sxs-lookup"><span data-stu-id="127d6-132">There is no requirement for a stretched virtual local area network (VLAN).</span></span> <span data-ttu-id="127d6-133">通过拉伸持久聊天服务器池，可以逻辑地在拓扑中配置一个池，但实际将池中的服务器放在两个不同的数据中心。</span><span class="sxs-lookup"><span data-stu-id="127d6-133">By stretching a Persistent Chat Server pool, you configure one pool in the topology logically, but you physically place the servers in the pool in two different data centers.</span></span> <span data-ttu-id="127d6-134">您可以SQL Server配置数据库的镜像，并在同一数据中心部署数据库和镜像。</span><span class="sxs-lookup"><span data-stu-id="127d6-134">You configure SQL Server mirroring for the database in the same way, and deploy the database and the mirror in the same data center.</span></span> <span data-ttu-id="127d6-135">需要在辅助数据中心中配置一个备份数据库（在灾难恢复期间，用可选镜像来提供高可用性）。</span><span class="sxs-lookup"><span data-stu-id="127d6-135">You need to configure a backup database in the secondary data center (with an optional mirror to provide high availability during disaster recovery).</span></span> <span data-ttu-id="127d6-136">这是在灾难恢复期间用于故障转移的备份数据库。</span><span class="sxs-lookup"><span data-stu-id="127d6-136">This is the backup database used for failover during disaster recovery.</span></span> 
  
<span data-ttu-id="127d6-137">若要详细了解如何为持久聊天服务器配置高可用性和灾难恢复，请参阅在 Skype [for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md)中为持久聊天服务器配置高可用性和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="127d6-137">For details about how to configure high availability and disaster recovery for Persistent Chat Server, see [Configure high availability and disaster recovery for Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/configure-hadr-for-persistent-chat.md).</span></span> 
  
<span data-ttu-id="127d6-138">下图显示了如何在两个不同的扩展池拓扑中配置持久聊天服务器池：</span><span class="sxs-lookup"><span data-stu-id="127d6-138">The following figures show how the Persistent Chat Server pool can be configured in two different stretched pool topologies:</span></span>
  
- <span data-ttu-id="127d6-139">数据中心按地理位置分布时的扩展持久聊天服务器池（高带宽/低延迟）。</span><span class="sxs-lookup"><span data-stu-id="127d6-139">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>
    
- <span data-ttu-id="127d6-140">数据中心按地理位置分布时的扩展持久聊天服务器池（低带宽/高延迟）。</span><span class="sxs-lookup"><span data-stu-id="127d6-140">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>
    
<span data-ttu-id="127d6-141">图 1 显示了拉伸持久聊天服务器池拓扑，其中数据中心位于地理位置，高带宽/低延迟。</span><span class="sxs-lookup"><span data-stu-id="127d6-141">Figure 1 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span> <span data-ttu-id="127d6-142">为逻辑和物理拓扑假定以下内容：</span><span class="sxs-lookup"><span data-stu-id="127d6-142">Assume the following for the logical and physical topologies:</span></span>
  
- <span data-ttu-id="127d6-143">逻辑拓扑由以下内容组成：</span><span class="sxs-lookup"><span data-stu-id="127d6-143">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="127d6-144">跨站点 1 和站点 2 的持久聊天池，包含服务器 1 到 8。</span><span class="sxs-lookup"><span data-stu-id="127d6-144">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="127d6-145">前端服务器池、持久聊天数据库、镜像数据库以及见证数据库（可选） (未显示在) 站点 1 上。</span><span class="sxs-lookup"><span data-stu-id="127d6-145">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="127d6-146">驻留在站点 2 上的第二个前端服务器池和备份数据库。</span><span class="sxs-lookup"><span data-stu-id="127d6-146">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="127d6-147">物理拓扑由站点 1 和站点 2 组成，如下所示：</span><span class="sxs-lookup"><span data-stu-id="127d6-147">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="127d6-148">一个持久聊天池，包含站点 1 上的服务器 1 到 4、两个活动服务器、两个空闲服务器。</span><span class="sxs-lookup"><span data-stu-id="127d6-148">A Persistent Chat pool, containing servers 1 through 4, two active, two idle on Site 1.</span></span>
    
  - <span data-ttu-id="127d6-149">一个持久聊天池，包含站点 2 上的服务器 5 到 8、两个活动服务器和两个空闲服务器。</span><span class="sxs-lookup"><span data-stu-id="127d6-149">A Persistent Chat pool, containing servers 5 through 8, two active, two idle on Site 2.</span></span>
    
  - <span data-ttu-id="127d6-150">前端服务器池、持久聊天数据库、镜像数据库以及见证数据库（可选） (未显示在站点 1 上) 图表中显示的见证数据库池。</span><span class="sxs-lookup"><span data-stu-id="127d6-150">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="127d6-151">站点 2 上的前端服务器池和备份数据库SQL日志寄送目标。</span><span class="sxs-lookup"><span data-stu-id="127d6-151">A Front End Server Pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="127d6-152">**数据中心位于地理位置时扩展的持久聊天服务器池，具有高带宽/低延迟**</span><span class="sxs-lookup"><span data-stu-id="127d6-152">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency**</span></span>

![具有高带宽/低延迟的持久聊天拉伸池](../../media/55cf3d4b-5f51-4d2f-84ca-b4a13dc5eba3.png)
  
<span data-ttu-id="127d6-154">图 2 显示了一个拉伸的持久聊天服务器池拓扑，其中数据中心位于地理位置，低带宽/高延迟。</span><span class="sxs-lookup"><span data-stu-id="127d6-154">Figure 2 shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>
  
- <span data-ttu-id="127d6-155">逻辑拓扑由以下内容组成：</span><span class="sxs-lookup"><span data-stu-id="127d6-155">The logical topology consists of the following:</span></span>
    
  - <span data-ttu-id="127d6-156">跨站点 1 和站点 2 的持久聊天池，包含服务器 1 到 8。</span><span class="sxs-lookup"><span data-stu-id="127d6-156">A Persistent Chat pool across Sites 1 and 2 containing servers 1 through 8.</span></span>
    
  - <span data-ttu-id="127d6-157">前端服务器池、持久聊天数据库、镜像数据库以及见证数据库（可选） (未显示在) 站点 1 上。</span><span class="sxs-lookup"><span data-stu-id="127d6-157">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) residing physically on Site 1.</span></span> 
    
  - <span data-ttu-id="127d6-158">驻留在站点 2 上的第二个前端服务器池和备份数据库。</span><span class="sxs-lookup"><span data-stu-id="127d6-158">A second Front End Server pool and a backup database residing physically on Site 2.</span></span>
    
- <span data-ttu-id="127d6-159">物理拓扑由站点 1 和站点 2 组成，如下所示：</span><span class="sxs-lookup"><span data-stu-id="127d6-159">The physical topology consists of Sites 1 and 2 as follows:</span></span>
    
  - <span data-ttu-id="127d6-160">站点 1 上的持久聊天池，包含服务器 1 到 4，全部处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="127d6-160">A Persistent Chat pool, containing servers 1 through 4, all active, on Site 1.</span></span>
    
  - <span data-ttu-id="127d6-161">站点 2 上的持久聊天池，包含服务器 5 到 8，所有空闲。</span><span class="sxs-lookup"><span data-stu-id="127d6-161">A Persistent Chat pool, containing servers 5 through 8, all idle, on Site 2.</span></span>
    
  - <span data-ttu-id="127d6-162">前端服务器池、持久聊天数据库、镜像数据库以及见证数据库（可选） (未显示在站点 1 上) 图表中显示的见证数据库池。</span><span class="sxs-lookup"><span data-stu-id="127d6-162">A Front End Server pool, a Persistent Chat database, a mirrored database, and, optionally, a witness database (not shown in diagram) on Site 1.</span></span>
    
  - <span data-ttu-id="127d6-163">站点 2 上的前端服务器池和备份数据库SQL日志寄送目标。</span><span class="sxs-lookup"><span data-stu-id="127d6-163">A Front End Server pool, and a backup database, which is the SQL log shipping target, on Site 2.</span></span>
    
<span data-ttu-id="127d6-164">**数据中心位于地理位置时扩展的持久聊天服务器池，低带宽/高延迟**</span><span class="sxs-lookup"><span data-stu-id="127d6-164">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency**</span></span>

![低带宽/高延迟的持久聊天拉伸池](../../media/40cbd902-57b8-4d57-a61c-cde4e0bd47f0.png)
  

