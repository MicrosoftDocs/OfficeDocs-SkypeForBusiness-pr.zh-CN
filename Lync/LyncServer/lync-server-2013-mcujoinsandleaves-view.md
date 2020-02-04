---
title: Lync Server 2013： McuJoinsAndLeaves 视图
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
ms.openlocfilehash: d339df5b3b591cbf67376c36c5e0e4261c390851
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="92a6f-102">Lync Server 2013 中的 McuJoinsAndLeaves 视图</span><span class="sxs-lookup"><span data-stu-id="92a6f-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92a6f-103">_**主题上次修改时间：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="92a6f-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="92a6f-104">McuJoinsAndLeaves 视图存储有关用户为一个会议服务器加入和离开信息的信息。</span><span class="sxs-lookup"><span data-stu-id="92a6f-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="92a6f-105">此视图中的每条记录包含有关用户加入或离开和会议服务器的一个组合的调用详细信息。</span><span class="sxs-lookup"><span data-stu-id="92a6f-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="92a6f-106">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="92a6f-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="92a6f-107">列</span><span class="sxs-lookup"><span data-stu-id="92a6f-107">Column</span></span></th>
<th><span data-ttu-id="92a6f-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="92a6f-108">Data Type</span></span></th>
<th><span data-ttu-id="92a6f-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="92a6f-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="92a6f-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="92a6f-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="92a6f-111">datetime</span><span class="sxs-lookup"><span data-stu-id="92a6f-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="92a6f-112">会议实例的时间。</span><span class="sxs-lookup"><span data-stu-id="92a6f-112">Time of conference instance.</span></span> <span data-ttu-id="92a6f-113">与 SessionIdSeq 结合使用以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="92a6f-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="92a6f-114">有关详细信息，请参阅<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="92a6f-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92a6f-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="92a6f-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="92a6f-116">int</span><span class="sxs-lookup"><span data-stu-id="92a6f-116">int</span></span></p></td>
<td><p><span data-ttu-id="92a6f-117">标识会议实例的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="92a6f-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="92a6f-118">与 SessionIdTime 结合使用以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="92a6f-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="92a6f-119">有关详细信息，请参阅<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="92a6f-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92a6f-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="92a6f-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="92a6f-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="92a6f-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="92a6f-122">用户连接到的会议服务器的 URI。</span><span class="sxs-lookup"><span data-stu-id="92a6f-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92a6f-123"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="92a6f-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="92a6f-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="92a6f-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="92a6f-125">用户连接到的会议服务器的 URI。</span><span class="sxs-lookup"><span data-stu-id="92a6f-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="92a6f-126">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="92a6f-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92a6f-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="92a6f-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="92a6f-128">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="92a6f-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="92a6f-129">已捕获其会议服务器加入/离开信息的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="92a6f-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92a6f-130"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="92a6f-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="92a6f-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="92a6f-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="92a6f-132">已捕获其会议服务器加入/离开信息的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="92a6f-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="92a6f-133">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="92a6f-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92a6f-134"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="92a6f-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="92a6f-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="92a6f-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="92a6f-136">已捕获其会议服务器加入/离开信息的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="92a6f-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="92a6f-137">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="92a6f-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92a6f-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="92a6f-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="92a6f-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="92a6f-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="92a6f-140">已捕获会议服务器加入/离开信息的用户所使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="92a6f-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92a6f-141"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="92a6f-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="92a6f-142">int</span><span class="sxs-lookup"><span data-stu-id="92a6f-142">int</span></span></p></td>
<td><p><span data-ttu-id="92a6f-143">已捕获会议服务器加入/离开信息的用户所使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="92a6f-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="92a6f-144">有关详细信息，请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="92a6f-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92a6f-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="92a6f-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="92a6f-146">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="92a6f-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="92a6f-147">已捕获其会议服务器加入/离开信息的用户所使用的客户端类别的名称。</span><span class="sxs-lookup"><span data-stu-id="92a6f-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92a6f-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="92a6f-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="92a6f-149">int</span><span class="sxs-lookup"><span data-stu-id="92a6f-149">int</span></span></p></td>
<td><p><span data-ttu-id="92a6f-150">为同时登录到多台设备的用户唯一标识用户/设备组合。</span><span class="sxs-lookup"><span data-stu-id="92a6f-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92a6f-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="92a6f-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="92a6f-152">bit</span><span class="sxs-lookup"><span data-stu-id="92a6f-152">bit</span></span></p></td>
<td><p><span data-ttu-id="92a6f-153">表示用户是否为内部用户的位。</span><span class="sxs-lookup"><span data-stu-id="92a6f-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92a6f-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="92a6f-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="92a6f-155">datetime</span><span class="sxs-lookup"><span data-stu-id="92a6f-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="92a6f-156">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="92a6f-156">Time of session request.</span></span> <span data-ttu-id="92a6f-157">与 SessionIdSeq 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="92a6f-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="92a6f-158">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="92a6f-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92a6f-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="92a6f-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="92a6f-160">int</span><span class="sxs-lookup"><span data-stu-id="92a6f-160">int</span></span></p></td>
<td><p><span data-ttu-id="92a6f-161">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="92a6f-161">ID number to identify the session.</span></span> <span data-ttu-id="92a6f-162">与 SessionIdTime 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="92a6f-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="92a6f-163">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="92a6f-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92a6f-164"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="92a6f-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="92a6f-165">varchar （775）</span><span class="sxs-lookup"><span data-stu-id="92a6f-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="92a6f-166">会话的 SIP 对话框 ID。</span><span class="sxs-lookup"><span data-stu-id="92a6f-166">SIP dialog ID of the session.</span></span> <span data-ttu-id="92a6f-167">格式为：对话框; 从-标签; 到-标记。</span><span class="sxs-lookup"><span data-stu-id="92a6f-167">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="92a6f-168"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="92a6f-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="92a6f-169">datetime</span><span class="sxs-lookup"><span data-stu-id="92a6f-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="92a6f-170">用户加入会议服务器的时间。</span><span class="sxs-lookup"><span data-stu-id="92a6f-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="92a6f-171"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="92a6f-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="92a6f-172">datetime</span><span class="sxs-lookup"><span data-stu-id="92a6f-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="92a6f-173">用户离开会议服务器的时间。</span><span class="sxs-lookup"><span data-stu-id="92a6f-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

