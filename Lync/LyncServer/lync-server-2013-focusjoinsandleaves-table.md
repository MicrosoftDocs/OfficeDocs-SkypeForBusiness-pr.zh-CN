---
title: Lync Server 2013： FocusJoinsAndLeaves 表
description: Lync Server 2013： FocusJoinsAndLeaves 表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5796de16ed204ce4f33935d937cbaa425d63a67f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577438"
---
# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="29b12-103">Lync Server 2013 中的 FocusJoinsAndLeaves 表</span><span class="sxs-lookup"><span data-stu-id="29b12-103">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="29b12-104">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="29b12-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="29b12-105">此表中的每条记录包含有关一个用户的加入的 CDR 信息，并为一个会议留下信息。</span><span class="sxs-lookup"><span data-stu-id="29b12-105">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="29b12-106">每次用户加入并离开会议时，每个会议都会在此表中代表一条记录。</span><span class="sxs-lookup"><span data-stu-id="29b12-106">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="29b12-107">列</span><span class="sxs-lookup"><span data-stu-id="29b12-107">Column</span></span></th>
<th><span data-ttu-id="29b12-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="29b12-108">Data Type</span></span></th>
<th><span data-ttu-id="29b12-109">键/索引</span><span class="sxs-lookup"><span data-stu-id="29b12-109">Key/Index</span></span></th>
<th><span data-ttu-id="29b12-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="29b12-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="29b12-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="29b12-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="29b12-112">datetime</span><span class="sxs-lookup"><span data-stu-id="29b12-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="29b12-113">主、外</span><span class="sxs-lookup"><span data-stu-id="29b12-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="29b12-114">会议实例的时间。</span><span class="sxs-lookup"><span data-stu-id="29b12-114">Time of conference instance.</span></span> <span data-ttu-id="29b12-115">与 <strong>SessionIdSeq</strong> 结合使用，以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="29b12-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="29b12-116">有关详细信息，请参阅 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="29b12-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29b12-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="29b12-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="29b12-118">int</span><span class="sxs-lookup"><span data-stu-id="29b12-118">int</span></span></p></td>
<td><p><span data-ttu-id="29b12-119">主、外</span><span class="sxs-lookup"><span data-stu-id="29b12-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="29b12-120">用于标识会议实例的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="29b12-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="29b12-121">与 <strong>SessionIdTime</strong> 结合使用，以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="29b12-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="29b12-122">有关详细信息，请参阅 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="29b12-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29b12-123"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="29b12-123"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="29b12-124">datetime</span><span class="sxs-lookup"><span data-stu-id="29b12-124">datetime</span></span></p></td>
<td><p><span data-ttu-id="29b12-125">主、外</span><span class="sxs-lookup"><span data-stu-id="29b12-125">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="29b12-126">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="29b12-126">Time of session request.</span></span> <span data-ttu-id="29b12-127">与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="29b12-127">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="29b12-128">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="29b12-128">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29b12-129"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="29b12-129"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="29b12-130">int</span><span class="sxs-lookup"><span data-stu-id="29b12-130">int</span></span></p></td>
<td><p><span data-ttu-id="29b12-131">主、外</span><span class="sxs-lookup"><span data-stu-id="29b12-131">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="29b12-132">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="29b12-132">ID number to identify the session.</span></span> <span data-ttu-id="29b12-133">与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="29b12-133">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="29b12-134">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="29b12-134">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29b12-135"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="29b12-135"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="29b12-136">int</span><span class="sxs-lookup"><span data-stu-id="29b12-136">int</span></span></p></td>
<td><p><span data-ttu-id="29b12-137">对外</span><span class="sxs-lookup"><span data-stu-id="29b12-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="29b12-138">标识此用户的唯一编号， <a href="lync-server-2013-users-table.md">在 Lync Server 2013 中的 "用户" 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="29b12-138">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29b12-139"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="29b12-139"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="29b12-140">int</span><span class="sxs-lookup"><span data-stu-id="29b12-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="29b12-141">如果用户同时在多台计算机或设备上登录，则 <strong>UserInstance</strong> 将用于唯一标识用户/设备组合。</span><span class="sxs-lookup"><span data-stu-id="29b12-141">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29b12-142"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="29b12-142"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="29b12-143">位</span><span class="sxs-lookup"><span data-stu-id="29b12-143">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="29b12-144">用户是否已从内部登录。</span><span class="sxs-lookup"><span data-stu-id="29b12-144">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29b12-145"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="29b12-145"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="29b12-146">int</span><span class="sxs-lookup"><span data-stu-id="29b12-146">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="29b12-147">此用户在会议中的角色，如演示者或与会者。</span><span class="sxs-lookup"><span data-stu-id="29b12-147">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29b12-148"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="29b12-148"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="29b12-149">datetime</span><span class="sxs-lookup"><span data-stu-id="29b12-149">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="29b12-150">此用户加入会议的时间。</span><span class="sxs-lookup"><span data-stu-id="29b12-150">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29b12-151"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="29b12-151"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="29b12-152">datetime</span><span class="sxs-lookup"><span data-stu-id="29b12-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="29b12-153">此用户离开会议的时间。</span><span class="sxs-lookup"><span data-stu-id="29b12-153">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="29b12-154"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="29b12-154"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="29b12-155">int</span><span class="sxs-lookup"><span data-stu-id="29b12-155">int</span></span></p></td>
<td><p><span data-ttu-id="29b12-156">对外</span><span class="sxs-lookup"><span data-stu-id="29b12-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="29b12-157">用户的客户端软件的版本， <a href="lync-server-2013-clientversions-table.md">在 Lync Server 2013 中引用 ClientVersions 表</a>。</span><span class="sxs-lookup"><span data-stu-id="29b12-157">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="29b12-158"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="29b12-158"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="29b12-159">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="29b12-159">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="29b12-160">会议中使用的终结点 (GUID) 的全局唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="29b12-160">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="29b12-161">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="29b12-161">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

