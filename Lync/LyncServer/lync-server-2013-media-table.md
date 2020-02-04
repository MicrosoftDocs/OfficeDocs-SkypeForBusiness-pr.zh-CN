---
title: Lync Server 2013：Media 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media table
ms:assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398268(v=OCS.15)
ms:contentKeyID: 48183568
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69f9ad10c5c06ab8a9d2bc95eddceb67b20e745c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765100"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="b848d-102">Lync Server 2013 中的 Media 表</span><span class="sxs-lookup"><span data-stu-id="b848d-102">Media table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b848d-103">_**主题上次修改时间：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="b848d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="b848d-104">每条记录表示对等会话中使用的一种媒体类型。</span><span class="sxs-lookup"><span data-stu-id="b848d-104">Each record represents one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="b848d-105">如果使用多个媒体类型，则表中的多个记录将表示一个会话。</span><span class="sxs-lookup"><span data-stu-id="b848d-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b848d-106">不应使用 Media 表计算会话的媒体持续时间。</span><span class="sxs-lookup"><span data-stu-id="b848d-106">The Media table should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="b848d-107">此表包含会话中媒体交换的信号详细信息。</span><span class="sxs-lookup"><span data-stu-id="b848d-107">This table contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="b848d-108">媒体交换由邀请请求完成，并且 StartTime 指示发送邀请的时间。邀请时间不一定表示媒体开始时间，因为媒体仅在 sessionee 接受会话后才开始。</span><span class="sxs-lookup"><span data-stu-id="b848d-108">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session.</span></span> <span data-ttu-id="b848d-109">"结束时间" 通常表示本次会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="b848d-109">The EndTime usually means the end time of this session.</span></span>



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b848d-110">列</span><span class="sxs-lookup"><span data-stu-id="b848d-110">Column</span></span></th>
<th><span data-ttu-id="b848d-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="b848d-111">Data Type</span></span></th>
<th><span data-ttu-id="b848d-112">键/索引</span><span class="sxs-lookup"><span data-stu-id="b848d-112">Key/Index</span></span></th>
<th><span data-ttu-id="b848d-113">详细信息</span><span class="sxs-lookup"><span data-stu-id="b848d-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b848d-114"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="b848d-114"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b848d-115">datetime</span><span class="sxs-lookup"><span data-stu-id="b848d-115">datetime</span></span></p></td>
<td><p><span data-ttu-id="b848d-116">主、外部</span><span class="sxs-lookup"><span data-stu-id="b848d-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b848d-117">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="b848d-117">Time of session request.</span></span> <span data-ttu-id="b848d-118">与<strong>SessionIdSeq</strong>结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="b848d-118">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b848d-119">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="b848d-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b848d-120"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="b848d-120"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="b848d-121">int</span><span class="sxs-lookup"><span data-stu-id="b848d-121">int</span></span></p></td>
<td><p><span data-ttu-id="b848d-122">主、外部</span><span class="sxs-lookup"><span data-stu-id="b848d-122">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b848d-123">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="b848d-123">ID number to identify the session.</span></span> <span data-ttu-id="b848d-124">与<strong>SessionIdTime</strong>结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="b848d-124">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="b848d-125">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="b848d-125">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b848d-126"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="b848d-126"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="b848d-127">tinyint</span><span class="sxs-lookup"><span data-stu-id="b848d-127">tinyint</span></span></p></td>
<td><p><span data-ttu-id="b848d-128">主、外部</span><span class="sxs-lookup"><span data-stu-id="b848d-128">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="b848d-129">标识此媒体类型的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="b848d-129">Unique number identifying this media type.</span></span> <span data-ttu-id="b848d-130">有关详细信息，请参阅<a href="lync-server-2013-medialist-table.md">Lync Server 2013 中的 MediaList 表</a>。</span><span class="sxs-lookup"><span data-stu-id="b848d-130">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b848d-131"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="b848d-131"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b848d-132">datetime</span><span class="sxs-lookup"><span data-stu-id="b848d-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="b848d-133">Primary</span><span class="sxs-lookup"><span data-stu-id="b848d-133">Primary</span></span></p></td>
<td><p><span data-ttu-id="b848d-134">这是发送媒体请求的时间，而不是真正的媒体开始时间。</span><span class="sxs-lookup"><span data-stu-id="b848d-134">This is the time that a media request was sent out, not the real media start time.</span></span> <span data-ttu-id="b848d-135"><strong>StartTime</strong>包括会话设置时间。</span><span class="sxs-lookup"><span data-stu-id="b848d-135"><strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b848d-136"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="b848d-136"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="b848d-137">datetime</span><span class="sxs-lookup"><span data-stu-id="b848d-137">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="b848d-138">这是会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="b848d-138">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

