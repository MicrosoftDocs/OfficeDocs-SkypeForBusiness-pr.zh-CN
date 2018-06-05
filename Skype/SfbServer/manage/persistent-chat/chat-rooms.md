---
title: 在 Skype for Business Server 2015 中管理持久聊天服务器内的聊天室
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 摘要： 了解如何管理 Persistent Chat Server 聊天室中 Skype for Business Server 2015。
ms.openlocfilehash: 7febc9736f43f3168d7bc62b0ddf833fa6b5864b
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2018
ms.locfileid: "19569398"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="1a623-103">在 Skype for Business Server 2015 中管理持久聊天服务器内的聊天室</span><span class="sxs-lookup"><span data-stu-id="1a623-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1a623-104">**摘要：** 了解如何为业务服务器 2015年管理持久聊天服务器中 Skype 的聊天室。</span><span class="sxs-lookup"><span data-stu-id="1a623-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="1a623-105">通过正确使用类别，创建和管理聊天室的过程可以大大简化。</span><span class="sxs-lookup"><span data-stu-id="1a623-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="1a623-106">类别定义谁可以创建或加入聊天室。</span><span class="sxs-lookup"><span data-stu-id="1a623-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="1a623-107">您尝试管理聊天室之前，请务必阅读[持久聊天类别、 聊天室和用户角色中的业务服务器 2015 Skype](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)和[管理类别中的业务服务器 2015 Skype Persistent Chat Server 中](categories.md)。</span><span class="sxs-lookup"><span data-stu-id="1a623-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
<span data-ttu-id="1a623-108">您可以配置和管理聊天室，通过使用 Windows PowerShell 命令行界面，或通过使用 Skype for Business 客户端，如果您是聊天室的成员。</span><span class="sxs-lookup"><span data-stu-id="1a623-108">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="1a623-109">本主题介绍了如何使用 Windows PowerShell 命令行界面管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="1a623-109">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="1a623-110">如果您想要使用 Skype 业务客户端管理聊天室，请参阅客户端帮助。</span><span class="sxs-lookup"><span data-stu-id="1a623-110">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="1a623-111">聊天室可以是两种类型之一： 普通和大会堂。</span><span class="sxs-lookup"><span data-stu-id="1a623-111">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="1a623-112">Normal 聊天室允许所有成员发布和阅读消息。</span><span class="sxs-lookup"><span data-stu-id="1a623-112">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="1a623-113">Auditorium 聊天室仅允许演示者发布消息，但所有人都可以阅读消息。</span><span class="sxs-lookup"><span data-stu-id="1a623-113">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="1a623-114">可访问和管理聊天室的人员取决于用户角色，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1a623-114">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="1a623-115">用户必须是聊天室的成员才能发布和阅读消息。</span><span class="sxs-lookup"><span data-stu-id="1a623-115">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="1a623-116">演示者可以向 Auditorium 聊天室发布消息。</span><span class="sxs-lookup"><span data-stu-id="1a623-116">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="1a623-117">管理员可删除任何聊天室的旧内容（例如，特定日期前发布的内容）以保持数据库的大小不会极大地增加。</span><span class="sxs-lookup"><span data-stu-id="1a623-117">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="1a623-118">管理员也可以删除或替换认为对特定聊天室不合适的消息。</span><span class="sxs-lookup"><span data-stu-id="1a623-118">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="1a623-119">最终用户（包括消息作者）无法删除任何聊天室的内容。</span><span class="sxs-lookup"><span data-stu-id="1a623-119">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="1a623-120">聊天室管理者可以对所有聊天室属性进行更改，包括禁用聊天室。</span><span class="sxs-lookup"><span data-stu-id="1a623-120">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="1a623-121">但管理者无法删除聊天室或更改聊天室的类别。</span><span class="sxs-lookup"><span data-stu-id="1a623-121">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="1a623-122">聊天室创建后，仅管理员可删除它。</span><span class="sxs-lookup"><span data-stu-id="1a623-122">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="1a623-123">您可以使用以下 Windows PowerShell cmdlet 配置和管理聊天室：</span><span class="sxs-lookup"><span data-stu-id="1a623-123">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="1a623-124">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="1a623-124">**Cmdlet**</span></span>|<span data-ttu-id="1a623-125">**说明**</span><span class="sxs-lookup"><span data-stu-id="1a623-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1a623-126">New-cspersistentchatroom</span><span class="sxs-lookup"><span data-stu-id="1a623-126">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="1a623-127">新建聊天室</span><span class="sxs-lookup"><span data-stu-id="1a623-127">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="1a623-128">Set-cspersistentchatroom</span><span class="sxs-lookup"><span data-stu-id="1a623-128">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="1a623-129">配置现有聊天室的设置；向聊天室分配用户和用户组</span><span class="sxs-lookup"><span data-stu-id="1a623-129">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="1a623-130">Get-cspersistentchatroom</span><span class="sxs-lookup"><span data-stu-id="1a623-130">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="1a623-131">检索有关聊天室的信息</span><span class="sxs-lookup"><span data-stu-id="1a623-131">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="1a623-132">Clear-cspersistentchatroom</span><span class="sxs-lookup"><span data-stu-id="1a623-132">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="1a623-133">清除聊天室或清除聊天室中的消息</span><span class="sxs-lookup"><span data-stu-id="1a623-133">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="1a623-134">即 Remove-cspersistentchatroom</span><span class="sxs-lookup"><span data-stu-id="1a623-134">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="1a623-135">删除聊天室</span><span class="sxs-lookup"><span data-stu-id="1a623-135">Remove a room</span></span>  <br/> |
|<span data-ttu-id="1a623-136">删除 CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="1a623-136">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="1a623-137">从聊天室删除消息</span><span class="sxs-lookup"><span data-stu-id="1a623-137">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="1a623-138">使用 **New-CsPersistentChatRoom** cmdlet 来创建聊天室，使用 **Set-CsPersistentChatRoom** cmdlet 来配置现有聊天室，包括向聊天室添加用户。</span><span class="sxs-lookup"><span data-stu-id="1a623-138">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="1a623-139">您可以配置聊天室的以下参数：</span><span class="sxs-lookup"><span data-stu-id="1a623-139">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="1a623-140">Disabled。</span><span class="sxs-lookup"><span data-stu-id="1a623-140">Disabled.</span></span> <span data-ttu-id="1a623-141">允许您禁用或启用聊天室。</span><span class="sxs-lookup"><span data-stu-id="1a623-141">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="1a623-142">Invitations。</span><span class="sxs-lookup"><span data-stu-id="1a623-142">Invitations.</span></span> <span data-ttu-id="1a623-143">允许您禁用或启用聊天室邀请，在用户被添加为聊天室成员时，可使用邀请来通知用户。</span><span class="sxs-lookup"><span data-stu-id="1a623-143">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="1a623-144">将继承默认邀请设置，这导致聊天室会采用在其所属的类别上配置的邀请设置。</span><span class="sxs-lookup"><span data-stu-id="1a623-144">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="1a623-145">在聊天室级别将邀请设置配置为 false 可覆盖类别设置。</span><span class="sxs-lookup"><span data-stu-id="1a623-145">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="1a623-146">Privacy。</span><span class="sxs-lookup"><span data-stu-id="1a623-146">Privacy.</span></span> <span data-ttu-id="1a623-147">使您可以指定聊天室是“开放式”、“封闭式”还是“机密”。</span><span class="sxs-lookup"><span data-stu-id="1a623-147">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="1a623-148">任何人都可以搜索和访问“开放式”聊天室。</span><span class="sxs-lookup"><span data-stu-id="1a623-148">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="1a623-149">任何人都可以搜索“封闭式”聊天室，但只有成员才能访问。</span><span class="sxs-lookup"><span data-stu-id="1a623-149">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="1a623-150">只有聊天室的成员才能搜索和访问“机密”聊天室。</span><span class="sxs-lookup"><span data-stu-id="1a623-150">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="1a623-151">默认情况下，每个新聊天室最初都会配置为“封闭式”。</span><span class="sxs-lookup"><span data-stu-id="1a623-151">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="1a623-152">Type。</span><span class="sxs-lookup"><span data-stu-id="1a623-152">Type.</span></span> <span data-ttu-id="1a623-153">允许您指定聊天室是否正常的室内，接受任何成员，或大会堂聊天室，其接受只能由演示者张贴的消息张贴的消息。</span><span class="sxs-lookup"><span data-stu-id="1a623-153">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="1a623-154">Addin。</span><span class="sxs-lookup"><span data-stu-id="1a623-154">Addin.</span></span> <span data-ttu-id="1a623-155">让您可以将之前配置的外接程序与聊天室关联，从而允许成员在加入时查看 URL 内容。</span><span class="sxs-lookup"><span data-stu-id="1a623-155">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="1a623-156">除了上述参数， **Set-cspersistentchatroom** cmdlet 可以将用户分配到聊天室，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1a623-156">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="1a623-157">Members。</span><span class="sxs-lookup"><span data-stu-id="1a623-157">Members.</span></span> <span data-ttu-id="1a623-158">配置聊天室的成员关系。</span><span class="sxs-lookup"><span data-stu-id="1a623-158">Configures membership for the chat room.</span></span> <span data-ttu-id="1a623-159">您可以通过指定用户的 SIP 地址，使用单个 cmdlet 添加或删除单个或多个成员。</span><span class="sxs-lookup"><span data-stu-id="1a623-159">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="1a623-160">要允许批量添加用户，也可指定 Active Directory 组织单位或通讯组。</span><span class="sxs-lookup"><span data-stu-id="1a623-160">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="1a623-161">Managers。</span><span class="sxs-lookup"><span data-stu-id="1a623-161">Managers.</span></span> <span data-ttu-id="1a623-162">让您可以向聊天室分配管理者。</span><span class="sxs-lookup"><span data-stu-id="1a623-162">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="1a623-163">管理者有权定义聊天室的成员关系和其他设置。</span><span class="sxs-lookup"><span data-stu-id="1a623-163">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="1a623-p114">Presenters。让您可以向 Auditorium 聊天室分配演示者。</span><span class="sxs-lookup"><span data-stu-id="1a623-p114">Presenters. Lets you assign presenters to an Auditorium chat room.</span></span> 
    
 <span data-ttu-id="1a623-166">有关语法，包括所有参数的详细信息，请参阅[Skype 的业务服务器 2015年命令行管理程序](../management-shell.md)。</span><span class="sxs-lookup"><span data-stu-id="1a623-166">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="1a623-167">创建新聊天室</span><span class="sxs-lookup"><span data-stu-id="1a623-167">Create a new room</span></span>

<span data-ttu-id="1a623-168">您可以使用 **New-CsPersistentChatRoom** cmdlet 创建新聊天室。</span><span class="sxs-lookup"><span data-stu-id="1a623-168">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="1a623-169">例如，以下命令可在池 atl-cs-001.contoso.com 上创建名为 ITChatRoom 的新聊天室。</span><span class="sxs-lookup"><span data-stu-id="1a623-169">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="1a623-170">在此示例中，聊天室被添加到 IT 类别：</span><span class="sxs-lookup"><span data-stu-id="1a623-170">In this example, the chat room is added to the IT category:</span></span>
  
```
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="1a623-171">**注意：** 如果下列选项之一为 true，则不需要 PersistentChatPoolFqdn:</span><span class="sxs-lookup"><span data-stu-id="1a623-171">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="1a623-172">没有只有一个持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="1a623-172">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="1a623-173">您为类别提供了一个池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="1a623-173">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="1a623-174">您提供了一个池 Fqdn 以添加聊天室。</span><span class="sxs-lookup"><span data-stu-id="1a623-174">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="1a623-175">配置现有聊天室</span><span class="sxs-lookup"><span data-stu-id="1a623-175">Configure an existing room</span></span>

<span data-ttu-id="1a623-176">您可以使用**Set-cspersistentchatroom** cmdlet 配置现有的聊天室。</span><span class="sxs-lookup"><span data-stu-id="1a623-176">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="1a623-177">例如，以下命令分配作为成员和演示者的 user1 和 user2 作为经理，testCat 大会堂聊天室的：</span><span class="sxs-lookup"><span data-stu-id="1a623-177">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="1a623-178">下一个示例将 Active Directoryor 中 NorthAmericaUsers OU 中的所有用户添加到 NorthAmerica 聊天室：</span><span class="sxs-lookup"><span data-stu-id="1a623-178">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="1a623-179">下一个示例将 Finance 通讯组中的所有成员添加到相同的聊天室：</span><span class="sxs-lookup"><span data-stu-id="1a623-179">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="1a623-180">禁用或启用聊天室</span><span class="sxs-lookup"><span data-stu-id="1a623-180">Disable or enable a room</span></span>

<span data-ttu-id="1a623-181">如果持久聊天聊天室的主题不再重要，您可以使聊天室内不可用对用户禁用它。</span><span class="sxs-lookup"><span data-stu-id="1a623-181">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="1a623-182">禁用聊天室时，所有成员将立即从聊天室断开。</span><span class="sxs-lookup"><span data-stu-id="1a623-182">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="1a623-183">禁用聊天室后，用户无法重新加入或在聊天室搜索中找到该聊天室。</span><span class="sxs-lookup"><span data-stu-id="1a623-183">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="1a623-184">如果聊天室的历史记录仍然存在，请禁用聊天室时，将保留内容。</span><span class="sxs-lookup"><span data-stu-id="1a623-184">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="1a623-185">但是，在该聊天室处于禁用状态时，该内容不会显示在搜索中。</span><span class="sxs-lookup"><span data-stu-id="1a623-185">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="1a623-186">如果随后启用该聊天室，则用户可以搜索禁用该聊天室之前发布的消息。</span><span class="sxs-lookup"><span data-stu-id="1a623-186">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="1a623-187">有关配置聊天室的历史记录的信息，请参阅[中的业务服务器 2015 Skype Persistent Chat Server 中管理类别](categories.md)。</span><span class="sxs-lookup"><span data-stu-id="1a623-187">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="1a623-188">如果聊天室被禁用，其成员关系列表和其他设置将被保留。</span><span class="sxs-lookup"><span data-stu-id="1a623-188">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="1a623-189">作为管理员，您可以启用被禁用的聊天室，您无需手动重新创建设置。</span><span class="sxs-lookup"><span data-stu-id="1a623-189">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="1a623-190">您可以通过使用**Set-cspersistentchatroom** cmdlet 并禁用参数设置为 true 时，禁用聊天室：</span><span class="sxs-lookup"><span data-stu-id="1a623-190">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="1a623-191">要启用聊天室，请将 Disabled 参数设置为 False：</span><span class="sxs-lookup"><span data-stu-id="1a623-191">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a><span data-ttu-id="1a623-192">获取有关聊天室的信息</span><span class="sxs-lookup"><span data-stu-id="1a623-192">Get information about rooms</span></span>

<span data-ttu-id="1a623-193">要获取有关您的组织中配置使用的聊天室的信息，可以使用 **Get-CsPersistentChatRoom** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1a623-193">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="1a623-194">以下命令返回有关配置为在组织中使用的所有聊天室的信息：</span><span class="sxs-lookup"><span data-stu-id="1a623-194">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="1a623-195">从聊天室删除所有内容</span><span class="sxs-lookup"><span data-stu-id="1a623-195">Remove all content from a room</span></span>

<span data-ttu-id="1a623-p120">您可以使用 **Clear-CsPersistentChatRoom** cmdlet 从聊天室删除内容。例如，以下命令可从持久聊天室 ITChatRoom 中删除 2015 年 3 月 1 日或之前添加到聊天室的所有内容：</span><span class="sxs-lookup"><span data-stu-id="1a623-p120">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet. For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="1a623-198">从聊天室删除消息</span><span class="sxs-lookup"><span data-stu-id="1a623-198">Remove a message from a room</span></span>

<span data-ttu-id="1a623-p121">您可以使用 **Remove-CsPersistentChatMessage** cmdlet 删除持久聊天数据库中的一条或多条消息，并且可以选择将消息替换为默认消息或管理员提供的消息。例如，以下命令可从 ITChatRoom 聊天室删除用户 kenmyer@contoso.com 发布的所有消息：</span><span class="sxs-lookup"><span data-stu-id="1a623-p121">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet. For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="1a623-201">在下一个示例中，任何已删除的消息都将替换为说明消息已不再可用的通知：</span><span class="sxs-lookup"><span data-stu-id="1a623-201">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="1a623-202">删除聊天室</span><span class="sxs-lookup"><span data-stu-id="1a623-202">Remove a room</span></span>

<span data-ttu-id="1a623-203">您可以通过使用 **Remove-CsPersistentChatRoom** cmdlet 来删除聊天室。</span><span class="sxs-lookup"><span data-stu-id="1a623-203">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="1a623-204">例如，以下命令可删除聊天室 RedmondChatRoom：</span><span class="sxs-lookup"><span data-stu-id="1a623-204">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="1a623-205">将聊天室从一个类别移动到另一个类别</span><span class="sxs-lookup"><span data-stu-id="1a623-205">Move a room from one category to another</span></span>

<span data-ttu-id="1a623-p122">如果聊天室管理员在其他类别中具有  **Creator** 特权，则他/她可以将聊天室从一个类别移动到另一个类别。将不会删除和重新创建该聊天室。这是数据库中的关联的更改。</span><span class="sxs-lookup"><span data-stu-id="1a623-p122">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another. The room is not deleted and recreated. It is a change of association within the database.</span></span>
  
<span data-ttu-id="1a623-p123">应该尽量不要或者谨慎更改聊天室类别。类别用于确定聊天室允许的成员身份，因此当聊天室移动到另一个类别时，新类别不再支持的所有系统访问控制列表 (SACL) 都将清除。例如，如果用户是聊天室的成员，且不再是新类别中的许可成员，则系统会修改聊天室成员身份，并将用户从聊天室中删除。</span><span class="sxs-lookup"><span data-stu-id="1a623-p123">Changing a chat room category should be done rarely and with caution. A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged. For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  

