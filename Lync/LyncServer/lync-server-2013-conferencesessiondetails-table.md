---
title: Lync Server 2013： ConferenceSessionDetails 表
description: Lync Server 2013： ConferenceSessionDetails 表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0d101eb1607e366ab814e60acaeee80820fe87c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566778"
---
# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="356f3-103">Lync Server 2013 中的 ConferenceSessionDetails 表</span><span class="sxs-lookup"><span data-stu-id="356f3-103">ConferenceSessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="356f3-104">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="356f3-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="356f3-105">每个记录表示一个会议会话，它可以是具有会议状态中心的会话，也可以是具有特定会议服务器的会话。</span><span class="sxs-lookup"><span data-stu-id="356f3-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="356f3-106">列</span><span class="sxs-lookup"><span data-stu-id="356f3-106">Column</span></span></th>
<th><span data-ttu-id="356f3-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="356f3-107">Data Type</span></span></th>
<th><span data-ttu-id="356f3-108">键/索引</span><span class="sxs-lookup"><span data-stu-id="356f3-108">Key/Index</span></span></th>
<th><span data-ttu-id="356f3-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="356f3-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="356f3-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-111">Datetime</span><span class="sxs-lookup"><span data-stu-id="356f3-111">Datetime</span></span></p></td>
<td><p><span data-ttu-id="356f3-112">主、外</span><span class="sxs-lookup"><span data-stu-id="356f3-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="356f3-113">会话请求的时间；与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会议会话。</span><span class="sxs-lookup"><span data-stu-id="356f3-113">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="356f3-114">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="356f3-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356f3-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-116">int</span><span class="sxs-lookup"><span data-stu-id="356f3-116">int</span></span></p></td>
<td><p><span data-ttu-id="356f3-117">主、外</span><span class="sxs-lookup"><span data-stu-id="356f3-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="356f3-118">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="356f3-118">ID number to identify the session.</span></span> <span data-ttu-id="356f3-119">与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会议会话。</span><span class="sxs-lookup"><span data-stu-id="356f3-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="356f3-120">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="356f3-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356f3-121"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-121"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-122">int</span><span class="sxs-lookup"><span data-stu-id="356f3-122">int</span></span></p></td>
<td><p><span data-ttu-id="356f3-123">对外</span><span class="sxs-lookup"><span data-stu-id="356f3-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="356f3-124">与此会话相关的会议状态中心会议 URI。</span><span class="sxs-lookup"><span data-stu-id="356f3-124">Focus conference URI related to this session.</span></span> <span data-ttu-id="356f3-125">有关详细信息，请参阅 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="356f3-125">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="356f3-126">此 URI 是基于会议状态中心的会议 URI。</span><span class="sxs-lookup"><span data-stu-id="356f3-126">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356f3-127"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-127"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-128">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="356f3-128">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="356f3-129">区分各个定期会议实例的标识符。</span><span class="sxs-lookup"><span data-stu-id="356f3-129">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="356f3-130">每个定期会议实例的 ConferenceURI 都相同，但具有不同的 ConfInstance 值。</span><span class="sxs-lookup"><span data-stu-id="356f3-130">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="356f3-131">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="356f3-131">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356f3-132"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-132"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-133">int</span><span class="sxs-lookup"><span data-stu-id="356f3-133">int</span></span></p></td>
<td><p><span data-ttu-id="356f3-134">对外</span><span class="sxs-lookup"><span data-stu-id="356f3-134">Foreign</span></span></p></td>
<td><p><span data-ttu-id="356f3-135">与此会话相关的会议服务器会议 URI。</span><span class="sxs-lookup"><span data-stu-id="356f3-135">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="356f3-136">有关详细信息，请参阅 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="356f3-136">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="356f3-137">此 URI 是基于会议服务器的会议 URI。</span><span class="sxs-lookup"><span data-stu-id="356f3-137">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="356f3-138">对于会议状态中心会议会话，此列将为 null。</span><span class="sxs-lookup"><span data-stu-id="356f3-138">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356f3-139"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-139"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-140">int</span><span class="sxs-lookup"><span data-stu-id="356f3-140">int</span></span></p></td>
<td><p><span data-ttu-id="356f3-141">对外</span><span class="sxs-lookup"><span data-stu-id="356f3-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="356f3-142">会议会话中的一个用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="356f3-142">ID of one user in the conference session.</span></span> <span data-ttu-id="356f3-143">有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="356f3-143">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356f3-144"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-144"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-145">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="356f3-145">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="356f3-p107">用于标识终结点的实例的 GUID。例如，如果一个用户使用相同帐户登录到不同的计算机上，则每台计算机将具有不同的终结点 ID。</span><span class="sxs-lookup"><span data-stu-id="356f3-p107">A GUID to identify the instance of endpoint. For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356f3-148"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-148"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-149">int</span><span class="sxs-lookup"><span data-stu-id="356f3-149">int</span></span></p></td>
<td><p><span data-ttu-id="356f3-150">对外</span><span class="sxs-lookup"><span data-stu-id="356f3-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="356f3-151">指示呼叫者所代表的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="356f3-151">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="356f3-152">有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="356f3-152">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356f3-153"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-153"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-154">int</span><span class="sxs-lookup"><span data-stu-id="356f3-154">int</span></span></p></td>
<td><p><span data-ttu-id="356f3-155">对外</span><span class="sxs-lookup"><span data-stu-id="356f3-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="356f3-156">引用呼叫的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="356f3-156">ID of the user by who the call is referred.</span></span> <span data-ttu-id="356f3-157">有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="356f3-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356f3-158"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-158"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-159">int</span><span class="sxs-lookup"><span data-stu-id="356f3-159">int</span></span></p></td>
<td><p><span data-ttu-id="356f3-160">对外</span><span class="sxs-lookup"><span data-stu-id="356f3-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="356f3-161">会议用户使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="356f3-161">Client version used by the conference user.</span></span> <span data-ttu-id="356f3-162">有关详细信息，请参阅 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="356f3-162">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356f3-163"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-163"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-164">int</span><span class="sxs-lookup"><span data-stu-id="356f3-164">int</span></span></p></td>
<td><p><span data-ttu-id="356f3-165">对外</span><span class="sxs-lookup"><span data-stu-id="356f3-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="356f3-166">会议服务器使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="356f3-166">Client version used by the conference server.</span></span> <span data-ttu-id="356f3-167">有关详细信息，请参阅 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="356f3-167">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356f3-168"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-168"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-169">datetime</span><span class="sxs-lookup"><span data-stu-id="356f3-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="356f3-170">对外</span><span class="sxs-lookup"><span data-stu-id="356f3-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="356f3-171">用于标识由当前会话取代的对话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="356f3-171">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="356f3-172">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="356f3-172">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356f3-173"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-173"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-174">int</span><span class="sxs-lookup"><span data-stu-id="356f3-174">int</span></span></p></td>
<td><p><span data-ttu-id="356f3-175">对外</span><span class="sxs-lookup"><span data-stu-id="356f3-175">Foreign</span></span></p></td>
<td><p><span data-ttu-id="356f3-176">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="356f3-176">ID number to identify the session.</span></span> <span data-ttu-id="356f3-177">与 <strong>ReplacesDialogIdTime</strong> 结合使用来唯一地标识由此会话取代的会话。</span><span class="sxs-lookup"><span data-stu-id="356f3-177">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="356f3-178">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="356f3-178">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356f3-179"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-179"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-180">位</span><span class="sxs-lookup"><span data-stu-id="356f3-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="356f3-181">指示会话是否是由会议服务器启动的。</span><span class="sxs-lookup"><span data-stu-id="356f3-181">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356f3-182"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-182"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-183">位</span><span class="sxs-lookup"><span data-stu-id="356f3-183">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="356f3-184">指示会话是否是由会议服务器终止的。</span><span class="sxs-lookup"><span data-stu-id="356f3-184">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356f3-185"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-185"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-186">位</span><span class="sxs-lookup"><span data-stu-id="356f3-186">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="356f3-187">用户是否从内部登录。</span><span class="sxs-lookup"><span data-stu-id="356f3-187">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356f3-188"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-188"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-189">int</span><span class="sxs-lookup"><span data-stu-id="356f3-189">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="356f3-190">会话邀请的会话初始协议 (SIP) 响应代码。</span><span class="sxs-lookup"><span data-stu-id="356f3-190">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="356f3-191">此字段通常用从会话中的初始 INVITE 消息生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="356f3-191">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="356f3-192">如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="356f3-192">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356f3-193"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-193"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-194">int</span><span class="sxs-lookup"><span data-stu-id="356f3-194">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="356f3-195">从 SIP 标头捕获的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="356f3-195">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356f3-196"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-196"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-197">int</span><span class="sxs-lookup"><span data-stu-id="356f3-197">int</span></span></p></td>
<td><p><span data-ttu-id="356f3-198">对外</span><span class="sxs-lookup"><span data-stu-id="356f3-198">Foreign</span></span></p></td>
<td><p><span data-ttu-id="356f3-199">用于此会话的前端服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="356f3-199">ID of the front-end server used for this session.</span></span> <span data-ttu-id="356f3-200">有关详细信息，请参阅 <a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="356f3-200">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356f3-201"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-201"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-202">int</span><span class="sxs-lookup"><span data-stu-id="356f3-202">int</span></span></p></td>
<td><p><span data-ttu-id="356f3-203">对外</span><span class="sxs-lookup"><span data-stu-id="356f3-203">Foreign</span></span></p></td>
<td><p><span data-ttu-id="356f3-204">在其中捕获会话的池的 ID。</span><span class="sxs-lookup"><span data-stu-id="356f3-204">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="356f3-205">有关详细信息，请参阅 <a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="356f3-205">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356f3-206"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-206"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-207">int</span><span class="sxs-lookup"><span data-stu-id="356f3-207">int</span></span></p></td>
<td><p><span data-ttu-id="356f3-208">对外</span><span class="sxs-lookup"><span data-stu-id="356f3-208">Foreign</span></span></p></td>
<td><p><span data-ttu-id="356f3-209">呼叫使用的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="356f3-209">The Mediation Server the call is using.</span></span> <span data-ttu-id="356f3-210">有关详细信息，请参阅 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="356f3-210">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356f3-211"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-211"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-212">int</span><span class="sxs-lookup"><span data-stu-id="356f3-212">int</span></span></p></td>
<td><p><span data-ttu-id="356f3-213">对外</span><span class="sxs-lookup"><span data-stu-id="356f3-213">Foreign</span></span></p></td>
<td><p><span data-ttu-id="356f3-214">呼叫使用的网关。</span><span class="sxs-lookup"><span data-stu-id="356f3-214">The gateway the call is using.</span></span> <span data-ttu-id="356f3-215">有关详细信息，请参阅 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的网关表</a> 。</span><span class="sxs-lookup"><span data-stu-id="356f3-215">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356f3-216"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-216"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-217">int</span><span class="sxs-lookup"><span data-stu-id="356f3-217">int</span></span></p></td>
<td><p><span data-ttu-id="356f3-218">对外</span><span class="sxs-lookup"><span data-stu-id="356f3-218">Foreign</span></span></p></td>
<td><p><span data-ttu-id="356f3-219">呼叫使用的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="356f3-219">The Edge Server the call is using.</span></span> <span data-ttu-id="356f3-220">有关详细信息，请参阅 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="356f3-220">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356f3-221"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-221"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-222">int</span><span class="sxs-lookup"><span data-stu-id="356f3-222">int</span></span></p></td>
<td><p><span data-ttu-id="356f3-223">对外</span><span class="sxs-lookup"><span data-stu-id="356f3-223">Foreign</span></span></p></td>
<td><p><span data-ttu-id="356f3-224">会话中使用的内容类型。</span><span class="sxs-lookup"><span data-stu-id="356f3-224">Content type used in the session.</span></span> <span data-ttu-id="356f3-225">有关详细信息，请参阅 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="356f3-225">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356f3-226"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-226"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-227">datetime</span><span class="sxs-lookup"><span data-stu-id="356f3-227">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="356f3-p121">第一个 INVITE 请求的时间。此字段通常用从会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="356f3-p121">The time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356f3-231"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-231"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-232">datetime</span><span class="sxs-lookup"><span data-stu-id="356f3-232">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="356f3-233">第一个 SIP 响应的时间。</span><span class="sxs-lookup"><span data-stu-id="356f3-233">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="356f3-234">此字段通常用从会话中的初始 INVITE 消息生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="356f3-234">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="356f3-235">如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="356f3-235">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356f3-236"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-236"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-237">datetime</span><span class="sxs-lookup"><span data-stu-id="356f3-237">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="356f3-238">会话结束的时间。</span><span class="sxs-lookup"><span data-stu-id="356f3-238">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356f3-239"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-239"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-240">tinyint</span><span class="sxs-lookup"><span data-stu-id="356f3-240">tinyint</span></span></p></td>
<td><p><span data-ttu-id="356f3-241">对外</span><span class="sxs-lookup"><span data-stu-id="356f3-241">Foreign</span></span></p></td>
<td><p><span data-ttu-id="356f3-242"><a href="lync-server-2013-uritypes-table.md">在 Lync Server 2013 中的 UriTypes 表中</a>包含 MCU URI 类型值。</span><span class="sxs-lookup"><span data-stu-id="356f3-242">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="356f3-243">此字段用于改进查询性能。</span><span class="sxs-lookup"><span data-stu-id="356f3-243">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="356f3-244">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="356f3-244">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="356f3-245"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-245"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-246">smallint</span><span class="sxs-lookup"><span data-stu-id="356f3-246">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="356f3-p124">指示用户属性的位集。列出了以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="356f3-p124">A bit set that indicates the user attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="356f3-249">与桌面电话集成 - 1</span><span class="sxs-lookup"><span data-stu-id="356f3-249">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="356f3-250"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="356f3-250"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="356f3-251">smallint</span><span class="sxs-lookup"><span data-stu-id="356f3-251">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="356f3-p125">指示呼叫属性的位集。列出了以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="356f3-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="356f3-254">重试会话 - 1</span><span class="sxs-lookup"><span data-stu-id="356f3-254">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="356f3-255">\* 对于大多数会话，SessionIdSeq 的值将为1。</span><span class="sxs-lookup"><span data-stu-id="356f3-255">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="356f3-256">如果多个会话完全同时启动，则一个会话的 SessionIdSeq 将为 1，另一个会话的 SessionIdSeq 将为 2，依此类推。</span><span class="sxs-lookup"><span data-stu-id="356f3-256">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

