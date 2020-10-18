---
title: Lync Server 2013： AppSharingStream 表
description: Lync Server 2013： AppSharingStream 表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b530af5b489e090e5d0d00fbb01b2b950bafbe5a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574718"
---
# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="d336b-103">Lync Server 2013 中的 AppSharingStream 表</span><span class="sxs-lookup"><span data-stu-id="d336b-103">AppSharingStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d336b-104">_**上次修改的主题：** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="d336b-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="d336b-105">AppSharingStream 表包含用于应用程序共享的网络流的用户体验质量指标。</span><span class="sxs-lookup"><span data-stu-id="d336b-105">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="d336b-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="d336b-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d336b-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="d336b-108"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="d336b-109"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="d336b-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d336b-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-112">dateTime</span><span class="sxs-lookup"><span data-stu-id="d336b-112">dateTime</span></span></p></td>
<td><p><span data-ttu-id="d336b-113">主、外</span><span class="sxs-lookup"><span data-stu-id="d336b-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d336b-114">会话开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="d336b-114">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-116">int</span><span class="sxs-lookup"><span data-stu-id="d336b-116">int</span></span></p></td>
<td><p><span data-ttu-id="d336b-117">主、外</span><span class="sxs-lookup"><span data-stu-id="d336b-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d336b-118">用于区分在相同日期和时间开始的会话的顺序标识符。</span><span class="sxs-lookup"><span data-stu-id="d336b-118">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="d336b-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d336b-121">主、外</span><span class="sxs-lookup"><span data-stu-id="d336b-121">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d336b-p102">表示在呼叫中使用的视频行的类型。允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="d336b-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="d336b-124">0–音频</span><span class="sxs-lookup"><span data-stu-id="d336b-124">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="d336b-125">1–视频</span><span class="sxs-lookup"><span data-stu-id="d336b-125">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="d336b-126">2 – 全景视频</span><span class="sxs-lookup"><span data-stu-id="d336b-126">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="d336b-127">3–应用程序/桌面共享</span><span class="sxs-lookup"><span data-stu-id="d336b-127">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-128"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-128"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-129">int</span><span class="sxs-lookup"><span data-stu-id="d336b-129">int</span></span></p></td>
<td><p><span data-ttu-id="d336b-130">主</span><span class="sxs-lookup"><span data-stu-id="d336b-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="d336b-131">应用程序共享流的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="d336b-131">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-132"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-132"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-133">int</span><span class="sxs-lookup"><span data-stu-id="d336b-133">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-134">在 RTP 数据包到达之间检测到的平均抖动率。</span><span class="sxs-lookup"><span data-stu-id="d336b-134">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="d336b-135"> (抖动是 shakiness 的衡量指标 &quot; &quot; 。 ) 高抖动值通常由拥塞或过载的媒体服务器引起，并导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="d336b-135">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-136"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-136"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-137">int</span><span class="sxs-lookup"><span data-stu-id="d336b-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-138">在 RTP 数据包到达之间检测到的最大抖动率。</span><span class="sxs-lookup"><span data-stu-id="d336b-138">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="d336b-139"> (抖动是 shakiness 的衡量指标 &quot; &quot; 。 ) 高抖动值通常由拥塞或过载的媒体服务器引起，并导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="d336b-139">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-140"><strong>工程</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-140"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-141">int</span><span class="sxs-lookup"><span data-stu-id="d336b-141">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-p105">实时传输协议数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 200 毫秒被视为质量可接受。</span><span class="sxs-lookup"><span data-stu-id="d336b-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="d336b-p106">高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</span><span class="sxs-lookup"><span data-stu-id="d336b-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-146"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-146"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-147">int</span><span class="sxs-lookup"><span data-stu-id="d336b-147">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-p107">实时传输协议数据包来往于另一个终结点所需的最大时间量（以毫秒为单位）。来回行程的时间小于或等于 200 毫秒被视为质量可接受。</span><span class="sxs-lookup"><span data-stu-id="d336b-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="d336b-p108">高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</span><span class="sxs-lookup"><span data-stu-id="d336b-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-152"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-152"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-153">float</span><span class="sxs-lookup"><span data-stu-id="d336b-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-p109">平均实时传输协议 (RTP) 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时，即发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。数据包丢失通常导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="d336b-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-157"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-157"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-158">float</span><span class="sxs-lookup"><span data-stu-id="d336b-158">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-p110">最大实时传输协议 (RTP) 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时，即发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。数据包丢失通常导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="d336b-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-162"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-162"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-163">int</span><span class="sxs-lookup"><span data-stu-id="d336b-163">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-164">发送的数据包数。</span><span class="sxs-lookup"><span data-stu-id="d336b-164">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-165"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-165"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-166">int</span><span class="sxs-lookup"><span data-stu-id="d336b-166">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-p111">在会话末尾可用的单向带宽的估计值。以每秒的位数的形式报告。</span><span class="sxs-lookup"><span data-stu-id="d336b-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-169"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-169"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-170">int</span><span class="sxs-lookup"><span data-stu-id="d336b-170">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-171">应用程序共享负载的描述。</span><span class="sxs-lookup"><span data-stu-id="d336b-171">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-172"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-172"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-173">float</span><span class="sxs-lookup"><span data-stu-id="d336b-173">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-p112">单向延迟的总量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="d336b-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-176"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-176"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-177">float</span><span class="sxs-lookup"><span data-stu-id="d336b-177">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-p113">单向延迟的平均量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="d336b-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-180"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-180"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-181">float</span><span class="sxs-lookup"><span data-stu-id="d336b-181">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-p114">单向延迟的最大量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="d336b-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-184"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-184"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-185">int</span><span class="sxs-lookup"><span data-stu-id="d336b-185">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-p115">单向突发总发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="d336b-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-189"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-189"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-190">float</span><span class="sxs-lookup"><span data-stu-id="d336b-190">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-p116">单向突发总密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="d336b-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-194"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-194"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-195">float</span><span class="sxs-lookup"><span data-stu-id="d336b-195">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-p117">单向突发总持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="d336b-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-199"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-199"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-200">int</span><span class="sxs-lookup"><span data-stu-id="d336b-200">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-p118">单向间隙总发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="d336b-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-204"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-204"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-205">float</span><span class="sxs-lookup"><span data-stu-id="d336b-205">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-p119">单向间隙总密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="d336b-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-209"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-209"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-210">float</span><span class="sxs-lookup"><span data-stu-id="d336b-210">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-p120">单向间隙总持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="d336b-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-214"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-214"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-215">varChar (256) </span><span class="sxs-lookup"><span data-stu-id="d336b-215">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-216">应用程序角色（共享者或查看者）和内容类型。</span><span class="sxs-lookup"><span data-stu-id="d336b-216">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-217"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-217"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-218">float</span><span class="sxs-lookup"><span data-stu-id="d336b-218">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-p121">远程桌面协议 (RDP) 图块的总处理时间。总时间量越大，查看体验的延迟就越长。</span><span class="sxs-lookup"><span data-stu-id="d336b-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-221"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-221"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-222">float</span><span class="sxs-lookup"><span data-stu-id="d336b-222">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-p122">远程桌面协议 (RDP) 图块的平均处理时间。总时间量越大，查看体验的延迟就越长。</span><span class="sxs-lookup"><span data-stu-id="d336b-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-225"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-225"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-226">float</span><span class="sxs-lookup"><span data-stu-id="d336b-226">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-p123">远程桌面协议 (RDP) 图块的最大处理时间。总时间量越大，查看体验的延迟就越长。</span><span class="sxs-lookup"><span data-stu-id="d336b-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-229"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-229"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-230">int</span><span class="sxs-lookup"><span data-stu-id="d336b-230">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-p124">远程桌面协议 (RDP) 图块的处理时间中的突发发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。</span><span class="sxs-lookup"><span data-stu-id="d336b-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-233"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-233"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-234">float</span><span class="sxs-lookup"><span data-stu-id="d336b-234">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-p125">远程桌面协议 (RDP) 图块的处理时间中的突发密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。</span><span class="sxs-lookup"><span data-stu-id="d336b-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-237"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-237"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-238">float</span><span class="sxs-lookup"><span data-stu-id="d336b-238">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-p126">远程桌面协议 (RDP) 图块的处理时间中的突发持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。</span><span class="sxs-lookup"><span data-stu-id="d336b-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-241"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-241"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-242">int</span><span class="sxs-lookup"><span data-stu-id="d336b-242">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-243">远程桌面协议 (RDP) 图块的处理时间中的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="d336b-243">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-244"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-244"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-245">float</span><span class="sxs-lookup"><span data-stu-id="d336b-245">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-p127">远程桌面协议 (RDP) 图块的处理时间中的间隙密度。间隙密度越低，查看体验就越佳。</span><span class="sxs-lookup"><span data-stu-id="d336b-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-248"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-248"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-249">float</span><span class="sxs-lookup"><span data-stu-id="d336b-249">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-p128">远程桌面协议 (RDP) 图块的处理时间中的间隙持续时间。间隙持续时间越短，查看体验就越佳。</span><span class="sxs-lookup"><span data-stu-id="d336b-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-252"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-252"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-253">float</span><span class="sxs-lookup"><span data-stu-id="d336b-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-254">图块的总捕获率（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="d336b-254">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-255"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-255"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-256">float</span><span class="sxs-lookup"><span data-stu-id="d336b-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-257">图块的平均捕获率（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="d336b-257">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-258"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-258"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-259">float</span><span class="sxs-lookup"><span data-stu-id="d336b-259">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-260">图块的最大捕获率（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="d336b-260">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-261"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-261"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-262">int</span><span class="sxs-lookup"><span data-stu-id="d336b-262">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-263">图块的捕获率的突发发生次数（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="d336b-263">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-264"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-264"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-265">float</span><span class="sxs-lookup"><span data-stu-id="d336b-265">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-266">图块的捕获率的突发密度（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="d336b-266">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-267"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-267"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-268">float</span><span class="sxs-lookup"><span data-stu-id="d336b-268">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-269">图块的捕获率的突发持续时间（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="d336b-269">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-270"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-270"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-271">int</span><span class="sxs-lookup"><span data-stu-id="d336b-271">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-272">图块的捕获率的间隙发生次数（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="d336b-272">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-273"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-273"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-274">float</span><span class="sxs-lookup"><span data-stu-id="d336b-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-275">图块的捕获率的间隙密度（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="d336b-275">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-276"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-276"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-277">float</span><span class="sxs-lookup"><span data-stu-id="d336b-277">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-278">图块的捕获率的间隙持续时间（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="d336b-278">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-279"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-279"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-280">float</span><span class="sxs-lookup"><span data-stu-id="d336b-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-281">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的总百分比。</span><span class="sxs-lookup"><span data-stu-id="d336b-281">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-282"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-282"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-283">float</span><span class="sxs-lookup"><span data-stu-id="d336b-283">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-284">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的平均百分比。</span><span class="sxs-lookup"><span data-stu-id="d336b-284">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-285"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-285"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-286">float</span><span class="sxs-lookup"><span data-stu-id="d336b-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-287">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的最大百分比。</span><span class="sxs-lookup"><span data-stu-id="d336b-287">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-288"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-288"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-289">int</span><span class="sxs-lookup"><span data-stu-id="d336b-289">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-290">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的突发发生次数。</span><span class="sxs-lookup"><span data-stu-id="d336b-290">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-291"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-291"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-292">float</span><span class="sxs-lookup"><span data-stu-id="d336b-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-293">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的突发密度。</span><span class="sxs-lookup"><span data-stu-id="d336b-293">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-294"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-294"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-295">float</span><span class="sxs-lookup"><span data-stu-id="d336b-295">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-296">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的突发持续时间。</span><span class="sxs-lookup"><span data-stu-id="d336b-296">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-297"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-297"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-298">int</span><span class="sxs-lookup"><span data-stu-id="d336b-298">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-299">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="d336b-299">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-300"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-300"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-301">float</span><span class="sxs-lookup"><span data-stu-id="d336b-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-302">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="d336b-302">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-303"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-303"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-304">float</span><span class="sxs-lookup"><span data-stu-id="d336b-304">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-305">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的间隙持续时间。</span><span class="sxs-lookup"><span data-stu-id="d336b-305">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-306"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-306"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-307">float</span><span class="sxs-lookup"><span data-stu-id="d336b-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-308">从图形源擦除的总帧数。</span><span class="sxs-lookup"><span data-stu-id="d336b-308">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-309"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-309"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-310">float</span><span class="sxs-lookup"><span data-stu-id="d336b-310">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-311">从图形源擦除的平均帧数。</span><span class="sxs-lookup"><span data-stu-id="d336b-311">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-312"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-312"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-313">float</span><span class="sxs-lookup"><span data-stu-id="d336b-313">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-314">从图形源擦除的最大帧数。</span><span class="sxs-lookup"><span data-stu-id="d336b-314">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-315"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-315"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-316">int</span><span class="sxs-lookup"><span data-stu-id="d336b-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-317">从图形源擦除的帧数的突发发生次数。</span><span class="sxs-lookup"><span data-stu-id="d336b-317">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-318"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-318"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-319">float</span><span class="sxs-lookup"><span data-stu-id="d336b-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-320">从图形源擦除的帧数的突发密度。</span><span class="sxs-lookup"><span data-stu-id="d336b-320">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-321"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-321"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-322">float</span><span class="sxs-lookup"><span data-stu-id="d336b-322">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-323">从图形源擦除的帧数的突发持续时间。</span><span class="sxs-lookup"><span data-stu-id="d336b-323">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-324"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-324"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-325">int</span><span class="sxs-lookup"><span data-stu-id="d336b-325">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-326">从图形源擦除的帧数的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="d336b-326">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-327"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-327"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-328">float</span><span class="sxs-lookup"><span data-stu-id="d336b-328">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-329">从图形源擦除的帧数的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="d336b-329">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-330"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-330"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-331">float</span><span class="sxs-lookup"><span data-stu-id="d336b-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-332">从图形源擦除的帧数的间隙持续时间。</span><span class="sxs-lookup"><span data-stu-id="d336b-332">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-333"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-333"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-334">float</span><span class="sxs-lookup"><span data-stu-id="d336b-334">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-335">查看者收到的总传入帧速率。</span><span class="sxs-lookup"><span data-stu-id="d336b-335">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-336"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-336"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-337">float</span><span class="sxs-lookup"><span data-stu-id="d336b-337">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-338">查看者收到的平均传入帧速率。</span><span class="sxs-lookup"><span data-stu-id="d336b-338">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-339"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-339"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-340">float</span><span class="sxs-lookup"><span data-stu-id="d336b-340">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-341">查看者收到的最大传入图块速率。</span><span class="sxs-lookup"><span data-stu-id="d336b-341">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-342"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-342"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-343">int</span><span class="sxs-lookup"><span data-stu-id="d336b-343">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-344">查看者收到的传入图块速率的突发发生次数。</span><span class="sxs-lookup"><span data-stu-id="d336b-344">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-345"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-345"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-346">float</span><span class="sxs-lookup"><span data-stu-id="d336b-346">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-347">查看者收到的传入图块速率的突发密度。</span><span class="sxs-lookup"><span data-stu-id="d336b-347">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-348"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-348"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-349">float</span><span class="sxs-lookup"><span data-stu-id="d336b-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-350">查看者收到的传入图块速率的突发持续时间。</span><span class="sxs-lookup"><span data-stu-id="d336b-350">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-351"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-351"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-352">int</span><span class="sxs-lookup"><span data-stu-id="d336b-352">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-353">查看者收到的传入图块速率的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="d336b-353">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-354"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-354"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-355">float</span><span class="sxs-lookup"><span data-stu-id="d336b-355">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-356">查看者收到的传入图块速率的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="d336b-356">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-357"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-357"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-358">float</span><span class="sxs-lookup"><span data-stu-id="d336b-358">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-359">查看者收到的传入图块速率的间隙持续时间。</span><span class="sxs-lookup"><span data-stu-id="d336b-359">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-360"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-360"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-361">float</span><span class="sxs-lookup"><span data-stu-id="d336b-361">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-362">查看者收到的总传入帧速率。</span><span class="sxs-lookup"><span data-stu-id="d336b-362">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-363"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-363"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-364">float</span><span class="sxs-lookup"><span data-stu-id="d336b-364">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-365">查看者收到的平均传入帧速率。</span><span class="sxs-lookup"><span data-stu-id="d336b-365">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-366"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-366"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-367">float</span><span class="sxs-lookup"><span data-stu-id="d336b-367">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-368">查看者收到的最大传入帧速率。</span><span class="sxs-lookup"><span data-stu-id="d336b-368">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-369"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-369"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-370">int</span><span class="sxs-lookup"><span data-stu-id="d336b-370">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-371">查看者收到的传入帧速率的突发发生次数。</span><span class="sxs-lookup"><span data-stu-id="d336b-371">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-372"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-372"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-373">float</span><span class="sxs-lookup"><span data-stu-id="d336b-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-374">查看者收到的传入帧速率的突发密度。</span><span class="sxs-lookup"><span data-stu-id="d336b-374">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-375"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-375"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-376">float</span><span class="sxs-lookup"><span data-stu-id="d336b-376">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-377">查看者收到的传入帧速率的突发持续时间。</span><span class="sxs-lookup"><span data-stu-id="d336b-377">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-378"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-378"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-379">int</span><span class="sxs-lookup"><span data-stu-id="d336b-379">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-380">查看者收到的传入帧速率的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="d336b-380">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-381"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-381"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-382">float</span><span class="sxs-lookup"><span data-stu-id="d336b-382">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-383">查看者收到的传入帧速率的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="d336b-383">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-384"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-384"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-385">float</span><span class="sxs-lookup"><span data-stu-id="d336b-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-386">查看者收到的传入帧速率的间隙持续时间。</span><span class="sxs-lookup"><span data-stu-id="d336b-386">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-387"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-387"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-388">float</span><span class="sxs-lookup"><span data-stu-id="d336b-388">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-389">发送者的总传出图块速率。</span><span class="sxs-lookup"><span data-stu-id="d336b-389">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-390"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-390"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-391">float</span><span class="sxs-lookup"><span data-stu-id="d336b-391">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-392">发送者的平均传出图块速率。</span><span class="sxs-lookup"><span data-stu-id="d336b-392">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-393"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-393"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-394">float</span><span class="sxs-lookup"><span data-stu-id="d336b-394">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-395">发送者的最大传出图块速率。</span><span class="sxs-lookup"><span data-stu-id="d336b-395">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-396"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-396"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-397">int</span><span class="sxs-lookup"><span data-stu-id="d336b-397">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-398">发送者的传出图块速率的突发发生次数。</span><span class="sxs-lookup"><span data-stu-id="d336b-398">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-399"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-399"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-400">float</span><span class="sxs-lookup"><span data-stu-id="d336b-400">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-401">发送者的传出图块速率的突发密度。</span><span class="sxs-lookup"><span data-stu-id="d336b-401">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-402"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-402"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-403">float</span><span class="sxs-lookup"><span data-stu-id="d336b-403">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-404">发送者的传出图块速率的突发持续时间。</span><span class="sxs-lookup"><span data-stu-id="d336b-404">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-405"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-405"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-406">int</span><span class="sxs-lookup"><span data-stu-id="d336b-406">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-407">发送者的传出图块速率的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="d336b-407">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-408"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-408"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-409">float</span><span class="sxs-lookup"><span data-stu-id="d336b-409">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-410">发送者的传出图块速率的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="d336b-410">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-411"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-411"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-412">float</span><span class="sxs-lookup"><span data-stu-id="d336b-412">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-413">发送者的传出图块速率的间隙持续时间。</span><span class="sxs-lookup"><span data-stu-id="d336b-413">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-414"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-414"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-415">float</span><span class="sxs-lookup"><span data-stu-id="d336b-415">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-416">发送者的总传出帧速率。</span><span class="sxs-lookup"><span data-stu-id="d336b-416">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-417"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-417"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-418">float</span><span class="sxs-lookup"><span data-stu-id="d336b-418">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-419">发送者的平均传出帧速率。</span><span class="sxs-lookup"><span data-stu-id="d336b-419">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-420"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-420"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-421">float</span><span class="sxs-lookup"><span data-stu-id="d336b-421">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-422">发送者的最大传出帧速率。</span><span class="sxs-lookup"><span data-stu-id="d336b-422">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-423"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-423"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-424">int</span><span class="sxs-lookup"><span data-stu-id="d336b-424">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-425">发送者的传出帧速率的突发发生次数。</span><span class="sxs-lookup"><span data-stu-id="d336b-425">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-426"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-426"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-427">float</span><span class="sxs-lookup"><span data-stu-id="d336b-427">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-428">发送者的传出帧速率的突发密度。</span><span class="sxs-lookup"><span data-stu-id="d336b-428">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-429"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-429"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-430">float</span><span class="sxs-lookup"><span data-stu-id="d336b-430">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-431">发送者的传出帧速率的突发持续时间。</span><span class="sxs-lookup"><span data-stu-id="d336b-431">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-432"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-432"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-433">int</span><span class="sxs-lookup"><span data-stu-id="d336b-433">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-434">发送者的传出帧速率的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="d336b-434">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-435"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-435"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-436">float</span><span class="sxs-lookup"><span data-stu-id="d336b-436">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-437">发送者的传出帧速率的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="d336b-437">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-438"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-438"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-439">float</span><span class="sxs-lookup"><span data-stu-id="d336b-439">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-440">发送者的传出帧速率的间隙持续时间。</span><span class="sxs-lookup"><span data-stu-id="d336b-440">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-441"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-441"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-442">int</span><span class="sxs-lookup"><span data-stu-id="d336b-442">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-443">平均视频分辨率高度（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="d336b-443">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-444"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-444"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-445">int</span><span class="sxs-lookup"><span data-stu-id="d336b-445">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-446">平均视频分辨率宽度（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="d336b-446">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-447"><strong>进货</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-447"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-448">位</span><span class="sxs-lookup"><span data-stu-id="d336b-448">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-449">入站传输的平均帧速率（以每秒帧数为单位）。</span><span class="sxs-lookup"><span data-stu-id="d336b-449">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d336b-450"><strong>出站</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-450"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-451">位</span><span class="sxs-lookup"><span data-stu-id="d336b-451">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-452">出站传输的平均帧速率（以每秒帧数为单位）。</span><span class="sxs-lookup"><span data-stu-id="d336b-452">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d336b-453"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="d336b-453"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="d336b-454">位</span><span class="sxs-lookup"><span data-stu-id="d336b-454">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d336b-455">1 表示流方向是从呼叫者到被叫方。</span><span class="sxs-lookup"><span data-stu-id="d336b-455">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="d336b-456">0 表示流方向是从被叫方到呼叫者。</span><span class="sxs-lookup"><span data-stu-id="d336b-456">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

