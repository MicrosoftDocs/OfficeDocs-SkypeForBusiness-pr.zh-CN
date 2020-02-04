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
ms.openlocfilehash: 6b80446d9117a37b86c386132aa80439cb568a98
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41734032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="assigning-per-user-policies-in-lync-server-2013"></a><span data-ttu-id="16319-102">在 Lync Server 2013 中分配每个用户的策略</span><span class="sxs-lookup"><span data-stu-id="16319-102">Assigning per-user policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="16319-103">_**主题上次修改时间：** 2012-10-14_</span><span class="sxs-lookup"><span data-stu-id="16319-103">_**Topic Last Modified:** 2012-10-14_</span></span>

<span data-ttu-id="16319-104">你可以将某些策略分配给用户或用户组，以指定与分配给其他用户的策略（如全局策略）中定义的设置不同的特定设置。</span><span class="sxs-lookup"><span data-stu-id="16319-104">You can assign certain policies to a user or a group of users in order to specify particular settings that deviate from the settings defined in policies assigned to other users, such as global policies.</span></span> <span data-ttu-id="16319-105">这些策略称为每用户策略。</span><span class="sxs-lookup"><span data-stu-id="16319-105">These policies are called per-user policies.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="16319-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="16319-106">In This Section</span></span>

  - [<span data-ttu-id="16319-107">在 Lync Server 2013 中分配每用户会议策略</span><span class="sxs-lookup"><span data-stu-id="16319-107">Assign a per-user conferencing policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-conferencing-policy.md)

  - [<span data-ttu-id="16319-108">在 Lync Server 2013 中分配每用户客户端版本策略</span><span class="sxs-lookup"><span data-stu-id="16319-108">Assign a per-user client version policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-client-version-policy.md)

  - [<span data-ttu-id="16319-109">在 Lync Server 2013 中分配每用户 PIN 策略</span><span class="sxs-lookup"><span data-stu-id="16319-109">Assign a per-user PIN policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-pin-policy.md)

  - [<span data-ttu-id="16319-110">在 Lync Server 2013 中将外部用户访问策略分配到启用 Lync 的用户</span><span class="sxs-lookup"><span data-stu-id="16319-110">Assign an external user access policy to a Lync enabled user in Lync Server 2013</span></span>](lync-server-2013-assign-an-external-user-access-policy-to-a-lync-enabled-user.md)

  - [<span data-ttu-id="16319-111">在 Lync Server 2013 中分配每用户存档策略</span><span class="sxs-lookup"><span data-stu-id="16319-111">Assign a per-user archiving policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-archiving-policy.md)

  - [<span data-ttu-id="16319-112">在 Lync Server 2013 中分配每用户位置策略</span><span class="sxs-lookup"><span data-stu-id="16319-112">Assign a per-user location policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-location-policy.md)

  - [<span data-ttu-id="16319-113">在 Lync Server 2013 中分配每用户移动策略</span><span class="sxs-lookup"><span data-stu-id="16319-113">Assign a per-user mobility policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-mobility-policy.md)

  - [<span data-ttu-id="16319-114">在 Lync Server 2013 中分配每用户持久聊天策略</span><span class="sxs-lookup"><span data-stu-id="16319-114">Assign a per-user Persistent Chat policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-persistent-chat-policy.md)

  - [<span data-ttu-id="16319-115">在 Lync Server 2013 中分配每个用户的拨号计划策略</span><span class="sxs-lookup"><span data-stu-id="16319-115">Assign a per-user dial plan policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-dial-plan-policy.md)

  - [<span data-ttu-id="16319-116">在 Lync Server 2013 中分配每用户语音策略</span><span class="sxs-lookup"><span data-stu-id="16319-116">Assign a per-user voice policy in Lync Server 2013</span></span>](lync-server-2013-assign-a-per-user-voice-policy.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="16319-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="16319-117">See Also</span></span>


[<span data-ttu-id="16319-118">在 Lync Server 2013 中管理用户</span><span class="sxs-lookup"><span data-stu-id="16319-118">Managing users in Lync Server 2013</span></span>](lync-server-2013-managing-users-in-lync-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

