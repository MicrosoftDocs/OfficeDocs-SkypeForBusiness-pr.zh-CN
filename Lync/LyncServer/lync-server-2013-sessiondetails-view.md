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
ms.openlocfilehash: fabf7ae963240f6a2b14ac8c3db272e0cb06091c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764708"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="sessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="34e1b-102">Lync Server 2013 中的 SessionDetails 视图</span><span class="sxs-lookup"><span data-stu-id="34e1b-102">SessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34e1b-103">_**主题上次修改时间：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="34e1b-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="34e1b-104">SessionDetails 视图存储有关对等会话的信息，这些会话可能是 VoIP-VoIP 电话呼叫、两方 IM 会话或其他类型的会话。</span><span class="sxs-lookup"><span data-stu-id="34e1b-104">The SessionDetails view stores information about peer-to-peer sessions, which could be a VoIP-VoIP phone call, two-party IM session, or other type of session.</span></span> <span data-ttu-id="34e1b-105">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="34e1b-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="34e1b-106">列</span><span class="sxs-lookup"><span data-stu-id="34e1b-106">Column</span></span></th>
<th><span data-ttu-id="34e1b-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="34e1b-107">Data Type</span></span></th>
<th><span data-ttu-id="34e1b-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="34e1b-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-110">datetime</span><span class="sxs-lookup"><span data-stu-id="34e1b-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="34e1b-111">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="34e1b-111">Time of session request.</span></span> <span data-ttu-id="34e1b-112">与 SessionIdSeq 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="34e1b-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="34e1b-113">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 表中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="34e1b-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-115">int</span><span class="sxs-lookup"><span data-stu-id="34e1b-115">int</span></span></p></td>
<td><p><span data-ttu-id="34e1b-116">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="34e1b-116">ID number to identify the session.</span></span> <span data-ttu-id="34e1b-117">与 SessionIdTime 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="34e1b-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="34e1b-118">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="34e1b-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-119"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-119"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-120">datetime</span><span class="sxs-lookup"><span data-stu-id="34e1b-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="34e1b-121">第一次邀请请求的时间。</span><span class="sxs-lookup"><span data-stu-id="34e1b-121">Time of the first INVITE request.</span></span> <span data-ttu-id="34e1b-122">此字段通常由会话中的初始邀请消息所生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="34e1b-122">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="34e1b-123">如果没有邀请消息，则该字段将填充第一个相关 SIP 邮件的日期和时间（再见、取消、消息或信息）。</span><span class="sxs-lookup"><span data-stu-id="34e1b-123">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span> <span data-ttu-id="34e1b-124">此字段通常由会话中的初始邀请消息所生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="34e1b-124">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="34e1b-125">如果没有邀请消息，则该字段将填充第一个相关 SIP 邮件的日期和时间（再见、取消、消息或信息）。</span><span class="sxs-lookup"><span data-stu-id="34e1b-125">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-126"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-126"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-127">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="34e1b-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-128">启动会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="34e1b-128">URI of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-129"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-129"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-130">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="34e1b-130">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-131">加入会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="34e1b-131">URI of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-132"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-132"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-133">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34e1b-133">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-134">启动会话的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="34e1b-134">Type of URI of the user who started the session.</span></span> <span data-ttu-id="34e1b-135">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="34e1b-135">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34e1b-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-138">加入会话的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="34e1b-138">Type of URI of the user who joined the session.</span></span> <span data-ttu-id="34e1b-139">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="34e1b-139">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-140"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-140"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-141">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="34e1b-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-142">启动会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="34e1b-142">Tenant of the user who started the session.</span></span> <span data-ttu-id="34e1b-143">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="34e1b-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-144"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-144"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-145">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34e1b-145">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-146">加入会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="34e1b-146">The tenant of the user who joined the session.</span></span> <span data-ttu-id="34e1b-147">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="34e1b-147">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-148"><strong>FromEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-148"><strong>FromEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-149">标识符</span><span class="sxs-lookup"><span data-stu-id="34e1b-149">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="34e1b-150">启动会话的用户的终结点的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="34e1b-150">Unique identifier of the endpoint of the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-151"><strong>ToEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-151"><strong>ToEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-152">标识符</span><span class="sxs-lookup"><span data-stu-id="34e1b-152">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="34e1b-153">加入会话的用户的终结点的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="34e1b-153">Unique identifier of the endpoint of the user who joined the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-154"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-154"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-155">datetime</span><span class="sxs-lookup"><span data-stu-id="34e1b-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="34e1b-156">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="34e1b-156">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-157"><strong>FromMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-157"><strong>FromMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-158">int</span><span class="sxs-lookup"><span data-stu-id="34e1b-158">int</span></span></p></td>
<td><p><span data-ttu-id="34e1b-159">启动会话的用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="34e1b-159">Number of messages sent by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-160"><strong>ToMessageCount</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-160"><strong>ToMessageCount</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-161">int</span><span class="sxs-lookup"><span data-stu-id="34e1b-161">int</span></span></p></td>
<td><p><span data-ttu-id="34e1b-162">加入会话的用户发送的消息数。</span><span class="sxs-lookup"><span data-stu-id="34e1b-162">Number of messages sent by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-163"><strong>FromClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-163"><strong>FromClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-164">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34e1b-164">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-165">启动会话的用户所使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="34e1b-165">Version of client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-166"><strong>FromClientType</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-166"><strong>FromClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-167">int</span><span class="sxs-lookup"><span data-stu-id="34e1b-167">int</span></span></p></td>
<td><p><span data-ttu-id="34e1b-168">启动会话的用户所使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="34e1b-168">Client used by the user who started the session.</span></span> <span data-ttu-id="34e1b-169">有关详细信息，请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="34e1b-169">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-170"><strong>FromClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-170"><strong>FromClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-171">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="34e1b-171">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-172">启动会话的用户所使用的客户端类别的名称。</span><span class="sxs-lookup"><span data-stu-id="34e1b-172">Name of the category of the client used by the user who started the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-173"><strong>ToClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-173"><strong>ToClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-174">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34e1b-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-175">加入会话的用户使用的客户端版本</span><span class="sxs-lookup"><span data-stu-id="34e1b-175">Version of client used by the user who joined the session</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-176"><strong>ToClientType</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-176"><strong>ToClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-177">int</span><span class="sxs-lookup"><span data-stu-id="34e1b-177">int</span></span></p></td>
<td><p><span data-ttu-id="34e1b-178">加入会话的用户所使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="34e1b-178">Client used by the user who joined the session.</span></span> <span data-ttu-id="34e1b-179">有关详细信息，请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="34e1b-179">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-180"><strong>ToClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-180"><strong>ToClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-181">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="34e1b-181">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-182">加入会话的用户所使用的客户端类别的名称。</span><span class="sxs-lookup"><span data-stu-id="34e1b-182">Name of the category of the client used by the user who joined the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-183"><strong>TargetUri</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-183"><strong>TargetUri</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-184">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="34e1b-184">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-185">会话的目标用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="34e1b-185">URI of the target user of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-186"><strong>TargetUriType</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-186"><strong>TargetUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-187">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="34e1b-187">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-188">会话的目标用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="34e1b-188">Type of URI of the target user for the session.</span></span> <span data-ttu-id="34e1b-189">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="34e1b-189">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-190"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-190"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-191">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="34e1b-191">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-192">已代表其启动会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="34e1b-192">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-193"><strong>OnnnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-193"><strong>OnnnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34e1b-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-195">已代表其启动会话的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="34e1b-195">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="34e1b-196">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="34e1b-196">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-197"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-197"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34e1b-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-199">其代表启动会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="34e1b-199">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="34e1b-200">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="34e1b-200">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-201"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-201"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-202">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="34e1b-202">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-203">引用会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="34e1b-203">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-204"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-204"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-205">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34e1b-205">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-206">引用会话的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="34e1b-206">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="34e1b-207">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="34e1b-207">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-208"><strong>ReferredByTenant</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-208"><strong>ReferredByTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-209">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34e1b-209">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-210">引用会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="34e1b-210">Tenant of the user who referred the session.</span></span> <span data-ttu-id="34e1b-211">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="34e1b-211">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-212"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-212"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-213">varchar （775）</span><span class="sxs-lookup"><span data-stu-id="34e1b-213">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-214">SIP 对话框 ID。</span><span class="sxs-lookup"><span data-stu-id="34e1b-214">SIP dialog ID.</span></span> <span data-ttu-id="34e1b-215">格式为：</span><span class="sxs-lookup"><span data-stu-id="34e1b-215">The format is:</span></span></p>
<p><span data-ttu-id="34e1b-216">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="34e1b-216">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-217"><strong>True&correlationid</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-217"><strong>CorrelationId</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-218">标识符</span><span class="sxs-lookup"><span data-stu-id="34e1b-218">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="34e1b-219">用于关联多个会话的 GUID。</span><span class="sxs-lookup"><span data-stu-id="34e1b-219">GUID used to correlate multiple sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-220"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-220"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-221">datetime</span><span class="sxs-lookup"><span data-stu-id="34e1b-221">datetime</span></span></p></td>
<td><p><span data-ttu-id="34e1b-222">会话替换的对话的时间。</span><span class="sxs-lookup"><span data-stu-id="34e1b-222">Time of the dialog which was replaced by the session.</span></span> <span data-ttu-id="34e1b-223">与 ReplaceDialogIdSeq 结合使用以唯一标识由会话替换的对话框。</span><span class="sxs-lookup"><span data-stu-id="34e1b-223">Used in conjunction with ReplaceDialogIdSeq to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="34e1b-224">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="34e1b-224">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-225"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-225"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-226">int</span><span class="sxs-lookup"><span data-stu-id="34e1b-226">int</span></span></p></td>
<td><p><span data-ttu-id="34e1b-227">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="34e1b-227">ID number to identify the session.</span></span> <span data-ttu-id="34e1b-228">与 ReplaceDialogIdTime 结合使用以唯一标识由会话替换的对话框。</span><span class="sxs-lookup"><span data-stu-id="34e1b-228">Used in conjunction with ReplaceDialogIdTime to uniquely identify a dialog that is replaced by the session.</span></span> <span data-ttu-id="34e1b-229">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="34e1b-229">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-230"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-230"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-231">varchar （775）</span><span class="sxs-lookup"><span data-stu-id="34e1b-231">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-232">会话将替换的 SIP 对话框 ID。</span><span class="sxs-lookup"><span data-stu-id="34e1b-232">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="34e1b-233">格式为：</span><span class="sxs-lookup"><span data-stu-id="34e1b-233">The format is:</span></span></p>
<p><span data-ttu-id="34e1b-234">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="34e1b-234">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-235"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-235"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-236">datetime</span><span class="sxs-lookup"><span data-stu-id="34e1b-236">datetime</span></span></p></td>
<td><p><span data-ttu-id="34e1b-237">对第一个邀请消息的答复时间。</span><span class="sxs-lookup"><span data-stu-id="34e1b-237">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="34e1b-238">此字段通常由会话中的初始邀请消息所生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="34e1b-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="34e1b-239">如果没有邀请消息，则该字段将填充第一个相关 SIP 邮件的日期和时间（再见、取消、消息或信息）。</span><span class="sxs-lookup"><span data-stu-id="34e1b-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-240"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-240"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-241">int</span><span class="sxs-lookup"><span data-stu-id="34e1b-241">int</span></span></p></td>
<td><p><span data-ttu-id="34e1b-242">会议邀请的 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="34e1b-242">SIP response code to the session invitation.</span></span> <span data-ttu-id="34e1b-243">此字段通常由会话中的初始邀请消息所生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="34e1b-243">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="34e1b-244">如果没有邀请消息，则该字段将填充第一个相关 SIP 邮件的日期和时间（再见、取消、消息或信息）。</span><span class="sxs-lookup"><span data-stu-id="34e1b-244">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-245"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-245"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-246">int</span><span class="sxs-lookup"><span data-stu-id="34e1b-246">int</span></span></p></td>
<td><p><span data-ttu-id="34e1b-247">从 SIP 标题捕获的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="34e1b-247">Diagnostic ID captured from SIP headers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-248"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-248"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-249">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34e1b-249">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-250">会话的内容类型。</span><span class="sxs-lookup"><span data-stu-id="34e1b-250">Type of content for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-251"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-251"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-252">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34e1b-252">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-253">捕获会话的数据的前端服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="34e1b-253">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-254"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-254"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-255">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34e1b-255">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-256">捕获会话的数据的池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="34e1b-256">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-257"><strong>FromEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-257"><strong>FromEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-258">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34e1b-258">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-259">启动会话的用户所使用的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="34e1b-259">FQDN of the Edge server used by the user who started the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-260"><strong>ToEdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-260"><strong>ToEdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-261">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34e1b-261">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-262">启动会话的用户所使用的边缘服务器的 FQDN</span><span class="sxs-lookup"><span data-stu-id="34e1b-262">FQDN of the Edge server used by the user who started the session</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-263"><strong>IsFromInternal</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-263"><strong>IsFromInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-264">bit</span><span class="sxs-lookup"><span data-stu-id="34e1b-264">bit</span></span></p></td>
<td><p><span data-ttu-id="34e1b-265">指示启动会话的用户是否从内部网络登录。</span><span class="sxs-lookup"><span data-stu-id="34e1b-265">Indicates whether the user who started the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-266"><strong>IsToInternal</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-266"><strong>IsToInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-267">bit</span><span class="sxs-lookup"><span data-stu-id="34e1b-267">bit</span></span></p></td>
<td><p><span data-ttu-id="34e1b-268">指示加入会话的用户是否从内部网络登录。</span><span class="sxs-lookup"><span data-stu-id="34e1b-268">Indicates whether the user who joined the session logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-269"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-269"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-270">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="34e1b-270">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-271">会话的调用优先级。</span><span class="sxs-lookup"><span data-stu-id="34e1b-271">Call priority of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-272"><strong>FromUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-272"><strong>FromUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-273">smallint</span><span class="sxs-lookup"><span data-stu-id="34e1b-273">smallint</span></span></p></td>
<td><p><span data-ttu-id="34e1b-274">指示启动会话的用户的属性。</span><span class="sxs-lookup"><span data-stu-id="34e1b-274">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="34e1b-275">允许以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="34e1b-275">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="34e1b-276">0x01-与桌面电话集成</span><span class="sxs-lookup"><span data-stu-id="34e1b-276">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-277"><strong>ToUserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-277"><strong>ToUserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-278">smallint</span><span class="sxs-lookup"><span data-stu-id="34e1b-278">smallint</span></span></p></td>
<td><p><span data-ttu-id="34e1b-279">指示启动会话的用户的属性。</span><span class="sxs-lookup"><span data-stu-id="34e1b-279">Indicates the attributes of the user who started the session.</span></span> <span data-ttu-id="34e1b-280">允许以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="34e1b-280">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="34e1b-281">0x01-与桌面电话集成</span><span class="sxs-lookup"><span data-stu-id="34e1b-281">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="34e1b-282"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-282"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-283">smallint</span><span class="sxs-lookup"><span data-stu-id="34e1b-283">smallint</span></span></p></td>
<td><p><span data-ttu-id="34e1b-284">指示通话属性。</span><span class="sxs-lookup"><span data-stu-id="34e1b-284">Indicates the call attributes.</span></span> <span data-ttu-id="34e1b-285">允许以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="34e1b-285">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="34e1b-286">0x01-重试会话</span><span class="sxs-lookup"><span data-stu-id="34e1b-286">0x01 - Retried Session</span></span></p>
<p><span data-ttu-id="34e1b-287">0x02-代表响应组的代理发出的呼叫</span><span class="sxs-lookup"><span data-stu-id="34e1b-287">0x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="34e1b-288"><strong>位置</strong></span><span class="sxs-lookup"><span data-stu-id="34e1b-288"><strong>Location</strong></span></span></p></td>
<td><p><span data-ttu-id="34e1b-289">varchar （max）</span><span class="sxs-lookup"><span data-stu-id="34e1b-289">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="34e1b-290">紧急电话的位置。</span><span class="sxs-lookup"><span data-stu-id="34e1b-290">Location of emergency call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

