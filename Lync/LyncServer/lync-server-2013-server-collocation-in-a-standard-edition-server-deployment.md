---
title: Standard Edition 服务器部署中的 Lync Server 2013 服务器并置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Server collocation in a Standard Edition server deployment
ms:assetid: 0763ffab-4fd6-463a-8e62-d97876b376d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398131(v=OCS.15)
ms:contentKeyID: 48183314
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 950f2ab06a146ec99ef9ebb2ecbc64c885c82d70
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34821962"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="server-collocation-in-a-standard-edition-server-deployment-for-lync-server-2013"></a><span data-ttu-id="c5899-102">Lync Server 2013 的 Standard Edition 服务器部署中的服务器并置</span><span class="sxs-lookup"><span data-stu-id="c5899-102">Server collocation in a Standard Edition server deployment for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c5899-103">_**主题上次修改时间:** 2013-01-20_</span><span class="sxs-lookup"><span data-stu-id="c5899-103">_**Topic Last Modified:** 2013-01-20_</span></span>

<span data-ttu-id="c5899-104">本部分介绍了可在 Lync Server 2013 标准版服务器部署中 collocate 的服务器角色、数据库和文件共享。</span><span class="sxs-lookup"><span data-stu-id="c5899-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Standard Edition server deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="c5899-105">服务器角色</span><span class="sxs-lookup"><span data-stu-id="c5899-105">Server Roles</span></span>

<span data-ttu-id="c5899-106">在 Lync Server 2013 中, A/V 会议服务、中介服务、监视和存档都在标准版服务器上 collocated, 但需要进行其他配置才能启用它们。</span><span class="sxs-lookup"><span data-stu-id="c5899-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Standard Edition Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="c5899-107">你可以选择在单独的服务器上部署中介服务。</span><span class="sxs-lookup"><span data-stu-id="c5899-107">You can choose to deploy Mediation service on separate servers.</span></span>

<span data-ttu-id="c5899-108">你可以使用标准版服务器 collocate 受信任的应用程序服务器。</span><span class="sxs-lookup"><span data-stu-id="c5899-108">You can collocate a trusted application server with a Standard Edition server.</span></span>

<span data-ttu-id="c5899-109">以下服务器角色必须分别部署在单独的计算机上:</span><span class="sxs-lookup"><span data-stu-id="c5899-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="c5899-110">控制器</span><span class="sxs-lookup"><span data-stu-id="c5899-110">Director</span></span>

  - <span data-ttu-id="c5899-111">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="c5899-111">Edge Server</span></span>

  - <span data-ttu-id="c5899-112">中介服务器 (如果未与标准版服务器 collocated)</span><span class="sxs-lookup"><span data-stu-id="c5899-112">Mediation Server (if not collocated with the Standard Edition server)</span></span>

  - <span data-ttu-id="c5899-113">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="c5899-113">Office Web Apps Server</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="c5899-114">数据库</span><span class="sxs-lookup"><span data-stu-id="c5899-114">Databases</span></span>

<span data-ttu-id="c5899-115">默认情况下, SQL Server Express 后端数据库在标准版服务器上 collocated。</span><span class="sxs-lookup"><span data-stu-id="c5899-115">By default, the SQL Server Express back-end database is collocated on the Standard Edition server.</span></span> <span data-ttu-id="c5899-116">不能将其移动到单独的计算机。</span><span class="sxs-lookup"><span data-stu-id="c5899-116">You cannot move it to a separate computer.</span></span> <span data-ttu-id="c5899-117">除了一个例外, 不能在标准版服务器上 collocate 其他数据库。</span><span class="sxs-lookup"><span data-stu-id="c5899-117">With one exception, you cannot collocate other databases on the Standard Edition server.</span></span> <span data-ttu-id="c5899-118">如果您选择在标准版服务器上部署持久聊天服务器, 则可以在同一标准版服务器上 collocate 持久聊天数据库和持久聊天合规性数据库。</span><span class="sxs-lookup"><span data-stu-id="c5899-118">If you choose to deploy Persistent Chat Server on a Standard Edition server, you can collocate the Persistent chat database and the Persistent Chat Compliance database on the same Standard Edition server.</span></span>

<span data-ttu-id="c5899-119">你可以在单个数据库服务器上 collocate 以下每个数据库:</span><span class="sxs-lookup"><span data-stu-id="c5899-119">You can collocate each of the following databases on a single database server:</span></span>

  - <span data-ttu-id="c5899-120">监控数据库</span><span class="sxs-lookup"><span data-stu-id="c5899-120">Monitoring database</span></span>

  - <span data-ttu-id="c5899-121">存档数据库</span><span class="sxs-lookup"><span data-stu-id="c5899-121">Archiving database</span></span>

  - <span data-ttu-id="c5899-122">适用于企业版前端池的后端数据库</span><span class="sxs-lookup"><span data-stu-id="c5899-122">A back-end database for an Enterprise Edition Front End pool</span></span>

<span data-ttu-id="c5899-123">你可以在单个 SQL 实例中 collocate 任何或所有或所有这些数据库, 或者对每个实例使用单独的 SQL 实例, 但具有以下限制:</span><span class="sxs-lookup"><span data-stu-id="c5899-123">You can collocate any or any or all of these databases in a single SQL instance or use a separate SQL instances for each, with the following limitations:</span></span>

  - <span data-ttu-id="c5899-124">每个 SQL 实例只能包含一个后端数据库 (适用于企业版前端池)、单个监视数据库、单个存档数据库、单个持久聊天数据库和单个持久聊天合规性数据库。</span><span class="sxs-lookup"><span data-stu-id="c5899-124">Each SQL instance can contain only a single back-end database (for an Enterprise Edition Front End pool), single Monitoring database, single Archiving database, single persistent chat database, and single persistent chat compliance database.</span></span>

  - <span data-ttu-id="c5899-125">数据库服务器无法支持多个企业版前端池、一个运行存档的服务器、一个运行监视的服务器、单个持久聊天数据库和单个持久聊天合规性数据库, 但它可以支持其中一种无论数据库使用的是相同的 SQL Server 实例还是 SQL Server 的单独实例。</span><span class="sxs-lookup"><span data-stu-id="c5899-125">The database server cannot support more than one Enterprise Edition Front End pool, one server running Archiving, one server running Monitoring, single Persistent Chat database, and single Persistent Chat compliance database, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="c5899-126">你可以将文件共享与数据库 collocate, 如本节后面部分所述。</span><span class="sxs-lookup"><span data-stu-id="c5899-126">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c5899-127">在 Lync Server 2013 中, 你可以选择将监控和存档存储与部署中的部分或所有用户的 Exchange 2013 存储进行集成。</span><span class="sxs-lookup"><span data-stu-id="c5899-127">In Lync Server 2013, you have the option of integrating Monitoring and Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="c5899-128">不能在 Exchange 存储所在的服务器上部署任何运行 Lync Server 或组件的服务器。</span><span class="sxs-lookup"><span data-stu-id="c5899-128">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="c5899-129">尽管支持 collocation 数据库, 但数据库的大小可以快速增长。</span><span class="sxs-lookup"><span data-stu-id="c5899-129">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="c5899-130">例如, 当你考虑将存档数据库与其他数据库 collocating 时, 请注意, 如果你要对超过几个用户的邮件进行存档, 则存档数据库所需的磁盘空间可能会变得非常大。</span><span class="sxs-lookup"><span data-stu-id="c5899-130">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="c5899-131">出于此原因, 我们不建议使用企业版池后端数据库的多个数据库 (尤其是存档数据库、持久聊天数据库和持久聊天合规性数据库) collocating。</span><span class="sxs-lookup"><span data-stu-id="c5899-131">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, Persistent Chat database, and Persistent Chat compliance database with the back-end database of an Enterprise pool.</span></span>



</div>

</div>

<div>

## <a name="file-shares"></a><span data-ttu-id="c5899-132">文件共享</span><span class="sxs-lookup"><span data-stu-id="c5899-132">File Shares</span></span>

<span data-ttu-id="c5899-133">文件共享可以是单独的服务器, 也可以在同一台服务器上 collocated, 如下所示:</span><span class="sxs-lookup"><span data-stu-id="c5899-133">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="c5899-134">数据库服务器, 包括企业版前端池的后端服务器</span><span class="sxs-lookup"><span data-stu-id="c5899-134">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="c5899-135">存档数据库</span><span class="sxs-lookup"><span data-stu-id="c5899-135">Archiving database</span></span>

  - <span data-ttu-id="c5899-136">监控数据库</span><span class="sxs-lookup"><span data-stu-id="c5899-136">Monitoring database</span></span>

  - <span data-ttu-id="c5899-137">持久聊天数据库</span><span class="sxs-lookup"><span data-stu-id="c5899-137">Persistent Chat database</span></span>

  - <span data-ttu-id="c5899-138">持久聊天合规性数据库</span><span class="sxs-lookup"><span data-stu-id="c5899-138">Persistent Chat compliance database</span></span>

<span data-ttu-id="c5899-139">单个文件共享可用于多个前端池, 标准版服务器 (所有位于同一网站中)。</span><span class="sxs-lookup"><span data-stu-id="c5899-139">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c5899-140">在 Lync Server 2013 中, 监视和存档将 Lync Server 文件共享用作标准版服务器。</span><span class="sxs-lookup"><span data-stu-id="c5899-140">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Standard Edition server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="c5899-141">其他组件</span><span class="sxs-lookup"><span data-stu-id="c5899-141">Other Components</span></span>

<span data-ttu-id="c5899-142">不能 collocate 不是 Lync Server 2013 组件的反向代理服务器, 但如果你希望支持使用任何 Lync Server 2013 服务器角色的联盟用户共享 web 内容, 则你的部署中需要使用该服务器。</span><span class="sxs-lookup"><span data-stu-id="c5899-142">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="c5899-143">但是, 你可以通过在你的组织中针对其他应用程序使用的现有反向代理服务器上配置支持, 从而实现 Lync Server 2013 部署的反向代理支持。</span><span class="sxs-lookup"><span data-stu-id="c5899-143">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="c5899-144">您不能通过任何 Lync Server 2013 角色 collocate 任何 Exchange UM 组件或 SharePoint 组件。</span><span class="sxs-lookup"><span data-stu-id="c5899-144">You cannot collocate any Exchange UM component or SharePoint component with any Lync Server 2013 role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

