---
title: Lync Server 2013：FocusJoinsAndLeaves 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: FocusJoinsAndLeaves table
ms:assetid: e6f0212c-67e9-4061-8720-d0296e855991
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399026(v=OCS.15)
ms:contentKeyID: 48185690
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9ead6fc2ce79f7ab1206476ee420bd2ba5a7711f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-table-in-lync-server-2013"></a><span data-ttu-id="42cbe-102">Lync Server 2013 中的 FocusJoinsAndLeaves 表</span><span class="sxs-lookup"><span data-stu-id="42cbe-102">FocusJoinsAndLeaves table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="42cbe-103">_**主题上次修改时间:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="42cbe-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="42cbe-104">此表中的每条记录包含有关一个用户的加入的 CDR 信息, 并为一个会议留下信息。</span><span class="sxs-lookup"><span data-stu-id="42cbe-104">Each record in this table contains the CDR information about one user’s join and leave information for one conference.</span></span> <span data-ttu-id="42cbe-105">每次用户加入和离开会议时, 每个会议都将在此表中由一条记录表示。</span><span class="sxs-lookup"><span data-stu-id="42cbe-105">Each conference is represented in this table by one record for each time a user joins and leaves the conference.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="42cbe-106">列</span><span class="sxs-lookup"><span data-stu-id="42cbe-106">Column</span></span></th>
<th><span data-ttu-id="42cbe-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="42cbe-107">Data Type</span></span></th>
<th><span data-ttu-id="42cbe-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="42cbe-108">Key/Index</span></span></th>
<th><span data-ttu-id="42cbe-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="42cbe-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="42cbe-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="42cbe-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="42cbe-111">datetime</span><span class="sxs-lookup"><span data-stu-id="42cbe-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="42cbe-112">主、外部</span><span class="sxs-lookup"><span data-stu-id="42cbe-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="42cbe-113">会议实例的时间。</span><span class="sxs-lookup"><span data-stu-id="42cbe-113">Time of conference instance.</span></span> <span data-ttu-id="42cbe-114">与<strong>SessionIdSeq</strong>结合使用以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="42cbe-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="42cbe-115">有关详细信息, 请参阅<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="42cbe-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42cbe-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="42cbe-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="42cbe-117">int</span><span class="sxs-lookup"><span data-stu-id="42cbe-117">int</span></span></p></td>
<td><p><span data-ttu-id="42cbe-118">主、外部</span><span class="sxs-lookup"><span data-stu-id="42cbe-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="42cbe-119">标识会议实例的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="42cbe-119">ID number to identify the conference instance.</span></span> <span data-ttu-id="42cbe-120">与<strong>SessionIdTime</strong>结合使用以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="42cbe-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference instance.</span></span> <span data-ttu-id="42cbe-121">有关详细信息, 请参阅<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="42cbe-121">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42cbe-122"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="42cbe-122"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="42cbe-123">datetime</span><span class="sxs-lookup"><span data-stu-id="42cbe-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="42cbe-124">主、外部</span><span class="sxs-lookup"><span data-stu-id="42cbe-124">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="42cbe-125">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="42cbe-125">Time of session request.</span></span> <span data-ttu-id="42cbe-126">与<strong>SessionIdSeq</strong>结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="42cbe-126">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="42cbe-127">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="42cbe-127">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42cbe-128"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="42cbe-128"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="42cbe-129">int</span><span class="sxs-lookup"><span data-stu-id="42cbe-129">int</span></span></p></td>
<td><p><span data-ttu-id="42cbe-130">主、外部</span><span class="sxs-lookup"><span data-stu-id="42cbe-130">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="42cbe-131">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="42cbe-131">ID number to identify the session.</span></span> <span data-ttu-id="42cbe-132">与<strong>SessionIdTime</strong>结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="42cbe-132">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="42cbe-133">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="42cbe-133">see the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42cbe-134"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="42cbe-134"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="42cbe-135">int</span><span class="sxs-lookup"><span data-stu-id="42cbe-135">int</span></span></p></td>
<td><p><span data-ttu-id="42cbe-136">外表</span><span class="sxs-lookup"><span data-stu-id="42cbe-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42cbe-137">标识此用户的唯一号码, 从<a href="lync-server-2013-users-table.md">Lync Server 2013 的 "用户" 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="42cbe-137">Unique number identifying this user, referenced from the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42cbe-138"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="42cbe-138"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="42cbe-139">int</span><span class="sxs-lookup"><span data-stu-id="42cbe-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42cbe-140">如果用户同时在多台计算机或设备上登录, 则<strong>UserInstance</strong>用于唯一标识用户/设备组合。</span><span class="sxs-lookup"><span data-stu-id="42cbe-140">If a user is logged on at multiple computers or devices at the same time, <strong>UserInstance</strong> is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42cbe-141"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="42cbe-141"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="42cbe-142">bit</span><span class="sxs-lookup"><span data-stu-id="42cbe-142">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="42cbe-143">用户是否已从内部登录。</span><span class="sxs-lookup"><span data-stu-id="42cbe-143">Whether the user logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42cbe-144"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="42cbe-144"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="42cbe-145">int</span><span class="sxs-lookup"><span data-stu-id="42cbe-145">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="42cbe-146">此用户在会议中的角色, 如 "演示者" 或 "与会者"。</span><span class="sxs-lookup"><span data-stu-id="42cbe-146">This user’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42cbe-147"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="42cbe-147"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="42cbe-148">datetime</span><span class="sxs-lookup"><span data-stu-id="42cbe-148">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="42cbe-149">此用户加入会议的时间。</span><span class="sxs-lookup"><span data-stu-id="42cbe-149">The time this user joins the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42cbe-150"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="42cbe-150"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="42cbe-151">datetime</span><span class="sxs-lookup"><span data-stu-id="42cbe-151">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="42cbe-152">此用户离开会议的时间。</span><span class="sxs-lookup"><span data-stu-id="42cbe-152">The time this user leaves the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="42cbe-153"><strong>ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="42cbe-153"><strong>ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="42cbe-154">int</span><span class="sxs-lookup"><span data-stu-id="42cbe-154">int</span></span></p></td>
<td><p><span data-ttu-id="42cbe-155">外表</span><span class="sxs-lookup"><span data-stu-id="42cbe-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="42cbe-156">用户的客户端软件版本,<a href="lync-server-2013-clientversions-table.md">在 Lync Server 2013 中引用 ClientVersions 表</a>。</span><span class="sxs-lookup"><span data-stu-id="42cbe-156">Version of the user’s client software, referenced to the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="42cbe-157"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="42cbe-157"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="42cbe-158">标识符</span><span class="sxs-lookup"><span data-stu-id="42cbe-158">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="42cbe-159">会议中使用的终结点的全局唯一标识符 (GUID)。</span><span class="sxs-lookup"><span data-stu-id="42cbe-159">Globally unique identifier (GUID) of the endpoint used in the conference.</span></span></p>
<p><span data-ttu-id="42cbe-160">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="42cbe-160">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

