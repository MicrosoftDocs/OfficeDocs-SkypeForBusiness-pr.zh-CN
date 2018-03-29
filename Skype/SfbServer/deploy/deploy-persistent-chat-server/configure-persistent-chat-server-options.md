---
title: 在 Skype for Business Server 2015 中配置持久聊天服务器选项
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 19ced8de-8867-4152-b38a-891f3bc2a5ea
description: 摘要： 了解如何配置在全局持久聊天服务器选项、 网站或池级别在 Skype 业务服务器 2015年。
ms.openlocfilehash: 6fe06b6a5383178f0a9465624f7a0e739c2a32e6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-persistent-chat-server-options-in-skype-for-business-server-2015"></a><span data-ttu-id="6fb9f-103">在 Skype for Business Server 2015 中配置持久聊天服务器选项</span><span class="sxs-lookup"><span data-stu-id="6fb9f-103">Configure Persistent Chat Server options in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6fb9f-104">**摘要：**了解如何配置在全局持久聊天服务器选项、 网站或池级别在 Skype 业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-104">**Summary:** Learn how to configure Persistent Chat Server options at the global, site, or pool level in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="6fb9f-105">您可以指定到一个站点内的所有池或在站点内的一个特定的池可以全局，应用的持久聊天服务器的多个选项。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-105">You can specify several options for Persistent Chat Server that can be applied globally, to all pools within a site, or to a specific pool within a site.</span></span> <span data-ttu-id="6fb9f-106">持久聊天服务器选项包括以下内容：</span><span class="sxs-lookup"><span data-stu-id="6fb9f-106">Persistent Chat server options include the following:</span></span> 
  
- <span data-ttu-id="6fb9f-107">默认聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-107">Default Chat History.</span></span> <span data-ttu-id="6fb9f-108">首次请求时每个聊天室的可用聊天消息数量。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-108">The number of chat messages that are available for each chat room upon first request.</span></span> <span data-ttu-id="6fb9f-109">全局默认设置为 30 条聊天消息。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-109">The global default is 30 chat messages.</span></span> 
    
- <span data-ttu-id="6fb9f-p103">最大文件大小。可从聊天室上载或下载的最大文件大小。全局默认设置为 20MB。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-p103">Maximum File Size. The maximum size of a file that can be uploaded to or downloaded from a room. The global default is 20MB.</span></span>
    
- <span data-ttu-id="6fb9f-113">参与者更新限制。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-113">Participant Update Limit.</span></span> <span data-ttu-id="6fb9f-114">指定聊天室中持久聊天向其发送名单更新的最大参与者人数。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-114">The maximum number of participants in a given chat room for which Persistent Chat will send roster updates.</span></span> <span data-ttu-id="6fb9f-115">全局默认设置为 75。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-115">The global default is 75.</span></span>
    
- <span data-ttu-id="6fb9f-116">文件室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-116">Room Management URL.</span></span> <span data-ttu-id="6fb9f-117">用于自定义聊天室管理的 URL。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-117">The URL used for custom chat room management.</span></span> <span data-ttu-id="6fb9f-118">该设置允许使用自定义聊天室管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-118">The setting allows the use of a custom room management solution.</span></span> 
    
## <a name="configure-persistent-chat-server-global-options"></a><span data-ttu-id="6fb9f-119">配置持久聊天服务器的全局选项</span><span class="sxs-lookup"><span data-stu-id="6fb9f-119">Configure Persistent Chat Server global options</span></span>

<span data-ttu-id="6fb9f-120">若要配置全局持久聊天服务器的选项：</span><span class="sxs-lookup"><span data-stu-id="6fb9f-120">To configure Persistent Chat Server global options:</span></span>
  
1. <span data-ttu-id="6fb9f-121">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-121">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6fb9f-122">从**开始**菜单中，选择 Skype 业务服务器的控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-122">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="6fb9f-123">在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天配置**”。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-123">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="6fb9f-124">在**聊天的持久性配置**页上，单击**新建**，然后单击**站点配置**。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-124">On the **Persistent Chat Configuration** page, click **New,** and then click **Site configuration**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6fb9f-125">如果您想要应用于网站中部署的所有持久聊天服务器池的配置，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-125">Choose this option if you want the configuration to be applied to all Persistent Chat Server pools deployed in the site.</span></span> <span data-ttu-id="6fb9f-126">如果您想要应用于一个特定的持久性聊天服务器池的配置，请单击**池配置**。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-126">Click **Pool Configuration** if you want the configuration to be applied to a specific Persistent Chat Server pool.</span></span>
  
5. <span data-ttu-id="6fb9f-127">在**选择网站**选择要持久聊天服务器站点配置为进行配置的站点。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-127">In **Select a Site**, select the site to be configured for the Persistent Chat Server site configuration.</span></span>
    
6. <span data-ttu-id="6fb9f-128">在“**新建持久聊天配置**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="6fb9f-128">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="6fb9f-p107">在“**名称**”中，指定新配置设置的名称。默认情况下，已存在站点名称。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-p107">In **Name**, specify a name for the new configuration settings. By default, the site name already exists.</span></span>
    
   - <span data-ttu-id="6fb9f-p108">在“**默认聊天历史记录**”中，定义首次请求时每个聊天室要处理的聊天消息的数目。默认情况下，此数目为 30。这是全局默认值，管理员可根据每个类别禁用聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-p108">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6fb9f-134">持久的聊天服务器将缓存在内存中，这些消息以便增加此数字，如果将缓存更多的消息。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-134">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="6fb9f-135">您始终可通过搜索来访问历史内容。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-135">You can always access historical content by search.</span></span> <span data-ttu-id="6fb9f-136">默认数目只确定您在连接到聊天室时最初看到的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-136">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="6fb9f-p110">在“**最大文件大小(KB)**”中，选择每条聊天历史记录的最大文件大小。默认情况下，此数目为 20 MB (20,000 KB)。这是可以上载到系统（已通过对应的“**类别**”设置为其启用文件上载）中任意聊天室的文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-p110">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="6fb9f-140">在“**参与者更新限制**”中，选择对参与者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-140">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="6fb9f-141">已连接的用户数达到此数量之前，持久的聊天服务器发送给所有参与者名单信息 （连接到一个聊天房间）。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-141">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="6fb9f-142">默认情况下，此数目为 75。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-142">By default, the number is 75.</span></span> <span data-ttu-id="6fb9f-143">该限制指示给定文件室之外持续聊天服务器停止将名单更新发送到连接的客户端，有关谁将出现在文件室中参与者的最大数目。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-143">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="6fb9f-144">（可选）。在**文件室管理 URL**，选择文件室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-144">(Optional.) In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="6fb9f-145">这是基于 Web 的自定义聊天室管理的 URL。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-145">This is the URL for a web-based custom room management.</span></span> <span data-ttu-id="6fb9f-146">如果您不需要自定义文件室管理，并且只需使用默认设置，请将此选项留空。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-146">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span> <span data-ttu-id="6fb9f-147">在设置该 URL 后，它将应用为内部和外部聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-147">After the URL is set, it is applied as both the internal and external room management URL.</span></span>
    
    <span data-ttu-id="6fb9f-148">如果您想自定义您的空间的创建经验，包括您的特定业务流程，可以生成一个自定义文件室管理解决方案通过持久聊天服务器软件开发工具包 (SDK)、 承载到某处，并在此处输入 URL。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-148">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="6fb9f-149">此 URL 将被发送给客户端，以便用户在尝试查看或创建聊天室时将被定向到您的自定义聊天室管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-149">This URL is sent down to the client, so that when a user tries to view or create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="6fb9f-150">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-150">Click **Commit**.</span></span>
    
## <a name="configure-options-for-a-specific-persistent-chat-server-pool"></a><span data-ttu-id="6fb9f-151">为一个特定的持久性聊天服务器池配置选项</span><span class="sxs-lookup"><span data-stu-id="6fb9f-151">Configure options for a specific Persistent Chat Server pool</span></span>

<span data-ttu-id="6fb9f-152">若要为特定的持久性聊天服务器池配置选项。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-152">To configure options for a specific Persistent Chat Server pool.</span></span>
  
1. <span data-ttu-id="6fb9f-153">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-153">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="6fb9f-154">从**开始**菜单中，业务服务器控制面板，选择 Skype 或打开浏览器窗口，然后再输入管理。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-154">From the **Start** menu, select the Skype for Business Server Control Panel, or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="6fb9f-155">在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天配置**”。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-155">In the left navigation bar, click **Persistent Chat**, and then click **Persistent Chat Configuration**.</span></span>
    
4. <span data-ttu-id="6fb9f-156">在“**持久聊天配置**”页上，单击“**新建**”，然后单击“**池配置**”。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-156">On the **Persistent Chat Configuration** page, click **New**, and then click **Pool configuration**.</span></span>
    
5. <span data-ttu-id="6fb9f-157">中**选择一个服务**，请选择与要配置持久聊天服务器池相关联的服务。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-157">In **Select a Service**, select the service associated with the Persistent Chat Server pool to be configured.</span></span>
    
6. <span data-ttu-id="6fb9f-158">在“**新建持久聊天配置**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="6fb9f-158">In **New Persistent Chat Configuration**, do the following:</span></span>
    
   - <span data-ttu-id="6fb9f-p114">在“**名称**”中，指定新配置设置的名称。默认情况下，已存在站点池名称。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-p114">In **Name**, specify a name for the new configuration settings. By default, the site pool name already exists.</span></span>
    
   - <span data-ttu-id="6fb9f-p115">在“**默认聊天历史记录**”中，定义首次请求时每个聊天室要处理的聊天消息的数目。默认情况下，此数目为 30。这是全局默认值，管理员可根据每个类别禁用聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-p115">In **Default chat history**, define the number of chat messages that will be processed for each room upon first request. By default, the number is 30. This is the global default, and administrators can disable chat history per category.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="6fb9f-164">持久的聊天服务器将缓存在内存中，这些消息以便增加此数字，如果将缓存更多的消息。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-164">Persistent Chat Server will cache these messages in memory, so if you increase this number, more messages will be cached.</span></span> <span data-ttu-id="6fb9f-165">您始终可通过搜索来访问历史内容。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-165">You can always access historical content by search.</span></span> <span data-ttu-id="6fb9f-166">默认数目只确定您在连接到聊天室时最初看到的最大消息数。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-166">The default number simply determines the maximum number of messages that you initially see when connecting to a chat room.</span></span> 
  
   - <span data-ttu-id="6fb9f-p117">在“**最大文件大小(KB)**”中，选择每条聊天历史记录的最大文件大小。默认情况下，此数目为 20 MB (20,000 KB)。这是可以上载到系统（已通过对应的“**类别**”设置为其启用文件上载）中任意聊天室的文件的最大大小。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-p117">In **Maximum file size (KB)**, select the maximum file size of each chat history. By default, the number is 20 MB (20,000 KB). This is the maximum size for a file that can be uploaded to any chat room in the system (for which file uploads are enabled by its corresponding **Category** setting).</span></span>
    
   - <span data-ttu-id="6fb9f-170">在“**参与者更新限制**”中，选择对参与者更新的限制。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-170">In **Participant update limit**, select the limit for participant updates.</span></span> <span data-ttu-id="6fb9f-171">已连接的用户数达到此数量之前，持久的聊天服务器发送给所有参与者名单信息 （连接到一个聊天房间）。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-171">Persistent Chat Server sends roster information (who is connected to a chat room) to all participants until the number of connected users reaches this number.</span></span> <span data-ttu-id="6fb9f-172">默认情况下，此数目为 75。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-172">By default, the number is 75.</span></span> <span data-ttu-id="6fb9f-173">该限制指示给定文件室之外持续聊天服务器停止将名单更新发送到连接的客户端，有关谁将出现在文件室中参与者的最大数目。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-173">This limit indicates the maximum number of participants in a given room beyond which Persistent Chat Server stops sending roster updates to connected clients about who is present in the room.</span></span>
    
   - <span data-ttu-id="6fb9f-174">在“**聊天室管理 URL**”中，选择聊天室管理 URL。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-174">In **Room management URL**, select the room management URL.</span></span> <span data-ttu-id="6fb9f-175">这是基于 Web 的聊天室管理部署的 URL。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-175">This is the URL for a web-based room management deployment.</span></span> <span data-ttu-id="6fb9f-176">如果您不需要自定义文件室管理，并且只需使用默认设置，请将此选项留空。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-176">If you don't need to customize room management, and you simply use the default setting, leave this option blank.</span></span>
    
    <span data-ttu-id="6fb9f-177">如果您想自定义您的空间的创建经验，包括您的特定业务流程，可以生成一个自定义文件室管理解决方案通过持久聊天服务器软件开发工具包 (SDK)、 承载到某处，并在此处输入 URL。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-177">If you want to customize your room creation experience and include your specific business workflow, you can build a custom room management solution by using the Persistent Chat Server Software Development Kit (SDK), host it somewhere, and put the URL here.</span></span> <span data-ttu-id="6fb9f-178">此 URL 将被发送给客户端，以便用户在尝试查看/创建聊天室时将被定向到您的自定义聊天室管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-178">This URL is sent down to the client so that when a user tries to view/create a room, he or she is directed to your custom room management solution.</span></span>
    
7. <span data-ttu-id="6fb9f-179">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="6fb9f-179">Click **Commit**.</span></span>
    

