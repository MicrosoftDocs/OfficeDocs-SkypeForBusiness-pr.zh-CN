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
ms.openlocfilehash: 9b729112aa0fb064a518c50212a6a041a6661be3
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48499499"
---
# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="ab0b3-102">Lync Server 2013 中的 AppSharingStream 表</span><span class="sxs-lookup"><span data-stu-id="ab0b3-102">AppSharingStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab0b3-103">_**上次修改的主题：** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="ab0b3-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="ab0b3-104">AppSharingStream 表包含用于应用程序共享的网络流的用户体验质量指标。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="ab0b3-105">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab0b3-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="ab0b3-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="ab0b3-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="ab0b3-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="ab0b3-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="ab0b3-112">主、外</span><span class="sxs-lookup"><span data-stu-id="ab0b3-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab0b3-113">会话开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-115">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-115">int</span></span></p></td>
<td><p><span data-ttu-id="ab0b3-116">主、外</span><span class="sxs-lookup"><span data-stu-id="ab0b3-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab0b3-117">用于区分在相同日期和时间开始的会话的顺序标识符。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="ab0b3-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="ab0b3-120">主、外</span><span class="sxs-lookup"><span data-stu-id="ab0b3-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ab0b3-p102">表示在呼叫中使用的视频行的类型。允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="ab0b3-123">0–音频</span><span class="sxs-lookup"><span data-stu-id="ab0b3-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="ab0b3-124">1–视频</span><span class="sxs-lookup"><span data-stu-id="ab0b3-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="ab0b3-125">2 – 全景视频</span><span class="sxs-lookup"><span data-stu-id="ab0b3-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="ab0b3-126">3–应用程序/桌面共享</span><span class="sxs-lookup"><span data-stu-id="ab0b3-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-127"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-128">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-128">int</span></span></p></td>
<td><p><span data-ttu-id="ab0b3-129">主</span><span class="sxs-lookup"><span data-stu-id="ab0b3-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="ab0b3-130">应用程序共享流的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-132">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-133">在 RTP 数据包到达之间检测到的平均抖动率。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="ab0b3-134"> (抖动是 shakiness 的衡量指标 &quot; &quot; 。 ) 高抖动值通常由拥塞或过载的媒体服务器引起，并导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-136">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-137">在 RTP 数据包到达之间检测到的最大抖动率。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="ab0b3-138"> (抖动是 shakiness 的衡量指标 &quot; &quot; 。 ) 高抖动值通常由拥塞或过载的媒体服务器引起，并导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-139"><strong>工程</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-140">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-p105">实时传输协议数据包来往于另一个终结点所需的平均时间量（以毫秒为单位）。来回行程的时间小于或等于 200 毫秒被视为质量可接受。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="ab0b3-p106">高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-146">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-p107">实时传输协议数据包来往于另一个终结点所需的最大时间量（以毫秒为单位）。来回行程的时间小于或等于 200 毫秒被视为质量可接受。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="ab0b3-p108">高来回行程时间值可能是由国际呼叫路由、路由配置错误或媒体服务器超载造成的，从而导致双向实时音频对话存在问题。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-152">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-p109">平均实时传输协议 (RTP) 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时，即发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。数据包丢失通常导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-157">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-p110">最大实时传输协议 (RTP) 数据包丢失率。（当 RTP 数据包（一项用于在 Internet 中传输音频和视频的协议）无法到达其目标位置时，即发生数据包丢失。）高丢失率通常是由拥塞、带宽不足、无线拥塞/干扰或媒体服务器超载造成的。数据包丢失通常导致音频失真或丢失。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-162">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-163">发送的数据包数。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-164"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-165">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-p111">在会话末尾可用的单向带宽的估计值。以每秒的位数的形式报告。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-169">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-170">应用程序共享负载的描述。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-172">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-p112">单向延迟的总量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-176">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-p113">单向延迟的平均量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-180">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-p114">单向延迟的最大量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-184">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-p115">单向突发总发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-189">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-p116">单向突发总密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-194">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-p117">单向突发总持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-199">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-p118">单向间隙总发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-204">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-p119">单向间隙总密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-209">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-p120">单向间隙总持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-214">varChar (256) </span><span class="sxs-lookup"><span data-stu-id="ab0b3-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-215">应用程序角色（共享者或查看者）和内容类型。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-217">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-p121">远程桌面协议 (RDP) 图块的总处理时间。总时间量越大，查看体验的延迟就越长。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-221">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-p122">远程桌面协议 (RDP) 图块的平均处理时间。总时间量越大，查看体验的延迟就越长。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-225">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-p123">远程桌面协议 (RDP) 图块的最大处理时间。总时间量越大，查看体验的延迟就越长。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-229">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-p124">远程桌面协议 (RDP) 图块的处理时间中的突发发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-233">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-p125">远程桌面协议 (RDP) 图块的处理时间中的突发密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-237">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-p126">远程桌面协议 (RDP) 图块的处理时间中的突发持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-241">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-242">远程桌面协议 (RDP) 图块的处理时间中的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-244">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-p127">远程桌面协议 (RDP) 图块的处理时间中的间隙密度。间隙密度越低，查看体验就越佳。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-248">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-p128">远程桌面协议 (RDP) 图块的处理时间中的间隙持续时间。间隙持续时间越短，查看体验就越佳。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-252">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-253">图块的总捕获率（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-255">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-256">图块的平均捕获率（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-258">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-259">图块的最大捕获率（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-261">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-262">图块的捕获率的突发发生次数（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-264">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-265">图块的捕获率的突发密度（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-267">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-268">图块的捕获率的突发持续时间（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-270">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-271">图块的捕获率的间隙发生次数（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-273">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-274">图块的捕获率的间隙密度（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-276">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-277">图块的捕获率的间隙持续时间（以每秒的图块数为单位）。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-279">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-280">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的总百分比。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-282">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-283">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的平均百分比。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-285">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-286">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的最大百分比。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-288">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-289">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的突发发生次数。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-291">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-292">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的突发密度。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-294">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-295">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的突发持续时间。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-297">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-298">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-300">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-301">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-303">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-304">未送达给查看者但已被丢弃和已被新鲜内容覆盖的内容的间隙持续时间。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-306">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-307">从图形源擦除的总帧数。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-309">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-310">从图形源擦除的平均帧数。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-312">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-313">从图形源擦除的最大帧数。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-315">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-316">从图形源擦除的帧数的突发发生次数。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-318">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-319">从图形源擦除的帧数的突发密度。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-321">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-322">从图形源擦除的帧数的突发持续时间。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-324">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-325">从图形源擦除的帧数的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-327">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-328">从图形源擦除的帧数的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-330">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-331">从图形源擦除的帧数的间隙持续时间。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-333">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-334">查看者收到的总传入帧速率。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-336">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-337">查看者收到的平均传入帧速率。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-339">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-340">查看者收到的最大传入图块速率。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-342">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-343">查看者收到的传入图块速率的突发发生次数。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-345">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-346">查看者收到的传入图块速率的突发密度。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-348">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-349">查看者收到的传入图块速率的突发持续时间。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-351">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-352">查看者收到的传入图块速率的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-354">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-355">查看者收到的传入图块速率的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-357">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-358">查看者收到的传入图块速率的间隙持续时间。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-360">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-361">查看者收到的总传入帧速率。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-363">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-364">查看者收到的平均传入帧速率。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-366">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-367">查看者收到的最大传入帧速率。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-369">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-370">查看者收到的传入帧速率的突发发生次数。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-372">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-373">查看者收到的传入帧速率的突发密度。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-375">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-376">查看者收到的传入帧速率的突发持续时间。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-378">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-379">查看者收到的传入帧速率的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-381">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-382">查看者收到的传入帧速率的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-384">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-385">查看者收到的传入帧速率的间隙持续时间。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-387">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-388">发送者的总传出图块速率。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-390">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-391">发送者的平均传出图块速率。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-393">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-394">发送者的最大传出图块速率。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-396">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-397">发送者的传出图块速率的突发发生次数。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-399">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-400">发送者的传出图块速率的突发密度。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-402">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-403">发送者的传出图块速率的突发持续时间。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-405">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-406">发送者的传出图块速率的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-408">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-409">发送者的传出图块速率的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-411">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-412">发送者的传出图块速率的间隙持续时间。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-414">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-415">发送者的总传出帧速率。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-417">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-418">发送者的平均传出帧速率。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-420">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-421">发送者的最大传出帧速率。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-423">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-424">发送者的传出帧速率的突发发生次数。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-426">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-427">发送者的传出帧速率的突发密度。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-429">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-430">发送者的传出帧速率的突发持续时间。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-432">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-433">发送者的传出帧速率的间隙发生次数。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-435">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-436">发送者的传出帧速率的间隙密度。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-438">float</span><span class="sxs-lookup"><span data-stu-id="ab0b3-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-439">发送者的传出帧速率的间隙持续时间。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-441">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-442">平均视频分辨率高度（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-444">int</span><span class="sxs-lookup"><span data-stu-id="ab0b3-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-445">平均视频分辨率宽度（以像素为单位）。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-446"><strong>进货</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-447">位</span><span class="sxs-lookup"><span data-stu-id="ab0b3-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-448">入站传输的平均帧速率（以每秒帧数为单位）。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab0b3-449"><strong>出站</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-450">位</span><span class="sxs-lookup"><span data-stu-id="ab0b3-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-451">出站传输的平均帧速率（以每秒帧数为单位）。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab0b3-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="ab0b3-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="ab0b3-453">位</span><span class="sxs-lookup"><span data-stu-id="ab0b3-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ab0b3-454">1 表示流方向是从呼叫者到被叫方。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="ab0b3-455">0 表示流方向是从被叫方到呼叫者。</span><span class="sxs-lookup"><span data-stu-id="ab0b3-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

