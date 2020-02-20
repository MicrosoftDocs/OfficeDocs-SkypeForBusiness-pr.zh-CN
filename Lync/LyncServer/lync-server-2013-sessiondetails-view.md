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
ms.openlocfilehash: 3f7a143a0812b19a840c7eb339e80611720a08b3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42143786"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="ccba5-102">Lync Server 2013 中的 SessionDetails 视图</span><span class="sxs-lookup"><span data-stu-id="ccba5-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ccba5-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ccba5-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ccba5-104">SessionDetails 视图存储有关点对点会话的信息，这应该是 VoIP-VoIP 电话呼叫、双方 IM 会话或其他类型的会话。</span><span class="sxs-lookup"><span data-stu-id="ccba5-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="ccba5-105">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ccba5-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ccba5-106">列</span><span class="sxs-lookup"><span data-stu-id="ccba5-106">Column</span></span></th>
<th><span data-ttu-id="ccba5-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="ccba5-107">Data Type</span></span></th>
<th><span data-ttu-id="ccba5-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="ccba5-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-110">datetime</span><span class="sxs-lookup"><span data-stu-id="ccba5-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="ccba5-111">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="ccba5-111">Time of session request.</span></span> <span data-ttu-id="ccba5-112">与 SessionIdSeq 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="ccba5-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="ccba5-113">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 表中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="ccba5-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-115">int</span><span class="sxs-lookup"><span data-stu-id="ccba5-115">int</span></span></p></td>
<td><p><span data-ttu-id="ccba5-116">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="ccba5-116">ID number to identify the session.</span></span> <span data-ttu-id="ccba5-117">与 SessionIdTime 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="ccba5-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="ccba5-118">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="ccba5-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-119"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-120">datetime</span><span class="sxs-lookup"><span data-stu-id="ccba5-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="ccba5-p104">第一个 INVITE 请求的时间。此字段通常由从会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="ccba5-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO). This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-127">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="ccba5-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-128">启动会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="ccba5-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-129"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-130">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="ccba5-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-131">加入会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="ccba5-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-133">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ccba5-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-134">启动会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="ccba5-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="ccba5-135">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ccba5-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-137">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ccba5-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-138">加入会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="ccba5-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="ccba5-139">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ccba5-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-141">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="ccba5-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-142">启动会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="ccba5-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="ccba5-143">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="ccba5-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-144"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-145">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ccba5-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-146">加入会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="ccba5-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="ccba5-147">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="ccba5-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-149">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="ccba5-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ccba5-150">启动会话的用户的终结点的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="ccba5-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-151"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-152">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="ccba5-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ccba5-153">加入会话的用户的终结点的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="ccba5-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-155">datetime</span><span class="sxs-lookup"><span data-stu-id="ccba5-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="ccba5-156">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="ccba5-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-158">int</span><span class="sxs-lookup"><span data-stu-id="ccba5-158">int</span></span></p></td>
<td><p><span data-ttu-id="ccba5-159">启动会话的用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="ccba5-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-161">int</span><span class="sxs-lookup"><span data-stu-id="ccba5-161">int</span></span></p></td>
<td><p><span data-ttu-id="ccba5-162">加入会话的用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="ccba5-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-164">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ccba5-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-165">启动会话的用户使用的客户端的版本。</span><span class="sxs-lookup"><span data-stu-id="ccba5-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-167">int</span><span class="sxs-lookup"><span data-stu-id="ccba5-167">int</span></span></p></td>
<td><p><span data-ttu-id="ccba5-168">启动会话的用户使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="ccba5-168">Client used by the user who started the session.</span></span> <span data-ttu-id="ccba5-169">有关更多详细信息，请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ccba5-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-171">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="ccba5-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-172">启动会话的用户使用的客户端的类别名称。</span><span class="sxs-lookup"><span data-stu-id="ccba5-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-174">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ccba5-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-175">加入会话的用户使用的客户端的版本。</span><span class="sxs-lookup"><span data-stu-id="ccba5-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-176"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-177">int</span><span class="sxs-lookup"><span data-stu-id="ccba5-177">int</span></span></p></td>
<td><p><span data-ttu-id="ccba5-178">加入会话的用户使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="ccba5-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="ccba5-179">有关更多详细信息，请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ccba5-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-181">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="ccba5-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-182">加入会话的用户使用的客户端的类别名称。</span><span class="sxs-lookup"><span data-stu-id="ccba5-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-184">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="ccba5-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-185">会话的目标用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="ccba5-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-187">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="ccba5-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-188">会话的目标用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="ccba5-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="ccba5-189">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ccba5-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-191">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="ccba5-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-192">代表启动会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="ccba5-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-194">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ccba5-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-195">代表启动会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="ccba5-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="ccba5-196">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ccba5-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-198">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ccba5-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-199">代表启动会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="ccba5-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="ccba5-200">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="ccba5-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-202">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="ccba5-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-203">提交会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="ccba5-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-205">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ccba5-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-206">提交会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="ccba5-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="ccba5-207">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ccba5-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-209">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ccba5-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-210">提交会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="ccba5-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="ccba5-211">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="ccba5-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-213">varchar （775）</span><span class="sxs-lookup"><span data-stu-id="ccba5-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-p116">SIP 对话 ID。格式为：</span><span class="sxs-lookup"><span data-stu-id="ccba5-p116">SIP dialog ID. The format is:</span></span></p>
<p><span data-ttu-id="ccba5-216">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="ccba5-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-217"><strong>CorrelationId</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-218">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="ccba5-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ccba5-219">用于关联多个会话的 GUID。</span><span class="sxs-lookup"><span data-stu-id="ccba5-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-221">datetime</span><span class="sxs-lookup"><span data-stu-id="ccba5-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="ccba5-222">由会话取代的对话的时间。</span><span class="sxs-lookup"><span data-stu-id="ccba5-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="ccba5-223">与 ReplaceDialogIdSeq 结合起来使用，以唯一地标识由此会话取代的对话。</span><span class="sxs-lookup"><span data-stu-id="ccba5-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="ccba5-224">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="ccba5-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-226">int</span><span class="sxs-lookup"><span data-stu-id="ccba5-226">int</span></span></p></td>
<td><p><span data-ttu-id="ccba5-227">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="ccba5-227">ID number to identify the session.</span></span> <span data-ttu-id="ccba5-228">与 ReplacesDialogIdTime 结合使用来唯一地标识由该会话取代的会话。</span><span class="sxs-lookup"><span data-stu-id="ccba5-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="ccba5-229">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="ccba5-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-231">varchar （775）</span><span class="sxs-lookup"><span data-stu-id="ccba5-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-p119">会话取代的 SIP 对话 ID。格式为：</span><span class="sxs-lookup"><span data-stu-id="ccba5-p119">SIP dialog ID the session replaces. The format is:</span></span></p>
<p><span data-ttu-id="ccba5-234">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="ccba5-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-236">datetime</span><span class="sxs-lookup"><span data-stu-id="ccba5-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="ccba5-p120">对第一个 INVITE 消息的响应时间。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="ccba5-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-241">int</span><span class="sxs-lookup"><span data-stu-id="ccba5-241">int</span></span></p></td>
<td><p><span data-ttu-id="ccba5-p121">会话邀请的 SIP 响应代码。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="ccba5-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-245"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-246">int</span><span class="sxs-lookup"><span data-stu-id="ccba5-246">int</span></span></p></td>
<td><p><span data-ttu-id="ccba5-247">从 SIP 标头捕获的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="ccba5-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-249">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ccba5-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-250">会话内容的类型。</span><span class="sxs-lookup"><span data-stu-id="ccba5-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-251"><strong>前端</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-252">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ccba5-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-253">捕获会话数据的前端服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ccba5-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-255">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ccba5-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-256">捕获会话数据的池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ccba5-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-258">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ccba5-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-259">启动会话的用户使用的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ccba5-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-261">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ccba5-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-262">启动会话的用户使用的边缘服务器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="ccba5-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-264">位</span><span class="sxs-lookup"><span data-stu-id="ccba5-264">bit</span></span></p></td>
<td><p><span data-ttu-id="ccba5-265">指示启动会话的用户是否从内部网络登录。</span><span class="sxs-lookup"><span data-stu-id="ccba5-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-267">位</span><span class="sxs-lookup"><span data-stu-id="ccba5-267">bit</span></span></p></td>
<td><p><span data-ttu-id="ccba5-268">指示加入会话的用户是否从内部网络登录。</span><span class="sxs-lookup"><span data-stu-id="ccba5-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-270">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ccba5-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-271">会话的呼叫属性。</span><span class="sxs-lookup"><span data-stu-id="ccba5-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-273">smallint</span><span class="sxs-lookup"><span data-stu-id="ccba5-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="ccba5-p122">指示启动会话的用户的属性。允许以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="ccba5-p122">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="ccba5-276">0x01 - 与桌面电话集成</span><span class="sxs-lookup"><span data-stu-id="ccba5-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-278">smallint</span><span class="sxs-lookup"><span data-stu-id="ccba5-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="ccba5-p123">指示启动会话的用户的属性。允许以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="ccba5-p123">Indicates the attributes of the user who started the session. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="ccba5-281">0x01 - 与桌面电话集成</span><span class="sxs-lookup"><span data-stu-id="ccba5-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ccba5-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-283">smallint</span><span class="sxs-lookup"><span data-stu-id="ccba5-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="ccba5-p124">指示呼叫属性。允许以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="ccba5-p124">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="ccba5-286">0x01 - 重试会话</span><span class="sxs-lookup"><span data-stu-id="ccba5-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="ccba5-287">0x02 - 代表响应组的代理进行的呼叫</span><span class="sxs-lookup"><span data-stu-id="ccba5-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ccba5-288"><strong>Location</strong></span><span class="sxs-lookup"><span data-stu-id="ccba5-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="ccba5-289">varchar （max）</span><span class="sxs-lookup"><span data-stu-id="ccba5-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="ccba5-290">紧急呼叫的位置。</span><span class="sxs-lookup"><span data-stu-id="ccba5-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

