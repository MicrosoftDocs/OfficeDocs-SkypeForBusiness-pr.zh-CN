---
title: Skype for Business Server 2015 中的持久聊天类别、聊天室和用户角色
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 8/17/2015
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
description: 摘要：阅读本主题，了解 Skype for business Server 2015 中持久聊天服务器的类别、聊天室和用户和管理员角色。
ms.openlocfilehash: 03a7b68a9728b60ebae25081e3e974bb61b0fc5b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815760"
---
# <a name="persistent-chat-categories-chat-rooms-and-user-roles-in-skype-for-business-server-2015"></a><span data-ttu-id="ccc0d-103">Skype for Business Server 2015 中的持久聊天类别、聊天室和用户角色</span><span class="sxs-lookup"><span data-stu-id="ccc0d-103">Persistent chat categories, chat rooms, and user roles in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ccc0d-104">**摘要：** 阅读本主题，了解 Skype for business Server 2015 中持久聊天服务器的类别、聊天室和用户和管理员角色。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-104">**Summary:** Read this topic to learn about categories, chat rooms, and user and administrator roles for Persistent Chat Server in Skype for Business Server 2015.</span></span>
  
<span data-ttu-id="ccc0d-105">您可以控制聊天室的访问，方法是创建聊天室类别，然后指定类别以及类别中的聊天室的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-105">You can control access to chat rooms by creating chat room categories, then specifying access to categories and chat rooms within categories.</span></span> <span data-ttu-id="ccc0d-106">您也可以指定各种管理员角色。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-106">You can also specify various administrator roles.</span></span> <span data-ttu-id="ccc0d-107">本主题介绍了：</span><span class="sxs-lookup"><span data-stu-id="ccc0d-107">This topic describes:</span></span> 
  
- <span data-ttu-id="ccc0d-108">用于组织聊天室的类别</span><span class="sxs-lookup"><span data-stu-id="ccc0d-108">Categories for organizing chat rooms</span></span>
    
- <span data-ttu-id="ccc0d-109">聊天室和用户角色</span><span class="sxs-lookup"><span data-stu-id="ccc0d-109">Chat rooms and user roles</span></span>
    
- <span data-ttu-id="ccc0d-110">管理员角色</span><span class="sxs-lookup"><span data-stu-id="ccc0d-110">Administrator roles</span></span>

> [!NOTE] 
> <span data-ttu-id="ccc0d-111">Skype for business Server 2015 中提供了持久聊天，但 Skype for business Server 2019 不再支持此功能。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-111">Persistent chat is available in Skype for Business Server 2015 but is no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="ccc0d-112">团队中提供了相同的功能。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-112">The same functionality is available in Teams.</span></span> <span data-ttu-id="ccc0d-113">有关详细信息，请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-113">For more information, see [Getting started with your Microsoft Teams upgrade](/microsoftteams/upgrade-start-here).</span></span> <span data-ttu-id="ccc0d-114">如果需要使用持久聊天，您可以选择将需要此功能的用户迁移到团队，或继续使用 Skype for Business Server 2015。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-114">If you need to use Persistent chat, your choices are to either migrate users requiring this functionality to Teams, or to continue using Skype for Business Server 2015.</span></span> 
    
## <a name="categories-for-organizing-chat-rooms"></a><span data-ttu-id="ccc0d-115">用于组织聊天室的类别</span><span class="sxs-lookup"><span data-stu-id="ccc0d-115">Categories for organizing chat rooms</span></span>

<span data-ttu-id="ccc0d-116">类别允许您组织聊天室并控制可创建或加入这些类别中的聊天室的用户和组。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-116">Categories let you organize chat rooms and control which users and groups are permitted to create or join the chat rooms within those categories.</span></span> <span data-ttu-id="ccc0d-117">每个类别都具有关联的属性，这些属性决定了可用于该类别中的聊天室的选项。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-117">Each category has associated properties that determine the options available for the chat rooms within the category.</span></span> <span data-ttu-id="ccc0d-118">您可控制特定类别的访问权限，方法是指定“允许”或“拒绝”用户的访问权限。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-118">You control access to a particular category by specifying whether a user is Allowed or Denied access.</span></span>
  
<span data-ttu-id="ccc0d-p104">“允许”和“拒绝”的成员概念的主要原理是信息隔离墙。例如，银行和财务机构通常设立了阻止贸易商和分析师在实施策略和约定时共享通信的信息隔离区域。若要满足此要求，管理员可以创建相应类别，以便一个类别允许创建聊天室并允许贸易商使用该聊天室，而另一个类别允许创建聊天室并允许分析师使用该聊天室。父类别阻止某用户时，将无法把该用户添加为聊天室的成员。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-p104">The primary rationale for the concept of Allowed and Denied Members is ethical walls. For example, it is common in banking and financial institutions to have ethical boundaries that prevent traders and analysts from sharing communications while implementing policies and conventions. To address this requirement, an administrator can create categories so that one category allows rooms to be created and used by traders, and another category allows rooms to be created and used by analysts. Users cannot be added as a member of a chat room if the parent category prevents it.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ccc0d-123">类别中允许和拒绝的成员与应用于持久聊天室的**成员**角色不同。 > 搜索显示用户在 "允许" 和 "拒绝" 成员列表中执行搜索的所有打开和关闭的聊天室。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-123">Allowed and Denied members in a category are not the same as a **Member** role, which applies to a Persistent Chat room.> Searches display all open and closed chat rooms for which the user performing the search is in the Allowed and Denied member list.</span></span> <span data-ttu-id="ccc0d-124">不会显示加密聊天室，除非进行搜索的用户是加密聊天室的成员。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-124">Secret rooms are not displayed unless the user who performs the search is a member of the secret room.</span></span> <span data-ttu-id="ccc0d-125">用户只能搜索自己已经是其成员的聊天室，或者他们可以请求成员身份的聊天室。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-125">The user can search only for rooms that he or she is already a member of, or those for which they can request membership.</span></span> 
  
## <a name="chat-rooms-and-user-roles"></a><span data-ttu-id="ccc0d-126">聊天室和用户角色</span><span class="sxs-lookup"><span data-stu-id="ccc0d-126">Chat rooms and user roles</span></span>

<span data-ttu-id="ccc0d-127">除了类别的允许和拒绝成员外，你还可以通过指定以下用户角色来控制对聊天室的访问：创建者、管理者、成员和演示者。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-127">In addition to Allowed and Denied Members for categories, you can also control access to chat rooms by specifying the following user roles: Creator, Manager, Member, and Presenter.</span></span>
  
- <span data-ttu-id="ccc0d-p106">**创建者**：有权创建聊天室的用户。这些用户位于特定类别的“创建者”列表中：他们可以创建该类别的聊天室，还可以根据该类别分配成员身份，以及指派管理员管理聊天室。创建聊天室的用户将自动添加为聊天室的管理员。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-p106">**Creator**: Users who have permission to create chat rooms. These users are in the Creators list of certain categories: they can create chat rooms in that category, and they can also assign membership according to the category, and assign managers to manage the chat room. The user who creates a chat room is automatically added as a manager of the room.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ccc0d-p107">成为创建者仅仅为其提供创建聊天室的权限。通过自动升级为管理员，创建者才能够在已创建的聊天服务中进一步细化成员身份、管理员等等。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-p107">Being a Creator simply provides rights for creating chat rooms. It is the automatic promotion to Manager that enables the Creator to further refine memberships, managers, and so on, on the created chat services.</span></span> 
  
    <span data-ttu-id="ccc0d-133">此角色使您能够控制在您的组织中创建聊天室的用户，尤其是当您要集中管理聊天室创建活动以强制实施策略和约定并且随后将聊天室管理权委派给组织中的其他用户时。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-133">This role exists to give you the option of controlling who creates chat rooms in your organization, particularly if you want to centrally manage creating chat rooms to enforce policies and conventions, and subsequently delegate the chat room management to other users in the organization.</span></span>
    
- <span data-ttu-id="ccc0d-134">**管理者**：管理聊天室属性的用户。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-134">**Manager**: Users who manage properties of a chat room.</span></span> <span data-ttu-id="ccc0d-135">聊天室管理员可以修改成员列表（添加和移除成员），以及修改聊天室管理员列表（添加和移除管理员）。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-135">Chat room managers can modify the member list (add and remove members), and modify the chat room managers list (add and remove managers).</span></span> <span data-ttu-id="ccc0d-136">聊天室管理员可以将自己添加到成员或演示者列表（对于大会堂聊天室）中以便他们可以加入聊天室。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-136">Chat room managers can add themselves to the members or presenters list (for auditorium rooms) so they can participate in the chat room.</span></span> <span data-ttu-id="ccc0d-137">聊天室管理员还可以禁用聊天室（管理员可查询已禁用聊天室且可以将其永久删除）。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-137">Chat room managers can also disable chat rooms (administrators can query for disabled chat rooms and can permanently delete them).</span></span> <span data-ttu-id="ccc0d-138">除聊天室的类别外，管理员可以更改聊天室的所有属性。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-138">Managers can change all the properties of a chat room, except the category of the chat room.</span></span> <span data-ttu-id="ccc0d-139">创建聊天室后，只有持久聊天管理员才能更改类别。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-139">Only the Persistent Chat Administrator can change the category after the chat room has been created.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="ccc0d-140">如果该管理员还是其他类别的创建者，则他/她可以更改该类别以使自己有权创建聊天室。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-140">If the manager is also a Creator in another category, he or she can change the category to one where they are authorized to create rooms.</span></span> 
  
- <span data-ttu-id="ccc0d-141">**成员**：是聊天室成员的用户。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-141">**Member**: Users who are members of a chat room.</span></span> <span data-ttu-id="ccc0d-142">这些用户可以查看目录中的聊天室（即使聊天室是保密的），还可以订阅聊天室（包括元数据选项，如 "未读消息"、"ego 筛选器" 和 "关键字筛选器"），并参与聊天室（可以发布，除非聊天室是只有演示者可以发布、获取内容和搜索的 auditorium 房间。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-142">These users can see the chat rooms in the directory (even if the chat room is secret), as well as subscribe to the chat room (including metadata options such as unread messages, ego filters, and keyword filters), and participate in the chat room (can post, unless the room is an auditorium room where only presenters can post, get content, and search).</span></span> <span data-ttu-id="ccc0d-143">如果用户不是聊天室的成员，则可以搜索聊天室（如果他们位于该类别的 "允许的成员" 列表中），但需要请求访问权限才能加入这些聊天室以访问内容。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-143">Users who aren't members of the chat room can search for the chat room if they are in the Allowed Members list of the category, but need to request access to join these chat rooms to access content.</span></span> <span data-ttu-id="ccc0d-144">（没有在系统中内置的请求访问权限或审批; 这些权限通过电子邮件、电话或其他形式的联系人外部完成。）</span><span class="sxs-lookup"><span data-stu-id="ccc0d-144">(There is no request access or approvals built into the system; these are done externally by email, phone, or other forms of contact.)</span></span>
    
- <span data-ttu-id="ccc0d-145">**演示者**：可以在大会堂聊天室发布消息的用户。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-145">**Presenter**: Users who can post to an auditorium room.</span></span>
    
## <a name="administrator-roles"></a><span data-ttu-id="ccc0d-146">管理员角色</span><span class="sxs-lookup"><span data-stu-id="ccc0d-146">Administrator roles</span></span>

<span data-ttu-id="ccc0d-147">以下是持久聊天服务器的管理员角色：</span><span class="sxs-lookup"><span data-stu-id="ccc0d-147">The following are administrator roles for Persistent Chat Server:</span></span>
  
- <span data-ttu-id="ccc0d-148">**持久聊天管理员**：持久聊天管理员角色可以管理聊天室（修改所有属性，包括成员身份、管理器、类别、将聊天室标记为已禁用），以及创建和管理聊天室类别，这些类别定义了可以创建和访问聊天室的人员。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-148">**Persistent Chat Administrator**: The Persistent Chat Administrator role can manage chat rooms (modify all properties including membership, managers, categories, mark rooms as disabled), as well as create and manage chat room categories that define who can create and access chat rooms.</span></span> <span data-ttu-id="ccc0d-149">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span><span class="sxs-lookup"><span data-stu-id="ccc0d-149">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span></span> <span data-ttu-id="ccc0d-150">Administrators are not subject to the Creators or Allowed Members restrictions.</span><span class="sxs-lookup"><span data-stu-id="ccc0d-150">Administrators are not subject to the Creators or Allowed Members restrictions.</span></span> <span data-ttu-id="ccc0d-151">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span><span class="sxs-lookup"><span data-stu-id="ccc0d-151">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span></span> <span data-ttu-id="ccc0d-152">管理员还可以修改和管理持久聊天配置（池属性、全局设置和合规性配置），还可以计划和实施从较旧的组聊天服务器部署到 Skype for business Server 2015 的迁移和实施迁移持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-152">Administrators can also modify and manage Persistent Chat configuration (pool properties, global settings, and compliance configuration) and can also plan and implement migration from an older Group Chat Server deployment to Skype for Business Server 2015 Persistent Chat Server.</span></span>
    
    <span data-ttu-id="ccc0d-153">持久聊天管理员能够远程使用 Windows PowerShell cmdlet （即从持久聊天服务器之外的计算机）管理持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-153">Persistent Chat Administrators are able to administer Persistent Chat Server by using Windows PowerShell cmdlets remotely (that is, from a computer other than the Persistent Chat Server).</span></span> <span data-ttu-id="ccc0d-154">持久聊天服务器检查永久聊天管理员是否是持久聊天服务器前端服务器上 RTC 本地管理员本地组的成员。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-154">Persistent Chat Server checks that the Persistent Chat Administrator is a member of the RTC Local administrator local group on the Persistent Chat Server Front End Server.</span></span>
    
- <span data-ttu-id="ccc0d-155">**Skype for Business 服务器2015管理员**： skype For business server 2015 的整体企业管理员负责部署。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-155">**Skype for Business Server 2015 Administrator**: Overall enterprise administrator for Skype for Business Server 2015 responsible for deployment.</span></span>
    
- <span data-ttu-id="ccc0d-156">**操作管理员**：负责管理日常操作的用户。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-156">**Operations Manager**: User responsible for managing day-to-day operations.</span></span>
    
- <span data-ttu-id="ccc0d-157">**第三方开发人员和合作伙伴**：第三方开发人员可扩展系统，特别是针对组会话、合规性支持和工具、Web/移动客户端和自动程序开发框架提供信息隔离墙解决方案。</span><span class="sxs-lookup"><span data-stu-id="ccc0d-157">**Third-party developers and partners**: Third-party developers extend the system, in particular providing an ethical wall solution for group conversations, compliance support and tools, web/mobile clients, and a framework for Bot development.</span></span>
    
## <a name="for-more-information"></a><span data-ttu-id="ccc0d-158">有关详细信息</span><span class="sxs-lookup"><span data-stu-id="ccc0d-158">For more information</span></span>

<span data-ttu-id="ccc0d-159">有关配置和管理聊天室和用户角色的更多信息，请参阅以下主题：</span><span class="sxs-lookup"><span data-stu-id="ccc0d-159">For more information about configuring and managing chat rooms and user roles, see the following topics:</span></span>
  
- [<span data-ttu-id="ccc0d-160">在 Skype for Business Server 2015 中创建持久聊天管理员</span><span class="sxs-lookup"><span data-stu-id="ccc0d-160">Create a Persistent Chat administrator in Skype for Business Server 2015</span></span>](../../deploy/deploy-persistent-chat-server/create-a-persistent-chat-administrator.md)
    
- [<span data-ttu-id="ccc0d-161">在 Skype for Business Server 2015 中管理持久聊天服务器内的类别</span><span class="sxs-lookup"><span data-stu-id="ccc0d-161">Manage categories in Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/categories.md)
    
- [<span data-ttu-id="ccc0d-162">在 Skype for Business Server 2015 中管理持久聊天服务器内的聊天室</span><span class="sxs-lookup"><span data-stu-id="ccc0d-162">Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015</span></span>](../../manage/persistent-chat/chat-rooms.md)
    

