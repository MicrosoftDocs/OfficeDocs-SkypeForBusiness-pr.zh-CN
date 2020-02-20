---
title: Lync Server 2013：定义持久聊天服务器的要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15beb7728525fa3e4bb6b75dfc46fb46335d1063
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154674"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="07ab9-102">定义您的组织在 Lync Server 2013 中的持久聊天服务器的要求</span><span class="sxs-lookup"><span data-stu-id="07ab9-102">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="07ab9-103">_**上次修改的主题：** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="07ab9-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="07ab9-104">在为您的组织部署持久聊天服务器之前，必须考虑以下关键问题来优化您的部署：</span><span class="sxs-lookup"><span data-stu-id="07ab9-104">Before you deploy Persistent Chat Server for your organization, it’s essential to consider the following key questions to optimize your deployment:</span></span>

  - <span data-ttu-id="07ab9-105">应为持久聊天服务器启用哪些用户（用户配置文件）？</span><span class="sxs-lookup"><span data-stu-id="07ab9-105">Who (user profile) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="07ab9-106">持久聊天服务器是由可在全局、站点、池或用户级别设置的策略启用的。</span><span class="sxs-lookup"><span data-stu-id="07ab9-106">Persistent Chat Server is enabled by a policy that can be set at a Global, Site, Pool or User level.</span></span>

  - <span data-ttu-id="07ab9-107">应为持久聊天服务器启用多少用户（扩展）？</span><span class="sxs-lookup"><span data-stu-id="07ab9-107">How many users (scale) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="07ab9-108">持久聊天服务器支持150000预配的用户（由策略启用），最多使用持久聊天服务器的并发用户数最多为80000个。</span><span class="sxs-lookup"><span data-stu-id="07ab9-108">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users using Persistent Chat Server.</span></span> <span data-ttu-id="07ab9-109">一个持久聊天服务器可支持20000个连接的用户，一个持久聊天服务器池最长可包含4个活动服务器，共80000个并行连接的用户。</span><span class="sxs-lookup"><span data-stu-id="07ab9-109">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>

  - <span data-ttu-id="07ab9-110">您是从早期版本的组聊天服务器进行迁移，还是首次部署持久聊天服务器？</span><span class="sxs-lookup"><span data-stu-id="07ab9-110">Are you migrating from a previous version of Group Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>

  - <span data-ttu-id="07ab9-111">是否有合规性要求？</span><span class="sxs-lookup"><span data-stu-id="07ab9-111">Are there compliance requirements?</span></span> <span data-ttu-id="07ab9-112">持久聊天服务器支持符合性。</span><span class="sxs-lookup"><span data-stu-id="07ab9-112">Persistent Chat Server supports compliance.</span></span> <span data-ttu-id="07ab9-113">合规性服务在持久聊天服务器前端服务器上运行并置，而不是对以前的组聊天服务器部署中的单独计算机的要求。</span><span class="sxs-lookup"><span data-stu-id="07ab9-113">The compliance service runs collocated on the Persistent Chat Server Front End Server, as opposed to the requirement for a separate computer in previous Group Chat Server deployments.</span></span> <span data-ttu-id="07ab9-114">合规性是可选的，如果选择它，则需要必须配置为存储合规性数据和事件的合规性数据库。</span><span class="sxs-lookup"><span data-stu-id="07ab9-114">Compliance is optional, and if chosen, requires a compliance database that must be configured to store compliance data and events.</span></span> <span data-ttu-id="07ab9-115">您可能需要配置适配器以获取合规性数据库中的数据，并将其转换为其他格式（如 XML 文件或 Exchange 托管存档）。</span><span class="sxs-lookup"><span data-stu-id="07ab9-115">You may want to also configure an adapter to take the data from the compliance database and convert to another format (such as XML files or Exchange-hosted archives).</span></span>

  - <span data-ttu-id="07ab9-p104">您希望如何控制范围、信息隔离边界和访问？您可以定义**类别**来分隔这些边界，并选择可进入在每种类别中创建的聊天室的用户。</span><span class="sxs-lookup"><span data-stu-id="07ab9-p104">How do you want to control scopes, ethical boundaries, and access? You can define **Categories** to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>

  - <span data-ttu-id="07ab9-p105">您希望如何控制可创建聊天室的用户？您可以配置适合您的类别的**创建者**，他们可以创建聊天室。创建者可将其他成员指定为**聊天室管理员**，以便根据按类别配置的 **AllowedMembers/DeniedMembers** 的范围对聊天室进行持续管理（添加或删除其他成员）。</span><span class="sxs-lookup"><span data-stu-id="07ab9-p105">How do you want to control who can create rooms? You can configure **Creators**, appropriate to your categories, who can create rooms. Creators can assign other members as **Chat Room Managers** for ongoing management of the rooms (adding or removing additional members), according to the scope for **AllowedMembers/DeniedMembers** configured by the category.</span></span>

  - <span data-ttu-id="07ab9-121">您希望如何创建聊天室？</span><span class="sxs-lookup"><span data-stu-id="07ab9-121">How do you want to create rooms?</span></span> <span data-ttu-id="07ab9-122">持久聊天服务器为创建和管理会议室提供了基于 web 的功能。</span><span class="sxs-lookup"><span data-stu-id="07ab9-122">Persistent Chat Server provides a web-based feature for room creation and management.</span></span> <span data-ttu-id="07ab9-123">这可以从 Lync 2013 客户端启动。</span><span class="sxs-lookup"><span data-stu-id="07ab9-123">This can be launched from the Lync 2013 client.</span></span> <span data-ttu-id="07ab9-124">您可以选择定义自定义解决方案（使用持久聊天服务器软件开发工具包（SDK））来实现您的业务需求和工作流，并将持久聊天服务器配置为将用户引导到您的自定义解决方案。</span><span class="sxs-lookup"><span data-stu-id="07ab9-124">You can choose to define a custom solution (by using the Persistent Chat Server Software Development Kit (SDK)) that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>

  - <span data-ttu-id="07ab9-125">您希望设置哪一类外接程序？</span><span class="sxs-lookup"><span data-stu-id="07ab9-125">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="07ab9-126">**外接程序**通过利用 Lync 2013 客户端中的扩展性窗格来提供与聊天室相关的上下文，增强了会议室体验。</span><span class="sxs-lookup"><span data-stu-id="07ab9-126">**Add-ins** enhance the in-room experience by leveraging the extensibility pane in the Lync 2013 client to provide context that is relevant to the room.</span></span> <span data-ttu-id="07ab9-127">您可以选择可能最有用的常规外接程序（例如，您的公司网站、内部协作文档等）。</span><span class="sxs-lookup"><span data-stu-id="07ab9-127">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="07ab9-128">聊天室管理员可选择某个注册的外接程序并将该外接程序与其聊天室关联（如果需要）。</span><span class="sxs-lookup"><span data-stu-id="07ab9-128">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span>

  - <span data-ttu-id="07ab9-129">您具有哪一类高可用性和灾难恢复要求？</span><span class="sxs-lookup"><span data-stu-id="07ab9-129">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="07ab9-130">持久聊天服务器支持 SQL Server 镜像和 SQL Server 群集功能，以实现高可用性，并支持在具有 SQL Server 日志传送的延伸池中使用最多8台服务器（4个活动和4个备用）进行灾难恢复。</span><span class="sxs-lookup"><span data-stu-id="07ab9-130">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability and supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping for disaster recovery.</span></span>

  - <span data-ttu-id="07ab9-131">是否有管理要求？</span><span class="sxs-lookup"><span data-stu-id="07ab9-131">Are there regulatory requirements?</span></span> <span data-ttu-id="07ab9-132">如果贵公司所在的国家/地区内的数据需要保留在国家/地区内，您可能需要将多个持久聊天服务器池（每个本地）部署到特定地理位置。</span><span class="sxs-lookup"><span data-stu-id="07ab9-132">If your company is in a country/region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="07ab9-133">会议室、类别或加载项不会跨越池，仅属于一个持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="07ab9-133">A room, category, or add-in does not span pools—it belongs to only one Persistent Chat Server pool.</span></span> <span data-ttu-id="07ab9-134">您可以管理每个持久聊天服务器池的一组类别、外接程序和文件室。</span><span class="sxs-lookup"><span data-stu-id="07ab9-134">You can manage the set of categories, add-ins and rooms for each Persistent Chat Server pool.</span></span> <span data-ttu-id="07ab9-135">可以将用户配置为在一个或多个池中使用类别 AllowedMembers 作用域或文件室的成员范围来访问聊天室，具体取决于您设计类别的方式。</span><span class="sxs-lookup"><span data-stu-id="07ab9-135">Users can be configured to have access to rooms in one or more pools using the category AllowedMembers scope or Room’s membership scope, depending on how you design your categories.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="07ab9-136">具有多个持久聊天服务器池不会为您提供更多的规模（您仍可以在所有持久聊天服务器池中仅有80000个并发连接的用户）。</span><span class="sxs-lookup"><span data-stu-id="07ab9-136">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrently connected users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="07ab9-137">支持多个持久聊天服务器池的主要原因是为了支持法规方面的问题。</span><span class="sxs-lookup"><span data-stu-id="07ab9-137">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

