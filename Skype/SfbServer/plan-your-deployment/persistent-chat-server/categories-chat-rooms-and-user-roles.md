---
title: Skype for Business Server 2015 中的持久聊天类别、聊天室和用户角色
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 摘要： 请阅读本主题，以了解有关类别，聊天室和用户和管理员角色在 Skype 的持久聊天服务器的业务服务器 2015年。
ms.openlocfilehash: 73c7bd8863ba9560b8ef7d79b3e5dce1fbd797a1
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a><span data-ttu-id="7547c-103">Skype for Business Server 2015 中的持久聊天类别、聊天室和用户角色</span><span class="sxs-lookup"><span data-stu-id="7547c-103">Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7547c-104">**摘要：**阅读本主题可了解类别，聊天室和用户和管理员角色在 Skype 的持久聊天服务器的业务服务器 2015年。</span><span class="sxs-lookup"><span data-stu-id="7547c-104">**Summary:** Read this topic to learn about categories, chat rooms, and user and administrator roles for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="7547c-105">您可以控制聊天室的访问，方法是创建聊天室类别，然后指定类别以及类别中的聊天室的访问权限。</span><span class="sxs-lookup"><span data-stu-id="7547c-105">You can control access to chat rooms by creating chat room categories, then specifying access to categories and chat rooms within categories.</span></span> <span data-ttu-id="7547c-106">您也可以指定各种管理员角色。</span><span class="sxs-lookup"><span data-stu-id="7547c-106">You can also specify various administrator roles.</span></span> <span data-ttu-id="7547c-107">本主题介绍了：</span><span class="sxs-lookup"><span data-stu-id="7547c-107">This topic describes:</span></span> 
  
- <span data-ttu-id="7547c-108">用于组织聊天室的类别</span><span class="sxs-lookup"><span data-stu-id="7547c-108">Categories for organizing chat rooms</span></span>
    
- <span data-ttu-id="7547c-109">聊天室和用户角色</span><span class="sxs-lookup"><span data-stu-id="7547c-109">Chat rooms and user roles</span></span>
    
- <span data-ttu-id="7547c-110">管理员角色</span><span class="sxs-lookup"><span data-stu-id="7547c-110">Administrator roles</span></span>
    
## <a name="categories-for-organizing-chat-rooms"></a><span data-ttu-id="7547c-111">用于组织聊天室的类别</span><span class="sxs-lookup"><span data-stu-id="7547c-111">Categories for organizing chat rooms</span></span>

<span data-ttu-id="7547c-112">类别允许您组织聊天室并控制可创建或加入这些类别中的聊天室的用户和组。</span><span class="sxs-lookup"><span data-stu-id="7547c-112">Categories let you organize chat rooms and control which users and groups are permitted to create or join the chat rooms within those categories.</span></span> <span data-ttu-id="7547c-113">每个类别都具有关联的属性，这些属性决定了可用于该类别中的聊天室的选项。</span><span class="sxs-lookup"><span data-stu-id="7547c-113">Each category has associated properties that determine the options available for the chat rooms within the category.</span></span> <span data-ttu-id="7547c-114">您可控制特定类别的访问权限，方法是指定“允许”或“拒绝”用户的访问权限。</span><span class="sxs-lookup"><span data-stu-id="7547c-114">You control access to a particular category by specifying whether a user is Allowed or Denied access.</span></span>
  
<span data-ttu-id="7547c-p103">“允许”和“拒绝”的成员概念的主要原理是信息隔离墙。例如，银行和财务机构通常设立了阻止贸易商和分析师在实施策略和约定时共享通信的信息隔离区域。若要满足此要求，管理员可以创建相应类别，以便一个类别允许创建聊天室并允许贸易商使用该聊天室，而另一个类别允许创建聊天室并允许分析师使用该聊天室。父类别阻止某用户时，将无法把该用户添加为聊天室的成员。</span><span class="sxs-lookup"><span data-stu-id="7547c-p103">The primary rationale for the concept of Allowed and Denied Members is ethical walls. For example, it is common in banking and financial institutions to have ethical boundaries that prevent traders and analysts from sharing communications while implementing policies and conventions. To address this requirement, an administrator can create categories so that one category allows rooms to be created and used by traders, and another category allows rooms to be created and used by analysts. Users cannot be added as a member of a chat room if the parent category prevents it.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7547c-119">允许和拒绝的成员类别中没有相同**成员**的角色，它适用于持久性聊天室。 > 搜索显示所有打开和关闭聊天室用户执行的搜索是在允许和拒绝成员列表中。</span><span class="sxs-lookup"><span data-stu-id="7547c-119">Allowed and Denied members in a category are not the same as a **Member** role, which applies to a Persistent Chat room.> Searches display all open and closed chat rooms for which the user performing the search is in the Allowed and Denied member list.</span></span> <span data-ttu-id="7547c-120">不会显示加密聊天室，除非进行搜索的用户是加密聊天室的成员。</span><span class="sxs-lookup"><span data-stu-id="7547c-120">Secret rooms are not displayed unless the user who performs the search is a member of the secret room.</span></span> <span data-ttu-id="7547c-121">用户只能搜索自己已经是其成员的聊天室，或者他们可以请求成员身份的聊天室。</span><span class="sxs-lookup"><span data-stu-id="7547c-121">The user can search only for rooms that he or she is already a member of, or those for which they can request membership.</span></span> 
  
## <a name="chat-rooms-and-user-roles"></a><span data-ttu-id="7547c-122">聊天室和用户角色</span><span class="sxs-lookup"><span data-stu-id="7547c-122">Chat rooms and user roles</span></span>

<span data-ttu-id="7547c-123">除了允许和拒绝的成员类别，您还可以控制对聊天室的访问通过指定下面的用户角色： 创建者、 经理、 成员、 和演示者。</span><span class="sxs-lookup"><span data-stu-id="7547c-123">In addition to Allowed and Denied Members for categories, you can also control access to chat rooms by specifying the following user roles: Creator, Manager, Member, and Presenter.</span></span>
  
- <span data-ttu-id="7547c-p105">**创建者**：有权创建聊天室的用户。这些用户位于特定类别的“创建者”列表中：他们可以创建该类别的聊天室，还可以根据该类别分配成员身份，以及指派管理员管理聊天室。创建聊天室的用户将自动添加为聊天室的管理员。</span><span class="sxs-lookup"><span data-stu-id="7547c-p105">**Creator**: Users who have permission to create chat rooms. These users are in the Creators list of certain categories: they can create chat rooms in that category, and they can also assign membership according to the category, and assign managers to manage the chat room. The user who creates a chat room is automatically added as a manager of the room.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="7547c-p106">成为创建者仅仅为其提供创建聊天室的权限。通过自动升级为管理员，创建者才能够在已创建的聊天服务中进一步细化成员身份、管理员等等。</span><span class="sxs-lookup"><span data-stu-id="7547c-p106">Being a Creator simply provides rights for creating chat rooms. It is the automatic promotion to Manager that enables the Creator to further refine memberships, managers, and so on, on the created chat services.</span></span> 
  
    <span data-ttu-id="7547c-129">此角色使您能够控制在您的组织中创建聊天室的用户，尤其是当您要集中管理聊天室创建活动以强制实施策略和约定并且随后将聊天室管理权委派给组织中的其他用户时。</span><span class="sxs-lookup"><span data-stu-id="7547c-129">This role exists to give you the option of controlling who creates chat rooms in your organization, particularly if you want to centrally manage creating chat rooms to enforce policies and conventions, and subsequently delegate the chat room management to other users in the organization.</span></span>
    
- <span data-ttu-id="7547c-130">**管理者**：管理聊天室属性的用户。</span><span class="sxs-lookup"><span data-stu-id="7547c-130">**Manager**: Users who manage properties of a chat room.</span></span> <span data-ttu-id="7547c-131">聊天室管理员可以修改成员列表（添加和移除成员），以及修改聊天室管理员列表（添加和移除管理员）。</span><span class="sxs-lookup"><span data-stu-id="7547c-131">Chat room managers can modify the member list (add and remove members), and modify the chat room managers list (add and remove managers).</span></span> <span data-ttu-id="7547c-132">聊天室管理员可以将自己添加到成员或演示者列表（对于大会堂聊天室）中以便他们可以加入聊天室。</span><span class="sxs-lookup"><span data-stu-id="7547c-132">Chat room managers can add themselves to the members or presenters list (for auditorium rooms) so they can participate in the chat room.</span></span> <span data-ttu-id="7547c-133">聊天室管理员还可以禁用聊天室（管理员可查询已禁用聊天室且可以将其永久删除）。</span><span class="sxs-lookup"><span data-stu-id="7547c-133">Chat room managers can also disable chat rooms (administrators can query for disabled chat rooms and can permanently delete them).</span></span> <span data-ttu-id="7547c-134">除聊天室的类别外，管理员可以更改聊天室的所有属性。</span><span class="sxs-lookup"><span data-stu-id="7547c-134">Managers can change all the properties of a chat room, except the category of the chat room.</span></span> <span data-ttu-id="7547c-135">在创建聊天室后，仅持续聊天管理员可以更改的类别。</span><span class="sxs-lookup"><span data-stu-id="7547c-135">Only the Persistent Chat Administrator can change the category after the chat room has been created.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="7547c-136">如果该管理员还是其他类别的创建者，则他/她可以更改该类别以使自己有权创建聊天室。</span><span class="sxs-lookup"><span data-stu-id="7547c-136">If the manager is also a Creator in another category, he or she can change the category to one where they are authorized to create rooms.</span></span> 
  
- <span data-ttu-id="7547c-137">**成员**： 聊天室的成员的用户。</span><span class="sxs-lookup"><span data-stu-id="7547c-137">**Member**: Users who are members of a chat room.</span></span> <span data-ttu-id="7547c-138">这些用户可以查看目录中的聊天室 （即使聊天室是秘密），以及订阅 （包括元数据的选项，如未读的邮件、 ego 筛选和关键字筛选器） 的聊天室，和参与聊天室 (可以过帐时，除非该文件室是大会堂会议室仅演示者可以发布、 获取内容，和搜索）。</span><span class="sxs-lookup"><span data-stu-id="7547c-138">These users can see the chat rooms in the directory (even if the chat room is secret), as well as subscribe to the chat room (including metadata options such as unread messages, ego filters, and keyword filters), and participate in the chat room (can post, unless the room is an auditorium room where only presenters can post, get content, and search).</span></span> <span data-ttu-id="7547c-139">不是聊天室的成员的用户可以搜索聊天室，如果它们的类别，允许的成员列表中，但需要申请加入这些聊天室来访问内容的访问权限。</span><span class="sxs-lookup"><span data-stu-id="7547c-139">Users who aren't members of the chat room can search for the chat room if they are in the Allowed Members list of the category, but need to request access to join these chat rooms to access content.</span></span> <span data-ttu-id="7547c-140">（没有任何请求访问或内置于系统的批准; 它们通过电子邮件、 电话或其它形式的联系人外部完成）。</span><span class="sxs-lookup"><span data-stu-id="7547c-140">(There is no request access or approvals built into the system; these are done externally by email, phone, or other forms of contact.)</span></span>
    
- <span data-ttu-id="7547c-141">**演示者**：可以在大会堂聊天室发布消息的用户。</span><span class="sxs-lookup"><span data-stu-id="7547c-141">**Presenter**: Users who can post to an auditorium room.</span></span>
    
## <a name="administrator-roles"></a><span data-ttu-id="7547c-142">管理员角色</span><span class="sxs-lookup"><span data-stu-id="7547c-142">Administrator roles</span></span>

<span data-ttu-id="7547c-143">以下是持久聊天服务器的管理员角色：</span><span class="sxs-lookup"><span data-stu-id="7547c-143">The following are administrator roles for Persistent Chat Server:</span></span>
  
- <span data-ttu-id="7547c-144">**持续聊天管理员**： 持续聊天管理员角色可以管理聊天室 （修改成员身份、 经理、 类别标记为禁用的房间包括的所有属性），以及创建和管理用户定义的聊天室类别可以创建和访问聊天室。</span><span class="sxs-lookup"><span data-stu-id="7547c-144">**Persistent Chat Administrator**: The Persistent Chat Administrator role can manage chat rooms (modify all properties including membership, managers, categories, mark rooms as disabled), as well as create and manage chat room categories that define who can create and access chat rooms.</span></span> <span data-ttu-id="7547c-145">管理员还可以将聊天室标记为禁用并清理不再处于活动状态的聊天室。</span><span class="sxs-lookup"><span data-stu-id="7547c-145">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span></span> <span data-ttu-id="7547c-146">管理员不会受到“创建者”或“允许的成员”限制的影响。</span><span class="sxs-lookup"><span data-stu-id="7547c-146">Administrators are not subject to the Creators or Allowed Members restrictions.</span></span> <span data-ttu-id="7547c-147">管理员可以创建任何类型的聊天室以及将自己添加为任何聊天室的成员。</span><span class="sxs-lookup"><span data-stu-id="7547c-147">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span></span> <span data-ttu-id="7547c-148">管理员可以修改和管理持久聊天配置 （池属性、 全局设置和配置的法规遵从性） 和可以还计划并实施迁移从旧版本的组聊天服务器部署到 Skype 的业务服务器 2015持久的聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="7547c-148">Administrators can also modify and manage Persistent Chat configuration (pool properties, global settings, and compliance configuration) and can also plan and implement migration from an older Group Chat Server deployment to Skype for Business Server 2015 Persistent Chat Server.</span></span>
    
    <span data-ttu-id="7547c-149">持续聊天管理员也能够通过远程使用 Windows PowerShell cmdlet 管理持久聊天服务器 (即，从持久的聊天服务器之外的计算机)。</span><span class="sxs-lookup"><span data-stu-id="7547c-149">Persistent Chat Administrators are able to administer Persistent Chat Server by using Windows PowerShell cmdlets remotely (that is, from a computer other than the Persistent Chat Server).</span></span> <span data-ttu-id="7547c-150">持久的聊天服务器检查持久聊天管理员是持久聊天服务器前端服务器上的 RTC 本地管理员本地组的成员。</span><span class="sxs-lookup"><span data-stu-id="7547c-150">Persistent Chat Server checks that the Persistent Chat Administrator is a member of the RTC Local administrator local group on the Persistent Chat Server Front End Server.</span></span>
    
- <span data-ttu-id="7547c-151">**Skype 业务服务器 2015年管理员**： 负责部署业务服务器 2015年的 Skype 的整体企业管理员。</span><span class="sxs-lookup"><span data-stu-id="7547c-151">**Skype for Business Server 2015 Administrator**: Overall enterprise administrator for Skype for Business Server 2015 responsible for deployment.</span></span>
    
- <span data-ttu-id="7547c-152">**操作管理员**：负责管理日常操作的用户。</span><span class="sxs-lookup"><span data-stu-id="7547c-152">**Operations Manager**: User responsible for managing day-to-day operations.</span></span>
    
- <span data-ttu-id="7547c-153">**第三方开发人员和合作伙伴**：第三方开发人员可扩展系统，特别是针对组会话、合规性支持和工具、Web/移动客户端和自动程序开发框架提供信息隔离墙解决方案。</span><span class="sxs-lookup"><span data-stu-id="7547c-153">**Third-party developers and partners**: Third-party developers extend the system, in particular providing an ethical wall solution for group conversations, compliance support and tools, web/mobile clients, and a framework for Bot development.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="7547c-154">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="7547c-154">For more information</span></span>

<span data-ttu-id="7547c-155">有关配置和管理聊天室和用户角色的更多信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="7547c-155">For more information about configuring and managing chat rooms and user roles, see the following topics:</span></span>
  
- [<span data-ttu-id="7547c-156">在 Skype 业务服务器 2015年创建持久聊天的管理员</span><span class="sxs-lookup"><span data-stu-id="7547c-156">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [<span data-ttu-id="7547c-157">管理业务服务器 2015年在 Skype 的持久聊天服务器的类别</span><span class="sxs-lookup"><span data-stu-id="7547c-157">Manage categories in Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/categories.md)
    
- [<span data-ttu-id="7547c-158">管理业务服务器 2015年聊天室在 Skype 的持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="7547c-158">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/chat-rooms.md)
    

