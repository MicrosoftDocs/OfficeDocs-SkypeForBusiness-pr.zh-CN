---
title: Lync Server 2013：用于存档的组件和拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Components and topologies for Archiving
ms:assetid: 5893063d-a44a-4034-aba9-cbe883ecf710
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204916(v=OCS.15)
ms:contentKeyID: 48184213
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c434fd8216689b42e664b5b421101470ad984bf2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="7a919-102">Lync Server 2013 中用于存档的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="7a919-102">Components and topologies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a919-103">_**主题上次修改时间:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="7a919-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="7a919-104">如果要将 Lync Server 2013 IM 和会议内容存档, 可以在 Lync Server 中实现存档。</span><span class="sxs-lookup"><span data-stu-id="7a919-104">If you want to archive Lync Server 2013 IM and conferencing content, you can implement Archiving in Lync Server.</span></span>

<div>

## <a name="archiving-components"></a><span data-ttu-id="7a919-105">存档组件</span><span class="sxs-lookup"><span data-stu-id="7a919-105">Archiving Components</span></span>

<span data-ttu-id="7a919-106">存档功能包括以下组件:</span><span class="sxs-lookup"><span data-stu-id="7a919-106">The Archiving feature includes the following components:</span></span>

  - <span data-ttu-id="7a919-107">**存档代理**。</span><span class="sxs-lookup"><span data-stu-id="7a919-107">**Archiving agents**.</span></span> <span data-ttu-id="7a919-108">存档代理 (也称为统一数据收集代理) 在每个前端池和标准版服务器上自动安装和激活。</span><span class="sxs-lookup"><span data-stu-id="7a919-108">Archiving agents (also known as unified data collection agents) are installed and activated automatically on every Front End pool and Standard Edition server.</span></span> <span data-ttu-id="7a919-109">尽管自动激活了存档代理, 但在启用并正确配置存档之前, 不会实际捕获任何消息。</span><span class="sxs-lookup"><span data-stu-id="7a919-109">Although archiving agents are activated automatically, no messages are actually captured until Archiving is enabled and appropriately configured.</span></span>

  - <span data-ttu-id="7a919-110">**存档数据存储**。</span><span class="sxs-lookup"><span data-stu-id="7a919-110">**Archiving data storage**.</span></span> <span data-ttu-id="7a919-111">Lync Server 2013 的数据存储可以是以下两种情况之一:</span><span class="sxs-lookup"><span data-stu-id="7a919-111">Data storage for Lync Server 2013 can be either of the following:</span></span>
    
      - <span data-ttu-id="7a919-112">Exchange 2013 存储。</span><span class="sxs-lookup"><span data-stu-id="7a919-112">Exchange 2013 storage.</span></span> <span data-ttu-id="7a919-113">如果启用 "Microsoft Exchange 集成" 选项, 则托管在 Exchange 2013 服务器上的用户邮箱将 Exchange 2013 存储用于存档的数据, 但仅当邮箱已放在原地保留时。</span><span class="sxs-lookup"><span data-stu-id="7a919-113">If you enable the Microsoft Exchange integration option, user mailboxes homed on the Exchange 2013 server use Exchange 2013 storage for archived data, but only if the mailboxes have been put on In-Place Hold.</span></span>
    
      - <span data-ttu-id="7a919-114">SQL Server 存储。</span><span class="sxs-lookup"><span data-stu-id="7a919-114">SQL Server storage.</span></span> <span data-ttu-id="7a919-115">如果部署中的用户位于 Lync Server 2013 上托管, 则可以设置运行支持的 SQL Server 版本的存档数据库, 以便为这些用户启用存档。</span><span class="sxs-lookup"><span data-stu-id="7a919-115">If you have users in your deployment who are homed on Lync Server 2013, you can set up Archiving databases that run a supported version of SQL Server to enable archiving for those users.</span></span>

<span data-ttu-id="7a919-116">存档还需要文件存储, 但存档使用与前端服务器或标准版服务器相同的文件存储。</span><span class="sxs-lookup"><span data-stu-id="7a919-116">Archiving also requires file storage, but Archiving uses the same file storage as the Front End Servers or Standard Edition server.</span></span>

<span data-ttu-id="7a919-117">有关存档的硬件和软件要求的列表, 请参阅支持文档中的 lync [server 2013 支持的硬件](lync-server-2013-supported-hardware.md)和[lync server 2013 中的服务器软件和基础结构支持](lync-server-2013-server-software-and-infrastructure-support.md)。</span><span class="sxs-lookup"><span data-stu-id="7a919-117">For a list of hardware and software requirements for Archiving, see [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md) and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="7a919-118">支持的拓扑</span><span class="sxs-lookup"><span data-stu-id="7a919-118">Supported Topologies</span></span>

<span data-ttu-id="7a919-119">在具有需要存档支持的用户的每个池中部署存档。</span><span class="sxs-lookup"><span data-stu-id="7a919-119">You deploy Archiving in each pool that has users that require archiving support.</span></span> <span data-ttu-id="7a919-120">存档在企业版池的前端服务器和标准版服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="7a919-120">Archiving runs on Front End Servers in Enterprise Edition pools and on Standard Edition servers.</span></span> <span data-ttu-id="7a919-121">存档数据存储可能如下所示:</span><span class="sxs-lookup"><span data-stu-id="7a919-121">Archiving data storage can be the following:</span></span>

  - <span data-ttu-id="7a919-122">与 Exchange 2013 存储集成</span><span class="sxs-lookup"><span data-stu-id="7a919-122">Integrated with Exchange 2013 storage</span></span>

  - <span data-ttu-id="7a919-123">使用单独的 SQL Server 数据库进行部署</span><span class="sxs-lookup"><span data-stu-id="7a919-123">Deployed using separate SQL Server databases</span></span>

<span data-ttu-id="7a919-124">如果 Exchange 2013 部署不包括 Lync Server 部署中的所有用户, 则必须为其邮箱在 Exchange 2013 服务器上的主用户使用 Microsoft Exchange 集成, 并且必须为所有其他用户部署单独的 SQL Server 数据库。用于存档的 Lync 用户。</span><span class="sxs-lookup"><span data-stu-id="7a919-124">If your Exchange 2013 deployment does not include all users in your Lync Server deployment, you must use Microsoft Exchange integration for the users whose mailboxes are home on Exchange 2013 servers, and you must deploy separate SQL Server databases for all other Lync users to use for archiving.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="7a919-125">支持的 Collocation</span><span class="sxs-lookup"><span data-stu-id="7a919-125">Supported Collocation</span></span>

<span data-ttu-id="7a919-126">Lync Server 2013 支持各种 collocation 方案, 让你可以灵活地通过在一台服务器 (如果有一个小型组织) 上运行多个组件来节省硬件成本, 或在不同服务器上运行单个组件 (如果你有更大的需要可伸缩性和性能的组织)。</span><span class="sxs-lookup"><span data-stu-id="7a919-126">Lync Server 2013 supports a variety of collocation scenarios, allowing you flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="7a919-127">在决定是否 collocate 组件之前, 一定要考虑可伸缩性因素。</span><span class="sxs-lookup"><span data-stu-id="7a919-127">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="7a919-128">存档部署在池或标准版服务器的前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="7a919-128">Archiving is deployed on the Front End Servers of a pool or Standard Edition servers.</span></span> <span data-ttu-id="7a919-129">有关可在此处 collocated 的组件的详细信息, 请参阅支持文档中的[Lync server 2013 中的支持的服务器 collocation](lync-server-2013-supported-server-collocation.md) 。</span><span class="sxs-lookup"><span data-stu-id="7a919-129">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="7a919-130">如果你将单独的 SQL Server 数据库用于存档, 而不是或除了将存储与 Exchange 2013 存储集成, 则可以使用以下任一项 collocate 存档数据库:</span><span class="sxs-lookup"><span data-stu-id="7a919-130">If you use separate SQL Server databases for Archiving, instead of or in addition to integrating storage with Exchange 2013 storage, you can collocate the Archiving database with any of the following:</span></span>

  - <span data-ttu-id="7a919-131">监控数据库</span><span class="sxs-lookup"><span data-stu-id="7a919-131">Monitoring database</span></span>

  - <span data-ttu-id="7a919-132">企业版前端池的后端数据库</span><span class="sxs-lookup"><span data-stu-id="7a919-132">Back-end database of an Enterprise Edition Front End pool</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="7a919-p108">承载存档数据库的服务器可承载其他数据库。但当您考虑将存档数据库与其他数据库并置时，您应了解，如果要对多个用户的消息进行存档，则存档数据库所需的磁盘空间会变得很大。因此，不建议将存档数据库与后端数据库并置。</span><span class="sxs-lookup"><span data-stu-id="7a919-p108">The server hosting the Archiving database can host other databases. However, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large. For this reason, we do not recommend collocating the Archiving database with the back-end database.</span></span>



</div>

<span data-ttu-id="7a919-136">如果您 collocate 使用监视数据库、后端数据库或这两个数据库中的存档数据库, 则可以为任何或所有数据库使用单个 SQL 实例, 也可以为每个数据库使用单独的 SQL 实例, 如下所示责任</span><span class="sxs-lookup"><span data-stu-id="7a919-136">If you collocate the Archiving database with the Monitoring database, back-end database, or both of these databases, you can either use a single SQL instance for any or all of the databases, or you can use a separate SQL instance for each database, with the following limitation:</span></span>

  - <span data-ttu-id="7a919-137">每个 SQL 实例只能包含一个后端数据库、单个监视数据库和一个存档数据库。</span><span class="sxs-lookup"><span data-stu-id="7a919-137">Each SQL instance can contain only a single back-end database, single Monitoring database, and single Archiving database.</span></span>

<span data-ttu-id="7a919-138">有关所有服务器角色和数据库的 collocation 的详细信息, 请参阅支持文档中的[Lync server 2013 中的支持的服务器 collocation](lync-server-2013-supported-server-collocation.md) 。</span><span class="sxs-lookup"><span data-stu-id="7a919-138">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

