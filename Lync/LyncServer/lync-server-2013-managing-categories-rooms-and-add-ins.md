---
title: Lync Server 2013：管理类别、聊天室和外接程序
description: Lync Server 2013：管理类别、聊天室和外接程序。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing categories, rooms, and add-ins
ms:assetid: a9807031-7369-4a51-9369-6f09bec24141
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412799(v=OCS.15)
ms:contentKeyID: 48185100
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba09ed3e021ba24f424d28bbb2c5c379ab975741
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569128"
---
# <a name="managing-categories-rooms-and-add-ins-in-lync-server-2013"></a><span data-ttu-id="090a3-103">在 Lync Server 2013 中管理类别、聊天室和外接程序</span><span class="sxs-lookup"><span data-stu-id="090a3-103">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="090a3-104">_**上次修改的主题：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="090a3-104">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="090a3-105">在 Lync Server 2013 控制面板中，或通过使用 Windows PowerShell cmdlet，持久聊天管理员可以使用 " **持久聊天** " 页面创建类别和外接程序。若要管理持久聊天室，管理员可以使用 Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="090a3-105">In Lync Server 2013 Control Panel, or by using Windows PowerShell cmdlets, Persistent Chat Administrators can use the **Persistent Chat** page to create categories and add-ins. For managing Persistent Chat rooms, Administrators can use Windows PowerShell cmdlets.</span></span> <span data-ttu-id="090a3-106">或者，如果持久聊天管理员也是启用了 SIP 的，则可以使用 Lync 客户端启动网页来创建和管理聊天室。</span><span class="sxs-lookup"><span data-stu-id="090a3-106">Alternatively, if the Persistent Chat administrator is also SIP-enabled, they can use the Lync client to launch a web page to create and manage chat rooms.</span></span>

<span data-ttu-id="090a3-107">以下主题介绍了如何创建和使用类别与聊天室。</span><span class="sxs-lookup"><span data-stu-id="090a3-107">The following topics describe how to create and work with categories and chat rooms.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="090a3-108">本部分内容</span><span class="sxs-lookup"><span data-stu-id="090a3-108">In This Section</span></span>

  - [<span data-ttu-id="090a3-109">在 Lync Server 2013 中创建或编辑新类别</span><span class="sxs-lookup"><span data-stu-id="090a3-109">Creating or editing a new category in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-category.md)

  - [<span data-ttu-id="090a3-110">在 Lync Server 2013 中创建或编辑新聊天室</span><span class="sxs-lookup"><span data-stu-id="090a3-110">Creating or editing a new room in Lync Server 2013</span></span>](lync-server-2013-creating-or-editing-a-new-room.md)

  - [<span data-ttu-id="090a3-111">在 Lync Server 2013 中为聊天室创建新的外接程序</span><span class="sxs-lookup"><span data-stu-id="090a3-111">Creating new add-ins for rooms in Lync Server 2013</span></span>](lync-server-2013-creating-new-add-ins-for-rooms.md)

  - [<span data-ttu-id="090a3-112">在 Lync Server 2013 中设置可以在大会堂聊天室中发布邮件的权限</span><span class="sxs-lookup"><span data-stu-id="090a3-112">Setting who can post messages in an auditorium chat room in Lync Server 2013</span></span>](lync-server-2013-setting-who-can-post-messages-in-an-auditorium-chat-room.md)

  - [<span data-ttu-id="090a3-113">在 Lync Server 2013 中禁用或启用聊天室</span><span class="sxs-lookup"><span data-stu-id="090a3-113">Disabling or enabling a chat room in Lync Server 2013</span></span>](lync-server-2013-disabling-or-enabling-a-chat-room.md)

  - [<span data-ttu-id="090a3-114">在 Lync Server 2013 中将聊天室从一个类别移动到另一个类别</span><span class="sxs-lookup"><span data-stu-id="090a3-114">Moving a chat room from one category to another in Lync Server 2013</span></span>](lync-server-2013-moving-a-chat-room-from-one-category-to-another.md)

  - [<span data-ttu-id="090a3-115">在 Lync Server 2013 中删除聊天室或类别</span><span class="sxs-lookup"><span data-stu-id="090a3-115">Deleting a chat room or category in Lync Server 2013</span></span>](lync-server-2013-deleting-a-chat-room-or-category.md)

  - [<span data-ttu-id="090a3-116">在 Lync Server 2013 中删除邮件或清除过时邮件</span><span class="sxs-lookup"><span data-stu-id="090a3-116">Deleting a message or purging obsolete messages in Lync Server 2013</span></span>](lync-server-2013-deleting-a-message-or-purging-obsolete-messages.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

