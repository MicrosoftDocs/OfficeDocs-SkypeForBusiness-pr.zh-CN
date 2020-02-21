---
title: Lync Server 2013：持久聊天服务器所需的资源
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c925a695fd856c4e9c2d272d39f18a7c3d1f78c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214968"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="f9b66-102">Lync Server 2013 中持久聊天服务器所需的资源</span><span class="sxs-lookup"><span data-stu-id="f9b66-102">Required resources for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f9b66-103">_**上次修改的主题：** 2016-02-05_</span><span class="sxs-lookup"><span data-stu-id="f9b66-103">_**Topic Last Modified:** 2016-02-05_</span></span>

<span data-ttu-id="f9b66-104">持久聊天服务器的高可用性和灾难恢复所需的资源超出了完整操作通常所需的其他资源。</span><span class="sxs-lookup"><span data-stu-id="f9b66-104">High availability and disaster recovery for Persistent Chat Server requires additional resources beyond what is typically needed for full operation.</span></span> <span data-ttu-id="f9b66-105">在将持久聊天服务器配置为实现高可用性和灾难恢复之前，请确保除了标准持久聊天服务器操作所需的资源之外，还可以使用以下资源。</span><span class="sxs-lookup"><span data-stu-id="f9b66-105">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following resources in addition to what is required for standard Persistent Chat Server operation.</span></span> <span data-ttu-id="f9b66-106">有关其他配置信息，请参阅[在 Lync server 2013 中配置持久聊天服务器](lync-server-2013-configuring-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="f9b66-106">For additional configuration information, see [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span></span>

  - <span data-ttu-id="f9b66-107">一个专用数据库实例位于持久聊天服务器服务的主前端所在的同一物理数据中心。</span><span class="sxs-lookup"><span data-stu-id="f9b66-107">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="f9b66-108">此数据库将充当主持久聊天数据库的 SQL Server 镜像。</span><span class="sxs-lookup"><span data-stu-id="f9b66-108">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="f9b66-109">（可选）如果希望自动故障转移到镜像数据库，则指定其他 SQL Server 作为镜像见证。</span><span class="sxs-lookup"><span data-stu-id="f9b66-109">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>

  - <span data-ttu-id="f9b66-110">一个位于其他物理数据中心的专用数据库实例。</span><span class="sxs-lookup"><span data-stu-id="f9b66-110">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="f9b66-111">此数据库将充当主数据中心中数据库的 SQL Server 日志传送辅助数据库。</span><span class="sxs-lookup"><span data-stu-id="f9b66-111">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>

  - <span data-ttu-id="f9b66-112">一个专用数据库实例，充当辅助数据库的 SQL Server 镜像。</span><span class="sxs-lookup"><span data-stu-id="f9b66-112">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="f9b66-113">（可选）指定另一个 SQL Server 作为镜像见证服务器。</span><span class="sxs-lookup"><span data-stu-id="f9b66-113">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="f9b66-114">它们都必须位于辅助数据库所在的同一物理数据中心。</span><span class="sxs-lookup"><span data-stu-id="f9b66-114">Both of these must be located in the same physical data center as the secondary database.</span></span>

  - <span data-ttu-id="f9b66-115">如果启用持久聊天服务器合规性，则需要额外的三个专用数据库实例。</span><span class="sxs-lookup"><span data-stu-id="f9b66-115">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="f9b66-116">它们的分布与前面介绍的持久聊天数据库的分布相同。</span><span class="sxs-lookup"><span data-stu-id="f9b66-116">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="f9b66-117">尽管合规性数据库可以与持久聊天数据库共享相同的 SQL Server 实例，但我们建议采用独立实例来实现高可用性和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="f9b66-117">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, we recommend standalone instances for high availability and disaster recovery.</span></span>

  - <span data-ttu-id="f9b66-118">必须为 SQL Server 日志传送事务日志创建和指定文件共享。</span><span class="sxs-lookup"><span data-stu-id="f9b66-118">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="f9b66-119">运行持久聊天数据库的两个数据中心中的所有 SQL 服务器都必须具有对此文件共享的读/写访问权限。</span><span class="sxs-lookup"><span data-stu-id="f9b66-119">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="f9b66-120">此共享不会定义为 FileStore 角色的一部分。</span><span class="sxs-lookup"><span data-stu-id="f9b66-120">This share is not defined as part of a FileStore role.</span></span>

  - <span data-ttu-id="f9b66-121">辅助数据库服务器上的文件共享，用作从主服务器文件共享中复制的 SQL Server 事务日志的目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="f9b66-121">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f9b66-122">持久聊天服务器池中的活动持久聊天服务器必须与拓扑中定义的下一个跃点 Lync 池位于相同的时区。</span><span class="sxs-lookup"><span data-stu-id="f9b66-122">Active Persistent Chat servers in a Persistent Chat Server pool MUST reside in the same time zone as the next hop Lync Pool defined in the topology.</span></span>



</div>

<span data-ttu-id="f9b66-123">下图提供了有关如何在两个不同的延伸池拓扑中配置整个持久聊天服务器池的示例：</span><span class="sxs-lookup"><span data-stu-id="f9b66-123">The following figures provide examples about how the entire Persistent Chat Server pool can be configured in the two different stretched pool topologies:</span></span>

  - <span data-ttu-id="f9b66-124">数据中心按地理位置分布时的扩展持久聊天服务器池（高带宽/低延迟）。</span><span class="sxs-lookup"><span data-stu-id="f9b66-124">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>

  - <span data-ttu-id="f9b66-125">数据中心按地理位置分布时的扩展持久聊天服务器池（低带宽/高延迟）。</span><span class="sxs-lookup"><span data-stu-id="f9b66-125">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="f9b66-126">下图显示了持续的持久聊天服务器池拓扑，其中数据中心具有高带宽/低延迟的地理位置。</span><span class="sxs-lookup"><span data-stu-id="f9b66-126">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span>

<span data-ttu-id="f9b66-127">**数据中心按地理位置分布时的扩展持久聊天服务器池（高带宽/低延迟）。**</span><span class="sxs-lookup"><span data-stu-id="f9b66-127">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.**</span></span>

<span data-ttu-id="f9b66-128">![持久聊天服务器池 HBW 配置考试](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "持久聊天服务器池 HBW 配置考试")</span><span class="sxs-lookup"><span data-stu-id="f9b66-128">![Persistent Chat Server pool HBW configuration exam](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Persistent Chat Server pool HBW configuration exam")</span></span>

<span data-ttu-id="f9b66-129">下图显示了连续的持久聊天服务器池拓扑，其中数据中心的地理位置为低带宽/高延迟。</span><span class="sxs-lookup"><span data-stu-id="f9b66-129">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="f9b66-130">**数据中心按地理位置分布时的扩展持久聊天服务器池（低带宽/高延迟）。**</span><span class="sxs-lookup"><span data-stu-id="f9b66-130">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.**</span></span>

<span data-ttu-id="f9b66-131">![持久聊天服务器池 LBW 配置考试](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "持久聊天服务器池 LBW 配置考试")</span><span class="sxs-lookup"><span data-stu-id="f9b66-131">![Persistent Chat Server pool LBW configuration exam](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Persistent Chat Server pool LBW configuration exam")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

