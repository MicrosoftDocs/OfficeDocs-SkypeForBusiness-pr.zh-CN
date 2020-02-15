---
title: Lync Server 2013 数据库软件支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Database software support
ms:assetid: e05d0032-bbea-4e61-987d-d07b1c045fd5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398990(v=OCS.15)
ms:contentKeyID: 48185517
ms.date: 12/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da1ffd79ccfb652c0f853cb027577d477a14d33e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044124"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a><span data-ttu-id="25871-102">Lync Server 2013 中的数据库软件支持</span><span class="sxs-lookup"><span data-stu-id="25871-102">Database software support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="25871-103">_**上次修改的主题：** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="25871-103">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="25871-104">Lync Server 2013 支持以下数据库管理系统：</span><span class="sxs-lookup"><span data-stu-id="25871-104">Lync Server 2013 supports the following database management systems:</span></span>

  - <span data-ttu-id="25871-105">**前端池的后端数据库、存档数据库、监控数据库、持久聊天数据库和持久聊天合规性数据库**</span><span class="sxs-lookup"><span data-stu-id="25871-105">**Back-end database of a Front End pool, Archiving database, Monitoring database, persistent chat database, and persistent chat compliance database**</span></span>
    
      - <span data-ttu-id="25871-106">Microsoft SQL Server 2008 R2 企业版数据库软件（64-位版本）。</span><span class="sxs-lookup"><span data-stu-id="25871-106">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition).</span></span> <span data-ttu-id="25871-107">建议另外运行最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="25871-107">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="25871-108">Microsoft SQL Server 2008 R2 Standard （64-位版本）。</span><span class="sxs-lookup"><span data-stu-id="25871-108">Microsoft SQL Server 2008 R2 Standard (64-bit edition).</span></span> <span data-ttu-id="25871-109">建议另外运行最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="25871-109">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="25871-110">Microsoft SQL Server 2012 Enterprise （64-位版本）。</span><span class="sxs-lookup"><span data-stu-id="25871-110">Microsoft SQL Server 2012 Enterprise (64-bit edition).</span></span> <span data-ttu-id="25871-111">建议另外运行最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="25871-111">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="25871-112">Microsoft SQL Server 2012 Standard （64-位版本）。</span><span class="sxs-lookup"><span data-stu-id="25871-112">Microsoft SQL Server 2012 Standard (64-bit edition).</span></span> <span data-ttu-id="25871-113">建议另外运行最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="25871-113">Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="25871-114">**Standard Edition server 数据库和前端服务器数据库**</span><span class="sxs-lookup"><span data-stu-id="25871-114">**Standard Edition server database and Front End Server databases**</span></span>
    
      - <span data-ttu-id="25871-115">Microsoft SQL Server 2012 Express （64位版本）。</span><span class="sxs-lookup"><span data-stu-id="25871-115">Microsoft SQL Server 2012 Express (64-bit edition).</span></span> <span data-ttu-id="25871-116">建议另外运行最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="25871-116">Additionally running the latest service pack is recommended.</span></span>
        
        <span data-ttu-id="25871-117">我们支持对前端服务器和 Standard Edition 服务器上的 Microsoft SQL Server 进行修补和升级。</span><span class="sxs-lookup"><span data-stu-id="25871-117">We support the patching and upgrade of Microsoft SQL Server on Front End Servers and Standard Edition servers.</span></span> <span data-ttu-id="25871-118">但是，当您在前端服务器上进行任何类型的升级或修补程序时，您必须考虑仲裁要求。</span><span class="sxs-lookup"><span data-stu-id="25871-118">However, when you make any kind of upgrade or patch on Front End Servers, you must account for quorum requirements.</span></span> <span data-ttu-id="25871-119">有关详细信息，请参阅在 lync server [2013 中升级或更新前端服务器](lync-server-2013-upgrade-or-update-front-end-servers.md) [，以及在 lync server 2013 中的前端服务器、即时消息和状态的拓扑和组件](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="25871-119">For more information, see [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) and [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="25871-120">Microsoft SQL Server 2012 Express （64-bit edition）由 Lync Server 2013 自动安装在每个 Standard Edition 服务器和每台前端服务器服务器上。</span><span class="sxs-lookup"><span data-stu-id="25871-120">Microsoft SQL Server 2012 Express (64-bit edition) is automatically installed by Lync Server 2013 on each Standard Edition server and each Front End Server server.</span></span>

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="25871-121">Lync Server 2013 不支持32位版本的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="25871-121">Lync Server 2013 does not support the 32-bit edition of SQL Server.</span></span> <span data-ttu-id="25871-122">必须使用64位版本。</span><span class="sxs-lookup"><span data-stu-id="25871-122">You must use the 64-bit edition.</span></span></P>
> <LI>
> <P><span data-ttu-id="25871-123">SQL Server Web edition 和 SQL Server 工作组版不受支持。</span><span class="sxs-lookup"><span data-stu-id="25871-123">SQL Server Web edition and SQL Server Workgroup edition are not supported.</span></span> <span data-ttu-id="25871-124">不能将它们与 Lync Server 2013 一起使用。</span><span class="sxs-lookup"><span data-stu-id="25871-124">You cannot use them with Lync Server 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="25871-125">Lync Server 2013 支持本机数据库镜像。</span><span class="sxs-lookup"><span data-stu-id="25871-125">Lync Server 2013 does support native database mirroring.</span></span></P>
> <LI>
> <P><span data-ttu-id="25871-126">若要使用监视服务器角色，应安装 SQL Server Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="25871-126">To use the Monitoring Server role, you should install SQL Server Reporting Services.</span></span></P></LI></UL>



</div>

<span data-ttu-id="25871-127">在前端池中，后端数据库可以是单个 SQL Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="25871-127">In a Front End pool, the back-end database can be a single SQL Server computer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="25871-128">如果您并置 Lync Server 数据库与其他数据库，我们强烈建议评估可能影响可用性和性能的所有因素，并确保如果一个节点发生故障，剩余的节点可以处理负载。</span><span class="sxs-lookup"><span data-stu-id="25871-128">If you collocate Lync Server databases with other databases, we highly recommend assessing all factors that might affect availability and performance, as well as ensuring that, if one node fails, the remaining node can handle the load.</span></span> <span data-ttu-id="25871-129">若要验证故障转移功能，建议您测试所有故障转移方案。</span><span class="sxs-lookup"><span data-stu-id="25871-129">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a><span data-ttu-id="25871-130">使用 SQL 镜像和 SQL 群集</span><span class="sxs-lookup"><span data-stu-id="25871-130">Using SQL Mirroring and SQL Clustering</span></span>

<span data-ttu-id="25871-131">Lync Server 2013 支持对每个 Lync Server 数据库使用 SQL 镜像或 SQL 群集。</span><span class="sxs-lookup"><span data-stu-id="25871-131">Lync Server 2013 supports the use of either SQL mirroring or SQL clustering for each Lync Server database.</span></span> <span data-ttu-id="25871-132">您可以使用 Lync Server 2013 中的拓扑生成器工具轻松地设置 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="25871-132">You can easily set up SQL mirroring with the Topology Builder tool in Lync Server 2013.</span></span> <span data-ttu-id="25871-133">对于 SQL 故障转移群集，必须使用 SQL Server 进行安装。</span><span class="sxs-lookup"><span data-stu-id="25871-133">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="25871-134">Lync Server 2013 支持对所有部署（包括 greenfield 部署和从以前版本的 Lync Server 升级的组织）使用 SQL 镜像和 SQL 群集拓扑。</span><span class="sxs-lookup"><span data-stu-id="25871-134">Lync Server 2013 supports both SQL mirroring and SQL clustering topologies for all deployments, including greenfield deployments and organizations that have upgraded from previous versions of Lync Server.</span></span>

<span data-ttu-id="25871-135">SQL 群集支持适用于主动/被动配置。</span><span class="sxs-lookup"><span data-stu-id="25871-135">SQL Clustering support is for an active/passive configuration.</span></span> <span data-ttu-id="25871-136">出于性能原因，被动节点不应由任何其他 SQL 实例共享。</span><span class="sxs-lookup"><span data-stu-id="25871-136">For performance reasons, the passive node should not be shared by any other SQL instance.</span></span>

<span data-ttu-id="25871-137">包括以下支持：</span><span class="sxs-lookup"><span data-stu-id="25871-137">The following support is included:</span></span>

  - <span data-ttu-id="25871-138">针对以下各项的双节点故障转移群集：</span><span class="sxs-lookup"><span data-stu-id="25871-138">Two-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="25871-139">Microsoft SQL Server 2012 Standard （64-位版本）。</span><span class="sxs-lookup"><span data-stu-id="25871-139">Microsoft SQL Server 2012 Standard (64-bit edition).</span></span> <span data-ttu-id="25871-140">建议另外运行最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="25871-140">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="25871-141">Microsoft SQL Server 2008 R2 Standard （64-位版本）。</span><span class="sxs-lookup"><span data-stu-id="25871-141">Microsoft SQL Server 2008 R2 Standard (64-bit edition).</span></span> <span data-ttu-id="25871-142">建议另外运行最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="25871-142">Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="25871-143">针对以下各项的最高配置十六个节点的故障转移群集：</span><span class="sxs-lookup"><span data-stu-id="25871-143">Up to sixteen-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="25871-144">Microsoft SQL Server 2012 Enterprise （64-位版本）。</span><span class="sxs-lookup"><span data-stu-id="25871-144">Microsoft SQL Server 2012 Enterprise (64-bit edition).</span></span> <span data-ttu-id="25871-145">建议另外运行最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="25871-145">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="25871-146">Microsoft SQL Server 2008 R2 企业版数据库软件（64-位版本）。</span><span class="sxs-lookup"><span data-stu-id="25871-146">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition).</span></span> <span data-ttu-id="25871-147">建议另外运行最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="25871-147">Additionally running the latest service pack is recommended.</span></span>

<span data-ttu-id="25871-148">有关 SQL 镜像的详细信息，请参阅[Lync server 2013 中的后端服务器高可用性](lync-server-2013-back-end-server-high-availability.md)。</span><span class="sxs-lookup"><span data-stu-id="25871-148">For more information about SQL mirroring, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span> <span data-ttu-id="25871-149">有关如何部署 SQL 群集的详细信息，请参阅[CONFIGURE SQL Server 集群 For Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md)。</span><span class="sxs-lookup"><span data-stu-id="25871-149">For details on how to deploy SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<span data-ttu-id="25871-150">有关 SQL Server 2012 中故障转移群集的详细信息和最佳实践， <http://technet.microsoft.com/library/hh231721.aspx>请参阅。</span><span class="sxs-lookup"><span data-stu-id="25871-150">For more information and best practices for failover clustering in SQL Server 2012, see <http://technet.microsoft.com/library/hh231721.aspx>.</span></span> <span data-ttu-id="25871-151">有关 SQL Server 2008 中的故障转移群集<http://technet.microsoft.com/library/ms189134(v=sql.105).aspx>，请参阅。</span><span class="sxs-lookup"><span data-stu-id="25871-151">For failover clustering in SQL Server 2008, see <http://technet.microsoft.com/library/ms189134(v=sql.105).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

