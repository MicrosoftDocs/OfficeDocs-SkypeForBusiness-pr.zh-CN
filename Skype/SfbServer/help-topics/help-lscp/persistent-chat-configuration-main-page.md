---
title: 持久聊天配置主页
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatConfigMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e75d352-12cf-4548-9301-5d4c0e1c8f46
description: 持久聊天服务器部署可以承载许多并发持久聊天室。 聊天室可以组织到服务器上的一组类别中。 每个聊天室属于一个类别，并可从该类别继承部分设置。 这种组织方式可创建一种非常有用的结构以基于对话的业务目的识别对话，并有助于方便委托管理和简化控制。
ms.openlocfilehash: eb444869c036396ee490b38ea1b0bcd149cf29c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822062"
---
# <a name="persistent-chat-configuration-main-page"></a><span data-ttu-id="4cffe-106">持久聊天配置主页</span><span class="sxs-lookup"><span data-stu-id="4cffe-106">Persistent Chat Configuration Main Page</span></span>
 
<span data-ttu-id="4cffe-107">持久聊天服务器部署可以承载许多并发持久聊天室。</span><span class="sxs-lookup"><span data-stu-id="4cffe-107">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="4cffe-108">聊天室可以组织到服务器上的一组类别中。</span><span class="sxs-lookup"><span data-stu-id="4cffe-108">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="4cffe-109">每个聊天室属于一个类别，并可从该类别继承部分设置。</span><span class="sxs-lookup"><span data-stu-id="4cffe-109">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="4cffe-110">这种组织方式可创建一种非常有用的结构以基于对话的业务目的识别对话，并有助于方便委托管理和简化控制。</span><span class="sxs-lookup"><span data-stu-id="4cffe-110">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4cffe-111">尽管聊天室的许多管理功能在运行持久聊天的用户的计算机上可用，但 **cspersistentchatadministrator** 角色) 中的持久聊天管理员 (必须使用控制面板或命令行管理程序 cmdlet 创建或管理类别。</span><span class="sxs-lookup"><span data-stu-id="4cffe-111">Although many of the management features of chat rooms are available in computers running Persistent Chat for the user, Persistent Chat Administrators (in the **cspersistentchatadministrator** role) must use the control panel or management shell cmdlets to create or manage categories.</span></span>
  
<span data-ttu-id="4cffe-112">持久聊天管理员使用 Skype for Business Server 控制面板或 Windows PowerShell cmdlet 创建和管理类别，并设计组织中用户的聊天室访问权限。</span><span class="sxs-lookup"><span data-stu-id="4cffe-112">Persistent Chat Administrators use Skype for Business Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>
  
<span data-ttu-id="4cffe-113">具有管理一个或多个聊天室的能力的持久聊天室管理者可以使用客户端启动聊天室管理 Web 应用程序以创建和管理聊天室 (或者客户可以创建要调用的自定义解决方案和工作流) 。</span><span class="sxs-lookup"><span data-stu-id="4cffe-113">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> 
  
<span data-ttu-id="4cffe-p103">除聊天室的类别外，聊天室管理员可以更改所有聊天室的属性。管理员可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="4cffe-p103">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>
  
- <span data-ttu-id="4cffe-116">禁用聊天室</span><span class="sxs-lookup"><span data-stu-id="4cffe-116">Disabling a chat room</span></span>
    
- <span data-ttu-id="4cffe-117">更改聊天室名称</span><span class="sxs-lookup"><span data-stu-id="4cffe-117">Changing a chat room name</span></span>
    
- <span data-ttu-id="4cffe-118">更改聊天室说明</span><span class="sxs-lookup"><span data-stu-id="4cffe-118">Changing a chat room description</span></span>
    
- <span data-ttu-id="4cffe-119">更改聊天室类型（大会堂还是普通）</span><span class="sxs-lookup"><span data-stu-id="4cffe-119">Changing a chat room type (Auditorium versus Normal)</span></span>
    
- <span data-ttu-id="4cffe-120">更改聊天室的隐私（打开还是关闭还是保密）</span><span class="sxs-lookup"><span data-stu-id="4cffe-120">Changing the privacy of a room (open versus closed versus secret)</span></span>
    
- <span data-ttu-id="4cffe-121">添加或删除成员</span><span class="sxs-lookup"><span data-stu-id="4cffe-121">Adding or removing members</span></span>
    
- <span data-ttu-id="4cffe-122">添加或删除聊天室管理者</span><span class="sxs-lookup"><span data-stu-id="4cffe-122">Adding or removing chat room managers</span></span>
    
- <span data-ttu-id="4cffe-123">添加或删除加载项</span><span class="sxs-lookup"><span data-stu-id="4cffe-123">Adding or removing an add-in</span></span>
    
- <span data-ttu-id="4cffe-124">根据类别设置 (更改邀请等设置) </span><span class="sxs-lookup"><span data-stu-id="4cffe-124">Changing settings such as invitations (according to what's permitted by the category)</span></span>
    
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="4cffe-125">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="4cffe-125">Tasks that you can perform</span></span>

<span data-ttu-id="4cffe-126">您可以在"持久聊天配置"页上执行以下任务：全局配置持久聊天服务器选项或为特定池配置持久聊天服务器选项</span><span class="sxs-lookup"><span data-stu-id="4cffe-126">You can perform the following tasks on the **Persistent Chat Configuration** page: configure Persistent Chat Server options globally or for a specific pool</span></span>
  
## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="4cffe-127">全局配置持久聊天选项</span><span class="sxs-lookup"><span data-stu-id="4cffe-127">To configure Persistent Chat options globally</span></span>

1. <span data-ttu-id="4cffe-128">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录到您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="4cffe-128">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4cffe-129">从 **"开始** "菜单中，选择 Skype for Business Server 控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="4cffe-129">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="4cffe-130">在左侧导航栏中，单击“持久聊天”，然后单击“持久聊天配置”。</span><span class="sxs-lookup"><span data-stu-id="4cffe-130">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="4cffe-131">在"**持久聊天配置**"页上，单击 **"新建"，** 然后单击"**站点配置"。**</span><span class="sxs-lookup"><span data-stu-id="4cffe-131">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="4cffe-132">如果希望将配置应用于站点中部署的所有持久聊天服务器池，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="4cffe-132">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="4cffe-133">如果要 **将** 配置应用于特定的持久聊天服务器池，请单击"池配置"。</span><span class="sxs-lookup"><span data-stu-id="4cffe-133">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="4cffe-134">在 **"选择站点**"中，选择要为持久聊天服务器站点配置配置的站点。</span><span class="sxs-lookup"><span data-stu-id="4cffe-134">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="4cffe-135">在“新建持久聊天配置”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="4cffe-135">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="4cffe-p105">在“名称”中，指定新配置设置的名称。默认状态下，已存在站点名称。</span><span class="sxs-lookup"><span data-stu-id="4cffe-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
   - <span data-ttu-id="4cffe-p106">在“默认聊天历史记录”中，定义首次请求时每个聊天室要处理的聊天消息的数目。默认情况下，此数目为 30。这是全局默认值，管理员可根据每个类别禁用聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="4cffe-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="4cffe-141">持久聊天服务器将在内存中缓存这些消息，因此，如果增加此数目，将缓存更多消息。</span><span class="sxs-lookup"><span data-stu-id="4cffe-141">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="4cffe-142">您始终可通过搜索来访问历史记录内容。</span><span class="sxs-lookup"><span data-stu-id="4cffe-142">You can always access historical content by search.</span></span> <span data-ttu-id="4cffe-143">默认消息数仅确定您在连接到聊天室时首次看到的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="4cffe-143">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="4cffe-p108">在“最大文件大小(KB)”中，选择每条聊天历史记录的最大文件大小。默认情况下，此数目为 20 MB (20,000 KB)。这是可上载到系统（通过系统对应的“类别”设置为系统启用文件上载）中任何聊天室的文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="4cffe-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="4cffe-147">在“参与者更新限制”中，选择参与者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="4cffe-147">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="4cffe-148">持久聊天服务器向 (聊天室的用户发送名单) 发送给所有参与者，直到连接的用户数达到此数目。</span><span class="sxs-lookup"><span data-stu-id="4cffe-148">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="4cffe-149">默认情况下，此数目为 75。</span><span class="sxs-lookup"><span data-stu-id="4cffe-149">By default, the number is 75.</span></span> <span data-ttu-id="4cffe-150">此限制指示给定聊天室中参与者的最大数目，超过此限制后，持久聊天服务器将停止向连接客户端发送有关聊天室中与会者的名单更新。</span><span class="sxs-lookup"><span data-stu-id="4cffe-150">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="4cffe-151"> (Optional.) 在 **聊天室管理 URL 中**，选择聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="4cffe-151">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="4cffe-152">这是基于 Web 的自定义聊天室管理的 URL。</span><span class="sxs-lookup"><span data-stu-id="4cffe-152">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="4cffe-153">如果不需要自定义聊天室管理，并且只需使用默认设置，请保留此选项为空。</span><span class="sxs-lookup"><span data-stu-id="4cffe-153">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="4cffe-154">在设置该 URL 后，它将应用为内部和外部聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="4cffe-154">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
     <span data-ttu-id="4cffe-155">如果要自定义聊天室创建体验并包括特定的业务工作流，可以使用持久聊天服务器软件开发工具包 (SDK) 构建自定义聊天室管理解决方案，在某处托管它，将 URL 放在此处。</span><span class="sxs-lookup"><span data-stu-id="4cffe-155">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="4cffe-156">此 URL 将被发送给客户端，以便用户尝试查看/创建聊天室时将被指引到您的自定义聊天室管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="4cffe-156">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="4cffe-157">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="4cffe-157">Click **Commit**.</span></span>
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="4cffe-158">为特定持久聊天服务器池配置持久聊天选项</span><span class="sxs-lookup"><span data-stu-id="4cffe-158">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1. <span data-ttu-id="4cffe-159">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录到您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="4cffe-159">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4cffe-160">从 **"开始** "菜单中，选择 Skype for Business Server 控制面板，或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="4cffe-160">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="4cffe-161">在左侧导航栏中，单击“持久聊天”，然后单击“持久聊天配置”。</span><span class="sxs-lookup"><span data-stu-id="4cffe-161">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="4cffe-162">在“持久聊天配置”页上，单击“新建”，然后单击“池配置”。</span><span class="sxs-lookup"><span data-stu-id="4cffe-162">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="4cffe-163">在 **"选择服务**"中，选择与要配置的持久聊天服务器池关联的服务。</span><span class="sxs-lookup"><span data-stu-id="4cffe-163">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="4cffe-164">在“新建持久聊天配置”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="4cffe-164">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="4cffe-p112">在“名称”中，指定新配置设置的名称。默认情况下，已存在站点池名称。</span><span class="sxs-lookup"><span data-stu-id="4cffe-p112">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
   - <span data-ttu-id="4cffe-p113">在“默认聊天历史记录”中，定义首次请求时每个聊天室要处理的聊天消息的数目。默认情况下，此数目为 30。这是全局默认值，管理员可根据每个类别禁用聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="4cffe-p113">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="4cffe-170">持久聊天服务器将在内存中缓存这些消息，因此，如果增加此数目，将缓存更多消息。</span><span class="sxs-lookup"><span data-stu-id="4cffe-170">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="4cffe-171">您始终可通过搜索来访问历史记录内容。</span><span class="sxs-lookup"><span data-stu-id="4cffe-171">You can always access historical content by search.</span></span> <span data-ttu-id="4cffe-172">默认消息数仅确定您在连接到聊天室时首次看到的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="4cffe-172">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="4cffe-p115">在“最大文件大小(KB)”中，选择每条聊天历史记录的最大文件大小。默认情况下，此数目为 20 MB (20,000 KB)。这是可上载到系统（通过系统对应的“类别”设置为系统启用文件上载）中任何聊天室的文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="4cffe-p115">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="4cffe-176">在“参与者更新限制”中，选择参与者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="4cffe-176">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="4cffe-177">持久聊天服务器向 (聊天室的用户发送名单) 发送给所有参与者，直到连接的用户数达到此数目。</span><span class="sxs-lookup"><span data-stu-id="4cffe-177">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="4cffe-178">默认情况下，此数目为 75。</span><span class="sxs-lookup"><span data-stu-id="4cffe-178">By default, the number is 75.</span></span> <span data-ttu-id="4cffe-179">此限制指示给定聊天室中参与者的最大数目，超过此限制后，持久聊天服务器将停止向连接客户端发送有关聊天室中与会者的名单更新。</span><span class="sxs-lookup"><span data-stu-id="4cffe-179">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="4cffe-180">在“聊天室管理 URL”中，选择聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="4cffe-180">In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="4cffe-181">这是基于 Web 的聊天室管理部署的 URL。</span><span class="sxs-lookup"><span data-stu-id="4cffe-181">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="4cffe-182">如果不需要自定义聊天室管理，并且只需使用默认设置，请保留此选项为空。</span><span class="sxs-lookup"><span data-stu-id="4cffe-182">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
     <span data-ttu-id="4cffe-183">如果要自定义聊天室创建体验并包括特定的业务工作流，可以使用持久聊天服务器软件开发工具包 (SDK) 构建自定义聊天室管理解决方案，在某处托管它，将 URL 放在此处。</span><span class="sxs-lookup"><span data-stu-id="4cffe-183">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="4cffe-184">此 URL 将被发送给客户端，以便用户在尝试查看/创建聊天室时将被定向到您的自定义聊天室管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="4cffe-184">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="4cffe-185">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="4cffe-185">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="4cffe-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4cffe-186">See also</span></span>

<span data-ttu-id="4cffe-187">有关持久聊天服务器特性和功能的详细信息，请参阅规划 [Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)中的持久聊天服务器、在 Skype for Business Server [2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)中部署持久聊天服务器以及管理 [Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md)中的持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="4cffe-187">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

