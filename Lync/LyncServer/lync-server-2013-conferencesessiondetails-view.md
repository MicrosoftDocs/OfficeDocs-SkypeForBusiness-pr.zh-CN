---
title: 'Lync Server 2013: ConferenceSessionDetails 视图'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ConferenceSessionDetails view
ms:assetid: 5858c84d-baed-421d-ad1d-3726e150e256
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688066(v=OCS.15)
ms:contentKeyID: 49733660
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0432606a49766f7ea6755f5f234343ac70ca6c0e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="ca2aa-102">Lync Server 2013 中的 ConferenceSessionDetails 视图</span><span class="sxs-lookup"><span data-stu-id="ca2aa-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca2aa-103">_**主题上次修改时间:** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="ca2aa-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="ca2aa-104">ConferenceSessionDetails 视图存储有关多方会话的信息。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="ca2aa-105">每个记录表示一个会议会话, 该会话可以是与焦点的会话, 也可以是与特定的会议服务器的会话。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="ca2aa-106">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca2aa-107">列</span><span class="sxs-lookup"><span data-stu-id="ca2aa-107">Column</span></span></th>
<th><span data-ttu-id="ca2aa-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="ca2aa-108">Data Type</span></span></th>
<th><span data-ttu-id="ca2aa-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="ca2aa-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca2aa-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-111">datetime</span><span class="sxs-lookup"><span data-stu-id="ca2aa-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-112">Time of session request.</span></span> <span data-ttu-id="ca2aa-113">与 SessionIdSeq 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="ca2aa-114">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2aa-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-116">int</span><span class="sxs-lookup"><span data-stu-id="ca2aa-116">int</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-117">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-117">ID number to identify the session.</span></span> <span data-ttu-id="ca2aa-118">与 SessionIdTime 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="ca2aa-119">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2aa-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-121">datetime</span><span class="sxs-lookup"><span data-stu-id="ca2aa-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-122">第一次邀请请求的时间。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-122">Time of the first INVITE request.</span></span> <span data-ttu-id="ca2aa-123">此字段通常由会话中的初始邀请消息所生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-123">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="ca2aa-124">如果没有邀请消息, 则该字段将填充第一个相关 SIP 邮件的日期和时间 (再见、取消、消息或信息)。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-124">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2aa-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-126">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-127">会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2aa-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-130">会议 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-130">Type of conference URI.</span></span> <span data-ttu-id="ca2aa-131">有关详细信息, 请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2aa-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-133">标识符</span><span class="sxs-lookup"><span data-stu-id="ca2aa-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-134">区分定期会议的实例的标识符。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-134">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="ca2aa-135">每个定期会议实例具有相同的 ConferenceURI, 但具有不同的 ConfInstance 值。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-135">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2aa-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-137">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-138">会议服务器的 URI。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2aa-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-141">会议服务器 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-141">Type of conferencing server URI.</span></span> <span data-ttu-id="ca2aa-142">有关详细信息, 请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2aa-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-144">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-145">会话中涉及的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2aa-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-147">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-148">属于会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="ca2aa-149">有关详细信息, 请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2aa-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-152">属于会话一部分的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="ca2aa-153">有关详细信息, 请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2aa-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-155">标识符</span><span class="sxs-lookup"><span data-stu-id="ca2aa-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-156">属于会话的用户的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2aa-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-158">datetime</span><span class="sxs-lookup"><span data-stu-id="ca2aa-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-159">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2aa-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-161">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-162">会议服务器的版本。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2aa-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-164">int</span><span class="sxs-lookup"><span data-stu-id="ca2aa-164">int</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-165">会议服务器的类型。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-165">Type of conference server.</span></span> <span data-ttu-id="ca2aa-166">有关详细信息, 请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2aa-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-168">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-169">"会议服务器" 类别。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2aa-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-171">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-172">参与会话的用户使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2aa-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-174">int</span><span class="sxs-lookup"><span data-stu-id="ca2aa-174">int</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-175">参与会话的用户所使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="ca2aa-176">有关详细信息, 请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2aa-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-178">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-179">参与会话的用户所使用的客户端类别的名称。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2aa-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-181">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-182">已代表其启动会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2aa-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-184">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-185">已代表其启动会话的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="ca2aa-186">有关详细信息, 请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2aa-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-188">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-189">其代表启动会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="ca2aa-190">有关详细信息, 请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2aa-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-192">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-193">引用会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2aa-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-195">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-196">引用会话的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="ca2aa-197">有关详细信息, 请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2aa-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-199">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-200">引用会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="ca2aa-201">有关详细信息, 请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2aa-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-203">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-204">SIP 对话框 ID。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-204">SIP dialog ID.</span></span> <span data-ttu-id="ca2aa-205">格式为</span><span class="sxs-lookup"><span data-stu-id="ca2aa-205">The format is</span></span></p>
<p><span data-ttu-id="ca2aa-206">:d ialog; from-标记; to-标记</span><span class="sxs-lookup"><span data-stu-id="ca2aa-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2aa-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-208">datetime</span><span class="sxs-lookup"><span data-stu-id="ca2aa-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-209">标识由当前会话替换的对话框的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="ca2aa-210">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2aa-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-212">int</span><span class="sxs-lookup"><span data-stu-id="ca2aa-212">int</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-213">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-213">ID number to identify the session.</span></span> <span data-ttu-id="ca2aa-214">与 ReplaceDialogIdTime 结合使用以唯一标识此会话替换的会话。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="ca2aa-215">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2aa-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-217">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-218">会话将替换的 SIP 对话框 ID。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-218">SIP dialog ID the session replaces.</span></span> <span data-ttu-id="ca2aa-219">的格式为:</span><span class="sxs-lookup"><span data-stu-id="ca2aa-219">The format of the is:</span></span></p>
<p><span data-ttu-id="ca2aa-220">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="ca2aa-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2aa-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-222">bit</span><span class="sxs-lookup"><span data-stu-id="ca2aa-222">bit</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-223">指示会话是否由会议服务器启动。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2aa-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-225">bit</span><span class="sxs-lookup"><span data-stu-id="ca2aa-225">bit</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-226">指示会话是否已由会议服务器结束。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2aa-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-228">bit</span><span class="sxs-lookup"><span data-stu-id="ca2aa-228">bit</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-229">指示用户是否从内部网络登录。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2aa-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-231">datetime</span><span class="sxs-lookup"><span data-stu-id="ca2aa-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-232">对第一个邀请消息的答复时间。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-232">Time of the response to the first INVITE message.</span></span> <span data-ttu-id="ca2aa-233">此字段通常由会话中的初始邀请消息所生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="ca2aa-234">如果没有邀请消息, 则该字段将填充第一个相关 SIP 邮件的日期和时间 (再见、取消、消息或信息)。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2aa-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-236">int</span><span class="sxs-lookup"><span data-stu-id="ca2aa-236">int</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-237">会议邀请的 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-237">SIP response code to the session invitation.</span></span> <span data-ttu-id="ca2aa-238">此字段通常由会话中的初始邀请消息所生成的数据填充。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-238">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="ca2aa-239">如果没有邀请消息, 则该字段将填充第一个相关 SIP 邮件的日期和时间 (再见、取消、消息或信息)。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-239">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2aa-240"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-241">int</span><span class="sxs-lookup"><span data-stu-id="ca2aa-241">int</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-242">从会话 SIP 标题捕获的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2aa-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-244">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-245">会话的内容类型。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2aa-246"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-247">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-248">捕获会话的数据的前端服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2aa-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-250">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-251">捕获会话的数据的池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2aa-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-253">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-254">参与会话的用户使用的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2aa-255"><strong>网关</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-256">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-257">参与会话的用户使用的网关。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2aa-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-259">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca2aa-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-260">参与会话的用户所使用的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca2aa-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-262">smallint</span><span class="sxs-lookup"><span data-stu-id="ca2aa-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-263">指示参与会话的用户的属性。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-263">Indicates the attributes of the user who participated in the session.</span></span> <span data-ttu-id="ca2aa-264">允许以下属性定义:</span><span class="sxs-lookup"><span data-stu-id="ca2aa-264">The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="ca2aa-265">0x01-与桌面电话集成</span><span class="sxs-lookup"><span data-stu-id="ca2aa-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca2aa-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="ca2aa-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ca2aa-267">smallint</span><span class="sxs-lookup"><span data-stu-id="ca2aa-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="ca2aa-268">指示通话属性。</span><span class="sxs-lookup"><span data-stu-id="ca2aa-268">Indicates the call attributes.</span></span> <span data-ttu-id="ca2aa-269">允许以下属性定义:</span><span class="sxs-lookup"><span data-stu-id="ca2aa-269">The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="ca2aa-270">0x01-重试 Session0</span><span class="sxs-lookup"><span data-stu-id="ca2aa-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="ca2aa-271">x02-代表响应组的代理发出的呼叫</span><span class="sxs-lookup"><span data-stu-id="ca2aa-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

