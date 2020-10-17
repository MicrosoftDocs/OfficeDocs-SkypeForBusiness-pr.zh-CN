---
title: Lync Server 2013： CDR 视图列表
description: Lync Server 2013： CDR 视图的列表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f1c29560851c0e4466dbf4316bf0b1335906d4e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48550078"
---
# <a name="list-of-cdr-views-in-lync-server-2013"></a><span data-ttu-id="10d7d-103">Lync Server 2013 中的 CDR 视图列表</span><span class="sxs-lookup"><span data-stu-id="10d7d-103">List of CDR views in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="10d7d-104">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="10d7d-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="10d7d-105">可通过视图轻松访问有关用于从 CDR 数据库返回数据的最常见方案的信息。</span><span class="sxs-lookup"><span data-stu-id="10d7d-105">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="10d7d-106">建议使用视图生成自定义报告，而不是使用实际的 CDR 数据库表;这是因为数据库视图更有可能与 Lync Server 将来的版本保持向后兼容。</span><span class="sxs-lookup"><span data-stu-id="10d7d-106">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that’s because the database views are more likely to maintain backwards compatibility with future releases of Lync Server.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="10d7d-107">视图名称</span><span class="sxs-lookup"><span data-stu-id="10d7d-107">View Name</span></span></th>
<th><span data-ttu-id="10d7d-108">说明</span><span class="sxs-lookup"><span data-stu-id="10d7d-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="10d7d-109"><a href="lync-server-2013-clientversions-view.md">Lync Server 2013 中的 ClientVersions 视图</a></span><span class="sxs-lookup"><span data-stu-id="10d7d-109"><a href="lync-server-2013-clientversions-view.md">ClientVersions view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="10d7d-110">返回通信会话中使用的客户端软件/设备的相关信息。</span><span class="sxs-lookup"><span data-stu-id="10d7d-110">Returns information about the client software/devices used in a communication session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10d7d-111"><a href="lync-server-2013-conferencemessagecount-view.md">Lync Server 2013 中的 ConferenceMessageCount 视图</a></span><span class="sxs-lookup"><span data-stu-id="10d7d-111"><a href="lync-server-2013-conferencemessagecount-view.md">ConferenceMessageCount view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="10d7d-112">返回会议中的用户发送的消息数的相关信息。</span><span class="sxs-lookup"><span data-stu-id="10d7d-112">Returns information about the number of messages sent by users in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10d7d-113"><a href="lync-server-2013-conferences-view.md">Lync Server 2013 中的会议视图</a></span><span class="sxs-lookup"><span data-stu-id="10d7d-113"><a href="lync-server-2013-conferences-view.md">Conferences view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="10d7d-114">返回会议信息，包括开始时间、结束时间和会议组织者。</span><span class="sxs-lookup"><span data-stu-id="10d7d-114">Returns conference information, including start time, end time, and conference organizer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10d7d-115"><a href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013 中的 ConferenceSessionDetails 视图</a></span><span class="sxs-lookup"><span data-stu-id="10d7d-115"><a href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="10d7d-116">返回所有会议会话的会话详细信息，包括开始和结束时间、用户 ID、响应代码和诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="10d7d-116">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10d7d-117"><a href="lync-server-2013-conferenceuris-view.md">Lync Server 2013 中的 ConferenceUris 视图</a></span><span class="sxs-lookup"><span data-stu-id="10d7d-117"><a href="lync-server-2013-conferenceuris-view.md">ConferenceUris view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="10d7d-118">返回会议中使用的会议 URI 的相关信息</span><span class="sxs-lookup"><span data-stu-id="10d7d-118">Returns information about conference URIs used in a conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10d7d-119"><a href="lync-server-2013-errorreport-view.md">Lync Server 2013 中的 ErrorReport 视图</a></span><span class="sxs-lookup"><span data-stu-id="10d7d-119"><a href="lync-server-2013-errorreport-view.md">ErrorReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="10d7d-120">返回会话期间发生的错误的相关信息。</span><span class="sxs-lookup"><span data-stu-id="10d7d-120">Returns information about errors that occurred during a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10d7d-121"><a href="lync-server-2013-filetransfers-view.md">Lync Server 2013 中的 FileTransfers 视图</a></span><span class="sxs-lookup"><span data-stu-id="10d7d-121"><a href="lync-server-2013-filetransfers-view.md">FileTransfers view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="10d7d-122">返回文件传输会话的相关信息，包括文件名以及是接受、拒绝还是取消传输。</span><span class="sxs-lookup"><span data-stu-id="10d7d-122">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10d7d-123"><a href="lync-server-2013-focusjoinsandleaves-view.md">Lync Server 2013 中的 FocusJoinsAndLeaves 视图</a></span><span class="sxs-lookup"><span data-stu-id="10d7d-123"><a href="lync-server-2013-focusjoinsandleaves-view.md">FocusJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="10d7d-124">返回有关会议加入和离开活动的信息。</span><span class="sxs-lookup"><span data-stu-id="10d7d-124">Returns information about conference join and leave activities.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10d7d-125"><a href="lync-server-2013-mcujoinsandleaves-view.md">Lync Server 2013 中的 McuJoinsAndLeaves 视图</a></span><span class="sxs-lookup"><span data-stu-id="10d7d-125"><a href="lync-server-2013-mcujoinsandleaves-view.md">McuJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="10d7d-126">返回有关会议加入和离开活动的组合信息（每个会议加入与相应的会议离开配对）。</span><span class="sxs-lookup"><span data-stu-id="10d7d-126">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10d7d-127"><a href="lync-server-2013-mcus-view.md">Lync Server 2013 中的 mcu 视图</a></span><span class="sxs-lookup"><span data-stu-id="10d7d-127"><a href="lync-server-2013-mcus-view.md">Mcus view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="10d7d-128">返回有关会议服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="10d7d-128">Returns information about Conferencing servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10d7d-129"><a href="lync-server-2013-media-view.md">Lync Server 2013 中的媒体视图</a></span><span class="sxs-lookup"><span data-stu-id="10d7d-129"><a href="lync-server-2013-media-view.md">Media view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="10d7d-130">返回有关对等通信会话中使用的媒体类型的信息。</span><span class="sxs-lookup"><span data-stu-id="10d7d-130">Returns information about the types of media used in peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10d7d-131"><a href="lync-server-2013-progressreport-view.md">Lync Server 2013 中的 ProgressReport 视图</a></span><span class="sxs-lookup"><span data-stu-id="10d7d-131"><a href="lync-server-2013-progressreport-view.md">ProgressReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="10d7d-132">返回有关已完成会话的信息。</span><span class="sxs-lookup"><span data-stu-id="10d7d-132">Returns information about completed sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10d7d-133"><a href="lync-server-2013-registration-view.md">Lync Server 2013 中的 "注册" 视图</a></span><span class="sxs-lookup"><span data-stu-id="10d7d-133"><a href="lync-server-2013-registration-view.md">Registration view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="10d7d-134">返回有关使用 Lync Server 进行注册的信息。</span><span class="sxs-lookup"><span data-stu-id="10d7d-134">Returns information about registrations with Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10d7d-135"><a href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 中的 SessionDetails 视图</a></span><span class="sxs-lookup"><span data-stu-id="10d7d-135"><a href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="10d7d-136">返回有关对等会话的信息，包括 VoIP-VoIP 电话呼叫、双方 IM 会话或其他对等通信会话。</span><span class="sxs-lookup"><span data-stu-id="10d7d-136">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="10d7d-137"><a href="lync-server-2013-user-view.md">Lync Server 2013 中的用户视图</a></span><span class="sxs-lookup"><span data-stu-id="10d7d-137"><a href="lync-server-2013-user-view.md">User view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="10d7d-138">返回参与通信会话的用户的相关信息。</span><span class="sxs-lookup"><span data-stu-id="10d7d-138">Returns information about the users who have participated in communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="10d7d-139"><a href="lync-server-2013-voipdetails-view.md">Lync Server 2013 中的 VoIPDetails 视图</a></span><span class="sxs-lookup"><span data-stu-id="10d7d-139"><a href="lync-server-2013-voipdetails-view.md">VoIPDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="10d7d-140">返回至少包括一个 VoIP (Voice over IO) 用户的对等会话的相关信息。</span><span class="sxs-lookup"><span data-stu-id="10d7d-140">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

