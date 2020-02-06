---
title: 规划 Skype for Business Server 2015 中的持久聊天服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9e652487-a123-40c0-ae61-47fb8ecc4a20
description: 摘要：阅读本主题，了解如何在 Skype for business Server 2015 中规划持久聊天服务器。
ms.openlocfilehash: f2adc5bc9ed23f4ca02843e8c6136c44fca92d6d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815730"
---
# <a name="plan-for-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="becb7-103">规划 Skype for Business Server 2015 中的持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="becb7-103">Plan for Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="becb7-104">**摘要：** 阅读本主题，了解如何在 Skype for Business Server 2015 中规划持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="becb7-104">**Summary:** Read this topic to learn how to plan for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="becb7-105">持久聊天服务器是一种可选角色，允许组织中的多个用户参与不断保持的聊天室对话。</span><span class="sxs-lookup"><span data-stu-id="becb7-105">Persistent Chat Server is an optional role that lets multiple users in your organization participate in chat room conversations that persist over time.</span></span> <span data-ttu-id="becb7-106">尽管用户可以在聊天会话期间实时通信，每个会话的内容 - 包括文本、链接和文件 - 将持久存在，这意味着用户可以随时查看和搜索所有会话内容。</span><span class="sxs-lookup"><span data-stu-id="becb7-106">Although users can communicate in real time during a chat session, the content of each session--including text, links, and files--is persistent, which means users can view and search all content of the session at any time.</span></span>
  
<span data-ttu-id="becb7-107">持久聊天服务器可以通过以下方式帮助改善组织内的通信：</span><span class="sxs-lookup"><span data-stu-id="becb7-107">Persistent Chat Server can help improve communication within your organization by:</span></span>
  
- <span data-ttu-id="becb7-108">扩大组织内的信息意识和参与度</span><span class="sxs-lookup"><span data-stu-id="becb7-108">Broadening information awareness and participation throughout the organization</span></span>
    
- <span data-ttu-id="becb7-109">支持高效的信息共享</span><span class="sxs-lookup"><span data-stu-id="becb7-109">Enabling efficient information sharing</span></span> 
    
- <span data-ttu-id="becb7-110">改善团队间的通信，包括分散在不同地理位置的跨部门团队</span><span class="sxs-lookup"><span data-stu-id="becb7-110">Improving communication between teams, including geographically dispersed and cross-functional teams</span></span>
    
- <span data-ttu-id="becb7-111">减少信息过载</span><span class="sxs-lookup"><span data-stu-id="becb7-111">Reducing information overload</span></span>
    
- <span data-ttu-id="becb7-112">通过有选择地部署持久聊天合规性服务来遵守合规性法规</span><span class="sxs-lookup"><span data-stu-id="becb7-112">Following compliance regulations by optionally deploying the Persistent Chat Compliance service</span></span>

> [!NOTE] 
> <span data-ttu-id="becb7-113">Skype for business Server 2015 中提供了持久聊天，但 Skype for business Server 2019 不再支持此功能。</span><span class="sxs-lookup"><span data-stu-id="becb7-113">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="becb7-114">团队中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="becb7-114">The same functionality is available in Teams.</span></span> <span data-ttu-id="becb7-115">有关详细信息，请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。</span><span class="sxs-lookup"><span data-stu-id="becb7-115">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="becb7-116">如果需要使用持久聊天，您可以选择将需要此功能的用户迁移到团队，或继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="becb7-116">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
    
## <a name="persistent-chat-server-high-level-architecture"></a><span data-ttu-id="becb7-117">持久聊天服务器高级体系结构</span><span class="sxs-lookup"><span data-stu-id="becb7-117">Persistent Chat Server high-level architecture</span></span>

<span data-ttu-id="becb7-118">下图显示了持久聊天服务器体系结构的高级视图。</span><span class="sxs-lookup"><span data-stu-id="becb7-118">The following diagram shows a high-level view of the Persistent Chat Server architecture.</span></span> 
  
![持久聊天服务器高级体系结构](../../media/0344f6e2-0c6d-4391-b4b3-ec31062b1576.png)
  
<span data-ttu-id="becb7-120">持久聊天包含前端服务器角色（提供持久聊天服务）以及后端 SQL 数据库组件。</span><span class="sxs-lookup"><span data-stu-id="becb7-120">Persistent Chat consists of a front-end server role that provides the Persistent Chat services as well as a back-end SQL database component.</span></span> <span data-ttu-id="becb7-121">前端和后端组件都包含在专门的持久聊天池中。</span><span class="sxs-lookup"><span data-stu-id="becb7-121">Both front-end and back-end components are included in a dedicated Persistent Chat pool.</span></span> <span data-ttu-id="becb7-122">托管持久聊天服务器的每台计算机都必须具有访问现有 Skype for Business Server 2015 拓扑的权限。</span><span class="sxs-lookup"><span data-stu-id="becb7-122">Each computer that hosts Persistent Chat Server must have access to an existing Skype for Business Server 2015 topology.</span></span> <span data-ttu-id="becb7-123">在此图中，有一个持久聊天服务器池（A），它依赖于 Skype for business 服务器池 A 来向其发送消息。</span><span class="sxs-lookup"><span data-stu-id="becb7-123">In this diagram, there is one Persistent Chat Server pool (A), which is dependent on Skype for Business Server Pool A for routing messages to it.</span></span>
  
<span data-ttu-id="becb7-124">你可以部署一个或多个持久聊天服务器池，每个池最多可以支持最多四个活动的80K 并发用户。</span><span class="sxs-lookup"><span data-stu-id="becb7-124">You can deploy one or more Persistent Chat Server pools, each with up to four active Persistent Chat Servers supporting up to 80K concurrent users.</span></span>
  
<span data-ttu-id="becb7-125">Skype for Business Server 2015 通过用于注册的会话初始协议（SIP）和通过 SIP 协议（XCCOS）进行的 "可扩展聊天通信" 与持久聊天服务进行通信，进行聊天。</span><span class="sxs-lookup"><span data-stu-id="becb7-125">Skype for Business Server 2015 communicates with the Persistent Chat service using the Session Initiation Protocol (SIP) for registration and the Extensible Chat Communication Over SIP protocol (XCCOS) for chat.</span></span> 
  
## <a name="persistent-chat-services"></a><span data-ttu-id="becb7-126">持久聊天服务</span><span class="sxs-lookup"><span data-stu-id="becb7-126">Persistent Chat services</span></span>

<span data-ttu-id="becb7-127">下图显示了持久聊天服务器前端服务，以及这些服务如何与后端数据库组件进行通信。</span><span class="sxs-lookup"><span data-stu-id="becb7-127">The following diagram shows the Persistent Chat Server front-end services, and how these services communicate with the back-end database components.</span></span> <span data-ttu-id="becb7-128">前端组件包括持久聊天服务和合规性服务。</span><span class="sxs-lookup"><span data-stu-id="becb7-128">The front-end components include the Persistent Chat services and the Compliance service.</span></span> <span data-ttu-id="becb7-129">后端组件包括持久聊天存储和持久聊天合规性存储。</span><span class="sxs-lookup"><span data-stu-id="becb7-129">The back-end components include the Persistent Chat store and the Persistent Chat compliance store.</span></span>
  
![持久聊天服务器高级服务](../../media/bcdbadbe-e868-4a46-8a73-36562648fdf7.png)
  
### <a name="chat-service"></a><span data-ttu-id="becb7-131">聊天服务</span><span class="sxs-lookup"><span data-stu-id="becb7-131">Chat service</span></span>

<span data-ttu-id="becb7-132">聊天服务（也称作通道服务）是用于持久聊天服务器的核心服务。</span><span class="sxs-lookup"><span data-stu-id="becb7-132">The Chat service, also called the Channel service, is the core service responsible for Persistent Chat Server.</span></span> <span data-ttu-id="becb7-133">聊天服务提供了以下功能：</span><span class="sxs-lookup"><span data-stu-id="becb7-133">The Chat service provides the following functions:</span></span>
  
- <span data-ttu-id="becb7-134">接受传入消息</span><span class="sxs-lookup"><span data-stu-id="becb7-134">Accepts incoming messages</span></span>
    
- <span data-ttu-id="becb7-135">注册并列出持久聊天室内的联机参与者</span><span class="sxs-lookup"><span data-stu-id="becb7-135">Registers and lists online participants within a Persistent Chat room</span></span>
    
- <span data-ttu-id="becb7-136">向其他通道订阅者重新传输消息</span><span class="sxs-lookup"><span data-stu-id="becb7-136">Retransmits messages to other channel subscribers</span></span>
    
- <span data-ttu-id="becb7-137">实现通道管理、聊天室邀请、搜索和新内容通知的逻辑</span><span class="sxs-lookup"><span data-stu-id="becb7-137">Implements logic for channel management, chat room invitations, search and new content notifications</span></span>
    
<span data-ttu-id="becb7-138">持久聊天服务使用持久聊天存储来存储和访问聊天室内容和其他系统元数据（授权规则等）。</span><span class="sxs-lookup"><span data-stu-id="becb7-138">The Persistent Chat service stores and accesses chat room content and other system metadata (authorization rules and so on) by using the Persistent Chat store.</span></span> <span data-ttu-id="becb7-139">此服务将上载到聊天室中的文件存储到持久聊天文件存储中。</span><span class="sxs-lookup"><span data-stu-id="becb7-139">The service stores files that are uploaded into chat rooms in the Persistent Chat file store.</span></span>
  
### <a name="compliance-service"></a><span data-ttu-id="becb7-140">合规性服务</span><span class="sxs-lookup"><span data-stu-id="becb7-140">Compliance service</span></span>

<span data-ttu-id="becb7-141">如果您的组织规定必须存档持久聊天活动，您可以部署可选的持久聊天合规性服务。</span><span class="sxs-lookup"><span data-stu-id="becb7-141">If your organization has regulations that require Persistent Chat activity to be archived, you can deploy the optional Persistent Chat Compliance service.</span></span> <span data-ttu-id="becb7-142">合规性服务用于将聊天内容和事件（比如加入和离开聊天室）存档到持久聊天合规性文件存储中。</span><span class="sxs-lookup"><span data-stu-id="becb7-142">The Compliance service is responsible for archiving chat content and events, such as joining and leaving rooms, to the Persistent Chat Compliance file store.</span></span> <span data-ttu-id="becb7-143">合规性服务安装在持久聊天池中的每个持久聊天服务器上。</span><span class="sxs-lookup"><span data-stu-id="becb7-143">The Compliance service is installed on each Persistent Chat Server in a Persistent Chat pool.</span></span> 
  
### <a name="web-services"></a><span data-ttu-id="becb7-144">Web 服务</span><span class="sxs-lookup"><span data-stu-id="becb7-144">Web services</span></span>

<span data-ttu-id="becb7-145">在 Skype for business 前端服务器上运行持久聊天 web 服务。</span><span class="sxs-lookup"><span data-stu-id="becb7-145">The Persistent Chat web services run on the Skype for Business Front End Servers.</span></span> <span data-ttu-id="becb7-146">Web 服务依赖于 Internet 信息服务 (IIS)，其被实施为 Web 组件：</span><span class="sxs-lookup"><span data-stu-id="becb7-146">The web services depend on Internet Information Services (IIS), and are implemented as web components:</span></span>
  
- <span data-ttu-id="becb7-147">用于文件上载和下载的持久聊天 Web 服务   负责在聊天室中发布和检索文件。</span><span class="sxs-lookup"><span data-stu-id="becb7-147">Persistent Chat web services for file upload and download are responsible for posting and retrieving files from chat rooms.</span></span>
    
- <span data-ttu-id="becb7-148">用于聊天室管理的持久聊天 Web 服务负责为用户提供管理其聊天室和创建新聊天室的能力。</span><span class="sxs-lookup"><span data-stu-id="becb7-148">Persistent Chat web services for chat room management are responsible for providing users the ability to manage their chat rooms, and create new chat rooms.</span></span>
    
## <a name="defining-requirements-for-your-organization"></a><span data-ttu-id="becb7-149">为您的组织定义要求</span><span class="sxs-lookup"><span data-stu-id="becb7-149">Defining requirements for your organization</span></span>

<span data-ttu-id="becb7-150">如果你决定部署持久聊天服务器，你需要确定你的组织的业务需求，然后定义拓扑、基础结构和技术要求以支持你的业务需求。</span><span class="sxs-lookup"><span data-stu-id="becb7-150">If you decide to deploy Persistent Chat Server, you'll need to determine your organization's business requirements, then define the topology, infrastructure, and technical requirements to support your business needs.</span></span> <span data-ttu-id="becb7-151">若要优化部署，你需要回答以下问题：</span><span class="sxs-lookup"><span data-stu-id="becb7-151">To optimize your deployment, you'll need to answer the following questions:</span></span>
  
- <span data-ttu-id="becb7-152">是从早期版本的组聊天服务器还是以前版本的持久聊天服务器迁移还是首次部署持久聊天服务器？</span><span class="sxs-lookup"><span data-stu-id="becb7-152">Are you migrating from a previous version of Group Chat Server, or a previous version of Persistent Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>
    
- <span data-ttu-id="becb7-p110">谁可以使用持久聊天服务器？您指定持久聊天策略以在全局、站点或用户级别确定用户访问权限。</span><span class="sxs-lookup"><span data-stu-id="becb7-p110">Who can use Persistent Chat Server? You specify Persistent Chat policies to determine user access at the global, site, or user level.</span></span>
    
- <span data-ttu-id="becb7-p111">多少用户将要求访问持久聊天服务器？持久聊天服务器支持 150,000 个已设置用户（由策略启用）以及最多 80,000 个并发用户。一个持久聊天服务器可支持 20,000 个已连接用户，一个持久聊天服务器池可具有最多 4 个活动服务器，以便总共 80,000 个同时连接的用户使用。</span><span class="sxs-lookup"><span data-stu-id="becb7-p111">How many users will require access to Persistent Chat Server? Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users. A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>
    
- <span data-ttu-id="becb7-p112">您希望如何控制范围、信息隔离边界和访问？您可以定义 类别 来分隔这些边界，并选择可进入在每种类别中创建的聊天室的用户。</span><span class="sxs-lookup"><span data-stu-id="becb7-p112">How do you want to control scopes, ethical boundaries, and access? You can define categories to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>
    
- <span data-ttu-id="becb7-160">您希望如何控制可以创建聊天室的人员？</span><span class="sxs-lookup"><span data-stu-id="becb7-160">How do you want to control who can create rooms?</span></span> <span data-ttu-id="becb7-161">您可以定义能够创建聊天室的创建者。</span><span class="sxs-lookup"><span data-stu-id="becb7-161">You can define creators who can create rooms.</span></span> <span data-ttu-id="becb7-162">创建者可以将其他成员指定为聊天室管理者以对聊天室进行持续管理。</span><span class="sxs-lookup"><span data-stu-id="becb7-162">Creators can assign other members as chat room managers for ongoing management of the rooms.</span></span>
    
- <span data-ttu-id="becb7-163">您希望如何创建聊天室？</span><span class="sxs-lookup"><span data-stu-id="becb7-163">How do you want to create rooms?</span></span> <span data-ttu-id="becb7-164">持久聊天服务器提供用于创建和管理会议室的基于 web 的功能。</span><span class="sxs-lookup"><span data-stu-id="becb7-164">Persistent Chat Server provides a web-based feature for creating and managing rooms.</span></span> <span data-ttu-id="becb7-165">这可以从 Skype for Business 客户端启动。</span><span class="sxs-lookup"><span data-stu-id="becb7-165">This can be launched from the Skype for Business client.</span></span> <span data-ttu-id="becb7-166">你可以选择定义实现你的业务需求和工作流的客户解决方案，并配置持久聊天服务器以将用户引导到你的自定义解决方案。</span><span class="sxs-lookup"><span data-stu-id="becb7-166">You can choose to define a customer solution that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>
    
- <span data-ttu-id="becb7-167">您希望设置哪一类外接程序？</span><span class="sxs-lookup"><span data-stu-id="becb7-167">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="becb7-168">外接程序将利用 Skype for Business 客户端中的可扩展性窗格来提供与聊天室相关的上下文，从而改进聊天室内体验。</span><span class="sxs-lookup"><span data-stu-id="becb7-168">Add-ins enhance the in-room experience by leveraging the extensibility pane in the Skype for Business client to provide context that is relevant to the room.</span></span> <span data-ttu-id="becb7-169">您可以选择可能最有用的常规外接程序（例如，您的公司网站、内部协作文档等）。</span><span class="sxs-lookup"><span data-stu-id="becb7-169">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="becb7-170">聊天室管理员可选择某个注册的外接程序并将该外接程序与其聊天室关联（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="becb7-170">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span> 
    
- <span data-ttu-id="becb7-171">您具有哪一类高可用性和灾难恢复要求？</span><span class="sxs-lookup"><span data-stu-id="becb7-171">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="becb7-172">持久聊天服务器支持 SQL Server 镜像和 SQL Server 群集以实现高可用性。</span><span class="sxs-lookup"><span data-stu-id="becb7-172">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability.</span></span> <span data-ttu-id="becb7-173">对于灾难恢复，持久聊天服务器在带有 SQL Server 日志传送的延伸池中支持最多8台服务器（4主动和4备用）。</span><span class="sxs-lookup"><span data-stu-id="becb7-173">For disaster recovery, Persistent Chat Server supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping.</span></span> 
    
- <span data-ttu-id="becb7-174">是否存在法规要求？</span><span class="sxs-lookup"><span data-stu-id="becb7-174">Are there regulatory requirements?</span></span> <span data-ttu-id="becb7-175">如果您的公司所在的国家或地区需要在国家/地区保留数据，则您可能需要将多个持久聊天服务器池部署到特定地理位置。</span><span class="sxs-lookup"><span data-stu-id="becb7-175">If your company is in a country or region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="becb7-176">房间、类别或加载项不会跨越池，它仅属于一个持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="becb7-176">A room, category, or add-in does not span pools--it belongs to only one Persistent Chat Server pool.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="becb7-177">具有多个持久聊天服务器池不会为你提供更多规模（你只能在所有持久聊天服务器池中使用80000并发用户）。</span><span class="sxs-lookup"><span data-stu-id="becb7-177">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrent users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="becb7-178">支持多个持久聊天服务器池的主要原因是支持法规问题。</span><span class="sxs-lookup"><span data-stu-id="becb7-178">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span> 
  
## <a name="for-more-information"></a><span data-ttu-id="becb7-179">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="becb7-179">For more information</span></span>

<span data-ttu-id="becb7-180">有关安装和配置持久聊天服务器的详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="becb7-180">For more information about installing and configuring Persistent Chat Server, see the following topics:</span></span>
  
- <span data-ttu-id="becb7-181">有关如何部署持久聊天服务器的详细信息，请参阅[在 Skype For Business server 2015 中部署持久聊天服务器](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)。</span><span class="sxs-lookup"><span data-stu-id="becb7-181">For details about how to deploy Persistent Chat Server, see [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md).</span></span> 
    
- <span data-ttu-id="becb7-182">有关如何在持久聊天服务器部署上配置设置的详细信息，请参阅[在 Skype For Business server 2015 中管理持久聊天服务器](../../manage/persistent-chat/persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="becb7-182">For details about how to configure settings on your Persistent Chat Server deployment, see [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
    

