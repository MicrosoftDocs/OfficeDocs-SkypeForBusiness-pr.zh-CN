---
title: 在 Skype for Business Server 2015 中配置持久聊天服务器选项
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: 摘要：了解如何在 Skype for Business Server 2015 中的全局、站点或池级别配置持久聊天服务器选项。
ms.openlocfilehash: 9c0b6d5e03b9bc4f7d955ea0dae3e1c45b14ada3
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802122"
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a><span data-ttu-id="1dbaa-103">在 Skype for Business Server 2015 中配置持久聊天服务器选项</span><span class="sxs-lookup"><span data-stu-id="1dbaa-103">Configure Persistent Chat Server options in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1dbaa-104">**摘要：** 了解如何在 Skype for Business Server 2015 中的全局、站点或池级别配置持久聊天服务器选项。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-104">**Summary:** Learn how to configure Persistent Chat Server options at the global, site, or pool level in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="1dbaa-105">您可以为持久聊天服务器指定多个选项，这些选项可以全局应用于站点内的所有池或站点中的特定池。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-105">You can specify several options for Persistent Chat Server that can be applied globally, to all pools within a site, or to a specific pool within a site.</span></span> <span data-ttu-id="1dbaa-106">持久聊天服务器选项包括：</span><span class="sxs-lookup"><span data-stu-id="1dbaa-106">Persistent Chat server options include the following:</span></span> 
  
- <span data-ttu-id="1dbaa-107">默认聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-107">Default Chat History.</span></span> <span data-ttu-id="1dbaa-108">首次请求时每个聊天室可用的聊天消息数。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-108">The number of chat messages that are available for each chat room upon first request.</span></span> <span data-ttu-id="1dbaa-109">全局默认值为 30 条聊天消息。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-109">The global default is 30 chat messages.</span></span> 
    
- <span data-ttu-id="1dbaa-110">最大文件大小。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-110">Maximum File Size.</span></span> <span data-ttu-id="1dbaa-111">可以上载到聊天室或从聊天室下载的文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-111">The maximum size of a file that can be uploaded to or downloaded from a room.</span></span> <span data-ttu-id="1dbaa-112">全局默认值为 20MB。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-112">The global default is 20MB.</span></span>
    
- <span data-ttu-id="1dbaa-113">参与者更新限制。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-113">Participant Update Limit.</span></span> <span data-ttu-id="1dbaa-114">持久聊天将发送其名单更新的给定聊天室中的最大参与者数。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-114">The maximum number of participants in a given chat room for which Persistent Chat will send roster updates.</span></span> <span data-ttu-id="1dbaa-115">全局默认值为 75。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-115">The global default is 75.</span></span>
    
- <span data-ttu-id="1dbaa-116">聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-116">Room Management URL.</span></span> <span data-ttu-id="1dbaa-117">用于自定义聊天室管理的 URL。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-117">The URL used for custom chat room management.</span></span> <span data-ttu-id="1dbaa-118">该设置允许使用自定义聊天室管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-118">The setting allows the use of a custom room management solution.</span></span> 
   
> [!NOTE] 
> <span data-ttu-id="1dbaa-119">持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-119">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="1dbaa-120">Teams 中也提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-120">The same functionality is available in Teams.</span></span> <span data-ttu-id="1dbaa-121">有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-121">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="1dbaa-122">如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-122">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span>
 
## <a name="configure-persistent-chat-server-global-options"></a><span data-ttu-id="1dbaa-123">配置持久聊天服务器全局选项</span><span class="sxs-lookup"><span data-stu-id="1dbaa-123">Configure Persistent Chat Server global options</span></span>

<span data-ttu-id="1dbaa-124">配置持久聊天服务器全局选项：</span><span class="sxs-lookup"><span data-stu-id="1dbaa-124">To configure Persistent Chat Server global options:</span></span>
  
1. <span data-ttu-id="1dbaa-125">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录到您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-125">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="1dbaa-126">从 **"开始** "菜单中，选择 Skype for Business Server 控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-126">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="1dbaa-127">在左侧导航栏中，单击“持久聊天”，然后单击“持久聊天配置”。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-127">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="1dbaa-128">在"**持久聊天配置**"页上，单击 **"新建"，** 然后单击"**站点配置"。**</span><span class="sxs-lookup"><span data-stu-id="1dbaa-128">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="1dbaa-129">如果希望将配置应用于站点中部署的所有持久聊天服务器池，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-129">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="1dbaa-130">如果要 **将** 配置应用于特定的持久聊天服务器池，请单击"池配置"。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-130">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="1dbaa-131">在 **"选择站点**"中，选择要为持久聊天服务器站点配置配置的站点。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-131">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="1dbaa-132">在“新建持久聊天配置”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1dbaa-132">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="1dbaa-p108">在“名称”中，指定新配置设置的名称。默认状态下，已存在站点名称。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-p108">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
   - <span data-ttu-id="1dbaa-p109">在“默认聊天历史记录”中，定义首次请求时每个聊天室要处理的聊天消息的数目。默认情况下，此数目为 30。这是全局默认值，管理员可根据每个类别禁用聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-p109">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="1dbaa-138">持久聊天服务器将在内存中缓存这些消息，因此，如果增加此数目，将缓存更多消息。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-138">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="1dbaa-139">您始终可通过搜索来访问历史记录内容。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-139">You can always access historical content by search.</span></span> <span data-ttu-id="1dbaa-140">默认消息数仅确定您在连接到聊天室时首次看到的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-140">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="1dbaa-p111">在“最大文件大小(KB)”中，选择每条聊天历史记录的最大文件大小。默认情况下，此数目为 20 MB (20,000 KB)。这是可上载到系统（通过系统对应的“类别”设置为系统启用文件上载）中任何聊天室的文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-p111">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="1dbaa-144">在“参与者更新限制”中，选择参与者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-144">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="1dbaa-145">持久聊天服务器向 (聊天室的用户发送名单) 发送给所有参与者，直到连接的用户数达到此数目。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-145">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="1dbaa-146">默认情况下，此数目为 75。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-146">By default, the number is 75.</span></span> <span data-ttu-id="1dbaa-147">此限制指示给定聊天室中参与者的最大数目，超过此限制后，持久聊天服务器将停止向连接客户端发送有关聊天室中与会者的名单更新。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-147">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="1dbaa-148"> (Optional.) 在 **聊天室管理 URL 中**，选择聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-148">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="1dbaa-149">这是基于 Web 的自定义聊天室管理的 URL。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-149">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="1dbaa-150">如果不需要自定义聊天室管理，并且只需使用默认设置，请保留此选项为空。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-150">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="1dbaa-151">在设置该 URL 后，它将应用为内部和外部聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-151">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
     <span data-ttu-id="1dbaa-152">如果要自定义聊天室创建体验并包括特定的业务工作流，可以使用持久聊天服务器软件开发工具包 (SDK) 构建自定义聊天室管理解决方案，在某处托管它，将 URL 放在此处。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-152">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="1dbaa-153">此 URL 将被发送给客户端，以便用户尝试查看/创建聊天室时将被指引到您的自定义聊天室管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-153">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="1dbaa-154">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-154">Click **Commit**.</span></span>
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="1dbaa-155">配置特定持久聊天服务器池的选项</span><span class="sxs-lookup"><span data-stu-id="1dbaa-155">Configure options for a specific Persistent Chat Server pool</span></span>

<span data-ttu-id="1dbaa-156">配置特定持久聊天服务器池的选项。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-156">To configure options for a specific Persistent Chat Server pool.</span></span>
  
1. <span data-ttu-id="1dbaa-157">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录到您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-157">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="1dbaa-158">从 **"开始** "菜单中，选择 Skype for Business Server 控制面板，或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-158">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="1dbaa-159">在左侧导航栏中，单击“持久聊天”，然后单击“持久聊天配置”。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-159">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="1dbaa-160">在“持久聊天配置”页上，单击“新建”，然后单击“池配置”。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-160">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="1dbaa-161">在 **"选择服务**"中，选择与要配置的持久聊天服务器池关联的服务。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-161">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="1dbaa-162">在“新建持久聊天配置”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="1dbaa-162">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="1dbaa-p115">在“名称”中，指定新配置设置的名称。默认情况下，已存在站点池名称。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-p115">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
   - <span data-ttu-id="1dbaa-p116">在“默认聊天历史记录”中，定义首次请求时每个聊天室要处理的聊天消息的数目。默认情况下，此数目为 30。这是全局默认值，管理员可根据每个类别禁用聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-p116">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="1dbaa-168">持久聊天服务器将在内存中缓存这些消息，因此，如果增加此数目，将缓存更多消息。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-168">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="1dbaa-169">您始终可通过搜索来访问历史记录内容。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-169">You can always access historical content by search.</span></span> <span data-ttu-id="1dbaa-170">默认消息数仅确定您在连接到聊天室时首次看到的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-170">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="1dbaa-p118">在“最大文件大小(KB)”中，选择每条聊天历史记录的最大文件大小。默认情况下，此数目为 20 MB (20,000 KB)。这是可上载到系统（通过系统对应的“类别”设置为系统启用文件上载）中任何聊天室的文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-p118">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="1dbaa-174">在“参与者更新限制”中，选择参与者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-174">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="1dbaa-175">持久聊天服务器向 (聊天室的用户发送名单) 发送给所有参与者，直到连接的用户数达到此数目。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-175">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="1dbaa-176">默认情况下，此数目为 75。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-176">By default, the number is 75.</span></span> <span data-ttu-id="1dbaa-177">此限制指示给定聊天室中参与者的最大数目，超过此限制后，持久聊天服务器将停止向连接客户端发送有关聊天室中与会者的名单更新。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-177">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="1dbaa-178">在“聊天室管理 URL”中，选择聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-178">In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="1dbaa-179">这是基于 Web 的聊天室管理部署的 URL。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-179">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="1dbaa-180">如果不需要自定义聊天室管理，并且只需使用默认设置，请保留此选项为空。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-180">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
     <span data-ttu-id="1dbaa-181">如果要自定义聊天室创建体验并包括特定的业务工作流，可以使用持久聊天服务器软件开发工具包 (SDK) 构建自定义聊天室管理解决方案，在某处托管它，将 URL 放在此处。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-181">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="1dbaa-182">此 URL 将被发送给客户端，以便用户在尝试查看/创建聊天室时将被定向到您的自定义聊天室管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-182">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="1dbaa-183">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="1dbaa-183">Click **Commit**.</span></span>
    

