---
title: Lync Server 2013： FocusJoinsAndLeaves 视图
description: Lync Server 2013： FocusJoinsAndLeaves 视图。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6f68c44461e378e9ebedce1305ee6b384a7a8a7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577448"
---
# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="dc44b-103">Lync Server 2013 中的 FocusJoinsAndLeaves 视图</span><span class="sxs-lookup"><span data-stu-id="dc44b-103">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc44b-104">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="dc44b-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="dc44b-105">FocusJoinsAndLeaves 视图存储有关加入和离开某会议的信息。</span><span class="sxs-lookup"><span data-stu-id="dc44b-105">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="dc44b-106">每个会议在此视图中由一条在每次用户加入和离开该会议时编写的记录表示。</span><span class="sxs-lookup"><span data-stu-id="dc44b-106">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="dc44b-107">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="dc44b-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dc44b-108">列</span><span class="sxs-lookup"><span data-stu-id="dc44b-108">Column</span></span></th>
<th><span data-ttu-id="dc44b-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="dc44b-109">Data Type</span></span></th>
<th><span data-ttu-id="dc44b-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="dc44b-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dc44b-111"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="dc44b-111"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dc44b-112">datetime</span><span class="sxs-lookup"><span data-stu-id="dc44b-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="dc44b-113">会议实例的时间。</span><span class="sxs-lookup"><span data-stu-id="dc44b-113">Time of conference instance.</span></span> <span data-ttu-id="dc44b-114">与 SessionIdSeq 结合使用来唯一地标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="dc44b-114">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="dc44b-115">有关详细信息，请参阅 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="dc44b-115">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc44b-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="dc44b-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="dc44b-117">int</span><span class="sxs-lookup"><span data-stu-id="dc44b-117">int</span></span></p></td>
<td><p><span data-ttu-id="dc44b-118">用于标识会议实例的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="dc44b-118">ID number to identify the conference instance.</span></span> <span data-ttu-id="dc44b-119">与 SessionIdTime 结合使用来唯一地标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="dc44b-119">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="dc44b-120">有关详细信息，请参阅 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="dc44b-120">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc44b-121"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="dc44b-121"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="dc44b-122">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="dc44b-122">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="dc44b-123">已捕获其会议加入/离开信息的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="dc44b-123">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc44b-124"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="dc44b-124"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="dc44b-125">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="dc44b-125">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dc44b-126">已捕获其会议加入/离开信息的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="dc44b-126">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="dc44b-127">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="dc44b-127">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc44b-128"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="dc44b-128"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="dc44b-129">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="dc44b-129">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dc44b-130">已捕获其会议加入/离开信息的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="dc44b-130">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="dc44b-131">有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a> 。</span><span class="sxs-lookup"><span data-stu-id="dc44b-131">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc44b-132"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="dc44b-132"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="dc44b-133">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="dc44b-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="dc44b-134">已捕获其会议加入/离开信息的用户的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="dc44b-134">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc44b-135"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="dc44b-135"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="dc44b-136">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="dc44b-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dc44b-137">由已捕获其会议加入/离开信息的用户使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="dc44b-137">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc44b-138"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="dc44b-138"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="dc44b-139">int</span><span class="sxs-lookup"><span data-stu-id="dc44b-139">int</span></span></p></td>
<td><p><span data-ttu-id="dc44b-140">由已捕获其会议加入/离开信息的用户使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="dc44b-140">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="dc44b-141">有关更多详细信息，请参阅 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="dc44b-141">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc44b-142"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="dc44b-142"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="dc44b-143">nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="dc44b-143">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="dc44b-144">由已捕获其会议加入/离开信息的用户使用的客户端的类别名称。</span><span class="sxs-lookup"><span data-stu-id="dc44b-144">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc44b-145"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="dc44b-145"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="dc44b-146">int</span><span class="sxs-lookup"><span data-stu-id="dc44b-146">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc44b-147"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="dc44b-147"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="dc44b-148">位</span><span class="sxs-lookup"><span data-stu-id="dc44b-148">bit</span></span></p></td>
<td><p><span data-ttu-id="dc44b-149">表示用户是否为内部用户的位。</span><span class="sxs-lookup"><span data-stu-id="dc44b-149">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc44b-150"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="dc44b-150"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dc44b-151">datetime</span><span class="sxs-lookup"><span data-stu-id="dc44b-151">datetime</span></span></p></td>
<td><p><span data-ttu-id="dc44b-152">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="dc44b-152">Time of session request.</span></span> <span data-ttu-id="dc44b-153">与 SessionIdSeq 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="dc44b-153">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="dc44b-154">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="dc44b-154">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc44b-155"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="dc44b-155"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="dc44b-156">int</span><span class="sxs-lookup"><span data-stu-id="dc44b-156">int</span></span></p></td>
<td><p><span data-ttu-id="dc44b-157">如果用户同时在多台计算机或设备登录，则使用 UserInstance 来唯一地标识该用户/设备组合。</span><span class="sxs-lookup"><span data-stu-id="dc44b-157">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc44b-158"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="dc44b-158"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="dc44b-159">varchar (775) </span><span class="sxs-lookup"><span data-stu-id="dc44b-159">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="dc44b-p108">会话的 SIP 对话 ID。格式为：dialog;from-tag;to-tag。</span><span class="sxs-lookup"><span data-stu-id="dc44b-p108">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc44b-162"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="dc44b-162"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dc44b-163">datetime</span><span class="sxs-lookup"><span data-stu-id="dc44b-163">datetime</span></span></p></td>
<td><p><span data-ttu-id="dc44b-164">用户加入会议的时间。</span><span class="sxs-lookup"><span data-stu-id="dc44b-164">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dc44b-165"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="dc44b-165"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dc44b-166">datetime</span><span class="sxs-lookup"><span data-stu-id="dc44b-166">datetime</span></span></p></td>
<td><p><span data-ttu-id="dc44b-167">用户离开会议的时间。</span><span class="sxs-lookup"><span data-stu-id="dc44b-167">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dc44b-168"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="dc44b-168"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="dc44b-169">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="dc44b-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="dc44b-170">用户在会议中的角色，如演示者或与会者。</span><span class="sxs-lookup"><span data-stu-id="dc44b-170">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

