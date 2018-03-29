---
title: 规划 Skype for Business Server 2015 中的持久聊天服务器
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: 摘要： 阅读本主题，以了解如何在 Skype 的持久聊天服务器的业务服务器 2015年计划。
ms.openlocfilehash: 0380b5ebb43e198160faa3e7f10b1563b4def80f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="590d4-103">规划 Skype for Business Server 2015 中的持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="590d4-103">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="590d4-104">**摘要：**阅读本主题，以了解如何在 Skype 的持久聊天服务器的业务服务器 2015年计划。</span><span class="sxs-lookup"><span data-stu-id="590d4-104">**Summary:** Read this topic to learn how to plan for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="590d4-105">持久的聊天服务器是可让您的组织中的多个用户的可选角色参与随着时间的推移保持的聊天室会话。</span><span class="sxs-lookup"><span data-stu-id="590d4-105">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="590d4-106">尽管用户可以在聊天会话期间实时通信，每个会话的内容 - 包括文本、链接和文件 - 将持久存在，这意味着用户可以随时查看和搜索所有会话内容。</span><span class="sxs-lookup"><span data-stu-id="590d4-106">Although users can communicate in real time during a chat session, the content of each session--including text, links, and files--is persistent, which means users can view and search all content of the session at any time.</span></span>
  
<span data-ttu-id="590d4-107">持久的聊天服务器可以帮助改善由组织内的沟通：</span><span class="sxs-lookup"><span data-stu-id="590d4-107">Persistent Chat Server can help improve communication within your organization by:</span></span>
  
- <span data-ttu-id="590d4-108">扩大组织内的信息意识和参与度</span><span class="sxs-lookup"><span data-stu-id="590d4-108">Broadening information awareness and participation throughout the organization</span></span>
    
- <span data-ttu-id="590d4-109">支持高效的信息共享</span><span class="sxs-lookup"><span data-stu-id="590d4-109">Enabling efficient information sharing</span></span> 
    
- <span data-ttu-id="590d4-110">提高团队，包括地理位置分散和跨职能团队之间的通信</span><span class="sxs-lookup"><span data-stu-id="590d4-110">Improving communication between teams, including geographically dispersed and cross-functional teams</span></span>
    
- <span data-ttu-id="590d4-111">减少信息过载</span><span class="sxs-lookup"><span data-stu-id="590d4-111">Reducing information overload</span></span>
    
- <span data-ttu-id="590d4-112">通过有选择地部署持久聊天合规性服务来遵守合规性法规</span><span class="sxs-lookup"><span data-stu-id="590d4-112">Following compliance regulations by optionally deploying the Persistent Chat Compliance service</span></span>
    
## <a name="persistent-chat-server-high-level-architecture"></a><span data-ttu-id="590d4-113">持久聊天服务器高级体系结构</span><span class="sxs-lookup"><span data-stu-id="590d4-113">Persistent Chat Server high-level architecture</span></span>

<span data-ttu-id="590d4-114">下图显示了持久聊天服务器体系结构的高级视图。</span><span class="sxs-lookup"><span data-stu-id="590d4-114">The following diagram shows a high-level view of the Persistent Chat Server architecture.</span></span> 
  
![持久聊天服务器高级体系结构](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
<span data-ttu-id="590d4-116">持久聊天包含前端服务器角色（提供持久聊天服务）以及后端 SQL 数据库组件。</span><span class="sxs-lookup"><span data-stu-id="590d4-116">Persistent Chat consists of a front-end server role that provides the Persistent Chat services as well as a back-end SQL database component.</span></span> <span data-ttu-id="590d4-117">前端和后端组件都包含在专门的持久聊天池中。</span><span class="sxs-lookup"><span data-stu-id="590d4-117">Both front-end and back-end components are included in a dedicated Persistent Chat pool.</span></span> <span data-ttu-id="590d4-118">承载持久聊天服务器的每台计算机必须具有对现有 Skype 业务服务器 2015年拓扑的访问权限。</span><span class="sxs-lookup"><span data-stu-id="590d4-118">Each computer that hosts Persistent Chat Server must have access to an existing Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="590d4-119">在此图中，没有一个持续聊天服务器池 (A)，这取决于向其路由邮件的业务服务器池 a Skype。</span><span class="sxs-lookup"><span data-stu-id="590d4-119">In this diagram, there is one Persistent Chat Server pool (A), which is dependent on Skype for Business Server Pool A for routing messages to it.</span></span>
  
<span data-ttu-id="590d4-120">您可以部署一个或多个持久性聊天服务器池，每个都有最多四个活动持久聊天服务器支持向上到 80 K 并发用户。</span><span class="sxs-lookup"><span data-stu-id="590d4-120">You can deploy one or more Persistent Chat Server pools, each with up to four active Persistent Chat Servers supporting up to 80K concurrent users.</span></span>
  
<span data-ttu-id="590d4-121">业务服务器 2015年的 Skype 与持久的聊天服务，使用注册和可扩展聊天通信通过 SIP 协议 (XCCOS) 对聊天会话启动协议 (SIP) 通信。</span><span class="sxs-lookup"><span data-stu-id="590d4-121">Skype for Business Server 2015 communicates with the Persistent Chat service using the Session Initiation Protocol (SIP) for registration and the Extensible Chat Communication Over SIP protocol (XCCOS) for chat.</span></span> 
  
## <a name="persistent-chat-services"></a><span data-ttu-id="590d4-122">持久聊天服务</span><span class="sxs-lookup"><span data-stu-id="590d4-122">Persistent Chat services</span></span>

<span data-ttu-id="590d4-123">下图显示了持久聊天服务器前端服务，以及这些服务如何与后端数据库组件进行通信。</span><span class="sxs-lookup"><span data-stu-id="590d4-123">The following diagram shows the Persistent Chat Server front-end services, and how these services communicate with the back-end database components.</span></span> <span data-ttu-id="590d4-124">前端组件包括持久聊天服务和合规性服务。</span><span class="sxs-lookup"><span data-stu-id="590d4-124">The front-end components include the Persistent Chat services and the Compliance service.</span></span> <span data-ttu-id="590d4-125">后端组件包括持久聊天存储和持久聊天合规性存储。</span><span class="sxs-lookup"><span data-stu-id="590d4-125">The back-end components include the Persistent Chat store and the Persistent Chat compliance store.</span></span>
  
![持久聊天服务器高级服务](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a><span data-ttu-id="590d4-127">聊天服务</span><span class="sxs-lookup"><span data-stu-id="590d4-127">Chat service</span></span>

<span data-ttu-id="590d4-128">聊天服务（也称作通道服务）是用于持久聊天服务器的核心服务。</span><span class="sxs-lookup"><span data-stu-id="590d4-128">The Chat service, also called the Channel service, is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="590d4-129">聊天服务提供了以下功能：</span><span class="sxs-lookup"><span data-stu-id="590d4-129">The Chat service provides the following functions:</span></span>
  
- <span data-ttu-id="590d4-130">接受传入消息</span><span class="sxs-lookup"><span data-stu-id="590d4-130">Accepts incoming messages</span></span>
    
- <span data-ttu-id="590d4-131">注册，并列出了持久聊天工作室的在线参与者</span><span class="sxs-lookup"><span data-stu-id="590d4-131">Registers and lists online participants within a Persistent Chat room</span></span>
    
- <span data-ttu-id="590d4-132">重新传输到其他频道订阅服务器上的邮件</span><span class="sxs-lookup"><span data-stu-id="590d4-132">Retransmits messages to other channel subscribers</span></span>
    
- <span data-ttu-id="590d4-133">实现通道管理、聊天室邀请、搜索和新内容通知的逻辑</span><span class="sxs-lookup"><span data-stu-id="590d4-133">Implements logic for channel management, chat room invitations, search and new content notifications</span></span>
    
<span data-ttu-id="590d4-134">持久聊天服务使用持久聊天存储来存储和访问聊天室内容和其他系统元数据（授权规则等）。</span><span class="sxs-lookup"><span data-stu-id="590d4-134">The Persistent Chat service stores and accesses chat room content and other system metadata (authorization rules and so on) by using the Persistent Chat store.</span></span> <span data-ttu-id="590d4-135">此服务将上载到聊天室中的文件存储到持久聊天文件存储中。</span><span class="sxs-lookup"><span data-stu-id="590d4-135">The service stores files that are uploaded into chat rooms in the Persistent Chat file store.</span></span>
  
### <a name="compliance-service"></a><span data-ttu-id="590d4-136">合规性服务</span><span class="sxs-lookup"><span data-stu-id="590d4-136">Compliance service</span></span>

<span data-ttu-id="590d4-137">如果您的组织规定必须存档持久聊天活动，您可以部署可选的持久聊天合规性服务。</span><span class="sxs-lookup"><span data-stu-id="590d4-137">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="590d4-138">合规性服务用于将聊天内容和事件（比如加入和离开聊天室）存档到持久聊天合规性文件存储中。</span><span class="sxs-lookup"><span data-stu-id="590d4-138">The Compliance service is responsible for archiving chat content and events, such as joining and leaving rooms, to the Persistent Chat Compliance file store.</span></span> <span data-ttu-id="590d4-139">持续聊天池中每个持久聊天服务器上安装了法规遵从性服务。</span><span class="sxs-lookup"><span data-stu-id="590d4-139">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> 
  
### <a name="web-services"></a><span data-ttu-id="590d4-140">Web 服务</span><span class="sxs-lookup"><span data-stu-id="590d4-140">Web services</span></span>

<span data-ttu-id="590d4-141">持续聊天 web 服务运行在 Skype 上业务前端服务器。</span><span class="sxs-lookup"><span data-stu-id="590d4-141">The Persistent Chat web services run on the Skype for Business Front End Servers.</span></span> <span data-ttu-id="590d4-142">Web 服务依赖于 Internet 信息服务 (IIS)，其被实施为 Web 组件：</span><span class="sxs-lookup"><span data-stu-id="590d4-142">The web services depend on Internet Information Services (IIS), and are implemented as web components:</span></span>
  
- <span data-ttu-id="590d4-143">用于文件上载和下载的持久聊天 Web 服务   负责在聊天室中发布和检索文件。</span><span class="sxs-lookup"><span data-stu-id="590d4-143">Persistent Chat web services for file upload and download are responsible for posting and retrieving files from chat rooms.</span></span>
    
- <span data-ttu-id="590d4-144">用于聊天室管理的持久聊天 Web 服务负责为用户提供管理其聊天室和创建新聊天室的能力。</span><span class="sxs-lookup"><span data-stu-id="590d4-144">Persistent Chat web services for chat room management are responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>
    
## <a name="defining-requirements-for-your-organization"></a><span data-ttu-id="590d4-145">为您的组织定义要求</span><span class="sxs-lookup"><span data-stu-id="590d4-145">Defining requirements for your organization</span></span>

<span data-ttu-id="590d4-146">如果您决定将持久聊天服务器部署，您需要确定贵组织的业务需求，然后定义拓扑、 基础架构和技术要求，以支持您的业务需求。</span><span class="sxs-lookup"><span data-stu-id="590d4-146">If you decide to deploy Persistent Chat Server, you'll need to determine your organization's business requirements, then define the topology, infrastructure, and technical requirements to support your business needs.</span></span> <span data-ttu-id="590d4-147">若要优化您的部署，您需要回答以下问题：</span><span class="sxs-lookup"><span data-stu-id="590d4-147">To optimize your deployment, you'll need to answer the following questions:</span></span>
  
- <span data-ttu-id="590d4-148">您正在迁移组聊天服务器的早期版本或以前版本的持久聊天服务器，或者第一次部署持续聊天服务器？</span><span class="sxs-lookup"><span data-stu-id="590d4-148">Are you migrating from a previous version of Group Chat Server, or a previous version of Persistent Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>
    
- <span data-ttu-id="590d4-p109">谁可以使用持久聊天服务器？您指定持久聊天策略以在全局、站点或用户级别确定用户访问权限。</span><span class="sxs-lookup"><span data-stu-id="590d4-p109">Who can use Persistent Chat Server? You specify Persistent Chat policies to determine user access at the global, site, or user level.</span></span>
    
- <span data-ttu-id="590d4-p110">多少用户将要求访问持久聊天服务器？持久聊天服务器支持 150,000 个已设置用户（由策略启用）以及最多 80,000 个并发用户。一个持久聊天服务器可支持 20,000 个已连接用户，一个持久聊天服务器池可具有最多 4 个活动服务器，以便总共 80,000 个同时连接的用户使用。</span><span class="sxs-lookup"><span data-stu-id="590d4-p110">How many users will require access to Persistent Chat Server? Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users. A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>
    
- <span data-ttu-id="590d4-p111">您希望如何控制范围、信息隔离边界和访问？您可以定义 类别 来分隔这些边界，并选择可进入在每种类别中创建的聊天室的用户。</span><span class="sxs-lookup"><span data-stu-id="590d4-p111">How do you want to control scopes, ethical boundaries, and access? You can define categories to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>
    
- <span data-ttu-id="590d4-156">您希望如何控制可以创建聊天室的人员？</span><span class="sxs-lookup"><span data-stu-id="590d4-156">How do you want to control who can create rooms?</span></span> <span data-ttu-id="590d4-157">您可以定义能够创建聊天室的创建者。</span><span class="sxs-lookup"><span data-stu-id="590d4-157">You can define creators who can create rooms.</span></span> <span data-ttu-id="590d4-158">创建者可以将其他成员指定为聊天室管理者以对聊天室进行持续管理。</span><span class="sxs-lookup"><span data-stu-id="590d4-158">Creators can assign other members as chat room managers for ongoing management of the rooms.</span></span>
    
- <span data-ttu-id="590d4-159">您希望如何创建聊天室？</span><span class="sxs-lookup"><span data-stu-id="590d4-159">How do you want to create rooms?</span></span> <span data-ttu-id="590d4-160">持久的聊天服务器提供了一种基于 web 的功能用于创建和管理文件室。</span><span class="sxs-lookup"><span data-stu-id="590d4-160">Persistent Chat Server provides a web-based feature for creating and managing rooms.</span></span> <span data-ttu-id="590d4-161">这可以从 Skype 业务客户端启动。</span><span class="sxs-lookup"><span data-stu-id="590d4-161">This can be launched from the Skype for Business client.</span></span> <span data-ttu-id="590d4-162">您可以选择定义的客户解决方案，实现您的业务需求和工作流，并将持续聊天服务器配置为将用户定向到您的自定义解决方案。</span><span class="sxs-lookup"><span data-stu-id="590d4-162">You can choose to define a customer solution that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>
    
- <span data-ttu-id="590d4-163">您希望设置哪一类外接程序？</span><span class="sxs-lookup"><span data-stu-id="590d4-163">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="590d4-164">外接程序将利用 Skype for Business 客户端中的可扩展性窗格来提供与聊天室相关的上下文，从而改进聊天室内体验。</span><span class="sxs-lookup"><span data-stu-id="590d4-164">Add-ins enhance the in-room experience by leveraging the extensibility pane in the Skype for Business client to provide context that is relevant to the room.</span></span> <span data-ttu-id="590d4-165">您可以选择可能最有用的常规外接程序（例如，您的公司网站、内部协作文档等）。</span><span class="sxs-lookup"><span data-stu-id="590d4-165">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="590d4-166">聊天室管理员可选择某个注册的外接程序并将该外接程序与其聊天室关联（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="590d4-166">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span> 
    
- <span data-ttu-id="590d4-167">您具有哪一类高可用性和灾难恢复要求？</span><span class="sxs-lookup"><span data-stu-id="590d4-167">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="590d4-168">持久的聊天服务器支持 SQL Server 镜像和高可用性群集 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="590d4-168">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability.</span></span> <span data-ttu-id="590d4-169">对于灾难恢复，持久聊天服务器支持多达 8 台服务器 （4 活动和 4 待机） 池中拉伸与 SQL Server 日志传送。</span><span class="sxs-lookup"><span data-stu-id="590d4-169">For disaster recovery, Persistent Chat Server supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping.</span></span> 
    
- <span data-ttu-id="590d4-170">是否存在法规要求？</span><span class="sxs-lookup"><span data-stu-id="590d4-170">Are there regulatory requirements?</span></span> <span data-ttu-id="590d4-171">如果您的公司是一个国家或地区需要保留在国家内的数据，您可能需要将持续聊天服务器的多个池，每个本地部署到特定的地理位置。</span><span class="sxs-lookup"><span data-stu-id="590d4-171">If your company is in a country or region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="590d4-172">房间、 类别或外接程序不跨越池-它属于一个持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="590d4-172">A room, category, or add-in does not span pools--it belongs to only one Persistent Chat Server pool.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="590d4-173">拥有持久聊天服务器的多个池不授予用户 （您仍可以只有 80000 并发用户跨您的所有持久聊天服务器池） 更大的规模。</span><span class="sxs-lookup"><span data-stu-id="590d4-173">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrent users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="590d4-174">支持多个持久性聊天服务器池的主要原因是支持方面的顾虑。</span><span class="sxs-lookup"><span data-stu-id="590d4-174">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="590d4-175">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="590d4-175">For more information</span></span>

<span data-ttu-id="590d4-176">有关安装和配置持久聊天服务器的详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="590d4-176">For more information about installing and configuring Persistent Chat Server, see the following topics:</span></span>
  
- <span data-ttu-id="590d4-177">有关如何部署持续聊天服务器的详细信息，请参阅[部署持续聊天中的服务器业务服务器 2015年的 Skype](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="590d4-177">For details about how to deploy Persistent Chat Server, see [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md).</span></span> 
    
- <span data-ttu-id="590d4-178">有关如何配置上持久聊天服务器的部署设置的详细信息，请参阅[管理持久聊天中的服务器业务服务器 2015年的 Skype](../../manage/persistent-chat/persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="590d4-178">For details about how to configure settings on your Persistent Chat Server deployment, see [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
    

