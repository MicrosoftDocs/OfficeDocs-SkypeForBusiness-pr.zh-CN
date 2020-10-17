---
title: 管理聊天室
description: 管理会议室。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Manage rooms
ms:assetid: d4835cf4-cd09-4769-a08e-e92706861b64
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205292(v=OCS.15)
ms:contentKeyID: 48185505
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be093e14a68639fdde73b58936e1b2f5cf4424cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544588"
---
# <a name="manage-rooms"></a><span data-ttu-id="92155-103">管理聊天室</span><span class="sxs-lookup"><span data-stu-id="92155-103">Manage rooms</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92155-104">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="92155-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="92155-105">创建新的持久聊天服务器聊天室</span><span class="sxs-lookup"><span data-stu-id="92155-105">To create a new Persistent Chat Server room</span></span>

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="92155-106">如果满足下列条件之一，则不需要 -PersistentChatPoolFqdn：</span><span class="sxs-lookup"><span data-stu-id="92155-106">-PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="92155-107">只有一个持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="92155-107">There is only one Persistent Chat Server pool.</span></span></P>
> <LI>
> <P><span data-ttu-id="92155-108">您为类别提供了一个池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="92155-108">You provide a pool FQDN to the category.</span></span></P>
> <LI>
> <P><span data-ttu-id="92155-109">您提供了一个池 Fqdn 以添加聊天室。</span><span class="sxs-lookup"><span data-stu-id="92155-109">You provide a pool FQDN to adding the room.</span></span></P></LI></UL>



</div>

<span data-ttu-id="92155-110">对现有持久聊天服务器聊天室进行更改</span><span class="sxs-lookup"><span data-stu-id="92155-110">To make changes to an existing Persistent Chat Server room</span></span>

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

<span data-ttu-id="92155-111">Windows PowerShell：可以同时设置成员、管理者和演示者。</span><span class="sxs-lookup"><span data-stu-id="92155-111">Windows PowerShell: Members, Managers and Presenters can be set simultaneously.</span></span> <span data-ttu-id="92155-112">他们都应为主机类别的 AllowedMembers 减去 DeniedMembers 所得到的子集的一部分。</span><span class="sxs-lookup"><span data-stu-id="92155-112">They all should be the subset of AllowedMembers minus DeniedMembers of the host Category.</span></span> <span data-ttu-id="92155-113">type=normal 的聊天室无法包含演示者。</span><span class="sxs-lookup"><span data-stu-id="92155-113">A room that is type=normal cannot include Presenters.</span></span>

<div>

## <a name="create-get-set-clear-or-remove-a-room"></a><span data-ttu-id="92155-114">创建、获取、设置、清除或删除聊天室</span><span class="sxs-lookup"><span data-stu-id="92155-114">Create, Get, Set, Clear, or Remove a Room</span></span>

<span data-ttu-id="92155-115">创建新聊天室</span><span class="sxs-lookup"><span data-stu-id="92155-115">To create a new room</span></span>

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

<span data-ttu-id="92155-116">设置聊天室</span><span class="sxs-lookup"><span data-stu-id="92155-116">To set a room</span></span>

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

<span data-ttu-id="92155-117">获取聊天室</span><span class="sxs-lookup"><span data-stu-id="92155-117">To get a room</span></span>

    Get-CsPersistentChatRoom -Identity <String>

<span data-ttu-id="92155-118">或</span><span class="sxs-lookup"><span data-stu-id="92155-118">or</span></span>

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

<span data-ttu-id="92155-119">其中 –filter 仅支持名称和说明，并可帮助您查找其名称/说明与关键字字符串匹配的聊天室。</span><span class="sxs-lookup"><span data-stu-id="92155-119">where –filter supports only Name and Description and helps you find rooms whose Name/Description matches the keyword string.</span></span> <span data-ttu-id="92155-120">PoolFqdn 在给定的持久聊天服务器池中进行搜索。</span><span class="sxs-lookup"><span data-stu-id="92155-120">PoolFqdn searches in a given Persistent Chat Server pool.</span></span>

<span data-ttu-id="92155-121">清除聊天室并清除聊天室中的消息</span><span class="sxs-lookup"><span data-stu-id="92155-121">To clear a room and clear messages from a room</span></span>

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="92155-122">或</span><span class="sxs-lookup"><span data-stu-id="92155-122">or</span></span>

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="92155-123">删除聊天室</span><span class="sxs-lookup"><span data-stu-id="92155-123">To remove a room</span></span>

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="92155-124">或</span><span class="sxs-lookup"><span data-stu-id="92155-124">or</span></span>

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

