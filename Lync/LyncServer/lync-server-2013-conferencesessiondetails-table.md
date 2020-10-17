---
title: Lync Server 2013： ConferenceSessionDetails 表
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
ms.openlocfilehash: 57d8e3cb0a79c8ce6a6c1c51891fbad265f045de
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529199"
---
# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="393eb-102">Lync Server 2013 中的 ConferenceSessionDetails 表</span><span class="sxs-lookup"><span data-stu-id="393eb-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="393eb-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="393eb-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="393eb-104">每个记录表示一个会议会话，它可以是具有会议状态中心的会话，也可以是具有特定会议服务器的会话。</span><span class="sxs-lookup"><span data-stu-id="393eb-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="393eb-105">列</span><span class="sxs-lookup"><span data-stu-id="393eb-105">Column</span></span></th>
<th><span data-ttu-id="393eb-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="393eb-106">Data Type</span></span></th>
<th><span data-ttu-id="393eb-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="393eb-107">Key/Index</span></span></th>
<th><span data-ttu-id="393eb-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="393eb-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="393eb-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-110">Datetime</span><span class="sxs-lookup"><span data-stu-id="393eb-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="393eb-111">主、外</span><span class="sxs-lookup"><span data-stu-id="393eb-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="393eb-112">会话请求的时间；与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会议会话。</span><span class="sxs-lookup"><span data-stu-id="393eb-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="393eb-113">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="393eb-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="393eb-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-115">int</span><span class="sxs-lookup"><span data-stu-id="393eb-115">int</span></span></p></td>
<td><p><span data-ttu-id="393eb-116">主、外</span><span class="sxs-lookup"><span data-stu-id="393eb-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="393eb-117">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="393eb-117">ID number to identify the session.</span></span> <span data-ttu-id="393eb-118">与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会议会话。</span><span class="sxs-lookup"><span data-stu-id="393eb-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="393eb-119">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="393eb-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="393eb-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-121">int</span><span class="sxs-lookup"><span data-stu-id="393eb-121">int</span></span></p></td>
<td><p><span data-ttu-id="393eb-122">对外</span><span class="sxs-lookup"><span data-stu-id="393eb-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="393eb-123">与此会话相关的会议状态中心会议 URI。</span><span class="sxs-lookup"><span data-stu-id="393eb-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="393eb-124">有关详细信息，请参阅 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="393eb-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="393eb-125">此 URI 是基于会议状态中心的会议 URI。</span><span class="sxs-lookup"><span data-stu-id="393eb-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="393eb-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-127">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="393eb-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="393eb-128">区分各个定期会议实例的标识符。</span><span class="sxs-lookup"><span data-stu-id="393eb-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="393eb-129">每个定期会议实例的 ConferenceURI 都相同，但具有不同的 ConfInstance 值。</span><span class="sxs-lookup"><span data-stu-id="393eb-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="393eb-130">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="393eb-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="393eb-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-132">int</span><span class="sxs-lookup"><span data-stu-id="393eb-132">int</span></span></p></td>
<td><p><span data-ttu-id="393eb-133">对外</span><span class="sxs-lookup"><span data-stu-id="393eb-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="393eb-134">与此会话相关的会议服务器会议 URI。</span><span class="sxs-lookup"><span data-stu-id="393eb-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="393eb-135">有关详细信息，请参阅 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="393eb-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="393eb-136">此 URI 是基于会议服务器的会议 URI。</span><span class="sxs-lookup"><span data-stu-id="393eb-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="393eb-137">对于会议状态中心会议会话，此列将为 null。</span><span class="sxs-lookup"><span data-stu-id="393eb-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="393eb-138"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-139">int</span><span class="sxs-lookup"><span data-stu-id="393eb-139">int</span></span></p></td>
<td><p><span data-ttu-id="393eb-140">对外</span><span class="sxs-lookup"><span data-stu-id="393eb-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="393eb-141">会议会话中的一个用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="393eb-141">ID of one user in the conference session.</span></span> <span data-ttu-id="393eb-142">有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="393eb-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="393eb-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-144">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="393eb-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="393eb-p107">用于标识终结点的实例的 GUID。例如，如果一个用户使用相同帐户登录到不同的计算机上，则每台计算机将具有不同的终结点 ID。</span><span class="sxs-lookup"><span data-stu-id="393eb-p107">A GUID to identify the instance of endpoint. For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="393eb-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-148">int</span><span class="sxs-lookup"><span data-stu-id="393eb-148">int</span></span></p></td>
<td><p><span data-ttu-id="393eb-149">对外</span><span class="sxs-lookup"><span data-stu-id="393eb-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="393eb-150">指示呼叫者所代表的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="393eb-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="393eb-151">有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="393eb-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="393eb-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-153">int</span><span class="sxs-lookup"><span data-stu-id="393eb-153">int</span></span></p></td>
<td><p><span data-ttu-id="393eb-154">对外</span><span class="sxs-lookup"><span data-stu-id="393eb-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="393eb-155">引用呼叫的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="393eb-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="393eb-156">有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="393eb-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="393eb-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-158">int</span><span class="sxs-lookup"><span data-stu-id="393eb-158">int</span></span></p></td>
<td><p><span data-ttu-id="393eb-159">对外</span><span class="sxs-lookup"><span data-stu-id="393eb-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="393eb-160">会议用户使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="393eb-160">Client version used by the conference user.</span></span> <span data-ttu-id="393eb-161">有关详细信息，请参阅 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="393eb-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="393eb-162"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-163">int</span><span class="sxs-lookup"><span data-stu-id="393eb-163">int</span></span></p></td>
<td><p><span data-ttu-id="393eb-164">对外</span><span class="sxs-lookup"><span data-stu-id="393eb-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="393eb-165">会议服务器使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="393eb-165">Client version used by the conference server.</span></span> <span data-ttu-id="393eb-166">有关详细信息，请参阅 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="393eb-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="393eb-167"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-168">datetime</span><span class="sxs-lookup"><span data-stu-id="393eb-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="393eb-169">对外</span><span class="sxs-lookup"><span data-stu-id="393eb-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="393eb-170">用于标识由当前会话取代的对话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="393eb-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="393eb-171">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="393eb-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="393eb-172"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-173">int</span><span class="sxs-lookup"><span data-stu-id="393eb-173">int</span></span></p></td>
<td><p><span data-ttu-id="393eb-174">对外</span><span class="sxs-lookup"><span data-stu-id="393eb-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="393eb-175">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="393eb-175">ID number to identify the session.</span></span> <span data-ttu-id="393eb-176">与 <strong>ReplacesDialogIdTime</strong> 结合使用来唯一地标识由此会话取代的会话。</span><span class="sxs-lookup"><span data-stu-id="393eb-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="393eb-177">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="393eb-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="393eb-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-179">位</span><span class="sxs-lookup"><span data-stu-id="393eb-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="393eb-180">指示会话是否是由会议服务器启动的。</span><span class="sxs-lookup"><span data-stu-id="393eb-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="393eb-181"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-182">位</span><span class="sxs-lookup"><span data-stu-id="393eb-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="393eb-183">指示会话是否是由会议服务器终止的。</span><span class="sxs-lookup"><span data-stu-id="393eb-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="393eb-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-185">位</span><span class="sxs-lookup"><span data-stu-id="393eb-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="393eb-186">用户是否从内部登录。</span><span class="sxs-lookup"><span data-stu-id="393eb-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="393eb-187"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-188">int</span><span class="sxs-lookup"><span data-stu-id="393eb-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="393eb-189">会话邀请的会话初始协议 (SIP) 响应代码。</span><span class="sxs-lookup"><span data-stu-id="393eb-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="393eb-190">此字段通常用从会话中的初始 INVITE 消息生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="393eb-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="393eb-191">如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="393eb-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="393eb-192"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-193">int</span><span class="sxs-lookup"><span data-stu-id="393eb-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="393eb-194">从 SIP 标头捕获的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="393eb-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="393eb-195"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-196">int</span><span class="sxs-lookup"><span data-stu-id="393eb-196">int</span></span></p></td>
<td><p><span data-ttu-id="393eb-197">对外</span><span class="sxs-lookup"><span data-stu-id="393eb-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="393eb-198">用于此会话的前端服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="393eb-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="393eb-199">有关详细信息，请参阅 <a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="393eb-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="393eb-200"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-201">int</span><span class="sxs-lookup"><span data-stu-id="393eb-201">int</span></span></p></td>
<td><p><span data-ttu-id="393eb-202">对外</span><span class="sxs-lookup"><span data-stu-id="393eb-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="393eb-203">在其中捕获会话的池的 ID。</span><span class="sxs-lookup"><span data-stu-id="393eb-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="393eb-204">有关详细信息，请参阅 <a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="393eb-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="393eb-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-206">int</span><span class="sxs-lookup"><span data-stu-id="393eb-206">int</span></span></p></td>
<td><p><span data-ttu-id="393eb-207">对外</span><span class="sxs-lookup"><span data-stu-id="393eb-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="393eb-208">呼叫使用的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="393eb-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="393eb-209">有关详细信息，请参阅 <a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="393eb-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="393eb-210"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-211">int</span><span class="sxs-lookup"><span data-stu-id="393eb-211">int</span></span></p></td>
<td><p><span data-ttu-id="393eb-212">对外</span><span class="sxs-lookup"><span data-stu-id="393eb-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="393eb-213">呼叫使用的网关。</span><span class="sxs-lookup"><span data-stu-id="393eb-213">The gateway the call is using.</span></span> <span data-ttu-id="393eb-214">有关详细信息，请参阅 <a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的网关表</a> 。</span><span class="sxs-lookup"><span data-stu-id="393eb-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="393eb-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-216">int</span><span class="sxs-lookup"><span data-stu-id="393eb-216">int</span></span></p></td>
<td><p><span data-ttu-id="393eb-217">对外</span><span class="sxs-lookup"><span data-stu-id="393eb-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="393eb-218">呼叫使用的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="393eb-218">The Edge Server the call is using.</span></span> <span data-ttu-id="393eb-219">有关详细信息，请参阅 <a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="393eb-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="393eb-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-221">int</span><span class="sxs-lookup"><span data-stu-id="393eb-221">int</span></span></p></td>
<td><p><span data-ttu-id="393eb-222">对外</span><span class="sxs-lookup"><span data-stu-id="393eb-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="393eb-223">会话中使用的内容类型。</span><span class="sxs-lookup"><span data-stu-id="393eb-223">Content type used in the session.</span></span> <span data-ttu-id="393eb-224">有关详细信息，请参阅 <a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="393eb-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="393eb-225"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-226">datetime</span><span class="sxs-lookup"><span data-stu-id="393eb-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="393eb-p121">第一个 INVITE 请求的时间。此字段通常用从会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="393eb-p121">The time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="393eb-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-231">datetime</span><span class="sxs-lookup"><span data-stu-id="393eb-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="393eb-232">第一个 SIP 响应的时间。</span><span class="sxs-lookup"><span data-stu-id="393eb-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="393eb-233">此字段通常用从会话中的初始 INVITE 消息生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="393eb-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="393eb-234">如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="393eb-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="393eb-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-236">datetime</span><span class="sxs-lookup"><span data-stu-id="393eb-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="393eb-237">会话结束的时间。</span><span class="sxs-lookup"><span data-stu-id="393eb-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="393eb-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-239">tinyint</span><span class="sxs-lookup"><span data-stu-id="393eb-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="393eb-240">对外</span><span class="sxs-lookup"><span data-stu-id="393eb-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="393eb-241"><a href="lync-server-2013-uritypes-table.md">在 Lync Server 2013 中的 UriTypes 表中</a>包含 MCU URI 类型值。</span><span class="sxs-lookup"><span data-stu-id="393eb-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="393eb-242">此字段用于改进查询性能。</span><span class="sxs-lookup"><span data-stu-id="393eb-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="393eb-243">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="393eb-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="393eb-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-245">smallint</span><span class="sxs-lookup"><span data-stu-id="393eb-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="393eb-p124">指示用户属性的位集。列出了以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="393eb-p124">A bit set that indicates the user attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="393eb-248">与桌面电话集成 - 1</span><span class="sxs-lookup"><span data-stu-id="393eb-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="393eb-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="393eb-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="393eb-250">smallint</span><span class="sxs-lookup"><span data-stu-id="393eb-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="393eb-p125">指示呼叫属性的位集。列出了以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="393eb-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="393eb-253">重试会话 - 1</span><span class="sxs-lookup"><span data-stu-id="393eb-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="393eb-254">\* 对于大多数会话，SessionIdSeq 的值将为1。</span><span class="sxs-lookup"><span data-stu-id="393eb-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="393eb-255">如果多个会话完全同时启动，则一个会话的 SessionIdSeq 将为 1，另一个会话的 SessionIdSeq 将为 2，依此类推。</span><span class="sxs-lookup"><span data-stu-id="393eb-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

