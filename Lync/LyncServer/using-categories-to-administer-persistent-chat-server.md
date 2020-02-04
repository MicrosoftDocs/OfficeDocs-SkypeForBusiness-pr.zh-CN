---
title: 使用类别管理持久聊天服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Using categories to administer Persistent Chat Server
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398988(v=OCS.15)
ms:contentKeyID: 48185628
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 52e56f776969ece55f71355ed7f184dd6dd46a91
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-categories-to-administer-persistent-chat-server"></a><span data-ttu-id="53da4-102">使用类别管理持久聊天服务器</span><span class="sxs-lookup"><span data-stu-id="53da4-102">Using categories to administer Persistent Chat Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53da4-103">_**主题上次修改时间：** 2013-10-01_</span><span class="sxs-lookup"><span data-stu-id="53da4-103">_**Topic Last Modified:** 2013-10-01_</span></span>

<span data-ttu-id="53da4-104">持久聊天服务器部署可以托管多个并发的持久聊天室。</span><span class="sxs-lookup"><span data-stu-id="53da4-104">Your Persistent Chat Server deployment can host many concurrent Persistent Chat rooms.</span></span> <span data-ttu-id="53da4-105">聊天室可以组织到服务器上的一组类别中。</span><span class="sxs-lookup"><span data-stu-id="53da4-105">Chat rooms can be organized into a set of categories on the server.</span></span> <span data-ttu-id="53da4-106">每个聊天室属于一个类别，并继承该类别的一些设置。</span><span class="sxs-lookup"><span data-stu-id="53da4-106">Each chat room belongs to one category, and inherits some settings from that category.</span></span> <span data-ttu-id="53da4-107">这种组织方式可创建一种非常有用的结构以基于对话的业务目的识别对话，并有助于委托管理和简化控制。</span><span class="sxs-lookup"><span data-stu-id="53da4-107">This organization creates a useful structure for identifying conversations, based on their business purpose, and facilitates delegated administration and simplified management.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="53da4-108">虽然聊天室的许多管理功能在运行持久聊天（Lync 客户端）的计算机中可用，但持续聊天管理员（在<STRONG>cspersistentchatadministrator</STRONG>角色中）必须使用 Lync Server 控制面板或 Windows PowerShell cmdlet 来创建或管理类别。</span><span class="sxs-lookup"><span data-stu-id="53da4-108">Although many of the management features of chat rooms are available in computers running Persistent Chat (Lync client) for the user, Persistent Chat Administrators (in the <STRONG>cspersistentchatadministrator</STRONG> role) must use the Lync Server Control Panel or Windows PowerShell cmdlets to create or manage categories.</span></span>



</div>

<span data-ttu-id="53da4-109">持久聊天管理员使用 Lync Server 控制面板或 Windows PowerShell cmdlet 来创建和管理类别，并为组织中的用户设计对聊天室的访问。</span><span class="sxs-lookup"><span data-stu-id="53da4-109">Persistent Chat administrators use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage categories, and to design access for chat rooms for the users in their organization.</span></span>

<span data-ttu-id="53da4-110">具有管理一个或多个聊天室的持久聊天室管理器，可使用 Lync 客户端启动聊天室管理 Web 应用程序来创建和管理聊天室（或者客户可以创建要调用的自定义解决方案和工作流）。</span><span class="sxs-lookup"><span data-stu-id="53da4-110">Persistent Chat room managers, who have the ability to manage one or more chat rooms, can use the Lync client to launch a room management Web application to create and manage rooms (or customers can create custom solutions and workflows to be invoked).</span></span> <span data-ttu-id="53da4-111">持久聊天管理员还可以使用 Lync Server 控制面板或 Windows PowerShell cmdlet 来创建和管理会议室。</span><span class="sxs-lookup"><span data-stu-id="53da4-111">Persistent Chat administrators can also use Lync Server Control Panel or Windows PowerShell cmdlets to create and manage rooms.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="53da4-112">持久聊天室的名称不能与永久聊天类别相同。</span><span class="sxs-lookup"><span data-stu-id="53da4-112">A Persistent Chat room cannot have the same name as a Persistent Chat category.</span></span>



</div>

<span data-ttu-id="53da4-p103">除了更改聊天室类别之外，聊天室管理员还可以更改所有聊天室属性。不能限制其执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="53da4-p103">Chat room managers can make changes to all chat room properties, except for changing the category of the room. They cannot be restricted from performing the following actions:</span></span>

  - <span data-ttu-id="53da4-115">禁用聊天室</span><span class="sxs-lookup"><span data-stu-id="53da4-115">Disabling a chat room</span></span>

  - <span data-ttu-id="53da4-116">更改聊天室名称</span><span class="sxs-lookup"><span data-stu-id="53da4-116">Changing a chat room name</span></span>

  - <span data-ttu-id="53da4-117">更改聊天室说明</span><span class="sxs-lookup"><span data-stu-id="53da4-117">Changing a chat room description</span></span>

  - <span data-ttu-id="53da4-118">更改聊天室类型（大会堂还是普通）</span><span class="sxs-lookup"><span data-stu-id="53da4-118">Changing a chat room type (Auditorium versus Normal)</span></span>

  - <span data-ttu-id="53da4-119">更改聊天室隐私（开放、关闭还是秘密）</span><span class="sxs-lookup"><span data-stu-id="53da4-119">Changing the privacy of a room (open versus closed versus secret)</span></span>

  - <span data-ttu-id="53da4-120">添加或删除成员</span><span class="sxs-lookup"><span data-stu-id="53da4-120">Adding or removing members</span></span>

  - <span data-ttu-id="53da4-121">添加或删除聊天室管理者</span><span class="sxs-lookup"><span data-stu-id="53da4-121">Adding or removing chat room managers</span></span>

  - <span data-ttu-id="53da4-122">添加或删除加载项</span><span class="sxs-lookup"><span data-stu-id="53da4-122">Adding or removing an add-in</span></span>

  - <span data-ttu-id="53da4-123">更改邀请之类的设置（根据类别允许的内容）</span><span class="sxs-lookup"><span data-stu-id="53da4-123">Changing settings such as invitations (according to what’s permitted by the category)</span></span>

<div>

## <a name="delegated-administration"></a><span data-ttu-id="53da4-124">委派管理</span><span class="sxs-lookup"><span data-stu-id="53da4-124">Delegated Administration</span></span>

<span data-ttu-id="53da4-125">使用正确的类别，创建和管理持久的聊天室更容易。</span><span class="sxs-lookup"><span data-stu-id="53da4-125">Creating and managing Persistent Chat rooms is much easier with the correct use of categories.</span></span> <span data-ttu-id="53da4-126">持续聊天管理员可以为每个类别定义**AllowedMembers**和**创建者**，还可以定义将应用于在类别中创建的所有聊天室的默认聊天室设置和行为。</span><span class="sxs-lookup"><span data-stu-id="53da4-126">A Persistent Chat Administrator can define **AllowedMembers** and **Creators** for each category, and can also define the default chat room settings and behaviors that will be applied to all chat rooms created in the category.</span></span> <span data-ttu-id="53da4-127">持久聊天管理员使用 Lync Server 控制面板或 Windows PowerShell cmdlet 创建和管理类别。</span><span class="sxs-lookup"><span data-stu-id="53da4-127">Persistent Chat administrators create and manage categories by using Lync Server Control Panel or Windows PowerShell cmdlets.</span></span>

<span data-ttu-id="53da4-p105">标识为类别创建者的用户、组织单位 (OU) 和用户组是仅有的被允许在类别中创建聊天室的个人和组。创建类别后，他们可以从类别的 **AllowedMembers** 列表中选择用户、OU 和用户组作为聊天室的管理员和成员来管理和参与聊天室。</span><span class="sxs-lookup"><span data-stu-id="53da4-p105">Users, Organizational Units (OUs), and user groups that are identified as Creators of the category are the only individuals and groups that are allowed to create rooms in the category. After the category is created, they can choose users, OUs, and user groups from the category’s **AllowedMembers** list as chat room managers and members to manage and participate in the room.</span></span>

<span data-ttu-id="53da4-130">在类别中创建的聊天室遵循由类别强制执行的策略和设置（如谁可以在聊天室的成员身份中，可以管理聊天室的人员、是否允许进行文件上载、是否已发送邀请等）。</span><span class="sxs-lookup"><span data-stu-id="53da4-130">Chat rooms that are created in a category adhere to the policies and settings enforced by the category (such as who can be in the room’s membership, who can manage the room, whether file uploads are allowed, whether invitations are sent, and so on).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

