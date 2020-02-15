---
title: Lync Server 2013： VideoClientEvent 表
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
ms.openlocfilehash: 63a0bf66a7b09801bea94e8995757543511e298e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007261"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videoclientevent-table-in-lync-server-2013"></a><span data-ttu-id="947ad-102">Lync Server 2013 中的 VideoClientEvent 表</span><span class="sxs-lookup"><span data-stu-id="947ad-102">VideoClientEvent table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="947ad-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="947ad-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="947ad-104">每个记录都包含视频呼叫中一个终结点的客户端事件。</span><span class="sxs-lookup"><span data-stu-id="947ad-104">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="947ad-105">通常情况下，一个呼叫有两个记录，一个用于呼叫者，一个用于被叫方。</span><span class="sxs-lookup"><span data-stu-id="947ad-105">Usually, one call has two records, one for caller and one for callee.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="947ad-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="947ad-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="947ad-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="947ad-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="947ad-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="947ad-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="947ad-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="947ad-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="947ad-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="947ad-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="947ad-111">datetime</span><span class="sxs-lookup"><span data-stu-id="947ad-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="947ad-112">主</span><span class="sxs-lookup"><span data-stu-id="947ad-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="947ad-113"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="947ad-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947ad-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="947ad-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="947ad-115">int</span><span class="sxs-lookup"><span data-stu-id="947ad-115">int</span></span></p></td>
<td><p><span data-ttu-id="947ad-116">主</span><span class="sxs-lookup"><span data-stu-id="947ad-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="947ad-117"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="947ad-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947ad-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="947ad-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="947ad-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="947ad-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="947ad-120">主</span><span class="sxs-lookup"><span data-stu-id="947ad-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="947ad-121"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="947ad-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947ad-122"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="947ad-122"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="947ad-123">位</span><span class="sxs-lookup"><span data-stu-id="947ad-123">bit</span></span></p></td>
<td><p><span data-ttu-id="947ad-124">主</span><span class="sxs-lookup"><span data-stu-id="947ad-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="947ad-125">0：被调用方的数据</span><span class="sxs-lookup"><span data-stu-id="947ad-125">0: Callee’s data</span></span></p>
<p><span data-ttu-id="947ad-126">1：呼叫者的数据</span><span class="sxs-lookup"><span data-stu-id="947ad-126">1: Caller’s data</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="947ad-127"><strong>NetworkBandwidthLowEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="947ad-127"><strong>NetworkBandwidthLowEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="947ad-128">会话百分比为 "错误" 状态触发了 LowBandwidth 事件。</span><span class="sxs-lookup"><span data-stu-id="947ad-128">Percentage of session the LowBandwidth event was fired for ‘Bad’ state.</span></span> <span data-ttu-id="947ad-129">可用带宽不足以获得可接受的语音体验。</span><span class="sxs-lookup"><span data-stu-id="947ad-129">The available bandwidth is insufficient for an acceptable voice experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="947ad-130"><strong>NetworkReceiveQualityEventRatio</strong></span><span class="sxs-lookup"><span data-stu-id="947ad-130"><strong>NetworkReceiveQualityEventRatio</strong></span></span></p></td>
<td></td>
<td><p> </p></td>
<td><p><span data-ttu-id="947ad-131">会话百分比为 "错误" 状态触发了 ReceiveSendQuality 事件。</span><span class="sxs-lookup"><span data-stu-id="947ad-131">Percentage of session the ReceiveSendQuality event was fired for ‘Bad’ state.</span></span></p>
<p><span data-ttu-id="947ad-132">在抖动或数据包丢失方面，网络质量很严重，会影响接收的音频质量。</span><span class="sxs-lookup"><span data-stu-id="947ad-132">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

