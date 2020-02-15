---
title: Lync Server 2013：用于存档的组件和拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Archiving
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204916(v=OCS.15)
ms:contentKeyID: 48184213
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a762219ef6cbecab47dcaeda313ff49dba51ed0b
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="296b5-102">Lync Server 2013 中用于存档的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="296b5-102">Components and topologies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="296b5-103">_**上次修改的主题：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="296b5-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="296b5-104">如果要存档 Lync Server 2013 IM 和会议内容，可以在 Lync Server 中实施存档。</span><span class="sxs-lookup"><span data-stu-id="296b5-104">If you want to archive Lync Server 2013 IM and conferencing content, you can implement Archiving in Lync Server.</span></span>

<div>

## <a name="archiving-components"></a><span data-ttu-id="296b5-105">存档组件</span><span class="sxs-lookup"><span data-stu-id="296b5-105">Archiving Components</span></span>

<span data-ttu-id="296b5-106">存档功能包括以下组件：</span><span class="sxs-lookup"><span data-stu-id="296b5-106">The Archiving feature includes the following components:</span></span>

  - <span data-ttu-id="296b5-p101">**存档代理**。将在每个前端池和 Standard Edition 服务器上自动安装和激活存档代理（也称为“统一数据收集代理”）。尽管会自动激活存档代理，但实际上并不捕获任何消息，除非启用存档并正确配置存档。</span><span class="sxs-lookup"><span data-stu-id="296b5-p101">**Archiving agents**. Archiving agents (also known as unified data collection agents) are installed and activated automatically on every Front End pool and Standard Edition server. Although archiving agents are activated automatically, no messages are actually captured until Archiving is enabled and appropriately configured.</span></span>

  - <span data-ttu-id="296b5-110">**存档数据存储**。</span><span class="sxs-lookup"><span data-stu-id="296b5-110">**Archiving data storage**.</span></span> <span data-ttu-id="296b5-111">Lync Server 2013 的数据存储可以是以下两种情况之一：</span><span class="sxs-lookup"><span data-stu-id="296b5-111">Data storage for Lync Server 2013 can be either of the following:</span></span>
    
      - <span data-ttu-id="296b5-112">Exchange 2013 存储。</span><span class="sxs-lookup"><span data-stu-id="296b5-112">Exchange 2013 storage.</span></span> <span data-ttu-id="296b5-113">如果启用了 Microsoft Exchange 集成选项，则驻留在 Exchange 2013 服务器上的用户邮箱将 Exchange 2013 存储用于存档的数据，但前提是这些邮箱已置于就地保留状态。</span><span class="sxs-lookup"><span data-stu-id="296b5-113">If you enable the Microsoft Exchange integration option, user mailboxes homed on the Exchange 2013 server use Exchange 2013 storage for archived data, but only if the mailboxes have been put on In-Place Hold.</span></span>
    
      - <span data-ttu-id="296b5-114">SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="296b5-114">SQL Server storage.</span></span> <span data-ttu-id="296b5-115">如果您的部署中有用户托管在 Lync Server 2013 上，则可以设置存档数据库，以运行受支持的 SQL Server 版本，以便为这些用户启用存档。</span><span class="sxs-lookup"><span data-stu-id="296b5-115">If you have users in your deployment who are homed on Lync Server 2013, you can set up Archiving databases that run a supported version of SQL Server to enable archiving for those users.</span></span>

<span data-ttu-id="296b5-116">存档还需要文件存储，但是存档使用与前端服务器或 Standard Edition 服务器相同的文件存储。</span><span class="sxs-lookup"><span data-stu-id="296b5-116">Archiving also requires file storage, but Archiving uses the same file storage as the Front End Servers or Standard Edition server.</span></span>

<span data-ttu-id="296b5-117">有关存档的硬件和软件要求的列表，请参阅可支持性文档中的 lync server [2013 支持的硬件](lync-server-2013-supported-hardware.md)和[lync server 2013 中的服务器软件和基础结构支持](lync-server-2013-server-software-and-infrastructure-support.md)。</span><span class="sxs-lookup"><span data-stu-id="296b5-117">For a list of hardware and software requirements for Archiving, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="296b5-118">支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="296b5-118">Supported Topologies</span></span>

<span data-ttu-id="296b5-119">您在每个具有需要存档支持的池中部署存档。</span><span class="sxs-lookup"><span data-stu-id="296b5-119">You deploy Archiving in each pool that has users that require archiving support.</span></span> <span data-ttu-id="296b5-120">存档在企业版池的前端服务器和 Standard Edition 服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="296b5-120">Archiving runs on Front End Servers in Enterprise Edition pools and on Standard Edition servers.</span></span> <span data-ttu-id="296b5-121">存档数据存储可以：</span><span class="sxs-lookup"><span data-stu-id="296b5-121">Archiving data storage can be the following:</span></span>

  - <span data-ttu-id="296b5-122">与 Exchange 2013 存储集成</span><span class="sxs-lookup"><span data-stu-id="296b5-122">Integrated with Exchange 2013 storage</span></span>

  - <span data-ttu-id="296b5-123">使用单独的 SQL Server 数据库部署</span><span class="sxs-lookup"><span data-stu-id="296b5-123">Deployed using separate SQL Server databases</span></span>

<span data-ttu-id="296b5-124">如果您的 Exchange 2013 部署不包括 Lync Server 部署中的所有用户，则您必须为其邮箱位于 Exchange 2013 服务器上的用户使用 Microsoft Exchange 集成，并且您必须为所有其他服务器部署单独的 SQL Server 数据库。用于存档的 Lync 用户。</span><span class="sxs-lookup"><span data-stu-id="296b5-124">If your Exchange 2013 deployment does not include all users in your Lync Server deployment, you must use Microsoft Exchange integration for the users whose mailboxes are home on Exchange 2013 servers, and you must deploy separate SQL Server databases for all other Lync users to use for archiving.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="296b5-125">支持的并置</span><span class="sxs-lookup"><span data-stu-id="296b5-125">Supported Collocation</span></span>

<span data-ttu-id="296b5-126">Lync Server 2013 支持各种并置方案，从而可以灵活地通过在一台服务器（如果有小型组织）上运行多个组件来节省硬件成本，或在不同的服务器上运行单个组件（如果有更大的需要可伸缩性和性能的组织）。</span><span class="sxs-lookup"><span data-stu-id="296b5-126">Lync Server 2013 supports a variety of collocation scenarios, allowing you flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="296b5-127">在决定是否并置组件之前，一定要考虑可伸缩性因素。</span><span class="sxs-lookup"><span data-stu-id="296b5-127">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="296b5-128">存档部署在池或 Standard Edition 服务器的前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="296b5-128">Archiving is deployed on the Front End Servers of a pool or Standard Edition servers.</span></span> <span data-ttu-id="296b5-129">有关可在其中并置的组件的详细信息，请参阅可支持性文档中的[Lync server 2013 中的支持的服务器并置](lync-server-2013-supported-server-collocation.md)。</span><span class="sxs-lookup"><span data-stu-id="296b5-129">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="296b5-130">如果将单独的 SQL Server 数据库用于存档，而不是或除了将存储与 Exchange 2013 存储集成，则可以使用以下任一项对存档数据库进行并置：</span><span class="sxs-lookup"><span data-stu-id="296b5-130">If you use separate SQL Server databases for Archiving, instead of or in addition to integrating storage with Exchange 2013 storage, you can collocate the Archiving database with any of the following:</span></span>

  - <span data-ttu-id="296b5-131">监控数据库</span><span class="sxs-lookup"><span data-stu-id="296b5-131">Monitoring database</span></span>

  - <span data-ttu-id="296b5-132">企业版前端池的后端数据库</span><span class="sxs-lookup"><span data-stu-id="296b5-132">Back-end database of an Enterprise Edition Front End pool</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="296b5-p108">承载存档数据库的服务器可承载其他数据库。但当您考虑将存档数据库与其他数据库并置时，您应了解，如果要对多个用户的消息进行存档，则存档数据库所需的磁盘空间会变得很大。因此，不建议将存档数据库与后端数据库并置。</span><span class="sxs-lookup"><span data-stu-id="296b5-p108">The server hosting the Archiving database can host other databases. However, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large. For this reason, we do not recommend collocating the Archiving database with the back-end database.</span></span>



</div>

<span data-ttu-id="296b5-136">如果将存档数据库与监控数据库、后端数据库或这两个数据库并置，则可以对任一或所有数据库使用单个 SQL 实例，也可以对每个数据库使用一个单独的 SQL 实例，但有以下限制：</span><span class="sxs-lookup"><span data-stu-id="296b5-136">If you collocate the Archiving database with the Monitoring database, back-end database, or both of these databases, you can either use a single SQL instance for any or all of the databases, or you can use a separate SQL instance for each database, with the following limitation:</span></span>

  - <span data-ttu-id="296b5-137">每个 SQL 实例只能包含一个后端数据库，一个监控数据库和一个存档数据库。</span><span class="sxs-lookup"><span data-stu-id="296b5-137">Each SQL instance can contain only a single back-end database, single Monitoring database, and single Archiving database.</span></span>

<span data-ttu-id="296b5-138">有关所有服务器角色和数据库的并置的详细信息，请参阅可支持性文档中的[Lync server 2013 中的支持的服务器并置](lync-server-2013-supported-server-collocation.md)。</span><span class="sxs-lookup"><span data-stu-id="296b5-138">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

