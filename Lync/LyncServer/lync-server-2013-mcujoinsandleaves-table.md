---
title: Lync Server 2013：McuJoinsAndLeaves 表
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
ms.openlocfilehash: 204906deb88a2067b7304088515b25fee2da0350
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="8678c-102">Lync Server 2013 中的 McuJoinsAndLeaves 表</span><span class="sxs-lookup"><span data-stu-id="8678c-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8678c-103">_**主题上次修改时间：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="8678c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="8678c-104">此表中的每条记录包含有关用户加入或离开和会议服务器的一个组合的调用详细信息。</span><span class="sxs-lookup"><span data-stu-id="8678c-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="8678c-105">例如，如果用户加入包含 web 会议和音频/视频元素的会议，将为该用户的网络会议加入创建一条记录，并且将为用户的音频/视频会议加入创建另一条记录。</span><span class="sxs-lookup"><span data-stu-id="8678c-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8678c-106">列</span><span class="sxs-lookup"><span data-stu-id="8678c-106">Column</span></span></th>
<th><span data-ttu-id="8678c-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="8678c-107">Data Type</span></span></th>
<th><span data-ttu-id="8678c-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="8678c-108">Key/Index</span></span></th>
<th><span data-ttu-id="8678c-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="8678c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8678c-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="8678c-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8678c-111">datetime</span><span class="sxs-lookup"><span data-stu-id="8678c-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="8678c-112">主、外部</span><span class="sxs-lookup"><span data-stu-id="8678c-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8678c-113">会议实例的时间。</span><span class="sxs-lookup"><span data-stu-id="8678c-113">Time of conference instance.</span></span> <span data-ttu-id="8678c-114">与<strong>SessionIdSeq</strong>结合使用以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="8678c-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="8678c-115">有关详细信息，请参阅<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="8678c-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8678c-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8678c-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8678c-117">int</span><span class="sxs-lookup"><span data-stu-id="8678c-117">int</span></span></p></td>
<td><p><span data-ttu-id="8678c-118">主、外部</span><span class="sxs-lookup"><span data-stu-id="8678c-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8678c-119">标识会议实例的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="8678c-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="8678c-120">与<strong>SessionIdTime</strong>结合使用以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="8678c-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="8678c-121">有关详细信息，请参阅<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="8678c-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8678c-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="8678c-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="8678c-123">int</span><span class="sxs-lookup"><span data-stu-id="8678c-123">int</span></span></p></td>
<td><p><span data-ttu-id="8678c-124">主、外部</span><span class="sxs-lookup"><span data-stu-id="8678c-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8678c-125">标识此用户的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="8678c-125">Unique number identifying this user.</span></span> <span data-ttu-id="8678c-126">有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 "用户" 表。</span><span class="sxs-lookup"><span data-stu-id="8678c-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8678c-127"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="8678c-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="8678c-128">int</span><span class="sxs-lookup"><span data-stu-id="8678c-128">int</span></span></p></td>
<td><p><span data-ttu-id="8678c-129">Primary</span><span class="sxs-lookup"><span data-stu-id="8678c-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="8678c-130">如果一次用户在多台计算机或设备上登录，McuUserInstance 将唯一标识用户/设备组合。</span><span class="sxs-lookup"><span data-stu-id="8678c-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8678c-131"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="8678c-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="8678c-132">bit</span><span class="sxs-lookup"><span data-stu-id="8678c-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8678c-133">用户是否从 PSTN 进行联接。</span><span class="sxs-lookup"><span data-stu-id="8678c-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8678c-134"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="8678c-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="8678c-135">int</span><span class="sxs-lookup"><span data-stu-id="8678c-135">int</span></span></p></td>
<td><p><span data-ttu-id="8678c-136">主、外部</span><span class="sxs-lookup"><span data-stu-id="8678c-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="8678c-137">标识此会议服务器的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="8678c-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="8678c-138">有关详细信息，请参阅<a href="lync-server-2013-mcus-table.md">Lync Server 2013 中的 Mcus 表</a>。</span><span class="sxs-lookup"><span data-stu-id="8678c-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8678c-139"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="8678c-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8678c-140">datetime</span><span class="sxs-lookup"><span data-stu-id="8678c-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="8678c-141">外表</span><span class="sxs-lookup"><span data-stu-id="8678c-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8678c-142">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="8678c-142">Time of session request.</span></span> <span data-ttu-id="8678c-143">与<strong>SessionIdSeq</strong>结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="8678c-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="8678c-144">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="8678c-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8678c-145"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="8678c-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="8678c-146">int</span><span class="sxs-lookup"><span data-stu-id="8678c-146">int</span></span></p></td>
<td><p><span data-ttu-id="8678c-147">外表</span><span class="sxs-lookup"><span data-stu-id="8678c-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8678c-148">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="8678c-148">ID number to identify the session.</span></span> <span data-ttu-id="8678c-149">与<strong>SessionIdTime</strong>结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="8678c-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="8678c-150">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="8678c-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8678c-151"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="8678c-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8678c-152">datetime</span><span class="sxs-lookup"><span data-stu-id="8678c-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8678c-153">此用户加入此会议服务器的时间。</span><span class="sxs-lookup"><span data-stu-id="8678c-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8678c-154"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="8678c-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="8678c-155">datetime</span><span class="sxs-lookup"><span data-stu-id="8678c-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="8678c-156">此用户离开此会议服务器的时间。</span><span class="sxs-lookup"><span data-stu-id="8678c-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8678c-157"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="8678c-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="8678c-158">int</span><span class="sxs-lookup"><span data-stu-id="8678c-158">int</span></span></p></td>
<td><p><span data-ttu-id="8678c-159">外表</span><span class="sxs-lookup"><span data-stu-id="8678c-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="8678c-160">用于指定会议中客户端软件使用的版本号的标识符。</span><span class="sxs-lookup"><span data-stu-id="8678c-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="8678c-161">有关详细信息，请参阅<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a>。</span><span class="sxs-lookup"><span data-stu-id="8678c-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="8678c-162">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="8678c-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

