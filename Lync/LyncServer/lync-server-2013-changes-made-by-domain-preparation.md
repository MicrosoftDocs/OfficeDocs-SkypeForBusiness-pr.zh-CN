---
title: 'Lync Server 2013: 由域准备进行的更改'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Changes made by domain preparation
ms:assetid: 9191221e-6166-4c2b-837e-fa73d90fdf80
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398742(v=OCS.15)
ms:contentKeyID: 48184845
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b674e2c3d65aeda22838dca08ac5b016fa83359
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837611"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-made-by-domain-preparation-in-lync-server-2013"></a><span data-ttu-id="3cbfa-102">Lync Server 2013 中的域准备进行的更改</span><span class="sxs-lookup"><span data-stu-id="3cbfa-102">Changes made by domain preparation in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3cbfa-103">_**主题上次修改时间:** 2010-10-18_</span><span class="sxs-lookup"><span data-stu-id="3cbfa-103">_**Topic Last Modified:** 2010-10-18_</span></span>

<span data-ttu-id="3cbfa-104">下表列出了域准备在域根上创建的访问控制条目 (Ace)。</span><span class="sxs-lookup"><span data-stu-id="3cbfa-104">The following table lists the access control entries (ACEs) that domain preparation creates on the domain root.</span></span> <span data-ttu-id="3cbfa-105">除非另有说明, 否则将继承所有 Ace。</span><span class="sxs-lookup"><span data-stu-id="3cbfa-105">All ACEs are inherited unless otherwise noted.</span></span>

<div id="sectionSection0" class="section">

### <a name="aces-added-to-domain-root"></a><span data-ttu-id="3cbfa-106">添加到域根的 Ace</span><span class="sxs-lookup"><span data-stu-id="3cbfa-106">ACEs Added to Domain Root</span></span>

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
<th><span data-ttu-id="3cbfa-107">棒</span><span class="sxs-lookup"><span data-stu-id="3cbfa-107">ACE</span></span></th>
<th><span data-ttu-id="3cbfa-108">RTCUniversal-UserReadOnly</span><span class="sxs-lookup"><span data-stu-id="3cbfa-108">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="3cbfa-109">RTCUniversal-ServerReadOnly</span><span class="sxs-lookup"><span data-stu-id="3cbfa-109">RTCUniversal-ServerReadOnly-Group</span></span></th>
<th><span data-ttu-id="3cbfa-110">RTCUniversal-UserAdmins</span><span class="sxs-lookup"><span data-stu-id="3cbfa-110">RTCUniversal-UserAdmins</span></span></th>
<th><span data-ttu-id="3cbfa-111">RTCHSUniversal-服务</span><span class="sxs-lookup"><span data-stu-id="3cbfa-111">RTCHSUniversal-Services</span></span></th>
<th><span data-ttu-id="3cbfa-112">已验证-用户</span><span class="sxs-lookup"><span data-stu-id="3cbfa-112">Authenticated-Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3cbfa-113">读取容器 (不是继承的)</span><span class="sxs-lookup"><span data-stu-id="3cbfa-113">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-114"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="3cbfa-114"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3cbfa-115"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="3cbfa-115"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3cbfa-116">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-116">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-117">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-117">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-118">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-118">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cbfa-119">阅读用户 PropertySet 用户帐户-限制</span><span class="sxs-lookup"><span data-stu-id="3cbfa-119">Read User PropertySet User-Account-Restrictions</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-120"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="3cbfa-120"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3cbfa-121">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-121">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-122">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-122">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-123">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-123">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-124">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-124">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cbfa-125">阅读用户 PropertySet 个人信息</span><span class="sxs-lookup"><span data-stu-id="3cbfa-125">Read User PropertySet Personal-Information</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-126"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="3cbfa-126"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3cbfa-127">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-127">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-128">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-128">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-129">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-129">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-130">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-130">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cbfa-131">阅读用户 PropertySet 常规信息</span><span class="sxs-lookup"><span data-stu-id="3cbfa-131">Read User PropertySet General-Information</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-132"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="3cbfa-132"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3cbfa-133">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-133">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-134">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-134">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-135">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-135">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-136">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-136">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cbfa-137">读取用户 PropertySet 公共信息</span><span class="sxs-lookup"><span data-stu-id="3cbfa-137">Read User PropertySet Public-Information</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-138"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="3cbfa-138"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3cbfa-139">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-139">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-140">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-140">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-141">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-141">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-142">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-142">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cbfa-143">Read User PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="3cbfa-143">Read User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-144"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="3cbfa-144"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3cbfa-145">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-145">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-146">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-146">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-147">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-147">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-148"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="3cbfa-148"><strong>Yes</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cbfa-149">阅读用户 PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="3cbfa-149">Read User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-150"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="3cbfa-150"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3cbfa-151">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-151">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-152">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-152">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-153">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-153">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-154">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-154">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cbfa-155">编写用户属性代理-地址</span><span class="sxs-lookup"><span data-stu-id="3cbfa-155">Write User Property Proxy-Addresses</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-156">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-156">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-157">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-157">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-158"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="3cbfa-158"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3cbfa-159">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-159">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-160">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-160">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cbfa-161">编写用户 PropertySet RTCUserSearchProperty-Set</span><span class="sxs-lookup"><span data-stu-id="3cbfa-161">Write User PropertySet RTCUserSearchProperty-Set</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-162">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-162">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-163">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-163">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-164"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="3cbfa-164"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3cbfa-165">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-165">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-166">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-166">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3cbfa-167">编写用户 PropertySet RTCPropertySet</span><span class="sxs-lookup"><span data-stu-id="3cbfa-167">Write User PropertySet RTCPropertySet</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-168">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-168">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-169">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-169">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-170"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="3cbfa-170"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3cbfa-171">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-171">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-172">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-172">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3cbfa-173">读取 PropertySet DS-复制-对所有 Active Directory 对象的获取更改</span><span class="sxs-lookup"><span data-stu-id="3cbfa-173">Read PropertySet DS-Replication-Get-Changes of all Active Directory objects</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-174">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-174">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-175">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-175">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-176">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-176">No</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-177"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="3cbfa-177"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3cbfa-178">否</span><span class="sxs-lookup"><span data-stu-id="3cbfa-178">No</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="3cbfa-179">下表列出了域准备在三个内置容器中创建的 Ace: 用户、计算机和域控制器。</span><span class="sxs-lookup"><span data-stu-id="3cbfa-179">The following table lists the ACEs that domain preparation creates in the three built-in containers: Users, Computers, and Domain Controllers.</span></span> <span data-ttu-id="3cbfa-180">除非另有说明, 否则将继承所有 Ace。</span><span class="sxs-lookup"><span data-stu-id="3cbfa-180">All ACEs are inherited unless otherwise noted.</span></span>

### <a name="aces-added-to-built-in-containers"></a><span data-ttu-id="3cbfa-181">添加到内置容器的 Ace</span><span class="sxs-lookup"><span data-stu-id="3cbfa-181">ACEs Added to Built-in Containers</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3cbfa-182">棒</span><span class="sxs-lookup"><span data-stu-id="3cbfa-182">ACE</span></span></th>
<th><span data-ttu-id="3cbfa-183">RTCUniversal-UserReadOnly</span><span class="sxs-lookup"><span data-stu-id="3cbfa-183">RTCUniversal-UserReadOnly-Group</span></span></th>
<th><span data-ttu-id="3cbfa-184">RTCUniversal-ServerReadOnly</span><span class="sxs-lookup"><span data-stu-id="3cbfa-184">RTCUniversal-ServerReadOnly-Group</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3cbfa-185">读取容器 (不是继承的)</span><span class="sxs-lookup"><span data-stu-id="3cbfa-185">Read Container (not inherited)</span></span></p></td>
<td><p><span data-ttu-id="3cbfa-186"><strong>是的</strong></span><span class="sxs-lookup"><span data-stu-id="3cbfa-186"><strong>Yes</strong></span></span></p></td>
<td><p><span data-ttu-id="3cbfa-187"><strong>是</strong></span><span class="sxs-lookup"><span data-stu-id="3cbfa-187"><strong>Yes</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

