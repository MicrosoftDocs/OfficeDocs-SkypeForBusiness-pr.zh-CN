---
title: 持久聊天配置主页
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatConfigMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1e75d352-12cf-4548-9301-5d4c0e1c8f46
description: 持久聊天服务器部署可以承载多个并发的持久聊天聊天室。 聊天室可以组织到服务器上的一组类别中。 每个聊天室属于一个类别，并继承该类别的一些设置。 这种组织方式可创建一种非常有用的结构以基于对话的业务目的识别对话，并有助于委托管理和简化控制。
ms.openlocfilehash: 4b8aa540b79ba92db441eb45e86ad8607a33c2f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33912160"
---
# <a name="persistent-chat-configuration-main-page"></a><span data-ttu-id="6e0f5-106">持久聊天配置主页</span><span class="sxs-lookup"><span data-stu-id="6e0f5-106">Persistent Chat Configuration Main Page</span></span>
 
<span data-ttu-id="6e0f5-107">持久聊天服务器部署可以承载多个并发的持久聊天聊天室。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-107">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="6e0f5-108">聊天室可以组织到服务器上的一组类别中。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-108">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="6e0f5-109">每个聊天室属于一个类别，并继承该类别的一些设置。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-109">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="6e0f5-110">这种组织方式可创建一种非常有用的结构以基于对话的业务目的识别对话，并有助于委托管理和简化控制。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-110">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6e0f5-111">尽管聊天室的管理功能的许多都运行持久聊天用户的计算机上可用，但 （ **cspersistentchatadministrator**角色） 中的持久聊天管理员必须使用控制面板或管理命令行管理程序 cmdlet若要创建或管理类别。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-111">Although many of the management features of chat rooms are available in computers running Persistent Chat for the user, Persistent Chat Administrators (in the **cspersistentchatadministrator** role) must use the control panel or management shell cmdlets to create or manage categories.</span></span>
  
<span data-ttu-id="6e0f5-112">持久聊天管理员为其组织中的用户使用 Skype 业务 Server Control Panel 或 Windows PowerShell cmdlet 创建和管理类别，并设计聊天室的访问权限。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-112">Persistent Chat Administrators use Skype for Business Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>
  
<span data-ttu-id="6e0f5-113">持久聊天聊天室经理，负责有一个或多个聊天室管理的功能，可以使用客户端启动聊天室管理 Web 应用程序以创建和管理聊天室 （或客户可以创建自定义解决方案和要调用的工作流）。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-113">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> 
  
<span data-ttu-id="6e0f5-p103">除了更改聊天室类别之外，聊天室管理员还可以更改所有聊天室属性。不能限制其执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6e0f5-p103">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>
  
- <span data-ttu-id="6e0f5-116">禁用聊天室</span><span class="sxs-lookup"><span data-stu-id="6e0f5-116">Disabling a chat room</span></span>
    
- <span data-ttu-id="6e0f5-117">更改聊天室名称</span><span class="sxs-lookup"><span data-stu-id="6e0f5-117">Changing a chat room name</span></span>
    
- <span data-ttu-id="6e0f5-118">更改聊天室说明</span><span class="sxs-lookup"><span data-stu-id="6e0f5-118">Changing a chat room description</span></span>
    
- <span data-ttu-id="6e0f5-119">更改聊天室类型（大会堂还是普通）</span><span class="sxs-lookup"><span data-stu-id="6e0f5-119">Changing a chat room type (Auditorium versus Normal)</span></span>
    
- <span data-ttu-id="6e0f5-120">更改聊天室隐私（开放、关闭还是秘密）</span><span class="sxs-lookup"><span data-stu-id="6e0f5-120">Changing the privacy of a room (open versus closed versus secret)</span></span>
    
- <span data-ttu-id="6e0f5-121">添加或删除成员</span><span class="sxs-lookup"><span data-stu-id="6e0f5-121">Adding or removing members</span></span>
    
- <span data-ttu-id="6e0f5-122">添加或删除聊天室管理者</span><span class="sxs-lookup"><span data-stu-id="6e0f5-122">Adding or removing chat room managers</span></span>
    
- <span data-ttu-id="6e0f5-123">添加或删除加载项</span><span class="sxs-lookup"><span data-stu-id="6e0f5-123">Adding or removing an add-in</span></span>
    
- <span data-ttu-id="6e0f5-124">更改设置，例如邀请 （根据类别允许内容）</span><span class="sxs-lookup"><span data-stu-id="6e0f5-124">Changing settings such as invitations (according to what's permitted by the category)</span></span>
    
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="6e0f5-125">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="6e0f5-125">Tasks that you can perform</span></span>

<span data-ttu-id="6e0f5-126">您可以在**持久聊天配置**页上执行以下任务： 全局范围或针对特定池配置持久聊天服务器选项</span><span class="sxs-lookup"><span data-stu-id="6e0f5-126">You can perform the following tasks on the **Persistent Chat Configuration** page: configure Persistent Chat Server options globally or for a specific pool</span></span>
  
## <a name="to-configure-persistent-chat-options-globally"></a><span data-ttu-id="6e0f5-127">全局配置持久聊天选项</span><span class="sxs-lookup"><span data-stu-id="6e0f5-127">To configure Persistent Chat options globally</span></span>

1. <span data-ttu-id="6e0f5-128">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-128">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6e0f5-129">从**开始**菜单上，选择业务 Server Control Panel Skype 或打开一个浏览器窗口中，，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-129">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="6e0f5-130">在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天配置**”。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-130">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="6e0f5-131">在**持久聊天配置**页上，单击**新建**，然后单击**站点配置**。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-131">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6e0f5-132">如果您想要应用于该站点中部署的所有持久聊天服务器池的配置，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-132">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="6e0f5-133">如果您想要应用于特定的持久聊天服务器池的配置，请单击**池配置**。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-133">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="6e0f5-134">在**选择站点**，选择要配置的站点的持久聊天服务器网站配置的站点。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-134">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="6e0f5-135">在“**新建持久聊天配置**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="6e0f5-135">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="6e0f5-p105">在“**名称**”中，指定新配置设置的名称。默认情况下，已存在站点名称。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-p105">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
   - <span data-ttu-id="6e0f5-p106">在“**默认聊天历史记录**”中，定义首次请求时每个聊天室要处理的聊天消息的数目。默认情况下，此数目为 30。这是全局默认值，管理员可根据每个类别禁用聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-p106">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="6e0f5-141">持久聊天服务器将缓存在内存中，这些消息以便更多邮件如果增加此号码，将进行缓存。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-141">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="6e0f5-142">您始终可通过搜索来访问历史内容。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-142">You can always access historical content by search.</span></span> <span data-ttu-id="6e0f5-143">默认数目只确定您在连接到聊天室时最初看到的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-143">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="6e0f5-p108">在“**最大文件大小(KB)**”中，选择每条聊天历史记录的最大文件大小。默认情况下，此数目为 20 MB (20,000 KB)。这是可以上载到系统（已通过对应的“**类别**”设置为其启用文件上载）中任意聊天室的文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-p108">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="6e0f5-147">在“**参与者更新限制**”中，选择对参与者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-147">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="6e0f5-148">持久聊天服务器向所有参与者发送名单信息 （用户连接到聊天室），直到连接的用户的数量达到此号码。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-148">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="6e0f5-149">默认情况下，此数目为 75。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-149">By default, the number is 75.</span></span> <span data-ttu-id="6e0f5-150">此限制指示给定聊天室超出其 Persistent Chat Server 停止向有关谁是在聊天室中存在连接的客户端发送名单更新中的参与者的最大数量。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-150">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="6e0f5-151">（可选）。在**聊天室管理 URL**中，选择聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-151">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="6e0f5-152">这是基于 Web 的自定义聊天室管理的 URL。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-152">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="6e0f5-153">如果不需要自定义聊天室管理，并且您只需使用的默认设置，请将此选项保留为空。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-153">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="6e0f5-154">在设置该 URL 后，它将应用为内部和外部聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-154">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
     <span data-ttu-id="6e0f5-155">如果您想要自定义聊天室创建体验，并包括特定业务工作流，您可以使用持久聊天服务器软件开发工具包 (SDK) 构建的自定义聊天室管理解决方案、 某个位置，承载和在此处输入 URL。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-155">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="6e0f5-156">此 URL 将被发送给客户端，以便用户在尝试查看或创建聊天室时将被定向到您的自定义聊天室管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-156">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="6e0f5-157">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-157">Click **Commit**.</span></span>
    
## <a name="to-configure-persistent-chat-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="6e0f5-158">若要配置的一个特定的持久聊天服务器池的持久聊天选项</span><span class="sxs-lookup"><span data-stu-id="6e0f5-158">To configure Persistent Chat options for a specific Persistent Chat Server pool</span></span>

1. <span data-ttu-id="6e0f5-159">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-159">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6e0f5-160">从**开始**菜单中，为业务服务器控制面板中，选择 Skype 或打开浏览器窗口，，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-160">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="6e0f5-161">在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天配置**”。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-161">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="6e0f5-162">在“**持久聊天配置**”页上，单击“**新建**”，然后单击“**池配置**”。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-162">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="6e0f5-163">在**选择服务**，选择与要配置的持久聊天服务器池关联的服务。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-163">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="6e0f5-164">在“**新建持久聊天配置**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="6e0f5-164">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="6e0f5-p112">在“**名称**”中，指定新配置设置的名称。默认情况下，已存在站点池名称。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-p112">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
   - <span data-ttu-id="6e0f5-p113">在“**默认聊天历史记录**”中，定义首次请求时每个聊天室要处理的聊天消息的数目。默认情况下，此数目为 30。这是全局默认值，管理员可根据每个类别禁用聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-p113">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="6e0f5-170">持久聊天服务器将缓存在内存中，这些消息以便更多邮件如果增加此号码，将进行缓存。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-170">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="6e0f5-171">您始终可通过搜索来访问历史内容。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-171">You can always access historical content by search.</span></span> <span data-ttu-id="6e0f5-172">默认数目只确定您在连接到聊天室时最初看到的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-172">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="6e0f5-p115">在“**最大文件大小(KB)**”中，选择每条聊天历史记录的最大文件大小。默认情况下，此数目为 20 MB (20,000 KB)。这是可以上载到系统（已通过对应的“**类别**”设置为其启用文件上载）中任意聊天室的文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-p115">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="6e0f5-176">在“**参与者更新限制**”中，选择对参与者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-176">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="6e0f5-177">持久聊天服务器向所有参与者发送名单信息 （用户连接到聊天室），直到连接的用户的数量达到此号码。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-177">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="6e0f5-178">默认情况下，此数目为 75。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-178">By default, the number is 75.</span></span> <span data-ttu-id="6e0f5-179">此限制指示给定聊天室超出其 Persistent Chat Server 停止向有关谁是在聊天室中存在连接的客户端发送名单更新中的参与者的最大数量。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-179">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="6e0f5-180">在“**聊天室管理 URL**”中，选择聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-180">In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="6e0f5-181">这是基于 Web 的聊天室管理部署的 URL。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-181">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="6e0f5-182">如果不需要自定义聊天室管理，并且您只需使用的默认设置，请将此选项保留为空。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-182">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
     <span data-ttu-id="6e0f5-183">如果您想要自定义聊天室创建体验，并包括特定业务工作流，您可以使用持久聊天服务器软件开发工具包 (SDK) 构建的自定义聊天室管理解决方案、 某个位置，承载和在此处输入 URL。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-183">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="6e0f5-184">此 URL 将被发送给客户端，以便用户在尝试查看/创建聊天室时将被定向到您的自定义聊天室管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-184">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="6e0f5-185">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-185">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="6e0f5-186">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6e0f5-186">See also</span></span>

<span data-ttu-id="6e0f5-187">有关详细信息 Persistent Chat Server 特性和功能，请参阅[Plan for Persistent Chat Server in 业务服务器 2015年的 Skype](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、[部署持久聊天服务器中的 Business Server 2015 Skype](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)和[管理持久聊天服务器在业务服务器 2015 Skype](../../manage/persistent-chat/persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="6e0f5-187">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

