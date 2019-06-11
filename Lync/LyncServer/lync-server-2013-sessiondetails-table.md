---
title: Lync Server 2013：SessionDetails 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: faebef9ad03370c2fa969d3b119f13b88d1d3173
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822109"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="5e89c-102">Lync Server 2013 中的 SessionDetails 表</span><span class="sxs-lookup"><span data-stu-id="5e89c-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e89c-103">_**主题上次修改时间:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="5e89c-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="5e89c-104">每条记录表示一个对等会话, 可以是 VoIP-VoIP 电话呼叫、两方 IM 会话或其他类型的会话。</span><span class="sxs-lookup"><span data-stu-id="5e89c-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="5e89c-105">你可以使用[Lync Server 2013 中的 media 表](lync-server-2013-media-table.md)执行表联接, 以查找此会话中涉及的每个媒体的详细信息。</span><span class="sxs-lookup"><span data-stu-id="5e89c-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="5e89c-106">请注意, IsUser1IntegratedWithDeskPhone 和 IsUser2IntegratedWithDeskPhone 字段已从 Microsoft Lync Server 2013 中使用的 SessionDetails 表中删除。</span><span class="sxs-lookup"><span data-stu-id="5e89c-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5e89c-107">列</span><span class="sxs-lookup"><span data-stu-id="5e89c-107">Column</span></span></th>
<th><span data-ttu-id="5e89c-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="5e89c-108">Data Type</span></span></th>
<th><span data-ttu-id="5e89c-109">键/索引</span><span class="sxs-lookup"><span data-stu-id="5e89c-109">Key/Index</span></span></th>
<th><span data-ttu-id="5e89c-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="5e89c-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e89c-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-112">datetime</span><span class="sxs-lookup"><span data-stu-id="5e89c-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="5e89c-113">主、外部</span><span class="sxs-lookup"><span data-stu-id="5e89c-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e89c-114">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="5e89c-114">Time of session request.</span></span> <span data-ttu-id="5e89c-115">与<strong>SessionIdSeq</strong>结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="5e89c-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="5e89c-116">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="5e89c-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e89c-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-118">int</span><span class="sxs-lookup"><span data-stu-id="5e89c-118">int</span></span></p></td>
<td><p><span data-ttu-id="5e89c-119">主、外部</span><span class="sxs-lookup"><span data-stu-id="5e89c-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e89c-120">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="5e89c-120">ID number to identify the session.</span></span> <span data-ttu-id="5e89c-121">与<strong>SessionIdTime</strong>结合使用以唯一标识会话。 \* 有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="5e89c-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e89c-122"><strong>True&correlationid</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-123">标识符</span><span class="sxs-lookup"><span data-stu-id="5e89c-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e89c-124">用于关联多个会话的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5e89c-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e89c-125"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-126">datetime</span><span class="sxs-lookup"><span data-stu-id="5e89c-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="5e89c-127">外表</span><span class="sxs-lookup"><span data-stu-id="5e89c-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e89c-128">标识由当前会话替换的对话框的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="5e89c-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="5e89c-129">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="5e89c-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e89c-130"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-131">int</span><span class="sxs-lookup"><span data-stu-id="5e89c-131">int</span></span></p></td>
<td><p><span data-ttu-id="5e89c-132">外表</span><span class="sxs-lookup"><span data-stu-id="5e89c-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e89c-133">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="5e89c-133">ID number to identify the session.</span></span> <span data-ttu-id="5e89c-134">与<strong>ReplacesDialogIdTime</strong>结合使用以唯一标识此会话替换的会话。</span><span class="sxs-lookup"><span data-stu-id="5e89c-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="5e89c-135">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="5e89c-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e89c-136"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-137">int</span><span class="sxs-lookup"><span data-stu-id="5e89c-137">int</span></span></p></td>
<td><p><span data-ttu-id="5e89c-138">外表</span><span class="sxs-lookup"><span data-stu-id="5e89c-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e89c-139">会话中一个用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="5e89c-139">ID of one user in the session.</span></span> <span data-ttu-id="5e89c-140">有关详细信息, 请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 "用户" 表。</span><span class="sxs-lookup"><span data-stu-id="5e89c-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e89c-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-142">int</span><span class="sxs-lookup"><span data-stu-id="5e89c-142">int</span></span></p></td>
<td><p><span data-ttu-id="5e89c-143">外表</span><span class="sxs-lookup"><span data-stu-id="5e89c-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e89c-144">会话中其他用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="5e89c-144">ID of the other user in the session.</span></span> <span data-ttu-id="5e89c-145">有关详细信息, 请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 "用户" 表。</span><span class="sxs-lookup"><span data-stu-id="5e89c-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e89c-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-147">标识符</span><span class="sxs-lookup"><span data-stu-id="5e89c-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e89c-148">标识会话中第一个用户使用的终结点的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5e89c-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="5e89c-149">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="5e89c-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e89c-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-151">标识符</span><span class="sxs-lookup"><span data-stu-id="5e89c-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e89c-152">标识会话中第二用户使用的终结点的 GUID。</span><span class="sxs-lookup"><span data-stu-id="5e89c-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="5e89c-153">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="5e89c-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e89c-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-155">int</span><span class="sxs-lookup"><span data-stu-id="5e89c-155">int</span></span></p></td>
<td><p><span data-ttu-id="5e89c-156">外表</span><span class="sxs-lookup"><span data-stu-id="5e89c-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e89c-157">SIP 请求中的原始用户 URI。</span><span class="sxs-lookup"><span data-stu-id="5e89c-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="5e89c-158">有关详细信息, 请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 "用户" 表。</span><span class="sxs-lookup"><span data-stu-id="5e89c-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e89c-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-160">int</span><span class="sxs-lookup"><span data-stu-id="5e89c-160">int</span></span></p></td>
<td><p><span data-ttu-id="5e89c-161">外表</span><span class="sxs-lookup"><span data-stu-id="5e89c-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e89c-162">启动会话的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="5e89c-162">ID of the user who started the session.</span></span> <span data-ttu-id="5e89c-163">有关详细信息, 请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 "用户" 表。</span><span class="sxs-lookup"><span data-stu-id="5e89c-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e89c-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-165">int</span><span class="sxs-lookup"><span data-stu-id="5e89c-165">int</span></span></p></td>
<td><p><span data-ttu-id="5e89c-166">外表</span><span class="sxs-lookup"><span data-stu-id="5e89c-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e89c-167">指明呼叫者代表的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="5e89c-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="5e89c-168">有关详细信息, 请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 "用户" 表。</span><span class="sxs-lookup"><span data-stu-id="5e89c-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e89c-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-170">int</span><span class="sxs-lookup"><span data-stu-id="5e89c-170">int</span></span></p></td>
<td><p><span data-ttu-id="5e89c-171">外表</span><span class="sxs-lookup"><span data-stu-id="5e89c-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e89c-172">按呼叫者引用的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="5e89c-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="5e89c-173">有关详细信息, 请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 "用户" 表。</span><span class="sxs-lookup"><span data-stu-id="5e89c-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e89c-174"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-175">int</span><span class="sxs-lookup"><span data-stu-id="5e89c-175">int</span></span></p></td>
<td><p><span data-ttu-id="5e89c-176">外表</span><span class="sxs-lookup"><span data-stu-id="5e89c-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e89c-177">用于此会话的前端服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="5e89c-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="5e89c-178">有关详细信息, 请参阅<a href="lync-server-2013-servers-table.md">Lync Server 2013 中</a>的 "服务器" 表。</span><span class="sxs-lookup"><span data-stu-id="5e89c-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e89c-179"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-180">int</span><span class="sxs-lookup"><span data-stu-id="5e89c-180">int</span></span></p></td>
<td><p><span data-ttu-id="5e89c-181">外表</span><span class="sxs-lookup"><span data-stu-id="5e89c-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e89c-182">捕获会话的池的 ID。</span><span class="sxs-lookup"><span data-stu-id="5e89c-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="5e89c-183">有关详细信息, 请参阅<a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表</a>。</span><span class="sxs-lookup"><span data-stu-id="5e89c-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e89c-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-185">int</span><span class="sxs-lookup"><span data-stu-id="5e89c-185">int</span></span></p></td>
<td><p><span data-ttu-id="5e89c-186">外表</span><span class="sxs-lookup"><span data-stu-id="5e89c-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e89c-187">会话中使用的内容类型。</span><span class="sxs-lookup"><span data-stu-id="5e89c-187">Content type used in the session.</span></span> <span data-ttu-id="5e89c-188">有关详细信息, 请参阅<a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="5e89c-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e89c-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-190">int</span><span class="sxs-lookup"><span data-stu-id="5e89c-190">int</span></span></p></td>
<td><p><span data-ttu-id="5e89c-191">外表</span><span class="sxs-lookup"><span data-stu-id="5e89c-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e89c-192">User1 使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="5e89c-192">Client version used by User1.</span></span> <span data-ttu-id="5e89c-193">有关详细信息, 请参阅<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a>。</span><span class="sxs-lookup"><span data-stu-id="5e89c-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e89c-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-195">int</span><span class="sxs-lookup"><span data-stu-id="5e89c-195">int</span></span></p></td>
<td><p><span data-ttu-id="5e89c-196">外表</span><span class="sxs-lookup"><span data-stu-id="5e89c-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e89c-197">用户2使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="5e89c-197">Client version used by User2.</span></span> <span data-ttu-id="5e89c-198">有关详细信息, 请参阅<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a>。</span><span class="sxs-lookup"><span data-stu-id="5e89c-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e89c-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-200">int</span><span class="sxs-lookup"><span data-stu-id="5e89c-200">int</span></span></p></td>
<td><p><span data-ttu-id="5e89c-201">外表</span><span class="sxs-lookup"><span data-stu-id="5e89c-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e89c-202">由 User1 使用的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="5e89c-202">Edge Server used by User1.</span></span> <span data-ttu-id="5e89c-203">有关详细信息, 请参阅<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a>。</span><span class="sxs-lookup"><span data-stu-id="5e89c-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e89c-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-205">int</span><span class="sxs-lookup"><span data-stu-id="5e89c-205">int</span></span></p></td>
<td><p><span data-ttu-id="5e89c-206">外表</span><span class="sxs-lookup"><span data-stu-id="5e89c-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e89c-207">由服务者使用的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="5e89c-207">Edge Server used by User2.</span></span> <span data-ttu-id="5e89c-208">有关详细信息, 请参阅<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a>。</span><span class="sxs-lookup"><span data-stu-id="5e89c-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e89c-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-210">bit</span><span class="sxs-lookup"><span data-stu-id="5e89c-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e89c-211">User1 是否从内部登录。</span><span class="sxs-lookup"><span data-stu-id="5e89c-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e89c-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-213">bit</span><span class="sxs-lookup"><span data-stu-id="5e89c-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e89c-214">2/2 是否已从内部登录。</span><span class="sxs-lookup"><span data-stu-id="5e89c-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e89c-215"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-216">datetime</span><span class="sxs-lookup"><span data-stu-id="5e89c-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e89c-217">第一次邀请请求的时间。</span><span class="sxs-lookup"><span data-stu-id="5e89c-217">The time of the first INVITE request.</span></span> <span data-ttu-id="5e89c-218">此字段通常由会话中的初始邀请消息所生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="5e89c-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="5e89c-219">如果没有邀请消息, 则该字段将填充第一个相关 SIP 邮件的日期和时间 (再见、取消、消息或信息)。</span><span class="sxs-lookup"><span data-stu-id="5e89c-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="5e89c-220">此字段通常由会话中的初始邀请消息所生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="5e89c-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="5e89c-221">如果没有邀请消息, 则该字段将填充第一个相关 SIP 邮件的日期和时间 (再见、取消、消息或信息)。</span><span class="sxs-lookup"><span data-stu-id="5e89c-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e89c-222"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-223">datetime</span><span class="sxs-lookup"><span data-stu-id="5e89c-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e89c-224">对第一个邀请消息的答复时间。</span><span class="sxs-lookup"><span data-stu-id="5e89c-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="5e89c-225">此字段通常由会话中的初始邀请消息所生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="5e89c-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="5e89c-226">如果没有邀请消息, 则该字段将填充第一个相关 SIP 邮件的日期和时间 (再见、取消、消息或信息)。</span><span class="sxs-lookup"><span data-stu-id="5e89c-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e89c-227"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-228">int</span><span class="sxs-lookup"><span data-stu-id="5e89c-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e89c-229">会议邀请的 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="5e89c-229">SIP response code to the session invitation.</span></span> <span data-ttu-id="5e89c-230">此字段通常由会话中的初始邀请消息所生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="5e89c-230">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="5e89c-231">如果没有邀请消息, 则该字段将填充第一个相关 SIP 邮件的日期和时间 (再见、取消、消息或信息)。</span><span class="sxs-lookup"><span data-stu-id="5e89c-231">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e89c-232"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-233">int</span><span class="sxs-lookup"><span data-stu-id="5e89c-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e89c-234">从 SIP 标题捕获的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="5e89c-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e89c-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-236">int</span><span class="sxs-lookup"><span data-stu-id="5e89c-236">int</span></span></p></td>
<td><p><span data-ttu-id="5e89c-237">外表</span><span class="sxs-lookup"><span data-stu-id="5e89c-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="5e89c-238">通话优先级。</span><span class="sxs-lookup"><span data-stu-id="5e89c-238">Call priority.</span></span> <span data-ttu-id="5e89c-239">有关详细信息, 请参阅<a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 中的 CallPriorities 表</a>。</span><span class="sxs-lookup"><span data-stu-id="5e89c-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e89c-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-241">int</span><span class="sxs-lookup"><span data-stu-id="5e89c-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e89c-242">在会话期间由 User1 发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="5e89c-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e89c-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-244">int</span><span class="sxs-lookup"><span data-stu-id="5e89c-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e89c-245">会话期间由操作者发送的邮件数。</span><span class="sxs-lookup"><span data-stu-id="5e89c-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e89c-246"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-247">datetime</span><span class="sxs-lookup"><span data-stu-id="5e89c-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e89c-248">会话结束时的时间。</span><span class="sxs-lookup"><span data-stu-id="5e89c-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e89c-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-250">int</span><span class="sxs-lookup"><span data-stu-id="5e89c-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e89c-251">指示此会话的媒体类型的位集。</span><span class="sxs-lookup"><span data-stu-id="5e89c-251">A bit set that indicates the media type of this session.</span></span> <span data-ttu-id="5e89c-252">列出的是以下类型的定义:</span><span class="sxs-lookup"><span data-stu-id="5e89c-252">Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5e89c-253">即时消息</span><span class="sxs-lookup"><span data-stu-id="5e89c-253">IM</span></span></p></td>
<td><p><span data-ttu-id="5e89c-254">1</span><span class="sxs-lookup"><span data-stu-id="5e89c-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e89c-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="5e89c-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="5e89c-256">2</span><span class="sxs-lookup"><span data-stu-id="5e89c-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e89c-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="5e89c-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="5e89c-258">4</span><span class="sxs-lookup"><span data-stu-id="5e89c-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e89c-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="5e89c-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="5e89c-260">个</span><span class="sxs-lookup"><span data-stu-id="5e89c-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e89c-261">视听</span><span class="sxs-lookup"><span data-stu-id="5e89c-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="5e89c-262">utf-16</span><span class="sxs-lookup"><span data-stu-id="5e89c-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e89c-263">VIDEO</span><span class="sxs-lookup"><span data-stu-id="5e89c-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="5e89c-264">32</span><span class="sxs-lookup"><span data-stu-id="5e89c-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e89c-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="5e89c-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="5e89c-266">64</span><span class="sxs-lookup"><span data-stu-id="5e89c-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e89c-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-268">smallint</span><span class="sxs-lookup"><span data-stu-id="5e89c-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e89c-269">指示 User1 属性的位集。</span><span class="sxs-lookup"><span data-stu-id="5e89c-269">A bit set that indicates the User1 attributes.</span></span> <span data-ttu-id="5e89c-270">列出了以下属性定义:</span><span class="sxs-lookup"><span data-stu-id="5e89c-270">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="5e89c-271">0x01-与桌面电话集成</span><span class="sxs-lookup"><span data-stu-id="5e89c-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e89c-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-273">smallint</span><span class="sxs-lookup"><span data-stu-id="5e89c-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e89c-274">指示 "工作 2" 属性的位集。</span><span class="sxs-lookup"><span data-stu-id="5e89c-274">A bit set that indicates the User2 attributes.</span></span> <span data-ttu-id="5e89c-275">列出了以下属性定义:</span><span class="sxs-lookup"><span data-stu-id="5e89c-275">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="5e89c-276">0x01-与桌面电话集成</span><span class="sxs-lookup"><span data-stu-id="5e89c-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5e89c-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-278">smallint</span><span class="sxs-lookup"><span data-stu-id="5e89c-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e89c-279">指示通话属性的位集。</span><span class="sxs-lookup"><span data-stu-id="5e89c-279">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="5e89c-280">列出了以下属性定义:</span><span class="sxs-lookup"><span data-stu-id="5e89c-280">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="5e89c-281">0x01-重试会话</span><span class="sxs-lookup"><span data-stu-id="5e89c-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="5e89c-282">0x02-代表响应组的代理发出的呼叫</span><span class="sxs-lookup"><span data-stu-id="5e89c-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5e89c-283"><strong>过</strong></span><span class="sxs-lookup"><span data-stu-id="5e89c-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="5e89c-284">bit</span><span class="sxs-lookup"><span data-stu-id="5e89c-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5e89c-285">供监视服务内部使用。</span><span class="sxs-lookup"><span data-stu-id="5e89c-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="5e89c-286">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="5e89c-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="5e89c-287">\*对于大多数会话, SessionIdSeq 将具有值1。</span><span class="sxs-lookup"><span data-stu-id="5e89c-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="5e89c-288">如果多个会话的开始时间完全相同, 则一个会话的 SessionIdSeq 将为 1, 而另一个会话将为 2, 依此类推。</span><span class="sxs-lookup"><span data-stu-id="5e89c-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

