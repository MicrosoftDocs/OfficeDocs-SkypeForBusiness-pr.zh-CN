---
title: 持久聊天类别主页
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
- ms.lync.lscp.PersistentChatCategoryMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b71c6e6f-681c-4230-954d-3e95ab64ca00
description: 您可以使用“持久聊天”页的“类别”部分配置类别。 持久的聊天室类别是用于组织聊天室的逻辑结构。 类别定义一组默认的访问控制列表 (ACL)，以便控制可以创建或加入聊天室的用户和用户组。 您还可以使用类别强制在组织中不同部门之间使用信息隔离墙。
ms.openlocfilehash: 939686f92505e8b1fd51c6e96f8b126438003d84
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41822555"
---
# <a name="persistent-chat-category-main-page"></a><span data-ttu-id="90465-106">持久聊天类别主页</span><span class="sxs-lookup"><span data-stu-id="90465-106">Persistent Chat Category Main Page</span></span>
 
<span data-ttu-id="90465-107">您可以使用“**持久聊天**”页的“**类别**”部分配置类别。</span><span class="sxs-lookup"><span data-stu-id="90465-107">You can use the **Category** section of the **Persistent Chat** page to configure categories.</span></span> <span data-ttu-id="90465-108">持久的聊天室类别是用于组织聊天室的逻辑结构。</span><span class="sxs-lookup"><span data-stu-id="90465-108">A Persistent Chat room category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="90465-109">类别定义一组默认的访问控制列表 (ACL)，以便控制可以创建或加入聊天室的用户和用户组。</span><span class="sxs-lookup"><span data-stu-id="90465-109">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who may create or join the chat rooms.</span></span> <span data-ttu-id="90465-110">您还可以使用类别强制在组织中不同部门之间使用信息隔离墙。</span><span class="sxs-lookup"><span data-stu-id="90465-110">You can use categories enforce ethical walls between different subdivisions within their organizations.</span></span>
  
<span data-ttu-id="90465-111">聊天室类别可以包含聊天室，但不包含其他类别。</span><span class="sxs-lookup"><span data-stu-id="90465-111">Chat room categories may contain chat rooms, but not other categories.</span></span> <span data-ttu-id="90465-112">每个类别都描述了其内容和元数据，如_名称_和_说明_。</span><span class="sxs-lookup"><span data-stu-id="90465-112">Each category describes its contents with metadata, such as  _Name_ and _Description_.</span></span> <span data-ttu-id="90465-113">此外，类别具有可设置的属性，以控制属于它的聊天室的行为，例如，如果聊天室允许_邀请_或_文件上载_，或者包含_聊天历史记录_。</span><span class="sxs-lookup"><span data-stu-id="90465-113">In addition, the category has properties which can be set to control the behavior of the chat rooms belonging to it, such as if the chat rooms allow  _Invitations_ or _File Uploads_, or contain  _Chat History_.</span></span>
  
<span data-ttu-id="90465-114">若要创建新类别，请参阅[在 Skype for Business server 2015 中管理持久聊天服务器](../../manage/persistent-chat/categories.md)中的类别。</span><span class="sxs-lookup"><span data-stu-id="90465-114">To create a new category, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/categories.md).</span></span> <span data-ttu-id="90465-115">如果您是持久的聊天管理员，则可以使用控制面板或 Windows PowerShell cmdlet 创建类别。</span><span class="sxs-lookup"><span data-stu-id="90465-115">If you are a Persistent Chat Administrator, you can create categories by using the control panel or Windows PowerShell cmdlets.</span></span>
  
## <a name="tasks-that-you-can-perform"></a><span data-ttu-id="90465-116">可执行的任务</span><span class="sxs-lookup"><span data-stu-id="90465-116">Tasks that you can perform</span></span>

<span data-ttu-id="90465-117">您可以在“**类别**”页上执行以下任务：</span><span class="sxs-lookup"><span data-stu-id="90465-117">You can perform the following tasks on the **Category** page:</span></span>
  
- <span data-ttu-id="90465-118">创建或编辑新类别</span><span class="sxs-lookup"><span data-stu-id="90465-118">Create or edit a new category</span></span>
    
- <span data-ttu-id="90465-119">将聊天室从一个类别移动到另一个类别</span><span class="sxs-lookup"><span data-stu-id="90465-119">Move a chat room from one category to another</span></span>
    
- <span data-ttu-id="90465-120">删除聊天室或类别</span><span class="sxs-lookup"><span data-stu-id="90465-120">Delete a chat room or category</span></span>
    
## <a name="to-configure-categories-for-persistent-chat-rooms"></a><span data-ttu-id="90465-121">为永久聊天室配置类别</span><span class="sxs-lookup"><span data-stu-id="90465-121">To configure categories for Persistent Chat rooms</span></span>

1. <span data-ttu-id="90465-122">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="90465-122">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="90465-123">从 "**开始**" 菜单中，选择 "Skype For business 服务器" 控制面板或打开一个浏览器窗口，然后输入管理员 URL。</span><span class="sxs-lookup"><span data-stu-id="90465-123">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span> <span data-ttu-id="90465-124">.</span><span class="sxs-lookup"><span data-stu-id="90465-124">.</span></span>
    
3. <span data-ttu-id="90465-125">在左侧导航栏中，单击“**持久聊天**”，然后单击“**类别**”。</span><span class="sxs-lookup"><span data-stu-id="90465-125">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="90465-126">对于多个持久聊天服务器池部署，从下拉列表中选择相应的池。</span><span class="sxs-lookup"><span data-stu-id="90465-126">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="90465-127">在“**类别**”页上，单击“**新建**”或“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="90465-127">On the **Category** page, click **New** or **Edit**.</span></span>
    
5. <span data-ttu-id="90465-128">在 "**选择服务**" 中，选择与需要在其中创建类别的持久聊天服务器池对应的服务。</span><span class="sxs-lookup"><span data-stu-id="90465-128">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="90465-129">该服务是持久聊天服务器池，永久聊天（客户端）使用它标识类别所属的池。</span><span class="sxs-lookup"><span data-stu-id="90465-129">The service is the Persistent Chat Server pool that the Persistent Chat (client) uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="90465-130">一个类别只能属于一个持久聊天服务器池，不能移到另一个，或与另一个池共享。</span><span class="sxs-lookup"><span data-stu-id="90465-130">A category can belong to only one Persistent Chat Server pool, and cannot be moved to another one, or shared with another pool.</span></span>
    
6. <span data-ttu-id="90465-131">在“**新建类别**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="90465-131">In **New Category**, do the following:</span></span>
    
7. <span data-ttu-id="90465-132">在“**名称**”中，指定新聊天室类别的名称。</span><span class="sxs-lookup"><span data-stu-id="90465-132">In **Name**, specify a name for the new room category.</span></span>
    
8. <span data-ttu-id="90465-133">在“**描述**”中，提供有关聊天室类别（例如 Contoso 聊天室类别）的详细描述。</span><span class="sxs-lookup"><span data-stu-id="90465-133">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
9. <span data-ttu-id="90465-134">要控制是否为属于此类别的聊天室启用邀请，请选中或清除“**启用邀请**”复选框。</span><span class="sxs-lookup"><span data-stu-id="90465-134">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="90465-135">如果选中，则此类别的聊天室将打开或关闭邀请；如果清除，则不允许此类别的聊天室具有邀请。</span><span class="sxs-lookup"><span data-stu-id="90465-135">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="90465-136">如果会议室有邀请，则在将新成员添加到聊天室时，他或她将收到新聊天室在其持久聊天客户端中的通知。</span><span class="sxs-lookup"><span data-stu-id="90465-136">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
10. <span data-ttu-id="90465-p108">要控制属于此类别的聊天室中的文件上载，请选中或清除“**启用文件上载**”复选框。如果选中，该类别的聊天室可以启用或禁用文件上载；如果清除，则不允许该类别的聊天室执行文件上载操作。</span><span class="sxs-lookup"><span data-stu-id="90465-p108">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
    
11. <span data-ttu-id="90465-139">若要控制聊天历史记录，请选中或清除 "**启用聊天历史记录**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="90465-139">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="90465-140">如果选中，则聊天室聊天内容将变成持久的；否则，将不会保留聊天消息。</span><span class="sxs-lookup"><span data-stu-id="90465-140">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="90465-141">如果启用了合规性，则将按合规性保存聊天室聊天内容，但用户无法访问较早的消息。</span><span class="sxs-lookup"><span data-stu-id="90465-141">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="90465-142">此选项可用于为不需要保留聊天历史记录的实时、临时协作的会议室指定的会议室。</span><span class="sxs-lookup"><span data-stu-id="90465-142">This option can be used for rooms designated for real-time, ad hoc collaborations that don't need chat history to be persisted.</span></span>
    
12. <span data-ttu-id="90465-143">在“**编辑类别**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="90465-143">In **Edit Category**, do the following:</span></span>
    
    - <span data-ttu-id="90465-144">在 "允许的成员" 部分**中，在**"**允许的成员**" 部分中，添加或删除允许添加为属于该类别的聊天室成员的用户和其他 Active Directory 域服务主体（用户、通讯组、组织单位等）。</span><span class="sxs-lookup"><span data-stu-id="90465-144">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="90465-145">类别允许的主体可搜索此类别的聊天室（除非隐藏了聊天室，在这种情况下，仅聊天室的成员可在此目录中搜索聊天室）。</span><span class="sxs-lookup"><span data-stu-id="90465-145">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
    - <span data-ttu-id="90465-146">在 "**拒绝成员**" 部分**中，在**"拒绝的成员" 部分中，添加或删除与从聊天室拒绝的成员关联的用户和其他 Active Directory 主体。</span><span class="sxs-lookup"><span data-stu-id="90465-146">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
    - <span data-ttu-id="90465-147">在 "**成员资格**" 部分中，在 "**创建者**" 部分中，添加或删除与类别的 "创建者" 关联的用户和其他 Active Directory 主体。</span><span class="sxs-lookup"><span data-stu-id="90465-147">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="90465-148">创建者是有权创建聊天室并指定聊天室管理员和成员的用户。</span><span class="sxs-lookup"><span data-stu-id="90465-148">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>
    
13. <span data-ttu-id="90465-149">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="90465-149">Click **Commit**.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="90465-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="90465-150">See also</span></span>

<span data-ttu-id="90465-151">有关持久聊天服务器功能和功能的详细信息，请参阅在 skype for business [server 2015 中规划持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、在 skype For business [server 2015 中部署持久](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)聊天服务器以及[在 skype For Business Server 2015 中管理持久聊天服务器](../../manage/persistent-chat/persistent-chat.md)。</span><span class="sxs-lookup"><span data-stu-id="90465-151">For details about Persistent Chat Server features and capabilities, see [Plan for Persistent Chat Server in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md), [Deploy Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md), and [Manage Persistent Chat Server in Skype for Business Server 2015](../../manage/persistent-chat/persistent-chat.md).</span></span>
  

