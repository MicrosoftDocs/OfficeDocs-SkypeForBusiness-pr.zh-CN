---
title: Skype for Business Server 2015 中的持久聊天类别、聊天室和用户角色
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 摘要：阅读本主题，了解 Skype for Business Server 2015 中持久聊天服务器的类别、聊天室以及用户和管理员角色。
ms.openlocfilehash: 50b5cd6df9cbaa8958d0f1036fe5474f2d7e47dc
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834562"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a><span data-ttu-id="0047a-103">Skype for Business Server 2015 中的持久聊天类别、聊天室和用户角色</span><span class="sxs-lookup"><span data-stu-id="0047a-103">Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0047a-104">**摘要：** 阅读本主题，了解 Skype for Business Server 2015 中持久聊天服务器的类别、聊天室以及用户和管理员角色。</span><span class="sxs-lookup"><span data-stu-id="0047a-104">**Summary:** Read this topic to learn about categories, chat rooms, and user and administrator roles for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="0047a-105">您可以通过创建聊天室类别，然后指定对类别中的类别和聊天室的访问权限来控制对聊天室的访问。</span><span class="sxs-lookup"><span data-stu-id="0047a-105">You can control access to chat rooms by creating chat room categories, then specifying access to categories and chat rooms within categories.</span></span> <span data-ttu-id="0047a-106">还可以指定各种管理员角色。</span><span class="sxs-lookup"><span data-stu-id="0047a-106">You can also specify various administrator roles.</span></span> <span data-ttu-id="0047a-107">本主题介绍：</span><span class="sxs-lookup"><span data-stu-id="0047a-107">This topic describes:</span></span> 
  
- <span data-ttu-id="0047a-108">用于组织聊天室的类别</span><span class="sxs-lookup"><span data-stu-id="0047a-108">Categories for organizing chat rooms</span></span>
    
- <span data-ttu-id="0047a-109">聊天室和用户角色</span><span class="sxs-lookup"><span data-stu-id="0047a-109">Chat rooms and user roles</span></span>
    
- <span data-ttu-id="0047a-110">管理员角色</span><span class="sxs-lookup"><span data-stu-id="0047a-110">Administrator roles</span></span>

> [!NOTE] 
> <span data-ttu-id="0047a-111">持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。</span><span class="sxs-lookup"><span data-stu-id="0047a-111">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="0047a-112">Teams 中也提供相同的功能。</span><span class="sxs-lookup"><span data-stu-id="0047a-112">The same functionality is available in Teams.</span></span> <span data-ttu-id="0047a-113">有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。</span><span class="sxs-lookup"><span data-stu-id="0047a-113">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="0047a-114">如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="0047a-114">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
    
## <a name="categories-for-organizing-chat-rooms"></a><span data-ttu-id="0047a-115">用于组织聊天室的类别</span><span class="sxs-lookup"><span data-stu-id="0047a-115">Categories for organizing chat rooms</span></span>

<span data-ttu-id="0047a-116">类别使你可以组织聊天室并控制允许哪些用户和组创建或加入这些类别中的聊天室。</span><span class="sxs-lookup"><span data-stu-id="0047a-116">Categories let you organize chat rooms and control which users and groups are permitted to create or join the chat rooms within those categories.</span></span> <span data-ttu-id="0047a-117">每个类别都有关联的属性，这些属性确定可用于类别中的聊天室的选项。</span><span class="sxs-lookup"><span data-stu-id="0047a-117">Each category has associated properties that determine the options available for the chat rooms within the category.</span></span> <span data-ttu-id="0047a-118">通过指定用户是允许访问还是拒绝访问，可以控制对特定类别的访问。</span><span class="sxs-lookup"><span data-stu-id="0047a-118">You control access to a particular category by specifying whether a user is Allowed or Denied access.</span></span>
  
<span data-ttu-id="0047a-119">"允许"和"拒绝的成员"概念的主要原理是信息墙。</span><span class="sxs-lookup"><span data-stu-id="0047a-119">The primary rationale for the concept of Allowed and Denied Members is ethical walls.</span></span> <span data-ttu-id="0047a-120">例如，银行和财务机构通常设立了阻止贸易商和分析师在实施策略和约定时共享通信的信息隔离区域。</span><span class="sxs-lookup"><span data-stu-id="0047a-120">For example, it is common in banking and financial institutions to have ethical boundaries that prevent traders and analysts from sharing communications while implementing policies and conventions.</span></span> <span data-ttu-id="0047a-121">若要满足此要求，管理员可以创建相应类别，以便一个类别允许创建聊天室并允许贸易商使用该聊天室，而另一个类别允许创建聊天室并允许分析师使用该聊天室。</span><span class="sxs-lookup"><span data-stu-id="0047a-121">To address this requirement, an administrator can create categories so that one category allows rooms to be created and used by traders, and another category allows rooms to be created and used by analysts.</span></span> <span data-ttu-id="0047a-122">如果父类别阻止了用户，则不能将用户添加为聊天室的成员。</span><span class="sxs-lookup"><span data-stu-id="0047a-122">Users cannot be added as a member of a chat room if the parent category prevents it.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0047a-123">类别中允许和拒绝的成员与成员角色不同，该角色适用于持久聊天室。> 搜索功能显示执行搜索的用户位于其"允许"和"拒绝"成员列表中的所有开放和关闭的聊天室。</span><span class="sxs-lookup"><span data-stu-id="0047a-123">Allowed and Denied members in a category are not the same as a **Member** role, which applies to a Persistent Chat room.> Searches display all open and closed chat rooms for which the user performing the search is in the Allowed and Denied member list.</span></span> <span data-ttu-id="0047a-124">不会显示加密聊天室，除非进行搜索的用户是加密聊天室的成员。</span><span class="sxs-lookup"><span data-stu-id="0047a-124">Secret rooms are not displayed unless the user who performs the search is a member of the secret room.</span></span> <span data-ttu-id="0047a-125">用户只能搜索自己已经是其成员的聊天室，或者他们可以请求成员身份的聊天室。</span><span class="sxs-lookup"><span data-stu-id="0047a-125">The user can search only for rooms that he or she is already a member of, or those for which they can request membership.</span></span> 
  
## <a name="chat-rooms-and-user-roles"></a><span data-ttu-id="0047a-126">聊天室和用户角色</span><span class="sxs-lookup"><span data-stu-id="0047a-126">Chat rooms and user roles</span></span>

<span data-ttu-id="0047a-127">除了类别允许和拒绝的成员之外，您还可以通过指定以下用户角色来控制对聊天室的访问：Creator、Manager、Member 和 Presenter。</span><span class="sxs-lookup"><span data-stu-id="0047a-127">In addition to Allowed and Denied Members for categories, you can also control access to chat rooms by specifying the following user roles: Creator, Manager, Member, and Presenter.</span></span>
  
- <span data-ttu-id="0047a-128">**创建者**：有权创建聊天室的用户。</span><span class="sxs-lookup"><span data-stu-id="0047a-128">**Creator**: Users who have permission to create chat rooms.</span></span> <span data-ttu-id="0047a-129">这些用户位于特定类别的“创建者”列表中：他们可以在该类别中创建聊天室，还可以根据该类别分配成员身份，以及指派管理员管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="0047a-129">These users are in the Creators list of certain categories: they can create chat rooms in that category, and they can also assign membership according to the category, and assign managers to manage the chat room.</span></span> <span data-ttu-id="0047a-130">创建聊天室的用户将自动添加为聊天室的管理员。</span><span class="sxs-lookup"><span data-stu-id="0047a-130">The user who creates a chat room is automatically added as a manager of the room.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="0047a-p107">成为创建者仅仅为其提供创建聊天室的权限。通过自动升级为管理员，创建者才能够在已创建的聊天服务中进一步细化成员身份、管理员等等。</span><span class="sxs-lookup"><span data-stu-id="0047a-p107">Being a Creator simply provides rights for creating chat rooms. It is the automatic promotion to Manager that enables the Creator to further refine memberships, managers, and so on, on the created chat services.</span></span> 
  
    <span data-ttu-id="0047a-133">此角色使您能够控制在您的组织中创建聊天室的用户，尤其是当您要集中管理聊天室创建活动以强制实施策略和约定并且随后将聊天室管理权委派给组织中的其他用户时。</span><span class="sxs-lookup"><span data-stu-id="0047a-133">This role exists to give you the option of controlling who creates chat rooms in your organization, particularly if you want to centrally manage creating chat rooms to enforce policies and conventions, and subsequently delegate the chat room management to other users in the organization.</span></span>
    
- <span data-ttu-id="0047a-134">**管理员**：管理聊天室属性的用户。</span><span class="sxs-lookup"><span data-stu-id="0047a-134">**Manager**: Users who manage properties of a chat room.</span></span> <span data-ttu-id="0047a-135">聊天室管理员可以修改成员列表（添加和移除成员），以及修改聊天室管理员列表（添加和移除管理员）。</span><span class="sxs-lookup"><span data-stu-id="0047a-135">Chat room managers can modify the member list (add and remove members), and modify the chat room managers list (add and remove managers).</span></span> <span data-ttu-id="0047a-136">聊天室管理员可以将自己添加到成员或演示者列表（对于大会堂聊天室）中以便他们可以加入聊天室。</span><span class="sxs-lookup"><span data-stu-id="0047a-136">Chat room managers can add themselves to the members or presenters list (for auditorium rooms) so they can participate in the chat room.</span></span> <span data-ttu-id="0047a-137">聊天室管理员还可以禁用聊天室（管理员可查询已禁用聊天室且可以将其永久删除）。</span><span class="sxs-lookup"><span data-stu-id="0047a-137">Chat room managers can also disable chat rooms (administrators can query for disabled chat rooms and can permanently delete them).</span></span> <span data-ttu-id="0047a-138">除聊天室的类别外，管理员可以更改聊天室的所有属性。</span><span class="sxs-lookup"><span data-stu-id="0047a-138">Managers can change all the properties of a chat room, except the category of the chat room.</span></span> <span data-ttu-id="0047a-139">只有持久聊天管理员可以在聊天室创建后更改类别。</span><span class="sxs-lookup"><span data-stu-id="0047a-139">Only the Persistent Chat Administrator can change the category after the chat room has been created.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="0047a-140">如果该管理员还是其他类别的创建者，则他/她可以更改该类别以使自己有权创建聊天室。</span><span class="sxs-lookup"><span data-stu-id="0047a-140">If the manager is also a Creator in another category, he or she can change the category to one where they are authorized to create rooms.</span></span> 
  
- <span data-ttu-id="0047a-141">**成员**：作为聊天室成员的用户。</span><span class="sxs-lookup"><span data-stu-id="0047a-141">**Member**: Users who are members of a chat room.</span></span> <span data-ttu-id="0047a-142">即使聊天室是机密) ，这些用户也可以查看目录 (中的聊天室，也可以订阅聊天室 (包括元数据选项（如未读消息、自我筛选器和关键字筛选器) ）并参与聊天室 (可以发布的内容，除非该聊天室是只有演示者可以发布、获取内容和搜索) 的大会堂聊天室。</span><span class="sxs-lookup"><span data-stu-id="0047a-142">These users can see the chat rooms in the directory (even if the chat room is secret), as well as subscribe to the chat room (including metadata options such as unread messages, ego filters, and keyword filters), and participate in the chat room (can post, unless the room is an auditorium room where only presenters can post, get content, and search).</span></span> <span data-ttu-id="0047a-143">不是聊天室成员的用户可以搜索聊天室（如果他们位于类别的"允许的成员"列表中，但需要请求访问才能加入这些聊天室来访问内容）。</span><span class="sxs-lookup"><span data-stu-id="0047a-143">Users who aren't members of the chat room can search for the chat room if they are in the Allowed Members list of the category, but need to request access to join these chat rooms to access content.</span></span> <span data-ttu-id="0047a-144"> (系统中没有内置的请求访问或审批;这些操作通过电子邮件、电话或其他形式的联系人在外部) </span><span class="sxs-lookup"><span data-stu-id="0047a-144">(There is no request access or approvals built into the system; these are done externally by email, phone, or other forms of contact.)</span></span>
    
- <span data-ttu-id="0047a-145">**演示者**：可以在大会堂聊天室发布消息的用户。</span><span class="sxs-lookup"><span data-stu-id="0047a-145">**Presenter**: Users who can post to an auditorium room.</span></span>
    
## <a name="administrator-roles"></a><span data-ttu-id="0047a-146">管理员角色</span><span class="sxs-lookup"><span data-stu-id="0047a-146">Administrator roles</span></span>

<span data-ttu-id="0047a-147">以下是持久聊天服务器的管理员角色：</span><span class="sxs-lookup"><span data-stu-id="0047a-147">The following are administrator roles for Persistent Chat Server:</span></span>
  
- <span data-ttu-id="0047a-148">持久聊天管理员：持久聊天管理员角色可以管理聊天室 (修改所有属性，包括成员身份、管理员、类别、将聊天室标记为禁用) ，以及创建和管理定义可以创建和访问聊天室的聊天室类别。</span><span class="sxs-lookup"><span data-stu-id="0047a-148">**Persistent Chat Administrator**: The Persistent Chat Administrator role can manage chat rooms (modify all properties including membership, managers, categories, mark rooms as disabled), as well as create and manage chat room categories that define who can create and access chat rooms.</span></span> <span data-ttu-id="0047a-149">管理员还可以将聊天室标记为禁用并清理不再处于活动状态的聊天室。</span><span class="sxs-lookup"><span data-stu-id="0047a-149">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span></span> <span data-ttu-id="0047a-150">管理员不会受到“创建者”或“允许的成员”限制的影响。</span><span class="sxs-lookup"><span data-stu-id="0047a-150">Administrators are not subject to the Creators or Allowed Members restrictions.</span></span> <span data-ttu-id="0047a-151">管理员可以创建任何类型的聊天室以及将自己添加为任何聊天室的成员。</span><span class="sxs-lookup"><span data-stu-id="0047a-151">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span></span> <span data-ttu-id="0047a-152">管理员还可以修改和管理持久聊天配置 (池属性、全局设置和合规性配置) ，还可以规划和实施从较旧的群聊服务器部署到 Skype for Business Server 2015 持久聊天服务器的迁移。</span><span class="sxs-lookup"><span data-stu-id="0047a-152">Administrators can also modify and manage Persistent Chat configuration (pool properties, global settings, and compliance configuration) and can also plan and implement migration from an older Group Chat Server deployment to Skype for Business Server 2015 Persistent Chat Server.</span></span>
    
    <span data-ttu-id="0047a-153">持久聊天管理员能够通过远程使用 Windows PowerShell cmdlet（即从持久聊天服务器 (计算机而不是持久聊天服务器) ）来管理持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="0047a-153">Persistent Chat Administrators are able to administer Persistent Chat Server by using Windows PowerShell cmdlets remotely (that is, from a computer other than the Persistent Chat Server).</span></span> <span data-ttu-id="0047a-154">持久聊天服务器检查持久聊天管理员是持久聊天服务器前端服务器上 RTC 本地管理员本地组的成员。</span><span class="sxs-lookup"><span data-stu-id="0047a-154">Persistent Chat Server checks that the Persistent Chat Administrator is a member of the RTC Local administrator local group on the Persistent Chat Server Front End Server.</span></span>
    
- <span data-ttu-id="0047a-155">**Skype for Business Server 2015 管理员**：负责部署的 Skype for Business Server 2015 的整体企业管理员。</span><span class="sxs-lookup"><span data-stu-id="0047a-155">**Skype for Business Server 2015 Administrator**: Overall enterprise administrator for Skype for Business Server 2015 responsible for deployment.</span></span>
    
- <span data-ttu-id="0047a-156">**操作管理员**：负责管理日常操作的用户。</span><span class="sxs-lookup"><span data-stu-id="0047a-156">**Operations Manager**: User responsible for managing day-to-day operations.</span></span>
    
- <span data-ttu-id="0047a-157">**第三方开发人员和合作伙伴**：第三方开发人员可扩展系统，特别是针对组会话、合规性支持和工具、Web/移动客户端和自动程序开发框架提供信息隔离墙解决方案。</span><span class="sxs-lookup"><span data-stu-id="0047a-157">**Third-party developers and partners**: Third-party developers extend the system, in particular providing an ethical wall solution for group conversations, compliance support and tools, web/mobile clients, and a framework for Bot development.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="0047a-158">详细信息</span><span class="sxs-lookup"><span data-stu-id="0047a-158">For more information</span></span>

<span data-ttu-id="0047a-159">有关配置和管理聊天室和用户角色详细信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="0047a-159">For more information about configuring and managing chat rooms and user roles, see the following topics:</span></span>
  
- [<span data-ttu-id="0047a-160">在 Skype for Business Server 2015 中创建持久聊天管理员</span><span class="sxs-lookup"><span data-stu-id="0047a-160">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [<span data-ttu-id="0047a-161">在 Skype for Business Server 2015 中管理持久聊天服务器中的类别</span><span class="sxs-lookup"><span data-stu-id="0047a-161">Manage categories in Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/categories.md)
    
- [<span data-ttu-id="0047a-162">在 Skype for Business Server 2015 中管理持久聊天服务器中的聊天室</span><span class="sxs-lookup"><span data-stu-id="0047a-162">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/chat-rooms.md)
    

