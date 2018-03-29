---
title: 持久聊天配置
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3f2891e6-bad3-4a23-a345-b7de4cae3bd9
description: 持久的聊天服务器的部署可以承载许多并发永久聊天房间。 聊天室可以组织到服务器上的一组类别中。 每个聊天室属于一个类别，并继承该类别的一些设置。 这种组织方式可创建一种非常有用的结构以基于对话的业务目的识别对话，并有助于委托管理和简化控制。
ms.openlocfilehash: c4408ebd4417d2cf825620837da018ef30f725c9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-configuration"></a><span data-ttu-id="80499-106">持久聊天配置</span><span class="sxs-lookup"><span data-stu-id="80499-106">Persistent Chat Configuration</span></span>
 
<span data-ttu-id="80499-107">持久的聊天服务器的部署可以承载许多并发永久聊天房间。</span><span class="sxs-lookup"><span data-stu-id="80499-107">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="80499-108">聊天室可以组织到服务器上的一组类别中。</span><span class="sxs-lookup"><span data-stu-id="80499-108">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="80499-109">每个聊天室属于一个类别，并继承该类别的一些设置。</span><span class="sxs-lookup"><span data-stu-id="80499-109">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="80499-110">这种组织方式可创建一种非常有用的结构以基于对话的业务目的识别对话，并有助于委托管理和简化控制。</span><span class="sxs-lookup"><span data-stu-id="80499-110">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>
  
> [!NOTE]
> <span data-ttu-id="80499-111">尽管许多聊天室的管理功能都可以在计算机中运行用户持久交谈，（在**cspersistentchatadministrator**的角色） 的持久聊天管理员必须使用控件面板或管理外壳若要创建或管理类别的 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="80499-111">Although many of the management features of chat rooms are available in computers running Persistent Chat for the user, Persistent Chat Administrators (in the **cspersistentchatadministrator** role) must use either the control panel or management shell cmdlets to create or manage categories.</span></span>
  
<span data-ttu-id="80499-112">持续聊天管理员为其组织中的用户使用 Skype 业务服务器的控制面板或 Windows PowerShell cmdlet 来创建和管理类别，并为设计访问聊天室。</span><span class="sxs-lookup"><span data-stu-id="80499-112">Persistent Chat Administrators use Skype for Business Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>
  
<span data-ttu-id="80499-113">持久的研讨室经理，已经能够管理一个或多个聊天室，可以使用客户端启动一个文件室管理 Web 应用程序创建和管理文件室 （或客户可以创建自定义的解决方案和工作流调用）。</span><span class="sxs-lookup"><span data-stu-id="80499-113">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> <span data-ttu-id="80499-114">持久聊天</span><span class="sxs-lookup"><span data-stu-id="80499-114">Persistent Chat</span></span>
  
<span data-ttu-id="80499-115">持久聊天管理员还可以使用控制面板或 Windows PowerShell cmdlet 创建和管理文件室。</span><span class="sxs-lookup"><span data-stu-id="80499-115">Persistent Chat administrators can also use control panel or Windows PowerShell cmdlets to create and manage rooms.</span></span>
  
<span data-ttu-id="80499-p104">除了更改聊天室类别之外，聊天室管理员还可以更改所有聊天室属性。不能限制其执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="80499-p104">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>
  
- <span data-ttu-id="80499-118">禁用聊天室</span><span class="sxs-lookup"><span data-stu-id="80499-118">Disabling a chat room</span></span>
    
- <span data-ttu-id="80499-119">更改聊天室名称</span><span class="sxs-lookup"><span data-stu-id="80499-119">Changing a chat room name</span></span>
    
- <span data-ttu-id="80499-120">更改聊天室说明</span><span class="sxs-lookup"><span data-stu-id="80499-120">Changing a chat room description</span></span>
    
- <span data-ttu-id="80499-121">更改聊天室类型（大会堂还是普通）</span><span class="sxs-lookup"><span data-stu-id="80499-121">Changing a chat room type (Auditorium versus Normal)</span></span>
    
- <span data-ttu-id="80499-122">更改聊天室隐私（开放、关闭还是秘密）</span><span class="sxs-lookup"><span data-stu-id="80499-122">Changing the privacy of a room (open versus closed versus secret)</span></span>
    
- <span data-ttu-id="80499-123">添加或删除成员</span><span class="sxs-lookup"><span data-stu-id="80499-123">Adding or removing members</span></span>
    
- <span data-ttu-id="80499-124">添加或删除聊天室管理者</span><span class="sxs-lookup"><span data-stu-id="80499-124">Adding or removing chat room managers</span></span>
    
- <span data-ttu-id="80499-125">添加或删除加载项</span><span class="sxs-lookup"><span data-stu-id="80499-125">Adding or removing an add-in</span></span>
    
- <span data-ttu-id="80499-126">更改设置，例如邀请 （根据什么允许按类别）</span><span class="sxs-lookup"><span data-stu-id="80499-126">Changing settings such as invitations (according to what's permitted by the category)</span></span>
    
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="80499-127">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="80499-127">Tasks that you can perform</span></span>

<span data-ttu-id="80499-128">可以对**聊天的持久性配置**页执行以下任务： 在全局范围内或针对一个特定的池配置持久聊天服务器选项。</span><span class="sxs-lookup"><span data-stu-id="80499-128">You can perform the following tasks on the **Persistent Chat Configuration** page: configure Persistent Chat Server options globally or for a specific pool.</span></span>
  
## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="80499-129">全局配置持久聊天选项</span><span class="sxs-lookup"><span data-stu-id="80499-129">To configure Persistent Chat options globally</span></span>

1. <span data-ttu-id="80499-130">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="80499-130">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="80499-131">从**开始**菜单中，选择 Skype 业务服务器的控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="80499-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="80499-132">在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天配置**”。</span><span class="sxs-lookup"><span data-stu-id="80499-132">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="80499-133">在**聊天的持久性配置**页上，单击**新建**，然后单击**站点配置**。</span><span class="sxs-lookup"><span data-stu-id="80499-133">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="80499-134">如果您想要应用于网站中部署的所有持久聊天服务器池的配置，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="80499-134">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="80499-135">如果您想要应用于一个特定的持久性聊天服务器池的配置，请单击**池配置**。</span><span class="sxs-lookup"><span data-stu-id="80499-135">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="80499-136">在**选择网站**选择要持久聊天服务器站点配置为进行配置的站点。</span><span class="sxs-lookup"><span data-stu-id="80499-136">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="80499-137">在“**新建持久聊天配置**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="80499-137">In **New Persistent Chat Configuration**, do the following:</span></span>
    
  - <span data-ttu-id="80499-p106">在“**名称**”中，指定新配置设置的名称。默认情况下，已存在站点名称。</span><span class="sxs-lookup"><span data-stu-id="80499-p106">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
  - <span data-ttu-id="80499-p107">在“**默认聊天历史记录**”中，定义首次请求时每个聊天室要处理的聊天消息的数目。默认情况下，此数目为 30。这是全局默认值，管理员可根据每个类别禁用聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="80499-p107">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="80499-143">持久的聊天服务器将缓存在内存中，这些消息以便增加此数字，如果将缓存更多的消息。</span><span class="sxs-lookup"><span data-stu-id="80499-143">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="80499-144">您始终可通过搜索来访问历史内容。</span><span class="sxs-lookup"><span data-stu-id="80499-144">You can always access historical content by search.</span></span> <span data-ttu-id="80499-145">默认数目只确定您在连接到聊天室时最初看到的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="80499-145">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
  - <span data-ttu-id="80499-p109">在“**最大文件大小(KB)**”中，选择每条聊天历史记录的最大文件大小。默认情况下，此数目为 20 MB (20,000 KB)。这是可以上载到系统（已通过对应的“**类别**”设置为其启用文件上载）中任意聊天室的文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="80499-p109">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
  - <span data-ttu-id="80499-149">在“**参与者更新限制**”中，选择对参与者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="80499-149">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="80499-150">已连接的用户数达到此数量之前，持久的聊天服务器发送给所有参与者名单信息 （连接到一个聊天房间）。</span><span class="sxs-lookup"><span data-stu-id="80499-150">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="80499-151">默认情况下，此数目为 75。</span><span class="sxs-lookup"><span data-stu-id="80499-151">By default, the number is 75.</span></span> <span data-ttu-id="80499-152">该限制指示给定文件室之外持续聊天服务器停止将名单更新发送到连接的客户端，有关谁将出现在文件室中参与者的最大数目。</span><span class="sxs-lookup"><span data-stu-id="80499-152">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
  - <span data-ttu-id="80499-153">（可选）。在**文件室管理 URL**，选择文件室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="80499-153">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="80499-154">这是基于 Web 的自定义聊天室管理的 URL。</span><span class="sxs-lookup"><span data-stu-id="80499-154">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="80499-155">如果您不需要自定义文件室管理，并且只需使用默认设置，请将此选项留空。</span><span class="sxs-lookup"><span data-stu-id="80499-155">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="80499-156">在设置该 URL 后，它将应用为内部和外部聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="80499-156">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
    <span data-ttu-id="80499-157">如果您想自定义您的空间的创建经验，包括您的特定业务流程，可以生成一个自定义文件室管理解决方案通过持久聊天服务器软件开发工具包 (SDK)、 承载到某处，并在此处输入 URL。</span><span class="sxs-lookup"><span data-stu-id="80499-157">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="80499-158">此 URL 将被发送给客户端，以便用户在尝试查看或创建聊天室时将被定向到您的自定义聊天室管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="80499-158">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="80499-159">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="80499-159">Click **Commit**.</span></span>
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="80499-160">若要配置特定的持久性聊天服务器池的持久聊天选项</span><span class="sxs-lookup"><span data-stu-id="80499-160">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1. <span data-ttu-id="80499-161">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="80499-161">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="80499-162">从**开始**菜单中，业务服务器控制面板，选择 Skype 或打开浏览器窗口，然后再输入管理。</span><span class="sxs-lookup"><span data-stu-id="80499-162">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="80499-163">在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天配置**”。</span><span class="sxs-lookup"><span data-stu-id="80499-163">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="80499-164">在“**持久聊天配置**”页上，单击“**新建**”，然后单击“**池配置**”。</span><span class="sxs-lookup"><span data-stu-id="80499-164">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="80499-165">中**选择一个服务**，请选择与要配置持久聊天服务器池相关联的服务。</span><span class="sxs-lookup"><span data-stu-id="80499-165">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="80499-166">在“**新建持久聊天配置**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="80499-166">In **New Persistent Chat Configuration**, do the following:</span></span>
    
  - <span data-ttu-id="80499-p113">在“**名称**”中，指定新配置设置的名称。默认情况下，已存在站点池名称。</span><span class="sxs-lookup"><span data-stu-id="80499-p113">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
  - <span data-ttu-id="80499-p114">在“**默认聊天历史记录**”中，定义首次请求时每个聊天室要处理的聊天消息的数目。默认情况下，此数目为 30。这是全局默认值，管理员可根据每个类别禁用聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="80499-p114">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="80499-172">持久的聊天服务器将缓存在内存中，这些消息以便增加此数字，如果将缓存更多的消息。</span><span class="sxs-lookup"><span data-stu-id="80499-172">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="80499-173">您始终可通过搜索来访问历史内容。</span><span class="sxs-lookup"><span data-stu-id="80499-173">You can always access historical content by search.</span></span> <span data-ttu-id="80499-174">默认数目只确定您在连接到聊天室时最初看到的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="80499-174">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
  - <span data-ttu-id="80499-p116">在“**最大文件大小(KB)**”中，选择每条聊天历史记录的最大文件大小。默认情况下，此数目为 20 MB (20,000 KB)。这是可以上载到系统（已通过对应的“**类别**”设置为其启用文件上载）中任意聊天室的文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="80499-p116">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
  - <span data-ttu-id="80499-178">在“**参与者更新限制**”中，选择对参与者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="80499-178">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="80499-179">已连接的用户数达到此数量之前，持久的聊天服务器发送给所有参与者名单信息 （连接到一个聊天房间）。</span><span class="sxs-lookup"><span data-stu-id="80499-179">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="80499-180">默认情况下，此数目为 75。</span><span class="sxs-lookup"><span data-stu-id="80499-180">By default, the number is 75.</span></span> <span data-ttu-id="80499-181">该限制指示给定文件室之外持续聊天服务器停止将名单更新发送到连接的客户端，有关谁将出现在文件室中参与者的最大数目。</span><span class="sxs-lookup"><span data-stu-id="80499-181">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
  - <span data-ttu-id="80499-182">（可选）在“**聊天室管理 URL**”中，选择聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="80499-182">(Optional) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="80499-183">这是基于 Web 的聊天室管理部署的 URL。</span><span class="sxs-lookup"><span data-stu-id="80499-183">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="80499-184">如果您不需要自定义文件室管理，并且只需使用默认设置，请将此选项留空。</span><span class="sxs-lookup"><span data-stu-id="80499-184">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
    <span data-ttu-id="80499-185">如果您想自定义您的空间的创建经验，包括您的特定业务流程，可以生成一个自定义文件室管理解决方案通过持久聊天服务器软件开发工具包 (SDK)、 承载到某处，并在此处输入 URL。</span><span class="sxs-lookup"><span data-stu-id="80499-185">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="80499-186">此 URL 将被发送给客户端，以便用户在尝试查看/创建聊天室时将被定向到您的自定义聊天室管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="80499-186">This URL is sent down to the client, so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="80499-187">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="80499-187">Click **Commit**.</span></span>
    
### 

<span data-ttu-id="80499-188">有关持久聊天服务器特性和功能，详细信息请参阅[规划业务服务器 2015年的 Skype 的持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、[业务服务器 2015 Skype 在部署持续聊天服务器](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)和[管理持续聊天服务器在 Skype 业务服务器 2015年](../../manage/persistent-chat/persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="80499-188">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

