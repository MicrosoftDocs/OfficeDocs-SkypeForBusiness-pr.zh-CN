---
title: 持久聊天类别
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatCategory
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6875d930-7502-4e47-bdb3-45eaeb065350
description: 持续聊天页面的类别部分可用于配置类别。 持久的聊天房间类别是组织聊天室的逻辑结构。 类别定义一组默认的访问控制列表 (ACL)，以便控制可以创建或加入聊天室的用户和用户组。 您还可以使用类别强制在组织中不同部门之间使用信息隔离墙。
ms.openlocfilehash: 24be7e342e5c87d355d577a05a7039872c0b2602
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-category"></a><span data-ttu-id="70302-106">持久聊天类别</span><span class="sxs-lookup"><span data-stu-id="70302-106">Persistent Chat Category</span></span>
 
<span data-ttu-id="70302-107">您可以使用“**持久聊天**”页的“**类别**”部分配置类别。</span><span class="sxs-lookup"><span data-stu-id="70302-107">You can use the **Category** section of the **Persistent Chat** page to configure categories.</span></span> <span data-ttu-id="70302-108">持久的聊天房间类别是组织聊天室的逻辑结构。</span><span class="sxs-lookup"><span data-stu-id="70302-108">A Persistent Chat room category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="70302-109">类别定义一组默认的访问控制列表 (ACL)，以便控制可以创建或加入聊天室的用户和用户组。</span><span class="sxs-lookup"><span data-stu-id="70302-109">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who may create or join the chat rooms.</span></span> <span data-ttu-id="70302-110">您还可以使用类别强制在组织中不同部门之间使用信息隔离墙。</span><span class="sxs-lookup"><span data-stu-id="70302-110">You can use categories enforce ethical walls between different subdivisions within their organizations.</span></span>
  
<span data-ttu-id="70302-111">聊天室类别可以包含聊天室，但不包含其他类别。</span><span class="sxs-lookup"><span data-stu-id="70302-111">Chat room categories may contain chat rooms, but not other categories.</span></span> <span data-ttu-id="70302-112">每个类别描述其内容和元数据，如_名称_和_说明_。</span><span class="sxs-lookup"><span data-stu-id="70302-112">Each category describes its contents with metadata, such as  _Name_ and _Description_.</span></span> <span data-ttu-id="70302-113">另外，类别具有属性可设置以控制属于它，聊天室的行为如聊天室允许_邀请_或_文件上载_，或者包含_聊天历史_。</span><span class="sxs-lookup"><span data-stu-id="70302-113">In addition, the category has properties which can be set to control the behavior of the chat rooms belonging to it, such as if the chat rooms allow  _Invitations_ or _File Uploads_, or contain  _Chat History_.</span></span>
  
<span data-ttu-id="70302-114">若要创建一个新类别，请参阅[在业务服务器 2015年的 Skype 的持久聊天服务器的管理类别](../../manage/persistent-chat/categories.md)。</span><span class="sxs-lookup"><span data-stu-id="70302-114">To create a new category, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/categories.md).</span></span> <span data-ttu-id="70302-115">如果您持续的聊天管理员，您可以通过使用控制面板或 Windows PowerShell cmdlet 创建类别。</span><span class="sxs-lookup"><span data-stu-id="70302-115">If you are a Persistent Chat Administrator, you can create categories by using the control panel or Windows PowerShell cmdlets.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="70302-116">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="70302-116">Tasks that you can perform</span></span>

<span data-ttu-id="70302-117">您可以在“**类别**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="70302-117">You can perform the following tasks on the **Category** page:</span></span>
  
- <span data-ttu-id="70302-118">创建或编辑新类别</span><span class="sxs-lookup"><span data-stu-id="70302-118">Create or edit a new category</span></span>
    
- <span data-ttu-id="70302-119">将聊天室从一个类别移动到另一个类别</span><span class="sxs-lookup"><span data-stu-id="70302-119">Move a chat room from one category to another</span></span>
    
- <span data-ttu-id="70302-120">删除聊天室或类别</span><span class="sxs-lookup"><span data-stu-id="70302-120">Delete a chat room or category</span></span>
    
## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="70302-121">配置聊天室的类别</span><span class="sxs-lookup"><span data-stu-id="70302-121">To configure categories for chat rooms</span></span>

1. <span data-ttu-id="70302-122">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="70302-122">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="70302-123">从**开始**菜单中，选择 Skype 业务服务器的控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="70302-123">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="70302-124">在左侧导航栏中，单击“**持久聊天**”，然后单击“**类别**”。</span><span class="sxs-lookup"><span data-stu-id="70302-124">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="70302-125">对于多个持久性聊天服务器池部署，从下拉列表中选择适当的池。</span><span class="sxs-lookup"><span data-stu-id="70302-125">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="70302-126">在“**类别**”页上，单击“**新建**”或“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="70302-126">On the **Category** page, click **New** or **Edit**.</span></span>
    
5. <span data-ttu-id="70302-127">中**选择一个服务**，请选择对应于持久的聊天服务器池需要创建类别的服务。</span><span class="sxs-lookup"><span data-stu-id="70302-127">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="70302-128">该服务是持久聊天服务器池持续聊天 （客户端） 用来标识该池类别属于。</span><span class="sxs-lookup"><span data-stu-id="70302-128">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="70302-129">类别可以属于一个持久聊天服务器池，并且无法移到另一个，或与另一个池共享。</span><span class="sxs-lookup"><span data-stu-id="70302-129">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>
    
6. <span data-ttu-id="70302-130">在“**新建类别**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="70302-130">In **New Category**, do the following:</span></span>
    
1. <span data-ttu-id="70302-131">在“**名称**”中，指定新聊天室类别的名称。</span><span class="sxs-lookup"><span data-stu-id="70302-131">In **Name**, specify a name for the new room category.</span></span>
    
2. <span data-ttu-id="70302-132">在“**描述**”中，提供有关聊天室类别（例如 Contoso 聊天室类别）的详细描述。</span><span class="sxs-lookup"><span data-stu-id="70302-132">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
3. <span data-ttu-id="70302-133">要控制是否为属于此类别的聊天室启用邀请，请选中或清除“**启用邀请**”复选框。</span><span class="sxs-lookup"><span data-stu-id="70302-133">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="70302-134">如果选中，则此类别的聊天室将打开或关闭邀请；如果清除，则不允许此类别的聊天室具有邀请。</span><span class="sxs-lookup"><span data-stu-id="70302-134">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="70302-135">如果一个房间上时将新成员添加到文件室的邀请，他或她将收到一条通知其持久聊天客户端中新建文件室。</span><span class="sxs-lookup"><span data-stu-id="70302-135">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
4. <span data-ttu-id="70302-p107">要控制属于此类别的聊天室中的文件上载，请选中或清除“**启用文件上载**”复选框。如果选中，该类别的聊天室可以启用或禁用文件上载；如果清除，则不允许该类别的聊天室执行文件上载操作。</span><span class="sxs-lookup"><span data-stu-id="70302-p107">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="70302-138">因为自定义应用程序或以前分组聊天客户端使用 Office 通信服务器 2007 R2 组聊天服务器或 Lync Server 2010 中，分组讨论，可以将文件张贴到房间，此设置是在服务器上强制执行。</span><span class="sxs-lookup"><span data-stu-id="70302-138">This setting is enforced on the server because custom applications or previous Group Chat clients that use Office Communications Server 2007 R2 Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="70302-139">Lync 2013 客户端没有文件上传/下载功能，因此如果您有一个纯 Lync 2013 部署或 Lync 2013 客户端，不可能在持久的聊天服务器的聊天房间文件投递。</span><span class="sxs-lookup"><span data-stu-id="70302-139">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span> 
  
5. <span data-ttu-id="70302-140">若要控制聊天历史记录，请选中或清除**启用聊天历史记录**复选框。</span><span class="sxs-lookup"><span data-stu-id="70302-140">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="70302-141">如果选中，则聊天室聊天内容将变成持久的；否则，将不会保留聊天消息。</span><span class="sxs-lookup"><span data-stu-id="70302-141">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="70302-142">如果启用了合规性，则将按合规性保存聊天室聊天内容，但用户无法访问较早的消息。</span><span class="sxs-lookup"><span data-stu-id="70302-142">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="70302-143">此选项可用于指定以进行实时地点对点协作不需要聊天历史记录，以保持房间。</span><span class="sxs-lookup"><span data-stu-id="70302-143">This option can be used for rooms designated for real-time, ad hoc collaborations that don't need chat history to be persisted.</span></span>
    
7. <span data-ttu-id="70302-144">在“**编辑类别**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="70302-144">In **Edit Category**, do the following:</span></span>
    
  - <span data-ttu-id="70302-145">在中的**成员资格**，**允许的成员**部分中，添加或删除用户，并允许被添加为成员的聊天室其他 Active Directory 域服务主体 （用户、 通讯组、 组织单位，等）属于该类别。</span><span class="sxs-lookup"><span data-stu-id="70302-145">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="70302-146">类别允许的主体可搜索此类别的聊天室（除非隐藏了聊天室，在这种情况下，仅聊天室的成员可在此目录中搜索聊天室）。</span><span class="sxs-lookup"><span data-stu-id="70302-146">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
  - <span data-ttu-id="70302-147">在中的**成员资格**，**拒绝的成员**部分中，添加或删除用户和其他 Active Directory 主体与被拒绝从文件室的成员。</span><span class="sxs-lookup"><span data-stu-id="70302-147">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
  - <span data-ttu-id="70302-148">在中的**成员资格**，**创建者**部分中，添加或删除用户和其他 Active Directory 主体与创建者的类别相关联。</span><span class="sxs-lookup"><span data-stu-id="70302-148">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="70302-149">创建者是有权创建聊天室并指定聊天室管理员和成员的用户。</span><span class="sxs-lookup"><span data-stu-id="70302-149">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>
    
8. <span data-ttu-id="70302-150">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="70302-150">Click **Commit**.</span></span>
    
### 

<span data-ttu-id="70302-151">有关持久聊天服务器特性和功能，详细信息请参阅[规划业务服务器 2015年的 Skype 的持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、[业务服务器 2015 Skype 在部署持续聊天服务器](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)和[管理持续聊天服务器在 Skype 业务服务器 2015年](../../manage/persistent-chat/persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="70302-151">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

