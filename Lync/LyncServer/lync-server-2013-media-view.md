---
title: Lync Server 2013：媒体视图
description: Lync Server 2013：媒体视图。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media view
ms:assetid: 1a7b2e59-082e-4188-98ae-48ae9bd3494a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687981(v=OCS.15)
ms:contentKeyID: 49733570
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 74643986b12a30b1055a46a37febf90eeb70c514
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48558008"
---
# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="842b2-103">Lync Server 2013 中的媒体视图</span><span class="sxs-lookup"><span data-stu-id="842b2-103">Media view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="842b2-104">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="842b2-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="842b2-105">“媒体”视图存储有关在对等会话中使用的一种媒体类型的信息。</span><span class="sxs-lookup"><span data-stu-id="842b2-105">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="842b2-106">如果使用多个媒体类型，则一个会话由表中的多条记录表示。</span><span class="sxs-lookup"><span data-stu-id="842b2-106">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="842b2-107">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="842b2-107">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="842b2-p102">“媒体”视图不应用来计算会话的媒体持续时间。此视图包含会话中的媒体交换信号详情。媒体交换通过 INVITE 请求实现，StartTime 指示发出 INVITE 的时间。邀请时间不一定表示媒体的启动时间，因为仅在会话被接受后，媒体才启动。</span><span class="sxs-lookup"><span data-stu-id="842b2-p102">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="842b2-111">媒体视图中包含 SessionDetails 视图中的所有列（在 [Lync Server 2013](lync-server-2013-sessiondetails-view.md) 中）以及下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="842b2-111">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="842b2-112">列</span><span class="sxs-lookup"><span data-stu-id="842b2-112">Column</span></span></th>
<th><span data-ttu-id="842b2-113">数据类型</span><span class="sxs-lookup"><span data-stu-id="842b2-113">Data Type</span></span></th>
<th><span data-ttu-id="842b2-114">详细信息</span><span class="sxs-lookup"><span data-stu-id="842b2-114">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="842b2-115"><strong>Media</strong></span><span class="sxs-lookup"><span data-stu-id="842b2-115"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="842b2-116">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="842b2-116">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="842b2-117">媒体类型。</span><span class="sxs-lookup"><span data-stu-id="842b2-117">Media type.</span></span> <span data-ttu-id="842b2-118">有关详细信息，请参阅 <a href="lync-server-2013-medialist-table.md">Lync Server 2013 中的 MediaList 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="842b2-118">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="842b2-119"><strong>MediaStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="842b2-119"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="842b2-120">datetime</span><span class="sxs-lookup"><span data-stu-id="842b2-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="842b2-121">发出媒体请求的时间。</span><span class="sxs-lookup"><span data-stu-id="842b2-121">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="842b2-122"><strong>MediaEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="842b2-122"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="842b2-123">datetime</span><span class="sxs-lookup"><span data-stu-id="842b2-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="842b2-124">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="842b2-124">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

