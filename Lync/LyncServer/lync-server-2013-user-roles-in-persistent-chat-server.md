---
title: 'Lync Server 2013: 持久聊天服务器中的用户角色'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: User roles in Persistent Chat Server
ms:assetid: 343a0563-9ca5-4ad0-b4f3-a72f1d7f1a81
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ676774(v=OCS.15)
ms:contentKeyID: 49361095
ms.date: 03/19/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 36f84f71ca5253d28d9182acc9279010127ee6f3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845486"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-roles-in-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="db1eb-102">Lync Server 2013 中持久聊天服务器中的用户角色</span><span class="sxs-lookup"><span data-stu-id="db1eb-102">User roles in Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db1eb-103">_**主题上次修改时间:** 2015-03-19_</span><span class="sxs-lookup"><span data-stu-id="db1eb-103">_**Topic Last Modified:** 2015-03-19_</span></span>

<span data-ttu-id="db1eb-104">持久聊天服务器提供允许/拒绝成员的概念, 这些成员适用于可访问特定类别中的聊天室的持久聊天类别和控件。</span><span class="sxs-lookup"><span data-stu-id="db1eb-104">Persistent Chat Server provides the concept of Allowed/Denied members, which applies to Persistent Chat categories and controls who can access rooms in a particular category.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="db1eb-105">类别中的允许/拒绝成员与应用于持久聊天室的<STRONG>成员</STRONG>角色不同。</span><span class="sxs-lookup"><span data-stu-id="db1eb-105">Allowed/Denied members in a Category is not the same as a <STRONG>Member</STRONG> role, which applies to a Persistent Chat room.</span></span><BR><span data-ttu-id="db1eb-106">搜索显示用户执行搜索的所有打开和关闭的聊天室在 "允许/拒绝成员" 列表中。</span><span class="sxs-lookup"><span data-stu-id="db1eb-106">Searches display all open and closed chat rooms for which the user performing the search is in the Allowed/Denied member list.</span></span> <span data-ttu-id="db1eb-107">不会显示加密聊天室，除非进行搜索的用户是加密聊天室的成员。</span><span class="sxs-lookup"><span data-stu-id="db1eb-107">Secret rooms are not displayed unless the user who performs the search is a member of the secret room.</span></span> <span data-ttu-id="db1eb-108">用户只能搜索自己已经是其成员的聊天室，或者他们可以请求成员身份的聊天室。</span><span class="sxs-lookup"><span data-stu-id="db1eb-108">The user can search only for rooms that he or she is already a member of, or those for which they can request membership.</span></span>



</div>

<span data-ttu-id="db1eb-109">允许/拒绝成员的概念的主要基本原理是道德留言板。</span><span class="sxs-lookup"><span data-stu-id="db1eb-109">The primary rationale for the concept of Allowed/Denied Members is ethical walls.</span></span> <span data-ttu-id="db1eb-110">例如，银行和财务机构通常设立了阻止贸易商和分析师在实施策略和约定时共享通信的信息隔离区域。</span><span class="sxs-lookup"><span data-stu-id="db1eb-110">For example, it is common in banking and financial institutions to have ethical boundaries that prevent traders and analysts from sharing communications while implementing policies and conventions.</span></span> <span data-ttu-id="db1eb-111">若要满足此要求，管理员可以创建相应类别，以便一个类别允许创建聊天室并允许贸易商使用该聊天室，而另一个类别允许创建聊天室并允许分析师使用该聊天室。</span><span class="sxs-lookup"><span data-stu-id="db1eb-111">To address this requirement, an administrator can create categories so that one category allows rooms to be created and used by traders, and another category allows rooms to be created and used by analysts.</span></span> <span data-ttu-id="db1eb-112">使用此约束设计到系统时, 如果父类别阻止将用户添加为会议室的成员, 则禁止将其添加到该文件。</span><span class="sxs-lookup"><span data-stu-id="db1eb-112">With this constraint is designed into the system prohibits adding a user as a member of the room if the parent category prevents it.</span></span>

<span data-ttu-id="db1eb-113">以下是四个用户角色持久聊天服务器:</span><span class="sxs-lookup"><span data-stu-id="db1eb-113">Following are the four user roles Persistent Chat Server:</span></span>

  - <span data-ttu-id="db1eb-114">**创建者:** 具有创建聊天室的权限的用户。</span><span class="sxs-lookup"><span data-stu-id="db1eb-114">**Creator:** Users who have permissions to create chat rooms.</span></span> <span data-ttu-id="db1eb-115">这些用户位于特定类别的“创建者”列表中：他们可以创建该类别的聊天室，还可以根据该类别分配成员身份，以及指派管理员管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="db1eb-115">These users are in the Creators list of certain categories: they can create chat rooms in that category, and they can also assign membership according to the category, and assign managers to manage the chat room.</span></span> <span data-ttu-id="db1eb-116">创建聊天室的用户将自动添加为聊天室的管理员。</span><span class="sxs-lookup"><span data-stu-id="db1eb-116">The user who creates a chat room is automatically added as a manager of the room.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="db1eb-p104">成为创建者仅仅为其提供创建聊天室的权限。通过自动升级为管理员，创建者才能够在已创建的聊天服务中进一步细化成员身份、管理员等等。</span><span class="sxs-lookup"><span data-stu-id="db1eb-p104">Being a Creator simply provides rights for creating chat rooms. It is the automatic promotion to Manager that enables the Creator to further refine memberships, managers, and so on, on the created chat services.</span></span>

    
    </div>
    
    <span data-ttu-id="db1eb-119">此角色使您能够控制在您的组织中创建聊天室的用户，尤其是当您要集中管理聊天室创建活动以强制实施策略和约定并且随后将聊天室管理权委派给组织中的其他用户时。</span><span class="sxs-lookup"><span data-stu-id="db1eb-119">This role exists to give you the option of controlling who creates chat rooms in your organization, particularly if you want to centrally manage creating chat rooms to enforce policies and conventions, and subsequently delegate the chat room management to other users in the organization.</span></span>

  - <span data-ttu-id="db1eb-120">**管理器:** 管理聊天室的属性的用户。</span><span class="sxs-lookup"><span data-stu-id="db1eb-120">**Manager:** Users who manage properties of a chat room.</span></span> <span data-ttu-id="db1eb-121">聊天室管理员可以修改成员列表（添加和移除成员），以及修改聊天室管理员列表（添加和移除管理员）。</span><span class="sxs-lookup"><span data-stu-id="db1eb-121">Chat room managers can modify the member list (add and remove members), and modify the chat room managers list (add and remove managers).</span></span> <span data-ttu-id="db1eb-122">聊天室管理员可以将自己添加到成员或演示者列表（对于大会堂聊天室）中以便他们可以加入聊天室。</span><span class="sxs-lookup"><span data-stu-id="db1eb-122">Chat room managers can add themselves to the members or presenters list (for auditorium rooms) so they can participate in the chat room.</span></span> <span data-ttu-id="db1eb-123">聊天室管理员还可以禁用聊天室（管理员可查询已禁用聊天室且可以将其永久删除）。</span><span class="sxs-lookup"><span data-stu-id="db1eb-123">Chat room managers can also disable chat rooms (administrators can query for disabled chat rooms and can permanently delete them).</span></span> <span data-ttu-id="db1eb-124">除聊天室的类别外，管理员可以更改聊天室的所有属性。</span><span class="sxs-lookup"><span data-stu-id="db1eb-124">Managers can change all the properties of a chat room, except the category of the chat room.</span></span> <span data-ttu-id="db1eb-125">创建聊天室后, 只有持久聊天管理员才能更改类别。</span><span class="sxs-lookup"><span data-stu-id="db1eb-125">Only the Persistent Chat Administrator can change the category after the chat room has been created.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="db1eb-126">如果该管理员还是其他类别的创建者，则他/她可以更改该类别以使自己有权创建聊天室。</span><span class="sxs-lookup"><span data-stu-id="db1eb-126">If the manager is also a Creator in another category, he or she can change the category to one where they are authorized to create rooms.</span></span>

    
    </div>

  - <span data-ttu-id="db1eb-127">**成员:** 是聊天室成员的用户。</span><span class="sxs-lookup"><span data-stu-id="db1eb-127">**Member:** Users who are members of a chat room.</span></span> <span data-ttu-id="db1eb-128">这些用户可以查看目录中的聊天室 (即使聊天室是保密的), 还可以订阅聊天室 (包括元数据选项, 如 "未读消息"、"ego 筛选器" 和 "关键字筛选器"), 并参与聊天室 (可以发布, 除非聊天室是只有演示者可以发布、获取内容和搜索的 auditorium 房间。</span><span class="sxs-lookup"><span data-stu-id="db1eb-128">These users can see the chat rooms in the directory (even if the chat room is secret), as well as subscribe to the chat room (including metadata options such as unread messages, ego filters, and keyword filters), and participate in the chat room (can post, unless the room is an auditorium room where only presenters can post, get content, and search).</span></span> <span data-ttu-id="db1eb-129">如果用户不是聊天室的成员, 则可以搜索聊天室 (如果他们位于该类别的 "允许的成员" 列表中), 但需要请求访问权限才能加入这些聊天室以访问内容。</span><span class="sxs-lookup"><span data-stu-id="db1eb-129">Users who aren’t members of the chat room can search for the chat room if they are in the Allowed Members list of the category, but need to request access to join these chat rooms to access content.</span></span> <span data-ttu-id="db1eb-130">(没有在系统中内置的请求访问权限或审批; 这些权限通过电子邮件、电话或其他形式的联系人外部完成。)</span><span class="sxs-lookup"><span data-stu-id="db1eb-130">(There is no request access or approvals built into the system; these are done externally by email, phone, or other forms of contact.)</span></span>

  - <span data-ttu-id="db1eb-131">**演示者:** 可以发布到 auditorium 聊天室的用户。</span><span class="sxs-lookup"><span data-stu-id="db1eb-131">**Presenter:** Users who can post to an auditorium room.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="db1eb-132">持久聊天服务器允许用户为特定网站创建和管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="db1eb-132">Persistent Chat Server lets users create and manage chat room for a specific site.</span></span> <span data-ttu-id="db1eb-133">但是, 用户无法在同一拓扑中的其他网站上创建或管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="db1eb-133">Users cannot, however, create or manage chat rooms on other sites within the same topology.</span></span> <span data-ttu-id="db1eb-134">请确保为组织中的所有网站指定聊天室创建者和管理人员。</span><span class="sxs-lookup"><span data-stu-id="db1eb-134">Be sure to specify chat room Creators and Managers for all the sites in your organization.</span></span>



</div>

<span data-ttu-id="db1eb-135">以下角色是持久聊天服务器的管理员角色:</span><span class="sxs-lookup"><span data-stu-id="db1eb-135">The following roles are administrator roles for Persistent Chat Server:</span></span>

  - <span data-ttu-id="db1eb-136">**持续聊天管理员 (CsPersistentChatAdministrator):** 这是一个新的基于角色的访问控制 (RBAC) 角色, 用于管理和管理持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="db1eb-136">**Persistent Chat Administrator (CsPersistentChatAdministrator):** This is a new Role-Based Access Control (RBAC) role to administer and manage Persistent Chat Server.</span></span> <span data-ttu-id="db1eb-137">指定为 CsPersistentChatAdministrator 的用户或安全组可通过使用 Windows PowerShell cmdlet 远程 (即从持久聊天服务器之外的计算机) 管理持久聊天服务器。</span><span class="sxs-lookup"><span data-stu-id="db1eb-137">Users or security groups designated as CsPersistentChatAdministrator are able administer Persistent Chat Server by using Windows PowerShell cmdlets remotely (that is, from a computer other than the Persistent Chat Server).</span></span> <span data-ttu-id="db1eb-138">持久聊天服务器检查持久聊天管理员是否是持久聊天服务器前端服务器上 RTC 本地管理员本地组的成员。</span><span class="sxs-lookup"><span data-stu-id="db1eb-138">Persistent Chat Server checks that the Persistent Chat Administrator is member of the RTC Local administrator local group on the Persistent Chat Server Front End Server.</span></span>
    
    <span data-ttu-id="db1eb-139">CsPersistentChatAdministrator 角色可以管理聊天室 (修改所有属性, 包括成员身份、管理器、类别、将聊天室标记为已禁用), 以及创建和管理聊天室类别, 这些类别定义了可以创建和访问聊天室的人员。</span><span class="sxs-lookup"><span data-stu-id="db1eb-139">The CsPersistentChatAdministrator role can manage chat rooms (modify all properties including membership, managers, categories, mark rooms as disabled), as well as create and manage chat room categories that define who can create and access chat rooms.</span></span> <span data-ttu-id="db1eb-140">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span><span class="sxs-lookup"><span data-stu-id="db1eb-140">Administrators can also mark chat rooms as disabled and clean up chat rooms that are no longer active.</span></span> <span data-ttu-id="db1eb-141">Administrators are not subject to the Creators or Allowed Members restrictions.</span><span class="sxs-lookup"><span data-stu-id="db1eb-141">Administrators are not subject to the Creators or Allowed Members restrictions.</span></span> <span data-ttu-id="db1eb-142">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span><span class="sxs-lookup"><span data-stu-id="db1eb-142">Administrators can create any kind of chat room and add themselves as a member to any chat room.</span></span> <span data-ttu-id="db1eb-143">管理员还可以修改和管理持久聊天配置 (池属性、全局设置和合规性配置), 还可以计划和实施从较旧的组聊天服务器部署到 Lync Server 2013 持久聊天的迁移和实施迁移服务.</span><span class="sxs-lookup"><span data-stu-id="db1eb-143">Administrators can also modify and manage Persistent Chat configuration (pool properties, global settings, and compliance configuration) and can also plan and implement migration from an older Group Chat Server deployment to Lync Server 2013 Persistent Chat Server.</span></span>

  - <span data-ttu-id="db1eb-144">**Lync 管理员:** Lync Server 2013 的整体企业管理员负责部署。</span><span class="sxs-lookup"><span data-stu-id="db1eb-144">**Lync Administrator:** Overall enterprise administrator for Lync Server 2013 responsible for deployment.</span></span>

  - <span data-ttu-id="db1eb-145">**Operations Manager:** 负责管理日常操作的用户。</span><span class="sxs-lookup"><span data-stu-id="db1eb-145">**Operations Manager:** User responsible for managing day-to-day operations.</span></span>

  - <span data-ttu-id="db1eb-146">**第三方开发人员和合作伙伴:** 第三方开发人员将扩展系统, 特别是为组对话、合规性支持和工具、web/移动客户和机器人开发框架提供符合道德的墙解决方案。</span><span class="sxs-lookup"><span data-stu-id="db1eb-146">**Third-party developers and partners:** Third-party developers extend the system, in particular providing an ethical wall solution for group conversations, compliance support and tools, web/mobile clients, and a framework for Bot development.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

