---
title: 规划持久聊天服务器拓扑
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 摘要：阅读本主题，了解 Skype for Business Server 2015 中的持久聊天服务器组件和拓扑。
ms.openlocfilehash: 548fc5ebecb0f123172ee4733346c03cf44aba7f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825502"
---
# <a name="plan-persistent-chat-server-topology"></a><span data-ttu-id="b1e3b-103">规划持久聊天服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="b1e3b-103">Plan Persistent Chat Server topology</span></span>
 
<span data-ttu-id="b1e3b-104">**摘要：** 阅读本主题，了解 Skype for Business Server 2015 中的持久聊天服务器组件和拓扑。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-104">**Summary:** Read this topic to learn about Persistent Chat Server components and topologies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b1e3b-105">持久聊天服务器支持单服务器和多服务器配置。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-105">Persistent Chat Server supports both single-server and multiple-server configurations.</span></span> <span data-ttu-id="b1e3b-106">可以在 Skype for Business Server 2015 Enterprise Edition 或 Standard Edition Server 上安装持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-106">You can install Persistent Chat Server on either a Skype for Business Server 2015 Enterprise Edition or Standard Edition Server.</span></span> 

> [!NOTE] 
> <span data-ttu-id="b1e3b-107">持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="b1e3b-108">Teams 中也提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="b1e3b-109">有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="b1e3b-110">如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="persistent-chat-server-components"></a><span data-ttu-id="b1e3b-111">持久聊天服务器组件</span><span class="sxs-lookup"><span data-stu-id="b1e3b-111">Persistent Chat Server components</span></span>

<span data-ttu-id="b1e3b-112">持久聊天服务器由以下组件组成：</span><span class="sxs-lookup"><span data-stu-id="b1e3b-112">Persistent Chat Server consists of the following components:</span></span>
  
- <span data-ttu-id="b1e3b-113">运行持久聊天服务器并提供以下服务的一台或多台计算机：</span><span class="sxs-lookup"><span data-stu-id="b1e3b-113">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
  - <span data-ttu-id="b1e3b-114">持久聊天服务</span><span class="sxs-lookup"><span data-stu-id="b1e3b-114">Persistent Chat service</span></span>
    
  - <span data-ttu-id="b1e3b-115">合规性服务，在启用合规性时打开</span><span class="sxs-lookup"><span data-stu-id="b1e3b-115">Compliance service, which is turned on if compliance is enabled</span></span>
    
- <span data-ttu-id="b1e3b-116">如果使用镜像 (一台或多台服务器) 则运行 SQL Server 后端数据库以承载存储聊天室内容、聊天室和类别的持久聊天内容数据库。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-116">One or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b1e3b-117">后端数据库存储聊天历史记录数据，包括有关已创建的类别和持久聊天室的信息。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-117">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span> 
  
- <span data-ttu-id="b1e3b-118">如果启用了合规性，则一台或多台服务器 (一台或多台服务器（如果使用镜像) 则运行 SQL Server 后端数据库以承载持久聊天合规性数据库，其中存储了合规性事件和用于合规性的聊天内容。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-118">If compliance is enabled, one or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>
    
<span data-ttu-id="b1e3b-119">有关持久聊天服务器的硬件和软件要求的详细信息，请参阅 [Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) 的服务器要求以及 Skype for Business Server [2015](hardware-and-software-requirements.md)中持久聊天服务器的硬件和软件要求。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-119">For details about hardware and software requirements for Persistent Chat Server, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015](hardware-and-software-requirements.md).</span></span> 
  
## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="b1e3b-120">持久聊天服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="b1e3b-120">Persistent Chat Server topologies</span></span>

<span data-ttu-id="b1e3b-121">可以在单服务器或多服务器池中以及单池或多池拓扑中部署持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-121">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span> <span data-ttu-id="b1e3b-122">持久聊天服务器支持以下拓扑：</span><span class="sxs-lookup"><span data-stu-id="b1e3b-122">Persistent Chat Server supports the following topologies:</span></span>
  
-  <span data-ttu-id="b1e3b-123">Standard Edition Server，其持久聊天服务器并位于前端服务器上</span><span class="sxs-lookup"><span data-stu-id="b1e3b-123">Standard Edition Server with Persistent Chat Server collocated on the Front End Server</span></span>
    
-  <span data-ttu-id="b1e3b-124">在单独的服务器上具有持久聊天服务器的 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="b1e3b-124">Standard Edition Server with Persistent Chat Server on a separate server</span></span>
    
-  <span data-ttu-id="b1e3b-125">在单独的服务器上具有单个持久聊天服务器的 Enterprise Edition Server</span><span class="sxs-lookup"><span data-stu-id="b1e3b-125">Enterprise Edition Server with a single Persistent Chat Server on a separate server</span></span>
    
-  <span data-ttu-id="b1e3b-126">在单独的服务器上具有多个持久聊天服务器的 Enterprise Edition Server</span><span class="sxs-lookup"><span data-stu-id="b1e3b-126">Enterprise Edition Server with more than one Persistent Chat Server on separate servers</span></span>
    
<span data-ttu-id="b1e3b-127">尽管您可以在 Standard Edition Server 上部署持久聊天服务器，但请注意性能和规模将受到影响，并且高可用性不是一个选项。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-127">Although you can deploy Persistent Chat Server on a Standard Edition Server, be aware that performance and scale will be affected, and high availability is not an option.</span></span> <span data-ttu-id="b1e3b-128">因此，建议主要出于概念证明和评估目的在 Standard Edition Server 上部署持久聊天。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-128">Therefore, it is recommended that you deploy Persistent Chat on a Standard Edition Server primarily for proof of concept and evaluation purposes.</span></span> 
  
<span data-ttu-id="b1e3b-129">Skype for Business Server 2015 支持各种并置方案，这样一来，如果您拥有小型组织)  (，您可以在一台服务器上运行多个组件，从而灵活节省硬件成本;如果组织规模较大，且需要可伸缩性和性能)  (则在不同服务器上运行各个组件。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-129">Skype for Business Server 2015 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="b1e3b-130">在决定是否并集组件之前，应考虑可伸缩性因素。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-130">You should consider scalability factors before deciding whether to collocate components.</span></span> <span data-ttu-id="b1e3b-131">Skype for Business Server 2015 Enterprise Edition 和 Standard Edition Server 的并置方案有所不同。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-131">Collocation scenarios differ for Skype for Business Server 2015 Enterprise Edition and Standard Edition servers.</span></span> 
  
<span data-ttu-id="b1e3b-132">以下各节更详细地介绍了拓扑，包括并置方案和后端数据库服务器的选项。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-132">The following sections describe the topologies in more detail, including collocation scenarios and options for the back-end database servers.</span></span> <span data-ttu-id="b1e3b-133">有关所有服务器角色和数据库并置的详细信息，请参阅[Topology Basics for Skype for Business Server 2015。](../../plan-your-deployment/topology-basics/topology-basics.md)</span><span class="sxs-lookup"><span data-stu-id="b1e3b-133">For details about collocation of all server roles and databases, see [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).</span></span>
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a><span data-ttu-id="b1e3b-134">Standard Edition Server，其持久聊天服务器并位于前端服务器上</span><span class="sxs-lookup"><span data-stu-id="b1e3b-134">Standard Edition Server with Persistent Chat Server collocated on the Front End Server</span></span>

<span data-ttu-id="b1e3b-135">使用 Standard Edition，可以在前端服务器上并排持久聊天。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-135">With Standard Edition, you can collocate Persistent Chat on the Front End Server.</span></span> <span data-ttu-id="b1e3b-136">这是最简单和最基本的配置。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-136">This is the simplest and most basic configuration.</span></span> <span data-ttu-id="b1e3b-137">必须确保现有前端服务器在物理资源方面具有足够的容量：CPU、内存、磁盘空间等。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-137">You must make sure that the existing Front End Server has enough capacity in terms of physical resources: CPU, memory, disk space, and so on.</span></span>
  
<span data-ttu-id="b1e3b-138">此外，如果在本地 SQL Server Express 后端服务器上启用了) ，您可以将持久聊天服务器后端服务器和持久聊天合规性数据库并 (。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-138">In addition, you can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server.</span></span> <span data-ttu-id="b1e3b-139">还可以选择将单独的应用程序SQL Server专用实例。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-139">You can also choose to use a separate SQL Server with a dedicated instance.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b1e3b-140">如果第一台持久聊天服务器与 Standard Edition 前端服务器并排，则不能向持久聊天服务器池添加其他服务器。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-140">You cannot add additional servers to a Persistent Chat Server pool if the first Persistent Chat Server is collocated with a Standard Edition Front End Server.</span></span> <span data-ttu-id="b1e3b-141">建议您将第一台服务器安装为独立实例，以便以后可以添加更多服务器（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-141">It is recommended that you install the first server as a standalone instance so that you can add more servers later, if needed.</span></span> 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a><span data-ttu-id="b1e3b-142">在单独的服务器上安装了持久聊天服务器的 Standard Edition Server</span><span class="sxs-lookup"><span data-stu-id="b1e3b-142">Standard Edition Server with Persistent Chat Server installed on a separate server</span></span>

<span data-ttu-id="b1e3b-143">使用 Standard Edition，可以安装持久聊天服务器作为独立实例，并稍后根据需要添加更多服务器。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-143">With Standard Edition, you can install Persistent Chat Server as a standalone instance and add more servers later if needed.</span></span> 
  
<span data-ttu-id="b1e3b-144">如果在本地 (Express 后端服务器上启用了) ，您可以将持久聊天服务器后端服务器和持久SQL Server合规性数据库并SQL Server。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-144">You can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server.</span></span> <span data-ttu-id="b1e3b-145">还可以选择将单独的应用程序SQL Server专用实例。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-145">You can also choose to use a separate SQL Server with a dedicated instance.</span></span> 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a><span data-ttu-id="b1e3b-146">Enterprise Edition Server 与单个持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="b1e3b-146">Enterprise Edition Server with a single Persistent Chat Server</span></span>

<span data-ttu-id="b1e3b-147">使用 Enterprise Edition，必须在单独的计算机上安装持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-147">With Enterprise Edition, you must install the Persistent Chat Server on a separate computer.</span></span> <span data-ttu-id="b1e3b-148">也就是说，您无法在 Enterprise Edition 前端服务器上并排持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-148">That is, you cannot collocate the Persistent Chat Server on the Enterprise Edition Front End Server.</span></span> <span data-ttu-id="b1e3b-149">此部署需要运行持久聊天服务器和合规性服务（如果启用 (）的) 。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-149">This deployment requires a separate server that runs Persistent Chat Server and the Compliance service (if enabled).</span></span>
  
<span data-ttu-id="b1e3b-150">但是，可以将持久SQL Server数据库并放在 Enterprise Edition 前端池的后端数据库上。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-150">You can, however, collocate the SQL Server database for Persistent Chat Server on the back-end database of an Enterprise Edition Front End pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b1e3b-151">如果您计划将 AlwaysOn 可用性SQL用于 HA DR，请注意，持久聊天服务器数据库不支持此组。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-151">If you plan to use SQL AlwaysOn Availability Groups for HA DR, note that it is not supported for Persistent Chat Server databases.</span></span> 
  
<span data-ttu-id="b1e3b-152">如果将持久聊天数据库与后端数据库并并，您可以对任意或所有数据库使用 SQL Server 的单个实例，也可以将单独的 SQL Server 实例用于每个数据库。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-152">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b1e3b-153">承载持久聊天数据库的服务器可以承载其他数据库。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-153">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="b1e3b-154">但是，当您考虑将持久聊天数据库与其他数据库并并时，请注意，如果您存储多个用户的消息，则持久聊天数据库所需的磁盘空间可能会变得很大。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-154">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="b1e3b-155">因此，建议不要将持久聊天数据库与后端数据库并并。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-155">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span> 
  
<span data-ttu-id="b1e3b-156">下图显示了启用了合规性的单个持久聊天服务器拓扑的所有组件 (可选) 。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-156">The following figure shows all components of a topology for a single Persistent Chat Server with compliance enabled (optional).</span></span>
  
<span data-ttu-id="b1e3b-157">**单服务器拓扑**</span><span class="sxs-lookup"><span data-stu-id="b1e3b-157">**Single Server Topology**</span></span>

![持久聊天服务器 - 单服务器拓扑](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a><span data-ttu-id="b1e3b-159">具有多台持久聊天服务器的 Enterprise Edition Server</span><span class="sxs-lookup"><span data-stu-id="b1e3b-159">Enterprise Edition Server with multiple Persistent Chat Servers</span></span>

<span data-ttu-id="b1e3b-160">使用 Enterprise Edition，可以部署多服务器拓扑，以提升容量和可靠性。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-160">With Enterprise Edition, you can deploy a multiple-server topology for greater capacity and reliability.</span></span> <span data-ttu-id="b1e3b-161">多服务器拓扑与单服务器拓扑相同，但多个服务器承载持久聊天服务器，并且可以扩展得更高。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-161">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="b1e3b-162">多服务器拓扑可以包含多达四台运行持久聊天服务器的活动计算机 (高可用性和灾难恢复配置最多允许使用八台，但只有四台处于活动状态，其余四台处于备用状态) 。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-162">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="b1e3b-163">每台服务器可支持 20，000 个并发用户，总共支持 80，000 个并发用户连接到具有 4 台服务器的持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-163">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="b1e3b-164">运行持久聊天服务器的多台计算机应驻留在与 Skype for Business Server 和合规性服务相同的 Active Directory 域服务域中。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-164">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Skype for Business Server and the Compliance service.</span></span>
  
<span data-ttu-id="b1e3b-165">下图显示了多服务器拓扑的所有组件，该拓扑具有多台运行持久聊天服务器的计算机、可选的合规性服务和单独的合规性数据库。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-165">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>
  
<span data-ttu-id="b1e3b-166">**多服务器拓扑**</span><span class="sxs-lookup"><span data-stu-id="b1e3b-166">**Multiple Server Topology**</span></span>

![持久聊天服务器 - 多服务器拓扑](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
<span data-ttu-id="b1e3b-168">多服务器拓扑提供了服务器池功能。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-168">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="b1e3b-169">在服务器池中，持久聊天服务通信和共享数据。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-169">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="b1e3b-170">例如，最初张贴到一个持久聊天服务的聊天历史记录可从系统的任何持久聊天服务获得。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-170">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="b1e3b-171">任何持久聊天服务都可以访问通过一个持久聊天服务上载的文件。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-171">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="b1e3b-172">用户可以连接到不同的持久聊天服务器前端服务器，并可以相互通信。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-172">Users can be connected to different Persistent Chat Server Front End Servers and can be communicating with each other.</span></span> <span data-ttu-id="b1e3b-173">TCP 8011 的默认端口将服务器连接到服务器池，持久聊天服务将其用于相互通信或用于管理目的。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-173">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat services to communicate between themselves, or for administrative purposes.</span></span>
  
<span data-ttu-id="b1e3b-174">例如，在一个四台服务器的持久聊天服务器部署中（其中 80，000 个用户可以同时登录持久聊天）中，负载平均分布为每台服务器 20，000 个用户。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-174">For example, in a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="b1e3b-175">如果一台服务器不可用，连接到该服务器的用户将失去对持久聊天服务器的访问权限。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-175">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="b1e3b-176">断开连接的用户将自动转接到其余的服务器，直到该不可用的服务器恢复使用。</span><span class="sxs-lookup"><span data-stu-id="b1e3b-176">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> 
  

