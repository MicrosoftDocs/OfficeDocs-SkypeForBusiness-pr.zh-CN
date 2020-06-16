---
title: 了解持久聊天成员身份
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 400866812ab2d5efb12960dc3c2f37c2fcb8eb45
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755676"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a><span data-ttu-id="98554-102">了解持久聊天成员身份</span><span class="sxs-lookup"><span data-stu-id="98554-102">Understanding Persistent Chat membership</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98554-103">_**上次修改的主题：** 2013-02-22_</span><span class="sxs-lookup"><span data-stu-id="98554-103">_**Topic Last Modified:** 2013-02-22_</span></span>

<span data-ttu-id="98554-104">用户对持久聊天室的访问权限由成员资格管理;用户必须是聊天室的成员才能发布和阅读邮件。</span><span class="sxs-lookup"><span data-stu-id="98554-104">User access to Persistent Chat rooms is managed by membership; users must be members of a chat room to be able to post and read messages.</span></span> <span data-ttu-id="98554-105">只允许与聊天室有指定的附属关系的**演示者**使用**在大会堂聊天室发布消息**。</span><span class="sxs-lookup"><span data-stu-id="98554-105">Only **Presenters** who have a designated affiliation with chat rooms are allowed to use **Posting to Auditorium rooms**.</span></span> <span data-ttu-id="98554-106">大会堂是其中一种聊天室类型（另一种是**普通聊天室**），在这种聊天室中，只有演示者能发布消息，但任何人都能阅读消息。</span><span class="sxs-lookup"><span data-stu-id="98554-106">An auditorium is a type of chat room (the other is **Normal**), where only Presenters can post and everyone can read.</span></span>

<span data-ttu-id="98554-107">此外，持久聊天室在类别规则下运行。</span><span class="sxs-lookup"><span data-stu-id="98554-107">In addition, Persistent Chat rooms operate under the rules of a category.</span></span> <span data-ttu-id="98554-108">有关类别的详细信息，请参阅[在 Lync Server 2013 中管理类别、聊天室和外接程序](lync-server-2013-managing-categories-rooms-and-add-ins.md)，以及本主题后面部分的 "类别作用域的工作原理" 和 "会议室类别策略" 部分。</span><span class="sxs-lookup"><span data-stu-id="98554-108">For details about categories, see [Managing categories, rooms, and add-ins in Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md), and also the sections "How Category Scoping Works" and "Room Category Strategies" later in this topic.</span></span>

<span data-ttu-id="98554-109">持久聊天管理员可以创建和管理聊天室类别。</span><span class="sxs-lookup"><span data-stu-id="98554-109">A Persistent Chat administrator can create and manage chat room categories.</span></span> <span data-ttu-id="98554-110">在创建和管理聊天室类别的过程中，持久聊天管理员可以配置有权访问特定类别的聊天室的成员或访问者的主体（Active Directory 域服务组、容器和用户）。</span><span class="sxs-lookup"><span data-stu-id="98554-110">As part of creating and managing chat room categories, the Persistent Chat administrator can configure principals (Active Directory Domain Services groups, containers, and users) that have access to be members or creators of chat rooms of a particular category.</span></span>

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a><span data-ttu-id="98554-111">Active Directory 域服务和持久聊天</span><span class="sxs-lookup"><span data-stu-id="98554-111">Active Directory Domain Services and Persistent Chat</span></span>

<span data-ttu-id="98554-112">持久聊天服务器依赖于内部持久聊天用户池的 Active Directory。</span><span class="sxs-lookup"><span data-stu-id="98554-112">Persistent Chat Server relies on Active Directory for the pool of internal Persistent Chat users.</span></span> <span data-ttu-id="98554-113">安装持久聊天（客户端）后，可以将用户和用户组的域添加到聊天室类别中。</span><span class="sxs-lookup"><span data-stu-id="98554-113">After you install Persistent Chat (client), you can add domains of users and user groups to the room category.</span></span> <span data-ttu-id="98554-114">然后，可以将这些用户和组添加到您的聊天室类别的成员身份中。</span><span class="sxs-lookup"><span data-stu-id="98554-114">You can then add these users and groups to the membership of your room categories.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="98554-115">您必须确保要对其持久聊天室进行更改的用户没有重复的名称。</span><span class="sxs-lookup"><span data-stu-id="98554-115">You must ensure that there are no duplicate names for users who want to make changes to their Persistent Chat room(s).</span></span> <span data-ttu-id="98554-116">如果存在重复的用户名，请将它们更改为不同的名称以解除针对用户进行这些更改的限制。</span><span class="sxs-lookup"><span data-stu-id="98554-116">If duplicate user names exist, change them to different names to unblock users from making those changes.</span></span> <span data-ttu-id="98554-117">如果用户在 Active Directory 中具有重复的名称，并尝试在其聊天室中进行更改，则会出现一条错误消息，提示用户与管理员联系以进行解决。</span><span class="sxs-lookup"><span data-stu-id="98554-117">If a user has duplicate names in Active Directory and tries to make changes in their room(s), an error message appears prompting the user to contact the administrator for resolution.</span></span>



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a><span data-ttu-id="98554-118">类别作用域的工作机制</span><span class="sxs-lookup"><span data-stu-id="98554-118">How Category Scoping Works</span></span>

<span data-ttu-id="98554-119">类别指定在该类别中的持久聊天室的成员资格列表中可以是其成员的所有用户和组，具体取决于其**AllowedMembers**属性。</span><span class="sxs-lookup"><span data-stu-id="98554-119">A category specifies all the users and groups that can be members in a membership list of a Persistent Chat room in that category, based on its **AllowedMembers** property.</span></span> <span data-ttu-id="98554-120">例如，如果将类别的**AllowedMembers**设置为 contoso.com，则可以将*contoso*中的任何组或用户添加为该类别中的聊天室的成员。</span><span class="sxs-lookup"><span data-stu-id="98554-120">For example, if you set the category’s **AllowedMembers** to contoso.com, you can add any group or user at *Contoso* as a member to chat rooms in that category.</span></span> <span data-ttu-id="98554-121">如果将某个类别上的 **AllowedMembers** 设置为 *Sales*，则只能将此通讯组列表中的组和用户添加为该类别中的聊天室的成员。</span><span class="sxs-lookup"><span data-stu-id="98554-121">If you set the **AllowedMembers** on a category to *Sales*, only groups and users in this distribution list can be added as members to chat rooms in that category.</span></span> <span data-ttu-id="98554-122">同样，利用 **Creators** 属性，您可以控制可在该类别中创建聊天室的人员。</span><span class="sxs-lookup"><span data-stu-id="98554-122">Similarly, the **Creators** property enables you to control who can create chat rooms in that category.</span></span> <span data-ttu-id="98554-123">创建聊天室后，可将 **AllowedMembers** 组中的任何人指定为聊天室中正在进行的管理操作（例如，成员身份更改和审批）的 **Manager**。</span><span class="sxs-lookup"><span data-stu-id="98554-123">After the chat room is created, anyone from the **AllowedMembers** group can be designated as a **Manager** for ongoing management operations on the rooms (for example, membership changes and approvals).</span></span>

<span data-ttu-id="98554-124">为类别定义 **AllowedMembers** 和 **Creators** 有以下好处：</span><span class="sxs-lookup"><span data-stu-id="98554-124">Defining **AllowedMembers** and **Creators** for a category has the following benefits:</span></span>

  - <span data-ttu-id="98554-125">All chat rooms in this category are bound by the restrictions set at the category level.</span><span class="sxs-lookup"><span data-stu-id="98554-125">All chat rooms in this category are bound by the restrictions set at the category level.</span></span> <span data-ttu-id="98554-126">You can use this to segregate chat rooms based on business need and access policies.</span><span class="sxs-lookup"><span data-stu-id="98554-126">You can use this to segregate chat rooms based on business need and access policies.</span></span>

  - <span data-ttu-id="98554-127">A user who is in the **Creators** list can create new chat rooms in that category.</span><span class="sxs-lookup"><span data-stu-id="98554-127">A user who is in the **Creators** list can create new chat rooms in that category.</span></span> <span data-ttu-id="98554-128">If you want to implement a system where a restricted number of personnel in the organization can create chat rooms, this control can be used to meet that requirement.</span><span class="sxs-lookup"><span data-stu-id="98554-128">If you want to implement a system where a restricted number of personnel in the organization can create chat rooms, this control can be used to meet that requirement.</span></span>

</div>

<div>

## <a name="room-category-strategies"></a><span data-ttu-id="98554-129">聊天室类别策略</span><span class="sxs-lookup"><span data-stu-id="98554-129">Room Category Strategies</span></span>

<span data-ttu-id="98554-130">类别的**AllowedMembers**必须包括将在此类别中使用任何持久聊天室的所有用户。</span><span class="sxs-lookup"><span data-stu-id="98554-130">A category’s **AllowedMembers** must include all users who will use any Persistent Chat room in this category.</span></span> <span data-ttu-id="98554-131">根据您保护业务数据和确保适当的访问级别的要求，您可能希望定义一个或多个类别以指定可在聊天室中进行搜索和加入聊天室的人员。</span><span class="sxs-lookup"><span data-stu-id="98554-131">Depending on your requirements to protect business data and ensure the appropriate level of access, you may want to define one or more categories to specify who can search and participate in rooms.</span></span> <span data-ttu-id="98554-132">如果希望只允许一组特定的用户（中央支持人员或仅全职员工）创建聊天室，则可以设置类别的 **Creators** 的作用域来满足该要求。</span><span class="sxs-lookup"><span data-stu-id="98554-132">If you want to allow only a particular set of users (a central helpdesk, or only full-time employees) to create rooms, you can scope the **Creators** of a category to satisfy that requirement.</span></span>

<span data-ttu-id="98554-133">Categories can also be used to create ethical walls.</span><span class="sxs-lookup"><span data-stu-id="98554-133">Categories can also be used to create ethical walls.</span></span> <span data-ttu-id="98554-134">Ethical walls prevent any conflict of interest in an organization.</span><span class="sxs-lookup"><span data-stu-id="98554-134">Ethical walls prevent any conflict of interest in an organization.</span></span> <span data-ttu-id="98554-135">For example, an administrator can create chat rooms in a category for traders only, whereas chat rooms in another category can be used by analysts only.</span><span class="sxs-lookup"><span data-stu-id="98554-135">For example, an administrator can create chat rooms in a category for traders only, whereas chat rooms in another category can be used by analysts only.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="98554-136">在 Lync Server 2013 的持久聊天服务器中，我们不支持对联合用户的访问。</span><span class="sxs-lookup"><span data-stu-id="98554-136">In Lync Server 2013, Persistent Chat Server, we do not support access to federated users.</span></span> <span data-ttu-id="98554-137">如果来自以前版本的持久聊天服务器的联盟用户的聊天，将迁移这些聊天。</span><span class="sxs-lookup"><span data-stu-id="98554-137">If there are chats from federated users in previous versions of Persistent Chat Server, they will be migrated.</span></span> <span data-ttu-id="98554-138">将联盟用户添加为已禁用的主体。</span><span class="sxs-lookup"><span data-stu-id="98554-138">The federated users are added as disabled principals.</span></span>



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a><span data-ttu-id="98554-139">将成员缩小至用户组</span><span class="sxs-lookup"><span data-stu-id="98554-139">Narrowing the Members to User Groups</span></span>

<span data-ttu-id="98554-140">当您向类别添加域时，组对象隶属于该域的用户组可供您使用，以将其指定为该类别中的聊天室的成员。</span><span class="sxs-lookup"><span data-stu-id="98554-140">When you add a domain to a category, the user groups whose group objects are contained in that domain are available to you so that you can specify them as members of rooms in that category.</span></span>

<span data-ttu-id="98554-141">我们建议您使用 Active Directory 容器（如域和组织单位）定义类别的**AllowedMembers**和**创建者**的常规规则。</span><span class="sxs-lookup"><span data-stu-id="98554-141">We recommend, as a general rule, that you use Active Directory containers, such as domains and organizational units, for defining a category’s **AllowedMembers** and **Creators**.</span></span> <span data-ttu-id="98554-142">您可以将任何域中的对象添加到 **AllowedMembers** 或 **Creators** 列表。</span><span class="sxs-lookup"><span data-stu-id="98554-142">You can add objects from any domain to an **AllowedMembers** or **Creators** list.</span></span> <span data-ttu-id="98554-143">只有 **AllowedMembers** 或 **Creators** 列表中的对象能添加到该类别下的聊天室。</span><span class="sxs-lookup"><span data-stu-id="98554-143">Only objects within the **AllowedMembers** or **Creators** list can be added to rooms under that category.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

