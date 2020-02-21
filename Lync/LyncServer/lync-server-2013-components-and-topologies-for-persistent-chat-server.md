---
title: Lync Server 2013：持久聊天服务器的组件和拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components and topologies for Persistent Chat Server
ms:assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398500(v=OCS.15)
ms:contentKeyID: 48184420
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 45707cafca4a7ed9da7cdeb5e162128ccd73468d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191505"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="components-and-topologies-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="8baba-102">Lync Server 2013 中持久聊天服务器的组件和拓扑</span><span class="sxs-lookup"><span data-stu-id="8baba-102">Components and topologies for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8baba-103">_**上次修改的主题：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="8baba-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="8baba-104">持久聊天服务器支持单服务器配置和多服务器配置。</span><span class="sxs-lookup"><span data-stu-id="8baba-104">Persistent Chat Server supports both single-server configurations and multiple-server configurations.</span></span> <span data-ttu-id="8baba-105">持久聊天服务器也可以在 Lync Server 2013 Standard Edition server 上运行。</span><span class="sxs-lookup"><span data-stu-id="8baba-105">Persistent Chat Server can also run on a Lync Server 2013 Standard Edition server.</span></span> <span data-ttu-id="8baba-106">这些配置包含以下持久聊天服务器组件和拓扑。</span><span class="sxs-lookup"><span data-stu-id="8baba-106">These configurations consist of the following Persistent Chat Server components and topologies.</span></span>

<div>

## <a name="persistent-chat-server-components"></a><span data-ttu-id="8baba-107">持久聊天服务器组件</span><span class="sxs-lookup"><span data-stu-id="8baba-107">Persistent Chat Server Components</span></span>

<span data-ttu-id="8baba-108">安装最新版本的持久聊天服务器需要以下组件：</span><span class="sxs-lookup"><span data-stu-id="8baba-108">Installing the latest version of Persistent Chat Server requires the following components:</span></span>

  - <span data-ttu-id="8baba-109">一个或多个运行持久聊天服务器并提供以下服务的计算机：</span><span class="sxs-lookup"><span data-stu-id="8baba-109">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
      - <span data-ttu-id="8baba-110">持久聊天服务</span><span class="sxs-lookup"><span data-stu-id="8baba-110">Persistent Chat service</span></span>
    
      - <span data-ttu-id="8baba-111">合规性服务，在启用合规性时打开</span><span class="sxs-lookup"><span data-stu-id="8baba-111">Compliance service, which is turned on if compliance is enabled</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="8baba-112">在 Lync Server 2013 中，用于文件上载/下载的持久聊天 Web 服务现在并置使用 Lync Server 2013&nbsp;前端服务器。</span><span class="sxs-lookup"><span data-stu-id="8baba-112">In Lync Server 2013, the Persistent Chat Web Services for File Upload/Download is now collocated with Lync Server 2013&nbsp;Front End Server.</span></span><BR><span data-ttu-id="8baba-113">聊天室管理的持久聊天 Web 服务也与 Lync Server 2013&nbsp;前端服务器并置。</span><span class="sxs-lookup"><span data-stu-id="8baba-113">The Persistent Chat Web Services for Chat Room Management is also collocated with Lync Server 2013&nbsp;Front End Server.</span></span>

    
    </div>

  - <span data-ttu-id="8baba-114">服务器（如果使用了镜像，则使用多台服务器）承载 SQL Server 后端数据库，以托管聊天室内容、聊天室和类别的持久聊天内容数据库。</span><span class="sxs-lookup"><span data-stu-id="8baba-114">Server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="8baba-115">后端数据库存储聊天历史记录数据，其中包括有关所创建的类别和持久聊天室的信息。</span><span class="sxs-lookup"><span data-stu-id="8baba-115">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span>

    
    </div>

  - <span data-ttu-id="8baba-116">如果启用了合规性，则为托管持久聊天合规性数据库的服务器（如果使用了多个服务器）承载 SQL Server 后端数据库，其中存储了合规性事件和用于合规性的聊天内容。</span><span class="sxs-lookup"><span data-stu-id="8baba-116">If compliance was enabled, a server(s) (more than one server if mirroring is used) that host the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>

<span data-ttu-id="8baba-117">若要从单独的计算机（如管理控制台）管理持久聊天服务器，请使用计算机上的 Lync Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="8baba-117">To administer Persistent Chat Server from a separate computer (such as an administrative console), use the Lync Server Control Panel on the computer.</span></span> <span data-ttu-id="8baba-118">此计算机必须部署在 Active Directory 域服务域中，林根中至少有一个全局编录服务器。</span><span class="sxs-lookup"><span data-stu-id="8baba-118">This computer must then be deployed in an Active Directory Domain Services domain, with at least one global catalog server in the forest root.</span></span>

<span data-ttu-id="8baba-119">有关持久聊天服务器的硬件和软件要求的详细信息，请参阅可支持性文档中的 lync server [2013 中的 "持久聊天服务器" 的技术要求](lync-server-2013-technical-requirements-for-persistent-chat-server.md)、lync server [2013 支持的硬件](lync-server-2013-supported-hardware.md)以及[Lync server 2013 中的服务器软件和基础结构支持](lync-server-2013-server-software-and-infrastructure-support.md)。</span><span class="sxs-lookup"><span data-stu-id="8baba-119">For details about hardware and software requirements for Persistent Chat Server, see [Technical requirements for Persistent Chat Server in Lync Server 2013](lync-server-2013-technical-requirements-for-persistent-chat-server.md), [Supported hardware for Lync Server 2013](lync-server-2013-supported-hardware.md), and [Server software and infrastructure support in Lync Server 2013](lync-server-2013-server-software-and-infrastructure-support.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="supported-collocation"></a><span data-ttu-id="8baba-120">支持的并置</span><span class="sxs-lookup"><span data-stu-id="8baba-120">Supported Collocation</span></span>

<span data-ttu-id="8baba-121">Lync Server 2013 支持各种并置方案，使您能够通过在一台服务器（如果有小型组织）上运行多个组件来节省硬件成本，或在不同的服务器上运行单个组件（如果您有需要可伸缩性和性能的更大的组织）。</span><span class="sxs-lookup"><span data-stu-id="8baba-121">Lync Server 2013 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="8baba-122">在决定是否并置组件之前，一定要考虑可伸缩性因素。</span><span class="sxs-lookup"><span data-stu-id="8baba-122">Scalability factors should certainly be considered before you decide whether to collocate components.</span></span>

<span data-ttu-id="8baba-123">如果合规性已启用，则持久聊天合规性服务将与 Lync Server 2013 前端服务器并置。</span><span class="sxs-lookup"><span data-stu-id="8baba-123">The Persistent Chat Compliance service, if compliance is enabled, is collocated with the Lync Server 2013 Front End Server.</span></span>

<span data-ttu-id="8baba-124">可以在 Standard Edition server 上部署持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="8baba-124">Persistent Chat Server can be deployed on the Standard Edition server.</span></span> <span data-ttu-id="8baba-125">可以在本地 SQL Server Express 后端服务器上的 Standard Edition server 上并置持久聊天服务器后端服务器和持久聊天合规性数据库。</span><span class="sxs-lookup"><span data-stu-id="8baba-125">The Persistent Chat Server Back End Server and the Persistent Chat Compliance database can be collocated on the Standard Edition server on the local SQL Server Express Back End Server.</span></span> <span data-ttu-id="8baba-126">有关可在其中并置的组件的详细信息，请参阅可支持性文档中的[Lync server 2013 中的支持的服务器并置](lync-server-2013-supported-server-collocation.md)。</span><span class="sxs-lookup"><span data-stu-id="8baba-126">For details about components that can be collocated there, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="8baba-127">对于 Lync Server 2013 Enterprise Edition，不能在 Enterprise Edition Server 上并置持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="8baba-127">For Lync Server 2013 Enterprise Edition, Persistent Chat Servers cannot be collocated on the Enterprise Edition server.</span></span> <span data-ttu-id="8baba-128">持久聊天服务器的 SQL Server 数据库可与 Enterprise Edition 前端池的后端服务器数据库并置。</span><span class="sxs-lookup"><span data-stu-id="8baba-128">The SQL Server database for Persistent Chat Server can be collocated with the Back End Server database of an Enterprise Edition Front End pool.</span></span> <span data-ttu-id="8baba-129">用于持久聊天合规性的 SQL Server 数据库也可以与 Enterprise Edition 池的后端服务器数据库并置。</span><span class="sxs-lookup"><span data-stu-id="8baba-129">The SQL Server database for Persistent Chat compliance can also be collocated with the Back End Server database of an Enterprise Edition pool.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8baba-130">承载持久聊天数据库的服务器可以承载其他数据库。</span><span class="sxs-lookup"><span data-stu-id="8baba-130">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="8baba-131">但是，当您考虑并置将持久聊天数据库与其他数据库一起使用时，请注意，如果存储的邮件超过几个用户，则持久聊天数据库所需的磁盘空间可能会变得非常大。</span><span class="sxs-lookup"><span data-stu-id="8baba-131">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="8baba-132">因此，我们不建议并置持久聊天数据库与后端数据库。</span><span class="sxs-lookup"><span data-stu-id="8baba-132">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span>



</div>

<span data-ttu-id="8baba-133">如果使用后端数据库并置持久聊天数据库，则可以对任意或所有数据库使用单个 SQL Server 实例，也可以对每个数据库使用单独的 SQL Server 实例，但有以下限制：</span><span class="sxs-lookup"><span data-stu-id="8baba-133">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database, with the following limitation:</span></span>

  - <span data-ttu-id="8baba-134">每个 SQL Server 实例只能包含一个后端数据库和一个持久聊天数据库。</span><span class="sxs-lookup"><span data-stu-id="8baba-134">Each instance of SQL Server can contain only a single back-end database and a single Persistent Chat database.</span></span>

<span data-ttu-id="8baba-135">有关所有服务器角色和数据库的并置的详细信息，请参阅可支持性文档中的[Lync server 2013 中的支持的服务器并置](lync-server-2013-supported-server-collocation.md)。</span><span class="sxs-lookup"><span data-stu-id="8baba-135">For details about collocation of all server roles and databases, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

</div>

<div>

## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="8baba-136">持久聊天服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="8baba-136">Persistent Chat Server Topologies</span></span>

<span data-ttu-id="8baba-137">持久聊天服务器支持下列拓扑：</span><span class="sxs-lookup"><span data-stu-id="8baba-137">Persistent Chat Server supports the following topologies:</span></span>

  - <span data-ttu-id="8baba-138">Lync Server 2013 Enterprise Edition 单服务器持久聊天服务器前端服务器</span><span class="sxs-lookup"><span data-stu-id="8baba-138">Lync Server 2013 Enterprise Edition single server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="8baba-139">Lync Server 2013 企业版多服务器持久聊天服务器前端服务器</span><span class="sxs-lookup"><span data-stu-id="8baba-139">Lync Server 2013 Enterprise Edition multiple server Persistent Chat Server Front End Server</span></span>

  - <span data-ttu-id="8baba-140">使用 SQL Server Express 的 Lync Server 2013 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="8baba-140">Lync Server 2013 Standard Edition server using SQL Server Express</span></span>

  - <span data-ttu-id="8baba-141">使用 Standard Edition server 作为下一个跃点服务器的独立服务器上的 Lync Server 2013 Standard Edition server 和持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="8baba-141">Lync Server 2013 Standard Edition server and Persistent Chat Server on a separate server using Standard Edition server as the next hop server.</span></span>

<span data-ttu-id="8baba-142">您可以使用拓扑生成器将持久聊天服务器添加到 Lync Server 2013 部署中。</span><span class="sxs-lookup"><span data-stu-id="8baba-142">You can add Persistent Chat Server to your Lync Server 2013 deployment by using Topology Builder.</span></span> <span data-ttu-id="8baba-143">可以将单个服务器或多服务器持久聊天服务器池添加到拓扑中。</span><span class="sxs-lookup"><span data-stu-id="8baba-143">You can add a single server or a multiple server Persistent Chat Server pool to your topology.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8baba-144">使用拓扑生成器创建具有单个服务器的持久聊天服务器池之后，不能向该池添加其他服务器。</span><span class="sxs-lookup"><span data-stu-id="8baba-144">After you create a Persistent Chat Server pool with a single server by using Topology Builder, you cannot add additional servers to the pool.</span></span>



</div>

<div>

## <a name="single-server-topology"></a><span data-ttu-id="8baba-145">单服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="8baba-145">Single-Server Topology</span></span>

<span data-ttu-id="8baba-146">持久聊天服务器的最小配置和最简单部署是一个持久聊天服务器前端服务器拓扑。</span><span class="sxs-lookup"><span data-stu-id="8baba-146">The minimum configuration and simplest deployment for Persistent Chat Server is a single Persistent Chat Server Front End Server topology.</span></span> <span data-ttu-id="8baba-147">此部署需要运行持久聊天服务器（如果合规性已启用）的一台服务器、承载 SQL Server 数据库的服务器，以及如果需要合规性，则为 SQL Server 数据库存储合规性数据。</span><span class="sxs-lookup"><span data-stu-id="8baba-147">This deployment requires a single server that runs Persistent Chat Server (which optionally runs the Compliance service, if compliance is enabled), a server that hosts both the SQL Server database, and if compliance is required, the SQL Server database to store the compliance data.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="8baba-148">您不能向作为拓扑生成器中的单个服务器部署启动的持久聊天服务器池添加其他服务器。</span><span class="sxs-lookup"><span data-stu-id="8baba-148">You cannot add additional servers to a Persistent Chat Server pool that is started as a single-server deployment in Topology Builder.</span></span> <span data-ttu-id="8baba-149">即使您使用的是单个服务器，也建议您使用多服务器池拓扑以便稍后添加更多服务器（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="8baba-149">We recommend using the multiple-server pool topology, even if you’re using a single server, so that you can add more servers later, if needed..</span></span>



</div>

<span data-ttu-id="8baba-150">下图显示了符合条件的单个持久聊天服务器前端服务器的拓扑的所有必需组件和可选组件。</span><span class="sxs-lookup"><span data-stu-id="8baba-150">The following figure shows all required and optional components of a topology for a single Persistent Chat Server Front End Server with compliance.</span></span>

<span data-ttu-id="8baba-151">**单个持久聊天服务器**</span><span class="sxs-lookup"><span data-stu-id="8baba-151">**Single Persistent Chat Server**</span></span>

<span data-ttu-id="8baba-152">![单服务器拓扑与合规性服务](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "单服务器拓扑与合规性服务")</span><span class="sxs-lookup"><span data-stu-id="8baba-152">![Single server topology with Compliance service](images/Gg398500.9168fa52-61e0-4d17-a14d-45fd32e81456(OCS.15).jpg "Single server topology with Compliance service")</span></span>

</div>

<div>

## <a name="multiple-server-topology"></a><span data-ttu-id="8baba-153">多服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="8baba-153">Multiple-Server Topology</span></span>

<span data-ttu-id="8baba-154">若要提供更大的容量和可靠性，可以部署多服务器拓扑，如在[Lync server 2013 中规划持久聊天服务器中](lync-server-2013-planning-for-persistent-chat-server.md)所述。</span><span class="sxs-lookup"><span data-stu-id="8baba-154">To provide greater capacity and reliability, you can deploy a multiple-server topology, as described in [Planning for Persistent Chat Server in Lync Server 2013](lync-server-2013-planning-for-persistent-chat-server.md).</span></span> <span data-ttu-id="8baba-155">多服务器拓扑可以包括多达四个运行持久聊天服务器的活动计算机（高可用性和灾难恢复配置允许最多八个，但只有四个活动，并且在待机时剩下四个）。</span><span class="sxs-lookup"><span data-stu-id="8baba-155">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="8baba-156">每个服务器最多可以支持多达20000个并发用户，共80000个并发用户连接到具有4台服务器的持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="8baba-156">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="8baba-157">多服务器拓扑与单服务器拓扑相同，不同之处在于多个服务器承载持久聊天服务器，并且可以扩展到更高级别。</span><span class="sxs-lookup"><span data-stu-id="8baba-157">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="8baba-158">运行持久聊天服务器的多台计算机应驻留在与 Lync Server 和合规性服务相同的 Active Directory 域服务域中。</span><span class="sxs-lookup"><span data-stu-id="8baba-158">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Lync Server and the Compliance service.</span></span>

<span data-ttu-id="8baba-159">下图显示了多个服务器拓扑的所有组件，其中包含多个运行持久聊天服务器、可选合规性服务和独立合规性数据库的计算机。</span><span class="sxs-lookup"><span data-stu-id="8baba-159">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>

<span data-ttu-id="8baba-160">**多个持久聊天服务器**</span><span class="sxs-lookup"><span data-stu-id="8baba-160">**Multiple Persistent Chat Servers**</span></span>

<span data-ttu-id="8baba-161">![多服务器拓扑](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "多服务器拓扑")</span><span class="sxs-lookup"><span data-stu-id="8baba-161">![Multiple server topology](images/Gg398500.19aea898-28df-4d9b-903c-f72ef062d919(OCS.15).jpg "Multiple server topology")</span></span>

<span data-ttu-id="8baba-162">多服务器拓扑提供了服务器池功能。</span><span class="sxs-lookup"><span data-stu-id="8baba-162">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="8baba-163">在服务器池中，持久聊天服务会进行通信并共享数据。</span><span class="sxs-lookup"><span data-stu-id="8baba-163">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="8baba-164">例如，可以从系统中的任何持久聊天服务获取最初发布到一个持久聊天服务的聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="8baba-164">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="8baba-165">通过一个持久聊天服务上载的文件可由任何持久聊天服务访问。</span><span class="sxs-lookup"><span data-stu-id="8baba-165">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="8baba-166">用户可以连接到不同的持久聊天服务器前端服务器，并且可以相互聊天和相互通信。</span><span class="sxs-lookup"><span data-stu-id="8baba-166">Users can be connected to different Persistent Chat Server Front End Servers and can be chatting and communicating with each other.</span></span>

<span data-ttu-id="8baba-167">TCP 8011 的默认端口将服务器连接到服务器池，持久聊天服务使用这些端口相互通信，或用于管理目的。</span><span class="sxs-lookup"><span data-stu-id="8baba-167">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat service to communicate between themselves, or for administrative purposes.</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

