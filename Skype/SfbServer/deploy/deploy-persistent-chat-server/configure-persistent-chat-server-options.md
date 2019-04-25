---
title: 在 Skype for Business Server 2015 中配置持久聊天服务器选项
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: 摘要： 了解如何为业务服务器 2015 Skype 中配置持久聊天服务器选项在全局、 站点或池级别。
ms.openlocfilehash: fd4d9ed10c2629f714d336190e5c85b2dfe1621e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225439"
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a><span data-ttu-id="252a1-103">在 Skype for Business Server 2015 中配置持久聊天服务器选项</span><span class="sxs-lookup"><span data-stu-id="252a1-103">Configure Persistent Chat Server options in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="252a1-104">**摘要：** 了解如何为业务服务器 2015 Skype 中配置持久聊天服务器选项在全局、 站点或池级别。</span><span class="sxs-lookup"><span data-stu-id="252a1-104">**Summary:** Learn how to configure Persistent Chat Server options at the global, site, or pool level in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="252a1-105">您可以指定多个选项可在网站内的所有池或网站中特定池全局应用的持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="252a1-105">You can specify several options for Persistent Chat Server that can be applied globally, to all pools within a site, or to a specific pool within a site.</span></span> <span data-ttu-id="252a1-106">持久聊天服务器选项包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="252a1-106">Persistent Chat server options include the following:</span></span> 
  
- <span data-ttu-id="252a1-107">默认聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="252a1-107">Default Chat History.</span></span> <span data-ttu-id="252a1-108">首次请求时每个聊天室的可用聊天消息数量。</span><span class="sxs-lookup"><span data-stu-id="252a1-108">The number of chat messages that are available for each chat room upon first request.</span></span> <span data-ttu-id="252a1-109">全局默认设置为 30 条聊天消息。</span><span class="sxs-lookup"><span data-stu-id="252a1-109">The global default is 30 chat messages.</span></span> 
    
- <span data-ttu-id="252a1-p103">最大文件大小。可从聊天室上载或下载的最大文件大小。全局默认设置为 20MB。</span><span class="sxs-lookup"><span data-stu-id="252a1-p103">Maximum File Size. The maximum size of a file that can be uploaded to or downloaded from a room. The global default is 20MB.</span></span>
    
- <span data-ttu-id="252a1-113">参与者更新限制。</span><span class="sxs-lookup"><span data-stu-id="252a1-113">Participant Update Limit.</span></span> <span data-ttu-id="252a1-114">指定聊天室中持久聊天向其发送名单更新的最大参与者人数。</span><span class="sxs-lookup"><span data-stu-id="252a1-114">The maximum number of participants in a given chat room for which Persistent Chat will send roster updates.</span></span> <span data-ttu-id="252a1-115">全局默认设置为 75。</span><span class="sxs-lookup"><span data-stu-id="252a1-115">The global default is 75.</span></span>
    
- <span data-ttu-id="252a1-116">会议室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="252a1-116">Room Management URL.</span></span> <span data-ttu-id="252a1-117">用于自定义聊天室管理的 URL。</span><span class="sxs-lookup"><span data-stu-id="252a1-117">The URL used for custom chat room management.</span></span> <span data-ttu-id="252a1-118">该设置允许使用自定义聊天室管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="252a1-118">The setting allows the use of a custom room management solution.</span></span> 
   
> [!NOTE] 
> <span data-ttu-id="252a1-119">持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。</span><span class="sxs-lookup"><span data-stu-id="252a1-119">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="252a1-120">中团队提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="252a1-120">The same functionality is available in Teams.</span></span> <span data-ttu-id="252a1-121">有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。</span><span class="sxs-lookup"><span data-stu-id="252a1-121">For more information, see [Journey from Skype for Business to Microsoft Teams](/microsoftteams/journey-skypeforbusiness-teams).</span></span> <span data-ttu-id="252a1-122">如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。</span><span class="sxs-lookup"><span data-stu-id="252a1-122">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>
 
## <a name="configure-persistent-chat-server-global-options"></a><span data-ttu-id="252a1-123">配置持久聊天服务器全局选项</span><span class="sxs-lookup"><span data-stu-id="252a1-123">Configure Persistent Chat Server global options</span></span>

<span data-ttu-id="252a1-124">配置持久聊天服务器全局选项：</span><span class="sxs-lookup"><span data-stu-id="252a1-124">To configure Persistent Chat Server global options:</span></span>
  
1. <span data-ttu-id="252a1-125">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="252a1-125">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="252a1-126">从**开始**菜单上，选择业务 Server Control Panel Skype 或打开一个浏览器窗口中，，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="252a1-126">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="252a1-127">在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天配置**”。</span><span class="sxs-lookup"><span data-stu-id="252a1-127">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="252a1-128">在**持久聊天配置**页上，单击**新建**，然后单击**站点配置**。</span><span class="sxs-lookup"><span data-stu-id="252a1-128">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="252a1-129">如果您想要应用于该站点中部署的所有持久聊天服务器池的配置，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="252a1-129">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="252a1-130">如果您想要应用于特定的持久聊天服务器池的配置，请单击**池配置**。</span><span class="sxs-lookup"><span data-stu-id="252a1-130">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="252a1-131">在**选择站点**，选择要配置的站点的持久聊天服务器网站配置的站点。</span><span class="sxs-lookup"><span data-stu-id="252a1-131">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="252a1-132">在“**新建持久聊天配置**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="252a1-132">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="252a1-p108">在“**名称**”中，指定新配置设置的名称。默认情况下，已存在站点名称。</span><span class="sxs-lookup"><span data-stu-id="252a1-p108">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
   - <span data-ttu-id="252a1-p109">在“**默认聊天历史记录**”中，定义首次请求时每个聊天室要处理的聊天消息的数目。默认情况下，此数目为 30。这是全局默认值，管理员可根据每个类别禁用聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="252a1-p109">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="252a1-138">持久聊天服务器将缓存在内存中，这些消息以便更多邮件如果增加此号码，将进行缓存。</span><span class="sxs-lookup"><span data-stu-id="252a1-138">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="252a1-139">您始终可通过搜索来访问历史内容。</span><span class="sxs-lookup"><span data-stu-id="252a1-139">You can always access historical content by search.</span></span> <span data-ttu-id="252a1-140">默认数目只确定您在连接到聊天室时最初看到的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="252a1-140">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="252a1-p111">在“**最大文件大小(KB)**”中，选择每条聊天历史记录的最大文件大小。默认情况下，此数目为 20 MB (20,000 KB)。这是可以上载到系统（已通过对应的“**类别**”设置为其启用文件上载）中任意聊天室的文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="252a1-p111">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="252a1-144">在“**参与者更新限制**”中，选择对参与者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="252a1-144">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="252a1-145">持久聊天服务器向所有参与者发送名单信息 （用户连接到聊天室），直到连接的用户的数量达到此号码。</span><span class="sxs-lookup"><span data-stu-id="252a1-145">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="252a1-146">默认情况下，此数目为 75。</span><span class="sxs-lookup"><span data-stu-id="252a1-146">By default, the number is 75.</span></span> <span data-ttu-id="252a1-147">此限制指示给定聊天室超出其 Persistent Chat Server 停止向有关谁是在聊天室中存在连接的客户端发送名单更新中的参与者的最大数量。</span><span class="sxs-lookup"><span data-stu-id="252a1-147">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="252a1-148">（可选）。在**聊天室管理 URL**中，选择聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="252a1-148">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="252a1-149">这是基于 Web 的自定义聊天室管理的 URL。</span><span class="sxs-lookup"><span data-stu-id="252a1-149">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="252a1-150">如果不需要自定义聊天室管理，并且您只需使用的默认设置，请将此选项保留为空。</span><span class="sxs-lookup"><span data-stu-id="252a1-150">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="252a1-151">在设置该 URL 后，它将应用为内部和外部聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="252a1-151">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
     <span data-ttu-id="252a1-152">如果您想要自定义聊天室创建体验，并包括特定业务工作流，您可以使用持久聊天服务器软件开发工具包 (SDK) 构建的自定义聊天室管理解决方案、 某个位置，承载和在此处输入 URL。</span><span class="sxs-lookup"><span data-stu-id="252a1-152">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="252a1-153">此 URL 将被发送给客户端，以便用户在尝试查看或创建聊天室时将被定向到您的自定义聊天室管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="252a1-153">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="252a1-154">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="252a1-154">Click **Commit**.</span></span>
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="252a1-155">为特定的持久聊天服务器池配置选项</span><span class="sxs-lookup"><span data-stu-id="252a1-155">Configure options for a specific Persistent Chat Server pool</span></span>

<span data-ttu-id="252a1-156">若要为特定的持久聊天服务器池配置选项。</span><span class="sxs-lookup"><span data-stu-id="252a1-156">To configure options for a specific Persistent Chat Server pool.</span></span>
  
1. <span data-ttu-id="252a1-157">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="252a1-157">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="252a1-158">从**开始**菜单中，为业务服务器控制面板中，选择 Skype 或打开浏览器窗口，，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="252a1-158">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="252a1-159">在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天配置**”。</span><span class="sxs-lookup"><span data-stu-id="252a1-159">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="252a1-160">在“**持久聊天配置**”页上，单击“**新建**”，然后单击“**池配置**”。</span><span class="sxs-lookup"><span data-stu-id="252a1-160">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="252a1-161">在**选择服务**，选择与要配置的持久聊天服务器池关联的服务。</span><span class="sxs-lookup"><span data-stu-id="252a1-161">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="252a1-162">在“**新建持久聊天配置**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="252a1-162">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="252a1-p115">在“**名称**”中，指定新配置设置的名称。默认情况下，已存在站点池名称。</span><span class="sxs-lookup"><span data-stu-id="252a1-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
   - <span data-ttu-id="252a1-p116">在“**默认聊天历史记录**”中，定义首次请求时每个聊天室要处理的聊天消息的数目。默认情况下，此数目为 30。这是全局默认值，管理员可根据每个类别禁用聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="252a1-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="252a1-168">持久聊天服务器将缓存在内存中，这些消息以便更多邮件如果增加此号码，将进行缓存。</span><span class="sxs-lookup"><span data-stu-id="252a1-168">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="252a1-169">您始终可通过搜索来访问历史内容。</span><span class="sxs-lookup"><span data-stu-id="252a1-169">You can always access historical content by search.</span></span> <span data-ttu-id="252a1-170">默认数目只确定您在连接到聊天室时最初看到的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="252a1-170">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="252a1-p118">在“**最大文件大小(KB)**”中，选择每条聊天历史记录的最大文件大小。默认情况下，此数目为 20 MB (20,000 KB)。这是可以上载到系统（已通过对应的“**类别**”设置为其启用文件上载）中任意聊天室的文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="252a1-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="252a1-174">在“**参与者更新限制**”中，选择对参与者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="252a1-174">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="252a1-175">持久聊天服务器向所有参与者发送名单信息 （用户连接到聊天室），直到连接的用户的数量达到此号码。</span><span class="sxs-lookup"><span data-stu-id="252a1-175">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="252a1-176">默认情况下，此数目为 75。</span><span class="sxs-lookup"><span data-stu-id="252a1-176">By default, the number is 75.</span></span> <span data-ttu-id="252a1-177">此限制指示给定聊天室超出其 Persistent Chat Server 停止向有关谁是在聊天室中存在连接的客户端发送名单更新中的参与者的最大数量。</span><span class="sxs-lookup"><span data-stu-id="252a1-177">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="252a1-178">在“**聊天室管理 URL**”中，选择聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="252a1-178">In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="252a1-179">这是基于 Web 的聊天室管理部署的 URL。</span><span class="sxs-lookup"><span data-stu-id="252a1-179">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="252a1-180">如果不需要自定义聊天室管理，并且您只需使用的默认设置，请将此选项保留为空。</span><span class="sxs-lookup"><span data-stu-id="252a1-180">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
     <span data-ttu-id="252a1-181">如果您想要自定义聊天室创建体验，并包括特定业务工作流，您可以使用持久聊天服务器软件开发工具包 (SDK) 构建的自定义聊天室管理解决方案、 某个位置，承载和在此处输入 URL。</span><span class="sxs-lookup"><span data-stu-id="252a1-181">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="252a1-182">此 URL 将被发送给客户端，以便用户在尝试查看/创建聊天室时将被定向到您的自定义聊天室管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="252a1-182">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="252a1-183">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="252a1-183">Click **Commit**.</span></span>
    

