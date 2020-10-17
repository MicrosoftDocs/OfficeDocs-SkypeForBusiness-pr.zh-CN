---
title: Lync Server 2013： tblRoleType
description: Lync Server 2013： tblRoleType。
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
ms.openlocfilehash: f458259acaee7821d5f6a7339b993c70fe65f595
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568538"
---
# <a name="tblroletype-in-lync-server-2013"></a><span data-ttu-id="f63c9-103">Lync Server 2013 中的 tblRoleType</span><span class="sxs-lookup"><span data-stu-id="f63c9-103">tblRoleType in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f63c9-104">_**上次修改的主题：** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="f63c9-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="f63c9-105">tblRoleType 是一个静态查找表，其中包含角色类型及其关联的权限集。</span><span class="sxs-lookup"><span data-stu-id="f63c9-105">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>

### <a name="columns"></a><span data-ttu-id="f63c9-106">列数</span><span class="sxs-lookup"><span data-stu-id="f63c9-106">Columns</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f63c9-107">列</span><span class="sxs-lookup"><span data-stu-id="f63c9-107">Column</span></span></th>
<th><span data-ttu-id="f63c9-108">类型</span><span class="sxs-lookup"><span data-stu-id="f63c9-108">Type</span></span></th>
<th><span data-ttu-id="f63c9-109">说明</span><span class="sxs-lookup"><span data-stu-id="f63c9-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f63c9-110">rtypeID</span><span class="sxs-lookup"><span data-stu-id="f63c9-110">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="f63c9-111">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="f63c9-111">int, not null</span></span></p></td>
<td><p><span data-ttu-id="f63c9-112">角色类型 ID。</span><span class="sxs-lookup"><span data-stu-id="f63c9-112">Role type ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f63c9-113">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="f63c9-113">rtypeDesc</span></span></p></td>
<td><p><span data-ttu-id="f63c9-114">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="f63c9-114">nvarchar (256), not null</span></span></p></td>
<td><p><span data-ttu-id="f63c9-p101">角色类型描述。可用角色有四种：</span><span class="sxs-lookup"><span data-stu-id="f63c9-p101">Role type description. There are four available roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="f63c9-117">成员：聊天室成员</span><span class="sxs-lookup"><span data-stu-id="f63c9-117">Member: Chat room member</span></span></p></li>
<li><p><span data-ttu-id="f63c9-118">管理员：聊天室管理员</span><span class="sxs-lookup"><span data-stu-id="f63c9-118">Manager: Chat room manager</span></span></p></li>
<li><p><span data-ttu-id="f63c9-119">有发布权的人：大会堂聊天室的演讲者</span><span class="sxs-lookup"><span data-stu-id="f63c9-119">Voiced: Presenter for an auditorium chat room</span></span></p></li>
<li><p><span data-ttu-id="f63c9-120">创建者：可以创建聊天室</span><span class="sxs-lookup"><span data-stu-id="f63c9-120">Creator: Can create chat rooms</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f63c9-121">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="f63c9-121">rtypeAllowedPermSet</span></span></p></td>
<td><p><span data-ttu-id="f63c9-122">bigint，不为 null</span><span class="sxs-lookup"><span data-stu-id="f63c9-122">bigint, not null</span></span></p></td>
<td><p><span data-ttu-id="f63c9-p102">角色的权限集。使用的位为：</span><span class="sxs-lookup"><span data-stu-id="f63c9-p102">Permission set for the role. The used bits are:</span></span></p>
<ul>
<li><p><span data-ttu-id="f63c9-125">2：在角色可以管理节点时为 True。</span><span class="sxs-lookup"><span data-stu-id="f63c9-125">2: True if the role can manage nodes.</span></span></p></li>
<li><p><span data-ttu-id="f63c9-126">4：在角色可以创建子节点时为 True。</span><span class="sxs-lookup"><span data-stu-id="f63c9-126">4: True if the role can create children nodes.</span></span></p></li>
<li><p><span data-ttu-id="f63c9-127">7：在角色可以加入聊天室（或某类别的子聊天室）时为 True。</span><span class="sxs-lookup"><span data-stu-id="f63c9-127">7: True if the role can join a chat room (or children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="f63c9-128">8：在角色可以在聊天室中（或某类别的子聊天室中）聊天时为 True。</span><span class="sxs-lookup"><span data-stu-id="f63c9-128">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span></p></li>
<li><p><span data-ttu-id="f63c9-129">10：在角色即使不加入聊天室也可读取聊天历史记录时为 True。</span><span class="sxs-lookup"><span data-stu-id="f63c9-129">10: True if the role can read chat history even when not joined to a chat room.</span></span></p></li>
<li><p><span data-ttu-id="f63c9-p103">11：在角色可以看到聊天室时为 True。（该值可通过作用域和可见性等因素进一步优化。）</span><span class="sxs-lookup"><span data-stu-id="f63c9-p103">11: True if the role can see the chat room. (This is further refined by factors such as scope and visibility.)</span></span></p></li>
<li><p><span data-ttu-id="f63c9-132">12：在角色可以在大会堂聊天室中聊天时为 True。</span><span class="sxs-lookup"><span data-stu-id="f63c9-132">12: True if the role can chat in an auditorium chat room.</span></span></p></li>
<li><p><span data-ttu-id="f63c9-133">13：在角色查看节点后可以绕过可见性规则时为 True。</span><span class="sxs-lookup"><span data-stu-id="f63c9-133">13: True if the role can bypass visibility rules when viewing nodes.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


### <a name="key"></a><span data-ttu-id="f63c9-134">键</span><span class="sxs-lookup"><span data-stu-id="f63c9-134">Key</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f63c9-135">列</span><span class="sxs-lookup"><span data-stu-id="f63c9-135">Column</span></span></th>
<th><span data-ttu-id="f63c9-136">说明</span><span class="sxs-lookup"><span data-stu-id="f63c9-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f63c9-137">rtypeID</span><span class="sxs-lookup"><span data-stu-id="f63c9-137">rtypeID</span></span></p></td>
<td><p><span data-ttu-id="f63c9-138">主键。</span><span class="sxs-lookup"><span data-stu-id="f63c9-138">Primary key.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

