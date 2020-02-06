---
title: 在 Skype for Business Server 2015 中配置持久聊天服务器选项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: 摘要：了解如何在 Skype for business Server 2015 中的全球版、网站或池级别配置持久聊天服务器选项。
ms.openlocfilehash: c842d0c0790f7aad18dda6f3f9cabe5382eb4f33
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41793560"
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a><span data-ttu-id="836ef-103">在 Skype for Business Server 2015 中配置持久聊天服务器选项</span><span class="sxs-lookup"><span data-stu-id="836ef-103">Configure Persistent Chat Server options in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="836ef-104">**摘要：** 了解如何在 Skype for business Server 2015 中的全球版、网站或池级别配置持久聊天服务器选项。</span><span class="sxs-lookup"><span data-stu-id="836ef-104">**Summary:** Learn how to configure Persistent Chat Server options at the global, site, or pool level in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="836ef-105">你可以为持久聊天服务器指定可全局应用的多个选项、网站内的所有池或网站内的特定池。</span><span class="sxs-lookup"><span data-stu-id="836ef-105">You can specify several options for Persistent Chat Server that can be applied globally, to all pools within a site, or to a specific pool within a site.</span></span> <span data-ttu-id="836ef-106">持久聊天服务器选项包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="836ef-106">Persistent Chat server options include the following:</span></span> 
  
- <span data-ttu-id="836ef-107">默认聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="836ef-107">Default Chat History.</span></span> <span data-ttu-id="836ef-108">首次请求时每个聊天室的可用聊天消息数量。</span><span class="sxs-lookup"><span data-stu-id="836ef-108">The number of chat messages that are available for each chat room upon first request.</span></span> <span data-ttu-id="836ef-109">全局默认设置为 30 条聊天消息。</span><span class="sxs-lookup"><span data-stu-id="836ef-109">The global default is 30 chat messages.</span></span> 
    
- <span data-ttu-id="836ef-p103">最大文件大小。可从聊天室上载或下载的最大文件大小。全局默认设置为 20MB。</span><span class="sxs-lookup"><span data-stu-id="836ef-p103">Maximum File Size. The maximum size of a file that can be uploaded to or downloaded from a room. The global default is 20MB.</span></span>
    
- <span data-ttu-id="836ef-113">参与者更新限制。</span><span class="sxs-lookup"><span data-stu-id="836ef-113">Participant Update Limit.</span></span> <span data-ttu-id="836ef-114">指定聊天室中持久聊天向其发送名单更新的最大参与者人数。</span><span class="sxs-lookup"><span data-stu-id="836ef-114">The maximum number of participants in a given chat room for which Persistent Chat will send roster updates.</span></span> <span data-ttu-id="836ef-115">全局默认设置为 75。</span><span class="sxs-lookup"><span data-stu-id="836ef-115">The global default is 75.</span></span>
    
- <span data-ttu-id="836ef-116">会议室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="836ef-116">Room Management URL.</span></span> <span data-ttu-id="836ef-117">用于自定义聊天室管理的 URL。</span><span class="sxs-lookup"><span data-stu-id="836ef-117">The URL used for custom chat room management.</span></span> <span data-ttu-id="836ef-118">该设置允许使用自定义聊天室管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="836ef-118">The setting allows the use of a custom room management solution.</span></span> 
   
> [!NOTE] 
> <span data-ttu-id="836ef-119">Skype for business Server 2015 中提供了持久聊天，但 Skype for business Server 2019 不再支持此功能。</span><span class="sxs-lookup"><span data-stu-id="836ef-119">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="836ef-120">团队中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="836ef-120">The same functionality is available in Teams.</span></span> <span data-ttu-id="836ef-121">有关详细信息，请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。</span><span class="sxs-lookup"><span data-stu-id="836ef-121">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="836ef-122">如果需要使用持久聊天，您可以选择将需要此功能的用户迁移到团队，或继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="836ef-122">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>
 
## <a name="configure-persistent-chat-server-global-options"></a><span data-ttu-id="836ef-123">配置持久聊天服务器全局选项</span><span class="sxs-lookup"><span data-stu-id="836ef-123">Configure Persistent Chat Server global options</span></span>

<span data-ttu-id="836ef-124">要配置持久聊天服务器全局选项，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="836ef-124">To configure Persistent Chat Server global options:</span></span>
  
1. <span data-ttu-id="836ef-125">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="836ef-125">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="836ef-126">从 "**开始**" 菜单中，选择 "Skype For business 服务器" 控制面板或打开一个浏览器窗口，然后输入管理员 URL。</span><span class="sxs-lookup"><span data-stu-id="836ef-126">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="836ef-127">在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天配置**”。</span><span class="sxs-lookup"><span data-stu-id="836ef-127">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="836ef-128">在 "**持久聊天配置**" 页面上，单击 "**新建"，** 然后单击 "**网站配置**"。</span><span class="sxs-lookup"><span data-stu-id="836ef-128">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="836ef-129">如果你希望将配置应用到网站中部署的所有持久聊天服务器池，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="836ef-129">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="836ef-130">如果要将配置应用于特定的持久聊天服务器池，请单击 "**池配置**"。</span><span class="sxs-lookup"><span data-stu-id="836ef-130">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="836ef-131">在 "**选择网站**" 中，选择要为持久聊天服务器网站配置配置的网站。</span><span class="sxs-lookup"><span data-stu-id="836ef-131">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="836ef-132">在“**新建持久聊天配置**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="836ef-132">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="836ef-p108">在“**名称**”中，指定新配置设置的名称。默认情况下，已存在站点名称。</span><span class="sxs-lookup"><span data-stu-id="836ef-p108">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
   - <span data-ttu-id="836ef-p109">在“**默认聊天历史记录**”中，定义首次请求时每个聊天室要处理的聊天消息的数目。默认情况下，此数目为 30。这是全局默认值，管理员可根据每个类别禁用聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="836ef-p109">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="836ef-138">持久聊天服务器将在内存中缓存这些消息，因此如果增加此数字，将缓存更多消息。</span><span class="sxs-lookup"><span data-stu-id="836ef-138">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="836ef-139">您始终可通过搜索来访问历史内容。</span><span class="sxs-lookup"><span data-stu-id="836ef-139">You can always access historical content by search.</span></span> <span data-ttu-id="836ef-140">默认数目只确定您在连接到聊天室时最初看到的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="836ef-140">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="836ef-p111">在“**最大文件大小(KB)**”中，选择每条聊天历史记录的最大文件大小。默认情况下，此数目为 20 MB (20,000 KB)。这是可以上载到系统（已通过对应的“**类别**”设置为其启用文件上载）中任意聊天室的文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="836ef-p111">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="836ef-144">在“**参与者更新限制**”中，选择对参与者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="836ef-144">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="836ef-145">持久聊天服务器向所有参与者发送名单信息（已连接到聊天室的用户），直到连接的用户数达到此号码。</span><span class="sxs-lookup"><span data-stu-id="836ef-145">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="836ef-146">默认情况下，此数目为 75。</span><span class="sxs-lookup"><span data-stu-id="836ef-146">By default, the number is 75.</span></span> <span data-ttu-id="836ef-147">此限制指示在指定房间内的参与者的最大数量，超过该空间后，永久聊天服务器将停止向已连接客户端发送名单更新。</span><span class="sxs-lookup"><span data-stu-id="836ef-147">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="836ef-148">（可选。）在 "**会议室管理 url**" 中，选择会议室管理 url。</span><span class="sxs-lookup"><span data-stu-id="836ef-148">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="836ef-149">这是基于 Web 的自定义聊天室管理的 URL。</span><span class="sxs-lookup"><span data-stu-id="836ef-149">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="836ef-150">如果不需要自定义聊天室管理，只需使用默认设置，请将此选项保留为空。</span><span class="sxs-lookup"><span data-stu-id="836ef-150">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="836ef-151">在设置该 URL 后，它将应用为内部和外部聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="836ef-151">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
     <span data-ttu-id="836ef-152">如果你想要自定义聊天室创建体验并包含特定的业务工作流，你可以使用持久聊天服务器软件开发工具包（SDK）构建自定义聊天室管理解决方案，并将 URL 放置在此处。</span><span class="sxs-lookup"><span data-stu-id="836ef-152">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="836ef-153">此 URL 将被发送给客户端，以便用户在尝试查看或创建聊天室时将被定向到您的自定义聊天室管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="836ef-153">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="836ef-154">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="836ef-154">Click **Commit**.</span></span>
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="836ef-155">配置特定持久聊天服务器池的选项</span><span class="sxs-lookup"><span data-stu-id="836ef-155">Configure options for a specific Persistent Chat Server pool</span></span>

<span data-ttu-id="836ef-156">配置特定持久聊天服务器池的选项。</span><span class="sxs-lookup"><span data-stu-id="836ef-156">To configure options for a specific Persistent Chat Server pool.</span></span>
  
1. <span data-ttu-id="836ef-157">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="836ef-157">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="836ef-158">从 "**开始**" 菜单中，选择 "Skype For business 服务器" 控制面板，或打开一个浏览器窗口，然后输入管理员 URL。</span><span class="sxs-lookup"><span data-stu-id="836ef-158">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="836ef-159">在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天配置**”。</span><span class="sxs-lookup"><span data-stu-id="836ef-159">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="836ef-160">在“**持久聊天配置**”页上，单击“**新建**”，然后单击“**池配置**”。</span><span class="sxs-lookup"><span data-stu-id="836ef-160">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="836ef-161">在 "**选择服务**" 中，选择与要配置的持久聊天服务器池相关联的服务。</span><span class="sxs-lookup"><span data-stu-id="836ef-161">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="836ef-162">在“**新建持久聊天配置**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="836ef-162">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="836ef-p115">在“**名称**”中，指定新配置设置的名称。默认情况下，已存在站点池名称。</span><span class="sxs-lookup"><span data-stu-id="836ef-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
   - <span data-ttu-id="836ef-p116">在“**默认聊天历史记录**”中，定义首次请求时每个聊天室要处理的聊天消息的数目。默认情况下，此数目为 30。这是全局默认值，管理员可根据每个类别禁用聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="836ef-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="836ef-168">持久聊天服务器将在内存中缓存这些消息，因此如果增加此数字，将缓存更多消息。</span><span class="sxs-lookup"><span data-stu-id="836ef-168">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="836ef-169">您始终可通过搜索来访问历史内容。</span><span class="sxs-lookup"><span data-stu-id="836ef-169">You can always access historical content by search.</span></span> <span data-ttu-id="836ef-170">默认数目只确定您在连接到聊天室时最初看到的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="836ef-170">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="836ef-p118">在“**最大文件大小(KB)**”中，选择每条聊天历史记录的最大文件大小。默认情况下，此数目为 20 MB (20,000 KB)。这是可以上载到系统（已通过对应的“**类别**”设置为其启用文件上载）中任意聊天室的文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="836ef-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="836ef-174">在“**参与者更新限制**”中，选择对参与者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="836ef-174">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="836ef-175">持久聊天服务器向所有参与者发送名单信息（已连接到聊天室的用户），直到连接的用户数达到此号码。</span><span class="sxs-lookup"><span data-stu-id="836ef-175">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="836ef-176">默认情况下，此数目为 75。</span><span class="sxs-lookup"><span data-stu-id="836ef-176">By default, the number is 75.</span></span> <span data-ttu-id="836ef-177">此限制指示在指定房间内的参与者的最大数量，超过该空间后，永久聊天服务器将停止向已连接客户端发送名单更新。</span><span class="sxs-lookup"><span data-stu-id="836ef-177">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="836ef-178">在“**聊天室管理 URL**”中，选择聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="836ef-178">In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="836ef-179">这是基于 Web 的聊天室管理部署的 URL。</span><span class="sxs-lookup"><span data-stu-id="836ef-179">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="836ef-180">如果不需要自定义聊天室管理，只需使用默认设置，请将此选项保留为空。</span><span class="sxs-lookup"><span data-stu-id="836ef-180">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
     <span data-ttu-id="836ef-181">如果你想要自定义聊天室创建体验并包含特定的业务工作流，你可以使用持久聊天服务器软件开发工具包（SDK）构建自定义聊天室管理解决方案，并将 URL 放置在此处。</span><span class="sxs-lookup"><span data-stu-id="836ef-181">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="836ef-182">此 URL 将被发送给客户端，以便用户在尝试查看/创建聊天室时将被定向到您的自定义聊天室管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="836ef-182">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="836ef-183">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="836ef-183">Click **Commit**.</span></span>
    

