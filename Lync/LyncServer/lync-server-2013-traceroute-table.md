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
ms.openlocfilehash: 691b7576d59511428400d14a3ff21109525dc5a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41745062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="traceroute-table-in-lync-server-2013"></a><span data-ttu-id="dbd06-102">Lync Server 2013 中的 TraceRoute 表</span><span class="sxs-lookup"><span data-stu-id="dbd06-102">TraceRoute table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbd06-103">_**主题上次修改时间：** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="dbd06-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="dbd06-104">TraceRoute 表包含来自呼叫的路由信息。</span><span class="sxs-lookup"><span data-stu-id="dbd06-104">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="dbd06-105">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="dbd06-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="dbd06-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="dbd06-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="dbd06-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="dbd06-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="dbd06-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="dbd06-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="dbd06-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="dbd06-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="dbd06-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="dbd06-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd06-111">datetime</span><span class="sxs-lookup"><span data-stu-id="dbd06-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="dbd06-112">主、外部</span><span class="sxs-lookup"><span data-stu-id="dbd06-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="dbd06-113">通话开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="dbd06-113">Date and time that the call began.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd06-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="dbd06-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd06-115">int</span><span class="sxs-lookup"><span data-stu-id="dbd06-115">int</span></span></p></td>
<td><p><span data-ttu-id="dbd06-116">主、外部</span><span class="sxs-lookup"><span data-stu-id="dbd06-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="dbd06-117">用于区分可能在同一日期和同一时间开始的多个通话的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="dbd06-117">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd06-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="dbd06-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd06-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="dbd06-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="dbd06-120">主、外部</span><span class="sxs-lookup"><span data-stu-id="dbd06-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="dbd06-121">表示通话中使用的视频线路类型。</span><span class="sxs-lookup"><span data-stu-id="dbd06-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="dbd06-122">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="dbd06-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="dbd06-123">0-音频</span><span class="sxs-lookup"><span data-stu-id="dbd06-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="dbd06-124">1-视频</span><span class="sxs-lookup"><span data-stu-id="dbd06-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="dbd06-125">2-全景视频</span><span class="sxs-lookup"><span data-stu-id="dbd06-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="dbd06-126">3-应用程序/桌面共享</span><span class="sxs-lookup"><span data-stu-id="dbd06-126">3 – Application/Desktop sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd06-127"><strong>FromCaller</strong></span><span class="sxs-lookup"><span data-stu-id="dbd06-127"><strong>FromCaller</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd06-128">bit</span><span class="sxs-lookup"><span data-stu-id="dbd06-128">bit</span></span></p></td>
<td><p><span data-ttu-id="dbd06-129">Primary</span><span class="sxs-lookup"><span data-stu-id="dbd06-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="dbd06-130">发出呼叫的终结点。</span><span class="sxs-lookup"><span data-stu-id="dbd06-130">Endpoint that placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd06-131"><strong>跳</strong></span><span class="sxs-lookup"><span data-stu-id="dbd06-131"><strong>Hop</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd06-132">int</span><span class="sxs-lookup"><span data-stu-id="dbd06-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd06-133">网络跃点/</span><span class="sxs-lookup"><span data-stu-id="dbd06-133">Network hop/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="dbd06-134"><strong>IPAddressKey</strong></span><span class="sxs-lookup"><span data-stu-id="dbd06-134"><strong>IPAddressKey</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd06-135">int</span><span class="sxs-lookup"><span data-stu-id="dbd06-135">int</span></span></p></td>
<td><p><span data-ttu-id="dbd06-136">外表</span><span class="sxs-lookup"><span data-stu-id="dbd06-136">Foreign</span></span></p></td>
<td><p><span data-ttu-id="dbd06-137">IP 地址的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="dbd06-137">Unique identifier for the IP address.</span></span> <span data-ttu-id="dbd06-138">IP 地址信息存储在<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 的 "IPAddress" 表中</a>。</span><span class="sxs-lookup"><span data-stu-id="dbd06-138">IP address information is stored in the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="dbd06-139"><strong>RTT</strong></span><span class="sxs-lookup"><span data-stu-id="dbd06-139"><strong>RTT</strong></span></span></p></td>
<td><p><span data-ttu-id="dbd06-140">int</span><span class="sxs-lookup"><span data-stu-id="dbd06-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="dbd06-141">往返时间。</span><span class="sxs-lookup"><span data-stu-id="dbd06-141">Roundtrip time.</span></span> <span data-ttu-id="dbd06-142">往返时间测量语音数据包到达其目标所需的时间量，然后发送发送回收到通知的时间。</span><span class="sxs-lookup"><span data-stu-id="dbd06-142">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

