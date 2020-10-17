---
title: Lync Server 2013： McuJoinsAndLeaves 表
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
ms.openlocfilehash: f4aa5fb14ff16d13b1cdff72f15c648f9e353922
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524729"
---
# <a name="mcujoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="1669a-102">Lync Server 2013 中的 McuJoinsAndLeaves 表</span><span class="sxs-lookup"><span data-stu-id="1669a-102">McuJoinsAndLeaves table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1669a-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1669a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1669a-104">此表中的每条记录都包含有关用户加入或离开和会议服务器的一个组合的呼叫详细信息。</span><span class="sxs-lookup"><span data-stu-id="1669a-104">Each record in this table contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="1669a-105">例如，如果用户加入包含 web 会议和音频/视频元素的会议，则会为该用户的 web 会议加入创建一条记录，并为用户的音频/视频会议加入创建另一条记录。</span><span class="sxs-lookup"><span data-stu-id="1669a-105">For example, if a user joins a conference that includes web conferencing and audio/video elements, one record would be created for that user’s web conferencing join, and another record would be created for the user’s audio/video conferencing join.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1669a-106">列</span><span class="sxs-lookup"><span data-stu-id="1669a-106">Column</span></span></th>
<th><span data-ttu-id="1669a-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="1669a-107">Data Type</span></span></th>
<th><span data-ttu-id="1669a-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="1669a-108">Key/Index</span></span></th>
<th><span data-ttu-id="1669a-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="1669a-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1669a-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="1669a-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1669a-111">datetime</span><span class="sxs-lookup"><span data-stu-id="1669a-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="1669a-112">主、外</span><span class="sxs-lookup"><span data-stu-id="1669a-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1669a-113">会议实例的时间。</span><span class="sxs-lookup"><span data-stu-id="1669a-113">Time of conference instance.</span></span> <span data-ttu-id="1669a-114">与 <strong>SessionIdSeq</strong> 结合使用，以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="1669a-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="1669a-115">有关详细信息，请参阅 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="1669a-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1669a-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1669a-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1669a-117">int</span><span class="sxs-lookup"><span data-stu-id="1669a-117">int</span></span></p></td>
<td><p><span data-ttu-id="1669a-118">主、外</span><span class="sxs-lookup"><span data-stu-id="1669a-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1669a-119">用于标识会议实例的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="1669a-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="1669a-120">与 <strong>SessionIdTime</strong> 结合使用，以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="1669a-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="1669a-121">有关详细信息，请参阅 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="1669a-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1669a-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="1669a-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="1669a-123">int</span><span class="sxs-lookup"><span data-stu-id="1669a-123">int</span></span></p></td>
<td><p><span data-ttu-id="1669a-124">主、外</span><span class="sxs-lookup"><span data-stu-id="1669a-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1669a-125">用于标识此用户的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="1669a-125">Unique number identifying this user.</span></span> <span data-ttu-id="1669a-126">有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="1669a-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1669a-127"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="1669a-127"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="1669a-128">int</span><span class="sxs-lookup"><span data-stu-id="1669a-128">int</span></span></p></td>
<td><p><span data-ttu-id="1669a-129">主</span><span class="sxs-lookup"><span data-stu-id="1669a-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="1669a-130">如果一次用户在多台计算机或设备上登录，则 McuUserInstance 将唯一标识该用户/设备组合。</span><span class="sxs-lookup"><span data-stu-id="1669a-130">If a user is logged on at multiple computers or devices at once, McuUserInstance uniquely identifies the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1669a-131"><strong>IsFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="1669a-131"><strong>IsFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="1669a-132">位</span><span class="sxs-lookup"><span data-stu-id="1669a-132">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1669a-133">用户是否从 PSTN 进行联接。</span><span class="sxs-lookup"><span data-stu-id="1669a-133">Whether the user is joining from a PSTN or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1669a-134"><strong>McuId</strong></span><span class="sxs-lookup"><span data-stu-id="1669a-134"><strong>McuId</strong></span></span></p></td>
<td><p><span data-ttu-id="1669a-135">int</span><span class="sxs-lookup"><span data-stu-id="1669a-135">int</span></span></p></td>
<td><p><span data-ttu-id="1669a-136">主、外</span><span class="sxs-lookup"><span data-stu-id="1669a-136">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="1669a-137">标识此会议服务器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="1669a-137">Unique number identifying this conferencing server.</span></span> <span data-ttu-id="1669a-138">有关详细信息，请参阅 <a href="lync-server-2013-mcus-table.md">Lync Server 2013 中的 mcu 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="1669a-138">See the <a href="lync-server-2013-mcus-table.md">Mcus table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1669a-139"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="1669a-139"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1669a-140">datetime</span><span class="sxs-lookup"><span data-stu-id="1669a-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="1669a-141">对外</span><span class="sxs-lookup"><span data-stu-id="1669a-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1669a-142">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="1669a-142">Time of session request.</span></span> <span data-ttu-id="1669a-143">与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="1669a-143">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="1669a-144">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="1669a-144">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1669a-145"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1669a-145"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1669a-146">int</span><span class="sxs-lookup"><span data-stu-id="1669a-146">int</span></span></p></td>
<td><p><span data-ttu-id="1669a-147">对外</span><span class="sxs-lookup"><span data-stu-id="1669a-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1669a-148">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="1669a-148">ID number to identify the session.</span></span> <span data-ttu-id="1669a-149">与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="1669a-149">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="1669a-150">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="1669a-150">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1669a-151"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="1669a-151"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1669a-152">datetime</span><span class="sxs-lookup"><span data-stu-id="1669a-152">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1669a-153">此用户加入此会议服务器的时间。</span><span class="sxs-lookup"><span data-stu-id="1669a-153">The time this user joins this conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1669a-154"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="1669a-154"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1669a-155">datetime</span><span class="sxs-lookup"><span data-stu-id="1669a-155">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1669a-156">此用户离开此会议服务器的时间。</span><span class="sxs-lookup"><span data-stu-id="1669a-156">The time this user leaves this conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1669a-157"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="1669a-157"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="1669a-158">int</span><span class="sxs-lookup"><span data-stu-id="1669a-158">int</span></span></p></td>
<td><p><span data-ttu-id="1669a-159">对外</span><span class="sxs-lookup"><span data-stu-id="1669a-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1669a-160">指定在会议中使用的客户端软件版本号的标识符。</span><span class="sxs-lookup"><span data-stu-id="1669a-160">Identifier that specifies the version number of the client software use in the conference.</span></span> <span data-ttu-id="1669a-161">有关详细信息，请参阅 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="1669a-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="1669a-162">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1669a-162">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

