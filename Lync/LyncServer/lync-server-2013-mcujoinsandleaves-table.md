---
title: Lync Server 2013： McuJoinsAndLeaves 表
description: Lync Server 2013： McuJoinsAndLeaves 表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves table
ms:assetid: 4e073366-0b5d-45b4-a3f6-d63dd5fd9f25
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398316(v=OCS.15)
ms:contentKeyID: 48184115
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee7d9473892ac357dcefd80b0d52382c5dd7d930
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556498"
---
# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="cebf4-103">Lync Server 2013 中的 McuJoinsAndLeaves 表</span><span class="sxs-lookup"><span data-stu-id="cebf4-103">McuJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cebf4-104">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="cebf4-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="cebf4-105">此表中的每条记录都包含有关用户加入或离开和会议服务器的一个组合的呼叫详细信息。</span><span class="sxs-lookup"><span data-stu-id="cebf4-105">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="cebf4-106">例如，如果用户加入包含 web 会议和音频/视频元素的会议，则会为该用户的 web 会议加入创建一条记录，并为用户的音频/视频会议加入创建另一条记录。</span><span class="sxs-lookup"><span data-stu-id="cebf4-106">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cebf4-107">列</span><span class="sxs-lookup"><span data-stu-id="cebf4-107">Column</span></span></th>
<th><span data-ttu-id="cebf4-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="cebf4-108">Data Type</span></span></th>
<th><span data-ttu-id="cebf4-109">键/索引</span><span class="sxs-lookup"><span data-stu-id="cebf4-109">Key/Index</span></span></th>
<th><span data-ttu-id="cebf4-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="cebf4-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cebf4-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="cebf4-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cebf4-112">datetime</span><span class="sxs-lookup"><span data-stu-id="cebf4-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="cebf4-113">主、外</span><span class="sxs-lookup"><span data-stu-id="cebf4-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="cebf4-114">会议实例的时间。</span><span class="sxs-lookup"><span data-stu-id="cebf4-114">Time of conference instance.</span></span> <span data-ttu-id="cebf4-115">与 <strong>SessionIdSeq</strong> 结合使用，以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="cebf4-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="cebf4-116">有关详细信息，请参阅 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="cebf4-116">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cebf4-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="cebf4-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cebf4-118">int</span><span class="sxs-lookup"><span data-stu-id="cebf4-118">int</span></span></p></td>
<td><p><span data-ttu-id="cebf4-119">主、外</span><span class="sxs-lookup"><span data-stu-id="cebf4-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="cebf4-120">用于标识会议实例的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="cebf4-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="cebf4-121">与 <strong>SessionIdTime</strong> 结合使用，以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="cebf4-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="cebf4-122">有关详细信息，请参阅 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="cebf4-122">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cebf4-123"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="cebf4-123"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="cebf4-124">int</span><span class="sxs-lookup"><span data-stu-id="cebf4-124">int</span></span></p></td>
<td><p><span data-ttu-id="cebf4-125">主、外</span><span class="sxs-lookup"><span data-stu-id="cebf4-125">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="cebf4-126">用于标识此用户的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="cebf4-126">Unique number identifying this user.</span></span> <span data-ttu-id="cebf4-127">有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="cebf4-127">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cebf4-128"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="cebf4-128"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="cebf4-129">int</span><span class="sxs-lookup"><span data-stu-id="cebf4-129">int</span></span></p></td>
<td><p><span data-ttu-id="cebf4-130">主</span><span class="sxs-lookup"><span data-stu-id="cebf4-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="cebf4-131">如果一次用户在多台计算机或设备上登录，则 McuUserInstance 将唯一标识该用户/设备组合。</span><span class="sxs-lookup"><span data-stu-id="cebf4-131">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cebf4-132"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="cebf4-132"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="cebf4-133">位</span><span class="sxs-lookup"><span data-stu-id="cebf4-133">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cebf4-134">用户是否从 PSTN 进行联接。</span><span class="sxs-lookup"><span data-stu-id="cebf4-134">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cebf4-135"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="cebf4-135"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="cebf4-136">int</span><span class="sxs-lookup"><span data-stu-id="cebf4-136">int</span></span></p></td>
<td><p><span data-ttu-id="cebf4-137">主、外</span><span class="sxs-lookup"><span data-stu-id="cebf4-137">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="cebf4-138">标识此会议服务器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="cebf4-138">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="cebf4-139">有关详细信息，请参阅 <a href="lync-server-2013-mcus-table.md">Lync Server 2013 中的 mcu 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="cebf4-139">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cebf4-140"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="cebf4-140"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cebf4-141">datetime</span><span class="sxs-lookup"><span data-stu-id="cebf4-141">datetime</span></span></p></td>
<td><p><span data-ttu-id="cebf4-142">对外</span><span class="sxs-lookup"><span data-stu-id="cebf4-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cebf4-143">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="cebf4-143">Time of session request.</span></span> <span data-ttu-id="cebf4-144">与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="cebf4-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="cebf4-145">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="cebf4-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cebf4-146"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="cebf4-146"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="cebf4-147">int</span><span class="sxs-lookup"><span data-stu-id="cebf4-147">int</span></span></p></td>
<td><p><span data-ttu-id="cebf4-148">对外</span><span class="sxs-lookup"><span data-stu-id="cebf4-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cebf4-149">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="cebf4-149">ID number to identify the session.</span></span> <span data-ttu-id="cebf4-150">与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="cebf4-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="cebf4-151">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="cebf4-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cebf4-152"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="cebf4-152"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cebf4-153">datetime</span><span class="sxs-lookup"><span data-stu-id="cebf4-153">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cebf4-154">此用户加入此会议服务器的时间。</span><span class="sxs-lookup"><span data-stu-id="cebf4-154">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cebf4-155"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="cebf4-155"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="cebf4-156">datetime</span><span class="sxs-lookup"><span data-stu-id="cebf4-156">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="cebf4-157">此用户离开此会议服务器的时间。</span><span class="sxs-lookup"><span data-stu-id="cebf4-157">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cebf4-158"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="cebf4-158"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="cebf4-159">int</span><span class="sxs-lookup"><span data-stu-id="cebf4-159">int</span></span></p></td>
<td><p><span data-ttu-id="cebf4-160">对外</span><span class="sxs-lookup"><span data-stu-id="cebf4-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="cebf4-161">指定在会议中使用的客户端软件版本号的标识符。</span><span class="sxs-lookup"><span data-stu-id="cebf4-161">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="cebf4-162">有关详细信息，请参阅 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="cebf4-162">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="cebf4-163">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="cebf4-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

