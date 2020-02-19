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
ms.openlocfilehash: ef6d8baf95cc99c342e18200f9a17e5ab03a7f4f
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42140555"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-view-in-lync-server-2013"></a><span data-ttu-id="ae4ae-102">Lync Server 2013 中的 ConferenceSessionDetails 视图</span><span class="sxs-lookup"><span data-stu-id="ae4ae-102">ConferenceSessionDetails view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae4ae-103">_**上次修改的主题：** 2012-11-12_</span><span class="sxs-lookup"><span data-stu-id="ae4ae-103">_**Topic Last Modified:** 2012-11-12_</span></span>

<span data-ttu-id="ae4ae-104">ConferenceSessionDetails 视图可存储有关多方会话的信息。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-104">The ConferenceSessionDetails view stores information about multiparty sessions.</span></span> <span data-ttu-id="ae4ae-105">每个记录表示一个会议会话，它可以是具有会议状态中心的会话，也可以是具有特定会议服务器的会话。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span> <span data-ttu-id="ae4ae-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ae4ae-107">列</span><span class="sxs-lookup"><span data-stu-id="ae4ae-107">Column</span></span></th>
<th><span data-ttu-id="ae4ae-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="ae4ae-108">Data Type</span></span></th>
<th><span data-ttu-id="ae4ae-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="ae4ae-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ae4ae-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-111">datetime</span><span class="sxs-lookup"><span data-stu-id="ae4ae-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-112">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-112">Time of session request.</span></span> <span data-ttu-id="ae4ae-113">与 SessionIdSeq 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="ae4ae-114">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ae-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-116">int</span><span class="sxs-lookup"><span data-stu-id="ae4ae-116">int</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-117">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-117">ID number to identify the session.</span></span> <span data-ttu-id="ae4ae-118">与 SessionIdTime 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="ae4ae-119">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ae-120"><strong>InviteTime</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-120"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-121">datetime</span><span class="sxs-lookup"><span data-stu-id="ae4ae-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-p104">第一个 INVITE 请求的时间。此字段通常用从会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则此字段将用第一条相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-p104">Time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ae-125"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-125"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-126">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-126">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-127">会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-127">URI of the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ae-128"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-128"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-129">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-130">会议 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-130">Type of conference URI.</span></span> <span data-ttu-id="ae4ae-131">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-131">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ae-132"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-132"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-133">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="ae4ae-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-p106">区分各个定期会议实例的标识符。每个定期会议实例的 ConferenceURI 都相同，但具有不同的 ConfInstance 值。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-p106">Identifier that differentiates between instances of recurring conferences. Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ae-136"><strong>McuConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-136"><strong>McuConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-137">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-138">会议服务器的 URI。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-138">URI of the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ae-139"><strong>McuConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-139"><strong>McuConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-140">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-141">会议服务器 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-141">Type of conferencing server URI.</span></span> <span data-ttu-id="ae4ae-142">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-142">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ae-143"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-143"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-144">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-144">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-145">会话所涉及的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-145">URI of the user involved in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ae-146"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-146"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-147">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-148">已作为会话的一部分的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-148">Type of URI of the user whose was part of the session.</span></span> <span data-ttu-id="ae4ae-149">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-149">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ae-150"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-150"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-151">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-152">已作为会话的一部分的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-152">Tenant of the user whose was part of the session.</span></span> <span data-ttu-id="ae4ae-153">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-153">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ae-154"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-154"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-155">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="ae4ae-155">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-156">已作为会话的一部分的用户的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-156">Unique identifier of the user whose was part of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ae-157"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-157"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-158">datetime</span><span class="sxs-lookup"><span data-stu-id="ae4ae-158">datetime</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-159">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-159">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ae-160"><strong>ConferenceClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-160"><strong>ConferenceClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-161">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-161">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-162">会议服务器的版本。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-162">Version of conference server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ae-163"><strong>ConferenceClientType</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-163"><strong>ConferenceClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-164">int</span><span class="sxs-lookup"><span data-stu-id="ae4ae-164">int</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-165">会议服务器的类型。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-165">Type of conference server.</span></span> <span data-ttu-id="ae4ae-166">有关详细信息，请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-166">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ae-167"><strong>ConferenceCategory</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-167"><strong>ConferenceCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-168">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-168">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-169">会议服务器类别。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-169">Conference server category.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ae-170"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-170"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-171">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-171">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-172">参与会话的用户所使用的客户端的版本。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-172">Version of client used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ae-173"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-173"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-174">int</span><span class="sxs-lookup"><span data-stu-id="ae4ae-174">int</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-175">参与会话的用户所使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-175">Client used by the user who participated in the session.</span></span> <span data-ttu-id="ae4ae-176">有关更多详细信息，请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-176">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ae-177"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-177"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-178">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-178">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-179">已作为会话的一部分的用户所使用的客户端的类别名称。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-179">Name of the category of the client used by the user who was part of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ae-180"><strong>OnBehalfOfUri</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-180"><strong>OnBehalfOfUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-181">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-181">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-182">作为启动会话的主体的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-182">URI of the user on whose behalf the session was started.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ae-183"><strong>OnBehalfOfUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-183"><strong>OnBehalfOfUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-184">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-184">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-185">代表启动会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-185">Type of URI of the user on whose behalf the session was started.</span></span> <span data-ttu-id="ae4ae-186">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-186">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ae-187"><strong>OnBehalfOfTenant</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-187"><strong>OnBehalfOfTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-188">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-188">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-189">代表启动会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-189">Tenant of the user whose on behalf the session was started.</span></span> <span data-ttu-id="ae4ae-190">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-190">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ae-191"><strong>ReferredByUri</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-191"><strong>ReferredByUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-192">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-192">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-193">提交会话的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-193">URI of the user who referred the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ae-194"><strong>ReferredByUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-194"><strong>ReferredByUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-195">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-196">提交会话的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-196">Type of URI of the user who referred the session.</span></span> <span data-ttu-id="ae4ae-197">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-197">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ae-198"><strong>ReferredByUriTenant</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-198"><strong>ReferredByUriTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-199">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-200">提交会话的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-200">Tenant of the user who referred the session.</span></span> <span data-ttu-id="ae4ae-201">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-201">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ae-202"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-202"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-203">varstring （775）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-203">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-p116">SIP 对话 ID。格式如下：</span><span class="sxs-lookup"><span data-stu-id="ae4ae-p116">SIP dialog ID. The format is</span></span></p>
<p><span data-ttu-id="ae4ae-206">:d ialog; from-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="ae4ae-206">:dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ae-207"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-207"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-208">datetime</span><span class="sxs-lookup"><span data-stu-id="ae4ae-208">datetime</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-209">用于标识由当前会话取代的对话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-209">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="ae4ae-210">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-210">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ae-211"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-211"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-212">int</span><span class="sxs-lookup"><span data-stu-id="ae4ae-212">int</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-213">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-213">ID number to identify the session.</span></span> <span data-ttu-id="ae4ae-214">与 ReplaceDialogIdTime 结合使用来唯一地标识此会话替换的会话。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-214">Used in conjunction with ReplaceDialogIdTime to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="ae4ae-215">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-215">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ae-216"><strong>ReplacesDialogId</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-216"><strong>ReplacesDialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-217">varchar （775）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-217">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-p119">会话取代的 SIP 对话 ID。格式如下：</span><span class="sxs-lookup"><span data-stu-id="ae4ae-p119">SIP dialog ID the session replaces. The format of the is:</span></span></p>
<p><span data-ttu-id="ae4ae-220">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="ae4ae-220">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ae-221"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-221"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-222">位</span><span class="sxs-lookup"><span data-stu-id="ae4ae-222">bit</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-223">指示会议服务器是否已启动会话。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-223">Indicates whether the session was started by the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ae-224"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-224"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-225">位</span><span class="sxs-lookup"><span data-stu-id="ae4ae-225">bit</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-226">指示会议服务器是否已结束会话。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-226">Indicates whether the session was ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ae-227"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-227"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-228">位</span><span class="sxs-lookup"><span data-stu-id="ae4ae-228">bit</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-229">指示用户是否是从内部网络登录的。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-229">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ae-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-231">datetime</span><span class="sxs-lookup"><span data-stu-id="ae4ae-231">datetime</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-p120">对第一个 INVITE 消息的响应时间。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-p120">Time of the response to the first INVITE message. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ae-235"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-235"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-236">int</span><span class="sxs-lookup"><span data-stu-id="ae4ae-236">int</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-p121">会话邀请的 SIP 响应代码。此字段通常由来自会话中的初始 INVITE 消息生成的数据填充。如果没有 INVITE 消息，则该字段由第一个相关 SIP 消息（BYE、CANCEL、MESSAGE 或 INFO）的日期和时间填充。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-p121">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ae-240"><strong>DiagnosticId</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-240"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-241">int</span><span class="sxs-lookup"><span data-stu-id="ae4ae-241">int</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-242">从会话 SIP 标头捕获的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-242">Diagnostic ID captured from session SIP headers.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ae-243"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-243"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-244">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-244">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-245">会话的内容类型。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-245">Content type for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ae-246"><strong>前端</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-246"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-247">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-247">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-248">捕获会话数据的前端服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-248">FQDN of the Front End server that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ae-249"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-249"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-250">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-250">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-251">已捕获会话的数据的池的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-251">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ae-252"><strong>MediationServer</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-252"><strong>MediationServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-253">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-253">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-254">参与会话的用户所使用的中介服务器。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-254">Mediation Server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ae-255"><strong>网关</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-255"><strong>Gateway</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-256">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-256">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-257">参与会话的用户所使用的网关。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-257">Gateway used by the user who participated the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ae-258"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-258"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-259">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="ae4ae-259">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-260">参与会话的用户所使用的边缘服务器的 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ae4ae-260">FQDN of the Edge server used by the user who participated in the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ae4ae-261"><strong>UserFlag</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-261"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-262">smallint</span><span class="sxs-lookup"><span data-stu-id="ae4ae-262">smallint</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-p122">指示参与会话的用户的属性。以下是允许的属性定义：</span><span class="sxs-lookup"><span data-stu-id="ae4ae-p122">Indicates the attributes of the user who participated in the session. The following attribute definitions allowed:</span></span></p>
<p><span data-ttu-id="ae4ae-265">0x01 - 与桌面电话集成</span><span class="sxs-lookup"><span data-stu-id="ae4ae-265">0x01 - Integrated with desktop phone</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ae4ae-266"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="ae4ae-266"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="ae4ae-267">smallint</span><span class="sxs-lookup"><span data-stu-id="ae4ae-267">smallint</span></span></p></td>
<td><p><span data-ttu-id="ae4ae-p123">指示呼叫属性。以下是允许的属性定义：</span><span class="sxs-lookup"><span data-stu-id="ae4ae-p123">Indicates the call attributes. The following attribute definitions are allowed:</span></span></p>
<p><span data-ttu-id="ae4ae-270">0x01 - 重试会话</span><span class="sxs-lookup"><span data-stu-id="ae4ae-270">0x01 - Retried Session0</span></span></p>
<p><span data-ttu-id="ae4ae-271">0x02 - 代表响应组的代理进行的呼叫</span><span class="sxs-lookup"><span data-stu-id="ae4ae-271">x02 - A call made by agent on behalf of a Response Group</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

