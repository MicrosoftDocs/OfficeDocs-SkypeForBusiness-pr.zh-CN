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
ms.openlocfilehash: 66d883b48d1269fff8a57594101f083c88f1fbd1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="53a24-102">Lync Server 2013 中的 SessionDetails 视图</span><span class="sxs-lookup"><span data-stu-id="53a24-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53a24-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="53a24-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="53a24-104">SessionDetails 视图存储有关点对点会话的信息，这应该是 VoIP-VoIP 电话呼叫、双方 IM 会话或其他类型的会话。</span><span class="sxs-lookup"><span data-stu-id="53a24-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="53a24-105">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="53a24-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53a24-106">列</span><span class="sxs-lookup"><span data-stu-id="53a24-106">Column</span></span></th>
<th><span data-ttu-id="53a24-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="53a24-107">Data Type</span></span></th>
<th><span data-ttu-id="53a24-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="53a24-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53a24-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-110">datetime</span><span class="sxs-lookup"><span data-stu-id="53a24-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="53a24-111">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="53a24-111">Time of session request.</span></span> <span data-ttu-id="53a24-112">与 SessionIdSeq 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="53a24-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="53a24-113">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 表中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="53a24-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-115">int</span><span class="sxs-lookup"><span data-stu-id="53a24-115">int</span></span></p></td>
<td><p><span data-ttu-id="53a24-116">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="53a24-116">ID number to identify the session.</span></span> <span data-ttu-id="53a24-117">与 SessionIdTime 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="53a24-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="53a24-118">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="53a24-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-119"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-120">datetime</span><span class="sxs-lookup"><span data-stu-id="53a24-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="53a24-p104">第一个 INVITE 请求的时间。此字段通常由从会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="53a24-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO). This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-127">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="53a24-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="53a24-128">启动会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="53a24-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-129"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-130">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="53a24-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="53a24-131">加入会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="53a24-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-133">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="53a24-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="53a24-134">启动会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="53a24-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="53a24-135">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="53a24-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-137">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="53a24-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="53a24-138">加入会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="53a24-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="53a24-139">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="53a24-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-141">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="53a24-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="53a24-142">启动会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="53a24-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="53a24-143">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="53a24-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-144"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-145">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="53a24-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="53a24-146">加入会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="53a24-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="53a24-147">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="53a24-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-149">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="53a24-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="53a24-150">启动会话的用户的终结点的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="53a24-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-151"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-152">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="53a24-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="53a24-153">加入会话的用户的终结点的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="53a24-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-155">datetime</span><span class="sxs-lookup"><span data-stu-id="53a24-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="53a24-156">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="53a24-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-158">int</span><span class="sxs-lookup"><span data-stu-id="53a24-158">int</span></span></p></td>
<td><p><span data-ttu-id="53a24-159">启动会话的用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="53a24-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-161">int</span><span class="sxs-lookup"><span data-stu-id="53a24-161">int</span></span></p></td>
<td><p><span data-ttu-id="53a24-162">加入会话的用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="53a24-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-164">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="53a24-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="53a24-165">启动会话的用户使用的客户端的版本。</span><span class="sxs-lookup"><span data-stu-id="53a24-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-167">int</span><span class="sxs-lookup"><span data-stu-id="53a24-167">int</span></span></p></td>
<td><p><span data-ttu-id="53a24-168">启动会话的用户使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="53a24-168">Client used by the user who started the session.</span></span> <span data-ttu-id="53a24-169">有关更多详细信息，请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="53a24-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-171">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="53a24-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="53a24-172">启动会话的用户使用的客户端的类别名称。</span><span class="sxs-lookup"><span data-stu-id="53a24-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-174">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="53a24-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="53a24-175">加入会话的用户使用的客户端的版本。</span><span class="sxs-lookup"><span data-stu-id="53a24-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-176"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-177">int</span><span class="sxs-lookup"><span data-stu-id="53a24-177">int</span></span></p></td>
<td><p><span data-ttu-id="53a24-178">加入会话的用户使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="53a24-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="53a24-179">有关更多详细信息，请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="53a24-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-181">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="53a24-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="53a24-182">加入会话的用户使用的客户端的类别名称。</span><span class="sxs-lookup"><span data-stu-id="53a24-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-184">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="53a24-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="53a24-185">会话的目标用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="53a24-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-187">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="53a24-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="53a24-188">会话的目标用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="53a24-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="53a24-189">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="53a24-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-191">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="53a24-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="53a24-192">代表启动会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="53a24-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-194">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="53a24-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="53a24-195">代表启动会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="53a24-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="53a24-196">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="53a24-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-198">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="53a24-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="53a24-199">代表启动会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="53a24-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="53a24-200">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="53a24-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-202">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="53a24-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="53a24-203">提交会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="53a24-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-205">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="53a24-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="53a24-206">提交会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="53a24-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="53a24-207">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="53a24-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-209">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="53a24-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="53a24-210">提交会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="53a24-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="53a24-211">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="53a24-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-213">varchar （775）</span><span class="sxs-lookup"><span data-stu-id="53a24-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="53a24-p116">SIP 对话 ID。格式为：</span><span class="sxs-lookup"><span data-stu-id="53a24-p116">SIP dialog ID. The format is:</span></span></p>
<p><span data-ttu-id="53a24-216">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="53a24-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-217"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-218">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="53a24-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="53a24-219">用于关联多个会话的 GUID。</span><span class="sxs-lookup"><span data-stu-id="53a24-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-221">datetime</span><span class="sxs-lookup"><span data-stu-id="53a24-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="53a24-222">由会话取代的对话的时间。</span><span class="sxs-lookup"><span data-stu-id="53a24-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="53a24-223">与 ReplaceDialogIdSeq 结合起来使用，以唯一地标识由此会话取代的对话。</span><span class="sxs-lookup"><span data-stu-id="53a24-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="53a24-224">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="53a24-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-226">int</span><span class="sxs-lookup"><span data-stu-id="53a24-226">int</span></span></p></td>
<td><p><span data-ttu-id="53a24-227">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="53a24-227">ID number to identify the session.</span></span> <span data-ttu-id="53a24-228">与 ReplacesDialogIdTime 结合使用来唯一地标识由该会话取代的会话。</span><span class="sxs-lookup"><span data-stu-id="53a24-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="53a24-229">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="53a24-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-231">varchar （775）</span><span class="sxs-lookup"><span data-stu-id="53a24-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="53a24-p119">会话取代的 SIP 对话 ID。格式为：</span><span class="sxs-lookup"><span data-stu-id="53a24-p119">SIP dialog ID the session replaces. The format is:</span></span></p>
<p><span data-ttu-id="53a24-234">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="53a24-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-236">datetime</span><span class="sxs-lookup"><span data-stu-id="53a24-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="53a24-p120">对第一个 INVITE 消息的响应时间。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="53a24-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-241">int</span><span class="sxs-lookup"><span data-stu-id="53a24-241">int</span></span></p></td>
<td><p><span data-ttu-id="53a24-p121">会话邀请的 SIP 响应代码。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="53a24-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-245"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-246">int</span><span class="sxs-lookup"><span data-stu-id="53a24-246">int</span></span></p></td>
<td><p><span data-ttu-id="53a24-247">从 SIP 标头捕获的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="53a24-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-249">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="53a24-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="53a24-250">会话内容的类型。</span><span class="sxs-lookup"><span data-stu-id="53a24-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-251"><strong>前端</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-252">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="53a24-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="53a24-253">捕获会话数据的前端服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="53a24-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-255">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="53a24-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="53a24-256">捕获会话数据的池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="53a24-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-258">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="53a24-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="53a24-259">启动会话的用户使用的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="53a24-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-261">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="53a24-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="53a24-262">启动会话的用户使用的边缘服务器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="53a24-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-264">位</span><span class="sxs-lookup"><span data-stu-id="53a24-264">bit</span></span></p></td>
<td><p><span data-ttu-id="53a24-265">指示启动会话的用户是否从内部网络登录。</span><span class="sxs-lookup"><span data-stu-id="53a24-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-267">位</span><span class="sxs-lookup"><span data-stu-id="53a24-267">bit</span></span></p></td>
<td><p><span data-ttu-id="53a24-268">指示加入会话的用户是否从内部网络登录。</span><span class="sxs-lookup"><span data-stu-id="53a24-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-270">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="53a24-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="53a24-271">会话的呼叫属性。</span><span class="sxs-lookup"><span data-stu-id="53a24-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-273">smallint</span><span class="sxs-lookup"><span data-stu-id="53a24-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="53a24-p122">指示启动会话的用户的属性。允许以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="53a24-p122">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="53a24-276">0x01 - 与桌面电话集成</span><span class="sxs-lookup"><span data-stu-id="53a24-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-278">smallint</span><span class="sxs-lookup"><span data-stu-id="53a24-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="53a24-p123">指示启动会话的用户的属性。允许以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="53a24-p123">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="53a24-281">0x01 - 与桌面电话集成</span><span class="sxs-lookup"><span data-stu-id="53a24-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53a24-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-283">smallint</span><span class="sxs-lookup"><span data-stu-id="53a24-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="53a24-p124">指示呼叫属性。允许以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="53a24-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="53a24-286">0x01 - 重试会话</span><span class="sxs-lookup"><span data-stu-id="53a24-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="53a24-287">0x02 - 代表响应组的代理进行的呼叫</span><span class="sxs-lookup"><span data-stu-id="53a24-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53a24-288"><strong>Location</strong></span><span class="sxs-lookup"><span data-stu-id="53a24-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="53a24-289">varchar （max）</span><span class="sxs-lookup"><span data-stu-id="53a24-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="53a24-290">紧急呼叫的位置。</span><span class="sxs-lookup"><span data-stu-id="53a24-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

