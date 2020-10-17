---
title: Lync Server 2013： SessionDetails 视图
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
ms.openlocfilehash: 8baf67ce72103ef0dda64a9b0b43a8f6dd6402f4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510059"
---
# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="e37fc-102">Lync Server 2013 中的 SessionDetails 视图</span><span class="sxs-lookup"><span data-stu-id="e37fc-102">SessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e37fc-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e37fc-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e37fc-104">SessionDetails 视图存储有关点对点会话的信息，这应该是 VoIP-VoIP 电话呼叫、双方 IM 会话或其他类型的会话。</span><span class="sxs-lookup"><span data-stu-id="e37fc-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="e37fc-105">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="e37fc-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e37fc-106">列</span><span class="sxs-lookup"><span data-stu-id="e37fc-106">Column</span></span></th>
<th><span data-ttu-id="e37fc-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="e37fc-107">Data Type</span></span></th>
<th><span data-ttu-id="e37fc-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="e37fc-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-110">datetime</span><span class="sxs-lookup"><span data-stu-id="e37fc-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="e37fc-111">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="e37fc-111">Time of session request.</span></span> <span data-ttu-id="e37fc-112">与 SessionIdSeq 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="e37fc-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="e37fc-113">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 表中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e37fc-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-115">int</span><span class="sxs-lookup"><span data-stu-id="e37fc-115">int</span></span></p></td>
<td><p><span data-ttu-id="e37fc-116">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="e37fc-116">ID number to identify the session.</span></span> <span data-ttu-id="e37fc-117">与 SessionIdTime 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="e37fc-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="e37fc-118">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e37fc-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-119"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-120">datetime</span><span class="sxs-lookup"><span data-stu-id="e37fc-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="e37fc-p104">第一个 INVITE 请求的时间。此字段通常由从会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="e37fc-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO). This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-127">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="e37fc-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-128">启动会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="e37fc-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-129"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-130">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="e37fc-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-131">加入会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="e37fc-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-133">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e37fc-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-134">启动会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="e37fc-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="e37fc-135">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e37fc-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-137">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e37fc-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-138">加入会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="e37fc-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="e37fc-139">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e37fc-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-141">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="e37fc-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-142">启动会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="e37fc-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="e37fc-143">有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e37fc-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-144"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-145">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e37fc-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-146">加入会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="e37fc-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="e37fc-147">有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e37fc-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-149">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="e37fc-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e37fc-150">启动会话的用户的终结点的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e37fc-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-151"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-152">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="e37fc-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e37fc-153">加入会话的用户的终结点的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e37fc-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-155">datetime</span><span class="sxs-lookup"><span data-stu-id="e37fc-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="e37fc-156">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="e37fc-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-158">int</span><span class="sxs-lookup"><span data-stu-id="e37fc-158">int</span></span></p></td>
<td><p><span data-ttu-id="e37fc-159">启动会话的用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="e37fc-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-161">int</span><span class="sxs-lookup"><span data-stu-id="e37fc-161">int</span></span></p></td>
<td><p><span data-ttu-id="e37fc-162">加入会话的用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="e37fc-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-164">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e37fc-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-165">启动会话的用户使用的客户端的版本。</span><span class="sxs-lookup"><span data-stu-id="e37fc-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-167">int</span><span class="sxs-lookup"><span data-stu-id="e37fc-167">int</span></span></p></td>
<td><p><span data-ttu-id="e37fc-168">启动会话的用户使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="e37fc-168">Client used by the user who started the session.</span></span> <span data-ttu-id="e37fc-169">有关更多详细信息，请参阅 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e37fc-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-171">nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="e37fc-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-172">启动会话的用户使用的客户端的类别名称。</span><span class="sxs-lookup"><span data-stu-id="e37fc-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-174">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e37fc-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-175">加入会话的用户使用的客户端的版本。</span><span class="sxs-lookup"><span data-stu-id="e37fc-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-176"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-177">int</span><span class="sxs-lookup"><span data-stu-id="e37fc-177">int</span></span></p></td>
<td><p><span data-ttu-id="e37fc-178">加入会话的用户使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="e37fc-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="e37fc-179">有关更多详细信息，请参阅 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e37fc-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-181">nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="e37fc-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-182">加入会话的用户使用的客户端的类别名称。</span><span class="sxs-lookup"><span data-stu-id="e37fc-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-184">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="e37fc-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-185">会话的目标用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="e37fc-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-187">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="e37fc-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-188">会话的目标用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="e37fc-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="e37fc-189">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e37fc-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-191">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="e37fc-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-192">代表启动会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="e37fc-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-194">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e37fc-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-195">代表启动会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="e37fc-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="e37fc-196">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e37fc-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-198">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e37fc-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-199">代表启动会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="e37fc-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="e37fc-200">有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e37fc-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-202">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="e37fc-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-203">提交会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="e37fc-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-205">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e37fc-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-206">提交会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="e37fc-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="e37fc-207">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e37fc-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-209">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e37fc-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-210">提交会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="e37fc-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="e37fc-211">有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e37fc-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-213">varchar (775) </span><span class="sxs-lookup"><span data-stu-id="e37fc-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-p116">SIP 对话 ID。格式为：</span><span class="sxs-lookup"><span data-stu-id="e37fc-p116">SIP dialog ID. The format is:</span></span></p>
<p><span data-ttu-id="e37fc-216">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="e37fc-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-217"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-218">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="e37fc-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e37fc-219">用于关联多个会话的 GUID。</span><span class="sxs-lookup"><span data-stu-id="e37fc-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-221">datetime</span><span class="sxs-lookup"><span data-stu-id="e37fc-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="e37fc-222">由会话取代的对话的时间。</span><span class="sxs-lookup"><span data-stu-id="e37fc-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="e37fc-223">与 ReplaceDialogIdSeq 结合起来使用，以唯一地标识由此会话取代的对话。</span><span class="sxs-lookup"><span data-stu-id="e37fc-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="e37fc-224">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e37fc-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-226">int</span><span class="sxs-lookup"><span data-stu-id="e37fc-226">int</span></span></p></td>
<td><p><span data-ttu-id="e37fc-227">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="e37fc-227">ID number to identify the session.</span></span> <span data-ttu-id="e37fc-228">与 ReplacesDialogIdTime 结合使用来唯一地标识由该会话取代的会话。</span><span class="sxs-lookup"><span data-stu-id="e37fc-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="e37fc-229">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e37fc-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-231">varchar (775) </span><span class="sxs-lookup"><span data-stu-id="e37fc-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-p119">会话取代的 SIP 对话 ID。格式为：</span><span class="sxs-lookup"><span data-stu-id="e37fc-p119">SIP dialog ID the session replaces. The format is:</span></span></p>
<p><span data-ttu-id="e37fc-234">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="e37fc-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-236">datetime</span><span class="sxs-lookup"><span data-stu-id="e37fc-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="e37fc-p120">对第一个 INVITE 消息的响应时间。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="e37fc-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-241">int</span><span class="sxs-lookup"><span data-stu-id="e37fc-241">int</span></span></p></td>
<td><p><span data-ttu-id="e37fc-p121">会话邀请的 SIP 响应代码。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="e37fc-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-245"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-246">int</span><span class="sxs-lookup"><span data-stu-id="e37fc-246">int</span></span></p></td>
<td><p><span data-ttu-id="e37fc-247">从 SIP 标头捕获的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="e37fc-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-249">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e37fc-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-250">会话内容的类型。</span><span class="sxs-lookup"><span data-stu-id="e37fc-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-252">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e37fc-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-253">捕获会话数据的前端服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e37fc-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-255">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e37fc-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-256">捕获会话数据的池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e37fc-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-258">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e37fc-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-259">启动会话的用户使用的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e37fc-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-261">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e37fc-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-262">启动会话的用户使用的边缘服务器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="e37fc-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-264">位</span><span class="sxs-lookup"><span data-stu-id="e37fc-264">bit</span></span></p></td>
<td><p><span data-ttu-id="e37fc-265">指示启动会话的用户是否从内部网络登录。</span><span class="sxs-lookup"><span data-stu-id="e37fc-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-267">位</span><span class="sxs-lookup"><span data-stu-id="e37fc-267">bit</span></span></p></td>
<td><p><span data-ttu-id="e37fc-268">指示加入会话的用户是否从内部网络登录。</span><span class="sxs-lookup"><span data-stu-id="e37fc-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-270">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e37fc-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-271">会话的呼叫属性。</span><span class="sxs-lookup"><span data-stu-id="e37fc-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-273">smallint</span><span class="sxs-lookup"><span data-stu-id="e37fc-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="e37fc-p122">指示启动会话的用户的属性。允许以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="e37fc-p122">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="e37fc-276">0x01 - 与桌面电话集成</span><span class="sxs-lookup"><span data-stu-id="e37fc-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-278">smallint</span><span class="sxs-lookup"><span data-stu-id="e37fc-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="e37fc-p123">指示启动会话的用户的属性。允许以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="e37fc-p123">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="e37fc-281">0x01 - 与桌面电话集成</span><span class="sxs-lookup"><span data-stu-id="e37fc-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e37fc-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-283">smallint</span><span class="sxs-lookup"><span data-stu-id="e37fc-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="e37fc-p124">指示呼叫属性。允许以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="e37fc-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="e37fc-286">0x01 - 重试会话</span><span class="sxs-lookup"><span data-stu-id="e37fc-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="e37fc-287">0x02 - 代表响应组的代理进行的呼叫</span><span class="sxs-lookup"><span data-stu-id="e37fc-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e37fc-288"><strong>位置</strong></span><span class="sxs-lookup"><span data-stu-id="e37fc-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="e37fc-289">varchar (max) </span><span class="sxs-lookup"><span data-stu-id="e37fc-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="e37fc-290">紧急呼叫的位置。</span><span class="sxs-lookup"><span data-stu-id="e37fc-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

