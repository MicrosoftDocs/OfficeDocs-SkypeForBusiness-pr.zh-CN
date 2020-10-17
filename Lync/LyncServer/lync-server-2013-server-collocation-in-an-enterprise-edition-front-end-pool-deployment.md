---
title: Lync Server 2013 Server 并置 in Enterprise Edition 前端池部署
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Server collocation in an Enterprise Edition Front End pool deployment
ms:assetid: 0516b18d-14c0-4237-9279-0f92e341b1bd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398102(v=OCS.15)
ms:contentKeyID: 48183287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0162a4338a1504ed425015e5b9391fca9903d4ab
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510279"
---
# <a name="server-collocation-in-an-enterprise-edition-front-end-pool-deployment-for-lync-server-2013"></a><span data-ttu-id="ec639-102">适用于 Lync Server 2013 的 Enterprise Edition 前端池部署中的服务器并置</span><span class="sxs-lookup"><span data-stu-id="ec639-102">Server collocation in an Enterprise Edition Front End pool deployment for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec639-103">_**上次修改的主题：** 2013-11-11_</span><span class="sxs-lookup"><span data-stu-id="ec639-103">_**Topic Last Modified:** 2013-11-11_</span></span>

<span data-ttu-id="ec639-104">本节介绍可以在 Lync Server 2013 前端池部署中并置的服务器角色、数据库和文件共享。</span><span class="sxs-lookup"><span data-stu-id="ec639-104">This section describes the server roles, databases, and file shares that you can collocate in a Lync Server 2013 Front End pool deployment.</span></span>

<div>

## <a name="server-roles"></a><span data-ttu-id="ec639-105">服务器角色</span><span class="sxs-lookup"><span data-stu-id="ec639-105">Server Roles</span></span>

<span data-ttu-id="ec639-106">在 Lync Server 2013 中，A/V 会议服务、中介服务、监控和存档在前端服务器上是并置，但需要进行其他配置才能启用它们。</span><span class="sxs-lookup"><span data-stu-id="ec639-106">In Lync Server 2013, A/V Conferencing service, Mediation service, Monitoring, and Archiving are collocated on the Front End Server, but additional configuration is required to enable them.</span></span> <span data-ttu-id="ec639-107">如果您不想将中介服务器与前端服务器并置，则可以在单独的计算机上将其作为独立中介服务器进行部署。</span><span class="sxs-lookup"><span data-stu-id="ec639-107">If you do not want to collocate the Mediation Server with the Front End Server, you can deploy it as a stand-alone Mediation Server on a separate computer.</span></span>

<span data-ttu-id="ec639-108">您可以使用前端服务器并置受信任的应用程序服务器。</span><span class="sxs-lookup"><span data-stu-id="ec639-108">You can collocate a trusted application server with the Front End Server.</span></span>

<span data-ttu-id="ec639-109">必须在单独的计算机上部署以下服务器角色：</span><span class="sxs-lookup"><span data-stu-id="ec639-109">The following server roles must each be deployed on a separate computer:</span></span>

  - <span data-ttu-id="ec639-110">控制器</span><span class="sxs-lookup"><span data-stu-id="ec639-110">Director</span></span>

  - <span data-ttu-id="ec639-111">边缘服务器</span><span class="sxs-lookup"><span data-stu-id="ec639-111">Edge Server</span></span>

  - <span data-ttu-id="ec639-112">如果没有与前端服务器并置的中介服务器 () </span><span class="sxs-lookup"><span data-stu-id="ec639-112">Mediation Server (if not collocated with the Front End Server)</span></span>

  - <span data-ttu-id="ec639-113">Office Web Apps Server</span><span class="sxs-lookup"><span data-stu-id="ec639-113">Office Web Apps Server</span></span>

<span data-ttu-id="ec639-114">您不能并置持久聊天服务器角色与前端服务器。</span><span class="sxs-lookup"><span data-stu-id="ec639-114">You cannot collocate Persistent Chat server role with the Front End Server.</span></span>

</div>

<div>

## <a name="databases"></a><span data-ttu-id="ec639-115">Databases</span><span class="sxs-lookup"><span data-stu-id="ec639-115">Databases</span></span>

<span data-ttu-id="ec639-116">您可以在同一个数据库服务器上并置以下每个数据库：</span><span class="sxs-lookup"><span data-stu-id="ec639-116">You can collocate each of the following databases on the same database server:</span></span>

  - <span data-ttu-id="ec639-117">后端数据库</span><span class="sxs-lookup"><span data-stu-id="ec639-117">Back-end database</span></span>

  - <span data-ttu-id="ec639-118">监控数据库</span><span class="sxs-lookup"><span data-stu-id="ec639-118">Monitoring database</span></span>

  - <span data-ttu-id="ec639-119">存档数据库</span><span class="sxs-lookup"><span data-stu-id="ec639-119">Archiving database</span></span>

  - <span data-ttu-id="ec639-120">持久聊天数据库</span><span class="sxs-lookup"><span data-stu-id="ec639-120">Persistent Chat database</span></span>

  - <span data-ttu-id="ec639-121">持久聊天合规性数据库</span><span class="sxs-lookup"><span data-stu-id="ec639-121">Persistent Chat compliance database</span></span>

<span data-ttu-id="ec639-122">可以在一个 SQL Server 实例中并置任何或全部或所有这些数据库，也可以为每个数据库使用单独的 SQL Server 实例，但具有以下限制：</span><span class="sxs-lookup"><span data-stu-id="ec639-122">You can collocate any or any or all of these databases in a single instance of SQL Server or use a separate instance of SQL Server for each, with the following limitations:</span></span>

  - <span data-ttu-id="ec639-123">每个 SQL Server 实例只能包含一个后端数据库、一个监视数据库、一个存档数据库、一个持久聊天数据库和一个持久聊天合规性数据库。</span><span class="sxs-lookup"><span data-stu-id="ec639-123">Each instance of SQL Server can contain only a single back-end database, a single Monitoring database, a single Archiving database, a single Persistent Chat database, and a single Persistent Chat compliance database.</span></span>

  - <span data-ttu-id="ec639-124">数据库服务器无法支持多个前端池、一个存档部署和一个监视部署，但它可以支持其中一个，而不管数据库是使用相同的 SQL Server 实例还是使用单独的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="ec639-124">The database server cannot support more than one Front End pool, one Archiving deployment, and one Monitoring deployment, but it can support one of each, regardless of whether the databases use the same instance of SQL Server or separate instances of SQL Server.</span></span>

<span data-ttu-id="ec639-125">还可以将文件共享与数据库并置，如本节后面所述。</span><span class="sxs-lookup"><span data-stu-id="ec639-125">You can collocate a file share with the databases, as described later in this section.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ec639-126">在 Lync Server 2013 中，可以选择将存档存储与部署中的部分或所有用户的 Exchange 2013 存储集成。</span><span class="sxs-lookup"><span data-stu-id="ec639-126">In Lync Server 2013, you have the option of integrating Archiving storage with Exchange 2013 storage for some or all users in your deployment.</span></span> <span data-ttu-id="ec639-127">您不能在与 Exchange 存储相同的服务器上部署任何运行 Lync Server 或组件的服务器。</span><span class="sxs-lookup"><span data-stu-id="ec639-127">You cannot deploy any servers running Lync Server or components on the same servers as the Exchange storage.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="ec639-128">尽管支持并置数据库，但数据库的大小增长非常快。</span><span class="sxs-lookup"><span data-stu-id="ec639-128">Although collocation of databases is supported, the size of the databases can grow quickly.</span></span> <span data-ttu-id="ec639-129">例如，当您考虑将存档数据库与其他数据库并置时，您应了解，如果您要对多个用户的消息进行存档，则存档数据库所需的磁盘空间会变得很大。</span><span class="sxs-lookup"><span data-stu-id="ec639-129">For example, when you consider collocating the Archiving database with other databases, be aware that if you are archiving the messages of more than a few users, the disk space needed by the Archiving database can grow very large.</span></span> <span data-ttu-id="ec639-130">因此，我们不建议并置多个数据库（尤其是存档数据库、持久聊天数据库或与后端数据库的持久聊天合规性数据库）。</span><span class="sxs-lookup"><span data-stu-id="ec639-130">For this reason, we do not recommend collocating multiple databases, especially the Archiving database, the Persistent Chat database, or the Persistent Chat compliance database with the back-end database.</span></span>



</div>

</div>

<div>

## <a name="file-share"></a><span data-ttu-id="ec639-131">文件共享</span><span class="sxs-lookup"><span data-stu-id="ec639-131">File Share</span></span>

<span data-ttu-id="ec639-132">文件共享可以配置为一台单独的服务器，也可以并置以下任意服务器或所有服务器上：</span><span class="sxs-lookup"><span data-stu-id="ec639-132">The file share can be a separate server or can be collocated on the same server as any or all of the following:</span></span>

  - <span data-ttu-id="ec639-133">数据库服务器，包括 Enterprise Edition 前端池的后端服务器</span><span class="sxs-lookup"><span data-stu-id="ec639-133">Database server, including the Back End Server of an Enterprise Edition Front End pool</span></span>

  - <span data-ttu-id="ec639-134">存档数据库</span><span class="sxs-lookup"><span data-stu-id="ec639-134">Archiving database</span></span>

  - <span data-ttu-id="ec639-135">监控数据库</span><span class="sxs-lookup"><span data-stu-id="ec639-135">Monitoring database</span></span>

  - <span data-ttu-id="ec639-136">持久聊天数据库</span><span class="sxs-lookup"><span data-stu-id="ec639-136">Persistent Chat database</span></span>

  - <span data-ttu-id="ec639-137">持久聊天合规性数据库</span><span class="sxs-lookup"><span data-stu-id="ec639-137">Persistent Chat compliance database</span></span>

<span data-ttu-id="ec639-138">单个文件共享可用于多个前端池、Standard Edition 服务器（均位于同一站点）。</span><span class="sxs-lookup"><span data-stu-id="ec639-138">A single file share can be used for multiple Front End pools, Standard Edition servers (all in the same site).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ec639-139">在 Lync Server 2013 中，监视和存档将 Lync Server 文件共享用作前端服务器。</span><span class="sxs-lookup"><span data-stu-id="ec639-139">In Lync Server 2013, Monitoring and Archiving use the Lync Server file share as the Front End Server.</span></span>



</div>

</div>

<div>

## <a name="other-components"></a><span data-ttu-id="ec639-140">其他组件</span><span class="sxs-lookup"><span data-stu-id="ec639-140">Other Components</span></span>

<span data-ttu-id="ec639-141">您不能并置不是 Lync Server 2013 组件的反向代理服务器，但如果您想要支持使用任何 Lync Server 2013 服务器角色的联合用户共享 web 内容，则您的部署中也是必需的。</span><span class="sxs-lookup"><span data-stu-id="ec639-141">You cannot collocate a reverse proxy server, which is not a Lync Server 2013 component, but is required in your deployment if you want to support sharing of web content for federated users with any Lync Server 2013 server role.</span></span> <span data-ttu-id="ec639-142">不过，您可以通过在组织中对其他应用程序使用的现有反向代理服务器上配置支持，来实现对 Lync Server 2013 部署的反向代理支持。</span><span class="sxs-lookup"><span data-stu-id="ec639-142">You can, however, implement reverse proxy support for a Lync Server 2013 deployment by configuring the support on an existing reverse proxy server in your organization that is used for other applications.</span></span>

<span data-ttu-id="ec639-143">您不能并置任何 Exchange 统一消息 (UM) 组件或具有任何 SharePoint Server 角色的 SharePoint 组件。</span><span class="sxs-lookup"><span data-stu-id="ec639-143">You cannot collocate any Exchange Unified Messaging (UM) component or SharePoint component with any SharePoint Server role.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

