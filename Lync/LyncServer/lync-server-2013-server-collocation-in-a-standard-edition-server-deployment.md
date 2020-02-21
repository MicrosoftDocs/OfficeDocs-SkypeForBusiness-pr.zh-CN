---
title: Lync Server 2013 server 并置 in Standard Edition Server 部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1122605aabea32d86fbacd1f23675fcdef687539
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a><span data-ttu-id="537e6-102">适用于 Lync Server 2013 的 Standard Edition server 部署中的服务器并置</span><span class="sxs-lookup"><span data-stu-id="537e6-102">Server collocation in a Standard Edition server deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="537e6-103">_**上次修改的主题：** 2013-01-20_</span><span class="sxs-lookup"><span data-stu-id="537e6-103">_**Topic Last Modified:** 2013-01-20_</span></span>

<span data-ttu-id="537e6-104">本节介绍了可以在 Lync Server 2013 Standard Edition server 部署中并置的服务器角色、数据库和文件共享。</span><span class="sxs-lookup"><span data-stu-id="537e6-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Standard Edition server deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="537e6-105">服务器角色</span><span class="sxs-lookup"><span data-stu-id="537e6-105">Server Roles</span></span>

<span data-ttu-id="537e6-106">在 Lync Server 2013 中，A/V 会议服务、中介服务、监控和存档在 Standard Edition Server 上是并置，但需要进行其他配置才能启用它们。</span><span class="sxs-lookup"><span data-stu-id="537e6-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Standard Edition Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="537e6-107">您可以选择在单独的服务器上部署中介服务。</span><span class="sxs-lookup"><span data-stu-id="537e6-107">You can choose to deploy Mediation service on separate servers.</span></span>

<span data-ttu-id="537e6-108">可以将受信任应用程序服务器与 Standard Edition 服务器并置。</span><span class="sxs-lookup"><span data-stu-id="537e6-108">You can collocate a trusted application server with a Standard Edition server.</span></span>

<span data-ttu-id="537e6-109">必须在单独的计算机上部署以下服务器角色：</span><span class="sxs-lookup"><span data-stu-id="537e6-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="537e6-110">控制器</span><span class="sxs-lookup"><span data-stu-id="537e6-110">Director</span></span>

  - <span data-ttu-id="537e6-111">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="537e6-111">Edge Server</span></span>

  - <span data-ttu-id="537e6-112">中介服务器（如果未与 Standard Edition 服务器并置）</span><span class="sxs-lookup"><span data-stu-id="537e6-112">Mediation Server (if not collocated with the Standard Edition server)</span></span>

  - <span data-ttu-id="537e6-113">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="537e6-113">Office Web Apps Server</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="537e6-114">Databases</span><span class="sxs-lookup"><span data-stu-id="537e6-114">Databases</span></span>

<span data-ttu-id="537e6-115">默认情况下，SQL Server Express 后端数据库并置在 Standard Edition 服务器上。</span><span class="sxs-lookup"><span data-stu-id="537e6-115">By default, the SQL Server Express back-end database is collocated on the Standard Edition server.</span></span> <span data-ttu-id="537e6-116">您不能将其移动到单独的计算机。</span><span class="sxs-lookup"><span data-stu-id="537e6-116">You cannot move it to a separate computer.</span></span> <span data-ttu-id="537e6-117">有一个例外，不能并置 Standard Edition server 上的其他数据库。</span><span class="sxs-lookup"><span data-stu-id="537e6-117">With one exception, you cannot collocate other databases on the Standard Edition server.</span></span> <span data-ttu-id="537e6-118">如果选择在 Standard Edition server 上部署持久聊天服务器，则可以在同一 Standard Edition 服务器上并置持久聊天数据库和持久聊天合规性数据库。</span><span class="sxs-lookup"><span data-stu-id="537e6-118">If you choose to deploy Persistent Chat Server on a Standard Edition server, you can collocate the Persistent chat database and the Persistent Chat Compliance database on the same Standard Edition server.</span></span>

<span data-ttu-id="537e6-119">您还可以在一个单独的数据库服务器上并置以下每个数据库：</span><span class="sxs-lookup"><span data-stu-id="537e6-119">You can collocate each of the following databases on a single database server:</span></span>

  - <span data-ttu-id="537e6-120">监控数据库</span><span class="sxs-lookup"><span data-stu-id="537e6-120">Monitoring database</span></span>

  - <span data-ttu-id="537e6-121">存档数据库</span><span class="sxs-lookup"><span data-stu-id="537e6-121">Archiving database</span></span>

  - <span data-ttu-id="537e6-122">Enterprise Edition 前端池的后端数据库</span><span class="sxs-lookup"><span data-stu-id="537e6-122">A back-end database for an Enterprise Edition Front End pool</span></span>

<span data-ttu-id="537e6-123">您可以在单一的 SQL 实例中并置上述任意或所有数据库，或针对每个数据库使用一个单独的 SQL 实例，但有以下限制：</span><span class="sxs-lookup"><span data-stu-id="537e6-123">You can collocate any or any or all of these databases in a single SQL instance or use a separate SQL instances for each, with the following limitations:</span></span>

  - <span data-ttu-id="537e6-124">每个 SQL 实例只能包含一个后端数据库（用于 Enterprise Edition 前端池）、一个监控数据库、一个存档数据库、一个持久聊天数据库以及一个持久聊天合规性数据库。</span><span class="sxs-lookup"><span data-stu-id="537e6-124">Each SQL instance can contain only a single back-end database (for an Enterprise Edition Front End pool), single Monitoring database, single Archiving database, single persistent chat database, and single persistent chat compliance database.</span></span>

  - <span data-ttu-id="537e6-125">数据库服务器无法支持多个 Enterprise Edition 前端池、一台运行存档的服务器、一台运行监控的服务器、单个持久聊天数据库和单个持久聊天合规性数据库，但它可以支持其中一种无论数据库是使用相同的 SQL Server 实例还是使用单独的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="537e6-125">The database server cannot support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, single Persistent Chat database, and single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="537e6-126">还可以将文件共享与数据库并置，如本节后面所述。</span><span class="sxs-lookup"><span data-stu-id="537e6-126">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="537e6-127">在 Lync Server 2013 中，可以选择将监控和存档存储与部署中的部分或所有用户的 Exchange 2013 存储集成。</span><span class="sxs-lookup"><span data-stu-id="537e6-127">In Lync Server 2013, you have the option of integrating Monitoring and Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="537e6-128">您不能在与 Exchange 存储相同的服务器上部署任何运行 Lync Server 或组件的服务器。</span><span class="sxs-lookup"><span data-stu-id="537e6-128">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="537e6-129">尽管支持并置数据库，但数据库的大小增长非常快。</span><span class="sxs-lookup"><span data-stu-id="537e6-129">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="537e6-130">例如，当您考虑将存档数据库与其他数据库并置时，您应了解，如果您要对多个用户的消息进行存档，则存档数据库所需的磁盘空间会变得很大。</span><span class="sxs-lookup"><span data-stu-id="537e6-130">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="537e6-131">因此，我们不建议并置多个数据库（尤其是存档数据库、持久聊天数据库和持久聊天合规性数据库）与企业版池的后端数据库一起使用。</span><span class="sxs-lookup"><span data-stu-id="537e6-131">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, Persistent Chat database, and Persistent Chat compliance database with the back-end database of an Enterprise pool.</span></span>



</div>

</div>

<div>

## <a name="file-shares"></a><span data-ttu-id="537e6-132">文件共享</span><span class="sxs-lookup"><span data-stu-id="537e6-132">File Shares</span></span>

<span data-ttu-id="537e6-133">文件共享可以配置为一台单独的服务器，也可以并置以下任意服务器或所有服务器上：</span><span class="sxs-lookup"><span data-stu-id="537e6-133">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="537e6-134">数据库服务器，包括 Enterprise Edition 前端池的后端服务器</span><span class="sxs-lookup"><span data-stu-id="537e6-134">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="537e6-135">存档数据库</span><span class="sxs-lookup"><span data-stu-id="537e6-135">Archiving database</span></span>

  - <span data-ttu-id="537e6-136">监控数据库</span><span class="sxs-lookup"><span data-stu-id="537e6-136">Monitoring database</span></span>

  - <span data-ttu-id="537e6-137">持久聊天数据库</span><span class="sxs-lookup"><span data-stu-id="537e6-137">Persistent Chat database</span></span>

  - <span data-ttu-id="537e6-138">持久聊天合规性数据库</span><span class="sxs-lookup"><span data-stu-id="537e6-138">Persistent Chat compliance database</span></span>

<span data-ttu-id="537e6-139">单个文件共享可用于多个前端池、Standard Edition 服务器（均位于同一站点）。</span><span class="sxs-lookup"><span data-stu-id="537e6-139">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="537e6-140">在 Lync Server 2013 中，监视和存档将 Lync Server 文件共享用作 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="537e6-140">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Standard Edition server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="537e6-141">其他组件</span><span class="sxs-lookup"><span data-stu-id="537e6-141">Other Components</span></span>

<span data-ttu-id="537e6-142">您不能并置不是 Lync Server 2013 组件的反向代理服务器，但如果您想要支持使用任何 Lync Server 2013 服务器角色的联合用户共享 web 内容，则您的部署中也是必需的。</span><span class="sxs-lookup"><span data-stu-id="537e6-142">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="537e6-143">不过，您可以通过在组织中对其他应用程序使用的现有反向代理服务器上配置支持，来实现对 Lync Server 2013 部署的反向代理支持。</span><span class="sxs-lookup"><span data-stu-id="537e6-143">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="537e6-144">您不能并置任何具有任何 Lync Server 2013 角色的 Exchange UM 组件或 SharePoint 组件。</span><span class="sxs-lookup"><span data-stu-id="537e6-144">You cannot collocate any Exchange UM component or SharePoint component with any Lync Server 2013 role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

