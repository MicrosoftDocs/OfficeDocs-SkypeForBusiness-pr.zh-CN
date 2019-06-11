---
title: 'Lync Server 2013: TraceRoute 表'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: TraceRoute table
ms:assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205205(v=OCS.15)
ms:contentKeyID: 48185242
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f1dd0f9bc3bd900d71a316bf2ff1ab7612a51194
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845536"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="ff567-102">Lync Server 2013 中的 TraceRoute 表</span><span class="sxs-lookup"><span data-stu-id="ff567-102">TraceRoute table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ff567-103">_**主题上次修改时间:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="ff567-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="ff567-104">TraceRoute 表包含来自呼叫的路由信息。</span><span class="sxs-lookup"><span data-stu-id="ff567-104">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="ff567-105">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ff567-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ff567-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="ff567-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ff567-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="ff567-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ff567-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="ff567-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ff567-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="ff567-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ff567-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="ff567-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ff567-111">datetime</span><span class="sxs-lookup"><span data-stu-id="ff567-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ff567-112">主、外部</span><span class="sxs-lookup"><span data-stu-id="ff567-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ff567-113">通话开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="ff567-113">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff567-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ff567-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ff567-115">int</span><span class="sxs-lookup"><span data-stu-id="ff567-115">int</span></span></p></td>
<td><p><span data-ttu-id="ff567-116">主、外部</span><span class="sxs-lookup"><span data-stu-id="ff567-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ff567-117">用于区分可能在同一日期和同一时间开始的多个通话的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="ff567-117">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff567-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="ff567-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="ff567-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="ff567-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ff567-120">主、外部</span><span class="sxs-lookup"><span data-stu-id="ff567-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ff567-121">表示通话中使用的视频线路类型。</span><span class="sxs-lookup"><span data-stu-id="ff567-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="ff567-122">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="ff567-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="ff567-123">0-音频</span><span class="sxs-lookup"><span data-stu-id="ff567-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="ff567-124">1-视频</span><span class="sxs-lookup"><span data-stu-id="ff567-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="ff567-125">2-全景视频</span><span class="sxs-lookup"><span data-stu-id="ff567-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="ff567-126">3-应用程序/桌面共享</span><span class="sxs-lookup"><span data-stu-id="ff567-126">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff567-127"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="ff567-127"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="ff567-128">bit</span><span class="sxs-lookup"><span data-stu-id="ff567-128">bit</span></span></p></td>
<td><p><span data-ttu-id="ff567-129">Primary</span><span class="sxs-lookup"><span data-stu-id="ff567-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="ff567-130">发出呼叫的终结点。</span><span class="sxs-lookup"><span data-stu-id="ff567-130">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff567-131"><strong>跳</strong></span><span class="sxs-lookup"><span data-stu-id="ff567-131"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="ff567-132">int</span><span class="sxs-lookup"><span data-stu-id="ff567-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ff567-133">网络跃点/</span><span class="sxs-lookup"><span data-stu-id="ff567-133">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ff567-134"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="ff567-134"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="ff567-135">int</span><span class="sxs-lookup"><span data-stu-id="ff567-135">int</span></span></p></td>
<td><p><span data-ttu-id="ff567-136">外表</span><span class="sxs-lookup"><span data-stu-id="ff567-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ff567-137">IP 地址的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="ff567-137">Unique identifier for the IP address.</span></span> <span data-ttu-id="ff567-138">IP 地址信息存储在<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 的 "IPAddress" 表中</a>。</span><span class="sxs-lookup"><span data-stu-id="ff567-138">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ff567-139"><strong>RTT</strong></span><span class="sxs-lookup"><span data-stu-id="ff567-139"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="ff567-140">int</span><span class="sxs-lookup"><span data-stu-id="ff567-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ff567-141">往返时间。</span><span class="sxs-lookup"><span data-stu-id="ff567-141">Roundtrip time.</span></span> <span data-ttu-id="ff567-142">往返时间测量语音数据包到达其目标所需的时间量, 然后发送发送回收到通知的时间。</span><span class="sxs-lookup"><span data-stu-id="ff567-142">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

