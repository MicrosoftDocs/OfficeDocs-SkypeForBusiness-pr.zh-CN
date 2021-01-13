---
title: 持久聊天类别
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
- ms.lync.lscp.PersistentChatCategory
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6875d930-7502-4e47-bdb3-45eaeb065350
description: 您可以使用持久聊天页面的"类别"部分来配置类别。 持久聊天室类别是组织聊天室的逻辑结构。 类别定义一组默认的访问控制列表 (ACL)，以便控制可以创建或加入聊天室的用户和用户组。 您还可以使用类别强制在组织中不同部门之间使用信息隔离墙。
ms.openlocfilehash: f7718a5d6cc92c0036f28843d21c4c349c0bc38d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803742"
---
# <a name="persistent-chat-category"></a><span data-ttu-id="04f11-106">持久聊天类别</span><span class="sxs-lookup"><span data-stu-id="04f11-106">Persistent Chat Category</span></span>
 
<span data-ttu-id="04f11-107">您可以使用 **持久聊天页面** 的"类别 **"** 部分来配置类别。</span><span class="sxs-lookup"><span data-stu-id="04f11-107">You can use the **Category** section of the **Persistent Chat** page to configure categories.</span></span> <span data-ttu-id="04f11-108">持久聊天室类别是组织聊天室的逻辑结构。</span><span class="sxs-lookup"><span data-stu-id="04f11-108">A Persistent Chat room category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="04f11-109">类别定义一组默认的访问控制列表 (ACL)，以便控制可以创建或加入聊天室的用户和用户组。</span><span class="sxs-lookup"><span data-stu-id="04f11-109">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who may create or join the chat rooms.</span></span> <span data-ttu-id="04f11-110">您还可以使用类别强制在组织中不同部门之间使用信息隔离墙。</span><span class="sxs-lookup"><span data-stu-id="04f11-110">You can use categories enforce ethical walls between different subdivisions within their organizations.</span></span>
  
<span data-ttu-id="04f11-111">聊天室类别可以包含聊天室，但不包含其他类别。</span><span class="sxs-lookup"><span data-stu-id="04f11-111">Chat room categories may contain chat rooms, but not other categories.</span></span> <span data-ttu-id="04f11-112">每个类别都使用元数据（如名称和说明 _）描述__其内容_。</span><span class="sxs-lookup"><span data-stu-id="04f11-112">Each category describes its contents with metadata, such as  _Name_ and _Description_.</span></span> <span data-ttu-id="04f11-113">此外，类别具有可设置以控制属于该类别的聊天室的行为的属性，例如聊天室是否允许邀请或文件上载，或包含 _聊天历史记录_。  </span><span class="sxs-lookup"><span data-stu-id="04f11-113">In addition, the category has properties which can be set to control the behavior of the chat rooms belonging to it, such as if the chat rooms allow  _Invitations_ or _File Uploads_, or contain  _Chat History_.</span></span>
  
<span data-ttu-id="04f11-114">若要创建新类别，请参阅"在 [Skype for Business Server 2015](../../manage/persistent-chat/categories.md)中管理持久聊天服务器中的类别"。</span><span class="sxs-lookup"><span data-stu-id="04f11-114">To create a new category, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/categories.md).</span></span> <span data-ttu-id="04f11-115">如果您是持久聊天管理员，可以使用控制面板或 cmdlet 创建Windows PowerShell类别。</span><span class="sxs-lookup"><span data-stu-id="04f11-115">If you are a Persistent Chat Administrator, you can create categories by using the control panel or Windows PowerShell cmdlets.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="04f11-116">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="04f11-116">Tasks that you can perform</span></span>

<span data-ttu-id="04f11-117">您可以在“类别”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="04f11-117">You can perform the following tasks on the **Category** page:</span></span>
  
- <span data-ttu-id="04f11-118">创建或编辑新类别</span><span class="sxs-lookup"><span data-stu-id="04f11-118">Create or edit a new category</span></span>
    
- <span data-ttu-id="04f11-119">将聊天室从一个类别移动到另一个类别</span><span class="sxs-lookup"><span data-stu-id="04f11-119">Move a chat room from one category to another</span></span>
    
- <span data-ttu-id="04f11-120">删除聊天室或类别</span><span class="sxs-lookup"><span data-stu-id="04f11-120">Delete a chat room or category</span></span>
    
## <a name="to-configure-categories-for-chat-rooms"></a><span data-ttu-id="04f11-121">配置聊天室的类别</span><span class="sxs-lookup"><span data-stu-id="04f11-121">To configure categories for chat rooms</span></span>

1. <span data-ttu-id="04f11-122">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录到您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="04f11-122">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="04f11-123">从 **"开始** "菜单中，选择 Skype for Business Server 控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="04f11-123">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="04f11-124">在左侧导航栏中，单击“持久聊天”，然后单击“类别”。</span><span class="sxs-lookup"><span data-stu-id="04f11-124">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="04f11-125">对于多个持久聊天服务器池部署，请从下拉列表中选择相应的池。</span><span class="sxs-lookup"><span data-stu-id="04f11-125">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="04f11-126">在“类别”页上，单击“新建”或“编辑”。</span><span class="sxs-lookup"><span data-stu-id="04f11-126">On the **Category** page, click **New** or **Edit**.</span></span>
    
5. <span data-ttu-id="04f11-127">在 **"选择服务**"中，选择与需要创建类别的持久聊天服务器池对应的服务。</span><span class="sxs-lookup"><span data-stu-id="04f11-127">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="04f11-128">该服务是持久聊天服务器池，持久聊天 (客户端) 该类别所属的池。</span><span class="sxs-lookup"><span data-stu-id="04f11-128">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="04f11-129">类别只能属于一个持久聊天服务器池，并且不能移动到另一个池，也不能与另一个池共享。</span><span class="sxs-lookup"><span data-stu-id="04f11-129">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>
    
6. <span data-ttu-id="04f11-130">在“新建类别”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="04f11-130">In **New Category**, do the following:</span></span>
    
7. <span data-ttu-id="04f11-131">在“名称”中，指定新聊天室类别的名称。</span><span class="sxs-lookup"><span data-stu-id="04f11-131">In **Name**, specify a name for the new room category.</span></span>
    
8. <span data-ttu-id="04f11-132">在“描述”中，提供有关聊天室类别（例如 Contoso 聊天室类别）的详细描述。</span><span class="sxs-lookup"><span data-stu-id="04f11-132">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
9. <span data-ttu-id="04f11-133">若要控制是否能为属于此类别的聊天室启用邀请，请选中或清除“启用邀请”复选框。</span><span class="sxs-lookup"><span data-stu-id="04f11-133">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="04f11-134">如果选中，此类别中的聊天室将可以打开或关闭邀请；如果清除，则不允许该类别中的聊天室执行邀请操作。</span><span class="sxs-lookup"><span data-stu-id="04f11-134">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="04f11-135">如果聊天室有邀请，当向聊天室中添加一名新成员时，他（她）会收到其持久聊天客户端中新聊天室的通知。</span><span class="sxs-lookup"><span data-stu-id="04f11-135">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
10. <span data-ttu-id="04f11-p107">若要控制属于此类别的聊天室中的文件上载，请选中或清除“启用文件上载”复选框。如果选中，该类别的聊天室可以启用或禁用文件上载；如果清除，则不允许该类别的聊天室执行文件上载操作。</span><span class="sxs-lookup"><span data-stu-id="04f11-p107">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
    
     > [!IMPORTANT]
     > <span data-ttu-id="04f11-138">在服务器上强制执行此设置，因为使用 Office Communications Server 2007 R2 群聊服务器或 Lync Server 2010 的自定义应用程序或以前的群聊客户端可以将文件张贴到聊天室。</span><span class="sxs-lookup"><span data-stu-id="04f11-138">This setting is enforced on the server because custom applications or previous Group Chat clients that use Office Communications Server 2007 R2 Group Chat Server or Lync Server 2010, Group Chat can post files to a room.</span></span> <span data-ttu-id="04f11-139">Lync 2013 客户端没有文件上载/下载功能，因此，如果您有纯 Lync 2013 部署或 Lync 2013 客户端，则不能将文件张贴在持久聊天服务器聊天室中。</span><span class="sxs-lookup"><span data-stu-id="04f11-139">The Lync 2013 client does not have file upload/download capability, so if you have a pure Lync 2013 deployment or Lync 2013 client, it is not possible to post files in a Persistent Chat Server chat room.</span></span> 
  
11. <span data-ttu-id="04f11-140">若要控制聊天历史记录，请选中或清除" **启用聊天历史记录"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="04f11-140">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="04f11-141">如果选中，聊天室聊天内容将是持久的；否则，聊天消息将不是持久的。</span><span class="sxs-lookup"><span data-stu-id="04f11-141">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="04f11-142">如果启用了合规性，将合规保存聊天室聊天内容，但用户无法访问较早的消息。</span><span class="sxs-lookup"><span data-stu-id="04f11-142">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="04f11-143">此选项可用于指定为不需要保留聊天历史记录实时临时协作的聊天室。</span><span class="sxs-lookup"><span data-stu-id="04f11-143">This option can be used for rooms designated for real-time, ad hoc collaborations that don't need chat history to be persisted.</span></span>
    
12. <span data-ttu-id="04f11-144">在“编辑类别”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="04f11-144">In **Edit Category**, do the following:</span></span>
    
    - <span data-ttu-id="04f11-145">在 **"** 成员身份"中，在"允许的成员"部分，添加或删除用户和其他 Active Directory 域服务主体 (用户、通讯组、组织单位等) 允许添加为属于该类别的聊天室的成员。</span><span class="sxs-lookup"><span data-stu-id="04f11-145">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="04f11-146">类别允许的主体可以搜索该类别中的聊天室（除非聊天室处于隐藏状态，在这种情况下只有聊天室的成员才能在目录中搜索它）。</span><span class="sxs-lookup"><span data-stu-id="04f11-146">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
    - <span data-ttu-id="04f11-147">在 **"成员身份**"中的"拒绝的成员"部分，添加或删除与聊天室中被拒绝的成员关联的用户和其他 Active Directory 主体。</span><span class="sxs-lookup"><span data-stu-id="04f11-147">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
    - <span data-ttu-id="04f11-148">在 **"成员身份**"中的" **创建者** "部分，添加或删除与类别的创建者关联的用户和其他 Active Directory 主体。</span><span class="sxs-lookup"><span data-stu-id="04f11-148">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="04f11-149">创建者是有权创建聊天室并指定聊天室管理员和成员的用户。</span><span class="sxs-lookup"><span data-stu-id="04f11-149">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>
    
13. <span data-ttu-id="04f11-150">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="04f11-150">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="04f11-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="04f11-151">See also</span></span>

<span data-ttu-id="04f11-152">有关持久聊天服务器特性和功能的详细信息，请参阅规划 [Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)中的持久聊天服务器、在 Skype for Business Server [2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)中部署持久聊天服务器以及管理 [Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md)中的持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="04f11-152">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

