---
title: 'Lync Server 2013: AppSharingStream 表'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 56f23e214ffcffad8613d413924a53ffe571883d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="9da43-102">Lync Server 2013 中的 AppSharingStream 表</span><span class="sxs-lookup"><span data-stu-id="9da43-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9da43-103">_**主题上次修改时间:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="9da43-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="9da43-104">AppSharingStream 表包含用于应用程序共享的网络流的体验指标的质量。</span><span class="sxs-lookup"><span data-stu-id="9da43-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="9da43-105">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="9da43-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9da43-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="9da43-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="9da43-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="9da43-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9da43-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-111">从中</span><span class="sxs-lookup"><span data-stu-id="9da43-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="9da43-112">主、外部</span><span class="sxs-lookup"><span data-stu-id="9da43-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9da43-113">会话开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="9da43-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-115">int</span><span class="sxs-lookup"><span data-stu-id="9da43-115">int</span></span></p></td>
<td><p><span data-ttu-id="9da43-116">主、外部</span><span class="sxs-lookup"><span data-stu-id="9da43-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9da43-117">用于区分在同一日期和同一时间启动的会话的顺序标识符。</span><span class="sxs-lookup"><span data-stu-id="9da43-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="9da43-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="9da43-120">主、外部</span><span class="sxs-lookup"><span data-stu-id="9da43-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="9da43-121">表示通话中使用的视频线路类型。</span><span class="sxs-lookup"><span data-stu-id="9da43-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="9da43-122">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="9da43-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="9da43-123">0-音频</span><span class="sxs-lookup"><span data-stu-id="9da43-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="9da43-124">1-视频</span><span class="sxs-lookup"><span data-stu-id="9da43-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="9da43-125">2-全景视频</span><span class="sxs-lookup"><span data-stu-id="9da43-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="9da43-126">3-应用程序/桌面共享</span><span class="sxs-lookup"><span data-stu-id="9da43-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-127"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-128">int</span><span class="sxs-lookup"><span data-stu-id="9da43-128">int</span></span></p></td>
<td><p><span data-ttu-id="9da43-129">Primary</span><span class="sxs-lookup"><span data-stu-id="9da43-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="9da43-130">应用程序共享流的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="9da43-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-132">int</span><span class="sxs-lookup"><span data-stu-id="9da43-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-133">在 RTP 数据包到达之间检测到的平均抖动率。</span><span class="sxs-lookup"><span data-stu-id="9da43-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="9da43-134">(抖动是&quot;shakiness&quot;通话的衡量。)高抖动值通常由拥塞或过载的媒体服务器导致, 并导致失真或丢失的音频。</span><span class="sxs-lookup"><span data-stu-id="9da43-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-136">int</span><span class="sxs-lookup"><span data-stu-id="9da43-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-137">在 RTP 数据包到达之间检测到最大抖动。</span><span class="sxs-lookup"><span data-stu-id="9da43-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="9da43-138">(抖动是&quot;shakiness&quot;通话的衡量。)高抖动值通常由拥塞或过载的媒体服务器导致, 并导致失真或丢失的音频。</span><span class="sxs-lookup"><span data-stu-id="9da43-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-139"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-140">int</span><span class="sxs-lookup"><span data-stu-id="9da43-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-p105">实时传输协议数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 200 毫秒被视为质量可接受。</span><span class="sxs-lookup"><span data-stu-id="9da43-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="9da43-p106">高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</span><span class="sxs-lookup"><span data-stu-id="9da43-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-146">int</span><span class="sxs-lookup"><span data-stu-id="9da43-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-147">实时传输协议数据包传送到另一个终结点和后端所需的最大值 (以毫秒为单位)。</span><span class="sxs-lookup"><span data-stu-id="9da43-147">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="9da43-148">来回行程的时间小于或等于 200 毫秒被视为质量可接受。</span><span class="sxs-lookup"><span data-stu-id="9da43-148">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="9da43-p108">高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</span><span class="sxs-lookup"><span data-stu-id="9da43-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-152">float</span><span class="sxs-lookup"><span data-stu-id="9da43-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-p109">平均实时传输协议 (RTP) 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时，即发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。数据包丢失通常导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="9da43-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-157">float</span><span class="sxs-lookup"><span data-stu-id="9da43-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-158">实时传输协议 (RTP) 数据包丢失的最大速率。</span><span class="sxs-lookup"><span data-stu-id="9da43-158">Maximum rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="9da43-159">(当 RTP 数据包 (用于在 Internet 上传输音频和视频的协议) 无法访问目标时, 将发生数据包丢失。)高损失率通常由拥塞引起;缺少带宽;无线拥挤或干扰;或重载的媒体服务器。</span><span class="sxs-lookup"><span data-stu-id="9da43-159">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="9da43-160">数据包丢失通常导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="9da43-160">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-162">int</span><span class="sxs-lookup"><span data-stu-id="9da43-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-163">发送的数据包数。</span><span class="sxs-lookup"><span data-stu-id="9da43-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-164"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-165">int</span><span class="sxs-lookup"><span data-stu-id="9da43-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-166">在会话结束时可用的估计单向带宽。</span><span class="sxs-lookup"><span data-stu-id="9da43-166">Estimated one-way bandwidth available at the end of the session.</span></span> <span data-ttu-id="9da43-167">以位/秒为单位报告。</span><span class="sxs-lookup"><span data-stu-id="9da43-167">Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-169">int</span><span class="sxs-lookup"><span data-stu-id="9da43-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-170">应用程序共享负载的说明。</span><span class="sxs-lookup"><span data-stu-id="9da43-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-172">float</span><span class="sxs-lookup"><span data-stu-id="9da43-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-173">单向延迟的总金额。</span><span class="sxs-lookup"><span data-stu-id="9da43-173">Total amount of one-way latency.</span></span> <span data-ttu-id="9da43-174">相对单向延迟测量客户端与服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="9da43-174">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-176">float</span><span class="sxs-lookup"><span data-stu-id="9da43-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-177">单向延迟的平均量。</span><span class="sxs-lookup"><span data-stu-id="9da43-177">Average amount of one-way latency.</span></span> <span data-ttu-id="9da43-178">相对单向延迟测量客户端与服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="9da43-178">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-180">float</span><span class="sxs-lookup"><span data-stu-id="9da43-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-181">单向延迟的最大值。</span><span class="sxs-lookup"><span data-stu-id="9da43-181">Maximum amount of one-way latency.</span></span> <span data-ttu-id="9da43-182">相对单向延迟测量客户端与服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="9da43-182">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-184">int</span><span class="sxs-lookup"><span data-stu-id="9da43-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-185">总单向爆发次数。</span><span class="sxs-lookup"><span data-stu-id="9da43-185">Total one-way burst occurrences.</span></span> <span data-ttu-id="9da43-186">"Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 数据流处于不可预知的突发流量。</span><span class="sxs-lookup"><span data-stu-id="9da43-186">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="9da43-187">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="9da43-187">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-189">float</span><span class="sxs-lookup"><span data-stu-id="9da43-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-190">总单向脉冲密度。</span><span class="sxs-lookup"><span data-stu-id="9da43-190">Total one-way burst density.</span></span> <span data-ttu-id="9da43-191">"Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 数据流处于不可预知的突发流量。</span><span class="sxs-lookup"><span data-stu-id="9da43-191">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="9da43-192">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="9da43-192">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-194">float</span><span class="sxs-lookup"><span data-stu-id="9da43-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-195">总的单向脉冲持续时间。</span><span class="sxs-lookup"><span data-stu-id="9da43-195">Total one-way burst duration.</span></span> <span data-ttu-id="9da43-196">"Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 数据流处于不可预知的突发流量。</span><span class="sxs-lookup"><span data-stu-id="9da43-196">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="9da43-197">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="9da43-197">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-199">int</span><span class="sxs-lookup"><span data-stu-id="9da43-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-200">总的单向间隔发生次数。</span><span class="sxs-lookup"><span data-stu-id="9da43-200">Total one-way gap occurrences.</span></span> <span data-ttu-id="9da43-201">"Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 其数据流可预料的猝发。间隙表示这些猝发之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="9da43-201">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="9da43-202">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="9da43-202">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-204">float</span><span class="sxs-lookup"><span data-stu-id="9da43-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-205">总单向间距密度。</span><span class="sxs-lookup"><span data-stu-id="9da43-205">Total one-way gap density.</span></span> <span data-ttu-id="9da43-206">"Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 其数据流可预料的猝发。间隙表示这些猝发之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="9da43-206">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="9da43-207">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="9da43-207">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-209">float</span><span class="sxs-lookup"><span data-stu-id="9da43-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-210">总的单间隔持续时间。</span><span class="sxs-lookup"><span data-stu-id="9da43-210">Total one-way gap duration.</span></span> <span data-ttu-id="9da43-211">"Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 其数据流可预料的猝发。间隙表示这些猝发之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="9da43-211">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="9da43-212">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="9da43-212">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="9da43-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-215">应用程序角色 (共享者或查看者) 和内容类型。</span><span class="sxs-lookup"><span data-stu-id="9da43-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-217">float</span><span class="sxs-lookup"><span data-stu-id="9da43-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-218">远程桌面协议 (RDP) 磁贴的处理总时间。</span><span class="sxs-lookup"><span data-stu-id="9da43-218">Total processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="9da43-219">较高的总计等于查看体验中较长的延迟。</span><span class="sxs-lookup"><span data-stu-id="9da43-219">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-221">float</span><span class="sxs-lookup"><span data-stu-id="9da43-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-222">远程桌面协议 (RDP) 磁贴的平均处理时间。</span><span class="sxs-lookup"><span data-stu-id="9da43-222">Average processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="9da43-223">较高的总计等于查看体验中较长的延迟。</span><span class="sxs-lookup"><span data-stu-id="9da43-223">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-225">float</span><span class="sxs-lookup"><span data-stu-id="9da43-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-226">远程桌面协议 (RDP) 磁贴的最长处理时间。</span><span class="sxs-lookup"><span data-stu-id="9da43-226">Maximum processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="9da43-227">较高的总计等于查看体验中较长的延迟。</span><span class="sxs-lookup"><span data-stu-id="9da43-227">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-229">int</span><span class="sxs-lookup"><span data-stu-id="9da43-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-230">远程桌面协议 (RDP) 磁贴的处理时间内的爆发次数。</span><span class="sxs-lookup"><span data-stu-id="9da43-230">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="9da43-231">"Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 数据流处于不可预知的突发流量。</span><span class="sxs-lookup"><span data-stu-id="9da43-231">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-233">float</span><span class="sxs-lookup"><span data-stu-id="9da43-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-234">远程桌面协议 (RDP) 磁贴的处理时间中的爆发密度。</span><span class="sxs-lookup"><span data-stu-id="9da43-234">Burst density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="9da43-235">"Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 数据流处于不可预知的突发流量。</span><span class="sxs-lookup"><span data-stu-id="9da43-235">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-237">float</span><span class="sxs-lookup"><span data-stu-id="9da43-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-238">远程桌面协议 (RDP) 磁贴的处理时间内的爆发持续时间。</span><span class="sxs-lookup"><span data-stu-id="9da43-238">Burst duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="9da43-239">"Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 数据流处于不可预知的突发流量。</span><span class="sxs-lookup"><span data-stu-id="9da43-239">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-241">int</span><span class="sxs-lookup"><span data-stu-id="9da43-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-242">在远程桌面协议 (RDP) 磁贴的处理时间内出现间隙的情况。</span><span class="sxs-lookup"><span data-stu-id="9da43-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-244">float</span><span class="sxs-lookup"><span data-stu-id="9da43-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-245">远程桌面协议 (RDP) 磁贴的处理时间方面的差距密度。</span><span class="sxs-lookup"><span data-stu-id="9da43-245">Gap density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="9da43-246">低间隙密度相当于更好的观看体验。</span><span class="sxs-lookup"><span data-stu-id="9da43-246">Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-248">float</span><span class="sxs-lookup"><span data-stu-id="9da43-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-249">远程桌面协议 (RDP) 磁贴的处理时间中的差距持续时间。</span><span class="sxs-lookup"><span data-stu-id="9da43-249">Gap duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="9da43-250">短间隙持续时间等于更好的观看体验。</span><span class="sxs-lookup"><span data-stu-id="9da43-250">Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-252">float</span><span class="sxs-lookup"><span data-stu-id="9da43-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-253">捕获的磁贴的总速率 (以平铺/秒为单位)。</span><span class="sxs-lookup"><span data-stu-id="9da43-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-255">float</span><span class="sxs-lookup"><span data-stu-id="9da43-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-256">捕获的图块的平均速率 (以平铺/秒为单位)。</span><span class="sxs-lookup"><span data-stu-id="9da43-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-258">float</span><span class="sxs-lookup"><span data-stu-id="9da43-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-259">捕获的磁贴的最大速率 (以平铺/秒为单位)。</span><span class="sxs-lookup"><span data-stu-id="9da43-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-261">在 t</span><span class="sxs-lookup"><span data-stu-id="9da43-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-262">在捕获的磁贴 (每秒的平铺) 的速率中的爆发次数。</span><span class="sxs-lookup"><span data-stu-id="9da43-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-264">float</span><span class="sxs-lookup"><span data-stu-id="9da43-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-265">已捕获磁贴 (以平铺/秒为单位) 的速率的脉冲密度。</span><span class="sxs-lookup"><span data-stu-id="9da43-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-267">float</span><span class="sxs-lookup"><span data-stu-id="9da43-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-268">以捕获的磁贴的速率 (在每秒的平铺中) 的爆发持续时间。</span><span class="sxs-lookup"><span data-stu-id="9da43-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-270">int</span><span class="sxs-lookup"><span data-stu-id="9da43-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-271">在捕获的磁贴 (每秒平铺) 的速率中的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="9da43-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-273">float</span><span class="sxs-lookup"><span data-stu-id="9da43-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-274">在捕获的图块 (每秒平铺) 的速率中的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="9da43-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-276">float</span><span class="sxs-lookup"><span data-stu-id="9da43-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-277">以捕获的磁贴的速率 (以平铺/秒为单位) 为单位的间隙持续时间。</span><span class="sxs-lookup"><span data-stu-id="9da43-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-279">float</span><span class="sxs-lookup"><span data-stu-id="9da43-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-280">未到达查看器但已被新内容放弃和覆盖的内容的总百分比。</span><span class="sxs-lookup"><span data-stu-id="9da43-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-282">float</span><span class="sxs-lookup"><span data-stu-id="9da43-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-283">未到达查看器但已被新内容放弃和覆盖的内容的平均百分比。</span><span class="sxs-lookup"><span data-stu-id="9da43-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-285">float</span><span class="sxs-lookup"><span data-stu-id="9da43-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-286">未到达查看的内容的最大百分比, 而是丢弃并被新内容覆盖。</span><span class="sxs-lookup"><span data-stu-id="9da43-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-288">int</span><span class="sxs-lookup"><span data-stu-id="9da43-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-289">未到达查看器但已被新内容放弃和覆盖的内容的突发事件发生。</span><span class="sxs-lookup"><span data-stu-id="9da43-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-291">float</span><span class="sxs-lookup"><span data-stu-id="9da43-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-292">未到达查看器的内容的爆发密度, 但已被新内容放弃和覆盖。</span><span class="sxs-lookup"><span data-stu-id="9da43-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-294">float</span><span class="sxs-lookup"><span data-stu-id="9da43-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-295">未到达查看器的内容的爆发期, 而是丢弃并被新内容覆盖。</span><span class="sxs-lookup"><span data-stu-id="9da43-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-297">int</span><span class="sxs-lookup"><span data-stu-id="9da43-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-298">未到达查看器的内容的间隙出现次数, 但已被新内容放弃和覆盖。</span><span class="sxs-lookup"><span data-stu-id="9da43-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-300">float</span><span class="sxs-lookup"><span data-stu-id="9da43-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-301">未到达查看器但已被新内容放弃和覆盖的内容的差距密度。</span><span class="sxs-lookup"><span data-stu-id="9da43-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-303">float</span><span class="sxs-lookup"><span data-stu-id="9da43-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-304">未到达查看器的内容的间距持续时间, 但已被新内容放弃和覆盖。</span><span class="sxs-lookup"><span data-stu-id="9da43-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-306">float</span><span class="sxs-lookup"><span data-stu-id="9da43-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-307">从图形源 scraped 的总帧数。</span><span class="sxs-lookup"><span data-stu-id="9da43-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-309">float</span><span class="sxs-lookup"><span data-stu-id="9da43-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-310">从图形源 scraped 的平均帧数。</span><span class="sxs-lookup"><span data-stu-id="9da43-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-312">float</span><span class="sxs-lookup"><span data-stu-id="9da43-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-313">从图形源 scraped 的最大帧数。</span><span class="sxs-lookup"><span data-stu-id="9da43-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-315">int</span><span class="sxs-lookup"><span data-stu-id="9da43-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-316">帧 scraped 中的爆发出现在图形源中。</span><span class="sxs-lookup"><span data-stu-id="9da43-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-318">float</span><span class="sxs-lookup"><span data-stu-id="9da43-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-319">来自图形源的帧 scraped 中的脉冲密度。</span><span class="sxs-lookup"><span data-stu-id="9da43-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-321">float</span><span class="sxs-lookup"><span data-stu-id="9da43-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-322">帧 scraped 中的爆发持续时间 (来自图形源)。</span><span class="sxs-lookup"><span data-stu-id="9da43-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-324">int</span><span class="sxs-lookup"><span data-stu-id="9da43-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-325">从图形源 scraped 的帧中的间隙出现次数。</span><span class="sxs-lookup"><span data-stu-id="9da43-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-327">float</span><span class="sxs-lookup"><span data-stu-id="9da43-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-328">从图形源 scraped 的帧中的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="9da43-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-330">float</span><span class="sxs-lookup"><span data-stu-id="9da43-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-331">帧 scraped 中的间距持续时间从图形源开始。</span><span class="sxs-lookup"><span data-stu-id="9da43-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-333">float</span><span class="sxs-lookup"><span data-stu-id="9da43-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-334">由查看器接收的传入帧速率总数。</span><span class="sxs-lookup"><span data-stu-id="9da43-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-336">float</span><span class="sxs-lookup"><span data-stu-id="9da43-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-337">查看器接收的平均传入帧速率。</span><span class="sxs-lookup"><span data-stu-id="9da43-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-339">float</span><span class="sxs-lookup"><span data-stu-id="9da43-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-340">查看器接收到的最大传入磁贴速度。</span><span class="sxs-lookup"><span data-stu-id="9da43-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-342">int</span><span class="sxs-lookup"><span data-stu-id="9da43-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-343">由查看器接收的传入磁贴速率中的爆发次数。</span><span class="sxs-lookup"><span data-stu-id="9da43-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-345">float</span><span class="sxs-lookup"><span data-stu-id="9da43-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-346">由查看器接收的传入磁贴速率中的脉冲密度。</span><span class="sxs-lookup"><span data-stu-id="9da43-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-348">float</span><span class="sxs-lookup"><span data-stu-id="9da43-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-349">由查看器接收的传入磁贴速率中的脉冲持续时间。</span><span class="sxs-lookup"><span data-stu-id="9da43-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-351">int</span><span class="sxs-lookup"><span data-stu-id="9da43-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-352">由查看器接收的传入磁贴速率中的间隙出现次数。</span><span class="sxs-lookup"><span data-stu-id="9da43-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-354">float</span><span class="sxs-lookup"><span data-stu-id="9da43-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-355">由查看器接收的传入磁贴费率中的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="9da43-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-357">float</span><span class="sxs-lookup"><span data-stu-id="9da43-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-358">由查看器接收的传入磁贴速率中的间隙持续时间。</span><span class="sxs-lookup"><span data-stu-id="9da43-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-360">float</span><span class="sxs-lookup"><span data-stu-id="9da43-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-361">由查看器接收的传入帧速率总数。</span><span class="sxs-lookup"><span data-stu-id="9da43-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-363">float</span><span class="sxs-lookup"><span data-stu-id="9da43-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-364">查看器接收的平均传入帧速率。</span><span class="sxs-lookup"><span data-stu-id="9da43-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-366">float</span><span class="sxs-lookup"><span data-stu-id="9da43-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-367">查看器接收到的最大传入帧速率。</span><span class="sxs-lookup"><span data-stu-id="9da43-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-369">int</span><span class="sxs-lookup"><span data-stu-id="9da43-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-370">由查看器接收的传入帧速率中的爆发次数。</span><span class="sxs-lookup"><span data-stu-id="9da43-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-372">float</span><span class="sxs-lookup"><span data-stu-id="9da43-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-373">查看器接收的传入帧速率中的脉冲密度。</span><span class="sxs-lookup"><span data-stu-id="9da43-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-375">float</span><span class="sxs-lookup"><span data-stu-id="9da43-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-376">按浏览器接收的传入帧速率中的爆发持续时间。</span><span class="sxs-lookup"><span data-stu-id="9da43-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-378">int</span><span class="sxs-lookup"><span data-stu-id="9da43-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-379">由查看器接收的传入帧速率中的间隙出现次数。</span><span class="sxs-lookup"><span data-stu-id="9da43-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-381">float</span><span class="sxs-lookup"><span data-stu-id="9da43-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-382">查看器接收的传入帧速率中的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="9da43-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-384">float</span><span class="sxs-lookup"><span data-stu-id="9da43-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-385">按查看器接收的传入帧速率中的间隙持续时间。</span><span class="sxs-lookup"><span data-stu-id="9da43-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-387">float</span><span class="sxs-lookup"><span data-stu-id="9da43-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-388">发件人的传出磁贴总费率。</span><span class="sxs-lookup"><span data-stu-id="9da43-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-390">float</span><span class="sxs-lookup"><span data-stu-id="9da43-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-391">发件人的平均传出磁贴速率。</span><span class="sxs-lookup"><span data-stu-id="9da43-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-393">float</span><span class="sxs-lookup"><span data-stu-id="9da43-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-394">发件人的最大传出磁贴费率。</span><span class="sxs-lookup"><span data-stu-id="9da43-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-396">int</span><span class="sxs-lookup"><span data-stu-id="9da43-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-397">发件人的传出磁贴速率中的爆发次数。</span><span class="sxs-lookup"><span data-stu-id="9da43-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-399">float</span><span class="sxs-lookup"><span data-stu-id="9da43-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-400">发件人的传出磁贴费率的脉冲密度。</span><span class="sxs-lookup"><span data-stu-id="9da43-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-402">float</span><span class="sxs-lookup"><span data-stu-id="9da43-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-403">发件人的传出磁贴费率的爆发持续时间。</span><span class="sxs-lookup"><span data-stu-id="9da43-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-405">int</span><span class="sxs-lookup"><span data-stu-id="9da43-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-406">发件人的传出磁贴费率中的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="9da43-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-408">float</span><span class="sxs-lookup"><span data-stu-id="9da43-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-409">发件人的传出磁贴费率的差距密度。</span><span class="sxs-lookup"><span data-stu-id="9da43-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-411">float</span><span class="sxs-lookup"><span data-stu-id="9da43-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-412">发件人的传出磁贴费率的差距持续时间。</span><span class="sxs-lookup"><span data-stu-id="9da43-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-414">float</span><span class="sxs-lookup"><span data-stu-id="9da43-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-415">发件人的传出帧费率总数。</span><span class="sxs-lookup"><span data-stu-id="9da43-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-417">float</span><span class="sxs-lookup"><span data-stu-id="9da43-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-418">发件人的平均传出帧速率。</span><span class="sxs-lookup"><span data-stu-id="9da43-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-420">float</span><span class="sxs-lookup"><span data-stu-id="9da43-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-421">发件人的最大传出帧速率。</span><span class="sxs-lookup"><span data-stu-id="9da43-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-423">int</span><span class="sxs-lookup"><span data-stu-id="9da43-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-424">发件人的传出帧费率中出现爆发。</span><span class="sxs-lookup"><span data-stu-id="9da43-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-426">float</span><span class="sxs-lookup"><span data-stu-id="9da43-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-427">发件人的传出帧费率的脉冲密度。</span><span class="sxs-lookup"><span data-stu-id="9da43-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-429">float</span><span class="sxs-lookup"><span data-stu-id="9da43-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-430">发件人的传出帧费率中的爆发持续时间。</span><span class="sxs-lookup"><span data-stu-id="9da43-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-432">int</span><span class="sxs-lookup"><span data-stu-id="9da43-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-433">发件人的传出帧费率中的间隙出现次数。</span><span class="sxs-lookup"><span data-stu-id="9da43-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-435">float</span><span class="sxs-lookup"><span data-stu-id="9da43-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-436">发件人的传出帧费率中的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="9da43-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-438">float</span><span class="sxs-lookup"><span data-stu-id="9da43-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-439">发件人的传出帧费率中的差距持续时间。</span><span class="sxs-lookup"><span data-stu-id="9da43-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-441">int</span><span class="sxs-lookup"><span data-stu-id="9da43-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-442">平均视频分辨率高度 (以像素为单位)。</span><span class="sxs-lookup"><span data-stu-id="9da43-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-444">int</span><span class="sxs-lookup"><span data-stu-id="9da43-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-445">平均视频分辨率宽度 (以像素为单位)。</span><span class="sxs-lookup"><span data-stu-id="9da43-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-446"><strong>封</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-447">bit</span><span class="sxs-lookup"><span data-stu-id="9da43-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-448">入站传输的平均帧速率 (以每秒帧数为单位)。</span><span class="sxs-lookup"><span data-stu-id="9da43-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9da43-449"><strong>出站</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-450">bit</span><span class="sxs-lookup"><span data-stu-id="9da43-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-451">出站传输的平均帧速率 (以每秒帧数为单位)。</span><span class="sxs-lookup"><span data-stu-id="9da43-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9da43-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="9da43-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="9da43-453">bit</span><span class="sxs-lookup"><span data-stu-id="9da43-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9da43-454">1表示流方向来自调用方的调用方。</span><span class="sxs-lookup"><span data-stu-id="9da43-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="9da43-455">0表示流方向来自被调用方的调用方。</span><span class="sxs-lookup"><span data-stu-id="9da43-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

