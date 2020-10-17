---
title: 管理聊天室
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
ms.openlocfilehash: 0ddb9e074a0eb0bdd614abb3fa29cd0785d2df42
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48527559"
---
# <a name="manage-rooms"></a><span data-ttu-id="66451-102">管理聊天室</span><span class="sxs-lookup"><span data-stu-id="66451-102">Manage rooms</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66451-103">_**上次修改的主题：** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="66451-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="66451-104">创建新的持久聊天服务器聊天室</span><span class="sxs-lookup"><span data-stu-id="66451-104">To create a new Persistent Chat Server room</span></span>

    New-CsPersistentChatRoom -Name Foo1 -PersistentChatPoolFqdn client.contoso.com -Category client.contoso.com\Foo [other parameters]

<div>


> [!IMPORTANT]  
> <span data-ttu-id="66451-105">如果满足下列条件之一，则不需要 -PersistentChatPoolFqdn：</span><span class="sxs-lookup"><span data-stu-id="66451-105">-PersistentChatPoolFqdn is not needed if one of the following is true:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="66451-106">只有一个持久聊天服务器池。</span><span class="sxs-lookup"><span data-stu-id="66451-106">There is only one Persistent Chat Server pool.</span></span></P>
> <LI>
> <P><span data-ttu-id="66451-107">您为类别提供了一个池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="66451-107">You provide a pool FQDN to the category.</span></span></P>
> <LI>
> <P><span data-ttu-id="66451-108">您提供了一个池 Fqdn 以添加聊天室。</span><span class="sxs-lookup"><span data-stu-id="66451-108">You provide a pool FQDN to adding the room.</span></span></P></LI></UL>



</div>

<span data-ttu-id="66451-109">对现有持久聊天服务器聊天室进行更改</span><span class="sxs-lookup"><span data-stu-id="66451-109">To make changes to an existing Persistent Chat Server room</span></span>

    Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
    Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
    Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}

<span data-ttu-id="66451-110">Windows PowerShell：可以同时设置成员、管理者和演示者。</span><span class="sxs-lookup"><span data-stu-id="66451-110">Windows PowerShell: Members, Managers and Presenters can be set simultaneously.</span></span> <span data-ttu-id="66451-111">他们都应为主机类别的 AllowedMembers 减去 DeniedMembers 所得到的子集的一部分。</span><span class="sxs-lookup"><span data-stu-id="66451-111">They all should be the subset of AllowedMembers minus DeniedMembers of the host Category.</span></span> <span data-ttu-id="66451-112">type=normal 的聊天室无法包含演示者。</span><span class="sxs-lookup"><span data-stu-id="66451-112">A room that is type=normal cannot include Presenters.</span></span>

<div>

## <a name="create-get-set-clear-or-remove-a-room"></a><span data-ttu-id="66451-113">创建、获取、设置、清除或删除聊天室</span><span class="sxs-lookup"><span data-stu-id="66451-113">Create, Get, Set, Clear, or Remove a Room</span></span>

<span data-ttu-id="66451-114">创建新聊天室</span><span class="sxs-lookup"><span data-stu-id="66451-114">To create a new room</span></span>

    New-CsPersistentChatRoom -Name <String> [-PersistentChatPoolFqdn <String>]-Category <String> [-Description <String>] [-Disabled <Switch Parameter>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Switch Parameter>]

<span data-ttu-id="66451-115">设置聊天室</span><span class="sxs-lookup"><span data-stu-id="66451-115">To set a room</span></span>

    Set-CsPersistentChatRoom -Identity <String> [-Name <String>] [-Category <String>] [-Description <String>] [-Disabled <boolean>] [-Type <Normal | Auditorium>] [-AddIn <String>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Invitations <Enum>] [-Members <PSListModifier<String>>] [-Managers <PSListModifier<String>>] [-Presenters <PSListModifier<String>>] [-Force < Switch Parameter >] [-Confirm <Switch Parameter>][-WhatIf <Switch Parameter>]

<span data-ttu-id="66451-116">获取聊天室</span><span class="sxs-lookup"><span data-stu-id="66451-116">To get a room</span></span>

    Get-CsPersistentChatRoom -Identity <String>

<span data-ttu-id="66451-117">或</span><span class="sxs-lookup"><span data-stu-id="66451-117">or</span></span>

    Get-CsPersistentChatRoom -filter <String> [-PersistentChatPoolFqdn <String>] [-SearchDescription] [-Member <String>] [-Manager <string>] [-Category <string>] [-Addin <string>] [-Disabled <bool>] [-Privacy <ChatRoomPrivacy> {Open | Closed | Secret}] [-Type <ChatRoomType> {Normal | Auditorium}] [-Invitations <ChatRoomInvitations> {False | Inherit}] [-ChatContentExceedsMB <int>] [-ResultSize <int>]

<span data-ttu-id="66451-118">其中 –filter 仅支持名称和说明，并可帮助您查找其名称/说明与关键字字符串匹配的聊天室。</span><span class="sxs-lookup"><span data-stu-id="66451-118">where –filter supports only Name and Description and helps you find rooms whose Name/Description matches the keyword string.</span></span> <span data-ttu-id="66451-119">PoolFqdn 在给定的持久聊天服务器池中进行搜索。</span><span class="sxs-lookup"><span data-stu-id="66451-119">PoolFqdn searches in a given Persistent Chat Server pool.</span></span>

<span data-ttu-id="66451-120">清除聊天室并清除聊天室中的消息</span><span class="sxs-lookup"><span data-stu-id="66451-120">To clear a room and clear messages from a room</span></span>

    Clear-CsPersistentChatRoom [-Identity] <string> -EndDate <DateTime> [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="66451-121">或</span><span class="sxs-lookup"><span data-stu-id="66451-121">or</span></span>

    Clear-CsPersistentChatRoom [-Instance] <ChatRoomObject> -EndDate <DateTime> [-WhatIf] [-Confirm] [<CommonParameters>]

<span data-ttu-id="66451-122">删除聊天室</span><span class="sxs-lookup"><span data-stu-id="66451-122">To remove a room</span></span>

    Remove-CsPersistentChatRoom [-Identity] <string> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

<span data-ttu-id="66451-123">或</span><span class="sxs-lookup"><span data-stu-id="66451-123">or</span></span>

    Remove-CsPersistentChatRoom [-Instance] <ChatRoomObject> [-Force] [-WhatIf] [-Confirm]  [<CommonParameters>]

</div>

</div>

<span> </span>

</div>

</div>

</div>

