---
title: Lync Server 2013：tblRoleType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: tblRoleType
ms:assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558623(v=OCS.15)
ms:contentKeyID: 48183577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ba6b5041453b0965fafc12ada2be62ec42316f89
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41731182"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="287dc-102">Lync Server 2013 中的 tblRoleType</span><span class="sxs-lookup"><span data-stu-id="287dc-102">tblRoleType in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="287dc-103">_**主题上次修改时间：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="287dc-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="287dc-104">tblRoleType 是一个具有角色类型及其关联权限集的静态查找表。</span><span class="sxs-lookup"><span data-stu-id="287dc-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="287dc-105">多</span><span class="sxs-lookup"><span data-stu-id="287dc-105">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="287dc-106">列</span><span class="sxs-lookup"><span data-stu-id="287dc-106">Column</span></span></th>
<th><span data-ttu-id="287dc-107">类型</span><span class="sxs-lookup"><span data-stu-id="287dc-107">Type</span></span></th>
<th><span data-ttu-id="287dc-108">说明</span><span class="sxs-lookup"><span data-stu-id="287dc-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="287dc-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="287dc-109">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="287dc-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="287dc-110">int, not null</span></span></p></td>
<td><p><span data-ttu-id="287dc-111">角色类型 ID。</span><span class="sxs-lookup"><span data-stu-id="287dc-111">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="287dc-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="287dc-112">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="287dc-113">nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="287dc-113">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="287dc-114">角色类型说明。</span><span class="sxs-lookup"><span data-stu-id="287dc-114">Role type description.</span></span> <span data-ttu-id="287dc-115">有四个可用的角色：</span><span class="sxs-lookup"><span data-stu-id="287dc-115">There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="287dc-116">成员：聊天室成员</span><span class="sxs-lookup"><span data-stu-id="287dc-116">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="287dc-117">管理器：聊天室管理器</span><span class="sxs-lookup"><span data-stu-id="287dc-117">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="287dc-118">浊音：演示者使用 auditorium 聊天室</span><span class="sxs-lookup"><span data-stu-id="287dc-118">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="287dc-119">创建者：可以创建聊天室</span><span class="sxs-lookup"><span data-stu-id="287dc-119">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="287dc-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="287dc-120">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="287dc-121">bigint，not null</span><span class="sxs-lookup"><span data-stu-id="287dc-121">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="287dc-122">角色的权限集。</span><span class="sxs-lookup"><span data-stu-id="287dc-122">Permission set for the role.</span></span> <span data-ttu-id="287dc-123">所用位为：</span><span class="sxs-lookup"><span data-stu-id="287dc-123">The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="287dc-124">2：如果角色可以管理节点，则为 True。</span><span class="sxs-lookup"><span data-stu-id="287dc-124">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="287dc-125">4：如果角色可以创建子节点，则为 True。</span><span class="sxs-lookup"><span data-stu-id="287dc-125">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="287dc-126">7：如果角色可以加入聊天室（或类别的子聊天室），则为 True。</span><span class="sxs-lookup"><span data-stu-id="287dc-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="287dc-127">8：如果角色可以在聊天室中（或在子类别的子聊天室中）聊天，则为 True。</span><span class="sxs-lookup"><span data-stu-id="287dc-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="287dc-128">10：如果角色可以读取聊天历史记录（即使未加入聊天室），则为 True。</span><span class="sxs-lookup"><span data-stu-id="287dc-128">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="287dc-129">11：如果角色可以查看聊天室，则为 True。</span><span class="sxs-lookup"><span data-stu-id="287dc-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="287dc-130">（这将通过范围和可见性等因素进一步改进。）</span><span class="sxs-lookup"><span data-stu-id="287dc-130">(This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="287dc-131">12：如果角色可以在 auditorium 聊天室中聊天，则为 True。</span><span class="sxs-lookup"><span data-stu-id="287dc-131">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="287dc-132">13：如果角色在查看节点时可以绕过可见性规则，则为 True。</span><span class="sxs-lookup"><span data-stu-id="287dc-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="287dc-133">关键字</span><span class="sxs-lookup"><span data-stu-id="287dc-133">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="287dc-134">列</span><span class="sxs-lookup"><span data-stu-id="287dc-134">Column</span></span></th>
<th><span data-ttu-id="287dc-135">说明</span><span class="sxs-lookup"><span data-stu-id="287dc-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="287dc-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="287dc-136">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="287dc-137">主键。</span><span class="sxs-lookup"><span data-stu-id="287dc-137">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

