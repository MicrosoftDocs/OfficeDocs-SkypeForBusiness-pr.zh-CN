---
title: Lync Server 2013： ConferenceSessionDetails 视图
description: Lync Server 2013： ConferenceSessionDetails 视图。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1c62f020413efecdbc0f909618256ccc7308d4f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566768"
---
# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="089b9-103">Lync Server 2013 中的 ConferenceSessionDetails 视图</span><span class="sxs-lookup"><span data-stu-id="089b9-103">ConferenceSessionDetails view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="089b9-104">_**上次修改的主题：** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="089b9-104">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="089b9-105">ConferenceSessionDetails 视图可存储有关多方会话的信息。</span><span class="sxs-lookup"><span data-stu-id="089b9-105">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="089b9-106">每个记录表示一个会议会话，它可以是具有会议状态中心的会话，也可以是具有特定会议服务器的会话。</span><span class="sxs-lookup"><span data-stu-id="089b9-106">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="089b9-107">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="089b9-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="089b9-108">列</span><span class="sxs-lookup"><span data-stu-id="089b9-108">Column</span></span></th>
<th><span data-ttu-id="089b9-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="089b9-109">Data Type</span></span></th>
<th><span data-ttu-id="089b9-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="089b9-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="089b9-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-112">datetime</span><span class="sxs-lookup"><span data-stu-id="089b9-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="089b9-113">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="089b9-113">Time of session request.</span></span> <span data-ttu-id="089b9-114">与 SessionIdSeq 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="089b9-114">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="089b9-115">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="089b9-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="089b9-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-117">int</span><span class="sxs-lookup"><span data-stu-id="089b9-117">int</span></span></p></td>
<td><p><span data-ttu-id="089b9-118">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="089b9-118">ID number to identify the session.</span></span> <span data-ttu-id="089b9-119">与 SessionIdTime 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="089b9-119">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="089b9-120">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="089b9-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="089b9-121"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-121"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-122">datetime</span><span class="sxs-lookup"><span data-stu-id="089b9-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="089b9-p104">第一个 INVITE 请求的时间。此字段通常用从会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="089b9-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="089b9-126"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-126"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-127">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="089b9-127">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="089b9-128">会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="089b9-128">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="089b9-129"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-129"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-130">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="089b9-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="089b9-131">会议 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="089b9-131">Type of conference URI.</span></span> <span data-ttu-id="089b9-132">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="089b9-132">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="089b9-133"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-133"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-134">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="089b9-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="089b9-p106">区分各个定期会议实例的标识符。每个定期会议实例的 ConferenceURI 都相同，但具有不同的 ConfInstance 值。</span><span class="sxs-lookup"><span data-stu-id="089b9-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="089b9-137"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-137"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-138">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="089b9-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="089b9-139">会议服务器的 URI。</span><span class="sxs-lookup"><span data-stu-id="089b9-139">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="089b9-140"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-140"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-141">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="089b9-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="089b9-142">会议服务器 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="089b9-142">Type of conferencing server URI.</span></span> <span data-ttu-id="089b9-143">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="089b9-143">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="089b9-144"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-144"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-145">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="089b9-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="089b9-146">会话所涉及的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="089b9-146">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="089b9-147"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-147"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-148">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="089b9-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="089b9-149">已作为会话的一部分的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="089b9-149">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="089b9-150">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="089b9-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="089b9-151"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-151"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-152">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="089b9-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="089b9-153">已作为会话的一部分的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="089b9-153">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="089b9-154">有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a> 。</span><span class="sxs-lookup"><span data-stu-id="089b9-154">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="089b9-155"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-155"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-156">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="089b9-156">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="089b9-157">已作为会话的一部分的用户的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="089b9-157">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="089b9-158"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-158"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-159">datetime</span><span class="sxs-lookup"><span data-stu-id="089b9-159">datetime</span></span></p></td>
<td><p><span data-ttu-id="089b9-160">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="089b9-160">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="089b9-161"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-161"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-162">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="089b9-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="089b9-163">会议服务器的版本。</span><span class="sxs-lookup"><span data-stu-id="089b9-163">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="089b9-164"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-164"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-165">int</span><span class="sxs-lookup"><span data-stu-id="089b9-165">int</span></span></p></td>
<td><p><span data-ttu-id="089b9-166">会议服务器的类型。</span><span class="sxs-lookup"><span data-stu-id="089b9-166">Type of conference server.</span></span> <span data-ttu-id="089b9-167">有关详细信息，请参阅 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="089b9-167">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="089b9-168"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-168"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-169">nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="089b9-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="089b9-170">会议服务器类别。</span><span class="sxs-lookup"><span data-stu-id="089b9-170">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="089b9-171"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-171"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-172">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="089b9-172">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="089b9-173">参与会话的用户所使用的客户端的版本。</span><span class="sxs-lookup"><span data-stu-id="089b9-173">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="089b9-174"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-174"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-175">int</span><span class="sxs-lookup"><span data-stu-id="089b9-175">int</span></span></p></td>
<td><p><span data-ttu-id="089b9-176">参与会话的用户所使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="089b9-176">Client used by the user who participated in the session.</span></span> <span data-ttu-id="089b9-177">有关更多详细信息，请参阅 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="089b9-177">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="089b9-178"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-178"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-179">nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="089b9-179">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="089b9-180">已作为会话的一部分的用户所使用的客户端的类别名称。</span><span class="sxs-lookup"><span data-stu-id="089b9-180">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="089b9-181"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-181"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-182">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="089b9-182">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="089b9-183">作为启动会话的主体的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="089b9-183">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="089b9-184"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-184"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-185">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="089b9-185">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="089b9-186">代表启动会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="089b9-186">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="089b9-187">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="089b9-187">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="089b9-188"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-188"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-189">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="089b9-189">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="089b9-190">代表启动会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="089b9-190">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="089b9-191">有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a> 。</span><span class="sxs-lookup"><span data-stu-id="089b9-191">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="089b9-192"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-192"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-193">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="089b9-193">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="089b9-194">提交会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="089b9-194">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="089b9-195"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-195"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-196">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="089b9-196">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="089b9-197">提交会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="089b9-197">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="089b9-198">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="089b9-198">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="089b9-199"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-199"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-200">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="089b9-200">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="089b9-201">提交会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="089b9-201">Tenant of the user who referred the session.</span></span> <span data-ttu-id="089b9-202">有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a> 。</span><span class="sxs-lookup"><span data-stu-id="089b9-202">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="089b9-203"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-203"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-204">varstring (775) </span><span class="sxs-lookup"><span data-stu-id="089b9-204">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="089b9-p116">SIP 对话 ID。格式如下：</span><span class="sxs-lookup"><span data-stu-id="089b9-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="089b9-207">:d ialog; from-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="089b9-207">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="089b9-208"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-208"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-209">datetime</span><span class="sxs-lookup"><span data-stu-id="089b9-209">datetime</span></span></p></td>
<td><p><span data-ttu-id="089b9-210">用于标识由当前会话取代的对话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="089b9-210">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="089b9-211">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="089b9-211">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="089b9-212"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-212"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-213">int</span><span class="sxs-lookup"><span data-stu-id="089b9-213">int</span></span></p></td>
<td><p><span data-ttu-id="089b9-214">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="089b9-214">ID number to identify the session.</span></span> <span data-ttu-id="089b9-215">与 ReplaceDialogIdTime 结合使用来唯一地标识此会话替换的会话。</span><span class="sxs-lookup"><span data-stu-id="089b9-215">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="089b9-216">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="089b9-216">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="089b9-217"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-217"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-218">varchar (775) </span><span class="sxs-lookup"><span data-stu-id="089b9-218">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="089b9-p119">会话取代的 SIP 对话 ID。格式如下：</span><span class="sxs-lookup"><span data-stu-id="089b9-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="089b9-221">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="089b9-221">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="089b9-222"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-222"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-223">位</span><span class="sxs-lookup"><span data-stu-id="089b9-223">bit</span></span></p></td>
<td><p><span data-ttu-id="089b9-224">指示会议服务器是否已启动会话。</span><span class="sxs-lookup"><span data-stu-id="089b9-224">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="089b9-225"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-225"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-226">位</span><span class="sxs-lookup"><span data-stu-id="089b9-226">bit</span></span></p></td>
<td><p><span data-ttu-id="089b9-227">指示会议服务器是否已结束会话。</span><span class="sxs-lookup"><span data-stu-id="089b9-227">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="089b9-228"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-228"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-229">位</span><span class="sxs-lookup"><span data-stu-id="089b9-229">bit</span></span></p></td>
<td><p><span data-ttu-id="089b9-230">指示用户是否是从内部网络登录的。</span><span class="sxs-lookup"><span data-stu-id="089b9-230">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="089b9-231"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-231"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-232">datetime</span><span class="sxs-lookup"><span data-stu-id="089b9-232">datetime</span></span></p></td>
<td><p><span data-ttu-id="089b9-p120">对第一个 INVITE 消息的响应时间。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="089b9-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="089b9-236"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-236"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-237">int</span><span class="sxs-lookup"><span data-stu-id="089b9-237">int</span></span></p></td>
<td><p><span data-ttu-id="089b9-p121">会话邀请的 SIP 响应代码。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="089b9-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="089b9-241"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-241"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-242">int</span><span class="sxs-lookup"><span data-stu-id="089b9-242">int</span></span></p></td>
<td><p><span data-ttu-id="089b9-243">从会话 SIP 标头捕获的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="089b9-243">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="089b9-244"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-244"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-245">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="089b9-245">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="089b9-246">会话的内容类型。</span><span class="sxs-lookup"><span data-stu-id="089b9-246">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="089b9-247"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-247"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-248">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="089b9-248">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="089b9-249">捕获会话数据的前端服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="089b9-249">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="089b9-250"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-250"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-251">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="089b9-251">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="089b9-252">已捕获会话的数据的池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="089b9-252">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="089b9-253"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-253"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-254">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="089b9-254">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="089b9-255">参与会话的用户所使用的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="089b9-255">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="089b9-256"><strong>网关</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-256"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-257">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="089b9-257">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="089b9-258">参与会话的用户所使用的网关。</span><span class="sxs-lookup"><span data-stu-id="089b9-258">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="089b9-259"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-259"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-260">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="089b9-260">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="089b9-261">参与会话的用户所使用的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="089b9-261">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="089b9-262"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-262"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-263">smallint</span><span class="sxs-lookup"><span data-stu-id="089b9-263">smallint</span></span></p></td>
<td><p><span data-ttu-id="089b9-p122">指示参与会话的用户的属性。以下是允许的属性定义：</span><span class="sxs-lookup"><span data-stu-id="089b9-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="089b9-266">0x01 - 与桌面电话集成</span><span class="sxs-lookup"><span data-stu-id="089b9-266">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="089b9-267"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="089b9-267"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="089b9-268">smallint</span><span class="sxs-lookup"><span data-stu-id="089b9-268">smallint</span></span></p></td>
<td><p><span data-ttu-id="089b9-p123">指示呼叫属性。以下是允许的属性定义：</span><span class="sxs-lookup"><span data-stu-id="089b9-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="089b9-271">0x01 - 重试会话</span><span class="sxs-lookup"><span data-stu-id="089b9-271">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="089b9-272">0x02 - 代表响应组的代理进行的呼叫</span><span class="sxs-lookup"><span data-stu-id="089b9-272">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

