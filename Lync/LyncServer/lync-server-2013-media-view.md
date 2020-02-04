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
ms.openlocfilehash: 6ad833bc84d488221d46822686077cfde2cda0ff
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765090"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-view-in-lync-server-2013"></a><span data-ttu-id="3c63a-102">Lync Server 2013 中的 "媒体" 视图</span><span class="sxs-lookup"><span data-stu-id="3c63a-102">Media view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3c63a-103">_**主题上次修改时间：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="3c63a-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="3c63a-104">媒体视图存储对等会话中使用的一种媒体类型的相关信息。</span><span class="sxs-lookup"><span data-stu-id="3c63a-104">The Media view stores information about one media type used in a peer-to-peer session.</span></span> <span data-ttu-id="3c63a-105">如果使用多个媒体类型，则表中的多个记录将表示一个会话。</span><span class="sxs-lookup"><span data-stu-id="3c63a-105">One session would be represented by multiple records in the table, if more than one media type is used.</span></span> <span data-ttu-id="3c63a-106">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="3c63a-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3c63a-107">不应使用 "媒体" 视图计算会话的媒体持续时间。</span><span class="sxs-lookup"><span data-stu-id="3c63a-107">The Media view should not be used to calculate the media duration for a session.</span></span> <span data-ttu-id="3c63a-108">此视图包含会话中媒体交换的信号详细信息。</span><span class="sxs-lookup"><span data-stu-id="3c63a-108">This view contains the signaling details of media exchange in a session.</span></span> <span data-ttu-id="3c63a-109">媒体交换由邀请请求完成，并且 StartTime 指示发送邀请的时间。邀请时间不一定意味着媒体开始时间，因为媒体仅在接受会话后才开始。</span><span class="sxs-lookup"><span data-stu-id="3c63a-109">Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the session is accepted.</span></span>



</div>

<span data-ttu-id="3c63a-110">媒体视图在[Lync Server 2013 的 SessionDetails 视图](lync-server-2013-sessiondetails-view.md)中包含所有列，此外还包含下面列出的列。</span><span class="sxs-lookup"><span data-stu-id="3c63a-110">The Media view contains all of the columns in the [SessionDetails view in Lync Server 2013](lync-server-2013-sessiondetails-view.md) in addition the ones listed below.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3c63a-111">列</span><span class="sxs-lookup"><span data-stu-id="3c63a-111">Column</span></span></th>
<th><span data-ttu-id="3c63a-112">数据类型</span><span class="sxs-lookup"><span data-stu-id="3c63a-112">Data Type</span></span></th>
<th><span data-ttu-id="3c63a-113">详细信息</span><span class="sxs-lookup"><span data-stu-id="3c63a-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3c63a-114"><strong>媒体</strong></span><span class="sxs-lookup"><span data-stu-id="3c63a-114"><strong>Media</strong></span></span></p></td>
<td><p><span data-ttu-id="3c63a-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3c63a-115">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3c63a-116">媒体类型。</span><span class="sxs-lookup"><span data-stu-id="3c63a-116">Media type.</span></span> <span data-ttu-id="3c63a-117">有关详细信息，请参阅<a href="lync-server-2013-medialist-table.md">Lync Server 2013 中的 MediaList 表</a>。</span><span class="sxs-lookup"><span data-stu-id="3c63a-117">See the <a href="lync-server-2013-medialist-table.md">MediaList table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3c63a-118"><strong>MediaStartTime</strong></span><span class="sxs-lookup"><span data-stu-id="3c63a-118"><strong>MediaStartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3c63a-119">datetime</span><span class="sxs-lookup"><span data-stu-id="3c63a-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="3c63a-120">媒体请求发出的时间。</span><span class="sxs-lookup"><span data-stu-id="3c63a-120">Time that a media request was sent out.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3c63a-121"><strong>MediaEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="3c63a-121"><strong>MediaEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3c63a-122">datetime</span><span class="sxs-lookup"><span data-stu-id="3c63a-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="3c63a-123">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="3c63a-123">End time of the session.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

