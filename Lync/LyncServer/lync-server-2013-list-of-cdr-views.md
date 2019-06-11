---
title: 'Lync Server 2013: CDR 视图列表'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 112e565c07c685c1ecdf5db1d8a2de8717ba959e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="list-of-cdr-views-in-lync-server-2013"></a><span data-ttu-id="d7fda-102">Lync Server 2013 中的 CDR 视图列表</span><span class="sxs-lookup"><span data-stu-id="d7fda-102">List of CDR views in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d7fda-103">_**主题上次修改时间:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d7fda-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d7fda-104">视图提供了一种简单的方法来访问有关用于从 CDR 数据库返回数据的最常见方案的信息。</span><span class="sxs-lookup"><span data-stu-id="d7fda-104">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="d7fda-105">建议使用视图生成自定义报表, 而不是使用实际的 CDR 数据库表;这是因为数据库视图更有可能保持与 Lync Server 未来版本的向后兼容性。</span><span class="sxs-lookup"><span data-stu-id="d7fda-105">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that’s because the database views are more likely to maintain backwards compatibility with future releases of Lync Server.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d7fda-106">视图名称</span><span class="sxs-lookup"><span data-stu-id="d7fda-106">View Name</span></span></th>
<th><span data-ttu-id="d7fda-107">说明</span><span class="sxs-lookup"><span data-stu-id="d7fda-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d7fda-108"><a href="lync-server-2013-clientversions-view.md">Lync Server 2013 中的 ClientVersions 视图</a></span><span class="sxs-lookup"><span data-stu-id="d7fda-108"><a href="lync-server-2013-clientversions-view.md">ClientVersions view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fda-109">返回有关在通信会话中使用的客户端软件/设备的信息。</span><span class="sxs-lookup"><span data-stu-id="d7fda-109">Returns information about the client software/devices used in a communication session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fda-110"><a href="lync-server-2013-conferencemessagecount-view.md">Lync Server 2013 中的 ConferenceMessageCount 视图</a></span><span class="sxs-lookup"><span data-stu-id="d7fda-110"><a href="lync-server-2013-conferencemessagecount-view.md">ConferenceMessageCount view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fda-111">返回有关会议中用户发送的邮件数的信息。</span><span class="sxs-lookup"><span data-stu-id="d7fda-111">Returns information about the number of messages sent by users in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fda-112"><a href="lync-server-2013-conferences-view.md">Lync Server 2013 中的 "会议" 视图</a></span><span class="sxs-lookup"><span data-stu-id="d7fda-112"><a href="lync-server-2013-conferences-view.md">Conferences view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fda-113">返回会议信息, 包括 "开始时间"、"结束时间" 和 "会议组织者"。</span><span class="sxs-lookup"><span data-stu-id="d7fda-113">Returns conference information, including start time, end time, and conference organizer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fda-114"><a href="lync-server-2013-conferencesessiondetails-view.md">Lync Server 2013 中的 ConferenceSessionDetails 视图</a></span><span class="sxs-lookup"><span data-stu-id="d7fda-114"><a href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fda-115">返回所有会议会话的会话详细信息, 包括开始和结束时间、用户 Id、响应代码和诊断 Id。</span><span class="sxs-lookup"><span data-stu-id="d7fda-115">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fda-116"><a href="lync-server-2013-conferenceuris-view.md">Lync Server 2013 中的 ConferenceUris 视图</a></span><span class="sxs-lookup"><span data-stu-id="d7fda-116"><a href="lync-server-2013-conferenceuris-view.md">ConferenceUris view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fda-117">返回有关会议中使用的会议 Uri 的信息</span><span class="sxs-lookup"><span data-stu-id="d7fda-117">Returns information about conference URIs used in a conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fda-118"><a href="lync-server-2013-errorreport-view.md">Lync Server 2013 中的 ErrorReport 视图</a></span><span class="sxs-lookup"><span data-stu-id="d7fda-118"><a href="lync-server-2013-errorreport-view.md">ErrorReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fda-119">返回有关会话期间发生的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="d7fda-119">Returns information about errors that occurred during a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fda-120"><a href="lync-server-2013-filetransfers-view.md">Lync Server 2013 中的 FileTransfers 视图</a></span><span class="sxs-lookup"><span data-stu-id="d7fda-120"><a href="lync-server-2013-filetransfers-view.md">FileTransfers view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fda-121">返回有关文件传输会话的信息, 包括文件名以及是否接受、拒绝或取消传输。</span><span class="sxs-lookup"><span data-stu-id="d7fda-121">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fda-122"><a href="lync-server-2013-focusjoinsandleaves-view.md">Lync Server 2013 中的 FocusJoinsAndLeaves 视图</a></span><span class="sxs-lookup"><span data-stu-id="d7fda-122"><a href="lync-server-2013-focusjoinsandleaves-view.md">FocusJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fda-123">返回有关会议加入和退出活动的信息。</span><span class="sxs-lookup"><span data-stu-id="d7fda-123">Returns information about conference join and leave activities.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fda-124"><a href="lync-server-2013-mcujoinsandleaves-view.md">Lync Server 2013 中的 McuJoinsAndLeaves 视图</a></span><span class="sxs-lookup"><span data-stu-id="d7fda-124"><a href="lync-server-2013-mcujoinsandleaves-view.md">McuJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fda-125">返回有关会议加入和退出活动的组合信息 (每个会议联接与相应的会议休假配对)。</span><span class="sxs-lookup"><span data-stu-id="d7fda-125">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fda-126"><a href="lync-server-2013-mcus-view.md">Lync Server 2013 中的 Mcus 视图</a></span><span class="sxs-lookup"><span data-stu-id="d7fda-126"><a href="lync-server-2013-mcus-view.md">Mcus view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fda-127">返回有关会议服务器的信息。</span><span class="sxs-lookup"><span data-stu-id="d7fda-127">Returns information about Conferencing servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fda-128"><a href="lync-server-2013-media-view.md">Lync Server 2013 中的 "媒体" 视图</a></span><span class="sxs-lookup"><span data-stu-id="d7fda-128"><a href="lync-server-2013-media-view.md">Media view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fda-129">返回有关对等通信会话中使用的媒体类型的信息。</span><span class="sxs-lookup"><span data-stu-id="d7fda-129">Returns information about the types of media used in peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fda-130"><a href="lync-server-2013-progressreport-view.md">Lync Server 2013 中的 ProgressReport 视图</a></span><span class="sxs-lookup"><span data-stu-id="d7fda-130"><a href="lync-server-2013-progressreport-view.md">ProgressReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fda-131">返回有关已完成会话的信息。</span><span class="sxs-lookup"><span data-stu-id="d7fda-131">Returns information about completed sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fda-132"><a href="lync-server-2013-registration-view.md">Lync Server 2013 中的注册视图</a></span><span class="sxs-lookup"><span data-stu-id="d7fda-132"><a href="lync-server-2013-registration-view.md">Registration view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fda-133">返回有关 Lync Server 注册的信息。</span><span class="sxs-lookup"><span data-stu-id="d7fda-133">Returns information about registrations with Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fda-134"><a href="lync-server-2013-sessiondetails-view.md">Lync Server 2013 中的 SessionDetails 视图</a></span><span class="sxs-lookup"><span data-stu-id="d7fda-134"><a href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fda-135">返回有关对等会话的信息, 包括 VoIP-VoIP 电话呼叫、两方 IM 会话或其他对等通信会话。</span><span class="sxs-lookup"><span data-stu-id="d7fda-135">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d7fda-136"><a href="lync-server-2013-user-view.md">Lync Server 2013 中的用户视图</a></span><span class="sxs-lookup"><span data-stu-id="d7fda-136"><a href="lync-server-2013-user-view.md">User view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fda-137">返回有关参与通信会话的用户的信息。</span><span class="sxs-lookup"><span data-stu-id="d7fda-137">Returns information about the users who have participated in communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d7fda-138"><a href="lync-server-2013-voipdetails-view.md">Lync Server 2013 中的 VoIPDetails 视图</a></span><span class="sxs-lookup"><span data-stu-id="d7fda-138"><a href="lync-server-2013-voipdetails-view.md">VoIPDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="d7fda-139">返回至少涉及一个 VoIP (通过 IO 的语音) 用户的对等会话的信息。</span><span class="sxs-lookup"><span data-stu-id="d7fda-139">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

