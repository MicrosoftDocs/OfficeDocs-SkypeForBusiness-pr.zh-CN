---
title: Lync Server 2013：tblRoleType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 698d6b07d5662a403a7485d009a39a0a8beccc73
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845712"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="0c768-102">Lync Server 2013 中的 tblRoleType</span><span class="sxs-lookup"><span data-stu-id="0c768-102">tblRoleType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0c768-103">_**主题上次修改时间:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="0c768-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="0c768-104">tblRoleType 是一个具有角色类型及其关联权限集的静态查找表。</span><span class="sxs-lookup"><span data-stu-id="0c768-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="0c768-105">多</span><span class="sxs-lookup"><span data-stu-id="0c768-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c768-106">列</span><span class="sxs-lookup"><span data-stu-id="0c768-106">Column</span></span></th>
<th><span data-ttu-id="0c768-107">类型</span><span class="sxs-lookup"><span data-stu-id="0c768-107">Type</span></span></th>
<th><span data-ttu-id="0c768-108">说明</span><span class="sxs-lookup"><span data-stu-id="0c768-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c768-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="0c768-109">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="0c768-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="0c768-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="0c768-111">角色类型 ID。</span><span class="sxs-lookup"><span data-stu-id="0c768-111">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0c768-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="0c768-112">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="0c768-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="0c768-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="0c768-114">角色类型说明。</span><span class="sxs-lookup"><span data-stu-id="0c768-114">Role type description.</span></span> <span data-ttu-id="0c768-115">有四个可用的角色:</span><span class="sxs-lookup"><span data-stu-id="0c768-115">There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="0c768-116">成员: 聊天室成员</span><span class="sxs-lookup"><span data-stu-id="0c768-116">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="0c768-117">管理器: 聊天室管理器</span><span class="sxs-lookup"><span data-stu-id="0c768-117">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="0c768-118">浊音: 演示者使用 auditorium 聊天室</span><span class="sxs-lookup"><span data-stu-id="0c768-118">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="0c768-119">创建者: 可以创建聊天室</span><span class="sxs-lookup"><span data-stu-id="0c768-119">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0c768-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="0c768-120">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="0c768-121">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="0c768-121">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="0c768-122">角色的权限集。</span><span class="sxs-lookup"><span data-stu-id="0c768-122">Permission set for the role.</span></span> <span data-ttu-id="0c768-123">所用位为:</span><span class="sxs-lookup"><span data-stu-id="0c768-123">The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="0c768-124">2: 如果角色可以管理节点, 则为 True。</span><span class="sxs-lookup"><span data-stu-id="0c768-124">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="0c768-125">4: 如果角色可以创建子节点, 则为 True。</span><span class="sxs-lookup"><span data-stu-id="0c768-125">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="0c768-126">7: 如果角色可以加入聊天室 (或类别的子聊天室), 则为 True。</span><span class="sxs-lookup"><span data-stu-id="0c768-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="0c768-127">8: 如果角色可以在聊天室中 (或在子类别的子聊天室中) 聊天, 则为 True。</span><span class="sxs-lookup"><span data-stu-id="0c768-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="0c768-128">10: 如果角色可以读取聊天历史记录 (即使未加入聊天室), 则为 True。</span><span class="sxs-lookup"><span data-stu-id="0c768-128">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="0c768-129">11: 如果角色可以查看聊天室, 则为 True。</span><span class="sxs-lookup"><span data-stu-id="0c768-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="0c768-130">(这将通过范围和可见性等因素进一步改进。)</span><span class="sxs-lookup"><span data-stu-id="0c768-130">(This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="0c768-131">12: 如果角色可以在 auditorium 聊天室中聊天, 则为 True。</span><span class="sxs-lookup"><span data-stu-id="0c768-131">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="0c768-132">13: 如果角色在查看节点时可以绕过可见性规则, 则为 True。</span><span class="sxs-lookup"><span data-stu-id="0c768-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="0c768-133">关键字</span><span class="sxs-lookup"><span data-stu-id="0c768-133">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0c768-134">列</span><span class="sxs-lookup"><span data-stu-id="0c768-134">Column</span></span></th>
<th><span data-ttu-id="0c768-135">说明</span><span class="sxs-lookup"><span data-stu-id="0c768-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0c768-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="0c768-136">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="0c768-137">主键。</span><span class="sxs-lookup"><span data-stu-id="0c768-137">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

