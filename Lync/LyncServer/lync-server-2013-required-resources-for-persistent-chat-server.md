---
title: Lync Server 2013：持久聊天服务器所需的资源
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Required resources
ms:assetid: bce50b95-f3c8-407e-963a-d8896ee77fbc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205211(v=OCS.15)
ms:contentKeyID: 48185255
ms.date: 02/05/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac51432de0a6ca261e42f77d64ef1aa1a615cb6d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823250"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="required-resources-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="06f52-102">Lync Server 2013 持久聊天服务器所需的资源</span><span class="sxs-lookup"><span data-stu-id="06f52-102">Required resources for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06f52-103">_**主题上次修改时间:** 2016-02-05_</span><span class="sxs-lookup"><span data-stu-id="06f52-103">_**Topic Last Modified:** 2016-02-05_</span></span>

<span data-ttu-id="06f52-104">持久聊天服务器的高可用性和灾难恢复需要更多资源, 而不是完全操作所需的资源。</span><span class="sxs-lookup"><span data-stu-id="06f52-104">High availability and disaster recovery for Persistent Chat Server requires additional resources beyond what is typically needed for full operation.</span></span> <span data-ttu-id="06f52-105">在为高可用性和灾难恢复配置持久聊天服务器之前, 请确保除了标准持久聊天服务器操作所需的内容外, 还可以使用以下资源。</span><span class="sxs-lookup"><span data-stu-id="06f52-105">Before configuring Persistent Chat Server for high availability and disaster recovery, ensure that you have the following resources in addition to what is required for standard Persistent Chat Server operation.</span></span> <span data-ttu-id="06f52-106">有关其他配置信息, 请参阅[在 Lync server 2013 中配置持久聊天服务器](lync-server-2013-configuring-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="06f52-106">For additional configuration information, see [Configuring Persistent Chat Server in Lync Server 2013](lync-server-2013-configuring-persistent-chat-server.md).</span></span>

  - <span data-ttu-id="06f52-107">一个专用数据库实例, 位于永久聊天服务器服务的主前端所在的同一物理数据中心。</span><span class="sxs-lookup"><span data-stu-id="06f52-107">One dedicated database instance located in the same physical data center in which the home front end of the Persistent Chat Server service is located.</span></span> <span data-ttu-id="06f52-108">此数据库将用作主持久聊天数据库的 SQL Server 镜像。</span><span class="sxs-lookup"><span data-stu-id="06f52-108">This database will serve as the SQL Server mirror for the primary Persistent Chat database.</span></span> <span data-ttu-id="06f52-109">(可选) 如果希望自动故障转移到镜像数据库, 请指定要用作镜像见证的其他 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="06f52-109">Optionally, designate an additional SQL Server to serve as the mirroring witness if you want an automated failover to the mirror database.</span></span>

  - <span data-ttu-id="06f52-110">一个位于其他物理数据中心的专用数据库实例。</span><span class="sxs-lookup"><span data-stu-id="06f52-110">One dedicated database instance located in the other physical data center.</span></span> <span data-ttu-id="06f52-111">此数据库将用作主数据中心中数据库的 SQL Server 日志传送辅助数据库。</span><span class="sxs-lookup"><span data-stu-id="06f52-111">This database will serve as the SQL Server Log Shipping secondary database for the database in the primary data center.</span></span>

  - <span data-ttu-id="06f52-112">一个专用数据库实例用作辅助数据库的 SQL Server 镜像。</span><span class="sxs-lookup"><span data-stu-id="06f52-112">One dedicated database instance to serve as the SQL Server mirror for the secondary database.</span></span> <span data-ttu-id="06f52-113">(可选) 将其他 SQL Server 指定为镜像见证服务器。</span><span class="sxs-lookup"><span data-stu-id="06f52-113">Optionally, designate an additional SQL Server to server as the mirroring witness.</span></span> <span data-ttu-id="06f52-114">它们都必须位于辅助数据库所在的同一物理数据中心。</span><span class="sxs-lookup"><span data-stu-id="06f52-114">Both of these must be located in the same physical data center as the secondary database.</span></span>

  - <span data-ttu-id="06f52-115">如果启用了持久聊天服务器合规性, 则需要另外三个专用数据库实例。</span><span class="sxs-lookup"><span data-stu-id="06f52-115">If Persistent Chat Server compliance is enabled, an additional three dedicated database instances are required.</span></span> <span data-ttu-id="06f52-116">其分布与以前为持久聊天数据库所概括的一样。</span><span class="sxs-lookup"><span data-stu-id="06f52-116">Their distribution is the same as those previously outlined for the Persistent Chat database.</span></span> <span data-ttu-id="06f52-117">虽然合规性数据库可能与持久聊天数据库共享相同的 SQL Server 实例, 但我们建议将独立实例用于高可用性和灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="06f52-117">While it is possible for the compliance database to share the same SQL Server instance as the Persistent Chat database, we recommend standalone instances for high availability and disaster recovery.</span></span>

  - <span data-ttu-id="06f52-118">必须为 SQL Server 日志传送事务日志创建和指定文件共享。</span><span class="sxs-lookup"><span data-stu-id="06f52-118">A file share must be created and designated for the SQL Server Log Shipping transaction logs.</span></span> <span data-ttu-id="06f52-119">运行持久聊天数据库的两个数据中心中的所有 SQL 服务器都必须具有对此文件共享的读/写访问权限。</span><span class="sxs-lookup"><span data-stu-id="06f52-119">All SQL Servers in both data centers that run Persistent Chat databases must have read/write access to this file share.</span></span> <span data-ttu-id="06f52-120">此共享不会定义为 FileStore 角色的一部分。</span><span class="sxs-lookup"><span data-stu-id="06f52-120">This share is not defined as part of a FileStore role.</span></span>

  - <span data-ttu-id="06f52-121">辅助数据库服务器上的文件共享, 用作从主服务器文件共享复制的 SQL Server 事务日志的目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="06f52-121">A file share on the secondary database server to serve as the destination folder for the SQL Server transaction logs that are copied from the primary server file share.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="06f52-122">持久聊天服务器池中的活动持久聊天服务器必须与拓扑中定义的下一个跃点 Lync 池驻留在同一个时区中。</span><span class="sxs-lookup"><span data-stu-id="06f52-122">Active Persistent Chat servers in a Persistent Chat Server pool MUST reside in the same time zone as the next hop Lync Pool defined in the topology.</span></span>



</div>

<span data-ttu-id="06f52-123">下图提供了有关如何在两个不同的延伸池拓扑中配置整个持久聊天服务器池的示例:</span><span class="sxs-lookup"><span data-stu-id="06f52-123">The following figures provide examples about how the entire Persistent Chat Server pool can be configured in the two different stretched pool topologies:</span></span>

  - <span data-ttu-id="06f52-124">延长的持久聊天服务器池当数据中心位于具有高带宽/低延迟的地域时。</span><span class="sxs-lookup"><span data-stu-id="06f52-124">Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.</span></span>

  - <span data-ttu-id="06f52-125">延长的持久聊天服务器池, 在数据中心位于具有低带宽/高延迟的地域时。</span><span class="sxs-lookup"><span data-stu-id="06f52-125">Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="06f52-126">下图显示了一种持续的持久聊天服务器池拓扑, 其中数据中心具有高带宽/低延迟的地理位置。</span><span class="sxs-lookup"><span data-stu-id="06f52-126">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with high bandwidth/low latency.</span></span>

<span data-ttu-id="06f52-127">**延长的持久聊天服务器池当数据中心位于具有高带宽/低延迟的地域时。**</span><span class="sxs-lookup"><span data-stu-id="06f52-127">**Stretched Persistent Chat Server pool when data centers are geo-located with high bandwidth/low latency.**</span></span>

<span data-ttu-id="06f52-128">![持久聊天服务器池 HBW 配置测试](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "持久聊天服务器池 HBW 配置测试")</span><span class="sxs-lookup"><span data-stu-id="06f52-128">![Persistent Chat Server pool HBW configuration exam](images/JJ205211.55d10910-c824-41e6-bed2-08d13a2abd65(OCS.15).jpg "Persistent Chat Server pool HBW configuration exam")</span></span>

<span data-ttu-id="06f52-129">下图显示了永久的持久聊天服务器池拓扑, 其中数据中心具有低带宽/高延迟的地理位置。</span><span class="sxs-lookup"><span data-stu-id="06f52-129">The following figure shows a stretched Persistent Chat Server pool topology where data centers are geo-located with low bandwidth/high latency.</span></span>

<span data-ttu-id="06f52-130">**延长的持久聊天服务器池, 在数据中心位于具有低带宽/高延迟的地域时。**</span><span class="sxs-lookup"><span data-stu-id="06f52-130">**Stretched Persistent Chat Server pool when data centers are geo-located with low bandwidth/high latency.**</span></span>

<span data-ttu-id="06f52-131">![持久聊天服务器池 LBW 配置测试](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "持久聊天服务器池 LBW 配置测试")</span><span class="sxs-lookup"><span data-stu-id="06f52-131">![Persistent Chat Server pool LBW configuration exam](images/JJ205211.586b0a3a-3767-4991-944f-ee54389512aa(OCS.15).jpg "Persistent Chat Server pool LBW configuration exam")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

