---
title: Lync Server 2013： McuJoinsAndLeaves 视图
description: Lync Server 2013： McuJoinsAndLeaves 视图。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7f2f51c340d5bd4824a6e8eff1a0da172a758c9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556488"
---
# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="5f3c8-103">Lync Server 2013 中的 McuJoinsAndLeaves 视图</span><span class="sxs-lookup"><span data-stu-id="5f3c8-103">McuJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f3c8-104">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="5f3c8-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="5f3c8-105">McuJoinsAndLeaves 视图存储有关用户加入和离开某个会议服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-105">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="5f3c8-106">此视图中的每条记录都包含有关用户加入或离开与会议服务器的组合的呼叫详细信息。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-106">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="5f3c8-107">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f3c8-108">列</span><span class="sxs-lookup"><span data-stu-id="5f3c8-108">Column</span></span></th>
<th><span data-ttu-id="5f3c8-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="5f3c8-109">Data Type</span></span></th>
<th><span data-ttu-id="5f3c8-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="5f3c8-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f3c8-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5f3c8-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5f3c8-112">datetime</span><span class="sxs-lookup"><span data-stu-id="5f3c8-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="5f3c8-113">会议实例的时间。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-113">Time of conference instance.</span></span> <span data-ttu-id="5f3c8-114">与 SessionIdSeq 结合使用来唯一地标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-114">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="5f3c8-115">有关详细信息，请参阅 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f3c8-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5f3c8-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5f3c8-117">int</span><span class="sxs-lookup"><span data-stu-id="5f3c8-117">int</span></span></p></td>
<td><p><span data-ttu-id="5f3c8-118">用于标识会议实例的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-118">ID number to identify the conference instance.</span></span> <span data-ttu-id="5f3c8-119">与 SessionIdTime 结合使用来唯一地标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-119">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="5f3c8-120">有关详细信息，请参阅 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-120">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f3c8-121"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="5f3c8-121"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5f3c8-122">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="5f3c8-122">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f3c8-123">用户连接到的会议服务器的 URI。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-123">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f3c8-124"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5f3c8-124"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f3c8-125">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="5f3c8-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f3c8-126">用户连接到的会议服务器的 URI。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-126">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="5f3c8-127">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-127">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f3c8-128"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="5f3c8-128"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5f3c8-129">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="5f3c8-129">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5f3c8-130">已捕获其会议服务器加入/离开信息的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-130">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f3c8-131"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5f3c8-131"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f3c8-132">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="5f3c8-132">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f3c8-133">已捕获其会议服务器加入/离开信息的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-133">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="5f3c8-134">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-134">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f3c8-135"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="5f3c8-135"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5f3c8-136">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="5f3c8-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f3c8-137">已捕获其会议服务器加入/离开信息的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-137">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="5f3c8-138">有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a> 。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-138">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f3c8-139"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="5f3c8-139"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="5f3c8-140">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="5f3c8-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f3c8-141">已捕获其会议服务器加入/离开信息的用户所使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-141">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f3c8-142"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="5f3c8-142"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f3c8-143">int</span><span class="sxs-lookup"><span data-stu-id="5f3c8-143">int</span></span></p></td>
<td><p><span data-ttu-id="5f3c8-144">已捕获其会议服务器加入/离开信息的用户所使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-144">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="5f3c8-145">有关更多详细信息，请参阅 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-145">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f3c8-146"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="5f3c8-146"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="5f3c8-147">nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="5f3c8-147">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="5f3c8-148">已捕获其会议服务器加入/离开信息的用户所使用的客户端类别的名称。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-148">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f3c8-149"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="5f3c8-149"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="5f3c8-150">int</span><span class="sxs-lookup"><span data-stu-id="5f3c8-150">int</span></span></p></td>
<td><p><span data-ttu-id="5f3c8-151">唯一标识同时登录到多台设备的用户的用户/设备组合。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-151">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f3c8-152"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="5f3c8-152"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="5f3c8-153">位</span><span class="sxs-lookup"><span data-stu-id="5f3c8-153">bit</span></span></p></td>
<td><p><span data-ttu-id="5f3c8-154">表示用户是否为内部用户的位。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-154">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f3c8-155"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5f3c8-155"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5f3c8-156">datetime</span><span class="sxs-lookup"><span data-stu-id="5f3c8-156">datetime</span></span></p></td>
<td><p><span data-ttu-id="5f3c8-157">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-157">Time of session request.</span></span> <span data-ttu-id="5f3c8-158">与 SessionIdSeq 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-158">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="5f3c8-159">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-159">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f3c8-160"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5f3c8-160"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5f3c8-161">int</span><span class="sxs-lookup"><span data-stu-id="5f3c8-161">int</span></span></p></td>
<td><p><span data-ttu-id="5f3c8-162">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-162">ID number to identify the session.</span></span> <span data-ttu-id="5f3c8-163">与 SessionIdTime 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-163">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="5f3c8-164">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-164">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f3c8-165"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="5f3c8-165"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="5f3c8-166">varchar (775) </span><span class="sxs-lookup"><span data-stu-id="5f3c8-166">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="5f3c8-p110">会话的 SIP 对话 ID。格式为：dialog;from-tag;to-tag。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-p110">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f3c8-169"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="5f3c8-169"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5f3c8-170">datetime</span><span class="sxs-lookup"><span data-stu-id="5f3c8-170">datetime</span></span></p></td>
<td><p><span data-ttu-id="5f3c8-171">用户加入会议服务器的时间。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-171">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f3c8-172"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="5f3c8-172"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5f3c8-173">datetime</span><span class="sxs-lookup"><span data-stu-id="5f3c8-173">datetime</span></span></p></td>
<td><p><span data-ttu-id="5f3c8-174">用户离开会议服务器的时间。</span><span class="sxs-lookup"><span data-stu-id="5f3c8-174">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

