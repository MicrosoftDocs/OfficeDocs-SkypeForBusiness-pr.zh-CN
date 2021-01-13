---
title: 在 Skype for Business Server 2015 中规划持久聊天服务器
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: 摘要：阅读本主题，了解如何在 Skype for Business Server 2015 中规划持久聊天服务器。
ms.openlocfilehash: 9195c149744b9aab9927f0b2a6e490442cff6573
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813662"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="82f4f-103">在 Skype for Business Server 2015 中规划持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="82f4f-103">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="82f4f-104">**摘要：** 阅读本主题，了解如何在 Skype for Business Server 2015 中规划持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="82f4f-104">**Summary:** Read this topic to learn how to plan for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="82f4f-105">持久聊天服务器是一个可选角色，可让贵组织中多个用户参与持续一段时间的聊天室对话。</span><span class="sxs-lookup"><span data-stu-id="82f4f-105">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="82f4f-106">尽管用户可以在聊天会话期间实时通信，但每个会话的内容（包括文本、链接和文件）都是持久的，这意味着用户可以随时查看和搜索会话的所有内容。</span><span class="sxs-lookup"><span data-stu-id="82f4f-106">Although users can communicate in real time during a chat session, the content of each session--including text, links, and files--is persistent, which means users can view and search all content of the session at any time.</span></span>
  
<span data-ttu-id="82f4f-107">持久聊天服务器可帮助改善组织内部的通信，方法为：</span><span class="sxs-lookup"><span data-stu-id="82f4f-107">Persistent Chat Server can help improve communication within your organization by:</span></span>
  
- <span data-ttu-id="82f4f-108">在整个组织中扩大信息意识和参与</span><span class="sxs-lookup"><span data-stu-id="82f4f-108">Broadening information awareness and participation throughout the organization</span></span>
    
- <span data-ttu-id="82f4f-109">启用高效的信息共享</span><span class="sxs-lookup"><span data-stu-id="82f4f-109">Enabling efficient information sharing</span></span> 
    
- <span data-ttu-id="82f4f-110">改善团队之间的通信，包括地理位置分散的跨职能团队</span><span class="sxs-lookup"><span data-stu-id="82f4f-110">Improving communication between teams, including geographically dispersed and cross-functional teams</span></span>
    
- <span data-ttu-id="82f4f-111">减少信息过载</span><span class="sxs-lookup"><span data-stu-id="82f4f-111">Reducing information overload</span></span>
    
- <span data-ttu-id="82f4f-112">通过选择性地部署持久聊天合规性服务遵循合规性法规</span><span class="sxs-lookup"><span data-stu-id="82f4f-112">Following compliance regulations by optionally deploying the Persistent Chat Compliance service</span></span>

> [!NOTE] 
> <span data-ttu-id="82f4f-113">持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="82f4f-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="82f4f-114">Teams 中也提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="82f4f-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="82f4f-115">有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。</span><span class="sxs-lookup"><span data-stu-id="82f4f-115">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="82f4f-116">如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="82f4f-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
    
## <a name="persistent-chat-server-high-level-architecture"></a><span data-ttu-id="82f4f-117">持久聊天服务器高级体系结构</span><span class="sxs-lookup"><span data-stu-id="82f4f-117">Persistent Chat Server high-level architecture</span></span>

<span data-ttu-id="82f4f-118">下图显示了持久聊天服务器体系结构的高级别视图。</span><span class="sxs-lookup"><span data-stu-id="82f4f-118">The following diagram shows a high-level view of the Persistent Chat Server architecture.</span></span> 
  
![持久聊天服务器高级体系结构](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
<span data-ttu-id="82f4f-120">持久聊天由提供持久聊天服务的前端服务器角色以及一个后端SQL数据库组件组成。</span><span class="sxs-lookup"><span data-stu-id="82f4f-120">Persistent Chat consists of a front-end server role that provides the Persistent Chat services as well as a back-end SQL database component.</span></span> <span data-ttu-id="82f4f-121">前端和后端组件都包含在专用的持久聊天池中。</span><span class="sxs-lookup"><span data-stu-id="82f4f-121">Both front-end and back-end components are included in a dedicated Persistent Chat pool.</span></span> <span data-ttu-id="82f4f-122">承载持久聊天服务器的每台计算机都必须有权访问现有的 Skype for Business Server 2015 拓扑。</span><span class="sxs-lookup"><span data-stu-id="82f4f-122">Each computer that hosts Persistent Chat Server must have access to an existing Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="82f4f-123">在此图中，有一个持久聊天服务器池 (A) ，它依赖于 Skype for Business Server 池 A 来将消息路由到该池。</span><span class="sxs-lookup"><span data-stu-id="82f4f-123">In this diagram, there is one Persistent Chat Server pool (A), which is dependent on Skype for Business Server Pool A for routing messages to it.</span></span>
  
<span data-ttu-id="82f4f-124">您可以部署一个或多个持久聊天服务器池，每个池最多支持四个活动持久聊天服务器，支持多达 8 万个并发用户。</span><span class="sxs-lookup"><span data-stu-id="82f4f-124">You can deploy one or more Persistent Chat Server pools, each with up to four active Persistent Chat Servers supporting up to 80K concurrent users.</span></span>
  
<span data-ttu-id="82f4f-125">Skype for Business Server 2015 使用会话初始协议 (SIP) 与持久聊天服务进行通信，通过 SIP 协议扩展聊天通信 (XCCOS) 用于聊天。</span><span class="sxs-lookup"><span data-stu-id="82f4f-125">Skype for Business Server 2015 communicates with the Persistent Chat service using the Session Initiation Protocol (SIP) for registration and the Extensible Chat Communication Over SIP protocol (XCCOS) for chat.</span></span> 
  
## <a name="persistent-chat-services"></a><span data-ttu-id="82f4f-126">持久聊天服务</span><span class="sxs-lookup"><span data-stu-id="82f4f-126">Persistent Chat services</span></span>

<span data-ttu-id="82f4f-127">下图显示了持久聊天服务器前端服务，以及这些服务与后端数据库组件通信的方式。</span><span class="sxs-lookup"><span data-stu-id="82f4f-127">The following diagram shows the Persistent Chat Server front-end services, and how these services communicate with the back-end database components.</span></span> <span data-ttu-id="82f4f-128">前端组件包括持久聊天服务和合规性服务。</span><span class="sxs-lookup"><span data-stu-id="82f4f-128">The front-end components include the Persistent Chat services and the Compliance service.</span></span> <span data-ttu-id="82f4f-129">后端组件包括持久聊天存储和持久聊天合规性存储。</span><span class="sxs-lookup"><span data-stu-id="82f4f-129">The back-end components include the Persistent Chat store and the Persistent Chat compliance store.</span></span>
  
![持久聊天服务器高级服务](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a><span data-ttu-id="82f4f-131">聊天服务</span><span class="sxs-lookup"><span data-stu-id="82f4f-131">Chat service</span></span>

<span data-ttu-id="82f4f-132">聊天服务（也称为频道服务）是负责持久聊天服务器的核心服务。</span><span class="sxs-lookup"><span data-stu-id="82f4f-132">The Chat service, also called the Channel service, is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="82f4f-133">聊天服务提供以下功能：</span><span class="sxs-lookup"><span data-stu-id="82f4f-133">The Chat service provides the following functions:</span></span>
  
- <span data-ttu-id="82f4f-134">接受传入消息</span><span class="sxs-lookup"><span data-stu-id="82f4f-134">Accepts incoming messages</span></span>
    
- <span data-ttu-id="82f4f-135">注册并列出持久聊天室中的联机参与者</span><span class="sxs-lookup"><span data-stu-id="82f4f-135">Registers and lists online participants within a Persistent Chat room</span></span>
    
- <span data-ttu-id="82f4f-136">向其他通道订阅者重新传输消息</span><span class="sxs-lookup"><span data-stu-id="82f4f-136">Retransmits messages to other channel subscribers</span></span>
    
- <span data-ttu-id="82f4f-137">实现通道管理、聊天室邀请、搜索和新内容通知的逻辑</span><span class="sxs-lookup"><span data-stu-id="82f4f-137">Implements logic for channel management, chat room invitations, search and new content notifications</span></span>
    
<span data-ttu-id="82f4f-138">持久聊天服务使用持久聊天存储 (聊天室内容和其他系统元数据，) 规则等。</span><span class="sxs-lookup"><span data-stu-id="82f4f-138">The Persistent Chat service stores and accesses chat room content and other system metadata (authorization rules and so on) by using the Persistent Chat store.</span></span> <span data-ttu-id="82f4f-139">该服务将上载到聊天室的文件存储在持久聊天文件存储中。</span><span class="sxs-lookup"><span data-stu-id="82f4f-139">The service stores files that are uploaded into chat rooms in the Persistent Chat file store.</span></span>
  
### <a name="compliance-service"></a><span data-ttu-id="82f4f-140">合规性服务</span><span class="sxs-lookup"><span data-stu-id="82f4f-140">Compliance service</span></span>

<span data-ttu-id="82f4f-141">如果您的组织规定需要存档持久聊天活动，您可以部署可选的持久聊天合规性服务。</span><span class="sxs-lookup"><span data-stu-id="82f4f-141">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="82f4f-142">合规性服务负责将聊天内容和事件（如加入和离开聊天室）存档到持久聊天合规性文件存储。</span><span class="sxs-lookup"><span data-stu-id="82f4f-142">The Compliance service is responsible for archiving chat content and events, such as joining and leaving rooms, to the Persistent Chat Compliance file store.</span></span> <span data-ttu-id="82f4f-143">合规性服务安装在持久聊天池中的每台持久聊天服务器上。</span><span class="sxs-lookup"><span data-stu-id="82f4f-143">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> 
  
### <a name="web-services"></a><span data-ttu-id="82f4f-144">Web 服务</span><span class="sxs-lookup"><span data-stu-id="82f4f-144">Web services</span></span>

<span data-ttu-id="82f4f-145">持久聊天 Web 服务在 Skype for Business 前端服务器上运行。</span><span class="sxs-lookup"><span data-stu-id="82f4f-145">The Persistent Chat web services run on the Skype for Business Front End Servers.</span></span> <span data-ttu-id="82f4f-146">Web 服务依赖于 IIS Internet Information Services (，) 实现为 Web 组件：</span><span class="sxs-lookup"><span data-stu-id="82f4f-146">The web services depend on Internet Information Services (IIS), and are implemented as web components:</span></span>
  
- <span data-ttu-id="82f4f-147">用于文件上载和下载的持久聊天 Web 服务负责发布和检索聊天室中的文件。</span><span class="sxs-lookup"><span data-stu-id="82f4f-147">Persistent Chat web services for file upload and download are responsible for posting and retrieving files from chat rooms.</span></span>
    
- <span data-ttu-id="82f4f-148">用于聊天室管理的持久聊天 Web 服务负责为用户提供管理其聊天室和创建新聊天室的能力。</span><span class="sxs-lookup"><span data-stu-id="82f4f-148">Persistent Chat web services for chat room management are responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>
    
## <a name="defining-requirements-for-your-organization"></a><span data-ttu-id="82f4f-149">为组织定义要求</span><span class="sxs-lookup"><span data-stu-id="82f4f-149">Defining requirements for your organization</span></span>

<span data-ttu-id="82f4f-150">如果决定部署持久聊天服务器，则需要确定组织的业务需求，然后定义拓扑、基础结构和技术要求以支持业务需求。</span><span class="sxs-lookup"><span data-stu-id="82f4f-150">If you decide to deploy Persistent Chat Server, you'll need to determine your organization's business requirements, then define the topology, infrastructure, and technical requirements to support your business needs.</span></span> <span data-ttu-id="82f4f-151">若要优化部署，需要回答以下问题：</span><span class="sxs-lookup"><span data-stu-id="82f4f-151">To optimize your deployment, you'll need to answer the following questions:</span></span>
  
- <span data-ttu-id="82f4f-152">您是否正在从以前版本的群聊服务器或以前版本的持久聊天服务器迁移，还是首次部署持久聊天服务器？</span><span class="sxs-lookup"><span data-stu-id="82f4f-152">Are you migrating from a previous version of Group Chat Server, or a previous version of Persistent Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>
    
- <span data-ttu-id="82f4f-153">谁可以使用持久聊天服务器？</span><span class="sxs-lookup"><span data-stu-id="82f4f-153">Who can use Persistent Chat Server?</span></span> <span data-ttu-id="82f4f-154">指定持久聊天策略以确定全局、站点或用户级别的用户访问。</span><span class="sxs-lookup"><span data-stu-id="82f4f-154">You specify Persistent Chat policies to determine user access at the global, site, or user level.</span></span>
    
- <span data-ttu-id="82f4f-155">有多少用户需要访问持久聊天服务器？</span><span class="sxs-lookup"><span data-stu-id="82f4f-155">How many users will require access to Persistent Chat Server?</span></span> <span data-ttu-id="82f4f-156">持久聊天服务器支持 150，000 (策略) 启用的用户，以及最多 80，000 个并发用户。</span><span class="sxs-lookup"><span data-stu-id="82f4f-156">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users.</span></span> <span data-ttu-id="82f4f-157">一台持久聊天服务器可支持 20，000 个已连接用户，一个持久聊天服务器池可具有最多 4 个活动服务器，总共 80，000 个并发连接用户。</span><span class="sxs-lookup"><span data-stu-id="82f4f-157">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>
    
- <span data-ttu-id="82f4f-158">您希望如何控制范围、信息隔离边界和访问？</span><span class="sxs-lookup"><span data-stu-id="82f4f-158">How do you want to control scopes, ethical boundaries, and access?</span></span> <span data-ttu-id="82f4f-159">您可以定义类别以隔离这些边界，并选择允许谁位于在每个类别中创建的聊天室中。</span><span class="sxs-lookup"><span data-stu-id="82f4f-159">You can define categories to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>
    
- <span data-ttu-id="82f4f-160">您希望如何控制可创建聊天室的用户？</span><span class="sxs-lookup"><span data-stu-id="82f4f-160">How do you want to control who can create rooms?</span></span> <span data-ttu-id="82f4f-161">你可以定义可以创建聊天室的创建者。</span><span class="sxs-lookup"><span data-stu-id="82f4f-161">You can define creators who can create rooms.</span></span> <span data-ttu-id="82f4f-162">创建者可以将其他成员分配为聊天室管理员，以持续管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="82f4f-162">Creators can assign other members as chat room managers for ongoing management of the rooms.</span></span>
    
- <span data-ttu-id="82f4f-163">您希望如何创建聊天室？</span><span class="sxs-lookup"><span data-stu-id="82f4f-163">How do you want to create rooms?</span></span> <span data-ttu-id="82f4f-164">持久聊天服务器提供用于创建和管理聊天室的基于 Web 的功能。</span><span class="sxs-lookup"><span data-stu-id="82f4f-164">Persistent Chat Server provides a web-based feature for creating and managing rooms.</span></span> <span data-ttu-id="82f4f-165">这可以从 Skype for Business 客户端启动。</span><span class="sxs-lookup"><span data-stu-id="82f4f-165">This can be launched from the Skype for Business client.</span></span> <span data-ttu-id="82f4f-166">可以选择定义实现业务需求和工作流的客户解决方案，并配置持久聊天服务器以将用户引导到自定义解决方案。</span><span class="sxs-lookup"><span data-stu-id="82f4f-166">You can choose to define a customer solution that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>
    
- <span data-ttu-id="82f4f-167">您希望设置哪一类外接程序？</span><span class="sxs-lookup"><span data-stu-id="82f4f-167">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="82f4f-168">外接程序利用 Skype for Business 客户端中的扩展性窗格提供与聊天室相关的上下文，从而增强聊天室内体验。</span><span class="sxs-lookup"><span data-stu-id="82f4f-168">Add-ins enhance the in-room experience by leveraging the extensibility pane in the Skype for Business client to provide context that is relevant to the room.</span></span> <span data-ttu-id="82f4f-169">您可以选择可能最有用的常规外接程序（例如，您的公司网站、内部协作文档等）。</span><span class="sxs-lookup"><span data-stu-id="82f4f-169">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="82f4f-170">聊天室管理员可选择某个注册的外接程序并将该外接程序与其聊天室关联（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="82f4f-170">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span> 
    
- <span data-ttu-id="82f4f-171">您具有哪一类高可用性和灾难恢复要求？</span><span class="sxs-lookup"><span data-stu-id="82f4f-171">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="82f4f-172">持久聊天服务器SQL Server镜像和SQL Server群集实现高可用性。</span><span class="sxs-lookup"><span data-stu-id="82f4f-172">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability.</span></span> <span data-ttu-id="82f4f-173">对于灾难恢复，持久聊天服务器支持最多 8 台服务器 (4 个活动服务器，在拉伸池中支持 4) 备用服务器，SQL Server日志。</span><span class="sxs-lookup"><span data-stu-id="82f4f-173">For disaster recovery, Persistent Chat Server supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping.</span></span> 
    
- <span data-ttu-id="82f4f-174">是否有管理要求？</span><span class="sxs-lookup"><span data-stu-id="82f4f-174">Are there regulatory requirements?</span></span> <span data-ttu-id="82f4f-175">如果您的公司位于需要将数据保留在国家/地区内的一个或多个国家/地区，您可能需要部署多个持久聊天服务器池，每个池都是特定地理位置的本地池。</span><span class="sxs-lookup"><span data-stu-id="82f4f-175">If your company is in a country or region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="82f4f-176">聊天室、类别或外接程序不跨池，它仅属于一个持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="82f4f-176">A room, category, or add-in does not span pools--it belongs to only one Persistent Chat Server pool.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="82f4f-177">拥有多个持久聊天服务器池不会为您提供更多的扩展 (您在所有持久聊天服务器池中仍只能有 80，000 个并发) 。</span><span class="sxs-lookup"><span data-stu-id="82f4f-177">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrent users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="82f4f-178">支持多个持久聊天服务器池的主要原因是支持法规问题。</span><span class="sxs-lookup"><span data-stu-id="82f4f-178">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="82f4f-179">详细信息</span><span class="sxs-lookup"><span data-stu-id="82f4f-179">For more information</span></span>

<span data-ttu-id="82f4f-180">有关安装和配置持久聊天服务器的信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="82f4f-180">For more information about installing and configuring Persistent Chat Server, see the following topics:</span></span>
  
- <span data-ttu-id="82f4f-181">若要详细了解如何部署持久聊天服务器，请参阅在 [Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)中部署持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="82f4f-181">For details about how to deploy Persistent Chat Server, see [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md).</span></span> 
    
- <span data-ttu-id="82f4f-182">若要详细了解如何在持久聊天服务器部署上配置设置，请参阅"在 [Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md)中管理持久聊天服务器"。</span><span class="sxs-lookup"><span data-stu-id="82f4f-182">For details about how to configure settings on your Persistent Chat Server deployment, see [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
    

