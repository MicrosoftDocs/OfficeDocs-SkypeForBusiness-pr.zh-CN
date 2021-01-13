---
title: 在 Skype for Business Server 2015 中管理持久聊天服务器中的类别
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: 摘要：了解如何在 Skype for Business Server 2015 中管理持久聊天服务器类别。
ms.openlocfilehash: 648629e42994c59f5d6ba5ee5592729f4dff0bbe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815122"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="4feac-103">在 Skype for Business Server 2015 中管理持久聊天服务器中的类别</span><span class="sxs-lookup"><span data-stu-id="4feac-103">Manage categories in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4feac-104">**摘要：** 了解如何在 Skype for Business Server 2015 中管理持久聊天服务器类别。</span><span class="sxs-lookup"><span data-stu-id="4feac-104">**Summary:** Learn how to manage Persistent Chat Server categories in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="4feac-105">类别是组织聊天室的逻辑结构。</span><span class="sxs-lookup"><span data-stu-id="4feac-105">A category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="4feac-106">类别定义一组默认的访问控制列表 (ACL) 用于控制可以创建或加入聊天室的用户和用户组。</span><span class="sxs-lookup"><span data-stu-id="4feac-106">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who can create or join the chat rooms.</span></span> <span data-ttu-id="4feac-107">聊天室类别包含聊天室，但不包含其他类别。</span><span class="sxs-lookup"><span data-stu-id="4feac-107">Chat room categories contain chat rooms, but not other categories.</span></span> <span data-ttu-id="4feac-108">每个类别使用名称 和描述 等元数据描述其内容。</span><span class="sxs-lookup"><span data-stu-id="4feac-108">Each category describes its contents with metadata, such as Name and Description.</span></span> <span data-ttu-id="4feac-109">类别具有可设置以控制属于该类别的聊天室的行为的属性;例如，聊天室是否允许邀请或文件上载，或包含聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="4feac-109">The category has properties that can be set to control the behavior of the chat rooms belonging to it; for example, whether the chat rooms allow Invitations or File Uploads, or contain Chat History.</span></span> 
  
<span data-ttu-id="4feac-110">正确使用类别可更轻松地创建和管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="4feac-110">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="4feac-111">作为持久聊天服务器管理员，您可以为每个类别定义 AllowedMembers 和 Creators，还可以定义将应用于类别中创建的所有聊天室的默认聊天室设置和行为。</span><span class="sxs-lookup"><span data-stu-id="4feac-111">As a Persistent Chat Server administrator, you can define AllowedMembers and Creators for each category, and also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="4feac-112">例如，如果将类别的 AllowedMembers 设置为 contoso.com，您可以将 Contoso 的任何组或用户作为成员添加到该类别中的聊天室。</span><span class="sxs-lookup"><span data-stu-id="4feac-112">For example, if you set the category's AllowedMembers to contoso.com, you can add any group or user at Contoso as a member to chat rooms in that category.</span></span> <span data-ttu-id="4feac-113">如果将类别中的"允许的成员"设置为"销售"，则只有此通讯组列表中的组和用户才能作为成员添加到该类别中的聊天室。</span><span class="sxs-lookup"><span data-stu-id="4feac-113">If you set the Allowed Members on a category to Sales, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="4feac-114">Creators 属性使您能够控制可在该类别中创建聊天室的人。</span><span class="sxs-lookup"><span data-stu-id="4feac-114">The Creators property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="4feac-115">创建聊天室后，可以将 AllowedMembers 组中的任何人指定为对聊天室执行持续管理 (例如，成员身份更改和审批) 。</span><span class="sxs-lookup"><span data-stu-id="4feac-115">After the chat room is created, anyone from the AllowedMembers group can be designated as a Manager for ongoing management operations on the rooms (for example, membership changes and approval).</span></span>
  
<span data-ttu-id="4feac-116">为类别定义 AllowedMembers 和 Creators 有以下好处：</span><span class="sxs-lookup"><span data-stu-id="4feac-116">Defining AllowedMembers and Creators for a category has the following benefits:</span></span>
  
- <span data-ttu-id="4feac-p103">该类别中的所有聊天室都绑定了在类别级别设置的限制。您可以使用此限制，根据业务需求和访问策略隔离聊天室。</span><span class="sxs-lookup"><span data-stu-id="4feac-p103">All chat rooms in this category are bound by the restrictions set at the category level. You can use this to segregate chat rooms based on business need and access policies.</span></span>
    
- <span data-ttu-id="4feac-119">Creators 列表中的用户可在该类别中创建新聊天室。</span><span class="sxs-lookup"><span data-stu-id="4feac-119">A user who is in the Creators list can create new chat rooms in that category.</span></span> <span data-ttu-id="4feac-120">如果要实现一个系统，在该系统中，组织中有限数量的人员可以创建聊天室，此控制可用于满足该要求。</span><span class="sxs-lookup"><span data-stu-id="4feac-120">If you want to implement a system where a restricted number of personnel in the organization can create chat rooms this control can be used to meet that requirements.</span></span> 
    
<span data-ttu-id="4feac-121">标识为 (创建者的用户、组织单位) 和用户组是唯一被允许在类别中创建聊天室的个人和组。</span><span class="sxs-lookup"><span data-stu-id="4feac-121">Users, Organization Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="4feac-122">创建类别后，可以从类别的 AllowedMembers 列表中选择用户、US 和用户组作为聊天室管理员和成员来管理和参与聊天室。</span><span class="sxs-lookup"><span data-stu-id="4feac-122">After the category is created, you can choose users, OUs, and user groups from the category's AllowedMembers list as chat room managers and members to manage and participate in the room.</span></span> 
  
<span data-ttu-id="4feac-123">在配置类别之前，请务必阅读 [Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)中的持久聊天类别、聊天室和用户角色。</span><span class="sxs-lookup"><span data-stu-id="4feac-123">Before you configure categories, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md).</span></span>
  
<span data-ttu-id="4feac-124">可以使用控制面板或 cmdlet 配置和管理Windows PowerShell类别。</span><span class="sxs-lookup"><span data-stu-id="4feac-124">You can configure and manage categories by using the Control Panel or by using Windows PowerShell cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="4feac-125">持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="4feac-125">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="4feac-126">Teams 中也提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="4feac-126">The same functionality is available in Teams.</span></span> <span data-ttu-id="4feac-127">有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。</span><span class="sxs-lookup"><span data-stu-id="4feac-127">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="4feac-128">如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="4feac-128">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="configure-categories-by-using-the-control-panel"></a><span data-ttu-id="4feac-129">使用控制面板配置类别</span><span class="sxs-lookup"><span data-stu-id="4feac-129">Configure categories by using the Control Panel</span></span>

1. <span data-ttu-id="4feac-130">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录到您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="4feac-130">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4feac-131">从 **"开始** "菜单中，选择 Skype for Business Server 控制面板或打开浏览器窗口，然后输入管理 URL。</span><span class="sxs-lookup"><span data-stu-id="4feac-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="4feac-132">在左侧导航栏中，单击“持久聊天”，然后单击“类别”。</span><span class="sxs-lookup"><span data-stu-id="4feac-132">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="4feac-133">对于多个持久聊天服务器池部署，请从下拉列表中选择相应的池。</span><span class="sxs-lookup"><span data-stu-id="4feac-133">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="4feac-134">在“类别”页上，单击“新建”或“编辑”。</span><span class="sxs-lookup"><span data-stu-id="4feac-134">On the **Category** page, click **New** or **Edit**.</span></span>
    
5. <span data-ttu-id="4feac-135">在 **"选择服务**"中，选择与需要创建类别的持久聊天服务器池对应的服务。</span><span class="sxs-lookup"><span data-stu-id="4feac-135">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="4feac-136">该服务是持久聊天客户端用来标识类别所属的池的持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="4feac-136">The service is the Persistent Chat Server pool that the Persistent Chat client uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="4feac-137">类别只能属于一个持久聊天服务器池，并且不能移动到另一个池或与另一个池共享。</span><span class="sxs-lookup"><span data-stu-id="4feac-137">A category can belong to only one Persistent Chat Server pool, and cannot be moved to, or shared with, another pool.</span></span>
    
6. <span data-ttu-id="4feac-138">在“新建类别”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="4feac-138">In **New Category**, do the following:</span></span>
    
   - <span data-ttu-id="4feac-139">在“名称”中，指定新聊天室类别的名称。</span><span class="sxs-lookup"><span data-stu-id="4feac-139">In **Name**, specify a name for the new room category.</span></span>
    
   - <span data-ttu-id="4feac-140">在“描述”中，提供有关聊天室类别（例如 Contoso 聊天室类别）的详细描述。</span><span class="sxs-lookup"><span data-stu-id="4feac-140">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
   - <span data-ttu-id="4feac-141">若要控制是否能为属于此类别的聊天室启用邀请，请选中或清除“启用邀请”复选框。</span><span class="sxs-lookup"><span data-stu-id="4feac-141">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="4feac-142">如果选中，此类别中的聊天室将可以打开或关闭邀请；如果清除，则不允许该类别中的聊天室执行邀请操作。</span><span class="sxs-lookup"><span data-stu-id="4feac-142">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="4feac-143">如果聊天室有邀请，当向聊天室中添加一名新成员时，他（她）会收到其持久聊天客户端中新聊天室的通知。</span><span class="sxs-lookup"><span data-stu-id="4feac-143">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
   - <span data-ttu-id="4feac-p109">若要控制属于此类别的聊天室中的文件上载，请选中或清除“启用文件上载”复选框。如果选中，该类别的聊天室可以启用或禁用文件上载；如果清除，则不允许该类别的聊天室执行文件上载操作。</span><span class="sxs-lookup"><span data-stu-id="4feac-p109">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
    
   - <span data-ttu-id="4feac-146">若要控制聊天历史记录，请选中或清除" **启用聊天历史记录"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="4feac-146">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="4feac-147">如果选中，聊天室聊天内容将是持久的；否则，聊天消息将不是持久的。</span><span class="sxs-lookup"><span data-stu-id="4feac-147">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="4feac-148">如果启用了合规性，将合规保存聊天室聊天内容，但用户无法访问较早的消息。</span><span class="sxs-lookup"><span data-stu-id="4feac-148">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="4feac-149">此选项可用于指定为不需要保留聊天历史记录实时临时协作的聊天室。</span><span class="sxs-lookup"><span data-stu-id="4feac-149">This option can be used for rooms designated for real-time, ad hoc collaborations that don't need chat history to be persisted.</span></span>
    
7. <span data-ttu-id="4feac-150">在“编辑类别”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="4feac-150">In **Edit Category**, do the following:</span></span>
    
   - <span data-ttu-id="4feac-151">在 **"** 成员身份"中，在"允许的成员"部分，添加或删除用户和其他 Active Directory 域服务主体 (用户、通讯组、组织单位等) 允许添加为属于该类别的聊天室的成员。</span><span class="sxs-lookup"><span data-stu-id="4feac-151">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="4feac-152">类别允许的主体可以搜索该类别中的聊天室（除非聊天室处于隐藏状态，在这种情况下只有聊天室的成员才能在目录中搜索它）。</span><span class="sxs-lookup"><span data-stu-id="4feac-152">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
   - <span data-ttu-id="4feac-153">在 **"成员身份**"中的"拒绝的成员"部分，添加或删除与聊天室中被拒绝的成员关联的用户和其他 Active Directory 主体。</span><span class="sxs-lookup"><span data-stu-id="4feac-153">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
   - <span data-ttu-id="4feac-154">在 **"成员身份**"中的" **创建者** "部分，添加或删除与类别的创建者关联的用户和其他 Active Directory 主体。</span><span class="sxs-lookup"><span data-stu-id="4feac-154">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="4feac-155">创建者是有权创建聊天室并指定聊天室管理员和成员的用户。</span><span class="sxs-lookup"><span data-stu-id="4feac-155">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>
    
8. <span data-ttu-id="4feac-156">单击“提交”。</span><span class="sxs-lookup"><span data-stu-id="4feac-156">Click **Commit**.</span></span>
    
## <a name="configure-categories-by-using-windows-powershell"></a><span data-ttu-id="4feac-157">使用自定义配置Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4feac-157">Configure categories by using Windows PowerShell</span></span>

<span data-ttu-id="4feac-158">可以使用以下 cmdlet 配置Windows PowerShell：</span><span class="sxs-lookup"><span data-stu-id="4feac-158">You can configure categories by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="4feac-159">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="4feac-159">**Cmdlet**</span></span>|<span data-ttu-id="4feac-160">**说明**</span><span class="sxs-lookup"><span data-stu-id="4feac-160">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="4feac-161">New-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="4feac-161">New-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="4feac-162">创建新类别</span><span class="sxs-lookup"><span data-stu-id="4feac-162">Create a new category</span></span>  <br/> |
|<span data-ttu-id="4feac-163">Set-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="4feac-163">Set-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="4feac-164">配置现有类别的设置</span><span class="sxs-lookup"><span data-stu-id="4feac-164">Configure settings for an existing category</span></span>  <br/> |
|<span data-ttu-id="4feac-165">Get-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="4feac-165">Get-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="4feac-166">检索有关类别的信息</span><span class="sxs-lookup"><span data-stu-id="4feac-166">Retrieve information about categories</span></span>  <br/> |
|<span data-ttu-id="4feac-167">Remove-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="4feac-167">Remove-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="4feac-168">删除类别</span><span class="sxs-lookup"><span data-stu-id="4feac-168">Remove a category</span></span>  <br/> |
   
<span data-ttu-id="4feac-169">您可以为类别配置以下参数：</span><span class="sxs-lookup"><span data-stu-id="4feac-169">You can configure the following parameters for categories:</span></span>
  
- <span data-ttu-id="4feac-170">EnableFileUpload。</span><span class="sxs-lookup"><span data-stu-id="4feac-170">EnableFileUpload.</span></span> <span data-ttu-id="4feac-171">允许将文件上载到类别中的聊天室。</span><span class="sxs-lookup"><span data-stu-id="4feac-171">Allows file uploads to the chat rooms in the category.</span></span>
    
- <span data-ttu-id="4feac-172">EnableInvitations。</span><span class="sxs-lookup"><span data-stu-id="4feac-172">EnableInvitations.</span></span> <span data-ttu-id="4feac-173">启用类别邀请。</span><span class="sxs-lookup"><span data-stu-id="4feac-173">Enables invitations for the category.</span></span> <span data-ttu-id="4feac-174">AllowedMembers 列表中的用户在新建聊天室时将自动收到加入新聊天室的邀请。</span><span class="sxs-lookup"><span data-stu-id="4feac-174">Users on the AllowedMembers list will automatically receive an invitation to join a new chat room at the time the new room is created.</span></span>
    
- <span data-ttu-id="4feac-175">ChatHistory。</span><span class="sxs-lookup"><span data-stu-id="4feac-175">ChatHistory.</span></span> <span data-ttu-id="4feac-176">启用或禁用聊天历史记录功能。</span><span class="sxs-lookup"><span data-stu-id="4feac-176">Enables or disables the chat history feature.</span></span>
    
- <span data-ttu-id="4feac-177">创建者。</span><span class="sxs-lookup"><span data-stu-id="4feac-177">Creators.</span></span> <span data-ttu-id="4feac-178">指定允许在类别中创建聊天室的用户。</span><span class="sxs-lookup"><span data-stu-id="4feac-178">Specifies the users who are allowed to create chat rooms within the category.</span></span>
    
- <span data-ttu-id="4feac-179">AllowedMembers。</span><span class="sxs-lookup"><span data-stu-id="4feac-179">AllowedMembers.</span></span> <span data-ttu-id="4feac-180">指定允许访问类别中的聊天室的用户。</span><span class="sxs-lookup"><span data-stu-id="4feac-180">Specifies the users who are allowed to access chat rooms within the category.</span></span>
    
- <span data-ttu-id="4feac-181">DeniedMembers。</span><span class="sxs-lookup"><span data-stu-id="4feac-181">DeniedMembers.</span></span> <span data-ttu-id="4feac-182">列出不允许访问类别中的聊天室的用户。</span><span class="sxs-lookup"><span data-stu-id="4feac-182">Lists the users who are not allowed to access chat rooms within the category.</span></span>
    
<span data-ttu-id="4feac-183">有关 cmdlet 语法的完整信息（包括所有参数），请参阅[Skype for Business Server 2015 Management Shell。](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="4feac-183">For complete information about cmdlet syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
### <a name="create-a-new-category"></a><span data-ttu-id="4feac-184">创建新类别</span><span class="sxs-lookup"><span data-stu-id="4feac-184">Create a new category</span></span>

<span data-ttu-id="4feac-185">您可以使用 **New-CsPersistentChatCategory** cmdlet 创建新类别。</span><span class="sxs-lookup"><span data-stu-id="4feac-185">You can create a new category by using the **New-CsPersistentChatCategory** cmdlet.</span></span> <span data-ttu-id="4feac-186">例如，以下命令在池池上创建一个名为 HelpDesk 的新atl-cs-001.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="4feac-186">For example, the following command creates a new category named HelpDesk on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="4feac-187">本示例中启用文件上载：</span><span class="sxs-lookup"><span data-stu-id="4feac-187">In this example, file upload is enabled:</span></span>
  
```PowerShell
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a><span data-ttu-id="4feac-188">配置现有类别</span><span class="sxs-lookup"><span data-stu-id="4feac-188">Configure an existing category</span></span>

<span data-ttu-id="4feac-189">可以使用 **Set-CsPersistentCategory** cmdlet 配置现有类别。</span><span class="sxs-lookup"><span data-stu-id="4feac-189">You can configure an existing category by using the **Set-CsPersistentCategory** cmdlet.</span></span>
  
<span data-ttu-id="4feac-190">例如，以下命令指定 user1 是 AllowedMember 和 Creator，而 user2 被拒绝访问类别中的聊天室：</span><span class="sxs-lookup"><span data-stu-id="4feac-190">For example, the following command specifies that user1 is an AllowedMember and a Creator, while user2 is denied access to the rooms in the category:</span></span>
  
```PowerShell
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a><span data-ttu-id="4feac-191">获取有关类别的信息</span><span class="sxs-lookup"><span data-stu-id="4feac-191">Get information about categories</span></span>

<span data-ttu-id="4feac-192">您可以使用 **Get-CsPersistentChatCategory** cmdlet 获取有关类别的信息。</span><span class="sxs-lookup"><span data-stu-id="4feac-192">You can get information about categories by using the **Get-CsPersistentChatCategory** cmdlet.</span></span> <span data-ttu-id="4feac-193">例如，以下命令返回组织中所有持久聊天类别的信息：</span><span class="sxs-lookup"><span data-stu-id="4feac-193">For example, the following command returns information for all the Persistent Chat categories in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a><span data-ttu-id="4feac-194">删除类别</span><span class="sxs-lookup"><span data-stu-id="4feac-194">Remove a category</span></span>

<span data-ttu-id="4feac-195">您可以使用 **Remove-CsPersistentChatCategory** cmdlet 删除类别。</span><span class="sxs-lookup"><span data-stu-id="4feac-195">You can remove a category by using the **Remove-CsPersistentChatCategory** cmdlet.</span></span> <span data-ttu-id="4feac-196">在删除类别之前，必须先删除类别下的所有聊天室，或将聊天室移动到新类别。</span><span class="sxs-lookup"><span data-stu-id="4feac-196">Before removing a category, you must first either delete all chat rooms under it or move the chat rooms to a new category.</span></span> <span data-ttu-id="4feac-197">例如，以下命令删除 Identity 为"atl-cs-001.contoso.com\helpdesk"的类别：</span><span class="sxs-lookup"><span data-stu-id="4feac-197">For example, the following command removes the category that has the Identity "atl-cs-001.contoso.com\helpdesk":</span></span>
  
```PowerShell
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
