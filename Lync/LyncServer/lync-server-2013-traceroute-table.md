---
title: Lync Server 2013： TraceRoute 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 057253527615164b4b8b22a1fa13e7ea48778ee1
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="96a0f-102">Lync Server 2013 中的 TraceRoute 表</span><span class="sxs-lookup"><span data-stu-id="96a0f-102">TraceRoute table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="96a0f-103">_**上次修改的主题：** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="96a0f-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="96a0f-104">TraceRoute 表包含来自呼叫的路由信息。</span><span class="sxs-lookup"><span data-stu-id="96a0f-104">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="96a0f-105">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="96a0f-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="96a0f-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="96a0f-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="96a0f-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="96a0f-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="96a0f-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="96a0f-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="96a0f-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="96a0f-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="96a0f-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="96a0f-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="96a0f-111">datetime</span><span class="sxs-lookup"><span data-stu-id="96a0f-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="96a0f-112">主、外</span><span class="sxs-lookup"><span data-stu-id="96a0f-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="96a0f-113">呼叫开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="96a0f-113">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96a0f-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="96a0f-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="96a0f-115">int</span><span class="sxs-lookup"><span data-stu-id="96a0f-115">int</span></span></p></td>
<td><p><span data-ttu-id="96a0f-116">主、外</span><span class="sxs-lookup"><span data-stu-id="96a0f-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="96a0f-117">用来区分可能在相同日期和相同时间开始的多个呼叫的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="96a0f-117">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96a0f-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="96a0f-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="96a0f-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="96a0f-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="96a0f-120">主、外</span><span class="sxs-lookup"><span data-stu-id="96a0f-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="96a0f-p102">表示在呼叫中使用的视频行的类型。允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="96a0f-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="96a0f-123">0–音频</span><span class="sxs-lookup"><span data-stu-id="96a0f-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="96a0f-124">1–视频</span><span class="sxs-lookup"><span data-stu-id="96a0f-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="96a0f-125">2 – 全景视频</span><span class="sxs-lookup"><span data-stu-id="96a0f-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="96a0f-126">3–应用程序/桌面共享</span><span class="sxs-lookup"><span data-stu-id="96a0f-126">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96a0f-127"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="96a0f-127"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="96a0f-128">位</span><span class="sxs-lookup"><span data-stu-id="96a0f-128">bit</span></span></p></td>
<td><p><span data-ttu-id="96a0f-129">主</span><span class="sxs-lookup"><span data-stu-id="96a0f-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="96a0f-130">发起呼叫的终结点。</span><span class="sxs-lookup"><span data-stu-id="96a0f-130">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96a0f-131"><strong>跃点</strong></span><span class="sxs-lookup"><span data-stu-id="96a0f-131"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="96a0f-132">int</span><span class="sxs-lookup"><span data-stu-id="96a0f-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96a0f-133">网络跃点/</span><span class="sxs-lookup"><span data-stu-id="96a0f-133">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="96a0f-134"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="96a0f-134"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="96a0f-135">int</span><span class="sxs-lookup"><span data-stu-id="96a0f-135">int</span></span></p></td>
<td><p><span data-ttu-id="96a0f-136">对外</span><span class="sxs-lookup"><span data-stu-id="96a0f-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="96a0f-137">IP 地址的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="96a0f-137">Unique identifier for the IP address.</span></span> <span data-ttu-id="96a0f-138">IP 地址信息存储在<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 的 IPAddress 表中</a>。</span><span class="sxs-lookup"><span data-stu-id="96a0f-138">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="96a0f-139"><strong>RTT</strong></span><span class="sxs-lookup"><span data-stu-id="96a0f-139"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="96a0f-140">int</span><span class="sxs-lookup"><span data-stu-id="96a0f-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="96a0f-p104">来回行程的时间。来回行程的时间会测量语音数据包到达其目标，然后将其所收到的通知发送回来所需的时间量。</span><span class="sxs-lookup"><span data-stu-id="96a0f-p104">Roundtrip time. The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

