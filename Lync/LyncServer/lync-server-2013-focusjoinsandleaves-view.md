---
title: Lync Server 2013： FocusJoinsAndLeaves 视图
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
ms.openlocfilehash: 9d7cc1da4f5923a7c42e74c9069054863f1d99a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722402"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="1f961-102">Lync Server 2013 中的 FocusJoinsAndLeaves 视图</span><span class="sxs-lookup"><span data-stu-id="1f961-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1f961-103">_**主题上次修改时间：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="1f961-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="1f961-104">FocusJoinsAndLeaves 视图存储有关加入和离开一次会议的信息的信息。</span><span class="sxs-lookup"><span data-stu-id="1f961-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="1f961-105">每个会议在用户加入和离开会议时编写的记录在此视图中表示。</span><span class="sxs-lookup"><span data-stu-id="1f961-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="1f961-106">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="1f961-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1f961-107">列</span><span class="sxs-lookup"><span data-stu-id="1f961-107">Column</span></span></th>
<th><span data-ttu-id="1f961-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="1f961-108">Data Type</span></span></th>
<th><span data-ttu-id="1f961-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="1f961-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1f961-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="1f961-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1f961-111">datetime</span><span class="sxs-lookup"><span data-stu-id="1f961-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="1f961-112">会议实例的时间。</span><span class="sxs-lookup"><span data-stu-id="1f961-112">Time of conference instance.</span></span> <span data-ttu-id="1f961-113">与 SessionIdSeq 结合使用以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="1f961-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="1f961-114">有关详细信息，请参阅<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="1f961-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f961-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1f961-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1f961-116">int</span><span class="sxs-lookup"><span data-stu-id="1f961-116">int</span></span></p></td>
<td><p><span data-ttu-id="1f961-117">标识会议实例的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="1f961-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="1f961-118">与 SessionIdTime 结合使用以唯一标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="1f961-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="1f961-119">有关详细信息，请参阅<a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a>的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="1f961-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f961-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="1f961-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="1f961-121">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="1f961-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="1f961-122">已捕获其会议加入/离开信息的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="1f961-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f961-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="1f961-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="1f961-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1f961-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1f961-125">已捕获其会议加入/离开信息的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="1f961-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="1f961-126">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="1f961-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f961-127"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="1f961-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="1f961-128">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1f961-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1f961-129">已捕获其会议加入/离开信息的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="1f961-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="1f961-130">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="1f961-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f961-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="1f961-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="1f961-132">标识符</span><span class="sxs-lookup"><span data-stu-id="1f961-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="1f961-133">已捕获其会议加入/离开信息的用户的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="1f961-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f961-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="1f961-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="1f961-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1f961-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1f961-136">已捕获其会议加入/离开信息的用户使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="1f961-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f961-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="1f961-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="1f961-138">int</span><span class="sxs-lookup"><span data-stu-id="1f961-138">int</span></span></p></td>
<td><p><span data-ttu-id="1f961-139">已捕获会议加入/离开信息的用户使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="1f961-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="1f961-140">有关详细信息，请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="1f961-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f961-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="1f961-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="1f961-142">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="1f961-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="1f961-143">已捕获会议加入/离开信息的用户所使用的客户端类别的名称。</span><span class="sxs-lookup"><span data-stu-id="1f961-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f961-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="1f961-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="1f961-145">int</span><span class="sxs-lookup"><span data-stu-id="1f961-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f961-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="1f961-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="1f961-147">bit</span><span class="sxs-lookup"><span data-stu-id="1f961-147">bit</span></span></p></td>
<td><p><span data-ttu-id="1f961-148">表示用户是否为内部用户的位。</span><span class="sxs-lookup"><span data-stu-id="1f961-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f961-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="1f961-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1f961-150">datetime</span><span class="sxs-lookup"><span data-stu-id="1f961-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="1f961-151">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="1f961-151">Time of session request.</span></span> <span data-ttu-id="1f961-152">与 SessionIdSeq 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="1f961-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="1f961-153">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="1f961-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f961-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1f961-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1f961-155">int</span><span class="sxs-lookup"><span data-stu-id="1f961-155">int</span></span></p></td>
<td><p><span data-ttu-id="1f961-156">如果用户同时在多台计算机或设备上登录，则 UserInstance 用于唯一标识用户/设备组合。</span><span class="sxs-lookup"><span data-stu-id="1f961-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f961-157"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="1f961-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="1f961-158">varchar （775）</span><span class="sxs-lookup"><span data-stu-id="1f961-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="1f961-159">会话的 SIP 对话框 ID。</span><span class="sxs-lookup"><span data-stu-id="1f961-159">SIP dialog ID of the session.</span></span> <span data-ttu-id="1f961-160">格式为：对话框; 从-标签; 到-标记。</span><span class="sxs-lookup"><span data-stu-id="1f961-160">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f961-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="1f961-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1f961-162">datetime</span><span class="sxs-lookup"><span data-stu-id="1f961-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="1f961-163">用户加入会议的时间。</span><span class="sxs-lookup"><span data-stu-id="1f961-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1f961-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="1f961-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1f961-165">datetime</span><span class="sxs-lookup"><span data-stu-id="1f961-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="1f961-166">用户离开会议的时间。</span><span class="sxs-lookup"><span data-stu-id="1f961-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1f961-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="1f961-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="1f961-168">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1f961-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1f961-169">用户在会议中的角色，如 "演示者" 或 "与会者"。</span><span class="sxs-lookup"><span data-stu-id="1f961-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

