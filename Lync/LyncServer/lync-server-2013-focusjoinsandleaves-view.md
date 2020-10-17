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
ms.openlocfilehash: 8b71678b9fbd19cfd52c81976de0955ea39ce9e4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48500819"
---
# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="c2748-102">Lync Server 2013 中的 FocusJoinsAndLeaves 视图</span><span class="sxs-lookup"><span data-stu-id="c2748-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2748-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="c2748-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="c2748-104">FocusJoinsAndLeaves 视图存储有关加入和离开某会议的信息。</span><span class="sxs-lookup"><span data-stu-id="c2748-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="c2748-105">每个会议在此视图中由一条在每次用户加入和离开该会议时编写的记录表示。</span><span class="sxs-lookup"><span data-stu-id="c2748-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="c2748-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c2748-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c2748-107">列</span><span class="sxs-lookup"><span data-stu-id="c2748-107">Column</span></span></th>
<th><span data-ttu-id="c2748-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="c2748-108">Data Type</span></span></th>
<th><span data-ttu-id="c2748-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="c2748-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c2748-110"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="c2748-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c2748-111">datetime</span><span class="sxs-lookup"><span data-stu-id="c2748-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="c2748-112">会议实例的时间。</span><span class="sxs-lookup"><span data-stu-id="c2748-112">Time of conference instance.</span></span> <span data-ttu-id="c2748-113">与 SessionIdSeq 结合使用来唯一地标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="c2748-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="c2748-114">有关详细信息，请参阅 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="c2748-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2748-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c2748-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c2748-116">int</span><span class="sxs-lookup"><span data-stu-id="c2748-116">int</span></span></p></td>
<td><p><span data-ttu-id="c2748-117">用于标识会议实例的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="c2748-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="c2748-118">与 SessionIdTime 结合使用来唯一地标识会议实例。</span><span class="sxs-lookup"><span data-stu-id="c2748-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="c2748-119">有关详细信息，请参阅 <a href="lync-server-2013-conferences-table.md">Lync Server 2013 中</a> 的 "会议" 表。</span><span class="sxs-lookup"><span data-stu-id="c2748-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2748-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="c2748-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="c2748-121">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="c2748-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c2748-122">已捕获其会议加入/离开信息的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="c2748-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2748-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="c2748-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="c2748-124">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="c2748-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c2748-125">已捕获其会议加入/离开信息的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="c2748-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="c2748-126">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="c2748-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2748-127"><strong>UserTenant</strong></span><span class="sxs-lookup"><span data-stu-id="c2748-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="c2748-128">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="c2748-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c2748-129">已捕获其会议加入/离开信息的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="c2748-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="c2748-130">有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a> 。</span><span class="sxs-lookup"><span data-stu-id="c2748-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2748-131"><strong>UserEndpointId</strong></span><span class="sxs-lookup"><span data-stu-id="c2748-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="c2748-132">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="c2748-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="c2748-133">已捕获其会议加入/离开信息的用户的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="c2748-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2748-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="c2748-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="c2748-135">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="c2748-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c2748-136">由已捕获其会议加入/离开信息的用户使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="c2748-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2748-137"><strong>UserClientType</strong></span><span class="sxs-lookup"><span data-stu-id="c2748-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="c2748-138">int</span><span class="sxs-lookup"><span data-stu-id="c2748-138">int</span></span></p></td>
<td><p><span data-ttu-id="c2748-139">由已捕获其会议加入/离开信息的用户使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="c2748-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="c2748-140">有关更多详细信息，请参阅 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="c2748-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2748-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="c2748-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="c2748-142">nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="c2748-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="c2748-143">由已捕获其会议加入/离开信息的用户使用的客户端的类别名称。</span><span class="sxs-lookup"><span data-stu-id="c2748-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2748-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="c2748-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="c2748-145">int</span><span class="sxs-lookup"><span data-stu-id="c2748-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2748-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="c2748-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="c2748-147">位</span><span class="sxs-lookup"><span data-stu-id="c2748-147">bit</span></span></p></td>
<td><p><span data-ttu-id="c2748-148">表示用户是否为内部用户的位。</span><span class="sxs-lookup"><span data-stu-id="c2748-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2748-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="c2748-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c2748-150">datetime</span><span class="sxs-lookup"><span data-stu-id="c2748-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="c2748-151">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="c2748-151">Time of session request.</span></span> <span data-ttu-id="c2748-152">与 SessionIdSeq 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="c2748-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="c2748-153">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="c2748-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2748-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c2748-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c2748-155">int</span><span class="sxs-lookup"><span data-stu-id="c2748-155">int</span></span></p></td>
<td><p><span data-ttu-id="c2748-156">如果用户同时在多台计算机或设备登录，则使用 UserInstance 来唯一地标识该用户/设备组合。</span><span class="sxs-lookup"><span data-stu-id="c2748-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2748-157"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="c2748-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="c2748-158">varchar (775) </span><span class="sxs-lookup"><span data-stu-id="c2748-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="c2748-p108">会话的 SIP 对话 ID。格式为：dialog;from-tag;to-tag。</span><span class="sxs-lookup"><span data-stu-id="c2748-p108">SIP dialog ID of the session. The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2748-161"><strong>UserJoinTime</strong></span><span class="sxs-lookup"><span data-stu-id="c2748-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c2748-162">datetime</span><span class="sxs-lookup"><span data-stu-id="c2748-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="c2748-163">用户加入会议的时间。</span><span class="sxs-lookup"><span data-stu-id="c2748-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c2748-164"><strong>UserLeaveTime</strong></span><span class="sxs-lookup"><span data-stu-id="c2748-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c2748-165">datetime</span><span class="sxs-lookup"><span data-stu-id="c2748-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="c2748-166">用户离开会议的时间。</span><span class="sxs-lookup"><span data-stu-id="c2748-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c2748-167"><strong>UserRole</strong></span><span class="sxs-lookup"><span data-stu-id="c2748-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="c2748-168">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="c2748-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c2748-169">用户在会议中的角色，如演示者或与会者。</span><span class="sxs-lookup"><span data-stu-id="c2748-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

