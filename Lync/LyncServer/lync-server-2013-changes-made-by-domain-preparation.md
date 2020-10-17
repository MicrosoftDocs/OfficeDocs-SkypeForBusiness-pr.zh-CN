---
title: Lync Server 2013：域准备所做的更改
description: Lync Server 2013：由域准备进行的更改。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26400bd1c72c6ae3b8dc1f2d2d8f6c6906b80595
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543688"
---
# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="fd78f-103">Lync Server 2013 中的域准备所做的更改</span><span class="sxs-lookup"><span data-stu-id="fd78f-103">Changes made by domain preparation in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fd78f-104">_**上次修改的主题：** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="fd78f-104">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="fd78f-p101">下表列出域准备在域根上创建的访问控制项 (ACE)。除非另行说明，否则所有 ACE 都是继承的。</span><span class="sxs-lookup"><span data-stu-id="fd78f-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="fd78f-107">添加到域根的 ACE</span><span class="sxs-lookup"><span data-stu-id="fd78f-107">ACEs Added to Domain Root</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd78f-108">ACE</span><span class="sxs-lookup"><span data-stu-id="fd78f-108">ACE</span></span></th>
<th><span data-ttu-id="fd78f-109">RTCUniversal-UserReadOnly-组</span><span class="sxs-lookup"><span data-stu-id="fd78f-109">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="fd78f-110">RTCUniversal-ServerReadOnly-组</span><span class="sxs-lookup"><span data-stu-id="fd78f-110">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="fd78f-111">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="fd78f-111">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="fd78f-112">RTCHSUniversal-Services</span><span class="sxs-lookup"><span data-stu-id="fd78f-112">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="fd78f-113">Authenticated-Users</span><span class="sxs-lookup"><span data-stu-id="fd78f-113">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd78f-114">读取容器（非继承）</span><span class="sxs-lookup"><span data-stu-id="fd78f-114">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="fd78f-115"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="fd78f-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="fd78f-116"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="fd78f-116"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="fd78f-117">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-117">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-118">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-118">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-119">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-119">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd78f-120">读取用户属性集 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="fd78f-120">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="fd78f-121"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="fd78f-121"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="fd78f-122">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-122">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-123">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-123">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-124">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-124">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-125">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-125">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd78f-126">读取用户属性集 Personal-Information</span><span class="sxs-lookup"><span data-stu-id="fd78f-126">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="fd78f-127"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="fd78f-127"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="fd78f-128">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-128">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-129">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-129">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-130">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-130">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-131">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-131">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd78f-132">读取用户属性集 General-Information</span><span class="sxs-lookup"><span data-stu-id="fd78f-132">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="fd78f-133"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="fd78f-133"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="fd78f-134">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-134">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-135">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-135">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-136">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-136">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-137">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-137">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd78f-138">读取用户属性集 Public-Information</span><span class="sxs-lookup"><span data-stu-id="fd78f-138">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="fd78f-139"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="fd78f-139"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="fd78f-140">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-140">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-141">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-141">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-142">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-142">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-143">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-143">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd78f-144">读取用户属性集 RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="fd78f-144">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="fd78f-145"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="fd78f-145"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="fd78f-146">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-146">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-147">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-147">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-148">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-148">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-149"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="fd78f-149"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd78f-150">读取用户属性集 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="fd78f-150">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="fd78f-151"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="fd78f-151"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="fd78f-152">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-152">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-153">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-153">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-154">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-154">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-155">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-155">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd78f-156">写入用户属性 Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="fd78f-156">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="fd78f-157">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-157">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-158">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-158">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-159"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="fd78f-159"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="fd78f-160">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-160">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-161">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-161">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd78f-162">写入用户属性集 RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="fd78f-162">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="fd78f-163">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-163">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-164">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-164">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-165"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="fd78f-165"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="fd78f-166">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-166">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-167">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-167">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fd78f-168">写入用户属性集 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="fd78f-168">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="fd78f-169">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-169">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-170">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-170">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-171"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="fd78f-171"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="fd78f-172">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-172">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-173">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-173">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fd78f-174">读取所有 Active Directory 对象的属性集 DS-Replication-Get-Changes</span><span class="sxs-lookup"><span data-stu-id="fd78f-174">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="fd78f-175">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-175">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-176">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-176">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-177">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-177">No</span></span></p></td>
<td><p><span data-ttu-id="fd78f-178"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="fd78f-178"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="fd78f-179">否</span><span class="sxs-lookup"><span data-stu-id="fd78f-179">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="fd78f-p102">下表列出域准备在以下三个内置容器中创建的 ACE：用户、计算机和域控制器。除非另行说明，否则所有 ACE 都是继承的。</span><span class="sxs-lookup"><span data-stu-id="fd78f-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="fd78f-182">添加到内置容器的 ACE</span><span class="sxs-lookup"><span data-stu-id="fd78f-182">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fd78f-183">ACE</span><span class="sxs-lookup"><span data-stu-id="fd78f-183">ACE</span></span></th>
<th><span data-ttu-id="fd78f-184">RTCUniversal-UserReadOnly-组</span><span class="sxs-lookup"><span data-stu-id="fd78f-184">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="fd78f-185">RTCUniversal-ServerReadOnly-组</span><span class="sxs-lookup"><span data-stu-id="fd78f-185">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fd78f-186">读取容器（非继承）</span><span class="sxs-lookup"><span data-stu-id="fd78f-186">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="fd78f-187"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="fd78f-187"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="fd78f-188"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="fd78f-188"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

