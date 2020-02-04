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
ms.openlocfilehash: d4c39a51f742266c12f618f687c23c645977ffdb
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728562"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="database-software-support-in-lync-server-2013"></a><span data-ttu-id="4df1c-102">Lync Server 2013 中的数据库软件支持</span><span class="sxs-lookup"><span data-stu-id="4df1c-102">Database software support in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4df1c-103">_**主题上次修改时间：** 2014-12-01_</span><span class="sxs-lookup"><span data-stu-id="4df1c-103">_**Topic Last Modified:** 2014-12-01_</span></span>

<span data-ttu-id="4df1c-104">Lync Server 2013 支持下列数据库管理系统：</span><span class="sxs-lookup"><span data-stu-id="4df1c-104">Lync Server 2013 supports the following database management systems:</span></span>

  - <span data-ttu-id="4df1c-105">**前端池的后端数据库、存档数据库、监控数据库、持久聊天数据库和持久聊天合规性数据库**</span><span class="sxs-lookup"><span data-stu-id="4df1c-105">**Back-end database of a Front End pool, Archiving database, Monitoring database, persistent chat database, and persistent chat compliance database**</span></span>
    
      - <span data-ttu-id="4df1c-p101">Microsoft SQL Server 2008 R2 Enterprise 数据库软件（64 位版本）。此外，建议运行最新的 Service Pack。</span><span class="sxs-lookup"><span data-stu-id="4df1c-p101">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="4df1c-108">Microsoft SQL Server 2008 R2 Standard（64 位版本）。</span><span class="sxs-lookup"><span data-stu-id="4df1c-108">Microsoft SQL Server 2008 R2 Standard (64-bit edition).</span></span> <span data-ttu-id="4df1c-109">此外，建议运行最新的 Service Pack。</span><span class="sxs-lookup"><span data-stu-id="4df1c-109">Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="4df1c-p103">Microsoft SQL Server 2012 Enterprise（64 位版本）。此外，建议运行最新的 Service Pack。</span><span class="sxs-lookup"><span data-stu-id="4df1c-p103">Microsoft SQL Server 2012 Enterprise (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="4df1c-p104">Microsoft SQL Server 2012 Standard（64 位版本）。此外，建议运行最新的 Service Pack。</span><span class="sxs-lookup"><span data-stu-id="4df1c-p104">Microsoft SQL Server 2012 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="4df1c-114">**标准版服务器数据库和前端服务器数据库**</span><span class="sxs-lookup"><span data-stu-id="4df1c-114">**Standard Edition server database and Front End Server databases**</span></span>
    
      - <span data-ttu-id="4df1c-115">Microsoft SQL Server 2012 Express（64 位版本）。</span><span class="sxs-lookup"><span data-stu-id="4df1c-115">Microsoft SQL Server 2012 Express (64-bit edition).</span></span> <span data-ttu-id="4df1c-116">此外，建议运行最新的 Service Pack。</span><span class="sxs-lookup"><span data-stu-id="4df1c-116">Additionally running the latest service pack is recommended.</span></span>
        
        <span data-ttu-id="4df1c-117">我们支持在前端服务器和标准版服务器上修补和升级 Microsoft SQL Server。</span><span class="sxs-lookup"><span data-stu-id="4df1c-117">We support the patching and upgrade of Microsoft SQL Server on Front End Servers and Standard Edition servers.</span></span> <span data-ttu-id="4df1c-118">但是，当您在前端服务器上进行任何类型的升级或修补程序时，必须考虑仲裁要求。</span><span class="sxs-lookup"><span data-stu-id="4df1c-118">However, when you make any kind of upgrade or patch on Front End Servers, you must account for quorum requirements.</span></span> <span data-ttu-id="4df1c-119">有关详细信息，请参阅[Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md)和 [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md)。</span><span class="sxs-lookup"><span data-stu-id="4df1c-119">For more information, see [Upgrade or update Front End Servers in Lync Server 2013](lync-server-2013-upgrade-or-update-front-end-servers.md) and [Topologies and components for Front End Servers, instant messaging, and presence in Lync Server 2013](lync-server-2013-topologies-and-components-for-front-end-servers-instant-messaging-and-presence.md).</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="4df1c-120">Microsoft SQL Server 2012 Express （64位版）由 Lync Server 2013 在每个标准版服务器和每台前端服务器服务器上自动安装。</span><span class="sxs-lookup"><span data-stu-id="4df1c-120">Microsoft SQL Server 2012 Express (64-bit edition) is automatically installed by Lync Server 2013 on each Standard Edition server and each Front End Server server.</span></span>

    
    </div>

<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P><span data-ttu-id="4df1c-121">Lync Server 2013 不支持32位版本的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="4df1c-121">Lync Server 2013 does not support the 32-bit edition of SQL Server.</span></span> <span data-ttu-id="4df1c-122">必须使用 64 位版本。</span><span class="sxs-lookup"><span data-stu-id="4df1c-122">You must use the 64-bit edition.</span></span></P>
> <LI>
> <P><span data-ttu-id="4df1c-123">SQL Server Web edition 和 SQL Server 工作组版不受支持。</span><span class="sxs-lookup"><span data-stu-id="4df1c-123">SQL Server Web edition and SQL Server Workgroup edition are not supported.</span></span> <span data-ttu-id="4df1c-124">不能将它们与 Lync Server 2013 一起使用。</span><span class="sxs-lookup"><span data-stu-id="4df1c-124">You cannot use them with Lync Server 2013.</span></span></P>
> <LI>
> <P><span data-ttu-id="4df1c-125">Lync Server 2013 支持本机数据库镜像。</span><span class="sxs-lookup"><span data-stu-id="4df1c-125">Lync Server 2013 does support native database mirroring.</span></span></P>
> <LI>
> <P><span data-ttu-id="4df1c-126">若要使用监视服务器角色，应安装 SQL Server Reporting Services。</span><span class="sxs-lookup"><span data-stu-id="4df1c-126">To use the Monitoring Server role, you should install SQL Server Reporting Services.</span></span></P></LI></UL>



</div>

<span data-ttu-id="4df1c-127">在前端池中，后端数据库可以是单个 SQL Server 计算机。</span><span class="sxs-lookup"><span data-stu-id="4df1c-127">In a Front End pool, the back-end database can be a single SQL Server computer.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="4df1c-128">如果你将 Lync Server 数据库与其他数据库 collocate，我们强烈建议评估可能影响可用性和性能的所有因素，并确保如果一个节点出现故障，则其余节点可以处理该负载。</span><span class="sxs-lookup"><span data-stu-id="4df1c-128">If you collocate Lync Server databases with other databases, we highly recommend assessing all factors that might affect availability and performance, as well as ensuring that, if one node fails, the remaining node can handle the load.</span></span> <span data-ttu-id="4df1c-129">若要验证故障转移功能，建议您测试所有故障转移方案。</span><span class="sxs-lookup"><span data-stu-id="4df1c-129">To verify failover capabilities, we recommend testing all failover scenarios.</span></span>



</div>

<div>

## <a name="using-sql-mirroring-and-sql-clustering"></a><span data-ttu-id="4df1c-130">使用 SQL 镜像和 SQL 群集</span><span class="sxs-lookup"><span data-stu-id="4df1c-130">Using SQL Mirroring and SQL Clustering</span></span>

<span data-ttu-id="4df1c-131">Lync Server 2013 支持对每个 Lync Server 数据库使用 SQL 镜像或 SQL 群集。</span><span class="sxs-lookup"><span data-stu-id="4df1c-131">Lync Server 2013 supports the use of either SQL mirroring or SQL clustering for each Lync Server database.</span></span> <span data-ttu-id="4df1c-132">你可以在 Lync Server 2013 中轻松设置拓扑生成器工具的 SQL 镜像。</span><span class="sxs-lookup"><span data-stu-id="4df1c-132">You can easily set up SQL mirroring with the Topology Builder tool in Lync Server 2013.</span></span> <span data-ttu-id="4df1c-133">对于 SQL 故障转移群集，您必须使用 SQL Server 进行设置。</span><span class="sxs-lookup"><span data-stu-id="4df1c-133">For SQL failover clustering, you must use SQL Server for setup.</span></span>

<span data-ttu-id="4df1c-134">Lync Server 2013 支持针对所有部署（包括全新部署和从早期版本的 Lync Server 升级的组织）的 SQL 镜像和 SQL 群集拓扑。</span><span class="sxs-lookup"><span data-stu-id="4df1c-134">Lync Server 2013 supports both SQL mirroring and SQL clustering topologies for all deployments, including greenfield deployments and organizations that have upgraded from previous versions of Lync Server.</span></span>

<span data-ttu-id="4df1c-p111">SQL 群集支持适用于主动/被动配置。出于性能原因，被动节点不应被任何其他 SQL 实例共享。</span><span class="sxs-lookup"><span data-stu-id="4df1c-p111">SQL Clustering support is for an active/passive configuration. For performance reasons, the passive node should not be shared by any other SQL instance.</span></span>

<span data-ttu-id="4df1c-137">包括以下支持：</span><span class="sxs-lookup"><span data-stu-id="4df1c-137">The following support is included:</span></span>

  - <span data-ttu-id="4df1c-138">针对以下各项的双节点故障转移群集：</span><span class="sxs-lookup"><span data-stu-id="4df1c-138">Two-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="4df1c-p112">Microsoft SQL Server 2012 Standard（64 位版本）。此外，建议运行最新的 Service Pack。</span><span class="sxs-lookup"><span data-stu-id="4df1c-p112">Microsoft SQL Server 2012 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="4df1c-p113">Microsoft SQL Server 2008 R2 Standard（64 位版本）。此外，建议运行最新的 Service Pack。</span><span class="sxs-lookup"><span data-stu-id="4df1c-p113">Microsoft SQL Server 2008 R2 Standard (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

  - <span data-ttu-id="4df1c-143">针对以下各项的最多十六节点的故障转移群集：</span><span class="sxs-lookup"><span data-stu-id="4df1c-143">Up to sixteen-node failover clustering for the following:</span></span>
    
      - <span data-ttu-id="4df1c-p114">Microsoft SQL Server 2012 Enterprise（64 位版本）。此外，建议运行最新的 Service Pack。</span><span class="sxs-lookup"><span data-stu-id="4df1c-p114">Microsoft SQL Server 2012 Enterprise (64-bit edition). Additionally running the latest service pack is recommended.</span></span>
    
      - <span data-ttu-id="4df1c-p115">Microsoft SQL Server 2008 R2 Enterprise 数据库软件（64 位版本）。此外，建议运行最新的 Service Pack。</span><span class="sxs-lookup"><span data-stu-id="4df1c-p115">Microsoft SQL Server 2008 R2 Enterprise database software (64-bit edition). Additionally running the latest service pack is recommended.</span></span>

<span data-ttu-id="4df1c-148">有关 SQL 镜像的详细信息，请参阅[Lync server 2013 中的后端服务器高可用性](lync-server-2013-back-end-server-high-availability.md)。</span><span class="sxs-lookup"><span data-stu-id="4df1c-148">For more information about SQL mirroring, see [Back End Server high availability in Lync Server 2013](lync-server-2013-back-end-server-high-availability.md).</span></span> <span data-ttu-id="4df1c-149">有关如何部署 SQL 群集的详细信息，请参阅[配置 Lync server 2013 的 SQL Server 群集](lync-server-2013-configure-sql-server-clustering.md)。</span><span class="sxs-lookup"><span data-stu-id="4df1c-149">For details on how to deploy SQL clustering, see [Configure SQL Server clustering for Lync Server 2013](lync-server-2013-configure-sql-server-clustering.md).</span></span>

<span data-ttu-id="4df1c-150">有关 SQL Server 2012 中故障转移群集的详细信息和最佳做法， <http://technet.microsoft.com/en-us/library/hh231721.aspx>请参阅。</span><span class="sxs-lookup"><span data-stu-id="4df1c-150">For more information and best practices for failover clustering in SQL Server 2012, see <http://technet.microsoft.com/en-us/library/hh231721.aspx>.</span></span> <span data-ttu-id="4df1c-151">有关 SQL Server 2008 中的故障转移群集<http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>，请参阅。</span><span class="sxs-lookup"><span data-stu-id="4df1c-151">For failover clustering in SQL Server 2008, see <http://technet.microsoft.com/en-us/library/ms189134(v=sql.105).aspx>.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

