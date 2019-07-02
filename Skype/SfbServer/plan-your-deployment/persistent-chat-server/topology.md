---
title: 规划持久聊天服务器拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 5/17/2016
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: '摘要: 阅读本主题, 了解 Skype for Business Server 2015 中的持久聊天服务器组件和拓扑。'
ms.openlocfilehash: c31cb8b0ada280b52d902e975f1bacf947fd19e7
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "35418271"
---
# <a name="plan-persistent-chat-server-topology"></a><span data-ttu-id="ca838-103">规划持久聊天服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="ca838-103">Plan Persistent Chat Server topology</span></span>
 
<span data-ttu-id="ca838-104">**摘要:** 阅读本主题, 了解 Skype for Business Server 2015 中的持久聊天服务器组件和拓扑。</span><span class="sxs-lookup"><span data-stu-id="ca838-104">**Summary:** Read this topic to learn about Persistent Chat Server components and topologies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ca838-105">持久聊天服务器支持单服务器和多服务器配置。</span><span class="sxs-lookup"><span data-stu-id="ca838-105">Persistent Chat Server supports both single-server and multiple-server configurations.</span></span> <span data-ttu-id="ca838-106">你可以在 Skype for Business Server 2015 Enterprise Edition 或 Standard Edition 服务器上安装持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="ca838-106">You can install Persistent Chat Server on either a Skype for Business Server 2015 Enterprise Edition or Standard Edition Server.</span></span> 

> [!NOTE] 
> <span data-ttu-id="ca838-107">Skype for business Server 2015 中提供了持久聊天, 但 Skype for business Server 2019 不再支持此功能。</span><span class="sxs-lookup"><span data-stu-id="ca838-107">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ca838-108">团队中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="ca838-108">The same functionality is available in Teams.</span></span> <span data-ttu-id="ca838-109">有关详细信息, 请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。</span><span class="sxs-lookup"><span data-stu-id="ca838-109">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="ca838-110">如果需要使用持久聊天, 您可以选择将需要此功能的用户迁移到团队, 或继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="ca838-110">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="persistent-chat-server-components"></a><span data-ttu-id="ca838-111">持久聊天服务器组件</span><span class="sxs-lookup"><span data-stu-id="ca838-111">Persistent Chat Server components</span></span>

<span data-ttu-id="ca838-112">持久聊天服务器由以下组件组成：</span><span class="sxs-lookup"><span data-stu-id="ca838-112">Persistent Chat Server consists of the following components:</span></span>
  
- <span data-ttu-id="ca838-113">运行持久聊天服务器并提供以下服务的一个或多个计算机:</span><span class="sxs-lookup"><span data-stu-id="ca838-113">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
  - <span data-ttu-id="ca838-114">持久聊天服务</span><span class="sxs-lookup"><span data-stu-id="ca838-114">Persistent Chat service</span></span>
    
  - <span data-ttu-id="ca838-115">合规性服务，在启用合规性时打开</span><span class="sxs-lookup"><span data-stu-id="ca838-115">Compliance service, which is turned on if compliance is enabled</span></span>
    
- <span data-ttu-id="ca838-116">一个或多个服务器 (如果使用镜像, 则使用多个) 运行 SQL Server 后端数据库以托管持久聊天内容数据库, 其中存储了聊天室内容、会议室和类别。</span><span class="sxs-lookup"><span data-stu-id="ca838-116">One or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ca838-117">后端数据库存储聊天历史记录数据, 包括有关已创建的类别和持续聊天室的信息。</span><span class="sxs-lookup"><span data-stu-id="ca838-117">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span> 
  
- <span data-ttu-id="ca838-118">如果启用合规性, 则一个或多个服务器 (如果使用了镜像) 运行 SQL Server 后端数据库, 以托管持久的聊天合规性数据库, 其中存储了合规性事件和用于实现合规性的聊天内容。</span><span class="sxs-lookup"><span data-stu-id="ca838-118">If compliance is enabled, one or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>
    
<span data-ttu-id="ca838-119">有关持久聊天服务器的硬件和软件要求的详细信息, 请参阅 skype for business server [2015 的服务器要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)和[Skype for business Server 2015 中持久聊天服务器的硬件和软件要求](hardware-and-software-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="ca838-119">For details about hardware and software requirements for Persistent Chat Server, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015](hardware-and-software-requirements.md).</span></span> 
  
## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="ca838-120">持久聊天服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="ca838-120">Persistent Chat Server topologies</span></span>

<span data-ttu-id="ca838-121">你可以在单服务器或多服务器池中部署持久聊天服务器, 并通过单个池或多池拓扑进行部署。</span><span class="sxs-lookup"><span data-stu-id="ca838-121">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span> <span data-ttu-id="ca838-122">持久聊天服务器支持下列拓扑:</span><span class="sxs-lookup"><span data-stu-id="ca838-122">Persistent Chat Server supports the following topologies:</span></span>
  
-  <span data-ttu-id="ca838-123">Standard Edition Server 与持久聊天服务器并置在前端服务器上</span><span class="sxs-lookup"><span data-stu-id="ca838-123">Standard Edition Server with Persistent Chat Server collocated on the Front End Server</span></span>
    
-  <span data-ttu-id="ca838-124">单独服务器上具有持久聊天服务器的标准版服务器</span><span class="sxs-lookup"><span data-stu-id="ca838-124">Standard Edition Server with Persistent Chat Server on a separate server</span></span>
    
-  <span data-ttu-id="ca838-125">企业版服务器, 在单独的服务器上使用单个持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="ca838-125">Enterprise Edition Server with a single Persistent Chat Server on a separate server</span></span>
    
-  <span data-ttu-id="ca838-126">不同服务器上有多个持久聊天服务器的企业版服务器</span><span class="sxs-lookup"><span data-stu-id="ca838-126">Enterprise Edition Server with more than one Persistent Chat Server on separate servers</span></span>
    
<span data-ttu-id="ca838-127">虽然你可以在标准版服务器上部署持久聊天服务器, 但请注意性能和规模将受到影响, 并且不能选择高可用性。</span><span class="sxs-lookup"><span data-stu-id="ca838-127">Although you can deploy Persistent Chat Server on a Standard Edition Server, be aware that performance and scale will be affected, and high availability is not an option.</span></span> <span data-ttu-id="ca838-128">因此, 建议在标准版服务器上部署持久聊天, 主要用于概念和评估目的。</span><span class="sxs-lookup"><span data-stu-id="ca838-128">Therefore, it is recommended that you deploy Persistent Chat on a Standard Edition Server primarily for proof of concept and evaluation purposes.</span></span> 
  
<span data-ttu-id="ca838-129">Skype for Business Server 2015 支持各种 collocation 方案, 让你可以通过在一台服务器 (如果有一个小型组织) 上运行多个组件来灵活地保存硬件成本, 或在不同服务器上运行单个组件 (如果您有一个需要可伸缩性和性能的大型组织。</span><span class="sxs-lookup"><span data-stu-id="ca838-129">Skype for Business Server 2015 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="ca838-130">在决定是否 collocate 组件之前, 应考虑可伸缩性因素。</span><span class="sxs-lookup"><span data-stu-id="ca838-130">You should consider scalability factors before deciding whether to collocate components.</span></span> <span data-ttu-id="ca838-131">Collocation 方案不同于 Skype for business Server 2015 Enterprise Edition 和 Standard Edition 服务器。</span><span class="sxs-lookup"><span data-stu-id="ca838-131">Collocation scenarios differ for Skype for Business Server 2015 Enterprise Edition and Standard Edition servers.</span></span> 
  
<span data-ttu-id="ca838-132">以下几节更为具体地介绍了拓扑，包括并置方案和后端数据库服务器选项。</span><span class="sxs-lookup"><span data-stu-id="ca838-132">The following sections describe the topologies in more detail, including collocation scenarios and options for the back-end database servers.</span></span> <span data-ttu-id="ca838-133">有关所有服务器角色和数据库的 collocation 的详细信息, 请参阅[Skype for Business server 2015 的拓扑基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="ca838-133">For details about collocation of all server roles and databases, see [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).</span></span>
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a><span data-ttu-id="ca838-134">Standard Edition Server 与持久聊天服务器并置在前端服务器上</span><span class="sxs-lookup"><span data-stu-id="ca838-134">Standard Edition Server with Persistent Chat Server collocated on the Front End Server</span></span>

<span data-ttu-id="ca838-135">使用 Standard Edition，可以将持久聊天并置在前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="ca838-135">With Standard Edition, you can collocate Persistent Chat on the Front End Server.</span></span> <span data-ttu-id="ca838-136">这是最简单也最基本的配置。</span><span class="sxs-lookup"><span data-stu-id="ca838-136">This is the simplest and most basic configuration.</span></span> <span data-ttu-id="ca838-137">您必须确保现有前端服务器在物理资源方面具有足够的容量: CPU、内存、磁盘空间等。</span><span class="sxs-lookup"><span data-stu-id="ca838-137">You must make sure that the existing Front End Server has enough capacity in terms of physical resources: CPU, memory, disk space, and so on.</span></span>
  
<span data-ttu-id="ca838-138">此外, 你可以在本地 SQL Server Express 后端服务器上 collocate 持久聊天服务器后端服务器和持久聊天合规性数据库 (如果已启用)。</span><span class="sxs-lookup"><span data-stu-id="ca838-138">In addition, you can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server.</span></span> <span data-ttu-id="ca838-139">还可以选择使用独立的 SQL Server 及专用实例。</span><span class="sxs-lookup"><span data-stu-id="ca838-139">You can also choose to use a separate SQL Server with a dedicated instance.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="ca838-140">如果第一个持久聊天服务器与标准版前端服务器 collocated, 则不能将其他服务器添加到持久聊天服务器池中。</span><span class="sxs-lookup"><span data-stu-id="ca838-140">You cannot add additional servers to a Persistent Chat Server pool if the first Persistent Chat Server is collocated with a Standard Edition Front End Server.</span></span> <span data-ttu-id="ca838-141">建议你将第一台服务器安装为独立实例, 以便你可以在以后添加更多服务器 (如果需要)。</span><span class="sxs-lookup"><span data-stu-id="ca838-141">It is recommended that you install the first server as a standalone instance so that you can add more servers later, if needed.</span></span> 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a><span data-ttu-id="ca838-142">Standard Edition Server 与持久聊天服务器安装在不同的服务器上</span><span class="sxs-lookup"><span data-stu-id="ca838-142">Standard Edition Server with Persistent Chat Server installed on a separate server</span></span>

<span data-ttu-id="ca838-143">使用 Standard Edition，您可以将持久聊天服务器作为独立实例安装，随后按需添加更多服务器。  </span><span class="sxs-lookup"><span data-stu-id="ca838-143">With Standard Edition, you can install Persistent Chat Server as a standalone instance and add more servers later if needed.</span></span> 
  
<span data-ttu-id="ca838-144">你可以在本地 SQL Server Express 后端服务器上 collocate 持久聊天服务器后端服务器和持久聊天合规性数据库 (如果已启用)。</span><span class="sxs-lookup"><span data-stu-id="ca838-144">You can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server.</span></span> <span data-ttu-id="ca838-145">还可以选择使用独立的 SQL Server 及专用实例。</span><span class="sxs-lookup"><span data-stu-id="ca838-145">You can also choose to use a separate SQL Server with a dedicated instance.</span></span> 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a><span data-ttu-id="ca838-146">Enterprise Edition Server 与一个持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="ca838-146">Enterprise Edition Server with a single Persistent Chat Server</span></span>

<span data-ttu-id="ca838-147">使用 Enterprise Edition 时，必须将持久聊天服务器安装在不同的计算机上。</span><span class="sxs-lookup"><span data-stu-id="ca838-147">With Enterprise Edition, you must install the Persistent Chat Server on a separate computer.</span></span> <span data-ttu-id="ca838-148">也就是说，不能将持久聊天服务器并置在 Enterprise Edition 前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="ca838-148">That is, you cannot collocate the Persistent Chat Server on the Enterprise Edition Front End Server.</span></span> <span data-ttu-id="ca838-149">此部署需要运行持久聊天服务器和合规性服务 (如果已启用) 的单独服务器。</span><span class="sxs-lookup"><span data-stu-id="ca838-149">This deployment requires a separate server that runs Persistent Chat Server and the Compliance service (if enabled).</span></span>
  
<span data-ttu-id="ca838-150">但是, 你可以为企业版前端池的后端数据库上的持久聊天服务器 collocate SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="ca838-150">You can, however, collocate the SQL Server database for Persistent Chat Server on the back-end database of an Enterprise Edition Front End pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ca838-151">如果计划为 HA DR 使用 SQL AlwaysOn 可用性组，请注意它不受持久聊天服务器数据库支持。</span><span class="sxs-lookup"><span data-stu-id="ca838-151">If you plan to use SQL AlwaysOn Availability Groups for HA DR, note that it is not supported for Persistent Chat Server databases.</span></span> 
  
<span data-ttu-id="ca838-152">如果你将持久聊天数据库与后端数据库 collocate, 则可以对任何或所有数据库使用一个 SQL Server 实例, 也可以为每个数据库使用单独的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="ca838-152">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ca838-153">托管持久聊天数据库的服务器可以托管其他数据库。</span><span class="sxs-lookup"><span data-stu-id="ca838-153">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="ca838-154">但是, 当你考虑将持久聊天数据库与其他数据库一起使用时, 请注意, 如果你存储的消息超过了几个用户, 则持久聊天数据库所需的磁盘空间会变得非常大。</span><span class="sxs-lookup"><span data-stu-id="ca838-154">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="ca838-155">因此, 我们不建议将持久聊天数据库与后端数据库 collocating。</span><span class="sxs-lookup"><span data-stu-id="ca838-155">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span> 
  
<span data-ttu-id="ca838-156">下图显示了一个已启用合规性的单个持久聊天服务器的拓扑的所有组件 (可选)。</span><span class="sxs-lookup"><span data-stu-id="ca838-156">The following figure shows all components of a topology for a single Persistent Chat Server with compliance enabled (optional).</span></span>
  
<span data-ttu-id="ca838-157">**单服务器拓扑**</span><span class="sxs-lookup"><span data-stu-id="ca838-157">**Single Server Topology**</span></span>

![持久聊天服务器 - 单服务器拓扑](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a><span data-ttu-id="ca838-159">Enterprise Edition Server 与多个持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="ca838-159">Enterprise Edition Server with multiple Persistent Chat Servers</span></span>

<span data-ttu-id="ca838-160">使用企业版, 你可以部署多服务器拓扑, 以获得更大的容量和可靠性。</span><span class="sxs-lookup"><span data-stu-id="ca838-160">With Enterprise Edition, you can deploy a multiple-server topology for greater capacity and reliability.</span></span> <span data-ttu-id="ca838-161">多服务器拓扑与单服务器拓扑相同, 不同之处在于多台服务器托管持久聊天服务器, 并且可以更高的比例。</span><span class="sxs-lookup"><span data-stu-id="ca838-161">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="ca838-162">多服务器拓扑可以包括多达四个运行持久聊天服务器的活动计算机 (高可用性和灾难恢复配置最多允许八个, 但只有四个可以激活, 并且其余四个处于待机状态)。</span><span class="sxs-lookup"><span data-stu-id="ca838-162">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="ca838-163">每台服务器可支持多达20000并行用户, 总共可支持连接到具有4台服务器的持久聊天服务器池的80000个并发用户。</span><span class="sxs-lookup"><span data-stu-id="ca838-163">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="ca838-164">运行持久聊天服务器的多台计算机应位于与 Skype for Business 服务器和合规性服务相同的 Active Directory 域服务域中。</span><span class="sxs-lookup"><span data-stu-id="ca838-164">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Skype for Business Server and the Compliance service.</span></span>
  
<span data-ttu-id="ca838-165">下图显示多服务器拓扑的所有组件, 其中包含运行持久聊天服务器的多台计算机、可选合规性服务和单独的合规性数据库。</span><span class="sxs-lookup"><span data-stu-id="ca838-165">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>
  
<span data-ttu-id="ca838-166">**多服务器拓扑**</span><span class="sxs-lookup"><span data-stu-id="ca838-166">**Multiple Server Topology**</span></span>

![持久聊天服务器 - 多服务器拓扑](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
<span data-ttu-id="ca838-168">多服务器拓扑提供了服务器池功能。</span><span class="sxs-lookup"><span data-stu-id="ca838-168">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="ca838-169">在服务器池中, 持久聊天服务与数据进行通信和共享。</span><span class="sxs-lookup"><span data-stu-id="ca838-169">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="ca838-170">例如, 您可以从系统中的任何持续聊天服务获取最初发布到一个持久聊天服务的聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="ca838-170">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="ca838-171">通过一个持久聊天服务上载的文件可由任何永久聊天服务访问。</span><span class="sxs-lookup"><span data-stu-id="ca838-171">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="ca838-172">用户可以连接到不同的持久聊天服务器前端服务器, 并且可以相互进行通信。</span><span class="sxs-lookup"><span data-stu-id="ca838-172">Users can be connected to different Persistent Chat Server Front End Servers and can be communicating with each other.</span></span> <span data-ttu-id="ca838-173">TCP 8011 的默认端口将服务器连接到服务器池, 并由持久聊天服务用于自身通信, 或用于管理用途。</span><span class="sxs-lookup"><span data-stu-id="ca838-173">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat services to communicate between themselves, or for administrative purposes.</span></span>
  
<span data-ttu-id="ca838-174">例如, 在四台服务器持久聊天服务器部署 (其中80000用户可以同时登录到持久聊天) 中, 每个服务器的20000用户均会平均分配负载。</span><span class="sxs-lookup"><span data-stu-id="ca838-174">For example, in a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="ca838-175">如果一台服务器不可用, 连接到该服务器的用户将失去其永久聊天服务器的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ca838-175">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="ca838-176">断开连接的用户将自动转移到其他服务器，直至不可用服务器恢复为止。</span><span class="sxs-lookup"><span data-stu-id="ca838-176">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> 
  

