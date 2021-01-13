---
title: 在 Skype for Business Server 2015 中管理持久聊天服务器中的聊天室
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
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 摘要：了解如何在 Skype for Business Server 2015 中管理持久聊天服务器聊天室。
ms.openlocfilehash: 2b1b2e3bdc3411a4bacae5f1dc81b626abb92a91
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815102"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a><span data-ttu-id="629a9-103">在 Skype for Business Server 2015 中管理持久聊天服务器中的聊天室</span><span class="sxs-lookup"><span data-stu-id="629a9-103">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="629a9-104">**摘要：** 了解如何在 Skype for Business Server 2015 中管理持久聊天服务器聊天室。</span><span class="sxs-lookup"><span data-stu-id="629a9-104">**Summary:** Learn how to manage Persistent Chat Server chat rooms in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="629a9-105">正确使用类别可更轻松地创建和管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="629a9-105">Creating and managing chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="629a9-106">类别定义可以创建或加入聊天室的人。</span><span class="sxs-lookup"><span data-stu-id="629a9-106">A category defines who can create or join the chat rooms.</span></span> <span data-ttu-id="629a9-107">在尝试管理聊天室之前，请务必阅读 [Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) 中的持久聊天类别、聊天室和用户角色，以及管理 Skype for Business Server [2015](categories.md)中持久聊天服务器中的类别。</span><span class="sxs-lookup"><span data-stu-id="629a9-107">Before you attempt to manage chat rooms, be sure to read [Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md) and [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="629a9-108">持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="629a9-108">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="629a9-109">Teams 中也提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="629a9-109">The same functionality is available in Teams.</span></span> <span data-ttu-id="629a9-110">有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。</span><span class="sxs-lookup"><span data-stu-id="629a9-110">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="629a9-111">如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="629a9-111">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 

<span data-ttu-id="629a9-112">您可以使用 Windows PowerShell 命令行界面或 Skype for Business 客户端配置和管理聊天室（如果你是聊天室的成员）。</span><span class="sxs-lookup"><span data-stu-id="629a9-112">You can configure and manage chat rooms by using the Windows PowerShell command-line interface, or by using the Skype for Business client if you are a member of the chat room.</span></span> <span data-ttu-id="629a9-113">本主题介绍如何使用命令行界面Windows PowerShell聊天室。</span><span class="sxs-lookup"><span data-stu-id="629a9-113">This topic describes how to manage chat rooms by using the Windows PowerShell command-line interface.</span></span> <span data-ttu-id="629a9-114">如果要使用 Skype for Business 客户端管理聊天室，请参阅客户端帮助。</span><span class="sxs-lookup"><span data-stu-id="629a9-114">If you want to manage chat rooms by using the Skype for Business client, see the client help.</span></span> 
  
<span data-ttu-id="629a9-115">聊天室可以是两种类型之一：Normal 和 Auditorium。</span><span class="sxs-lookup"><span data-stu-id="629a9-115">Chat rooms can be one of two types: Normal and Auditorium.</span></span> <span data-ttu-id="629a9-116">Normal 聊天室允许所有成员发布和阅读消息。</span><span class="sxs-lookup"><span data-stu-id="629a9-116">A Normal chat room allows all members to post and read messages.</span></span> <span data-ttu-id="629a9-117">大会堂是一种聊天室，只有演示者才能发布消息，但每个人都可以阅读。</span><span class="sxs-lookup"><span data-stu-id="629a9-117">An Auditorium is a type of chat room where only Presenters can post, but everyone can read.</span></span>
  
<span data-ttu-id="629a9-118">谁可以访问和管理聊天室取决于用户角色，如下所示：</span><span class="sxs-lookup"><span data-stu-id="629a9-118">Who can access and manage chat rooms depends on user roles as follows:</span></span>
  
- <span data-ttu-id="629a9-119">用户必须是聊天室的成员才能发布和阅读消息。</span><span class="sxs-lookup"><span data-stu-id="629a9-119">Users must be Members of a chat room to be able to post and read messages.</span></span>
    
- <span data-ttu-id="629a9-120">演示者可以张贴到大会堂聊天室。</span><span class="sxs-lookup"><span data-stu-id="629a9-120">Presenters are allowed to post to Auditorium rooms.</span></span>
    
- <span data-ttu-id="629a9-121">管理员可删除任何聊天室的旧内容（例如，特定日期前发布的内容）以保持数据库的大小不会极大地增加。</span><span class="sxs-lookup"><span data-stu-id="629a9-121">Administrators can delete earlier content (for example, content that was posted before a certain date) from any chat room to keep the database from growing too large.</span></span> <span data-ttu-id="629a9-122">管理员还可以删除或替换认为不适合特定聊天室的消息。</span><span class="sxs-lookup"><span data-stu-id="629a9-122">Administrators can also remove or replace messages that are considered inappropriate for a particular chat room.</span></span>
    
- <span data-ttu-id="629a9-123">最终用户（包括消息作者）无法删除任何聊天室的内容。</span><span class="sxs-lookup"><span data-stu-id="629a9-123">End users, including message authors, cannot delete content from any chat room.</span></span>
    
- <span data-ttu-id="629a9-124">聊天室管理员可更改所有聊天室属性，包括禁用聊天室。</span><span class="sxs-lookup"><span data-stu-id="629a9-124">Chat room Managers can make changes to all chat room properties, including disabling rooms.</span></span> <span data-ttu-id="629a9-125">但是，管理员不能删除聊天室或更改聊天室的类别。</span><span class="sxs-lookup"><span data-stu-id="629a9-125">Managers cannot, however, delete a room, or change the category of a room.</span></span> 
    
- <span data-ttu-id="629a9-126">只有管理员才能在聊天室创建后删除该聊天室。</span><span class="sxs-lookup"><span data-stu-id="629a9-126">Only Administrators can delete a chat room after it has been created.</span></span>
    
<span data-ttu-id="629a9-127">您可以使用以下 cmdlet 配置和管理Windows PowerShell聊天室：</span><span class="sxs-lookup"><span data-stu-id="629a9-127">You can configure and manage chat rooms by using the following Windows PowerShell cmdlets:</span></span>
  

|<span data-ttu-id="629a9-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="629a9-128">**Cmdlet**</span></span>|<span data-ttu-id="629a9-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="629a9-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="629a9-130">New-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="629a9-130">New-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="629a9-131">创建新的聊天室</span><span class="sxs-lookup"><span data-stu-id="629a9-131">Create a new chat room</span></span>  <br/> |
|<span data-ttu-id="629a9-132">Set-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="629a9-132">Set-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="629a9-133">配置现有聊天室的设置;将用户和用户组分配给聊天室</span><span class="sxs-lookup"><span data-stu-id="629a9-133">Configure settings for an existing room; assign users and user groups to the room</span></span>  <br/> |
|<span data-ttu-id="629a9-134">Get-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="629a9-134">Get-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="629a9-135">检索有关聊天室的信息</span><span class="sxs-lookup"><span data-stu-id="629a9-135">Retrieve information about rooms</span></span>  <br/> |
|<span data-ttu-id="629a9-136">Clear-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="629a9-136">Clear-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="629a9-137">清除聊天室或聊天室的消息</span><span class="sxs-lookup"><span data-stu-id="629a9-137">Clear a room or messages from a room</span></span>  <br/> |
|<span data-ttu-id="629a9-138">Remove-CsPersistentChatRoom</span><span class="sxs-lookup"><span data-stu-id="629a9-138">Remove-CsPersistentChatRoom</span></span>  <br/> |<span data-ttu-id="629a9-139">删除聊天室</span><span class="sxs-lookup"><span data-stu-id="629a9-139">Remove a room</span></span>  <br/> |
|<span data-ttu-id="629a9-140">Remove-CsPersistentChatMessage</span><span class="sxs-lookup"><span data-stu-id="629a9-140">Remove-CsPersistentChatMessage</span></span>  <br/> |<span data-ttu-id="629a9-141">从聊天室中删除邮件</span><span class="sxs-lookup"><span data-stu-id="629a9-141">Remove messages from a room</span></span>  <br/> |
   
<span data-ttu-id="629a9-142">使用 **New-CsPersistentChatRoom** cmdlet 创建聊天室，使用 **Set-CsPersistentChatRoom** cmdlet 配置现有聊天室，包括向聊天室添加用户。</span><span class="sxs-lookup"><span data-stu-id="629a9-142">You use the **New-CsPersistentChatRoom** cmdlet to create chat rooms and the **Set-CsPersistentChatRoom** cmdlet to configure an existing chat room, including adding users to the chat room.</span></span> <span data-ttu-id="629a9-143">您可以为聊天室配置以下参数：</span><span class="sxs-lookup"><span data-stu-id="629a9-143">You can configure the following parameters for chat rooms:</span></span>
  
- <span data-ttu-id="629a9-144">已禁用。</span><span class="sxs-lookup"><span data-stu-id="629a9-144">Disabled.</span></span> <span data-ttu-id="629a9-145">允许您禁用或启用聊天室。</span><span class="sxs-lookup"><span data-stu-id="629a9-145">Lets you disable or enable a chat room.</span></span> 
    
- <span data-ttu-id="629a9-146">邀请。</span><span class="sxs-lookup"><span data-stu-id="629a9-146">Invitations.</span></span> <span data-ttu-id="629a9-147">允许您启用或禁用聊天室邀请，这些邀请用于在用户被添加为聊天室成员时通知用户。</span><span class="sxs-lookup"><span data-stu-id="629a9-147">Lets you enable or disable chat room invitations, which are used to notify users when they have been added as chat room members.</span></span> <span data-ttu-id="629a9-148">继承邀请的默认设置，导致聊天室采用在所属类别上配置的邀请设置。</span><span class="sxs-lookup"><span data-stu-id="629a9-148">The default setting for invitations in inherit, which caused the chat room to adopt the invitation setting configured on the category it belongs to.</span></span> <span data-ttu-id="629a9-149">在聊天室级别将邀请设置配置为 false 可覆盖类别设置。</span><span class="sxs-lookup"><span data-stu-id="629a9-149">Configuring the invitations setting to false at the chat room level allows the category setting to be overridden.</span></span> 
    
- <span data-ttu-id="629a9-150">隐私。</span><span class="sxs-lookup"><span data-stu-id="629a9-150">Privacy.</span></span> <span data-ttu-id="629a9-151">允许您指定聊天室是"打开"、"关闭"还是"机密"。</span><span class="sxs-lookup"><span data-stu-id="629a9-151">Lets you specify whether a chat room is Open, Closed, or Secret.</span></span> <span data-ttu-id="629a9-152">任何人都可以搜索和访问开放式聊天室。</span><span class="sxs-lookup"><span data-stu-id="629a9-152">Open rooms can be searched and accessed by anyone.</span></span> <span data-ttu-id="629a9-153">任何人都可以搜索封闭式聊天室，但只有成员才能访问。</span><span class="sxs-lookup"><span data-stu-id="629a9-153">Closed rooms can be searched by anyone, but can be accessed only by members.</span></span> <span data-ttu-id="629a9-154">只有聊天室的成员才能搜索和访问机密聊天室。</span><span class="sxs-lookup"><span data-stu-id="629a9-154">Secret rooms can be searched and accessed only by members of the room.</span></span> <span data-ttu-id="629a9-155">默认情况下，每个新聊天室最初配置为"已关闭"。</span><span class="sxs-lookup"><span data-stu-id="629a9-155">By default, each new room is initially configured as Closed.</span></span>
    
- <span data-ttu-id="629a9-156">类型。</span><span class="sxs-lookup"><span data-stu-id="629a9-156">Type.</span></span> <span data-ttu-id="629a9-157">允许您指定聊天室是 Normal 聊天室（接受任何成员发布的消息）还是 Auditorium 聊天室（仅接受演示者发布的消息）。</span><span class="sxs-lookup"><span data-stu-id="629a9-157">Lets you specify whether a chat room is a Normal room, which accepts messages posted by any member, or an Auditorium room, which accepts messages posted only by a Presenter.</span></span>
    
- <span data-ttu-id="629a9-158">加载项。</span><span class="sxs-lookup"><span data-stu-id="629a9-158">Addin.</span></span> <span data-ttu-id="629a9-159">允许您将以前配置的外接程序与聊天室关联，这样成员可以在参与时查看 URL 内容。</span><span class="sxs-lookup"><span data-stu-id="629a9-159">Lets you associate a previously configured add-in with a chat room, which allows URL content to be viewed by members while participating.</span></span>
    
<span data-ttu-id="629a9-160">除了上述参数之外 **，Set-CsPersistentChatRoom** cmdlet 还允许您将用户分配到聊天室，如下所示：</span><span class="sxs-lookup"><span data-stu-id="629a9-160">In addition to the above parameters, the **Set-CsPersistentChatRoom** cmdlet lets you assign users to the chat room as follows:</span></span>
  
- <span data-ttu-id="629a9-161">成员。</span><span class="sxs-lookup"><span data-stu-id="629a9-161">Members.</span></span> <span data-ttu-id="629a9-162">配置聊天室的成员身份。</span><span class="sxs-lookup"><span data-stu-id="629a9-162">Configures membership for the chat room.</span></span> <span data-ttu-id="629a9-163">可以通过指定用户的 SIP 地址，使用单个 cmdlet 添加或删除单个或多个成员。</span><span class="sxs-lookup"><span data-stu-id="629a9-163">You can add or remove either the individual or multiple members using a single cmdlet by specifying the SIP address of the users.</span></span> <span data-ttu-id="629a9-164">若要允许批量添加用户，还可以指定 Active Directory 组织单位或通讯组。</span><span class="sxs-lookup"><span data-stu-id="629a9-164">To allow users to be added in bulk, Active Directory organizational units or distribution groups can also be specified.</span></span>
    
- <span data-ttu-id="629a9-165">经理。</span><span class="sxs-lookup"><span data-stu-id="629a9-165">Managers.</span></span> <span data-ttu-id="629a9-166">允许您将管理员分配给聊天室。</span><span class="sxs-lookup"><span data-stu-id="629a9-166">Lets you assign managers to the chat room.</span></span> <span data-ttu-id="629a9-167">管理员具有定义聊天室成员身份以及其他设置的权限。</span><span class="sxs-lookup"><span data-stu-id="629a9-167">Managers have the permissions to define membership of a chat room along with other settings.</span></span>
    
- <span data-ttu-id="629a9-168">演示者。</span><span class="sxs-lookup"><span data-stu-id="629a9-168">Presenters.</span></span> <span data-ttu-id="629a9-169">允许你将演示者分配到 Auditorium 聊天室。</span><span class="sxs-lookup"><span data-stu-id="629a9-169">Lets you assign presenters to an Auditorium chat room.</span></span> 
    
  <span data-ttu-id="629a9-170">有关语法的详细信息，包括所有参数，请参阅 Skype [for Business Server 2015 Management Shell。](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="629a9-170">For details about syntax, including all parameters, see [Skype for Business Server 2015 Management Shell](../management-shell.md).</span></span>
  
## <a name="create-a-new-room"></a><span data-ttu-id="629a9-171">创建新聊天室</span><span class="sxs-lookup"><span data-stu-id="629a9-171">Create a new room</span></span>

<span data-ttu-id="629a9-172">您可以使用 **New-CsPersistentChatRoom** cmdlet 创建新聊天室。</span><span class="sxs-lookup"><span data-stu-id="629a9-172">You can create a new room by using the **New-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="629a9-173">例如，以下命令在池池上创建一个名为 ITChatRoom 的新atl-cs-001.contoso.com。</span><span class="sxs-lookup"><span data-stu-id="629a9-173">For example, the following command creates a new chat room named ITChatRoom on the pool atl-cs-001.contoso.com.</span></span> <span data-ttu-id="629a9-174">本示例将聊天室添加到 IT 类别：</span><span class="sxs-lookup"><span data-stu-id="629a9-174">In this example, the chat room is added to the IT category:</span></span>
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

<span data-ttu-id="629a9-175">**注意：** 如果为以下情况之一，则不需要 PersistentChatPoolFqdn：</span><span class="sxs-lookup"><span data-stu-id="629a9-175">**Note:** PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
  
- <span data-ttu-id="629a9-176">只有一个持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="629a9-176">There is only one Persistent Chat Server pool.</span></span>
    
- <span data-ttu-id="629a9-177">您为类别提供了一个池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="629a9-177">You provide a pool FQDN to the category.</span></span>
    
- <span data-ttu-id="629a9-178">您提供了一个池 Fqdn 以添加聊天室。</span><span class="sxs-lookup"><span data-stu-id="629a9-178">You provide a pool FQDN to adding the room.</span></span>
    
## <a name="configure-an-existing-room"></a><span data-ttu-id="629a9-179">配置现有聊天室</span><span class="sxs-lookup"><span data-stu-id="629a9-179">Configure an existing room</span></span>

<span data-ttu-id="629a9-180">可以使用 **Set-CsPersistentChatRoom** cmdlet 配置现有聊天室。</span><span class="sxs-lookup"><span data-stu-id="629a9-180">You can configure an existing room by using the **Set-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="629a9-181">例如，以下命令将 user1 分配为 testCat Auditorium 会议室的成员和演示者，并将 user2 分配为经理：</span><span class="sxs-lookup"><span data-stu-id="629a9-181">For example, the following command assigns user1 as a Member and Presenter, and user2 as a Manager, of the testCat Auditorium room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 <span data-ttu-id="629a9-182">下一个示例将 Active Directory 中 NorthAmericaUsers OU 的所有用户添加到 NorthAmerica 聊天室：</span><span class="sxs-lookup"><span data-stu-id="629a9-182">The next example adds all the users from the NorthAmericaUsers OU in active Directory to the NorthAmerica chat room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

<span data-ttu-id="629a9-183">下一个示例将 Finance 通讯组的所有成员添加到同一聊天室：</span><span class="sxs-lookup"><span data-stu-id="629a9-183">The next example adds all the members from the Finance distribution group to the same chat room:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a><span data-ttu-id="629a9-184">禁用或启用聊天室</span><span class="sxs-lookup"><span data-stu-id="629a9-184">Disable or enable a room</span></span>

<span data-ttu-id="629a9-185">如果持久聊天室的主题不再相关，您可以通过禁用该聊天室来使用户无法使用该聊天室。</span><span class="sxs-lookup"><span data-stu-id="629a9-185">If the topic of a Persistent Chat room is no longer relevant, you can make the chat room unavailable to users by disabling it.</span></span> <span data-ttu-id="629a9-186">禁用聊天室后，所有成员将立即与聊天室断开连接。</span><span class="sxs-lookup"><span data-stu-id="629a9-186">When a chat room is disabled, all members are immediately disconnected from the room.</span></span> <span data-ttu-id="629a9-187">禁用聊天室后，用户将无法重新加入该聊天室或在聊天室搜索中查找该聊天室。</span><span class="sxs-lookup"><span data-stu-id="629a9-187">After a chat room is disabled, users cannot rejoin it or find it in chat room searches.</span></span>
  
<span data-ttu-id="629a9-188">如果聊天室的历史记录仍然存在，则禁用该聊天室时将保留该内容。</span><span class="sxs-lookup"><span data-stu-id="629a9-188">If the chat room's history persists, the content is preserved when the chat room is disabled.</span></span> <span data-ttu-id="629a9-189">但是，在聊天室保持禁用状态期间，该内容不会显示在搜索中。</span><span class="sxs-lookup"><span data-stu-id="629a9-189">However, that content will not appear in searches during the time that the chat room remains in a disabled state.</span></span> <span data-ttu-id="629a9-190">如果稍后启用聊天室，则用户可以搜索在禁用聊天室之前发布的消息。</span><span class="sxs-lookup"><span data-stu-id="629a9-190">If you later enable the chat room, users can search for messages that were posted before the chat room was disabled.</span></span> <span data-ttu-id="629a9-191">有关配置聊天室历史记录的信息，请参阅 [在 Skype for Business Server 2015](categories.md)中管理持久聊天服务器中的类别。</span><span class="sxs-lookup"><span data-stu-id="629a9-191">For information about configuring chat room history, see [Manage categories in Persistent Chat Server in Skype for Business Server 2015](categories.md).</span></span> 
  
<span data-ttu-id="629a9-192">禁用某聊天室时，将保留其成员身份列表和其他设置。</span><span class="sxs-lookup"><span data-stu-id="629a9-192">If a chat room is disabled, its membership list and other settings are preserved.</span></span> <span data-ttu-id="629a9-193">作为管理员，您可以启用已禁用的聊天室，并且无需手动重新创建设置。</span><span class="sxs-lookup"><span data-stu-id="629a9-193">As an administrator, you can enable a room that has been disabled, and you do not need to manually re-create the settings.</span></span>
  
<span data-ttu-id="629a9-194">可以使用 **Set-CsPersistentChatRoom** cmdlet 将 Disabled 参数设置为 True 来禁用聊天室：</span><span class="sxs-lookup"><span data-stu-id="629a9-194">You can disable a room by using the **Set-CsPersistentChatRoom** cmdlet and setting the Disabled parameter to True:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

<span data-ttu-id="629a9-195">若要启用聊天室，将 Disabled 参数设置为 False：</span><span class="sxs-lookup"><span data-stu-id="629a9-195">To enable a chat room, set the Disabled parameter to False:</span></span>
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a><span data-ttu-id="629a9-196">获取有关聊天室的信息</span><span class="sxs-lookup"><span data-stu-id="629a9-196">Get information about rooms</span></span>

<span data-ttu-id="629a9-197">若要获取有关配置为在组织使用的聊天室的信息，可以使用 **Get-CsPersistentChatRoom** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="629a9-197">To get information about the rooms configured for use in your organization, you can use the **Get-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="629a9-198">以下命令返回有关配置为在组织使用的所有聊天室的信息：</span><span class="sxs-lookup"><span data-stu-id="629a9-198">The following command returns information about all the chat rooms configured for use in the organization:</span></span>
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a><span data-ttu-id="629a9-199">从聊天室中删除所有内容</span><span class="sxs-lookup"><span data-stu-id="629a9-199">Remove all content from a room</span></span>

<span data-ttu-id="629a9-200">您可以使用 **Clear-CsPersistentChatRoom** cmdlet 从聊天室中删除内容。</span><span class="sxs-lookup"><span data-stu-id="629a9-200">You can remove content from a room by using the **Clear-CsPersistentChatRoom** cmdlet.</span></span> <span data-ttu-id="629a9-201">例如，以下命令从持久聊天室 ITChatRoom 中删除在 2015 年 3 月 1 日或之前添加到聊天室的所有内容：</span><span class="sxs-lookup"><span data-stu-id="629a9-201">For example, the following command removes all the content from the Persistent Chat room ITChatRoom that was added to the room on or before March 1, 2015:</span></span>
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a><span data-ttu-id="629a9-202">从聊天室中删除邮件</span><span class="sxs-lookup"><span data-stu-id="629a9-202">Remove a message from a room</span></span>

<span data-ttu-id="629a9-203">您可以使用 **Remove-CsPersistentChatMessage** cmdlet 删除持久聊天数据库中的一个或多个消息，也可以选择将消息替换为默认消息或管理员提供的消息。</span><span class="sxs-lookup"><span data-stu-id="629a9-203">You can remove one or more messages in the Persistent Chat database, and optionally replace the message with a default message or with an administrator-provided message, by using the **Remove-CsPersistentChatMessage** cmdlet.</span></span> <span data-ttu-id="629a9-204">例如，以下命令从 ITChatRoom 聊天室中删除用户发布的所有kenmyer@contoso.com：</span><span class="sxs-lookup"><span data-stu-id="629a9-204">For example, the following command removes all the messages from the ITChatRoom chat room that were posted by the user kenmyer@contoso.com:</span></span>
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

<span data-ttu-id="629a9-205">下一个示例将删除的任何邮件替换为该邮件不再可用的注释：</span><span class="sxs-lookup"><span data-stu-id="629a9-205">The next example replaces any removed messages with the note that the message is no longer available:</span></span>
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a><span data-ttu-id="629a9-206">删除聊天室</span><span class="sxs-lookup"><span data-stu-id="629a9-206">Remove a room</span></span>

<span data-ttu-id="629a9-207">可以使用 **Remove-CsPersistentChatRoom** cmdlet 删除聊天室。</span><span class="sxs-lookup"><span data-stu-id="629a9-207">You can remove a room by using the **Remove-CsPersistentChatRoom** cmdlet.</span></span>
  
<span data-ttu-id="629a9-208">例如，以下命令删除聊天室 RedmondChatRoom：</span><span class="sxs-lookup"><span data-stu-id="629a9-208">For example, the following command removes the chat room RedmondChatRoom:</span></span>
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a><span data-ttu-id="629a9-209">将聊天室从一个类别移动到另一个类别</span><span class="sxs-lookup"><span data-stu-id="629a9-209">Move a room from one category to another</span></span>

<span data-ttu-id="629a9-210">如果聊天室管理员在另一个类别中具有 **Creator** 权限，则他/她可以将聊天室从一个类别移动到另一个类别。</span><span class="sxs-lookup"><span data-stu-id="629a9-210">If a chat room manager has **Creator** privileges in another category, he or she can move the room from one category to another.</span></span> <span data-ttu-id="629a9-211">将不会删除和重新创建该聊天室。</span><span class="sxs-lookup"><span data-stu-id="629a9-211">The room is not deleted and recreated.</span></span> <span data-ttu-id="629a9-212">这是数据库中的关联的更改。</span><span class="sxs-lookup"><span data-stu-id="629a9-212">It is a change of association within the database.</span></span>
  
<span data-ttu-id="629a9-213">应很少和谨慎更改聊天室类别。</span><span class="sxs-lookup"><span data-stu-id="629a9-213">Changing a chat room category should be done rarely and with caution.</span></span> <span data-ttu-id="629a9-214">类别用于确定聊天室允许的成员身份，因此当聊天室移动到另一个类别时，新类别不再支持的所有系统访问控制列表 (SACL) 都将清除。</span><span class="sxs-lookup"><span data-stu-id="629a9-214">A category determines the allowed membership for the chat room, so when a chat room is moved to another category, all the system access control lists (SACLs) that are no longer supported by the new category are purged.</span></span> <span data-ttu-id="629a9-215">例如，如果用户是聊天室的成员，并且不再是新类别中的允许成员，将修改聊天室成员身份，并且将从聊天室中删除该用户。</span><span class="sxs-lookup"><span data-stu-id="629a9-215">For example, if a user was a member of the room and is no longer an allowed member in the new category, the room membership will be modified and the user will be removed from the room.</span></span>
  

