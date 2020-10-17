---
title: Lync Server 2013：媒体视图
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
ms.openlocfilehash: d0e6cd8658278a8d7798153698355f5a73f2952b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516149"
---
# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="43732-102">Lync Server 2013 中的媒体视图</span><span class="sxs-lookup"><span data-stu-id="43732-102">Media view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="43732-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="43732-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="43732-104">“媒体”视图存储有关在对等会话中使用的一种媒体类型的信息。</span><span class="sxs-lookup"><span data-stu-id="43732-104">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="43732-105">如果使用多个媒体类型，则一个会话由表中的多条记录表示。</span><span class="sxs-lookup"><span data-stu-id="43732-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="43732-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="43732-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="43732-p102">“媒体”视图不应用来计算会话的媒体持续时间。此视图包含会话中的媒体交换信号详情。媒体交换通过 INVITE 请求实现，StartTime 指示发出 INVITE 的时间。邀请时间不一定表示媒体的启动时间，因为仅在会话被接受后，媒体才启动。</span><span class="sxs-lookup"><span data-stu-id="43732-p102">The Media view should not be used to calculate the media duration for a session. This view contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="43732-110">媒体视图中包含 SessionDetails 视图中的所有列（在 [Lync Server 2013](lync-server-2013-sessiondetails-view.md) 中）以及下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="43732-110">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="43732-111">列</span><span class="sxs-lookup"><span data-stu-id="43732-111">Column</span></span></th>
<th><span data-ttu-id="43732-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="43732-112">Data Type</span></span></th>
<th><span data-ttu-id="43732-113">详细信息</span><span class="sxs-lookup"><span data-stu-id="43732-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="43732-114"><strong>Media</strong></span><span class="sxs-lookup"><span data-stu-id="43732-114"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="43732-115">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="43732-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="43732-116">媒体类型。</span><span class="sxs-lookup"><span data-stu-id="43732-116">Media type.</span></span> <span data-ttu-id="43732-117">有关详细信息，请参阅 <a href="lync-server-2013-medialist-table.md">Lync Server 2013 中的 MediaList 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="43732-117">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="43732-118"><strong>MediaStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="43732-118"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="43732-119">datetime</span><span class="sxs-lookup"><span data-stu-id="43732-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="43732-120">发出媒体请求的时间。</span><span class="sxs-lookup"><span data-stu-id="43732-120">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="43732-121"><strong>MediaEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="43732-121"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="43732-122">datetime</span><span class="sxs-lookup"><span data-stu-id="43732-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="43732-123">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="43732-123">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

