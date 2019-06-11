---
title: Lync Server 2013：管理类别、聊天室和加载项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing categories, rooms, and add-ins
ms:assetid: a9807031-7369-4a51-9369-6f09bec24141
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412799(v=OCS.15)
ms:contentKeyID: 48185100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2870d83d463866e07afdffab7c0a840bb2686928
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34828080"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-categories-rooms-and-add-ins-in-lync-server-2013"></a><span data-ttu-id="ee5c9-102">在 Lync Server 2013 中管理类别、聊天室和加载项</span><span class="sxs-lookup"><span data-stu-id="ee5c9-102">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ee5c9-103">_**主题上次修改时间:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="ee5c9-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="ee5c9-104">在 Lync Server 2013 控制面板中, 或通过使用 Windows PowerShell cmdlet, 持久聊天管理员可以使用**持久聊天**页面创建类别和加载项。对于管理持久聊天室, 管理员可以使用 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="ee5c9-104">In Lync Server 2013 Control Panel, or by using Windows PowerShell cmdlets, Persistent Chat Administrators can use the **Persistent Chat** page to create categories and add-ins. For managing Persistent Chat rooms, Administrators can use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="ee5c9-105">或者, 如果持久聊天管理员也是 SIP 启用的, 则他们可以使用 Lync 客户端启动网页来创建和管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="ee5c9-105">Alternatively, if the Persistent Chat administrator is also SIP-enabled, they can use the Lync client to launch a web page to create and manage chat rooms.</span></span>

<span data-ttu-id="ee5c9-106">以下主题介绍如何创建和使用类别和聊天室。</span><span class="sxs-lookup"><span data-stu-id="ee5c9-106">The following topics describe how to create and work with categories and chat rooms.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ee5c9-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="ee5c9-107">In This Section</span></span>

  - [<span data-ttu-id="ee5c9-108">在 Lync Server 2013 中创建或编辑新类别</span><span class="sxs-lookup"><span data-stu-id="ee5c9-108">Creating or editing a new category in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-category.md)

  - [<span data-ttu-id="ee5c9-109">在 Lync Server 2013 中创建或编辑新聊天室</span><span class="sxs-lookup"><span data-stu-id="ee5c9-109">Creating or editing a new room in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-room.md)

  - [<span data-ttu-id="ee5c9-110">在 Lync Server 2013 中创建新的聊天室外接程序</span><span class="sxs-lookup"><span data-stu-id="ee5c9-110">Creating new add-ins for rooms in Lync Server 2013</span></span>](lync-server-2013-creating-new-add-ins-for-rooms.md)

  - [<span data-ttu-id="ee5c9-111">在 Lync Server 2013 中设置谁可以在大会堂聊天室发布消息</span><span class="sxs-lookup"><span data-stu-id="ee5c9-111">Setting who can post messages in an auditorium chat room in Lync Server 2013</span></span>](lync-server-2013-setting-who-can-post-messages-in-an-auditorium-chat-room.md)

  - [<span data-ttu-id="ee5c9-112">在 Lync Server 2013 中禁用或启用聊天室</span><span class="sxs-lookup"><span data-stu-id="ee5c9-112">Disabling or enabling a chat room in Lync Server 2013</span></span>](lync-server-2013-disabling-or-enabling-a-chat-room.md)

  - [<span data-ttu-id="ee5c9-113">在 Lync Server 2013 中将聊天室从一个类别移动到另一个类别</span><span class="sxs-lookup"><span data-stu-id="ee5c9-113">Moving a chat room from one category to another in Lync Server 2013</span></span>](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)

  - [<span data-ttu-id="ee5c9-114">在 Lync Server 2013 中删除聊天室或类别</span><span class="sxs-lookup"><span data-stu-id="ee5c9-114">Deleting a chat room or category in Lync Server 2013</span></span>](lync-server-2013-deleting-a-chat-room-or-category.md)

  - [<span data-ttu-id="ee5c9-115">在 Lync Server 2013 中删除消息或清除作废的消息</span><span class="sxs-lookup"><span data-stu-id="ee5c9-115">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>](lync-server-2013-deleting-a-message-or-purging-obsolete-messages.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

