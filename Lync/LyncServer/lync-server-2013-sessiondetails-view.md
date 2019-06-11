---
title: 'Lync Server 2013: SessionDetails 视图'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: SessionDetails view
ms:assetid: ea328c6f-cf22-48dd-8f7f-f1666c9148c8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721924(v=OCS.15)
ms:contentKeyID: 49733859
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4bd3902fd35679366e905c04e99ff1e72b2ece86
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822088"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="9832d-102">Lync Server 2013 中的 SessionDetails 视图</span><span class="sxs-lookup"><span data-stu-id="9832d-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9832d-103">_**主题上次修改时间:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9832d-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9832d-104">SessionDetails 视图存储有关对等会话的信息, 这些会话可能是 VoIP-VoIP 电话呼叫、两方 IM 会话或其他类型的会话。</span><span class="sxs-lookup"><span data-stu-id="9832d-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="9832d-105">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="9832d-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9832d-106">列</span><span class="sxs-lookup"><span data-stu-id="9832d-106">Column</span></span></th>
<th><span data-ttu-id="9832d-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="9832d-107">Data Type</span></span></th>
<th><span data-ttu-id="9832d-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="9832d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9832d-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-110">datetime</span><span class="sxs-lookup"><span data-stu-id="9832d-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="9832d-111">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="9832d-111">Time of session request.</span></span> <span data-ttu-id="9832d-112">与 SessionIdSeq 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="9832d-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="9832d-113">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 表中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="9832d-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-115">int</span><span class="sxs-lookup"><span data-stu-id="9832d-115">int</span></span></p></td>
<td><p><span data-ttu-id="9832d-116">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="9832d-116">ID number to identify the session.</span></span> <span data-ttu-id="9832d-117">与 SessionIdTime 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="9832d-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="9832d-118">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="9832d-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-119"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-120">datetime</span><span class="sxs-lookup"><span data-stu-id="9832d-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="9832d-121">第一次邀请请求的时间。</span><span class="sxs-lookup"><span data-stu-id="9832d-121">Time of the first INVITE request.</span></span> <span data-ttu-id="9832d-122">此字段通常由会话中的初始邀请消息所生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="9832d-122">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="9832d-123">如果没有邀请消息, 则该字段将填充第一个相关 SIP 邮件的日期和时间 (再见、取消、消息或信息)。</span><span class="sxs-lookup"><span data-stu-id="9832d-123">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="9832d-124">此字段通常由会话中的初始邀请消息所生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="9832d-124">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="9832d-125">如果没有邀请消息, 则该字段将填充第一个相关 SIP 邮件的日期和时间 (再见、取消、消息或信息)。</span><span class="sxs-lookup"><span data-stu-id="9832d-125">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-127">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9832d-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9832d-128">启动会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="9832d-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-129"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-130">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9832d-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9832d-131">加入会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="9832d-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-133">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9832d-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9832d-134">启动会话的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="9832d-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="9832d-135">有关详细信息, 请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="9832d-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9832d-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9832d-138">加入会话的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="9832d-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="9832d-139">有关详细信息, 请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="9832d-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-141">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9832d-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9832d-142">启动会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="9832d-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="9832d-143">有关详细信息, 请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="9832d-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-144"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-145">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9832d-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9832d-146">加入会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="9832d-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="9832d-147">有关详细信息, 请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="9832d-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-149">标识符</span><span class="sxs-lookup"><span data-stu-id="9832d-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9832d-150">启动会话的用户的终结点的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="9832d-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-151"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-152">标识符</span><span class="sxs-lookup"><span data-stu-id="9832d-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9832d-153">加入会话的用户的终结点的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="9832d-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-155">datetime</span><span class="sxs-lookup"><span data-stu-id="9832d-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="9832d-156">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="9832d-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-158">int</span><span class="sxs-lookup"><span data-stu-id="9832d-158">int</span></span></p></td>
<td><p><span data-ttu-id="9832d-159">启动会话的用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="9832d-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-161">int</span><span class="sxs-lookup"><span data-stu-id="9832d-161">int</span></span></p></td>
<td><p><span data-ttu-id="9832d-162">加入会话的用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="9832d-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-164">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9832d-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9832d-165">启动会话的用户所使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="9832d-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-167">int</span><span class="sxs-lookup"><span data-stu-id="9832d-167">int</span></span></p></td>
<td><p><span data-ttu-id="9832d-168">启动会话的用户所使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="9832d-168">Client used by the user who started the session.</span></span> <span data-ttu-id="9832d-169">有关详细信息, 请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="9832d-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-171">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9832d-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="9832d-172">启动会话的用户所使用的客户端类别的名称。</span><span class="sxs-lookup"><span data-stu-id="9832d-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-174">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9832d-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9832d-175">加入会话的用户使用的客户端版本</span><span class="sxs-lookup"><span data-stu-id="9832d-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-176"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-177">int</span><span class="sxs-lookup"><span data-stu-id="9832d-177">int</span></span></p></td>
<td><p><span data-ttu-id="9832d-178">加入会话的用户所使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="9832d-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="9832d-179">有关详细信息, 请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="9832d-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-181">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9832d-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="9832d-182">加入会话的用户所使用的客户端类别的名称。</span><span class="sxs-lookup"><span data-stu-id="9832d-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-184">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9832d-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9832d-185">会话的目标用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="9832d-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-187">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9832d-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9832d-188">会话的目标用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="9832d-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="9832d-189">有关详细信息, 请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="9832d-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-191">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9832d-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9832d-192">已代表其启动会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="9832d-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9832d-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9832d-195">已代表其启动会话的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="9832d-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="9832d-196">有关详细信息, 请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="9832d-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9832d-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9832d-199">其代表启动会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="9832d-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="9832d-200">有关详细信息, 请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="9832d-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-202">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9832d-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9832d-203">引用会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="9832d-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-205">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9832d-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9832d-206">引用会话的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="9832d-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="9832d-207">有关详细信息, 请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="9832d-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-209">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9832d-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9832d-210">引用会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="9832d-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="9832d-211">有关详细信息, 请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="9832d-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-213">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="9832d-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="9832d-214">SIP 对话框 ID。</span><span class="sxs-lookup"><span data-stu-id="9832d-214">SIP dialog ID.</span></span> <span data-ttu-id="9832d-215">格式为:</span><span class="sxs-lookup"><span data-stu-id="9832d-215">The format is:</span></span></p>
<p><span data-ttu-id="9832d-216">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="9832d-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-217"><strong>True&correlationid</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-218">标识符</span><span class="sxs-lookup"><span data-stu-id="9832d-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9832d-219">用于关联多个会话的 GUID。</span><span class="sxs-lookup"><span data-stu-id="9832d-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-221">datetime</span><span class="sxs-lookup"><span data-stu-id="9832d-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="9832d-222">会话替换的对话的时间。</span><span class="sxs-lookup"><span data-stu-id="9832d-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="9832d-223">与 ReplaceDialogIdSeq 结合使用以唯一标识由会话替换的对话框。</span><span class="sxs-lookup"><span data-stu-id="9832d-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="9832d-224">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="9832d-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-226">int</span><span class="sxs-lookup"><span data-stu-id="9832d-226">int</span></span></p></td>
<td><p><span data-ttu-id="9832d-227">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="9832d-227">ID number to identify the session.</span></span> <span data-ttu-id="9832d-228">与 ReplaceDialogIdTime 结合使用以唯一标识由会话替换的对话框。</span><span class="sxs-lookup"><span data-stu-id="9832d-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="9832d-229">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="9832d-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-231">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="9832d-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="9832d-232">会话将替换的 SIP 对话框 ID。</span><span class="sxs-lookup"><span data-stu-id="9832d-232">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="9832d-233">格式为:</span><span class="sxs-lookup"><span data-stu-id="9832d-233">The format is:</span></span></p>
<p><span data-ttu-id="9832d-234">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="9832d-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-236">datetime</span><span class="sxs-lookup"><span data-stu-id="9832d-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="9832d-237">对第一个邀请消息的答复时间。</span><span class="sxs-lookup"><span data-stu-id="9832d-237">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="9832d-238">此字段通常由会话中的初始邀请消息所生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="9832d-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="9832d-239">如果没有邀请消息, 则该字段将填充第一个相关 SIP 邮件的日期和时间 (再见、取消、消息或信息)。</span><span class="sxs-lookup"><span data-stu-id="9832d-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-241">int</span><span class="sxs-lookup"><span data-stu-id="9832d-241">int</span></span></p></td>
<td><p><span data-ttu-id="9832d-242">会议邀请的 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="9832d-242">SIP response code to the session invitation.</span></span> <span data-ttu-id="9832d-243">此字段通常由会话中的初始邀请消息所生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="9832d-243">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="9832d-244">如果没有邀请消息, 则该字段将填充第一个相关 SIP 邮件的日期和时间 (再见、取消、消息或信息)。</span><span class="sxs-lookup"><span data-stu-id="9832d-244">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-245"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-246">int</span><span class="sxs-lookup"><span data-stu-id="9832d-246">int</span></span></p></td>
<td><p><span data-ttu-id="9832d-247">从 SIP 标题捕获的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="9832d-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-249">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9832d-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9832d-250">会话的内容类型。</span><span class="sxs-lookup"><span data-stu-id="9832d-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-252">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9832d-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9832d-253">捕获会话的数据的前端服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9832d-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-255">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9832d-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9832d-256">捕获会话的数据的池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9832d-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-258">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9832d-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9832d-259">启动会话的用户所使用的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9832d-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-261">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9832d-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9832d-262">启动会话的用户所使用的边缘服务器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="9832d-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-264">bit</span><span class="sxs-lookup"><span data-stu-id="9832d-264">bit</span></span></p></td>
<td><p><span data-ttu-id="9832d-265">指示启动会话的用户是否从内部网络登录。</span><span class="sxs-lookup"><span data-stu-id="9832d-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-267">bit</span><span class="sxs-lookup"><span data-stu-id="9832d-267">bit</span></span></p></td>
<td><p><span data-ttu-id="9832d-268">指示加入会话的用户是否从内部网络登录。</span><span class="sxs-lookup"><span data-stu-id="9832d-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-270">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9832d-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9832d-271">会话的调用优先级。</span><span class="sxs-lookup"><span data-stu-id="9832d-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-273">smallint</span><span class="sxs-lookup"><span data-stu-id="9832d-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="9832d-274">指示启动会话的用户的属性。</span><span class="sxs-lookup"><span data-stu-id="9832d-274">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="9832d-275">允许以下属性定义:</span><span class="sxs-lookup"><span data-stu-id="9832d-275">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="9832d-276">0x01-与桌面电话集成</span><span class="sxs-lookup"><span data-stu-id="9832d-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-278">smallint</span><span class="sxs-lookup"><span data-stu-id="9832d-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="9832d-279">指示启动会话的用户的属性。</span><span class="sxs-lookup"><span data-stu-id="9832d-279">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="9832d-280">允许以下属性定义:</span><span class="sxs-lookup"><span data-stu-id="9832d-280">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="9832d-281">0x01-与桌面电话集成</span><span class="sxs-lookup"><span data-stu-id="9832d-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9832d-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-283">smallint</span><span class="sxs-lookup"><span data-stu-id="9832d-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="9832d-284">指示通话属性。</span><span class="sxs-lookup"><span data-stu-id="9832d-284">Indicates the call attributes.</span></span> <span data-ttu-id="9832d-285">允许以下属性定义:</span><span class="sxs-lookup"><span data-stu-id="9832d-285">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="9832d-286">0x01-重试会话</span><span class="sxs-lookup"><span data-stu-id="9832d-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="9832d-287">0x02-代表响应组的代理发出的呼叫</span><span class="sxs-lookup"><span data-stu-id="9832d-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9832d-288"><strong>位置</strong></span><span class="sxs-lookup"><span data-stu-id="9832d-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="9832d-289">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="9832d-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="9832d-290">紧急电话的位置。</span><span class="sxs-lookup"><span data-stu-id="9832d-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

