---
title: Lync Server 2013： AppSharingStream 表
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
ms.openlocfilehash: 4454b7fbcaffc1fc302d5c434666cfdfa93ada36
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="89e97-102">Lync Server 2013 中的 AppSharingStream 表</span><span class="sxs-lookup"><span data-stu-id="89e97-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="89e97-103">_**上次修改的主题：** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="89e97-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="89e97-104">AppSharingStream 表包含用于应用程序共享的网络流的用户体验质量指标。</span><span class="sxs-lookup"><span data-stu-id="89e97-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="89e97-105">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="89e97-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="89e97-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="89e97-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="89e97-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="89e97-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="89e97-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="89e97-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="89e97-112">主、外</span><span class="sxs-lookup"><span data-stu-id="89e97-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="89e97-113">会话开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="89e97-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-115">int</span><span class="sxs-lookup"><span data-stu-id="89e97-115">int</span></span></p></td>
<td><p><span data-ttu-id="89e97-116">主、外</span><span class="sxs-lookup"><span data-stu-id="89e97-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="89e97-117">用于区分在相同日期和时间开始的会话的顺序标识符。</span><span class="sxs-lookup"><span data-stu-id="89e97-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="89e97-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="89e97-120">主、外</span><span class="sxs-lookup"><span data-stu-id="89e97-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="89e97-p102">表示在呼叫中使用的视频行的类型。允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="89e97-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="89e97-123">0–音频</span><span class="sxs-lookup"><span data-stu-id="89e97-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="89e97-124">1–视频</span><span class="sxs-lookup"><span data-stu-id="89e97-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="89e97-125">2 – 全景视频</span><span class="sxs-lookup"><span data-stu-id="89e97-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="89e97-126">3–应用程序/桌面共享</span><span class="sxs-lookup"><span data-stu-id="89e97-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-127"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-128">int</span><span class="sxs-lookup"><span data-stu-id="89e97-128">int</span></span></p></td>
<td><p><span data-ttu-id="89e97-129">主</span><span class="sxs-lookup"><span data-stu-id="89e97-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="89e97-130">应用程序共享流的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="89e97-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-132">int</span><span class="sxs-lookup"><span data-stu-id="89e97-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-133">在 RTP 数据包到达之间检测到的平均抖动率。</span><span class="sxs-lookup"><span data-stu-id="89e97-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="89e97-134">（抖动是对&quot;shakiness&quot;的衡量。高抖动值通常是由拥塞或过载的媒体服务器引起的，并导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="89e97-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-136">int</span><span class="sxs-lookup"><span data-stu-id="89e97-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-137">在 RTP 数据包到达之间检测到的最大抖动率。</span><span class="sxs-lookup"><span data-stu-id="89e97-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="89e97-138">（抖动是对&quot;shakiness&quot;的衡量。高抖动值通常是由拥塞或过载的媒体服务器引起的，并导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="89e97-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-139"><strong>工程</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-140">int</span><span class="sxs-lookup"><span data-stu-id="89e97-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-p105">实时传输协议数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 200 毫秒被视为质量可接受。</span><span class="sxs-lookup"><span data-stu-id="89e97-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="89e97-p106">高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</span><span class="sxs-lookup"><span data-stu-id="89e97-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-146">int</span><span class="sxs-lookup"><span data-stu-id="89e97-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-p107">实时传输协议数据包来往于另一个终结点所需的最大时间量（以毫秒为单位）。来回行程的时间小于或等于 200 毫秒被视为质量可接受。</span><span class="sxs-lookup"><span data-stu-id="89e97-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="89e97-p108">高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</span><span class="sxs-lookup"><span data-stu-id="89e97-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-152">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-p109">平均实时传输协议 (RTP) 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时，即发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。数据包丢失通常导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="89e97-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-157">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-p110">最大实时传输协议 (RTP) 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时，即发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。数据包丢失通常导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="89e97-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-162">int</span><span class="sxs-lookup"><span data-stu-id="89e97-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-163">发送的数据包数。</span><span class="sxs-lookup"><span data-stu-id="89e97-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-164"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-165">int</span><span class="sxs-lookup"><span data-stu-id="89e97-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-p111">在会话末尾可用的单向带宽的估计值。以每秒的位数的形式报告。</span><span class="sxs-lookup"><span data-stu-id="89e97-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-169">int</span><span class="sxs-lookup"><span data-stu-id="89e97-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-170">应用程序共享负载的描述。</span><span class="sxs-lookup"><span data-stu-id="89e97-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-172">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-p112">单向延迟的总量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="89e97-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-176">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-p113">单向延迟的平均量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="89e97-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-180">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-p114">单向延迟的最大量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="89e97-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-184">int</span><span class="sxs-lookup"><span data-stu-id="89e97-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-p115">单向突发总发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="89e97-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-189">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-p116">单向突发总密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="89e97-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-194">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-p117">单向突发总持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="89e97-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-199">int</span><span class="sxs-lookup"><span data-stu-id="89e97-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-p118">单向间隙总发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="89e97-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-204">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-p119">单向间隙总密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="89e97-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-209">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-p120">单向间隙总持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="89e97-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-214">varChar （256）</span><span class="sxs-lookup"><span data-stu-id="89e97-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-215">应用程序角色（共享者或查看者）和内容类型。</span><span class="sxs-lookup"><span data-stu-id="89e97-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-217">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-p121">远程桌面协议 (RDP) 图块的总处理时间。总时间量越大，查看体验的延迟就越长。</span><span class="sxs-lookup"><span data-stu-id="89e97-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-221">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-p122">远程桌面协议 (RDP) 图块的平均处理时间。总时间量越大，查看体验的延迟就越长。</span><span class="sxs-lookup"><span data-stu-id="89e97-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-225">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-p123">远程桌面协议 (RDP) 图块的最大处理时间。总时间量越大，查看体验的延迟就越长。</span><span class="sxs-lookup"><span data-stu-id="89e97-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-229">int</span><span class="sxs-lookup"><span data-stu-id="89e97-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-p124">远程桌面协议 (RDP) 图块的处理时间中的突发发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。</span><span class="sxs-lookup"><span data-stu-id="89e97-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-233">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-p125">远程桌面协议 (RDP) 图块的处理时间中的突发密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。</span><span class="sxs-lookup"><span data-stu-id="89e97-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-237">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-p126">远程桌面协议 (RDP) 图块的处理时间中的突发持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。</span><span class="sxs-lookup"><span data-stu-id="89e97-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-241">int</span><span class="sxs-lookup"><span data-stu-id="89e97-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-242">远程桌面协议 (RDP) 图块的处理时间中的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="89e97-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-244">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-p127">远程桌面协议 (RDP) 图块的处理时间中的间隙密度。间隙密度越低，查看体验就越佳。</span><span class="sxs-lookup"><span data-stu-id="89e97-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-248">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-p128">远程桌面协议 (RDP) 图块的处理时间中的间隙持续时间。间隙持续时间越短，查看体验就越佳。</span><span class="sxs-lookup"><span data-stu-id="89e97-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-252">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-253">图块的总捕获率（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="89e97-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-255">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-256">图块的平均捕获率（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="89e97-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-258">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-259">图块的最大捕获率（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="89e97-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-261">int</span><span class="sxs-lookup"><span data-stu-id="89e97-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-262">图块的捕获率的突发发生次数（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="89e97-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-264">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-265">图块的捕获率的突发密度（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="89e97-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-267">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-268">图块的捕获率的突发持续时间（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="89e97-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-270">int</span><span class="sxs-lookup"><span data-stu-id="89e97-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-271">图块的捕获率的间隙发生次数（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="89e97-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-273">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-274">图块的捕获率的间隙密度（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="89e97-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-276">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-277">图块的捕获率的间隙持续时间（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="89e97-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-279">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-280">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的总百分比。</span><span class="sxs-lookup"><span data-stu-id="89e97-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-282">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-283">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的平均百分比。</span><span class="sxs-lookup"><span data-stu-id="89e97-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-285">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-286">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的最大百分比。</span><span class="sxs-lookup"><span data-stu-id="89e97-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-288">int</span><span class="sxs-lookup"><span data-stu-id="89e97-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-289">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的突发发生次数。</span><span class="sxs-lookup"><span data-stu-id="89e97-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-291">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-292">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的突发密度。</span><span class="sxs-lookup"><span data-stu-id="89e97-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-294">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-295">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的突发持续时间。</span><span class="sxs-lookup"><span data-stu-id="89e97-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-297">int</span><span class="sxs-lookup"><span data-stu-id="89e97-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-298">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="89e97-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-300">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-301">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="89e97-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-303">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-304">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的间隙持续时间。</span><span class="sxs-lookup"><span data-stu-id="89e97-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-306">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-307">从图形源擦除的总帧数。</span><span class="sxs-lookup"><span data-stu-id="89e97-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-309">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-310">从图形源擦除的平均帧数。</span><span class="sxs-lookup"><span data-stu-id="89e97-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-312">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-313">从图形源擦除的最大帧数。</span><span class="sxs-lookup"><span data-stu-id="89e97-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-315">int</span><span class="sxs-lookup"><span data-stu-id="89e97-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-316">从图形源擦除的帧数的突发发生次数。</span><span class="sxs-lookup"><span data-stu-id="89e97-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-318">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-319">从图形源擦除的帧数的突发密度。</span><span class="sxs-lookup"><span data-stu-id="89e97-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-321">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-322">从图形源擦除的帧数的突发持续时间。</span><span class="sxs-lookup"><span data-stu-id="89e97-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-324">int</span><span class="sxs-lookup"><span data-stu-id="89e97-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-325">从图形源擦除的帧数的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="89e97-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-327">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-328">从图形源擦除的帧数的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="89e97-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-330">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-331">从图形源擦除的帧数的间隙持续时间。</span><span class="sxs-lookup"><span data-stu-id="89e97-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-333">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-334">查看者收到的总传入帧速率。</span><span class="sxs-lookup"><span data-stu-id="89e97-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-336">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-337">查看者收到的平均传入帧速率。</span><span class="sxs-lookup"><span data-stu-id="89e97-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-339">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-340">查看者收到的最大传入图块速率。</span><span class="sxs-lookup"><span data-stu-id="89e97-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-342">int</span><span class="sxs-lookup"><span data-stu-id="89e97-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-343">查看者收到的传入图块速率的突发发生次数。</span><span class="sxs-lookup"><span data-stu-id="89e97-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-345">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-346">查看者收到的传入图块速率的突发密度。</span><span class="sxs-lookup"><span data-stu-id="89e97-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-348">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-349">查看者收到的传入图块速率的突发持续时间。</span><span class="sxs-lookup"><span data-stu-id="89e97-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-351">int</span><span class="sxs-lookup"><span data-stu-id="89e97-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-352">查看者收到的传入图块速率的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="89e97-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-354">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-355">查看者收到的传入图块速率的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="89e97-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-357">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-358">查看者收到的传入图块速率的间隙持续时间。</span><span class="sxs-lookup"><span data-stu-id="89e97-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-360">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-361">查看者收到的总传入帧速率。</span><span class="sxs-lookup"><span data-stu-id="89e97-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-363">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-364">查看者收到的平均传入帧速率。</span><span class="sxs-lookup"><span data-stu-id="89e97-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-366">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-367">查看者收到的最大传入帧速率。</span><span class="sxs-lookup"><span data-stu-id="89e97-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-369">int</span><span class="sxs-lookup"><span data-stu-id="89e97-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-370">查看者收到的传入帧速率的突发发生次数。</span><span class="sxs-lookup"><span data-stu-id="89e97-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-372">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-373">查看者收到的传入帧速率的突发密度。</span><span class="sxs-lookup"><span data-stu-id="89e97-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-375">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-376">查看者收到的传入帧速率的突发持续时间。</span><span class="sxs-lookup"><span data-stu-id="89e97-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-378">int</span><span class="sxs-lookup"><span data-stu-id="89e97-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-379">查看者收到的传入帧速率的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="89e97-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-381">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-382">查看者收到的传入帧速率的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="89e97-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-384">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-385">查看者收到的传入帧速率的间隙持续时间。</span><span class="sxs-lookup"><span data-stu-id="89e97-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-387">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-388">发送者的总传出图块速率。</span><span class="sxs-lookup"><span data-stu-id="89e97-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-390">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-391">发送者的平均传出图块速率。</span><span class="sxs-lookup"><span data-stu-id="89e97-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-393">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-394">发送者的最大传出图块速率。</span><span class="sxs-lookup"><span data-stu-id="89e97-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-396">int</span><span class="sxs-lookup"><span data-stu-id="89e97-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-397">发送者的传出图块速率的突发发生次数。</span><span class="sxs-lookup"><span data-stu-id="89e97-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-399">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-400">发送者的传出图块速率的突发密度。</span><span class="sxs-lookup"><span data-stu-id="89e97-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-402">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-403">发送者的传出图块速率的突发持续时间。</span><span class="sxs-lookup"><span data-stu-id="89e97-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-405">int</span><span class="sxs-lookup"><span data-stu-id="89e97-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-406">发送者的传出图块速率的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="89e97-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-408">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-409">发送者的传出图块速率的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="89e97-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-411">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-412">发送者的传出图块速率的间隙持续时间。</span><span class="sxs-lookup"><span data-stu-id="89e97-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-414">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-415">发送者的总传出帧速率。</span><span class="sxs-lookup"><span data-stu-id="89e97-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-417">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-418">发送者的平均传出帧速率。</span><span class="sxs-lookup"><span data-stu-id="89e97-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-420">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-421">发送者的最大传出帧速率。</span><span class="sxs-lookup"><span data-stu-id="89e97-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-423">int</span><span class="sxs-lookup"><span data-stu-id="89e97-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-424">发送者的传出帧速率的突发发生次数。</span><span class="sxs-lookup"><span data-stu-id="89e97-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-426">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-427">发送者的传出帧速率的突发密度。</span><span class="sxs-lookup"><span data-stu-id="89e97-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-429">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-430">发送者的传出帧速率的突发持续时间。</span><span class="sxs-lookup"><span data-stu-id="89e97-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-432">int</span><span class="sxs-lookup"><span data-stu-id="89e97-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-433">发送者的传出帧速率的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="89e97-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-435">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-436">发送者的传出帧速率的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="89e97-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-438">点数</span><span class="sxs-lookup"><span data-stu-id="89e97-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-439">发送者的传出帧速率的间隙持续时间。</span><span class="sxs-lookup"><span data-stu-id="89e97-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-441">int</span><span class="sxs-lookup"><span data-stu-id="89e97-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-442">平均视频分辨率高度（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="89e97-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-444">int</span><span class="sxs-lookup"><span data-stu-id="89e97-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-445">平均视频分辨率宽度（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="89e97-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-446"><strong>进货</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-447">位</span><span class="sxs-lookup"><span data-stu-id="89e97-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-448">入站传输的平均帧速率（以每秒帧数为单位）。</span><span class="sxs-lookup"><span data-stu-id="89e97-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="89e97-449"><strong>出站</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-450">位</span><span class="sxs-lookup"><span data-stu-id="89e97-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-451">出站传输的平均帧速率（以每秒帧数为单位）。</span><span class="sxs-lookup"><span data-stu-id="89e97-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="89e97-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="89e97-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="89e97-453">位</span><span class="sxs-lookup"><span data-stu-id="89e97-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="89e97-454">1 表示流方向是从呼叫者到被叫方。</span><span class="sxs-lookup"><span data-stu-id="89e97-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="89e97-455">0 表示流方向是从被叫方到呼叫者。</span><span class="sxs-lookup"><span data-stu-id="89e97-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

