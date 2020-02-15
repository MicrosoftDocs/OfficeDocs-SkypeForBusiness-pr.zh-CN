---
title: Lync Server 2013：分配每用户策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Assigning per-user policies
ms:assetid: a4ed0120-d9e5-4eb2-acfd-8de2cb503652
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182561(v=OCS.15)
ms:contentKeyID: 48184971
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e9b5780b17ad2ed7a057979f77e504fb1fca0db
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030035"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-policies-in-lync-server-2013"></a><span data-ttu-id="a0595-102">在 Lync Server 2013 中分配每用户策略</span><span class="sxs-lookup"><span data-stu-id="a0595-102">Assigning per-user policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a0595-103">_**上次修改的主题：** 2012-10-14_</span><span class="sxs-lookup"><span data-stu-id="a0595-103">_**Topic Last Modified:** 2012-10-14_</span></span>

<span data-ttu-id="a0595-p101">可以向用户或用户组分配特定策略，以指定与分配给其他用户的策略（如全局策略）中定义的设置所不同的特定设置。这些策略称为每用户策略。</span><span class="sxs-lookup"><span data-stu-id="a0595-p101">You can assign certain policies to a user or a group of users in order to specify particular settings that deviate from the settings defined in policies assigned to other users, such as global policies. These policies are called per-user policies.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="a0595-106">本部分内容</span><span class="sxs-lookup"><span data-stu-id="a0595-106">In This Section</span></span>

  - [<span data-ttu-id="a0595-107">在 Lync Server 2013 中分配每用户会议策略</span><span class="sxs-lookup"><span data-stu-id="a0595-107">Assign a per-user conferencing policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-conferencing-policy.md)

  - [<span data-ttu-id="a0595-108">在 Lync Server 2013 中分配每用户客户端版本策略</span><span class="sxs-lookup"><span data-stu-id="a0595-108">Assign a per-user client version policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-client-version-policy.md)

  - [<span data-ttu-id="a0595-109">在 Lync Server 2013 中分配每用户 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="a0595-109">Assign a per-user PIN policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-pin-policy.md)

  - [<span data-ttu-id="a0595-110">在 Lync Server 2013 中将外部用户访问策略分配给启用 Lync 的用户</span><span class="sxs-lookup"><span data-stu-id="a0595-110">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="a0595-111">在 Lync Server 2013 中分配每用户存档策略</span><span class="sxs-lookup"><span data-stu-id="a0595-111">Assign a per-user archiving policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-archiving-policy.md)

  - [<span data-ttu-id="a0595-112">在 Lync Server 2013 中分配每用户位置策略</span><span class="sxs-lookup"><span data-stu-id="a0595-112">Assign a per-user location policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-location-policy.md)

  - [<span data-ttu-id="a0595-113">在 Lync Server 2013 中分配每用户移动策略</span><span class="sxs-lookup"><span data-stu-id="a0595-113">Assign a per-user mobility policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-mobility-policy.md)

  - [<span data-ttu-id="a0595-114">在 Lync Server 2013 中分配每用户持久聊天策略</span><span class="sxs-lookup"><span data-stu-id="a0595-114">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-persistent-chat-policy.md)

  - [<span data-ttu-id="a0595-115">在 Lync Server 2013 中分配每用户拨号计划策略</span><span class="sxs-lookup"><span data-stu-id="a0595-115">Assign a per-user dial plan policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-dial-plan-policy.md)

  - [<span data-ttu-id="a0595-116">在 Lync Server 2013 中分配每用户语音策略</span><span class="sxs-lookup"><span data-stu-id="a0595-116">Assign a per-user voice policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-voice-policy.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="a0595-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a0595-117">See Also</span></span>


[<span data-ttu-id="a0595-118">在 Lync Server 2013 中管理用户</span><span class="sxs-lookup"><span data-stu-id="a0595-118">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

