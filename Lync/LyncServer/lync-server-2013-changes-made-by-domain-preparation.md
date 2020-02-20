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
ms.openlocfilehash: 3e02224636b3e5179a8834e5dd59c0218956e6eb
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151042"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="0d70a-102">Lync Server 2013 中的域准备所做的更改</span><span class="sxs-lookup"><span data-stu-id="0d70a-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0d70a-103">_**上次修改的主题：** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="0d70a-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="0d70a-p101">下表列出域准备在域根上创建的访问控制项 (ACE)。除非另行说明，否则所有 ACE 都是继承的。</span><span class="sxs-lookup"><span data-stu-id="0d70a-p101">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root. All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="0d70a-106">添加到域根的 ACE</span><span class="sxs-lookup"><span data-stu-id="0d70a-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="0d70a-107">ACE</span><span class="sxs-lookup"><span data-stu-id="0d70a-107">ACE</span></span></th>
<th><span data-ttu-id="0d70a-108">RTCUniversal-UserReadOnly-组</span><span class="sxs-lookup"><span data-stu-id="0d70a-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="0d70a-109">RTCUniversal-ServerReadOnly-组</span><span class="sxs-lookup"><span data-stu-id="0d70a-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="0d70a-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="0d70a-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="0d70a-111">RTCHSUniversal-服务</span><span class="sxs-lookup"><span data-stu-id="0d70a-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="0d70a-112">已通过身份验证-用户</span><span class="sxs-lookup"><span data-stu-id="0d70a-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-113">读取容器（非继承）</span><span class="sxs-lookup"><span data-stu-id="0d70a-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="0d70a-114"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-115"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-116">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-116">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-117">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-117">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-118">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-119">读取用户属性集 User-Account-Restrictions</span><span class="sxs-lookup"><span data-stu-id="0d70a-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="0d70a-120"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-121">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-121">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-122">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-122">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-123">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-123">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-124">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-125">读取用户属性集 Personal-Information</span><span class="sxs-lookup"><span data-stu-id="0d70a-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="0d70a-126"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-127">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-127">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-128">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-128">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-129">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-129">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-130">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-131">读取用户属性集 General-Information</span><span class="sxs-lookup"><span data-stu-id="0d70a-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="0d70a-132"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-133">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-133">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-134">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-134">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-135">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-135">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-136">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-137">读取用户属性集 Public-Information</span><span class="sxs-lookup"><span data-stu-id="0d70a-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="0d70a-138"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-139">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-139">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-140">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-140">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-141">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-141">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-142">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-143">读取用户属性集 RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="0d70a-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="0d70a-144"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-145">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-145">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-146">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-146">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-147">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-147">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-148"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-149">读取用户属性集 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="0d70a-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="0d70a-150"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-151">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-151">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-152">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-152">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-153">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-153">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-154">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-155">写入用户属性 Proxy-Addresses</span><span class="sxs-lookup"><span data-stu-id="0d70a-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="0d70a-156">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-156">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-157">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-157">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-158"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-159">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-159">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-160">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-161">写入用户属性集 RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="0d70a-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="0d70a-162">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-162">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-163">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-163">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-164"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-165">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-165">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-166">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0d70a-167">写入用户属性集 RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="0d70a-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="0d70a-168">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-168">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-169">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-169">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-170"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-171">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-171">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-172">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-173">读取所有 Active Directory 对象的属性集 DS-Replication-Get-Changes</span><span class="sxs-lookup"><span data-stu-id="0d70a-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="0d70a-174">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-174">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-175">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-175">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-176">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-176">No</span></span></p></td>
<td><p><span data-ttu-id="0d70a-177"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-178">否</span><span class="sxs-lookup"><span data-stu-id="0d70a-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="0d70a-p102">下表列出域准备在以下三个内置容器中创建的 ACE：用户、计算机和域控制器。除非另行说明，否则所有 ACE 都是继承的。</span><span class="sxs-lookup"><span data-stu-id="0d70a-p102">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers. All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="0d70a-181">添加到内置容器的 ACE</span><span class="sxs-lookup"><span data-stu-id="0d70a-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0d70a-182">ACE</span><span class="sxs-lookup"><span data-stu-id="0d70a-182">ACE</span></span></th>
<th><span data-ttu-id="0d70a-183">RTCUniversal-UserReadOnly-组</span><span class="sxs-lookup"><span data-stu-id="0d70a-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="0d70a-184">RTCUniversal-ServerReadOnly-组</span><span class="sxs-lookup"><span data-stu-id="0d70a-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0d70a-185">读取容器（非继承）</span><span class="sxs-lookup"><span data-stu-id="0d70a-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="0d70a-186"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="0d70a-187"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="0d70a-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

