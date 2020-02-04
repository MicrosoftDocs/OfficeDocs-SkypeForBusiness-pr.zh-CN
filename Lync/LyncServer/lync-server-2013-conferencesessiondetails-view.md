---
title: Lync Server 2013： ConferenceSessionDetails 视图
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
ms.openlocfilehash: 46356099c3eee20794a4198720597dc4395b563f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="e5ad4-102">Lync Server 2013 中的 ConferenceSessionDetails 视图</span><span class="sxs-lookup"><span data-stu-id="e5ad4-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5ad4-103">_**主题上次修改时间：** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="e5ad4-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="e5ad4-104">ConferenceSessionDetails 视图存储有关多方会话的信息。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="e5ad4-105">每个记录表示一个会议会话，该会话可以是与焦点的会话，也可以是与特定的会议服务器的会话。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="e5ad4-106">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5ad4-107">列</span><span class="sxs-lookup"><span data-stu-id="e5ad4-107">Column</span></span></th>
<th><span data-ttu-id="e5ad4-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="e5ad4-108">Data Type</span></span></th>
<th><span data-ttu-id="e5ad4-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="e5ad4-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5ad4-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-111">datetime</span><span class="sxs-lookup"><span data-stu-id="e5ad4-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-112">Time of session request.</span></span> <span data-ttu-id="e5ad4-113">与 SessionIdSeq 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="e5ad4-114">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5ad4-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-116">int</span><span class="sxs-lookup"><span data-stu-id="e5ad4-116">int</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-117">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-117">ID number to identify the session.</span></span> <span data-ttu-id="e5ad4-118">与 SessionIdTime 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="e5ad4-119">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5ad4-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-121">datetime</span><span class="sxs-lookup"><span data-stu-id="e5ad4-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-122">第一次邀请请求的时间。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-122">Time of the first INVITE request.</span></span> <span data-ttu-id="e5ad4-123">此字段通常由会话中的初始邀请消息所生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-123">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="e5ad4-124">如果没有邀请消息，则该字段将填充第一个相关 SIP 邮件的日期和时间（再见、取消、消息或信息）。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-124">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5ad4-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-126">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="e5ad4-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-127">会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5ad4-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5ad4-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-130">会议 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-130">Type of conference URI.</span></span> <span data-ttu-id="e5ad4-131">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5ad4-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-133">标识符</span><span class="sxs-lookup"><span data-stu-id="e5ad4-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-134">区分定期会议的实例的标识符。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-134">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="e5ad4-135">每个定期会议实例具有相同的 ConferenceURI，但具有不同的 ConfInstance 值。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-135">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5ad4-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-137">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="e5ad4-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-138">会议服务器的 URI。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5ad4-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5ad4-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-141">会议服务器 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-141">Type of conferencing server URI.</span></span> <span data-ttu-id="e5ad4-142">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5ad4-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-144">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="e5ad4-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-145">会话中涉及的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5ad4-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-147">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5ad4-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-148">属于会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="e5ad4-149">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5ad4-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5ad4-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-152">属于会话一部分的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="e5ad4-153">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5ad4-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-155">标识符</span><span class="sxs-lookup"><span data-stu-id="e5ad4-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-156">属于会话的用户的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5ad4-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-158">datetime</span><span class="sxs-lookup"><span data-stu-id="e5ad4-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-159">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5ad4-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-161">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5ad4-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-162">会议服务器的版本。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5ad4-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-164">int</span><span class="sxs-lookup"><span data-stu-id="e5ad4-164">int</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-165">会议服务器的类型。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-165">Type of conference server.</span></span> <span data-ttu-id="e5ad4-166">有关详细信息，请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5ad4-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-168">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="e5ad4-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-169">"会议服务器" 类别。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5ad4-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-171">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5ad4-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-172">参与会话的用户使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5ad4-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-174">int</span><span class="sxs-lookup"><span data-stu-id="e5ad4-174">int</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-175">参与会话的用户所使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="e5ad4-176">有关详细信息，请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5ad4-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-178">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="e5ad4-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-179">参与会话的用户所使用的客户端类别的名称。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5ad4-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-181">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="e5ad4-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-182">已代表其启动会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5ad4-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-184">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5ad4-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-185">已代表其启动会话的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="e5ad4-186">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5ad4-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-188">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5ad4-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-189">其代表启动会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="e5ad4-190">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5ad4-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-192">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="e5ad4-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-193">引用会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5ad4-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-195">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5ad4-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-196">引用会话的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="e5ad4-197">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5ad4-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-199">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5ad4-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-200">引用会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="e5ad4-201">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5ad4-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-203">varstring （775）</span><span class="sxs-lookup"><span data-stu-id="e5ad4-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-204">SIP 对话框 ID。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-204">SIP dialog ID.</span></span> <span data-ttu-id="e5ad4-205">格式为</span><span class="sxs-lookup"><span data-stu-id="e5ad4-205">The format is</span></span></p>
<p><span data-ttu-id="e5ad4-206">:d ialog; from-标记; to-标记</span><span class="sxs-lookup"><span data-stu-id="e5ad4-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5ad4-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-208">datetime</span><span class="sxs-lookup"><span data-stu-id="e5ad4-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-209">标识由当前会话替换的对话框的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="e5ad4-210">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5ad4-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-212">int</span><span class="sxs-lookup"><span data-stu-id="e5ad4-212">int</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-213">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-213">ID number to identify the session.</span></span> <span data-ttu-id="e5ad4-214">与 ReplaceDialogIdTime 结合使用以唯一标识此会话替换的会话。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="e5ad4-215">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5ad4-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-217">varchar （775）</span><span class="sxs-lookup"><span data-stu-id="e5ad4-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-218">会话将替换的 SIP 对话框 ID。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-218">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="e5ad4-219">的格式为：</span><span class="sxs-lookup"><span data-stu-id="e5ad4-219">The format of the is:</span></span></p>
<p><span data-ttu-id="e5ad4-220">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="e5ad4-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5ad4-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-222">bit</span><span class="sxs-lookup"><span data-stu-id="e5ad4-222">bit</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-223">指示会话是否由会议服务器启动。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5ad4-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-225">bit</span><span class="sxs-lookup"><span data-stu-id="e5ad4-225">bit</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-226">指示会话是否已由会议服务器结束。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5ad4-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-228">bit</span><span class="sxs-lookup"><span data-stu-id="e5ad4-228">bit</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-229">指示用户是否从内部网络登录。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5ad4-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-231">datetime</span><span class="sxs-lookup"><span data-stu-id="e5ad4-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-232">对第一个邀请消息的答复时间。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-232">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="e5ad4-233">此字段通常由会话中的初始邀请消息所生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="e5ad4-234">如果没有邀请消息，则该字段将填充第一个相关 SIP 邮件的日期和时间（再见、取消、消息或信息）。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5ad4-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-236">int</span><span class="sxs-lookup"><span data-stu-id="e5ad4-236">int</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-237">会议邀请的 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-237">SIP response code to the session invitation.</span></span> <span data-ttu-id="e5ad4-238">此字段通常由会话中的初始邀请消息所生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="e5ad4-239">如果没有邀请消息，则该字段将填充第一个相关 SIP 邮件的日期和时间（再见、取消、消息或信息）。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5ad4-240"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-241">int</span><span class="sxs-lookup"><span data-stu-id="e5ad4-241">int</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-242">从会话 SIP 标题捕获的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5ad4-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-244">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5ad4-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-245">会话的内容类型。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5ad4-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-247">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5ad4-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-248">捕获会话的数据的前端服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5ad4-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-250">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5ad4-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-251">捕获会话的数据的池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5ad4-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-253">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5ad4-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-254">参与会话的用户使用的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5ad4-255"><strong>网关</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-256">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5ad4-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-257">参与会话的用户使用的网关。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5ad4-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-259">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e5ad4-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-260">参与会话的用户所使用的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5ad4-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-262">smallint</span><span class="sxs-lookup"><span data-stu-id="e5ad4-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-263">指示参与会话的用户的属性。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-263">Indicates the attributes of the user who participated in the session.</span></span> <span data-ttu-id="e5ad4-264">允许以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="e5ad4-264">The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="e5ad4-265">0x01-与桌面电话集成</span><span class="sxs-lookup"><span data-stu-id="e5ad4-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5ad4-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="e5ad4-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e5ad4-267">smallint</span><span class="sxs-lookup"><span data-stu-id="e5ad4-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="e5ad4-268">指示通话属性。</span><span class="sxs-lookup"><span data-stu-id="e5ad4-268">Indicates the call attributes.</span></span> <span data-ttu-id="e5ad4-269">允许以下属性定义：</span><span class="sxs-lookup"><span data-stu-id="e5ad4-269">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="e5ad4-270">0x01-重试 Session0</span><span class="sxs-lookup"><span data-stu-id="e5ad4-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="e5ad4-271">x02-代表响应组的代理发出的呼叫</span><span class="sxs-lookup"><span data-stu-id="e5ad4-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

