---
title: Lync Server 2013：ConferenceSessionDetails 表
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
ms.openlocfilehash: 61da586f3ecaf215b3bb636a80141ba8aaa19f18
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741592"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="e9da3-102">Lync Server 2013 中的 ConferenceSessionDetails 表</span><span class="sxs-lookup"><span data-stu-id="e9da3-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e9da3-103">_**主题上次修改时间：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e9da3-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e9da3-104">每个记录表示一个会议会话，该会话可以是与焦点的会话，也可以是与特定的会议服务器的会话。</span><span class="sxs-lookup"><span data-stu-id="e9da3-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e9da3-105">列</span><span class="sxs-lookup"><span data-stu-id="e9da3-105">Column</span></span></th>
<th><span data-ttu-id="e9da3-106">数据类型</span><span class="sxs-lookup"><span data-stu-id="e9da3-106">Data Type</span></span></th>
<th><span data-ttu-id="e9da3-107">键/索引</span><span class="sxs-lookup"><span data-stu-id="e9da3-107">Key/Index</span></span></th>
<th><span data-ttu-id="e9da3-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="e9da3-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e9da3-109"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-110">从中</span><span class="sxs-lookup"><span data-stu-id="e9da3-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="e9da3-111">主、外部</span><span class="sxs-lookup"><span data-stu-id="e9da3-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9da3-112">会话请求的时间;与<strong>SessionIdSeq</strong>结合使用以唯一标识会议会话。</span><span class="sxs-lookup"><span data-stu-id="e9da3-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="e9da3-113">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="e9da3-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9da3-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-115">int</span><span class="sxs-lookup"><span data-stu-id="e9da3-115">int</span></span></p></td>
<td><p><span data-ttu-id="e9da3-116">主、外部</span><span class="sxs-lookup"><span data-stu-id="e9da3-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9da3-117">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="e9da3-117">ID number to identify the session.</span></span> <span data-ttu-id="e9da3-118">与<strong>SessionIdTime</strong>结合使用以唯一标识会议会话。</span><span class="sxs-lookup"><span data-stu-id="e9da3-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="e9da3-119">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="e9da3-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9da3-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-121">int</span><span class="sxs-lookup"><span data-stu-id="e9da3-121">int</span></span></p></td>
<td><p><span data-ttu-id="e9da3-122">外表</span><span class="sxs-lookup"><span data-stu-id="e9da3-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9da3-123">与此会话相关的焦点会议 URI。</span><span class="sxs-lookup"><span data-stu-id="e9da3-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="e9da3-124">有关详细信息，请参阅<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e9da3-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="e9da3-125">此 URI 是基于焦点的会议 URI。</span><span class="sxs-lookup"><span data-stu-id="e9da3-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9da3-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-127">标识符</span><span class="sxs-lookup"><span data-stu-id="e9da3-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e9da3-128">区分定期会议的实例的标识符。</span><span class="sxs-lookup"><span data-stu-id="e9da3-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="e9da3-129">每个定期会议实例具有相同的 ConferenceURI，但具有不同的 ConfInstance 值。</span><span class="sxs-lookup"><span data-stu-id="e9da3-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="e9da3-130">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="e9da3-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9da3-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-132">int</span><span class="sxs-lookup"><span data-stu-id="e9da3-132">int</span></span></p></td>
<td><p><span data-ttu-id="e9da3-133">外表</span><span class="sxs-lookup"><span data-stu-id="e9da3-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9da3-134">与此会话相关的会议服务器会议 URI。</span><span class="sxs-lookup"><span data-stu-id="e9da3-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="e9da3-135">有关详细信息，请参阅<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e9da3-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="e9da3-136">此 URI 是基于会议服务器的会议 URI。</span><span class="sxs-lookup"><span data-stu-id="e9da3-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="e9da3-137">对于聚焦会议会话，此列将为 null。</span><span class="sxs-lookup"><span data-stu-id="e9da3-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9da3-138"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-139">int</span><span class="sxs-lookup"><span data-stu-id="e9da3-139">int</span></span></p></td>
<td><p><span data-ttu-id="e9da3-140">外表</span><span class="sxs-lookup"><span data-stu-id="e9da3-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9da3-141">会议会话中一个用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="e9da3-141">ID of one user in the conference session.</span></span> <span data-ttu-id="e9da3-142">有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 "用户" 表。</span><span class="sxs-lookup"><span data-stu-id="e9da3-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9da3-143"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-144">标识符</span><span class="sxs-lookup"><span data-stu-id="e9da3-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e9da3-145">标识终结点实例的 GUID。</span><span class="sxs-lookup"><span data-stu-id="e9da3-145">A GUID to identify the instance of endpoint.</span></span> <span data-ttu-id="e9da3-146">例如，如果一个用户使用同一帐户登录到不同的计算机，则每台计算机都将具有不同的终结点 ID。</span><span class="sxs-lookup"><span data-stu-id="e9da3-146">For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9da3-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-148">int</span><span class="sxs-lookup"><span data-stu-id="e9da3-148">int</span></span></p></td>
<td><p><span data-ttu-id="e9da3-149">外表</span><span class="sxs-lookup"><span data-stu-id="e9da3-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9da3-150">指明呼叫者代表的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="e9da3-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="e9da3-151">有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 "用户" 表。</span><span class="sxs-lookup"><span data-stu-id="e9da3-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9da3-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-153">int</span><span class="sxs-lookup"><span data-stu-id="e9da3-153">int</span></span></p></td>
<td><p><span data-ttu-id="e9da3-154">外表</span><span class="sxs-lookup"><span data-stu-id="e9da3-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9da3-155">按呼叫者引用的用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="e9da3-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="e9da3-156">有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 "用户" 表。</span><span class="sxs-lookup"><span data-stu-id="e9da3-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9da3-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-158">int</span><span class="sxs-lookup"><span data-stu-id="e9da3-158">int</span></span></p></td>
<td><p><span data-ttu-id="e9da3-159">外表</span><span class="sxs-lookup"><span data-stu-id="e9da3-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9da3-160">会议用户使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="e9da3-160">Client version used by the conference user.</span></span> <span data-ttu-id="e9da3-161">有关详细信息，请参阅<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e9da3-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9da3-162"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-163">int</span><span class="sxs-lookup"><span data-stu-id="e9da3-163">int</span></span></p></td>
<td><p><span data-ttu-id="e9da3-164">外表</span><span class="sxs-lookup"><span data-stu-id="e9da3-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9da3-165">会议服务器使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="e9da3-165">Client version used by the conference server.</span></span> <span data-ttu-id="e9da3-166">有关详细信息，请参阅<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e9da3-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9da3-167"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-168">datetime</span><span class="sxs-lookup"><span data-stu-id="e9da3-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="e9da3-169">外表</span><span class="sxs-lookup"><span data-stu-id="e9da3-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9da3-170">标识由当前会话替换的对话框的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="e9da3-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="e9da3-171">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="e9da3-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9da3-172"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-173">int</span><span class="sxs-lookup"><span data-stu-id="e9da3-173">int</span></span></p></td>
<td><p><span data-ttu-id="e9da3-174">外表</span><span class="sxs-lookup"><span data-stu-id="e9da3-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9da3-175">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="e9da3-175">ID number to identify the session.</span></span> <span data-ttu-id="e9da3-176">与<strong>ReplacesDialogIdTime</strong>结合使用以唯一标识此会话替换的会话。</span><span class="sxs-lookup"><span data-stu-id="e9da3-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="e9da3-177">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="e9da3-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9da3-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-179">bit</span><span class="sxs-lookup"><span data-stu-id="e9da3-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e9da3-180">指示会议服务器是否已启动会话。</span><span class="sxs-lookup"><span data-stu-id="e9da3-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9da3-181"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-182">bit</span><span class="sxs-lookup"><span data-stu-id="e9da3-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e9da3-183">指示会议服务器是否已结束会话。</span><span class="sxs-lookup"><span data-stu-id="e9da3-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9da3-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-185">bit</span><span class="sxs-lookup"><span data-stu-id="e9da3-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e9da3-186">用户是否从内部登录。</span><span class="sxs-lookup"><span data-stu-id="e9da3-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9da3-187"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-188">int</span><span class="sxs-lookup"><span data-stu-id="e9da3-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e9da3-189">会话初始协议（SIP）响应代码到会话邀请。</span><span class="sxs-lookup"><span data-stu-id="e9da3-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="e9da3-190">此字段通常由会话中的初始邀请消息所生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="e9da3-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="e9da3-191">如果没有邀请消息，则该字段将填充第一个相关 SIP 邮件的日期和时间（再见、取消、消息或信息）。</span><span class="sxs-lookup"><span data-stu-id="e9da3-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9da3-192"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-193">int</span><span class="sxs-lookup"><span data-stu-id="e9da3-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e9da3-194">从 SIP 标题捕获的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="e9da3-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9da3-195"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-196">int</span><span class="sxs-lookup"><span data-stu-id="e9da3-196">int</span></span></p></td>
<td><p><span data-ttu-id="e9da3-197">外表</span><span class="sxs-lookup"><span data-stu-id="e9da3-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9da3-198">用于此会话的前端服务器的 ID。</span><span class="sxs-lookup"><span data-stu-id="e9da3-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="e9da3-199">有关详细信息，请参阅<a href="lync-server-2013-servers-table.md">Lync Server 2013 中</a>的 "服务器" 表。</span><span class="sxs-lookup"><span data-stu-id="e9da3-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9da3-200"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-201">int</span><span class="sxs-lookup"><span data-stu-id="e9da3-201">int</span></span></p></td>
<td><p><span data-ttu-id="e9da3-202">外表</span><span class="sxs-lookup"><span data-stu-id="e9da3-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9da3-203">捕获会话的池的 ID。</span><span class="sxs-lookup"><span data-stu-id="e9da3-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="e9da3-204">有关详细信息，请参阅<a href="lync-server-2013-pools-table.md">Lync Server 2013 中的 pool 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e9da3-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9da3-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-206">int</span><span class="sxs-lookup"><span data-stu-id="e9da3-206">int</span></span></p></td>
<td><p><span data-ttu-id="e9da3-207">外表</span><span class="sxs-lookup"><span data-stu-id="e9da3-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9da3-208">通话所使用的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="e9da3-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="e9da3-209">有关详细信息，请参阅<a href="lync-server-2013-mediationservers-table.md">Lync Server 2013 中的 MediationServers 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e9da3-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9da3-210"><strong>GatewayId</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-211">int</span><span class="sxs-lookup"><span data-stu-id="e9da3-211">int</span></span></p></td>
<td><p><span data-ttu-id="e9da3-212">外表</span><span class="sxs-lookup"><span data-stu-id="e9da3-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9da3-213">呼叫使用的网关。</span><span class="sxs-lookup"><span data-stu-id="e9da3-213">The gateway the call is using.</span></span> <span data-ttu-id="e9da3-214">有关详细信息，请参阅<a href="lync-server-2013-gateways-table.md">Lync Server 2013 中的网关表</a>。</span><span class="sxs-lookup"><span data-stu-id="e9da3-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9da3-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-216">int</span><span class="sxs-lookup"><span data-stu-id="e9da3-216">int</span></span></p></td>
<td><p><span data-ttu-id="e9da3-217">外表</span><span class="sxs-lookup"><span data-stu-id="e9da3-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9da3-218">通话所使用的边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="e9da3-218">The Edge Server the call is using.</span></span> <span data-ttu-id="e9da3-219">有关详细信息，请参阅<a href="lync-server-2013-edgeservers-table.md">Lync Server 2013 中的 EdgeServers 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e9da3-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9da3-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-221">int</span><span class="sxs-lookup"><span data-stu-id="e9da3-221">int</span></span></p></td>
<td><p><span data-ttu-id="e9da3-222">外表</span><span class="sxs-lookup"><span data-stu-id="e9da3-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9da3-223">会话中使用的内容类型。</span><span class="sxs-lookup"><span data-stu-id="e9da3-223">Content type used in the session.</span></span> <span data-ttu-id="e9da3-224">有关详细信息，请参阅<a href="lync-server-2013-contenttypes-table.md">Lync Server 2013 中的 ContentTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e9da3-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9da3-225"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-226">datetime</span><span class="sxs-lookup"><span data-stu-id="e9da3-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e9da3-227">第一次邀请请求的时间。</span><span class="sxs-lookup"><span data-stu-id="e9da3-227">The time of the first INVITE request.</span></span> <span data-ttu-id="e9da3-228">此字段通常由会话中的初始邀请消息所生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="e9da3-228">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="e9da3-229">如果没有邀请消息，则该字段将填充第一个相关 SIP 邮件的日期和时间（再见、取消、消息或信息）。</span><span class="sxs-lookup"><span data-stu-id="e9da3-229">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9da3-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-231">datetime</span><span class="sxs-lookup"><span data-stu-id="e9da3-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e9da3-232">第一次 SIP 响应的时间。</span><span class="sxs-lookup"><span data-stu-id="e9da3-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="e9da3-233">此字段通常由会话中的初始邀请消息所生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="e9da3-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="e9da3-234">如果没有邀请消息，则该字段将填充第一个相关 SIP 邮件的日期和时间（再见、取消、消息或信息）。</span><span class="sxs-lookup"><span data-stu-id="e9da3-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9da3-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-236">datetime</span><span class="sxs-lookup"><span data-stu-id="e9da3-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e9da3-237">会话结束的时间。</span><span class="sxs-lookup"><span data-stu-id="e9da3-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9da3-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-239">tinyint</span><span class="sxs-lookup"><span data-stu-id="e9da3-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e9da3-240">外表</span><span class="sxs-lookup"><span data-stu-id="e9da3-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e9da3-241"><a href="lync-server-2013-uritypes-table.md">在 Lync Server 2013 中的 UriTypes 表中</a>包含 MCU URI 类型值。</span><span class="sxs-lookup"><span data-stu-id="e9da3-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="e9da3-242">此字段用于提高查询性能。</span><span class="sxs-lookup"><span data-stu-id="e9da3-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="e9da3-243">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="e9da3-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e9da3-244"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-245">smallint</span><span class="sxs-lookup"><span data-stu-id="e9da3-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e9da3-246">指示用户属性的位集。</span><span class="sxs-lookup"><span data-stu-id="e9da3-246">A bit set that indicates the user attributes.</span></span> <span data-ttu-id="e9da3-247">列出了以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="e9da3-247">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="e9da3-248">与桌面电话集成-1</span><span class="sxs-lookup"><span data-stu-id="e9da3-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e9da3-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="e9da3-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e9da3-250">smallint</span><span class="sxs-lookup"><span data-stu-id="e9da3-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e9da3-251">指示通话属性的位集。</span><span class="sxs-lookup"><span data-stu-id="e9da3-251">A bit set that indicates the call attributes.</span></span> <span data-ttu-id="e9da3-252">列出了以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="e9da3-252">The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="e9da3-253">重试会话-1</span><span class="sxs-lookup"><span data-stu-id="e9da3-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="e9da3-254">\*对于大多数会话，SessionIdSeq 将具有值1。</span><span class="sxs-lookup"><span data-stu-id="e9da3-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="e9da3-255">如果多个会话的开始时间完全相同，则一个会话的 SessionIdSeq 将为1，而另一个会话将为2，依此类推。</span><span class="sxs-lookup"><span data-stu-id="e9da3-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

