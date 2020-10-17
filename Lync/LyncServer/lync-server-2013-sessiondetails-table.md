---
title: Lync Server 2013： SessionDetails 表
description: Lync Server 2013： SessionDetails 表。
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
ms.openlocfilehash: fd927f784fb0f2a835c896824105fe8bb112c7a1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569928"
---
# <a name="sessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="61a34-103">Lync Server 2013 中的 SessionDetails 表</span><span class="sxs-lookup"><span data-stu-id="61a34-103">SessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61a34-104">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="61a34-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="61a34-105">每条记录表示一个点对点会话，它可以是 VoIP-VoIP 电话呼叫、双方 IM 会话或其他类型的会话。</span><span class="sxs-lookup"><span data-stu-id="61a34-105">Each record represents one peer-to-peer session, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="61a34-106">您可以使用 [Lync Server 2013 中的 media 表](lync-server-2013-media-table.md) 执行表联接，以查找此会话中涉及的每个媒体的详细信息。</span><span class="sxs-lookup"><span data-stu-id="61a34-106">You can perform a table join with the [Media table in Lync Server 2013](lync-server-2013-media-table.md) to find the details of each media involved in this session.</span></span>

<span data-ttu-id="61a34-107">请注意，IsUser1IntegratedWithDeskPhone 和 IsUser2IntegratedWithDeskPhone 字段已从 Microsoft Lync Server 2013 中使用的 SessionDetails 表中删除。</span><span class="sxs-lookup"><span data-stu-id="61a34-107">Note that the IsUser1IntegratedWithDeskPhone and the IsUser2IntegratedWithDeskPhone fields have been dropped from the SessionDetails table used in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61a34-108">列</span><span class="sxs-lookup"><span data-stu-id="61a34-108">Column</span></span></th>
<th><span data-ttu-id="61a34-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="61a34-109">Data Type</span></span></th>
<th><span data-ttu-id="61a34-110">键/索引</span><span class="sxs-lookup"><span data-stu-id="61a34-110">Key/Index</span></span></th>
<th><span data-ttu-id="61a34-111">详细信息</span><span class="sxs-lookup"><span data-stu-id="61a34-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61a34-112"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-112"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-113">datetime</span><span class="sxs-lookup"><span data-stu-id="61a34-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="61a34-114">主、外</span><span class="sxs-lookup"><span data-stu-id="61a34-114">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="61a34-115">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="61a34-115">Time of session request.</span></span> <span data-ttu-id="61a34-116">与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="61a34-116">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="61a34-117">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="61a34-117">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61a34-118"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-118"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-119">int</span><span class="sxs-lookup"><span data-stu-id="61a34-119">int</span></span></p></td>
<td><p><span data-ttu-id="61a34-120">主、外</span><span class="sxs-lookup"><span data-stu-id="61a34-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="61a34-121">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="61a34-121">ID number to identify the session.</span></span> <span data-ttu-id="61a34-122">与 <strong>SessionIdTime</strong> 结合使用以唯一标识会话。 \* 有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="61a34-122">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.\* See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61a34-123"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-123"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-124">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="61a34-124">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61a34-125">用于关联多个会话的 GUID。</span><span class="sxs-lookup"><span data-stu-id="61a34-125">A GUID to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61a34-126"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-126"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-127">datetime</span><span class="sxs-lookup"><span data-stu-id="61a34-127">datetime</span></span></p></td>
<td><p><span data-ttu-id="61a34-128">对外</span><span class="sxs-lookup"><span data-stu-id="61a34-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61a34-129">用于标识由当前会话取代的对话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="61a34-129">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="61a34-130">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="61a34-130">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61a34-131"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-131"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-132">int</span><span class="sxs-lookup"><span data-stu-id="61a34-132">int</span></span></p></td>
<td><p><span data-ttu-id="61a34-133">对外</span><span class="sxs-lookup"><span data-stu-id="61a34-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61a34-134">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="61a34-134">ID number to identify the session.</span></span> <span data-ttu-id="61a34-135">与 <strong>ReplacesDialogIdTime</strong> 结合使用来唯一地标识由此会话取代的会话。</span><span class="sxs-lookup"><span data-stu-id="61a34-135">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="61a34-136">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="61a34-136">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61a34-137"><strong>User1Id</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-137"><strong>User1Id</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-138">int</span><span class="sxs-lookup"><span data-stu-id="61a34-138">int</span></span></p></td>
<td><p><span data-ttu-id="61a34-139">对外</span><span class="sxs-lookup"><span data-stu-id="61a34-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61a34-140">会话中的一个用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="61a34-140">ID of one user in the session.</span></span> <span data-ttu-id="61a34-141">有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="61a34-141">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61a34-142"><strong>User2Id</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-142"><strong>User2Id</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-143">int</span><span class="sxs-lookup"><span data-stu-id="61a34-143">int</span></span></p></td>
<td><p><span data-ttu-id="61a34-144">对外</span><span class="sxs-lookup"><span data-stu-id="61a34-144">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61a34-145">会话中另一个用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="61a34-145">ID of the other user in the session.</span></span> <span data-ttu-id="61a34-146">有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="61a34-146">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61a34-147"><strong>User1EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-147"><strong>User1EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-148">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="61a34-148">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61a34-149">标识会话中的第一个用户所使用的终结点的 GUID。</span><span class="sxs-lookup"><span data-stu-id="61a34-149">GUID that identifies the endpoint used by the first user in the session.</span></span></p>
<p><span data-ttu-id="61a34-150">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="61a34-150">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61a34-151"><strong>User2EndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-151"><strong>User2EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-152">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="61a34-152">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61a34-153">标识会话中的第二个用户所使用的终结点的 GUID。</span><span class="sxs-lookup"><span data-stu-id="61a34-153">GUID that identifies the endpoint used by the second user in the session.</span></span></p>
<p><span data-ttu-id="61a34-154">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="61a34-154">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61a34-155"><strong>TargetUserId</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-155"><strong>TargetUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-156">int</span><span class="sxs-lookup"><span data-stu-id="61a34-156">int</span></span></p></td>
<td><p><span data-ttu-id="61a34-157">对外</span><span class="sxs-lookup"><span data-stu-id="61a34-157">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61a34-158">SIP 请求中的原始目标用户 URI。</span><span class="sxs-lookup"><span data-stu-id="61a34-158">The original To user URI in the SIP request.</span></span> <span data-ttu-id="61a34-159">有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="61a34-159">see the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61a34-160"><strong>SessionStartedById</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-160"><strong>SessionStartedById</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-161">int</span><span class="sxs-lookup"><span data-stu-id="61a34-161">int</span></span></p></td>
<td><p><span data-ttu-id="61a34-162">对外</span><span class="sxs-lookup"><span data-stu-id="61a34-162">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61a34-163">启动会话的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="61a34-163">ID of the user who started the session.</span></span> <span data-ttu-id="61a34-164">有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="61a34-164">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61a34-165"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-165"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-166">int</span><span class="sxs-lookup"><span data-stu-id="61a34-166">int</span></span></p></td>
<td><p><span data-ttu-id="61a34-167">对外</span><span class="sxs-lookup"><span data-stu-id="61a34-167">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61a34-168">指示呼叫者所代表的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="61a34-168">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="61a34-169">有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="61a34-169">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61a34-170"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-170"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-171">int</span><span class="sxs-lookup"><span data-stu-id="61a34-171">int</span></span></p></td>
<td><p><span data-ttu-id="61a34-172">对外</span><span class="sxs-lookup"><span data-stu-id="61a34-172">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61a34-173">引用呼叫的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="61a34-173">ID of the user by who the call is referred.</span></span> <span data-ttu-id="61a34-174">有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="61a34-174">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61a34-175"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-175"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-176">int</span><span class="sxs-lookup"><span data-stu-id="61a34-176">int</span></span></p></td>
<td><p><span data-ttu-id="61a34-177">对外</span><span class="sxs-lookup"><span data-stu-id="61a34-177">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61a34-178">用于此会话的前端服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="61a34-178">ID of the front-end server used for this session.</span></span> <span data-ttu-id="61a34-179">有关详细信息，请参阅 <a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="61a34-179">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61a34-180"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-180"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-181">int</span><span class="sxs-lookup"><span data-stu-id="61a34-181">int</span></span></p></td>
<td><p><span data-ttu-id="61a34-182">对外</span><span class="sxs-lookup"><span data-stu-id="61a34-182">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61a34-183">在其中捕获会话的池的 ID。</span><span class="sxs-lookup"><span data-stu-id="61a34-183">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="61a34-184">有关详细信息，请参阅 <a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="61a34-184">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61a34-185"><strong>ContentTypeID</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-185"><strong>ContentTypeID</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-186">int</span><span class="sxs-lookup"><span data-stu-id="61a34-186">int</span></span></p></td>
<td><p><span data-ttu-id="61a34-187">对外</span><span class="sxs-lookup"><span data-stu-id="61a34-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61a34-188">会话中使用的内容类型。</span><span class="sxs-lookup"><span data-stu-id="61a34-188">Content type used in the session.</span></span> <span data-ttu-id="61a34-189">有关详细信息，请参阅 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="61a34-189">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61a34-190"><strong>User1ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-190"><strong>User1ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-191">int</span><span class="sxs-lookup"><span data-stu-id="61a34-191">int</span></span></p></td>
<td><p><span data-ttu-id="61a34-192">对外</span><span class="sxs-lookup"><span data-stu-id="61a34-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61a34-193">User1 使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="61a34-193">Client version used by User1.</span></span> <span data-ttu-id="61a34-194">有关详细信息，请参阅 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="61a34-194">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61a34-195"><strong>User2ClientVerId</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-195"><strong>User2ClientVerId</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-196">int</span><span class="sxs-lookup"><span data-stu-id="61a34-196">int</span></span></p></td>
<td><p><span data-ttu-id="61a34-197">对外</span><span class="sxs-lookup"><span data-stu-id="61a34-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61a34-198">User2 使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="61a34-198">Client version used by User2.</span></span> <span data-ttu-id="61a34-199">有关详细信息，请参阅 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="61a34-199">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61a34-200"><strong>User1EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-200"><strong>User1EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-201">int</span><span class="sxs-lookup"><span data-stu-id="61a34-201">int</span></span></p></td>
<td><p><span data-ttu-id="61a34-202">对外</span><span class="sxs-lookup"><span data-stu-id="61a34-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61a34-203">User1 使用的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="61a34-203">Edge Server used by User1.</span></span> <span data-ttu-id="61a34-204">有关详细信息，请参阅 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="61a34-204">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61a34-205"><strong>User2EdgeServerid</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-205"><strong>User2EdgeServerid</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-206">int</span><span class="sxs-lookup"><span data-stu-id="61a34-206">int</span></span></p></td>
<td><p><span data-ttu-id="61a34-207">对外</span><span class="sxs-lookup"><span data-stu-id="61a34-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61a34-208">User2 使用的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="61a34-208">Edge Server used by User2.</span></span> <span data-ttu-id="61a34-209">有关详细信息，请参阅 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="61a34-209">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61a34-210"><strong>IsUser1Internal</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-210"><strong>IsUser1Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-211">位</span><span class="sxs-lookup"><span data-stu-id="61a34-211">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61a34-212">User1 是否从内部登录。</span><span class="sxs-lookup"><span data-stu-id="61a34-212">Whether User1 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61a34-213"><strong>IsUser2Internal</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-213"><strong>IsUser2Internal</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-214">位</span><span class="sxs-lookup"><span data-stu-id="61a34-214">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61a34-215">User2 是否从内部登录。</span><span class="sxs-lookup"><span data-stu-id="61a34-215">Whether User2 is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61a34-216"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-216"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-217">datetime</span><span class="sxs-lookup"><span data-stu-id="61a34-217">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61a34-218">第一个 INVITE 请求的时间。</span><span class="sxs-lookup"><span data-stu-id="61a34-218">The time of the first INVITE request.</span></span> <span data-ttu-id="61a34-219">此字段通常用从会话中的初始 INVITE 消息生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="61a34-219">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="61a34-220">如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="61a34-220">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="61a34-221">此字段通常用从会话中的初始 INVITE 消息生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="61a34-221">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="61a34-222">如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="61a34-222">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61a34-223"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-223"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-224">datetime</span><span class="sxs-lookup"><span data-stu-id="61a34-224">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61a34-225">第一个 INVITE 消息的响应时间。</span><span class="sxs-lookup"><span data-stu-id="61a34-225">The time of the response to the first INVITE message.</span></span> <span data-ttu-id="61a34-226">此字段通常用从会话中的初始 INVITE 消息生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="61a34-226">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="61a34-227">如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="61a34-227">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61a34-228"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-228"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-229">int</span><span class="sxs-lookup"><span data-stu-id="61a34-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61a34-p121">会话邀请的 SIP 响应代码。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="61a34-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61a34-233"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-233"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-234">int</span><span class="sxs-lookup"><span data-stu-id="61a34-234">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61a34-235">从 SIP 标头捕获的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="61a34-235">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61a34-236"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-236"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-237">int</span><span class="sxs-lookup"><span data-stu-id="61a34-237">int</span></span></p></td>
<td><p><span data-ttu-id="61a34-238">对外</span><span class="sxs-lookup"><span data-stu-id="61a34-238">Foreign</span></span></p></td>
<td><p><span data-ttu-id="61a34-239">呼叫优先级。</span><span class="sxs-lookup"><span data-stu-id="61a34-239">Call priority.</span></span> <span data-ttu-id="61a34-240">有关详细信息，请参阅 <a href="lync-server-2013-callpriorities-table.md">Lync Server 2013 中的 CallPriorities 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="61a34-240">See the <a href="lync-server-2013-callpriorities-table.md">CallPriorities table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61a34-241"><strong>User1MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-241"><strong>User1MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-242">int</span><span class="sxs-lookup"><span data-stu-id="61a34-242">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61a34-243">User1 在会话期间发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="61a34-243">Number of messages sent by User1 during the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61a34-244"><strong>User2MessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-244"><strong>User2MessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-245">int</span><span class="sxs-lookup"><span data-stu-id="61a34-245">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61a34-246">User2 在会话期间发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="61a34-246">Number of messages sent by User2 during the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61a34-247"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-247"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-248">datetime</span><span class="sxs-lookup"><span data-stu-id="61a34-248">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61a34-249">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="61a34-249">Time at the end of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61a34-250"><strong>MediaTypes</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-250"><strong>MediaTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-251">int</span><span class="sxs-lookup"><span data-stu-id="61a34-251">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61a34-p123">指示此会话的媒体类型的位集。下面列出了类型的定义：</span><span class="sxs-lookup"><span data-stu-id="61a34-p123">A bit set that indicates the media type of this session. Listed are the definitions of the types:</span></span></p>
<h3 id="section-1"> </h3>
<div>
<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61a34-254">IM</span><span class="sxs-lookup"><span data-stu-id="61a34-254">IM</span></span></p></td>
<td><p><span data-ttu-id="61a34-255">1</span><span class="sxs-lookup"><span data-stu-id="61a34-255">1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61a34-256">FILE_TRANSFER</span><span class="sxs-lookup"><span data-stu-id="61a34-256">FILE_TRANSFER</span></span></p></td>
<td><p><span data-ttu-id="61a34-257">双面</span><span class="sxs-lookup"><span data-stu-id="61a34-257">2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61a34-258">REMOTE_ASSISTANCE</span><span class="sxs-lookup"><span data-stu-id="61a34-258">REMOTE_ASSISTANCE</span></span></p></td>
<td><p><span data-ttu-id="61a34-259">4 </span><span class="sxs-lookup"><span data-stu-id="61a34-259">4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61a34-260">APP_SHARING</span><span class="sxs-lookup"><span data-stu-id="61a34-260">APP_SHARING</span></span></p></td>
<td><p><span data-ttu-id="61a34-261">8 </span><span class="sxs-lookup"><span data-stu-id="61a34-261">8</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61a34-262">视频</span><span class="sxs-lookup"><span data-stu-id="61a34-262">AUDIO</span></span></p></td>
<td><p><span data-ttu-id="61a34-263">16 </span><span class="sxs-lookup"><span data-stu-id="61a34-263">16</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61a34-264">显示</span><span class="sxs-lookup"><span data-stu-id="61a34-264">VIDEO</span></span></p></td>
<td><p><span data-ttu-id="61a34-265">32</span><span class="sxs-lookup"><span data-stu-id="61a34-265">32</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61a34-266">APP_INVITE</span><span class="sxs-lookup"><span data-stu-id="61a34-266">APP_INVITE</span></span></p></td>
<td><p><span data-ttu-id="61a34-267">64</span><span class="sxs-lookup"><span data-stu-id="61a34-267">64</span></span></p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61a34-268"><strong>User1Flag</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-268"><strong>User1Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-269">smallint</span><span class="sxs-lookup"><span data-stu-id="61a34-269">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61a34-p124">指示 User1 属性的位集。列出了以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="61a34-p124">A bit set that indicates the User1 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="61a34-272">0x01 - 与桌面电话集成</span><span class="sxs-lookup"><span data-stu-id="61a34-272">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61a34-273"><strong>User2Flag</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-273"><strong>User2Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-274">smallint</span><span class="sxs-lookup"><span data-stu-id="61a34-274">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61a34-p125">指示 User2 属性的位集。列出了以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="61a34-p125">A bit set that indicates the User2 attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="61a34-277">0x01 - 与桌面电话集成</span><span class="sxs-lookup"><span data-stu-id="61a34-277">0x01 - Integrated with desktop phone</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61a34-278"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-278"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-279">smallint</span><span class="sxs-lookup"><span data-stu-id="61a34-279">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61a34-p126">指示呼叫属性的位集。列出了以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="61a34-p126">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="61a34-282">0x01 - 重试会话</span><span class="sxs-lookup"><span data-stu-id="61a34-282">0x01 - Retried Session</span></span></p></li>
<li><p><span data-ttu-id="61a34-283">0x02 - 代表响应组的代理进行的呼叫</span><span class="sxs-lookup"><span data-stu-id="61a34-283">0x02 - A call made by agent on behalf of a response group</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61a34-284"><strong>处理</strong></span><span class="sxs-lookup"><span data-stu-id="61a34-284"><strong>Processed</strong></span></span></p></td>
<td><p><span data-ttu-id="61a34-285">位</span><span class="sxs-lookup"><span data-stu-id="61a34-285">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="61a34-286">供监控服务内部使用。</span><span class="sxs-lookup"><span data-stu-id="61a34-286">For internal use by the Monitoring service.</span></span></p>
<p><span data-ttu-id="61a34-287">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="61a34-287">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="61a34-288">\* 对于大多数会话，SessionIdSeq 的值将为1。</span><span class="sxs-lookup"><span data-stu-id="61a34-288">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="61a34-289">如果多个会话完全同时启动，则一个会话的 SessionIdSeq 将为 1，另一个会话的 SessionIdSeq 将为 2，依此类推。</span><span class="sxs-lookup"><span data-stu-id="61a34-289">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

