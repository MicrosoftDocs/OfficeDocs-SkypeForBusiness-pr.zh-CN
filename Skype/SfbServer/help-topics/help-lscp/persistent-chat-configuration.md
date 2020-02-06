---
title: 持久聊天配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatConfig
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3f2891e6-bad3-4a23-a345-b7de4cae3bd9
description: 持久聊天服务器部署可以托管多个并发的持久聊天室。 聊天室可以组织到服务器上的一组类别中。 每个聊天室属于一个类别，并继承该类别的一些设置。 这种组织方式可创建一种非常有用的结构以基于对话的业务目的识别对话，并有助于委托管理和简化控制。
ms.openlocfilehash: 46d23d810b932b1295e4ad5f1c38dd3dd0990f5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822525"
---
# <a name="persistent-chat-configuration"></a><span data-ttu-id="13af5-106">持久聊天配置</span><span class="sxs-lookup"><span data-stu-id="13af5-106">Persistent Chat Configuration</span></span>
 
<span data-ttu-id="13af5-107">持久聊天服务器部署可以托管多个并发的持久聊天室。</span><span class="sxs-lookup"><span data-stu-id="13af5-107">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="13af5-108">聊天室可以组织到服务器上的一组类别中。</span><span class="sxs-lookup"><span data-stu-id="13af5-108">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="13af5-109">每个聊天室属于一个类别，并继承该类别的一些设置。</span><span class="sxs-lookup"><span data-stu-id="13af5-109">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="13af5-110">这种组织方式可创建一种非常有用的结构以基于对话的业务目的识别对话，并有助于委托管理和简化控制。</span><span class="sxs-lookup"><span data-stu-id="13af5-110">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>
  
> [!NOTE]
> <span data-ttu-id="13af5-111">虽然聊天室的许多管理功能在运行用户持久聊天的计算机中可用，但持续聊天管理员（在**cspersistentchatadministrator**角色中）必须使用 "控制面板" 或 "管理外壳" cmdlet 来创建或管理类别。</span><span class="sxs-lookup"><span data-stu-id="13af5-111">Although many of the management features of chat rooms are available in computers running Persistent Chat for the user, Persistent Chat Administrators (in the **cspersistentchatadministrator** role) must use either the control panel or management shell cmdlets to create or manage categories.</span></span>
  
<span data-ttu-id="13af5-112">持久聊天管理员使用 Skype for Business 服务器控制面板或 Windows PowerShell cmdlet 来创建和管理类别，并为组织中的用户设计对聊天室的访问。</span><span class="sxs-lookup"><span data-stu-id="13af5-112">Persistent Chat Administrators use Skype for Business Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>
  
<span data-ttu-id="13af5-113">持久的聊天室管理器，他们可以管理一个或多个聊天室，可以使用客户端启动聊天室管理 Web 应用程序来创建和管理会议室（或者客户可以创建要调用的自定义解决方案和工作流）。</span><span class="sxs-lookup"><span data-stu-id="13af5-113">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> <span data-ttu-id="13af5-114">持久聊天</span><span class="sxs-lookup"><span data-stu-id="13af5-114">Persistent Chat</span></span>
  
<span data-ttu-id="13af5-115">持久聊天管理员还可以使用 "控制面板" 或 Windows PowerShell cmdlet 来创建和管理会议室。</span><span class="sxs-lookup"><span data-stu-id="13af5-115">Persistent Chat administrators can also use control panel or Windows PowerShell cmdlets to create and manage rooms.</span></span>
  
<span data-ttu-id="13af5-p104">除了更改聊天室类别之外，聊天室管理员还可以更改所有聊天室属性。不能限制其执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="13af5-p104">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>
  
- <span data-ttu-id="13af5-118">禁用聊天室</span><span class="sxs-lookup"><span data-stu-id="13af5-118">Disabling a chat room</span></span>
    
- <span data-ttu-id="13af5-119">更改聊天室名称</span><span class="sxs-lookup"><span data-stu-id="13af5-119">Changing a chat room name</span></span>
    
- <span data-ttu-id="13af5-120">更改聊天室说明</span><span class="sxs-lookup"><span data-stu-id="13af5-120">Changing a chat room description</span></span>
    
- <span data-ttu-id="13af5-121">更改聊天室类型（大会堂还是普通）</span><span class="sxs-lookup"><span data-stu-id="13af5-121">Changing a chat room type (Auditorium versus Normal)</span></span>
    
- <span data-ttu-id="13af5-122">更改聊天室隐私（开放、关闭还是秘密）</span><span class="sxs-lookup"><span data-stu-id="13af5-122">Changing the privacy of a room (open versus closed versus secret)</span></span>
    
- <span data-ttu-id="13af5-123">添加或删除成员</span><span class="sxs-lookup"><span data-stu-id="13af5-123">Adding or removing members</span></span>
    
- <span data-ttu-id="13af5-124">添加或删除聊天室管理者</span><span class="sxs-lookup"><span data-stu-id="13af5-124">Adding or removing chat room managers</span></span>
    
- <span data-ttu-id="13af5-125">添加或删除加载项</span><span class="sxs-lookup"><span data-stu-id="13af5-125">Adding or removing an add-in</span></span>
    
- <span data-ttu-id="13af5-126">更改邀请的设置（根据类别允许的内容）</span><span class="sxs-lookup"><span data-stu-id="13af5-126">Changing settings such as invitations (according to what's permitted by the category)</span></span>
    
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="13af5-127">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="13af5-127">Tasks that you can perform</span></span>

<span data-ttu-id="13af5-128">可以在 "**持久聊天" 配置**页面上执行以下任务：为全局或特定池配置持久聊天服务器选项。</span><span class="sxs-lookup"><span data-stu-id="13af5-128">You can perform the following tasks on the **Persistent Chat Configuration** page: configure Persistent Chat Server options globally or for a specific pool.</span></span>
  
## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="13af5-129">全局配置持久聊天选项</span><span class="sxs-lookup"><span data-stu-id="13af5-129">To configure Persistent Chat options globally</span></span>

1. <span data-ttu-id="13af5-130">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="13af5-130">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="13af5-131">从 "**开始**" 菜单中，选择 "Skype For business 服务器" 控制面板或打开一个浏览器窗口，然后输入管理员 URL。</span><span class="sxs-lookup"><span data-stu-id="13af5-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="13af5-132">在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天配置**”。</span><span class="sxs-lookup"><span data-stu-id="13af5-132">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="13af5-133">在 "**持久聊天配置**" 页面上，单击 "**新建"，** 然后单击 "**网站配置**"。</span><span class="sxs-lookup"><span data-stu-id="13af5-133">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="13af5-134">如果你希望将配置应用到网站中部署的所有持久聊天服务器池，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="13af5-134">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="13af5-135">如果要将配置应用于特定的持久聊天服务器池，请单击 "**池配置**"。</span><span class="sxs-lookup"><span data-stu-id="13af5-135">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="13af5-136">在 "**选择网站**" 中，选择要为持久聊天服务器网站配置配置的网站。</span><span class="sxs-lookup"><span data-stu-id="13af5-136">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="13af5-137">在“**新建持久聊天配置**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="13af5-137">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="13af5-p106">在“**名称**”中，指定新配置设置的名称。默认情况下，已存在站点名称。</span><span class="sxs-lookup"><span data-stu-id="13af5-p106">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
   - <span data-ttu-id="13af5-p107">在“**默认聊天历史记录**”中，定义首次请求时每个聊天室要处理的聊天消息的数目。默认情况下，此数目为 30。这是全局默认值，管理员可根据每个类别禁用聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="13af5-p107">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="13af5-143">持久聊天服务器将在内存中缓存这些消息，因此如果增加此数字，将缓存更多消息。</span><span class="sxs-lookup"><span data-stu-id="13af5-143">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="13af5-144">您始终可通过搜索来访问历史内容。</span><span class="sxs-lookup"><span data-stu-id="13af5-144">You can always access historical content by search.</span></span> <span data-ttu-id="13af5-145">默认数目只确定您在连接到聊天室时最初看到的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="13af5-145">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="13af5-p109">在“**最大文件大小(KB)**”中，选择每条聊天历史记录的最大文件大小。默认情况下，此数目为 20 MB (20,000 KB)。这是可以上载到系统（已通过对应的“**类别**”设置为其启用文件上载）中任意聊天室的文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="13af5-p109">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="13af5-149">在“**参与者更新限制**”中，选择对参与者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="13af5-149">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="13af5-150">持久聊天服务器向所有参与者发送名单信息（已连接到聊天室的用户），直到连接的用户数达到此号码。</span><span class="sxs-lookup"><span data-stu-id="13af5-150">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="13af5-151">默认情况下，此数目为 75。</span><span class="sxs-lookup"><span data-stu-id="13af5-151">By default, the number is 75.</span></span> <span data-ttu-id="13af5-152">此限制指示在指定房间内的参与者的最大数量，超过该空间后，永久聊天服务器将停止向已连接客户端发送名单更新。</span><span class="sxs-lookup"><span data-stu-id="13af5-152">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="13af5-153">（可选。）在 "**会议室管理 url**" 中，选择会议室管理 url。</span><span class="sxs-lookup"><span data-stu-id="13af5-153">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="13af5-154">这是基于 Web 的自定义聊天室管理的 URL。</span><span class="sxs-lookup"><span data-stu-id="13af5-154">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="13af5-155">如果不需要自定义聊天室管理，只需使用默认设置，请将此选项保留为空。</span><span class="sxs-lookup"><span data-stu-id="13af5-155">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="13af5-156">在设置该 URL 后，它将应用为内部和外部聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="13af5-156">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
     <span data-ttu-id="13af5-157">如果你想要自定义聊天室创建体验并包含特定的业务工作流，你可以使用持久聊天服务器软件开发工具包（SDK）构建自定义聊天室管理解决方案，并将 URL 放置在此处。</span><span class="sxs-lookup"><span data-stu-id="13af5-157">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="13af5-158">此 URL 将被发送给客户端，以便用户在尝试查看或创建聊天室时将被定向到您的自定义聊天室管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="13af5-158">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="13af5-159">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="13af5-159">Click **Commit**.</span></span>
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="13af5-160">为特定的持久聊天服务器池配置持久聊天选项</span><span class="sxs-lookup"><span data-stu-id="13af5-160">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1. <span data-ttu-id="13af5-161">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="13af5-161">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="13af5-162">从 "**开始**" 菜单中，选择 "Skype For business 服务器" 控制面板，或打开一个浏览器窗口，然后输入管理员 URL。</span><span class="sxs-lookup"><span data-stu-id="13af5-162">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="13af5-163">在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天配置**”。</span><span class="sxs-lookup"><span data-stu-id="13af5-163">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="13af5-164">在“**持久聊天配置**”页上，单击“**新建**”，然后单击“**池配置**”。</span><span class="sxs-lookup"><span data-stu-id="13af5-164">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="13af5-165">在 "**选择服务**" 中，选择与要配置的持久聊天服务器池相关联的服务。</span><span class="sxs-lookup"><span data-stu-id="13af5-165">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="13af5-166">在“**新建持久聊天配置**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="13af5-166">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="13af5-p113">在“**名称**”中，指定新配置设置的名称。默认情况下，已存在站点池名称。</span><span class="sxs-lookup"><span data-stu-id="13af5-p113">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
   - <span data-ttu-id="13af5-p114">在“**默认聊天历史记录**”中，定义首次请求时每个聊天室要处理的聊天消息的数目。默认情况下，此数目为 30。这是全局默认值，管理员可根据每个类别禁用聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="13af5-p114">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="13af5-172">持久聊天服务器将在内存中缓存这些消息，因此如果增加此数字，将缓存更多消息。</span><span class="sxs-lookup"><span data-stu-id="13af5-172">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="13af5-173">您始终可通过搜索来访问历史内容。</span><span class="sxs-lookup"><span data-stu-id="13af5-173">You can always access historical content by search.</span></span> <span data-ttu-id="13af5-174">默认数目只确定您在连接到聊天室时最初看到的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="13af5-174">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="13af5-p116">在“**最大文件大小(KB)**”中，选择每条聊天历史记录的最大文件大小。默认情况下，此数目为 20 MB (20,000 KB)。这是可以上载到系统（已通过对应的“**类别**”设置为其启用文件上载）中任意聊天室的文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="13af5-p116">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="13af5-178">在“**参与者更新限制**”中，选择对参与者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="13af5-178">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="13af5-179">持久聊天服务器向所有参与者发送名单信息（已连接到聊天室的用户），直到连接的用户数达到此号码。</span><span class="sxs-lookup"><span data-stu-id="13af5-179">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="13af5-180">默认情况下，此数目为 75。</span><span class="sxs-lookup"><span data-stu-id="13af5-180">By default, the number is 75.</span></span> <span data-ttu-id="13af5-181">此限制指示在指定房间内的参与者的最大数量，超过该空间后，永久聊天服务器将停止向已连接客户端发送名单更新。</span><span class="sxs-lookup"><span data-stu-id="13af5-181">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="13af5-182">（可选）在“**聊天室管理 URL**”中，选择聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="13af5-182">(Optional) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="13af5-183">这是基于 Web 的聊天室管理部署的 URL。</span><span class="sxs-lookup"><span data-stu-id="13af5-183">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="13af5-184">如果不需要自定义聊天室管理，只需使用默认设置，请将此选项保留为空。</span><span class="sxs-lookup"><span data-stu-id="13af5-184">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
     <span data-ttu-id="13af5-185">如果你想要自定义聊天室创建体验并包含特定的业务工作流，你可以使用持久聊天服务器软件开发工具包（SDK）构建自定义聊天室管理解决方案，并将 URL 放置在此处。</span><span class="sxs-lookup"><span data-stu-id="13af5-185">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="13af5-186">此 URL 将被发送给客户端，以便用户在尝试查看/创建聊天室时将被定向到您的自定义聊天室管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="13af5-186">This URL is sent down to the client, so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="13af5-187">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="13af5-187">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="13af5-188">另请参阅</span><span class="sxs-lookup"><span data-stu-id="13af5-188">See also</span></span>

<span data-ttu-id="13af5-189">有关持久聊天服务器功能和功能的详细信息，请参阅在 skype for business [server 2015 中规划持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、在 skype For business [server 2015 中部署持久](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)聊天服务器以及[在 skype For Business Server 2015 中管理持久聊天服务器](../../manage/persistent-chat/persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="13af5-189">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

