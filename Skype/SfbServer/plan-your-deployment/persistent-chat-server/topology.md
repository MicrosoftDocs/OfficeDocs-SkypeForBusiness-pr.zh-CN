---
title: 规划持久聊天服务器拓扑
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 5/17/2016
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a0a14a0-baad-44e9-b26e-4d192c0a0e70
description: 摘要： 阅读本主题，以学习业务服务器 2015年有关持久聊天服务器组件和 Skype 的拓扑。
ms.openlocfilehash: 11d12283c3ee302c8133b0a56bbea53315508aec
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-persistent-chat-server-topology"></a><span data-ttu-id="b158e-103">规划持久聊天服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="b158e-103">Plan Persistent Chat Server topology</span></span>
 
<span data-ttu-id="b158e-104">**摘要：**阅读本主题，以学习业务服务器 2015年有关持久聊天服务器组件和 Skype 的拓扑。</span><span class="sxs-lookup"><span data-stu-id="b158e-104">**Summary:** Read this topic to learn about Persistent Chat Server components and topologies in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="b158e-105">持久的聊天服务器支持单服务器和多服务器配置。</span><span class="sxs-lookup"><span data-stu-id="b158e-105">Persistent Chat Server supports both single-server and multiple-server configurations.</span></span> <span data-ttu-id="b158e-106">业务服务器 2015年企业版或标准版服务器，您可以安装在任何一个 Skype 上持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="b158e-106">You can install Persistent Chat Server on either a Skype for Business Server 2015 Enterprise Edition or Standard Edition Server.</span></span> 
  
## <a name="persistent-chat-server-components"></a><span data-ttu-id="b158e-107">持久的聊天服务器组件</span><span class="sxs-lookup"><span data-stu-id="b158e-107">Persistent Chat Server components</span></span>

<span data-ttu-id="b158e-108">持久聊天服务器由以下组件组成：</span><span class="sxs-lookup"><span data-stu-id="b158e-108">Persistent Chat Server consists of the following components:</span></span>
  
- <span data-ttu-id="b158e-109">一个或多个计算机运行持续聊天服务器并提供以下服务：</span><span class="sxs-lookup"><span data-stu-id="b158e-109">One or more computers running Persistent Chat Server and providing the following services:</span></span>
    
  - <span data-ttu-id="b158e-110">持久的聊天服务</span><span class="sxs-lookup"><span data-stu-id="b158e-110">Persistent Chat service</span></span>
    
  - <span data-ttu-id="b158e-111">合规性服务，在启用合规性时打开</span><span class="sxs-lookup"><span data-stu-id="b158e-111">Compliance service, which is turned on if compliance is enabled</span></span>
    
- <span data-ttu-id="b158e-112">一个或多个服务器 （一个以上如果使用了镜像） 运行持续聊天内容数据库所在的 SQL Server 后端数据库存储聊天室内容、 房间和类别。</span><span class="sxs-lookup"><span data-stu-id="b158e-112">One or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat content database where chat room content, rooms, and categories are stored.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b158e-113">后端数据库存储聊天历史数据，包括有关信息类别和创建持久性聊天室。</span><span class="sxs-lookup"><span data-stu-id="b158e-113">The back-end database stores chat history data, including information about categories and Persistent Chat rooms that are created.</span></span> 
  
- <span data-ttu-id="b158e-114">如果启用了法规遵从性，（一个以上如果使用了镜像） 的一个或多个服务器运行 SQL Server 的后端数据库承载持久聊天法规数据库，出于法规遵从目的符合性事件和聊天的内容位置存储。</span><span class="sxs-lookup"><span data-stu-id="b158e-114">If compliance is enabled, one or more servers (more than one if mirroring is used) running the SQL Server back-end database for hosting the Persistent Chat Compliance database, where compliance events and chat content for the purpose of compliance are stored.</span></span>
    
<span data-ttu-id="b158e-115">持久的聊天服务器的硬件和软件要求的详细信息，请参阅[业务服务器 2015年的 Skype 的服务要求](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)和[业务服务器 2015年的 Skype 的持久聊天服务器的硬件和软件要求](hardware-and-software-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="b158e-115">For details about hardware and software requirements for Persistent Chat Server, see [Server requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md) and [Hardware and software requirements for Persistent Chat Server in Skype for Business Server 2015](hardware-and-software-requirements.md).</span></span> 
  
## <a name="persistent-chat-server-topologies"></a><span data-ttu-id="b158e-116">持久的聊天服务器拓扑</span><span class="sxs-lookup"><span data-stu-id="b158e-116">Persistent Chat Server topologies</span></span>

<span data-ttu-id="b158e-117">您可以部署持续聊天服务器单个服务器或多服务器池，再加上单池或多个池的拓扑结构。</span><span class="sxs-lookup"><span data-stu-id="b158e-117">You can deploy Persistent Chat Server in single-server or multiple-server pools, and with single-pool or multiple-pool topology.</span></span> <span data-ttu-id="b158e-118">持久的聊天服务器支持下列拓扑：</span><span class="sxs-lookup"><span data-stu-id="b158e-118">Persistent Chat Server supports the following topologies:</span></span>
  
-  <span data-ttu-id="b158e-119">Standard Edition Server 与持久聊天服务器并置在前端服务器上</span><span class="sxs-lookup"><span data-stu-id="b158e-119">Standard Edition Server with Persistent Chat Server collocated on the Front End Server</span></span>
    
-  <span data-ttu-id="b158e-120">标准版服务器与持久聊天服务器不同的服务器上</span><span class="sxs-lookup"><span data-stu-id="b158e-120">Standard Edition Server with Persistent Chat Server on a separate server</span></span>
    
-  <span data-ttu-id="b158e-121">企业版服务器与一个持久聊天服务器不同的服务器上</span><span class="sxs-lookup"><span data-stu-id="b158e-121">Enterprise Edition Server with a single Persistent Chat Server on a separate server</span></span>
    
-  <span data-ttu-id="b158e-122">企业版服务器与多个持久聊天服务器不同的服务器上</span><span class="sxs-lookup"><span data-stu-id="b158e-122">Enterprise Edition Server with more than one Persistent Chat Server on separate servers</span></span>
    
<span data-ttu-id="b158e-123">虽然您可以部署在标准版服务器的持久性聊天服务器，请注意，会影响性能和可扩展性，高可用性不是一个选项。</span><span class="sxs-lookup"><span data-stu-id="b158e-123">Although you can deploy Persistent Chat Server on a Standard Edition Server, be aware that performance and scale will be affected, and high availability is not an option.</span></span> <span data-ttu-id="b158e-124">因此，建议您将部署在主要的概念和评估目的的证明标准版服务器持续聊天。</span><span class="sxs-lookup"><span data-stu-id="b158e-124">Therefore, it is recommended that you deploy Persistent Chat on a Standard Edition Server primarily for proof of concept and evaluation purposes.</span></span> 
  
<span data-ttu-id="b158e-125">Skype 的业务服务器 2015年支持多种配置方案，为您提供的灵活性来节约硬件成本由多个组件运行在一个服务器上 （如果您有一个小的组织），或不同的服务器 （运行单个组件如果您有一个较大的组织所需要的可扩展性和性能）。</span><span class="sxs-lookup"><span data-stu-id="b158e-125">Skype for Business Server 2015 supports a variety of collocation scenarios, providing you the flexibility to save hardware costs by running multiple components on one server (if you have a small organization), or to run individual components on different servers (if you have a larger organization that needs scalability and performance).</span></span> <span data-ttu-id="b158e-126">在决定是否布置组件之前，应考虑可伸缩性因素。</span><span class="sxs-lookup"><span data-stu-id="b158e-126">You should consider scalability factors before deciding whether to collocate components.</span></span> <span data-ttu-id="b158e-127">Skype 业务服务器 2015年企业版和标准版服务器的不同配置方案。</span><span class="sxs-lookup"><span data-stu-id="b158e-127">Collocation scenarios differ for Skype for Business Server 2015 Enterprise Edition and Standard Edition servers.</span></span> 
  
<span data-ttu-id="b158e-128">以下几节更为具体地介绍了拓扑，包括并置方案和后端数据库服务器选项。</span><span class="sxs-lookup"><span data-stu-id="b158e-128">The following sections describe the topologies in more detail, including collocation scenarios and options for the back-end database servers.</span></span> <span data-ttu-id="b158e-129">所有服务器角色和数据库的配置的详细信息，请参阅[拓扑业务服务器 2015年的 Skype 的基础知识](../../plan-your-deployment/topology-basics/topology-basics.md)。</span><span class="sxs-lookup"><span data-stu-id="b158e-129">For details about collocation of all server roles and databases, see [Topology Basics for Skype for Business Server 2015](../../plan-your-deployment/topology-basics/topology-basics.md).</span></span>
  
### <a name="standard-edition-server-with-persistent-chat-server-collocated-on-the-front-end-server"></a><span data-ttu-id="b158e-130">Standard Edition Server 与持久聊天服务器并置在前端服务器上</span><span class="sxs-lookup"><span data-stu-id="b158e-130">Standard Edition Server with Persistent Chat Server collocated on the Front End Server</span></span>

<span data-ttu-id="b158e-131">使用 Standard Edition，可以将持久聊天并置在前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="b158e-131">With Standard Edition, you can collocate Persistent Chat on the Front End Server.</span></span> <span data-ttu-id="b158e-132">这是最简单也最基本的配置。</span><span class="sxs-lookup"><span data-stu-id="b158e-132">This is the simplest and most basic configuration.</span></span> <span data-ttu-id="b158e-133">您必须确保现有前端服务器具有足够的容量的物理资源： CPU、 内存、 磁盘空间等等。</span><span class="sxs-lookup"><span data-stu-id="b158e-133">You must make sure that the existing Front End Server has enough capacity in terms of physical resources: CPU, memory, disk space, and so on.</span></span>
  
<span data-ttu-id="b158e-134">此外，您可以配置持久聊天服务器后端服务器和持久聊天的法规遵从性数据库 （如果已启用） 本地 SQL Server Express 后端服务器上。</span><span class="sxs-lookup"><span data-stu-id="b158e-134">In addition, you can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server.</span></span> <span data-ttu-id="b158e-135">还可以选择使用独立的 SQL Server 及专用实例。</span><span class="sxs-lookup"><span data-stu-id="b158e-135">You can also choose to use a separate SQL Server with a dedicated instance.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b158e-136">如果第一个持久聊天服务器搭配使用标准版前端服务器，不能到持久聊天服务器池添加其他服务器。</span><span class="sxs-lookup"><span data-stu-id="b158e-136">You cannot add additional servers to a Persistent Chat Server pool if the first Persistent Chat Server is collocated with a Standard Edition Front End Server.</span></span> <span data-ttu-id="b158e-137">建议您安装第一台服务器作为独立实例，以便您可以添加更多服务器以后，如果需要。</span><span class="sxs-lookup"><span data-stu-id="b158e-137">It is recommended that you install the first server as a standalone instance so that you can add more servers later, if needed.</span></span> 
  
### <a name="standard-edition-server-with-persistent-chat-server-installed-on-a-separate-server"></a><span data-ttu-id="b158e-138">Standard Edition Server 与持久聊天服务器安装在不同的服务器上</span><span class="sxs-lookup"><span data-stu-id="b158e-138">Standard Edition Server with Persistent Chat Server installed on a separate server</span></span>

<span data-ttu-id="b158e-139">使用 Standard Edition，您可以将持久聊天服务器作为独立实例安装，随后按需添加更多服务器。  </span><span class="sxs-lookup"><span data-stu-id="b158e-139">With Standard Edition, you can install Persistent Chat Server as a standalone instance and add more servers later if needed.</span></span> 
  
<span data-ttu-id="b158e-140">您可以配置持久聊天服务器后端服务器和持久聊天的法规遵从性数据库 （如果已启用） 本地 SQL Server Express 后端服务器上。</span><span class="sxs-lookup"><span data-stu-id="b158e-140">You can collocate the Persistent Chat Server back-end server and the Persistent Chat Compliance database (if enabled) on the local SQL Server Express back-end server.</span></span> <span data-ttu-id="b158e-141">还可以选择使用独立的 SQL Server 及专用实例。</span><span class="sxs-lookup"><span data-stu-id="b158e-141">You can also choose to use a separate SQL Server with a dedicated instance.</span></span> 
  
### <a name="enterprise-edition-server-with-a-single-persistent-chat-server"></a><span data-ttu-id="b158e-142">Enterprise Edition Server 与一个持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="b158e-142">Enterprise Edition Server with a single Persistent Chat Server</span></span>

<span data-ttu-id="b158e-143">使用 Enterprise Edition 时，必须将持久聊天服务器安装在不同的计算机上。</span><span class="sxs-lookup"><span data-stu-id="b158e-143">With Enterprise Edition, you must install the Persistent Chat Server on a separate computer.</span></span> <span data-ttu-id="b158e-144">也就是说，不能将持久聊天服务器并置在 Enterprise Edition 前端服务器上。</span><span class="sxs-lookup"><span data-stu-id="b158e-144">That is, you cannot collocate the Persistent Chat Server on the Enterprise Edition Front End Server.</span></span> <span data-ttu-id="b158e-145">此部署需要一个单独的服务器，它运行持续聊天服务器和法规遵从性服务 （如果已启用）。</span><span class="sxs-lookup"><span data-stu-id="b158e-145">This deployment requires a separate server that runs Persistent Chat Server and the Compliance service (if enabled).</span></span>
  
<span data-ttu-id="b158e-146">但是，可以前端企业版池的后端数据库上为持久聊天服务器布置的 SQL Server 数据库。</span><span class="sxs-lookup"><span data-stu-id="b158e-146">You can, however, collocate the SQL Server database for Persistent Chat Server on the back-end database of an Enterprise Edition Front End pool.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b158e-147">如果计划为 HA DR 使用 SQL AlwaysOn 可用性组，请注意它不受持久聊天服务器数据库支持。</span><span class="sxs-lookup"><span data-stu-id="b158e-147">If you plan to use SQL AlwaysOn Availability Groups for HA DR, note that it is not supported for Persistent Chat Server databases.</span></span> 
  
<span data-ttu-id="b158e-148">如果布置的持久聊天数据库后端数据库，您可以任意或所有数据库，都使用 SQL Server 的单个实例或您可以为每个数据库都使用一个单独的 SQL Server 实例。</span><span class="sxs-lookup"><span data-stu-id="b158e-148">If you collocate the Persistent Chat database with the back-end database, you can either use a single instance of SQL Server for any or all of the databases, or you can use a separate instance of SQL Server for each database.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="b158e-149">持续聊天数据库所在的服务器可以承载其他数据库。</span><span class="sxs-lookup"><span data-stu-id="b158e-149">The server hosting the Persistent Chat database can host other databases.</span></span> <span data-ttu-id="b158e-150">但是，考虑配置持久聊天数据库与其他数据库时，会意识到，如果有存储的多个用户的邮件时，磁盘空间需要持久聊天数据库可以变得非常大。</span><span class="sxs-lookup"><span data-stu-id="b158e-150">However, when you consider collocating the Persistent Chat database with other databases, be aware that if you are storing the messages of more than a few users, the disk space needed by the Persistent Chat database can grow very large.</span></span> <span data-ttu-id="b158e-151">由于这个原因，我们不建议配置的持久聊天数据库后端数据库。</span><span class="sxs-lookup"><span data-stu-id="b158e-151">For this reason, we do not recommend collocating the Persistent Chat database with the back-end database.</span></span> 
  
<span data-ttu-id="b158e-152">下图显示了一个拓扑中的所有组件单个持久聊天服务器启用的法规 （可选）。</span><span class="sxs-lookup"><span data-stu-id="b158e-152">The following figure shows all components of a topology for a single Persistent Chat Server with compliance enabled (optional).</span></span>
  
<span data-ttu-id="b158e-153">**单服务器拓扑**</span><span class="sxs-lookup"><span data-stu-id="b158e-153">**Single Server Topology**</span></span>

![持久聊天服务器 - 单服务器拓扑](../../media/e1b39c28-8a4d-4c03-983b-4392889c2d14.png)
  
### <a name="enterprise-edition-server-with-multiple-persistent-chat-servers"></a><span data-ttu-id="b158e-155">Enterprise Edition Server 与多个持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="b158e-155">Enterprise Edition Server with multiple Persistent Chat Servers</span></span>

<span data-ttu-id="b158e-156">使用企业版，您可以部署一个多服务器拓扑结构为更高容量和可靠性。</span><span class="sxs-lookup"><span data-stu-id="b158e-156">With Enterprise Edition, you can deploy a multiple-server topology for greater capacity and reliability.</span></span> <span data-ttu-id="b158e-157">一个多服务器拓扑结构相同的单服务器拓扑只是多个服务器维护持久聊天服务器，并且可扩展性更高。</span><span class="sxs-lookup"><span data-stu-id="b158e-157">A multiple-server topology is the same as the single-server topology except that multiple servers host Persistent Chat Server, and can scale higher.</span></span> <span data-ttu-id="b158e-158">多服务器拓扑结构可以包含多达四个活动的计算机运行持续聊天服务器 （高可用性和灾难恢复配置将允许多达 8 个，但只有四个可以主动和剩余的四个待机状态）。</span><span class="sxs-lookup"><span data-stu-id="b158e-158">The multiple-server topology can include as many as four active computers running Persistent Chat Server (high availability and disaster recovery configurations will allow up to eight, but only four can be active and the remaining four on standby).</span></span> <span data-ttu-id="b158e-159">每个服务器可以支持多达 20000 个并发用户，总共为 80000 并发用户连接到 4 服务器的持久性聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="b158e-159">Each server can support as many as 20,000 concurrent users, for a total of 80,000 concurrent users connected to a Persistent Chat Server pool with 4 servers.</span></span> <span data-ttu-id="b158e-160">多台计算机运行持续聊天服务器应位于 Skype 与位于同一 Active Directory 域服务域业务服务器和法规遵从性服务。</span><span class="sxs-lookup"><span data-stu-id="b158e-160">Multiple computers running Persistent Chat Server should reside in the same Active Directory Domain Services domain as Skype for Business Server and the Compliance service.</span></span>
  
<span data-ttu-id="b158e-161">下图显示所有组件的多服务器拓扑结构与多台计算机运行持续聊天服务器、 可选的法规遵从性服务和一个单独的法规遵从性数据库。</span><span class="sxs-lookup"><span data-stu-id="b158e-161">The following figure shows all the components of a multiple-server topology with multiple computers running Persistent Chat Server, the optional Compliance service, and a separate compliance database.</span></span>
  
<span data-ttu-id="b158e-162">**多服务器拓扑结构**</span><span class="sxs-lookup"><span data-stu-id="b158e-162">**Multiple Server Topology**</span></span>

![持久聊天服务器 - 多服务器拓扑](../../media/8fc20997-7acc-46ea-8dea-11239ffd9458.png)
  
<span data-ttu-id="b158e-164">多服务器拓扑提供了服务器池功能。</span><span class="sxs-lookup"><span data-stu-id="b158e-164">Multiple-server topologies provide pooling of server functionality.</span></span> <span data-ttu-id="b158e-165">池中服务器持续聊天服务进行通讯和共享数据。</span><span class="sxs-lookup"><span data-stu-id="b158e-165">In a server pool, the Persistent Chat services communicate and share data.</span></span> <span data-ttu-id="b158e-166">例如，最初过帐到一个持久的聊天服务的聊天历史提供了任何持久聊天服务系统中。</span><span class="sxs-lookup"><span data-stu-id="b158e-166">For example, chat history that was originally posted to one Persistent Chat service is available from any Persistent Chat service in the system.</span></span> <span data-ttu-id="b158e-167">通过一个持久聊天服务上载的文件的可由任何持久聊天服务。</span><span class="sxs-lookup"><span data-stu-id="b158e-167">A file that is uploaded through one Persistent Chat service can be accessed by any Persistent Chat service.</span></span> <span data-ttu-id="b158e-168">用户可以连接到不同持久聊天服务器前端服务器，可以彼此通信。</span><span class="sxs-lookup"><span data-stu-id="b158e-168">Users can be connected to different Persistent Chat Server Front End Servers and can be communicating with each other.</span></span> <span data-ttu-id="b158e-169">默认端口的 TCP 8011 将服务器连接到服务器池，并持续聊天服务用于通信之间本身，或出于管理的目的。</span><span class="sxs-lookup"><span data-stu-id="b158e-169">The default port of TCP 8011 connects a server to a server pool, and is used by the Persistent Chat services to communicate between themselves, or for administrative purposes.</span></span>
  
<span data-ttu-id="b158e-170">例如，在四台服务器持续聊天服务器中部署，80000 用户可以同时登录并使用持久聊天，负载均匀分布在每个服务器的 20000 个用户。</span><span class="sxs-lookup"><span data-stu-id="b158e-170">For example, in a four-server Persistent Chat Server deployment, where 80,000 users can be simultaneously signed in to and using Persistent Chat, the load is distributed evenly at 20,000 users per server.</span></span> <span data-ttu-id="b158e-171">如果一台服务器变得不可用，连接到该服务器的用户将无法持久聊天服务器的访问。</span><span class="sxs-lookup"><span data-stu-id="b158e-171">If one server becomes unavailable, the users who are connected to that server will lose their access to Persistent Chat Server.</span></span> <span data-ttu-id="b158e-172">断开连接的用户将自动转移到其他服务器，直至不可用服务器恢复为止。</span><span class="sxs-lookup"><span data-stu-id="b158e-172">The disconnected users will be automatically transferred to the remaining servers until the unavailable server is restored.</span></span> 
  

