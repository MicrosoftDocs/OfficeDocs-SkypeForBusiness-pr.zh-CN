---
title: 规划持久聊天服务器拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/17/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 摘要： 阅读此主题以了解有关持久聊天服务器组件和拓扑中 Skype 的业务服务器 2015年。
ms.openlocfilehash: d004557da9a47a8d5de544af18e74eb7eecc01b0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926063"
---
# <a name="plan-persistent-chat-server-topology"></a><span data-ttu-id="f763e-103">规划持久聊天服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="f763e-103">Plan Persistent Chat Server topology</span></span>
 
<span data-ttu-id="f763e-104">**摘要：** 阅读此主题以了解有关持久聊天服务器组件和拓扑中 Skype 的业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="f763e-104">**Summary:** Read this topic to learn about Persistent Chat Server components and topologies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="f763e-105">Persistent Chat Server 支持单服务器和多服务器的配置。</span><span class="sxs-lookup"><span data-stu-id="f763e-105">Persistent Chat Server supports both single-server and multiple-server configurations.</span></span> <span data-ttu-id="f763e-106">业务 Server 2015 Enterprise Edition 或 Standard Edition Server，可以在任一 Skype 上安装持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="f763e-106">You can install Persistent Chat Server on either a Skype for Business Server 2015 Enterprise Edition or Standard Edition Server.</span></span> 

> [!NOTE] 
> <span data-ttu-id="f763e-107">持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="f763e-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="f763e-108">中团队提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="f763e-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="f763e-109">有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。</span><span class="sxs-lookup"><span data-stu-id="f763e-109">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="f763e-110">如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="f763e-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="persistent-chat-server-components"></a><span data-ttu-id="f763e-111">持久聊天服务器组件</span><span class="sxs-lookup"><span data-stu-id="f763e-111">Persistent Chat Server components</span></span>

<span data-ttu-id="f763e-112">持久聊天服务器由以下组件组成：</span><span class="sxs-lookup"><span data-stu-id="f763e-112">Persistent Chat Server consists of the following components:</span></span>
  
- <span data-ttu-id="f763e-113">一个或多个计算机运行持久聊天服务器并提供以下服务：</span><span class="sxs-lookup"><span data-stu-id="f763e-113">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
  - <span data-ttu-id="f763e-114">持久聊天服务</span><span class="sxs-lookup"><span data-stu-id="f763e-114">Persistent Chat service</span></span>
    
  - <span data-ttu-id="f763e-115">合规性服务，在启用合规性时打开</span><span class="sxs-lookup"><span data-stu-id="f763e-115">Compliance service, which is turned on if compliance is enabled</span></span>
    
- <span data-ttu-id="f763e-116">一个或多个服务器 （多个如果使用镜像类型） 运行承载持久聊天的内容数据库的 SQL Server 后端数据库存储聊天室内容、 聊天室和类别。</span><span class="sxs-lookup"><span data-stu-id="f763e-116">One or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="f763e-117">后端数据库用于存储聊天历史记录数据，包括有关类别和创建的持久聊天聊天室的信息。</span><span class="sxs-lookup"><span data-stu-id="f763e-117">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span> 
  
- <span data-ttu-id="f763e-118">如果启用合规性，则 （多个如果使用镜像类型） 的一个或多个服务器运行 SQL Server 后端数据库用于承载持久聊天合规性数据库中，出于合规性目的的合规性事件和聊天其中内容存储。</span><span class="sxs-lookup"><span data-stu-id="f763e-118">If compliance is enabled, one or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>
    
<span data-ttu-id="f763e-119">有关持久聊天服务器的硬件和软件要求的详细信息，请参阅[for Persistent Chat Server 中的业务服务器 2015 Skype 的硬件和软件要求](hardware-and-software-requirements.md)和[业务服务器 2015年的 Skype 服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f763e-119">For details about hardware and software requirements for Persistent Chat Server, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015](hardware-and-software-requirements.md).</span></span> 
  
## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="f763e-120">持久聊天服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="f763e-120">Persistent Chat Server topologies</span></span>

<span data-ttu-id="f763e-121">您可以部署持久聊天服务器在单服务器还是多服务器池，并使用单池或多池拓扑。</span><span class="sxs-lookup"><span data-stu-id="f763e-121">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span> <span data-ttu-id="f763e-122">持久聊天服务器支持以下拓扑：</span><span class="sxs-lookup"><span data-stu-id="f763e-122">Persistent Chat Server supports the following topologies:</span></span>
  
-  <span data-ttu-id="f763e-123">Standard Edition Server 与持久聊天服务器并置在前端服务器上</span><span class="sxs-lookup"><span data-stu-id="f763e-123">Standard Edition Server with Persistent Chat Server collocated on the Front End Server</span></span>
    
-  <span data-ttu-id="f763e-124">Standard Edition Server 与一台服务器上的持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="f763e-124">Standard Edition Server with Persistent Chat Server on a separate server</span></span>
    
-  <span data-ttu-id="f763e-125">与一个持久聊天服务器一台服务器上的 Enterprise Edition Server</span><span class="sxs-lookup"><span data-stu-id="f763e-125">Enterprise Edition Server with a single Persistent Chat Server on a separate server</span></span>
    
-  <span data-ttu-id="f763e-126">使用多个持久聊天服务器不同的服务器上的 Enterprise Edition Server</span><span class="sxs-lookup"><span data-stu-id="f763e-126">Enterprise Edition Server with more than one Persistent Chat Server on separate servers</span></span>
    
<span data-ttu-id="f763e-127">尽管可以部署 Standard Edition Server 上的持久聊天服务器，请注意会影响性能和范围，并不高可用性，一个选项。</span><span class="sxs-lookup"><span data-stu-id="f763e-127">Although you can deploy Persistent Chat Server on a Standard Edition Server, be aware that performance and scale will be affected, and high availability is not an option.</span></span> <span data-ttu-id="f763e-128">因此，建议您部署持久聊天主要用于证明概念和评估目的 Standard Edition Server 上。</span><span class="sxs-lookup"><span data-stu-id="f763e-128">Therefore, it is recommended that you deploy Persistent Chat on a Standard Edition Server primarily for proof of concept and evaluation purposes.</span></span> 
  
<span data-ttu-id="f763e-129">Skype 的业务服务器 2015年支持各种并置方案，从而灵活地通过在一台服务器 （如果您有一个小型组织） 上运行多个组件节省硬件成本，或在不同的服务器 （运行各个组件如果您有较大组织的需要可伸缩性和性能）。</span><span class="sxs-lookup"><span data-stu-id="f763e-129">Skype for Business Server 2015 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="f763e-130">决定是否将并置组件之前，应考虑可伸缩性因素。</span><span class="sxs-lookup"><span data-stu-id="f763e-130">You should consider scalability factors before deciding whether to collocate components.</span></span> <span data-ttu-id="f763e-131">并置方案不同的 Skype 业务 Server 2015 Enterprise Edition 和 Standard Edition 服务器。</span><span class="sxs-lookup"><span data-stu-id="f763e-131">Collocation scenarios differ for Skype for Business Server 2015 Enterprise Edition and Standard Edition servers.</span></span> 
  
<span data-ttu-id="f763e-132">以下几节更为具体地介绍了拓扑，包括并置方案和后端数据库服务器选项。</span><span class="sxs-lookup"><span data-stu-id="f763e-132">The following sections describe the topologies in more detail, including collocation scenarios and options for the back-end database servers.</span></span> <span data-ttu-id="f763e-133">有关所有服务器角色和数据库并置的详细信息，请参阅[拓扑的业务服务器 2015年的 Skype 的基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="f763e-133">For details about collocation of all server roles and databases, see [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).</span></span>
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a><span data-ttu-id="f763e-134">Standard Edition Server 与持久聊天服务器并置在前端服务器上</span><span class="sxs-lookup"><span data-stu-id="f763e-134">Standard Edition Server with Persistent Chat Server collocated on the Front End Server</span></span>

<span data-ttu-id="f763e-135">使用 Standard Edition，可以将持久聊天并置在前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="f763e-135">With Standard Edition, you can collocate Persistent Chat on the Front End Server.</span></span> <span data-ttu-id="f763e-136">这是最简单也最基本的配置。</span><span class="sxs-lookup"><span data-stu-id="f763e-136">This is the simplest and most basic configuration.</span></span> <span data-ttu-id="f763e-137">您必须确保现有前端服务器具有足够的容量会严重影响物理资源： CPU、 内存、 磁盘空间，等等。</span><span class="sxs-lookup"><span data-stu-id="f763e-137">You must make sure that the existing Front End Server has enough capacity in terms of physical resources: CPU, memory, disk space, and so on.</span></span>
  
<span data-ttu-id="f763e-138">此外，您可以并置的持久聊天服务器后端服务器和持久聊天合规性数据库 （如果已启用） 的本地 SQL Server Express 后端服务器上。</span><span class="sxs-lookup"><span data-stu-id="f763e-138">In addition, you can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server.</span></span> <span data-ttu-id="f763e-139">还可以选择使用独立的 SQL Server 及专用实例。</span><span class="sxs-lookup"><span data-stu-id="f763e-139">You can also choose to use a separate SQL Server with a dedicated instance.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="f763e-140">如果第一台持久聊天服务器与 Standard Edition 前端服务器并置，则不能向持久聊天服务器池添加其他服务器。</span><span class="sxs-lookup"><span data-stu-id="f763e-140">You cannot add additional servers to a Persistent Chat Server pool if the first Persistent Chat Server is collocated with a Standard Edition Front End Server.</span></span> <span data-ttu-id="f763e-141">建议您安装第一台服务器作为独立实例，以便您可以添加更多服务器更高版本，如果需要。</span><span class="sxs-lookup"><span data-stu-id="f763e-141">It is recommended that you install the first server as a standalone instance so that you can add more servers later, if needed.</span></span> 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a><span data-ttu-id="f763e-142">Standard Edition Server 与持久聊天服务器安装在不同的服务器上</span><span class="sxs-lookup"><span data-stu-id="f763e-142">Standard Edition Server with Persistent Chat Server installed on a separate server</span></span>

<span data-ttu-id="f763e-143">使用 Standard Edition，您可以将持久聊天服务器作为独立实例安装，随后按需添加更多服务器。  </span><span class="sxs-lookup"><span data-stu-id="f763e-143">With Standard Edition, you can install Persistent Chat Server as a standalone instance and add more servers later if needed.</span></span> 
  
<span data-ttu-id="f763e-144">您可以并置的持久聊天服务器后端服务器和持久聊天合规性数据库 （如果已启用） 的本地 SQL Server Express 后端服务器上。</span><span class="sxs-lookup"><span data-stu-id="f763e-144">You can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server.</span></span> <span data-ttu-id="f763e-145">还可以选择使用独立的 SQL Server 及专用实例。</span><span class="sxs-lookup"><span data-stu-id="f763e-145">You can also choose to use a separate SQL Server with a dedicated instance.</span></span> 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a><span data-ttu-id="f763e-146">Enterprise Edition Server 与一个持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="f763e-146">Enterprise Edition Server with a single Persistent Chat Server</span></span>

<span data-ttu-id="f763e-147">使用 Enterprise Edition 时，必须将持久聊天服务器安装在不同的计算机上。</span><span class="sxs-lookup"><span data-stu-id="f763e-147">With Enterprise Edition, you must install the Persistent Chat Server on a separate computer.</span></span> <span data-ttu-id="f763e-148">也就是说，不能将持久聊天服务器并置在 Enterprise Edition 前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="f763e-148">That is, you cannot collocate the Persistent Chat Server on the Enterprise Edition Front End Server.</span></span> <span data-ttu-id="f763e-149">这种部署需要单独的服务器在运行 Persistent Chat Server 和合规性服务 （如果已启用）。</span><span class="sxs-lookup"><span data-stu-id="f763e-149">This deployment requires a separate server that runs Persistent Chat Server and the Compliance service (if enabled).</span></span>
  
<span data-ttu-id="f763e-150">您可以但是，将并置的 SQL Server 数据库对于 Persistent Chat Server 上的 Enterprise Edition 前端池的后端数据库。</span><span class="sxs-lookup"><span data-stu-id="f763e-150">You can, however, collocate the SQL Server database for Persistent Chat Server on the back-end database of an Enterprise Edition Front End pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="f763e-151">如果计划为 HA DR 使用 SQL AlwaysOn 可用性组，请注意它不受持久聊天服务器数据库支持。</span><span class="sxs-lookup"><span data-stu-id="f763e-151">If you plan to use SQL AlwaysOn Availability Groups for HA DR, note that it is not supported for Persistent Chat Server databases.</span></span> 
  
<span data-ttu-id="f763e-152">如果您将并置的持久聊天数据库后端数据库，您可以使用 SQL Server 的单个实例的任意或全部数据库，或您可以为每个数据库使用单独的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="f763e-152">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f763e-153">承载持久聊天数据库的服务器可以承载其他数据库。</span><span class="sxs-lookup"><span data-stu-id="f763e-153">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="f763e-154">但是，当您考虑持久聊天数据库与其他数据库并置时，注意，如果存储较多的用户的消息的磁盘空间需要由持久聊天数据库可以变得非常大。</span><span class="sxs-lookup"><span data-stu-id="f763e-154">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="f763e-155">因此，我们不建议的持久聊天数据库后端数据库并置。</span><span class="sxs-lookup"><span data-stu-id="f763e-155">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span> 
  
<span data-ttu-id="f763e-156">下图显示拓扑的所有组件的单个持久聊天服务器与启用合规性 （可选）。</span><span class="sxs-lookup"><span data-stu-id="f763e-156">The following figure shows all components of a topology for a single Persistent Chat Server with compliance enabled (optional).</span></span>
  
<span data-ttu-id="f763e-157">**单服务器拓扑**</span><span class="sxs-lookup"><span data-stu-id="f763e-157">**Single Server Topology**</span></span>

![持久聊天服务器 - 单服务器拓扑](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a><span data-ttu-id="f763e-159">Enterprise Edition Server 与多个持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="f763e-159">Enterprise Edition Server with multiple Persistent Chat Servers</span></span>

<span data-ttu-id="f763e-160">与 Enterprise Edition，您可以部署更大容量和可靠性的多服务器拓扑。</span><span class="sxs-lookup"><span data-stu-id="f763e-160">With Enterprise Edition, you can deploy a multiple-server topology for greater capacity and reliability.</span></span> <span data-ttu-id="f763e-161">多服务器拓扑是单服务器拓扑相同只不过多台服务器承载持久聊天服务器，并可以扩展更高版本。</span><span class="sxs-lookup"><span data-stu-id="f763e-161">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="f763e-162">多服务器拓扑可以包括多达四台运行持久聊天服务器的活动计算机 （高可用性和灾难恢复配置将允许最多八个，但仅四可以是活动和四处于备用状态的剩余）。</span><span class="sxs-lookup"><span data-stu-id="f763e-162">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="f763e-163">每台服务器可以支持多达 20,000 个并发用户，用于连接到 4 台服务器的持久聊天服务器池的 80,000 并发用户总数。</span><span class="sxs-lookup"><span data-stu-id="f763e-163">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="f763e-164">运行持久聊天服务器的多台计算机应位于同一 Active Directory 域服务域 Skype 业务服务器和合规性服务。</span><span class="sxs-lookup"><span data-stu-id="f763e-164">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Skype for Business Server and the Compliance service.</span></span>
  
<span data-ttu-id="f763e-165">下图显示了所有组件的多服务器拓扑与运行持久聊天服务器、 可选的合规性服务和单独合规性数据库的多台计算机。</span><span class="sxs-lookup"><span data-stu-id="f763e-165">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>
  
<span data-ttu-id="f763e-166">**多服务器拓扑**</span><span class="sxs-lookup"><span data-stu-id="f763e-166">**Multiple Server Topology**</span></span>

![持久聊天服务器 - 多服务器拓扑](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
<span data-ttu-id="f763e-168">多服务器拓扑提供了服务器池功能。</span><span class="sxs-lookup"><span data-stu-id="f763e-168">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="f763e-169">在服务器池中，持久聊天服务进行通信和共享数据。</span><span class="sxs-lookup"><span data-stu-id="f763e-169">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="f763e-170">例如，最初发布到一个持久聊天服务的聊天历史记录系统中是可从任何持久聊天服务。</span><span class="sxs-lookup"><span data-stu-id="f763e-170">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="f763e-171">通过一个持久聊天服务上载的文件可以访问由任何持久聊天服务。</span><span class="sxs-lookup"><span data-stu-id="f763e-171">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="f763e-172">用户可以连接到不同持久聊天服务器的前端服务器，并且可以相互通信。</span><span class="sxs-lookup"><span data-stu-id="f763e-172">Users can be connected to different Persistent Chat Server Front End Servers and can be communicating with each other.</span></span> <span data-ttu-id="f763e-173">端口的 TCP 8011 的默认将服务器连接至服务器池，并由持久聊天服务进行通信，或用于管理用途。</span><span class="sxs-lookup"><span data-stu-id="f763e-173">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat services to communicate between themselves, or for administrative purposes.</span></span>
  
<span data-ttu-id="f763e-174">例如，在四台服务器持久聊天服务器部署中，其中 80,000 用户可以同时登录到持久聊天，负载均匀分布在每台服务器的 20,000 名用户。</span><span class="sxs-lookup"><span data-stu-id="f763e-174">For example, in a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="f763e-175">如果一台服务器变得不可用，连接到该服务器的用户将失去对持久聊天服务器的访问。</span><span class="sxs-lookup"><span data-stu-id="f763e-175">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="f763e-176">断开连接的用户将自动转移到其他服务器，直至不可用服务器恢复为止。</span><span class="sxs-lookup"><span data-stu-id="f763e-176">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> 
  

