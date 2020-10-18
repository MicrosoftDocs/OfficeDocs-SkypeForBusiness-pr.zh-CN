---
title: Lync Server 2013： SessionDetails 视图
description: Lync Server 2013： SessionDetails 视图。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c9f657257e54389defb805919be61adbdecad74
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573238"
---
# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="d1a54-103">Lync Server 2013 中的 SessionDetails 视图</span><span class="sxs-lookup"><span data-stu-id="d1a54-103">SessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1a54-104">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d1a54-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d1a54-105">SessionDetails 视图存储有关点对点会话的信息，这应该是 VoIP-VoIP 电话呼叫、双方 IM 会话或其他类型的会话。</span><span class="sxs-lookup"><span data-stu-id="d1a54-105">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="d1a54-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="d1a54-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1a54-107">列</span><span class="sxs-lookup"><span data-stu-id="d1a54-107">Column</span></span></th>
<th><span data-ttu-id="d1a54-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="d1a54-108">Data Type</span></span></th>
<th><span data-ttu-id="d1a54-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="d1a54-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-111">datetime</span><span class="sxs-lookup"><span data-stu-id="d1a54-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="d1a54-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="d1a54-112">Time of session request.</span></span> <span data-ttu-id="d1a54-113">与 SessionIdSeq 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="d1a54-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="d1a54-114">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 表中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="d1a54-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-116">int</span><span class="sxs-lookup"><span data-stu-id="d1a54-116">int</span></span></p></td>
<td><p><span data-ttu-id="d1a54-117">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="d1a54-117">ID number to identify the session.</span></span> <span data-ttu-id="d1a54-118">与 SessionIdTime 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="d1a54-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="d1a54-119">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="d1a54-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-121">datetime</span><span class="sxs-lookup"><span data-stu-id="d1a54-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="d1a54-p104">第一个 INVITE 请求的时间。此字段通常由从会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="d1a54-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO). This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-127"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-127"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-128">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="d1a54-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-129">启动会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="d1a54-129">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-130"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-130"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-131">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="d1a54-131">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-132">加入会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="d1a54-132">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-133"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-133"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-134">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d1a54-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-135">启动会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="d1a54-135">Type of URI of the user who started the session.</span></span> <span data-ttu-id="d1a54-136">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="d1a54-136">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-137"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-137"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-138">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d1a54-138">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-139">加入会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="d1a54-139">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="d1a54-140">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="d1a54-140">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-141"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-141"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-142">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="d1a54-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-143">启动会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="d1a54-143">Tenant of the user who started the session.</span></span> <span data-ttu-id="d1a54-144">有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a> 。</span><span class="sxs-lookup"><span data-stu-id="d1a54-144">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-145"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-145"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-146">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d1a54-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-147">加入会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="d1a54-147">The tenant of the user who joined the session.</span></span> <span data-ttu-id="d1a54-148">有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a> 。</span><span class="sxs-lookup"><span data-stu-id="d1a54-148">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-149"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-149"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-150">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="d1a54-150">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="d1a54-151">启动会话的用户的终结点的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="d1a54-151">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-152"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-152"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-153">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="d1a54-153">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="d1a54-154">加入会话的用户的终结点的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="d1a54-154">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-155"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-155"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-156">datetime</span><span class="sxs-lookup"><span data-stu-id="d1a54-156">datetime</span></span></p></td>
<td><p><span data-ttu-id="d1a54-157">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="d1a54-157">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-158"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-158"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-159">int</span><span class="sxs-lookup"><span data-stu-id="d1a54-159">int</span></span></p></td>
<td><p><span data-ttu-id="d1a54-160">启动会话的用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="d1a54-160">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-161"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-161"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-162">int</span><span class="sxs-lookup"><span data-stu-id="d1a54-162">int</span></span></p></td>
<td><p><span data-ttu-id="d1a54-163">加入会话的用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="d1a54-163">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-164"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-164"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-165">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d1a54-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-166">启动会话的用户使用的客户端的版本。</span><span class="sxs-lookup"><span data-stu-id="d1a54-166">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-167"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-167"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-168">int</span><span class="sxs-lookup"><span data-stu-id="d1a54-168">int</span></span></p></td>
<td><p><span data-ttu-id="d1a54-169">启动会话的用户使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="d1a54-169">Client used by the user who started the session.</span></span> <span data-ttu-id="d1a54-170">有关更多详细信息，请参阅 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="d1a54-170">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-171"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-171"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-172">nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="d1a54-172">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-173">启动会话的用户使用的客户端的类别名称。</span><span class="sxs-lookup"><span data-stu-id="d1a54-173">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-174"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-174"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-175">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d1a54-175">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-176">加入会话的用户使用的客户端的版本。</span><span class="sxs-lookup"><span data-stu-id="d1a54-176">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-177"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-177"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-178">int</span><span class="sxs-lookup"><span data-stu-id="d1a54-178">int</span></span></p></td>
<td><p><span data-ttu-id="d1a54-179">加入会话的用户使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="d1a54-179">Client used by the user who joined the session.</span></span> <span data-ttu-id="d1a54-180">有关更多详细信息，请参阅 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="d1a54-180">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-181"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-181"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-182">nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="d1a54-182">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-183">加入会话的用户使用的客户端的类别名称。</span><span class="sxs-lookup"><span data-stu-id="d1a54-183">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-184"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-184"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-185">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="d1a54-185">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-186">会话的目标用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="d1a54-186">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-187"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-187"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-188">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="d1a54-188">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-189">会话的目标用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="d1a54-189">Type of URI of the target user for the session.</span></span> <span data-ttu-id="d1a54-190">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="d1a54-190">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-191"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-191"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-192">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="d1a54-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-193">代表启动会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="d1a54-193">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-194"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-194"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-195">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d1a54-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-196">代表启动会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="d1a54-196">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="d1a54-197">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="d1a54-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-198"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-198"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-199">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d1a54-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-200">代表启动会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="d1a54-200">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="d1a54-201">有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a> 。</span><span class="sxs-lookup"><span data-stu-id="d1a54-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-202"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-202"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-203">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="d1a54-203">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-204">提交会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="d1a54-204">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-205"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-205"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-206">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d1a54-206">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-207">提交会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="d1a54-207">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="d1a54-208">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="d1a54-208">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-209"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-209"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-210">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d1a54-210">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-211">提交会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="d1a54-211">Tenant of the user who referred the session.</span></span> <span data-ttu-id="d1a54-212">有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a> 。</span><span class="sxs-lookup"><span data-stu-id="d1a54-212">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-213"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-213"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-214">varchar (775) </span><span class="sxs-lookup"><span data-stu-id="d1a54-214">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-p116">SIP 对话 ID。格式为：</span><span class="sxs-lookup"><span data-stu-id="d1a54-p116">SIP dialog ID. The format is:</span></span></p>
<p><span data-ttu-id="d1a54-217">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="d1a54-217">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-218"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-218"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-219">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="d1a54-219">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="d1a54-220">用于关联多个会话的 GUID。</span><span class="sxs-lookup"><span data-stu-id="d1a54-220">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-221"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-221"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-222">datetime</span><span class="sxs-lookup"><span data-stu-id="d1a54-222">datetime</span></span></p></td>
<td><p><span data-ttu-id="d1a54-223">由会话取代的对话的时间。</span><span class="sxs-lookup"><span data-stu-id="d1a54-223">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="d1a54-224">与 ReplaceDialogIdSeq 结合起来使用，以唯一地标识由此会话取代的对话。</span><span class="sxs-lookup"><span data-stu-id="d1a54-224">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="d1a54-225">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="d1a54-225">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-226"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-226"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-227">int</span><span class="sxs-lookup"><span data-stu-id="d1a54-227">int</span></span></p></td>
<td><p><span data-ttu-id="d1a54-228">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="d1a54-228">ID number to identify the session.</span></span> <span data-ttu-id="d1a54-229">与 ReplacesDialogIdTime 结合使用来唯一地标识由该会话取代的会话。</span><span class="sxs-lookup"><span data-stu-id="d1a54-229">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="d1a54-230">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="d1a54-230">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-231"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-231"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-232">varchar (775) </span><span class="sxs-lookup"><span data-stu-id="d1a54-232">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-p119">会话取代的 SIP 对话 ID。格式为：</span><span class="sxs-lookup"><span data-stu-id="d1a54-p119">SIP dialog ID the session replaces. The format is:</span></span></p>
<p><span data-ttu-id="d1a54-235">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="d1a54-235">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-236"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-236"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-237">datetime</span><span class="sxs-lookup"><span data-stu-id="d1a54-237">datetime</span></span></p></td>
<td><p><span data-ttu-id="d1a54-p120">对第一个 INVITE 消息的响应时间。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="d1a54-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-241"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-241"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-242">int</span><span class="sxs-lookup"><span data-stu-id="d1a54-242">int</span></span></p></td>
<td><p><span data-ttu-id="d1a54-p121">会话邀请的 SIP 响应代码。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="d1a54-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-246"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-246"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-247">int</span><span class="sxs-lookup"><span data-stu-id="d1a54-247">int</span></span></p></td>
<td><p><span data-ttu-id="d1a54-248">从 SIP 标头捕获的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="d1a54-248">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-249"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-249"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-250">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d1a54-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-251">会话内容的类型。</span><span class="sxs-lookup"><span data-stu-id="d1a54-251">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-252"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-252"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-253">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d1a54-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-254">捕获会话数据的前端服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d1a54-254">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-255"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-255"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-256">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d1a54-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-257">捕获会话数据的池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d1a54-257">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-258"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-258"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-259">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d1a54-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-260">启动会话的用户使用的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="d1a54-260">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-261"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-261"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-262">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d1a54-262">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-263">启动会话的用户使用的边缘服务器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="d1a54-263">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-264"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-264"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-265">位</span><span class="sxs-lookup"><span data-stu-id="d1a54-265">bit</span></span></p></td>
<td><p><span data-ttu-id="d1a54-266">指示启动会话的用户是否从内部网络登录。</span><span class="sxs-lookup"><span data-stu-id="d1a54-266">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-267"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-267"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-268">位</span><span class="sxs-lookup"><span data-stu-id="d1a54-268">bit</span></span></p></td>
<td><p><span data-ttu-id="d1a54-269">指示加入会话的用户是否从内部网络登录。</span><span class="sxs-lookup"><span data-stu-id="d1a54-269">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-270"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-270"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-271">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="d1a54-271">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-272">会话的呼叫属性。</span><span class="sxs-lookup"><span data-stu-id="d1a54-272">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-273"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-273"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-274">smallint</span><span class="sxs-lookup"><span data-stu-id="d1a54-274">smallint</span></span></p></td>
<td><p><span data-ttu-id="d1a54-p122">指示启动会话的用户的属性。允许以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="d1a54-p122">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="d1a54-277">0x01 - 与桌面电话集成</span><span class="sxs-lookup"><span data-stu-id="d1a54-277">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-278"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-278"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-279">smallint</span><span class="sxs-lookup"><span data-stu-id="d1a54-279">smallint</span></span></p></td>
<td><p><span data-ttu-id="d1a54-p123">指示启动会话的用户的属性。允许以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="d1a54-p123">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="d1a54-282">0x01 - 与桌面电话集成</span><span class="sxs-lookup"><span data-stu-id="d1a54-282">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1a54-283"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-283"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-284">smallint</span><span class="sxs-lookup"><span data-stu-id="d1a54-284">smallint</span></span></p></td>
<td><p><span data-ttu-id="d1a54-p124">指示呼叫属性。允许以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="d1a54-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="d1a54-287">0x01 - 重试会话</span><span class="sxs-lookup"><span data-stu-id="d1a54-287">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="d1a54-288">0x02 - 代表响应组的代理进行的呼叫</span><span class="sxs-lookup"><span data-stu-id="d1a54-288">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1a54-289"><strong>位置</strong></span><span class="sxs-lookup"><span data-stu-id="d1a54-289"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="d1a54-290">varchar (max) </span><span class="sxs-lookup"><span data-stu-id="d1a54-290">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="d1a54-291">紧急呼叫的位置。</span><span class="sxs-lookup"><span data-stu-id="d1a54-291">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

