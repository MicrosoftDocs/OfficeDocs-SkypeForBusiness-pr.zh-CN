---
title: Lync Server 2013： ConferenceUris 表
description: Lync Server 2013： ConferenceUris 表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceUris table
ms:assetid: b1721d52-3c65-45ea-8997-06af8fef93fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412854(v=OCS.15)
ms:contentKeyID: 48185160
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a142aa9ad1fe4d3ae92aa3e21aa9eee505457cbe
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566738"
---
# <a name="conferenceuris-table-in-lync-server-2013"></a><span data-ttu-id="3a8e9-103">Lync Server 2013 中的 ConferenceUris 表</span><span class="sxs-lookup"><span data-stu-id="3a8e9-103">ConferenceUris table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a8e9-104">_**上次修改的主题：** 2012-05-25_</span><span class="sxs-lookup"><span data-stu-id="3a8e9-104">_**Topic Last Modified:** 2012-05-25_</span></span>

<span data-ttu-id="3a8e9-p101">ConfereneUris 表是一个支持表，用于存储已参与数据库中记录的会议会话的各种会议 URI 列表。表中的每条记录代表一个会议 URI。</span><span class="sxs-lookup"><span data-stu-id="3a8e9-p101">The ConfereneUris table is a supporting table that stores a list of the various conference URIs that have participated in conference sessions recorded in the database. Each record in the table represents one conference URI.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3a8e9-107">列</span><span class="sxs-lookup"><span data-stu-id="3a8e9-107">Column</span></span></th>
<th><span data-ttu-id="3a8e9-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="3a8e9-108">Data Type</span></span></th>
<th><span data-ttu-id="3a8e9-109">键/索引</span><span class="sxs-lookup"><span data-stu-id="3a8e9-109">Key/Index</span></span></th>
<th><span data-ttu-id="3a8e9-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="3a8e9-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3a8e9-111"><strong>NextUpdateTS</strong></span><span class="sxs-lookup"><span data-stu-id="3a8e9-111"><strong>NextUpdateTS</strong></span></span></p></td>
<td><p><span data-ttu-id="3a8e9-112">datetime</span><span class="sxs-lookup"><span data-stu-id="3a8e9-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="3a8e9-113">主</span><span class="sxs-lookup"><span data-stu-id="3a8e9-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="3a8e9-114">内部使用的时间戳。</span><span class="sxs-lookup"><span data-stu-id="3a8e9-114">Time stamp, Internal used.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a8e9-115"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="3a8e9-115"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="3a8e9-116">int</span><span class="sxs-lookup"><span data-stu-id="3a8e9-116">int</span></span></p></td>
<td><p><span data-ttu-id="3a8e9-117">主</span><span class="sxs-lookup"><span data-stu-id="3a8e9-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="3a8e9-118">标识此会议 URI 的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="3a8e9-118">Unique number identifying this conference URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a8e9-119"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="3a8e9-119"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="3a8e9-120">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="3a8e9-120">nvarchar(450)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a8e9-121">会议 URI。</span><span class="sxs-lookup"><span data-stu-id="3a8e9-121">Conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3a8e9-122"><strong>校验和</strong></span><span class="sxs-lookup"><span data-stu-id="3a8e9-122"><strong>Checksum</strong></span></span></p></td>
<td><p><span data-ttu-id="3a8e9-123">int</span><span class="sxs-lookup"><span data-stu-id="3a8e9-123">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3a8e9-p102">ConferenceUri 的校验和。用于增加数据库搜索的速度。</span><span class="sxs-lookup"><span data-stu-id="3a8e9-p102">Checksum of ConferenceUri. Used to increases the speed of database searches.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3a8e9-126"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="3a8e9-126"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="3a8e9-127">int</span><span class="sxs-lookup"><span data-stu-id="3a8e9-127">int</span></span></p></td>
<td><p><span data-ttu-id="3a8e9-128">对外</span><span class="sxs-lookup"><span data-stu-id="3a8e9-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3a8e9-129">URI 类型，如 conf:chat 代表 IM 会议，conf:audio-video 代表音频/视频会议。</span><span class="sxs-lookup"><span data-stu-id="3a8e9-129">URI type, such as conf:chat for IM conference, or conf:audio-video for audio/video conference.</span></span> <span data-ttu-id="3a8e9-130">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 表中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="3a8e9-130">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> table for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

