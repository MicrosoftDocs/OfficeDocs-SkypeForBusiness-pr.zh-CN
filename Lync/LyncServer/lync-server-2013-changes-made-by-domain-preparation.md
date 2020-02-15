---
title: Lync Server 2013：域准备所做的更改
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
ms.openlocfilehash: fb693f79470e7d68a1aaf662c9ab82b8bafa5c39
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037252"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="c89f4-102">Lync Server 2013 中的域准备所做的更改</span><span class="sxs-lookup"><span data-stu-id="c89f4-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c89f4-103">_**上次修改的主题：** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="c89f4-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="c89f4-p101">下表列出域准备在域根上创建的访问控制项 (ACE)。除非另行说明，否则所有 ACE 都是继承的。</span><span class="sxs-lookup"><span data-stu-id="c89f4-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="c89f4-106">添加到域根的 ACE</span><span class="sxs-lookup"><span data-stu-id="c89f4-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="c89f4-107">ACE</span><span class="sxs-lookup"><span data-stu-id="c89f4-107">ACE</span></span></th>
<th><span data-ttu-id="c89f4-108">RTCUniversal-UserReadOnly-组</span><span class="sxs-lookup"><span data-stu-id="c89f4-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="c89f4-109">RTCUniversal-ServerReadOnly-组</span><span class="sxs-lookup"><span data-stu-id="c89f4-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="c89f4-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="c89f4-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="c89f4-111">RTCHSUniversal-服务</span><span class="sxs-lookup"><span data-stu-id="c89f4-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="c89f4-112">已通过身份验证-用户</span><span class="sxs-lookup"><span data-stu-id="c89f4-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c89f4-113">读取容器（非继承）</span><span class="sxs-lookup"><span data-stu-id="c89f4-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="c89f4-114"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="c89f4-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c89f4-115"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="c89f4-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c89f4-116">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-116">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-117">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-117">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-118">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c89f4-119">读取用户属性集 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="c89f4-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="c89f4-120"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="c89f4-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c89f4-121">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-121">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-122">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-122">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-123">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-123">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-124">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c89f4-125">读取用户属性集 Personal-Information</span><span class="sxs-lookup"><span data-stu-id="c89f4-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="c89f4-126"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="c89f4-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c89f4-127">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-127">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-128">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-128">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-129">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-129">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-130">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c89f4-131">读取用户属性集 General-Information</span><span class="sxs-lookup"><span data-stu-id="c89f4-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="c89f4-132"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="c89f4-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c89f4-133">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-133">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-134">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-134">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-135">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-135">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-136">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c89f4-137">读取用户属性集 Public-Information</span><span class="sxs-lookup"><span data-stu-id="c89f4-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="c89f4-138"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="c89f4-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c89f4-139">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-139">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-140">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-140">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-141">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-141">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-142">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c89f4-143">读取用户属性集 RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="c89f4-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="c89f4-144"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="c89f4-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c89f4-145">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-145">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-146">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-146">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-147">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-147">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-148"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="c89f4-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c89f4-149">读取用户属性集 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="c89f4-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="c89f4-150"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="c89f4-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c89f4-151">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-151">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-152">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-152">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-153">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-153">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-154">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c89f4-155">写入用户属性 Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="c89f4-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="c89f4-156">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-156">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-157">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-157">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-158"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="c89f4-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c89f4-159">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-159">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-160">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c89f4-161">写入用户属性集 RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="c89f4-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="c89f4-162">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-162">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-163">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-163">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-164"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="c89f4-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c89f4-165">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-165">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-166">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c89f4-167">写入用户属性集 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="c89f4-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="c89f4-168">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-168">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-169">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-169">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-170"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="c89f4-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c89f4-171">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-171">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-172">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c89f4-173">读取所有 Active Directory 对象的属性集 DS-Replication-Get-Changes</span><span class="sxs-lookup"><span data-stu-id="c89f4-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="c89f4-174">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-174">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-175">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-175">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-176">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-176">No</span></span></p></td>
<td><p><span data-ttu-id="c89f4-177"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="c89f4-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c89f4-178">否</span><span class="sxs-lookup"><span data-stu-id="c89f4-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c89f4-p102">下表列出域准备在以下三个内置容器中创建的 ACE：用户、计算机和域控制器。除非另行说明，否则所有 ACE 都是继承的。</span><span class="sxs-lookup"><span data-stu-id="c89f4-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="c89f4-181">添加到内置容器的 ACE</span><span class="sxs-lookup"><span data-stu-id="c89f4-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c89f4-182">ACE</span><span class="sxs-lookup"><span data-stu-id="c89f4-182">ACE</span></span></th>
<th><span data-ttu-id="c89f4-183">RTCUniversal-UserReadOnly-组</span><span class="sxs-lookup"><span data-stu-id="c89f4-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="c89f4-184">RTCUniversal-ServerReadOnly-组</span><span class="sxs-lookup"><span data-stu-id="c89f4-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c89f4-185">读取容器（非继承）</span><span class="sxs-lookup"><span data-stu-id="c89f4-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="c89f4-186"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="c89f4-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="c89f4-187"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="c89f4-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

