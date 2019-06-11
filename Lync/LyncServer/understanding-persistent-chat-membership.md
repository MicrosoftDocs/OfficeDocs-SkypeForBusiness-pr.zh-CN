---
title: 了解持久聊天成员身份
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e525d93e58e73304b9d3a26248418c88b5e9ea79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845082"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a><span data-ttu-id="2c4d9-102">了解持久聊天成员身份</span><span class="sxs-lookup"><span data-stu-id="2c4d9-102">Understanding Persistent Chat membership</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2c4d9-103">_**主题上次修改时间:** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="2c4d9-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="2c4d9-104">用户对持久聊天室的访问权限由成员身份管理;用户必须是聊天室的成员才能发布和阅读邮件。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-104">User access to Persistent Chat rooms is managed by membership; users must be members of a chat room to be able to post and read messages.</span></span> <span data-ttu-id="2c4d9-105">只有具有 "聊天室" 的指定隶属关系的**演示者**才允许使用**发布到 Auditorium 会议室**。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-105">Only **Presenters** who have a designated affiliation with chat rooms are allowed to use **Posting to Auditorium rooms**.</span></span> <span data-ttu-id="2c4d9-106">Auditorium 是一种类型的聊天室 (另一种是**正常**情况), 其中只有演示者可以发布, 并且所有人都可以阅读。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-106">An auditorium is a type of chat room (the other is **Normal**), where only Presenters can post and everyone can read.</span></span>

<span data-ttu-id="2c4d9-107">此外, 持久聊天室在类别规则下运行。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-107">In addition, Persistent Chat rooms operate under the rules of a category.</span></span> <span data-ttu-id="2c4d9-108">有关类别的详细信息, 请参阅在[Lync Server 2013 中管理类别、会议室和外接程序](lync-server-2013-managing-categories-rooms-and-add-ins.md), 以及本主题后面部分的 "类别范围的工作原理" 和 "会议室类别策略" 部分。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-108">For details about categories, see [Managing categories, rooms, and add-ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), and also the sections "How Category Scoping Works" and "Room Category Strategies" later in this topic.</span></span>

<span data-ttu-id="2c4d9-109">持久聊天管理员可以创建和管理聊天室类别。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-109">A Persistent Chat administrator can create and manage chat room categories.</span></span> <span data-ttu-id="2c4d9-110">在创建和管理聊天室类别的过程中, 持久聊天管理员可以配置主体 (Active Directory 域服务组、容器和用户), 这些主体有权访问属于特定类别的聊天室的成员或访问者。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-110">As part of creating and managing chat room categories, the Persistent Chat administrator can configure principals (Active Directory Domain Services groups, containers, and users) that have access to be members or creators of chat rooms of a particular category.</span></span>

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a><span data-ttu-id="2c4d9-111">Active Directory 域服务和持久聊天</span><span class="sxs-lookup"><span data-stu-id="2c4d9-111">Active Directory Domain Services and Persistent Chat</span></span>

<span data-ttu-id="2c4d9-112">持久聊天服务器依赖于内部持久聊天用户池的 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-112">Persistent Chat Server relies on Active Directory for the pool of internal Persistent Chat users.</span></span> <span data-ttu-id="2c4d9-113">安装持久聊天 (客户端) 后, 您可以将用户和用户组域添加到聊天室类别。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-113">After you install Persistent Chat (client), you can add domains of users and user groups to the room category.</span></span> <span data-ttu-id="2c4d9-114">然后, 你可以将这些用户和组添加到聊天室类别的成员身份。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-114">You can then add these users and groups to the membership of your room categories.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="2c4d9-115">您必须确保要对其永久聊天室进行更改的用户没有重复的名称。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-115">You must ensure that there are no duplicate names for users who want to make changes to their Persistent Chat room(s).</span></span> <span data-ttu-id="2c4d9-116">如果存在重复的用户名, 请将其更改为不同的名称, 以取消阻止用户进行这些更改。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-116">If duplicate user names exist, change them to different names to unblock users from making those changes.</span></span> <span data-ttu-id="2c4d9-117">如果用户在 Active Directory 中具有重复的名称, 并尝试在其聊天室中进行更改, 则会显示一条错误消息, 提示用户联系管理员进行解析。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-117">If a user has duplicate names in Active Directory and tries to make changes in their room(s), an error message appears prompting the user to contact the administrator for resolution.</span></span>



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a><span data-ttu-id="2c4d9-118">类别作用域的工作原理</span><span class="sxs-lookup"><span data-stu-id="2c4d9-118">How Category Scoping Works</span></span>

<span data-ttu-id="2c4d9-119">类别指定了所有用户和组, 这些用户和组可以是该类别中的持久聊天室的成员身份列表中的成员, 具体取决于其**AllowedMembers**属性。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-119">A category specifies all the users and groups that can be members in a membership list of a Persistent Chat room in that category, based on its **AllowedMembers** property.</span></span> <span data-ttu-id="2c4d9-120">例如, 如果将类别的**AllowedMembers**设置为 contoso.com, 则可以将*contoso*中的任何组或用户添加到该类别中的聊天室。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-120">For example, if you set the category’s **AllowedMembers** to contoso.com, you can add any group or user at *Contoso* as a member to chat rooms in that category.</span></span> <span data-ttu-id="2c4d9-121">如果将类别的**AllowedMembers**设置为 "*销售*", 则只能将此通讯组列表中的组和用户添加为该类别中的聊天室。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-121">If you set the **AllowedMembers** on a category to *Sales*, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="2c4d9-122">同样, "**创建者**" 属性使您能够控制哪些人可以创建该类别的聊天室。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-122">Similarly, the **Creators** property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="2c4d9-123">在创建聊天室后, **AllowedMembers**组中的任何人都可以被指定为**管理者**进行持续管理操作 (例如, 成员身份更改和审批)。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-123">After the chat room is created, anyone from the **AllowedMembers** group can be designated as a **Manager** for ongoing management operations on the rooms (for example, membership changes and approvals).</span></span>

<span data-ttu-id="2c4d9-124">定义类别的**AllowedMembers**和**创意者**具有以下优点:</span><span class="sxs-lookup"><span data-stu-id="2c4d9-124">Defining **AllowedMembers** and **Creators** for a category has the following benefits:</span></span>

  - <span data-ttu-id="2c4d9-125">该类别中的所有聊天室都绑定了在类别级别设置的限制。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-125">All chat rooms in this category are bound by the restrictions set at the category level.</span></span> <span data-ttu-id="2c4d9-126">您可以使用此限制，根据业务需求和访问策略隔离聊天室。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-126">You can use this to segregate chat rooms based on business need and access policies.</span></span>

  - <span data-ttu-id="2c4d9-127">"**创建者**" 列表中的用户可以在该类别中创建新的聊天室。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-127">A user who is in the **Creators** list can create new chat rooms in that category.</span></span> <span data-ttu-id="2c4d9-128">如果你想要实现组织中受限制的人员可以创建聊天室的系统, 则可以使用此控件来满足该要求。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-128">If you want to implement a system where a restricted number of personnel in the organization can create chat rooms, this control can be used to meet that requirement.</span></span>

</div>

<div>

## <a name="room-category-strategies"></a><span data-ttu-id="2c4d9-129">会议室类别策略</span><span class="sxs-lookup"><span data-stu-id="2c4d9-129">Room Category Strategies</span></span>

<span data-ttu-id="2c4d9-130">类别的**AllowedMembers**必须包括所有将在此类别中使用任何持久聊天室的用户。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-130">A category’s **AllowedMembers** must include all users who will use any Persistent Chat room in this category.</span></span> <span data-ttu-id="2c4d9-131">你可能希望定义一个或多个类别, 以指定可以搜索和参与聊天室的人员, 具体取决于保护业务数据和确保访问级别的要求。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-131">Depending on your requirements to protect business data and ensure the appropriate level of access, you may want to define one or more categories to specify who can search and participate in rooms.</span></span> <span data-ttu-id="2c4d9-132">如果你希望仅允许特定的一组用户 (中央帮助台, 或仅全职员工) 创建聊天室, 则可以将类别的**创建者**范围限定为满足该要求。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-132">If you want to allow only a particular set of users (a central helpdesk, or only full-time employees) to create rooms, you can scope the **Creators** of a category to satisfy that requirement.</span></span>

<span data-ttu-id="2c4d9-133">类别也可用于创建符合道德的留言板。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-133">Categories can also be used to create ethical walls.</span></span> <span data-ttu-id="2c4d9-134">符合道德的墙可防止组织的任何利益冲突。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-134">Ethical walls prevent any conflict of interest in an organization.</span></span> <span data-ttu-id="2c4d9-135">例如, 管理员可以仅在贸易类别中创建聊天室, 而另一类别中的聊天室只能由分析员使用。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-135">For example, an administrator can create chat rooms in a category for traders only, whereas chat rooms in another category can be used by analysts only.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2c4d9-136">在 Lync Server 2013 的持久聊天服务器中, 我们不支持对联盟用户的访问。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-136">In Lync Server 2013, Persistent Chat Server, we do not support access to federated users.</span></span> <span data-ttu-id="2c4d9-137">如果以前版本的持久聊天服务器中存在来自联盟用户的聊天, 则将迁移这些聊天。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-137">If there are chats from federated users in previous versions of Persistent Chat Server, they will be migrated.</span></span> <span data-ttu-id="2c4d9-138">将联盟用户添加为已禁用主体。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-138">The federated users are added as disabled principals.</span></span>



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a><span data-ttu-id="2c4d9-139">将成员收缩到用户组</span><span class="sxs-lookup"><span data-stu-id="2c4d9-139">Narrowing the Members to User Groups</span></span>

<span data-ttu-id="2c4d9-140">将域添加到类别时, 您可以使用域中包含其组对象的用户组, 以便将其指定为该类别中的会议室成员。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-140">When you add a domain to a category, the user groups whose group objects are contained in that domain are available to you so that you can specify them as members of rooms in that category.</span></span>

<span data-ttu-id="2c4d9-141">我们建议你使用 Active Directory 容器 (如域和组织单元) 来定义类别的**AllowedMembers**和**创建者**。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-141">We recommend, as a general rule, that you use Active Directory containers, such as domains and organizational units, for defining a category’s **AllowedMembers** and **Creators**.</span></span> <span data-ttu-id="2c4d9-142">你可以将任何域中的对象添加到**AllowedMembers**或**创建者**列表。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-142">You can add objects from any domain to an **AllowedMembers** or **Creators** list.</span></span> <span data-ttu-id="2c4d9-143">只有**AllowedMembers**或 "**创建者**" 列表中的对象才能添加到该类别下的聊天室中。</span><span class="sxs-lookup"><span data-stu-id="2c4d9-143">Only objects within the **AllowedMembers** or **Creators** list can be added to rooms under that category.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

