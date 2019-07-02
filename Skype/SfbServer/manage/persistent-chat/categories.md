---
title: 在 Skype for Business Server 2015 中管理持久聊天服务器内的类别
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: '摘要: 了解如何在 Skype for Business Server 2015 中管理持久聊天服务器类别。'
ms.openlocfilehash: 8a8e8060db896a272293df3259091d4f7667a7d3
ms.sourcegitcommit: d4248fefd706616bd3ccc5b510a6696303fa88e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "35417937"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="a5348-103">在 Skype for Business Server 2015 中管理持久聊天服务器内的类别</span><span class="sxs-lookup"><span data-stu-id="a5348-103">Manage categories in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a5348-104">**摘要:** 了解如何在 Skype for Business Server 2015 中管理持久聊天服务器类别。</span><span class="sxs-lookup"><span data-stu-id="a5348-104">**Summary:** Learn how to manage Persistent Chat Server categories in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="a5348-105">类别是用于组织聊天室的逻辑结构。</span><span class="sxs-lookup"><span data-stu-id="a5348-105">A category is a logical structure for organizing chat rooms.</span></span> <span data-ttu-id="a5348-106">类别定义了一套默认的访问控制列表 (ACL) 以控制可以创建或加入聊天室的用户和用户组。</span><span class="sxs-lookup"><span data-stu-id="a5348-106">A category defines a default set of access control lists (ACLs) for controlling the users and user groups who can create or join the chat rooms.</span></span> <span data-ttu-id="a5348-107">聊天室类别包含聊天室，但不包含其他类别。</span><span class="sxs-lookup"><span data-stu-id="a5348-107">Chat room categories contain chat rooms, but not other categories.</span></span> <span data-ttu-id="a5348-108">每个类别说明了其内容及元数据，比如名称和说明。</span><span class="sxs-lookup"><span data-stu-id="a5348-108">Each category describes its contents with metadata, such as Name and Description.</span></span> <span data-ttu-id="a5348-109">类别拥有各种属性，可设置这些属性来控制属于该类别的聊天室的行为；例如，聊天室是否允许邀请或文件上载，或包含聊天历史记录。</span><span class="sxs-lookup"><span data-stu-id="a5348-109">The category has properties that can be set to control the behavior of the chat rooms belonging to it; for example, whether the chat rooms allow Invitations or File Uploads, or contain Chat History.</span></span> 
  
<span data-ttu-id="a5348-110">通过正确使用类别，创建和管理聊天室的过程可以大大简化。</span><span class="sxs-lookup"><span data-stu-id="a5348-110">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="a5348-111">持久聊天服务器管理员可以定义每个类别的 AllowedMembers 和  Creators，还可以定义将应用于在该类别中创建的所有聊天室的默认聊天室设置和行为。</span><span class="sxs-lookup"><span data-stu-id="a5348-111">As a Persistent Chat Server administrator, you can define AllowedMembers and Creators for each category, and also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="a5348-112">例如, 如果将类别的 AllowedMembers 设置为 contoso.com, 则可以将 Contoso 中的任何组或用户添加到该类别中的聊天室。</span><span class="sxs-lookup"><span data-stu-id="a5348-112">For example, if you set the category's AllowedMembers to contoso.com, you can add any group or user at Contoso as a member to chat rooms in that category.</span></span> <span data-ttu-id="a5348-113">如果将某个类别上的 Allowed Members 设置为 Sales，则只能将此通讯组列表中的组和用户添加为该类别中的聊天室的成员。</span><span class="sxs-lookup"><span data-stu-id="a5348-113">If you set the Allowed Members on a category to Sales, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="a5348-114">同样，利用 Creators 属性，您可以控制可在该类别中创建聊天室的人员。</span><span class="sxs-lookup"><span data-stu-id="a5348-114">The Creators property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="a5348-115">创建聊天室后，可将 AllowedMembers 组中的任何人指定为聊天室中正在进行的管理操作（例如，成员身份更改和审批）的管理者。</span><span class="sxs-lookup"><span data-stu-id="a5348-115">After the chat room is created, anyone from the AllowedMembers group can be designated as a Manager for ongoing management operations on the rooms (for example, membership changes and approval).</span></span>
  
<span data-ttu-id="a5348-116">为类别定义  AllowedMembers  和  Creators  有以下好处：</span><span class="sxs-lookup"><span data-stu-id="a5348-116">Defining AllowedMembers and Creators for a category has the following benefits:</span></span>
  
- <span data-ttu-id="a5348-117">该类别中的所有聊天室都绑定了在类别级别设置的限制。</span><span class="sxs-lookup"><span data-stu-id="a5348-117">All chat rooms in this category are bound by the restrictions set at the category level.</span></span> <span data-ttu-id="a5348-118">您可以使用此限制，根据业务需求和访问策略隔离聊天室。</span><span class="sxs-lookup"><span data-stu-id="a5348-118">You can use this to segregate chat rooms based on business need and access policies.</span></span>
    
- <span data-ttu-id="a5348-p104">Creators 列表中的用户可在该类别中创建新聊天室。如果要实现这样一个系统 - 组织中有限数量的人员可创建聊天室，那么可使用此控制来满足要求。</span><span class="sxs-lookup"><span data-stu-id="a5348-p104">A user who is in the Creators list can create new chat rooms in that category. If you want to implement a system where a restricted number of personnel in the organization can create chat rooms this control can be used to meet that requirements.</span></span> 
    
<span data-ttu-id="a5348-121">标识为类别创建者的用户、组织单位 (OU) 和用户组是仅有的被允许在类别中创建聊天室的个人和组。</span><span class="sxs-lookup"><span data-stu-id="a5348-121">Users, Organization Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category.</span></span> <span data-ttu-id="a5348-122">创建类别后，您可以从类别的  AllowedMembers  列表中选择用户、OU 和用户组作为聊天室的管理员和成员来管理和参与聊天室。</span><span class="sxs-lookup"><span data-stu-id="a5348-122">After the category is created, you can choose users, OUs, and user groups from the category's AllowedMembers list as chat room managers and members to manage and participate in the room.</span></span> 
  
<span data-ttu-id="a5348-123">在配置类别之前, 请务必阅读[Skype For Business Server 2015 中的持久聊天类别、聊天室和用户角色](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="a5348-123">Before you configure categories, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md).</span></span>
  
<span data-ttu-id="a5348-124">您可以使用控制面板或 Windows PowerShell cmdlet 配置和管理类别。</span><span class="sxs-lookup"><span data-stu-id="a5348-124">You can configure and manage categories by using the Control Panel or by using Windows PowerShell cmdlets.</span></span>

> [!NOTE]
> <span data-ttu-id="a5348-125">Skype for business Server 2015 中提供了持久聊天, 但 Skype for business Server 2019 不再支持此功能。</span><span class="sxs-lookup"><span data-stu-id="a5348-125">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="a5348-126">团队中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="a5348-126">The same functionality is available in Teams.</span></span> <span data-ttu-id="a5348-127">有关详细信息, 请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。</span><span class="sxs-lookup"><span data-stu-id="a5348-127">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="a5348-128">如果需要使用持久聊天, 您可以选择将需要此功能的用户迁移到团队, 或继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="a5348-128">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
  
## <a name="configure-categories-by-using-the-control-panel"></a><span data-ttu-id="a5348-129">使用控制面板配置类别</span><span class="sxs-lookup"><span data-stu-id="a5348-129">Configure categories by using the Control Panel</span></span>

1. <span data-ttu-id="a5348-130">使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。</span><span class="sxs-lookup"><span data-stu-id="a5348-130">From a user account that is assigned to the CsPersistentChatAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="a5348-131">从 "**开始**" 菜单中, 选择 "Skype For business 服务器" 控制面板或打开一个浏览器窗口, 然后输入管理员 URL。</span><span class="sxs-lookup"><span data-stu-id="a5348-131">From the **Start** menu, select the Skype for Business Server Control Panel or open a browser window, and then enter the Admin URL.</span></span>
    
3. <span data-ttu-id="a5348-132">在左侧导航栏中，单击“**持久聊天**”，然后单击“**类别**”。</span><span class="sxs-lookup"><span data-stu-id="a5348-132">In the left navigation bar, click **Persistent Chat**, and then click **Category**.</span></span>
    
    <span data-ttu-id="a5348-133">对于多个持久聊天服务器池部署, 从下拉列表中选择相应的池。</span><span class="sxs-lookup"><span data-stu-id="a5348-133">For multiple Persistent Chat Server pool deployments, select the appropriate pool from the drop-down list.</span></span>
    
4. <span data-ttu-id="a5348-134">在“**类别**”页上，单击“**新建**”或“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="a5348-134">On the **Category** page, click **New** or **Edit**.</span></span>
    
5. <span data-ttu-id="a5348-135">在 "**选择服务**" 中, 选择与需要在其中创建类别的持久聊天服务器池对应的服务。</span><span class="sxs-lookup"><span data-stu-id="a5348-135">In **Select a Service**, select the service corresponding to the Persistent Chat Server pool on which the category needs to be created.</span></span> <span data-ttu-id="a5348-136">该服务是持久聊天服务器池, 永久聊天客户端使用它标识类别所属的池。</span><span class="sxs-lookup"><span data-stu-id="a5348-136">The service is the Persistent Chat Server pool that the Persistent Chat client uses to identify which pool the category belongs to.</span></span> <span data-ttu-id="a5348-137">一个类别只能属于一个持久聊天服务器池, 并且不能移动到另一个池或与另一个池共享。</span><span class="sxs-lookup"><span data-stu-id="a5348-137">A category can belong to only one Persistent Chat Server pool, and cannot be moved to, or shared with, another pool.</span></span>
    
6. <span data-ttu-id="a5348-138">在“**新建类别**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a5348-138">In **New Category**, do the following:</span></span>
    
   - <span data-ttu-id="a5348-139">在“**名称**”中，指定新聊天室类别的名称。</span><span class="sxs-lookup"><span data-stu-id="a5348-139">In **Name**, specify a name for the new room category.</span></span>
    
   - <span data-ttu-id="a5348-140">在“**描述**”中，提供有关聊天室类别（例如 Contoso 聊天室类别）的详细描述。</span><span class="sxs-lookup"><span data-stu-id="a5348-140">In **Description**, provide a detailed description for the room category (for example, a room category for Contoso).</span></span>
    
   - <span data-ttu-id="a5348-141">要控制是否为属于此类别的聊天室启用邀请，请选中或清除“**启用邀请**”复选框。</span><span class="sxs-lookup"><span data-stu-id="a5348-141">To control whether invitations can be enabled for chat rooms that belong to this category, select or clear the **Enable invitations** check box.</span></span> <span data-ttu-id="a5348-142">如果选中，则此类别的聊天室将打开或关闭邀请；如果清除，则不允许此类别的聊天室具有邀请。</span><span class="sxs-lookup"><span data-stu-id="a5348-142">If selected, rooms in this category may have invitations on or off; if cleared, the rooms in this category are not allowed to have invitations.</span></span> <span data-ttu-id="a5348-143">如果会议室有邀请, 则在将新成员添加到聊天室时, 他或她将收到新聊天室在其持久聊天客户端中的通知。</span><span class="sxs-lookup"><span data-stu-id="a5348-143">If a room has invitations on, when a new member is added to a room, he or she gets a notification of the new room in their Persistent Chat client.</span></span>
    
   - <span data-ttu-id="a5348-p109">要控制属于此类别的聊天室中的文件上载，请选中或清除“**启用文件上载**”复选框。如果选中，该类别的聊天室可以启用或禁用文件上载；如果清除，则不允许该类别的聊天室执行文件上载操作。</span><span class="sxs-lookup"><span data-stu-id="a5348-p109">To control file uploads in chat rooms belonging to this category, select or clear the **Enable file upload** check box. If selected, the rooms of this category can enable or disable file uploads; if cleared, the rooms of this category are not allowed to have file uploads.</span></span>
    
   - <span data-ttu-id="a5348-146">若要控制聊天历史记录, 请选中或清除 "**启用聊天历史记录**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="a5348-146">To control chat history, select or clear the **Enable chat history** check box.</span></span> <span data-ttu-id="a5348-147">如果选中，则聊天室聊天内容将变成持久的；否则，将不会保留聊天消息。</span><span class="sxs-lookup"><span data-stu-id="a5348-147">If selected, room chats become persistent; otherwise, chat messages are not persisted.</span></span> <span data-ttu-id="a5348-148">如果启用了合规性，则将按合规性保存聊天室聊天内容，但用户无法访问较早的消息。</span><span class="sxs-lookup"><span data-stu-id="a5348-148">If compliance is enabled, room chats will be saved in compliance, but users will not be able to access older messages.</span></span> <span data-ttu-id="a5348-149">此选项可用于为不需要保留聊天历史记录的实时、临时协作的会议室指定的会议室。</span><span class="sxs-lookup"><span data-stu-id="a5348-149">This option can be used for rooms designated for real-time, ad hoc collaborations that don't need chat history to be persisted.</span></span>
    
7. <span data-ttu-id="a5348-150">在“**编辑类别**”中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="a5348-150">In **Edit Category**, do the following:</span></span>
    
   - <span data-ttu-id="a5348-151">在\*\*\*\*"允许的成员" 部分中, 在 "**允许的成员**" 部分中, 添加或删除允许添加为聊天室成员的用户和其他 Active Directory 域服务主体 (用户、通讯组、组织单位等)属于类别。</span><span class="sxs-lookup"><span data-stu-id="a5348-151">In **Membership**, in the **Allowed members** section, add or remove users and other Active Directory Domain Services principals (users, distribution groups, organizational units, and so on) that are permitted to be added as members of chat rooms belonging to the category.</span></span> <span data-ttu-id="a5348-152">类别允许的主体可搜索此类别的聊天室（除非隐藏了聊天室，在这种情况下，仅聊天室的成员可在此目录中搜索聊天室）。</span><span class="sxs-lookup"><span data-stu-id="a5348-152">Principals permitted by a category can search for the rooms in the category (unless the room is hidden, in which case only members of the room can search for it in the directory).</span></span>
    
   - <span data-ttu-id="a5348-153">在\*\*\*\*"**拒绝成员**" 部分中, 在 "拒绝的成员" 部分中, 添加或删除与从聊天室拒绝的成员关联的用户和其他 Active Directory 主体。</span><span class="sxs-lookup"><span data-stu-id="a5348-153">In **Membership**, in the **Denied members** section, add or remove users and other Active Directory principals associated with members being denied from the room.</span></span>
    
   - <span data-ttu-id="a5348-154">在 "**成员资格**" 部分中, 在 "**创建者**" 部分中, 添加或删除与类别的 "创建者" 关联的用户和其他 Active Directory 主体。</span><span class="sxs-lookup"><span data-stu-id="a5348-154">In **Membership**, in the **Creators** section, add or remove users and other Active Directory principals associated with creators for the category.</span></span> <span data-ttu-id="a5348-155">创建者是有权创建聊天室并指定聊天室管理员和成员的用户。</span><span class="sxs-lookup"><span data-stu-id="a5348-155">A creator is a user who has permissions to create chat rooms and assign chat room managers and members.</span></span>
    
8. <span data-ttu-id="a5348-156">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="a5348-156">Click **Commit**.</span></span>
    
## <a name="configure-categories-by-using-windows-powershell"></a><span data-ttu-id="a5348-157">使用 Windows PowerShell 配置类别</span><span class="sxs-lookup"><span data-stu-id="a5348-157">Configure categories by using Windows PowerShell</span></span>

<span data-ttu-id="a5348-158">您可以使用以下 Windows PowerShell cmdlet 配置类别：</span><span class="sxs-lookup"><span data-stu-id="a5348-158">You can configure categories by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="a5348-159">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="a5348-159">**Cmdlet**</span></span>|<span data-ttu-id="a5348-160">**说明**</span><span class="sxs-lookup"><span data-stu-id="a5348-160">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a5348-161">New-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="a5348-161">New-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="a5348-162">创建新类别</span><span class="sxs-lookup"><span data-stu-id="a5348-162">Create a new category</span></span>  <br/> |
|<span data-ttu-id="a5348-163">Set-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="a5348-163">Set-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="a5348-164">配置现有类别的设置</span><span class="sxs-lookup"><span data-stu-id="a5348-164">Configure settings for an existing category</span></span>  <br/> |
|<span data-ttu-id="a5348-165">Get-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="a5348-165">Get-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="a5348-166">检索有关类别的信息</span><span class="sxs-lookup"><span data-stu-id="a5348-166">Retrieve information about categories</span></span>  <br/> |
|<span data-ttu-id="a5348-167">Remove-CsPersistentChatCategory</span><span class="sxs-lookup"><span data-stu-id="a5348-167">Remove-CsPersistentChatCategory</span></span>  <br/> |<span data-ttu-id="a5348-168">删除类别</span><span class="sxs-lookup"><span data-stu-id="a5348-168">Remove a category</span></span>  <br/> |
   
<span data-ttu-id="a5348-169">可以为类别配置以下参数：</span><span class="sxs-lookup"><span data-stu-id="a5348-169">You can configure the following parameters for categories:</span></span>
  
- <span data-ttu-id="a5348-p113">EnableFileUpload。允许类别中的聊天室具有文件上载功能。</span><span class="sxs-lookup"><span data-stu-id="a5348-p113">EnableFileUpload. Allows file uploads to the chat rooms in the category.</span></span>
    
- <span data-ttu-id="a5348-172">EnableInvitations。</span><span class="sxs-lookup"><span data-stu-id="a5348-172">EnableInvitations.</span></span> <span data-ttu-id="a5348-173">为类别启用邀请。</span><span class="sxs-lookup"><span data-stu-id="a5348-173">Enables invitations for the category.</span></span> <span data-ttu-id="a5348-174">AllowedMembers 列表中的用户将在创建新聊天室后自动收到加入该聊天室的邀请。</span><span class="sxs-lookup"><span data-stu-id="a5348-174">Users on the AllowedMembers list will automatically receive an invitation to join a new chat room at the time the new room is created.</span></span>
    
- <span data-ttu-id="a5348-175">ChatHistory。</span><span class="sxs-lookup"><span data-stu-id="a5348-175">ChatHistory.</span></span> <span data-ttu-id="a5348-176">启用或禁用聊天室历史记录功能。</span><span class="sxs-lookup"><span data-stu-id="a5348-176">Enables or disables the chat history feature.</span></span>
    
- <span data-ttu-id="a5348-177">Creators。</span><span class="sxs-lookup"><span data-stu-id="a5348-177">Creators.</span></span> <span data-ttu-id="a5348-178">指定允许在类别中创建聊天室的用户。</span><span class="sxs-lookup"><span data-stu-id="a5348-178">Specifies the users who are allowed to create chat rooms within the category.</span></span>
    
- <span data-ttu-id="a5348-179">AllowedMembers。</span><span class="sxs-lookup"><span data-stu-id="a5348-179">AllowedMembers.</span></span> <span data-ttu-id="a5348-180">指定允许访问类别中的聊天室的用户。</span><span class="sxs-lookup"><span data-stu-id="a5348-180">Specifies the users who are allowed to access chat rooms within the category.</span></span>
    
- <span data-ttu-id="a5348-p118">DeniedMembers。列出不允许访问类别中的聊天室的用户。</span><span class="sxs-lookup"><span data-stu-id="a5348-p118">DeniedMembers. Lists the users who are not allowed to access chat rooms within the category.</span></span>
    
<span data-ttu-id="a5348-183">有关 cmdlet 语法的完整信息，包括所有参数，请参阅[Skype for Business Server 2015 Management Shell](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="a5348-183">For complete information about cmdlet syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
### <a name="create-a-new-category"></a><span data-ttu-id="a5348-184">创建新类别</span><span class="sxs-lookup"><span data-stu-id="a5348-184">Create a new category</span></span>

<span data-ttu-id="a5348-185">您可以使用 **New-CsPersistentChatCategory** cmdlet 创建新类别。</span><span class="sxs-lookup"><span data-stu-id="a5348-185">You can create a new category by using the **New-CsPersistentChatCategory** cmdlet.</span></span> <span data-ttu-id="a5348-186">例如，以下命令可在池 atl-cs-001.contoso.com 上创建名为 HelpDesk 的新类别。</span><span class="sxs-lookup"><span data-stu-id="a5348-186">For example, the following command creates a new category named HelpDesk on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="a5348-187">在此示例中，启用了文件上载：</span><span class="sxs-lookup"><span data-stu-id="a5348-187">In this example, file upload is enabled:</span></span>
  
```
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a><span data-ttu-id="a5348-188">配置现有类别</span><span class="sxs-lookup"><span data-stu-id="a5348-188">Configure an existing category</span></span>

<span data-ttu-id="a5348-189">您可以使用 **Set-CsPersistentCategory** cmdlet 配置现有类别。</span><span class="sxs-lookup"><span data-stu-id="a5348-189">You can configure an existing category by using the **Set-CsPersistentCategory** cmdlet.</span></span>
  
<span data-ttu-id="a5348-190">例如, 以下命令指定 user1 是 AllowedMember 和创建者, 而当者被拒绝访问该类别中的聊天室时:</span><span class="sxs-lookup"><span data-stu-id="a5348-190">For example, the following command specifies that user1 is an AllowedMember and a Creator, while user2 is denied access to the rooms in the category:</span></span>
  
```
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a><span data-ttu-id="a5348-191">获取有关类别的信息</span><span class="sxs-lookup"><span data-stu-id="a5348-191">Get information about categories</span></span>

<span data-ttu-id="a5348-p120">您可以使用 **Get-CsPersistentChatCategory** cmdlet 获取有关类别的信息。例如，以下命令将为组织中的所有持久聊天类别返回信息：</span><span class="sxs-lookup"><span data-stu-id="a5348-p120">You can get information about categories by using the **Get-CsPersistentChatCategory** cmdlet. For example, the following command returns information for all the Persistent Chat categories in the organization:</span></span>
  
```
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a><span data-ttu-id="a5348-194">删除类别</span><span class="sxs-lookup"><span data-stu-id="a5348-194">Remove a category</span></span>

<span data-ttu-id="a5348-p121">您可以使用 **Remove-CsPersistentChatCategory** cmdlet 删除类别。删除类别前，您必须首先删除类别下的所有聊天室，或将聊天室移至新类别。例如，以下命令可删除具有 Identity“atl-cs-001.contoso.com\helpdesk”的类别：</span><span class="sxs-lookup"><span data-stu-id="a5348-p121">You can remove a category by using the **Remove-CsPersistentChatCategory** cmdlet. Before removing a category, you must first either delete all chat rooms under it or move the chat rooms to a new category. For example, the following command removes the category that has the Identity "atl-cs-001.contoso.com\helpdesk":</span></span>
  
```
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
