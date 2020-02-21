---
title: Lync Server 2013： SessionDetails 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails table
ms:assetid: 783d2508-e31f-4b54-be0c-63aa5ec21c04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398589(v=OCS.15)
ms:contentKeyID: 48184559
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bfdf5552f150b23c50e8ad6867e90f96a6b586fb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42182305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="c6d8f-102">Lync Server 2013 中的 SessionDetails 表</span><span class="sxs-lookup"><span data-stu-id="c6d8f-102">SessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6d8f-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="c6d8f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="c6d8f-104">每条记录表示一个点对点会话，它可以是 VoIP-VoIP 电话呼叫、双方 IM 会话或其他类型的会话。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-104">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="c6d8f-105">您可以使用[Lync Server 2013 中的 media 表](lync-server-2013-media-table.md)执行表联接，以查找此会话中涉及的每个媒体的详细信息。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-105">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="c6d8f-106">请注意，IsUser1IntegratedWithDeskPhone 和 IsUser2IntegratedWithDeskPhone 字段已从 Microsoft Lync Server 2013 中使用的 SessionDetails 表中删除。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-106">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c6d8f-107">列</span><span class="sxs-lookup"><span data-stu-id="c6d8f-107">Column</span></span></th>
<th><span data-ttu-id="c6d8f-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="c6d8f-108">Data Type</span></span></th>
<th><span data-ttu-id="c6d8f-109">键/索引</span><span class="sxs-lookup"><span data-stu-id="c6d8f-109">Key/Index</span></span></th>
<th><span data-ttu-id="c6d8f-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="c6d8f-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6d8f-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="c6d8f-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-113">主、外</span><span class="sxs-lookup"><span data-stu-id="c6d8f-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-114">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-114">Time of session request.</span></span> <span data-ttu-id="c6d8f-115">与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-115">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="c6d8f-116">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-116">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d8f-117"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-117"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-118">int</span><span class="sxs-lookup"><span data-stu-id="c6d8f-118">int</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-119">主、外</span><span class="sxs-lookup"><span data-stu-id="c6d8f-119">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-120">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-120">ID number to identify the session.</span></span> <span data-ttu-id="c6d8f-121">与<strong>SessionIdTime</strong>结合使用以唯一标识会话。 \* 有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-121">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d8f-122"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-122"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-123">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="c6d8f-123">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6d8f-124">用于关联多个会话的 GUID。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-124">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d8f-125"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-125"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-126">datetime</span><span class="sxs-lookup"><span data-stu-id="c6d8f-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-127">对外</span><span class="sxs-lookup"><span data-stu-id="c6d8f-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-128">用于标识由当前会话取代的对话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-128">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="c6d8f-129">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-129">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d8f-130"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-130"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-131">int</span><span class="sxs-lookup"><span data-stu-id="c6d8f-131">int</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-132">对外</span><span class="sxs-lookup"><span data-stu-id="c6d8f-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-133">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-133">ID number to identify the session.</span></span> <span data-ttu-id="c6d8f-134">与 <strong>ReplacesDialogIdTime</strong> 结合使用来唯一地标识由此会话取代的会话。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-134">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="c6d8f-135">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-135">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d8f-136"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-136"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-137">int</span><span class="sxs-lookup"><span data-stu-id="c6d8f-137">int</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-138">对外</span><span class="sxs-lookup"><span data-stu-id="c6d8f-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-139">会话中的一个用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-139">ID of one user in the session.</span></span> <span data-ttu-id="c6d8f-140">有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-140">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d8f-141"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-141"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-142">int</span><span class="sxs-lookup"><span data-stu-id="c6d8f-142">int</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-143">对外</span><span class="sxs-lookup"><span data-stu-id="c6d8f-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-144">会话中另一个用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-144">ID of the other user in the session.</span></span> <span data-ttu-id="c6d8f-145">有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-145">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d8f-146"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-146"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-147">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="c6d8f-147">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6d8f-148">标识会话中的第一个用户所使用的终结点的 GUID。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-148">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="c6d8f-149">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-149">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d8f-150"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-150"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-151">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="c6d8f-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6d8f-152">标识会话中的第二个用户所使用的终结点的 GUID。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-152">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="c6d8f-153">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d8f-154"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-154"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-155">int</span><span class="sxs-lookup"><span data-stu-id="c6d8f-155">int</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-156">对外</span><span class="sxs-lookup"><span data-stu-id="c6d8f-156">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-157">SIP 请求中的原始目标用户 URI。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-157">The original To user URI in the SIP request.</span></span> <span data-ttu-id="c6d8f-158">有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-158">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d8f-159"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-159"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-160">int</span><span class="sxs-lookup"><span data-stu-id="c6d8f-160">int</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-161">对外</span><span class="sxs-lookup"><span data-stu-id="c6d8f-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-162">启动会话的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-162">ID of the user who started the session.</span></span> <span data-ttu-id="c6d8f-163">有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-163">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d8f-164"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-164"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-165">int</span><span class="sxs-lookup"><span data-stu-id="c6d8f-165">int</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-166">对外</span><span class="sxs-lookup"><span data-stu-id="c6d8f-166">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-167">指示呼叫者所代表的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-167">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="c6d8f-168">有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-168">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d8f-169"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-169"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-170">int</span><span class="sxs-lookup"><span data-stu-id="c6d8f-170">int</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-171">对外</span><span class="sxs-lookup"><span data-stu-id="c6d8f-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-172">引用呼叫的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-172">ID of the user by who the call is referred.</span></span> <span data-ttu-id="c6d8f-173">有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-173">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d8f-174"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-174"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-175">int</span><span class="sxs-lookup"><span data-stu-id="c6d8f-175">int</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-176">对外</span><span class="sxs-lookup"><span data-stu-id="c6d8f-176">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-177">用于此会话的前端服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-177">ID of the front-end server used for this session.</span></span> <span data-ttu-id="c6d8f-178">有关详细信息，请参阅<a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 表</a>。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-178">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d8f-179"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-179"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-180">int</span><span class="sxs-lookup"><span data-stu-id="c6d8f-180">int</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-181">对外</span><span class="sxs-lookup"><span data-stu-id="c6d8f-181">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-182">在其中捕获会话的池的 ID。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-182">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="c6d8f-183">有关详细信息，请参阅<a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表</a>。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-183">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d8f-184"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-184"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-185">int</span><span class="sxs-lookup"><span data-stu-id="c6d8f-185">int</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-186">对外</span><span class="sxs-lookup"><span data-stu-id="c6d8f-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-187">会话中使用的内容类型。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-187">Content type used in the session.</span></span> <span data-ttu-id="c6d8f-188">有关详细信息，请参阅<a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-188">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d8f-189"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-189"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-190">int</span><span class="sxs-lookup"><span data-stu-id="c6d8f-190">int</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-191">对外</span><span class="sxs-lookup"><span data-stu-id="c6d8f-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-192">User1 使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-192">Client version used by User1.</span></span> <span data-ttu-id="c6d8f-193">有关详细信息，请参阅<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a>。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-193">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d8f-194"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-194"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-195">int</span><span class="sxs-lookup"><span data-stu-id="c6d8f-195">int</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-196">对外</span><span class="sxs-lookup"><span data-stu-id="c6d8f-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-197">User2 使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-197">Client version used by User2.</span></span> <span data-ttu-id="c6d8f-198">有关详细信息，请参阅<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a>。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-198">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d8f-199"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-199"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-200">int</span><span class="sxs-lookup"><span data-stu-id="c6d8f-200">int</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-201">对外</span><span class="sxs-lookup"><span data-stu-id="c6d8f-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-202">User1 使用的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-202">Edge Server used by User1.</span></span> <span data-ttu-id="c6d8f-203">有关详细信息，请参阅<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a>。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-203">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d8f-204"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-204"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-205">int</span><span class="sxs-lookup"><span data-stu-id="c6d8f-205">int</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-206">对外</span><span class="sxs-lookup"><span data-stu-id="c6d8f-206">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-207">User2 使用的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-207">Edge Server used by User2.</span></span> <span data-ttu-id="c6d8f-208">有关详细信息，请参阅<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a>。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-208">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d8f-209"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-209"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-210">位</span><span class="sxs-lookup"><span data-stu-id="c6d8f-210">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6d8f-211">User1 是否从内部登录。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-211">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d8f-212"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-212"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-213">位</span><span class="sxs-lookup"><span data-stu-id="c6d8f-213">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6d8f-214">User2 是否从内部登录。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-214">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d8f-215"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-215"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-216">datetime</span><span class="sxs-lookup"><span data-stu-id="c6d8f-216">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6d8f-217">第一个 INVITE 请求的时间。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-217">The time of the first INVITE request.</span></span> <span data-ttu-id="c6d8f-218">此字段通常用从会话中的初始 INVITE 消息生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-218">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="c6d8f-219">如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-219">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="c6d8f-220">此字段通常用从会话中的初始 INVITE 消息生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-220">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="c6d8f-221">如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-221">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d8f-222"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-222"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-223">datetime</span><span class="sxs-lookup"><span data-stu-id="c6d8f-223">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6d8f-224">第一个 INVITE 消息的响应时间。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-224">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="c6d8f-225">此字段通常用从会话中的初始 INVITE 消息生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-225">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="c6d8f-226">如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-226">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d8f-227"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-227"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-228">int</span><span class="sxs-lookup"><span data-stu-id="c6d8f-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6d8f-p121">会话邀请的 SIP 响应代码。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d8f-232"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-232"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-233">int</span><span class="sxs-lookup"><span data-stu-id="c6d8f-233">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6d8f-234">从 SIP 标头捕获的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-234">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d8f-235"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-235"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-236">int</span><span class="sxs-lookup"><span data-stu-id="c6d8f-236">int</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-237">对外</span><span class="sxs-lookup"><span data-stu-id="c6d8f-237">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-238">呼叫优先级。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-238">Call priority.</span></span> <span data-ttu-id="c6d8f-239">有关详细信息，请参阅<a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 中的 CallPriorities 表</a>。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-239">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d8f-240"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-240"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-241">int</span><span class="sxs-lookup"><span data-stu-id="c6d8f-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6d8f-242">User1 在会话期间发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-242">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d8f-243"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-243"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-244">int</span><span class="sxs-lookup"><span data-stu-id="c6d8f-244">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6d8f-245">User2 在会话期间发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-245">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d8f-246"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-246"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-247">datetime</span><span class="sxs-lookup"><span data-stu-id="c6d8f-247">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6d8f-248">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-248">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d8f-249"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-249"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-250">int</span><span class="sxs-lookup"><span data-stu-id="c6d8f-250">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6d8f-p123">指示此会话的媒体类型的位集。下面列出了类型的定义：</span><span class="sxs-lookup"><span data-stu-id="c6d8f-p123">A bit set that indicates the media type of this session. Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c6d8f-253">IM</span><span class="sxs-lookup"><span data-stu-id="c6d8f-253">IM</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-254">1</span><span class="sxs-lookup"><span data-stu-id="c6d8f-254">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d8f-255">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="c6d8f-255">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-256">双面</span><span class="sxs-lookup"><span data-stu-id="c6d8f-256">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d8f-257">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="c6d8f-257">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-258">4</span><span class="sxs-lookup"><span data-stu-id="c6d8f-258">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d8f-259">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="c6d8f-259">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-260">8 </span><span class="sxs-lookup"><span data-stu-id="c6d8f-260">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d8f-261">视频</span><span class="sxs-lookup"><span data-stu-id="c6d8f-261">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-262">16 </span><span class="sxs-lookup"><span data-stu-id="c6d8f-262">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d8f-263">显示</span><span class="sxs-lookup"><span data-stu-id="c6d8f-263">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-264">32</span><span class="sxs-lookup"><span data-stu-id="c6d8f-264">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d8f-265">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="c6d8f-265">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="c6d8f-266">64</span><span class="sxs-lookup"><span data-stu-id="c6d8f-266">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d8f-267"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-267"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-268">smallint</span><span class="sxs-lookup"><span data-stu-id="c6d8f-268">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6d8f-p124">指示 User1 属性的位集。列出了以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="c6d8f-p124">A bit set that indicates the User1 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6d8f-271">0x01 - 与桌面电话集成</span><span class="sxs-lookup"><span data-stu-id="c6d8f-271">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d8f-272"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-272"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-273">smallint</span><span class="sxs-lookup"><span data-stu-id="c6d8f-273">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6d8f-p125">指示 User2 属性的位集。列出了以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="c6d8f-p125">A bit set that indicates the User2 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6d8f-276">0x01 - 与桌面电话集成</span><span class="sxs-lookup"><span data-stu-id="c6d8f-276">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c6d8f-277"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-277"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-278">smallint</span><span class="sxs-lookup"><span data-stu-id="c6d8f-278">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6d8f-p126">指示呼叫属性的位集。列出了以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="c6d8f-p126">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="c6d8f-281">0x01 - 重试会话</span><span class="sxs-lookup"><span data-stu-id="c6d8f-281">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="c6d8f-282">0x02 - 代表响应组的代理进行的呼叫</span><span class="sxs-lookup"><span data-stu-id="c6d8f-282">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c6d8f-283"><strong>处理</strong></span><span class="sxs-lookup"><span data-stu-id="c6d8f-283"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="c6d8f-284">位</span><span class="sxs-lookup"><span data-stu-id="c6d8f-284">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c6d8f-285">供监控服务内部使用。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-285">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="c6d8f-286">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-286">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="c6d8f-287">\*对于大多数会话，SessionIdSeq 的值将为1。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-287">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="c6d8f-288">如果多个会话完全同时启动，则一个会话的 SessionIdSeq 将为 1，另一个会话的 SessionIdSeq 将为 2，依此类推。</span><span class="sxs-lookup"><span data-stu-id="c6d8f-288">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

