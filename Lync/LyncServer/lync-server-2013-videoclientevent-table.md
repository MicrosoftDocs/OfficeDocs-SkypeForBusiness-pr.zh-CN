---
title: Lync Server 2013：VideoClientEvent 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoClientEvent table
ms:assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399039(v=OCS.15)
ms:contentKeyID: 48185891
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8ff9e19288aaaa09b8c72f857f3cfcf4e5331dd7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41742002"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="68343-102">Lync Server 2013 中的 VideoClientEvent 表</span><span class="sxs-lookup"><span data-stu-id="68343-102">VideoClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="68343-103">_**主题上次修改时间：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="68343-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="68343-104">每条记录包含视频呼叫中一个终结点的客户端事件。</span><span class="sxs-lookup"><span data-stu-id="68343-104">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="68343-105">通常，一个通话有两个记录，一个用于呼叫方，另一个用于被呼叫方。</span><span class="sxs-lookup"><span data-stu-id="68343-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="68343-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="68343-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="68343-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="68343-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="68343-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="68343-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="68343-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="68343-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="68343-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="68343-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="68343-111">datetime</span><span class="sxs-lookup"><span data-stu-id="68343-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="68343-112">Primary</span><span class="sxs-lookup"><span data-stu-id="68343-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="68343-113">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="68343-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68343-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="68343-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="68343-115">int</span><span class="sxs-lookup"><span data-stu-id="68343-115">int</span></span></p></td>
<td><p><span data-ttu-id="68343-116">Primary</span><span class="sxs-lookup"><span data-stu-id="68343-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="68343-117">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="68343-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68343-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="68343-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="68343-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="68343-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="68343-120">Primary</span><span class="sxs-lookup"><span data-stu-id="68343-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="68343-121">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="68343-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68343-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="68343-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="68343-123">bit</span><span class="sxs-lookup"><span data-stu-id="68343-123">bit</span></span></p></td>
<td><p><span data-ttu-id="68343-124">Primary</span><span class="sxs-lookup"><span data-stu-id="68343-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="68343-125">0：被调用方的数据</span><span class="sxs-lookup"><span data-stu-id="68343-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="68343-126">1：调用方的数据</span><span class="sxs-lookup"><span data-stu-id="68343-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="68343-127"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="68343-127"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="68343-128">会话百分比为 "坏" 状态引发 LowBandwidth 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="68343-128">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="68343-129">可用带宽不足以获得可接受的语音体验。</span><span class="sxs-lookup"><span data-stu-id="68343-129">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="68343-130"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="68343-130"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="68343-131">会话百分比为 "坏" 状态引发 ReceiveSendQuality 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="68343-131">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="68343-132">"抖动" 或 "数据包丢失" 方面的网络质量非常严重，影响接收音频的质量。</span><span class="sxs-lookup"><span data-stu-id="68343-132">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

