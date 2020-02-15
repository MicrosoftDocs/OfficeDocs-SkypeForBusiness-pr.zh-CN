---
title: Lync Server 2013： Media 表
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
ms.openlocfilehash: c3d96a7d08a71b63c71c76617e78ebf1df605a52
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044934"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-table-in-lync-server-2013"></a><span data-ttu-id="96801-102">Lync Server 2013 中的媒体表</span><span class="sxs-lookup"><span data-stu-id="96801-102">Media table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96801-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="96801-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="96801-p101">每条记录表示一个用于点对点会话的媒体类型。如果使用多个媒体类型，则一个会话由表中的多条记录表示。</span><span class="sxs-lookup"><span data-stu-id="96801-p101">Each record represents one media type used in a peer-to-peer session. One session would be represented by multiple records in the table, if more than one media type is used.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="96801-p102">不应使用媒体表计算会话的媒体持续时间。该表包含会话中的媒体交换信号详情。媒体交换通过 INVITE 请求实现，StartTime 指示发出 INVITE 的时间。邀请时间不一定表示媒体的启动时间，因为仅在会话接收方接受会话后，媒体才启动。EndTime 通常表示该会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="96801-p102">The Media table should not be used to calculate the media duration for a session. This table contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session. The EndTime usually means the end time of this session.</span></span>



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
<th><span data-ttu-id="96801-110">列</span><span class="sxs-lookup"><span data-stu-id="96801-110">Column</span></span></th>
<th><span data-ttu-id="96801-111">数据类型</span><span class="sxs-lookup"><span data-stu-id="96801-111">Data Type</span></span></th>
<th><span data-ttu-id="96801-112">键/索引</span><span class="sxs-lookup"><span data-stu-id="96801-112">Key/Index</span></span></th>
<th><span data-ttu-id="96801-113">详细信息</span><span class="sxs-lookup"><span data-stu-id="96801-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96801-114"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="96801-114"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="96801-115">datetime</span><span class="sxs-lookup"><span data-stu-id="96801-115">datetime</span></span></p></td>
<td><p><span data-ttu-id="96801-116">主、外</span><span class="sxs-lookup"><span data-stu-id="96801-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="96801-117">会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="96801-117">Time of session request.</span></span> <span data-ttu-id="96801-118">与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="96801-118">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="96801-119">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="96801-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96801-120"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="96801-120"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="96801-121">int</span><span class="sxs-lookup"><span data-stu-id="96801-121">int</span></span></p></td>
<td><p><span data-ttu-id="96801-122">主、外</span><span class="sxs-lookup"><span data-stu-id="96801-122">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="96801-123">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="96801-123">ID number to identify the session.</span></span> <span data-ttu-id="96801-124">与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="96801-124">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="96801-125">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="96801-125">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96801-126"><strong>MediaId</strong></span><span class="sxs-lookup"><span data-stu-id="96801-126"><strong>MediaId</strong></span></span></p></td>
<td><p><span data-ttu-id="96801-127">tinyint</span><span class="sxs-lookup"><span data-stu-id="96801-127">tinyint</span></span></p></td>
<td><p><span data-ttu-id="96801-128">主、外</span><span class="sxs-lookup"><span data-stu-id="96801-128">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="96801-129">标识媒体类型的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="96801-129">Unique number identifying this media type.</span></span> <span data-ttu-id="96801-130">有关详细信息，请参阅<a href="lync-server-2013-medialist-table.md">Lync Server 2013 中的 MediaList 表</a>。</span><span class="sxs-lookup"><span data-stu-id="96801-130">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96801-131"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="96801-131"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="96801-132">datetime</span><span class="sxs-lookup"><span data-stu-id="96801-132">datetime</span></span></p></td>
<td><p><span data-ttu-id="96801-133">主</span><span class="sxs-lookup"><span data-stu-id="96801-133">Primary</span></span></p></td>
<td><p><span data-ttu-id="96801-p106">这是发出媒体请求的时间，而不是实际的媒体启动时间。<strong>StartTime</strong> 包括会话建立时间。</span><span class="sxs-lookup"><span data-stu-id="96801-p106">This is the time that a media request was sent out, not the real media start time. <strong>StartTime</strong> includes the session setup time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96801-136"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="96801-136"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="96801-137">datetime</span><span class="sxs-lookup"><span data-stu-id="96801-137">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96801-138">这是会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="96801-138">This is the end time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

