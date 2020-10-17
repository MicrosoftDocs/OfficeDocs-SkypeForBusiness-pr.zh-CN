---
title: Lync Server 2013： AudioStream 表
description: Lync Server 2013： AudioStream 表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8af2e622e14c54fa4f9a6313e1b0dae8f2483132
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552338"
---
# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="7a655-103">Lync Server 2013 中的 AudioStream 表</span><span class="sxs-lookup"><span data-stu-id="7a655-103">AudioStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a655-104">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7a655-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7a655-105">每个记录表示一个音频流。</span><span class="sxs-lookup"><span data-stu-id="7a655-105">Each record represents one audio stream.</span></span> <span data-ttu-id="7a655-106">一个音频媒体行通常包含两个音频流。</span><span class="sxs-lookup"><span data-stu-id="7a655-106">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7a655-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7a655-108"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7a655-109"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7a655-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7a655-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-112">datetime</span><span class="sxs-lookup"><span data-stu-id="7a655-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="7a655-113">主</span><span class="sxs-lookup"><span data-stu-id="7a655-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="7a655-114"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="7a655-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-116">int</span><span class="sxs-lookup"><span data-stu-id="7a655-116">int</span></span></p></td>
<td><p><span data-ttu-id="7a655-117">主</span><span class="sxs-lookup"><span data-stu-id="7a655-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="7a655-118"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="7a655-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="7a655-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7a655-121">主</span><span class="sxs-lookup"><span data-stu-id="7a655-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="7a655-122"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="7a655-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-123"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-123"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-124">int</span><span class="sxs-lookup"><span data-stu-id="7a655-124">int</span></span></p></td>
<td><p><span data-ttu-id="7a655-125">主</span><span class="sxs-lookup"><span data-stu-id="7a655-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="7a655-126">媒体行中的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="7a655-126">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-127"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-127"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-128">int</span><span class="sxs-lookup"><span data-stu-id="7a655-128">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-129">实时控制协议 (RTCP) 统计信息中的平均网络抖动。</span><span class="sxs-lookup"><span data-stu-id="7a655-129">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-130"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-130"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-131">int</span><span class="sxs-lookup"><span data-stu-id="7a655-131">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-132">呼叫期间的最大网络抖动。</span><span class="sxs-lookup"><span data-stu-id="7a655-132">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-133"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-133"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-134">十进制 (5、4) </span><span class="sxs-lookup"><span data-stu-id="7a655-134">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-135">呼叫期间的平均数据包丢失率。</span><span class="sxs-lookup"><span data-stu-id="7a655-135">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-136"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-136"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-137">十进制 (5、4) </span><span class="sxs-lookup"><span data-stu-id="7a655-137">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-138">呼叫期间观测到的数据包丢失最大值。</span><span class="sxs-lookup"><span data-stu-id="7a655-138">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-139"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-139"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-140">十进制 (9、4) </span><span class="sxs-lookup"><span data-stu-id="7a655-140">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-141">呼叫期间出现猝发损失期间的数据包丢失的平均密度。</span><span class="sxs-lookup"><span data-stu-id="7a655-141">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-142"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-142"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-143">int</span><span class="sxs-lookup"><span data-stu-id="7a655-143">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-144">呼叫期间出现猝发损失期间的数据包丢失的平均持续时间。</span><span class="sxs-lookup"><span data-stu-id="7a655-144">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-145"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-145"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-146">十进制 (9、4) </span><span class="sxs-lookup"><span data-stu-id="7a655-146">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-147">在出现猝发数据包丢失之间间隔期间的数据包丢失的平均密度。</span><span class="sxs-lookup"><span data-stu-id="7a655-147">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-148"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-148"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-149">int</span><span class="sxs-lookup"><span data-stu-id="7a655-149">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-150">猝发数据包丢失间隔的平均持续时间。</span><span class="sxs-lookup"><span data-stu-id="7a655-150">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-151"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-151"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-152">Int</span><span class="sxs-lookup"><span data-stu-id="7a655-152">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-153">音频流的数据包计数。</span><span class="sxs-lookup"><span data-stu-id="7a655-153">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-154"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-154"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-155">Int</span><span class="sxs-lookup"><span data-stu-id="7a655-155">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-156">音频流的带宽预估。</span><span class="sxs-lookup"><span data-stu-id="7a655-156">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-157"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-157"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-158">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="7a655-158">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-159">整个呼叫的网络 MOS 降级。</span><span class="sxs-lookup"><span data-stu-id="7a655-159">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="7a655-160">范围是0.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="7a655-160">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="7a655-161">此指标显示由于抖动和数据包丢失而导致网络 MOS 减少的量。</span><span class="sxs-lookup"><span data-stu-id="7a655-161">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="7a655-162">对于可接受的质量，它应小于0.5。</span><span class="sxs-lookup"><span data-stu-id="7a655-162">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-163"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-163"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-164">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="7a655-164">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-165">呼叫期间的最大网络 MOS 降级。</span><span class="sxs-lookup"><span data-stu-id="7a655-165">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-166"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-166"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-167">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="7a655-167">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-168">由抖动引起的网络 MOS 性能下降。</span><span class="sxs-lookup"><span data-stu-id="7a655-168">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-169"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-169"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-170">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="7a655-170">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-171">因数据包丢失而导致的网络 MOS 降级。</span><span class="sxs-lookup"><span data-stu-id="7a655-171">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-172"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-172"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-173">int</span><span class="sxs-lookup"><span data-stu-id="7a655-173">int</span></span></p></td>
<td><p><span data-ttu-id="7a655-174">对外</span><span class="sxs-lookup"><span data-stu-id="7a655-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7a655-175">用于呼叫的音频编解码器，从 PayloadDescription 表中引用。</span><span class="sxs-lookup"><span data-stu-id="7a655-175">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-176"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-176"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-177">int</span><span class="sxs-lookup"><span data-stu-id="7a655-177">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-178">音频流的采样率。</span><span class="sxs-lookup"><span data-stu-id="7a655-178">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-179"><strong>工程</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-179"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-180">int</span><span class="sxs-lookup"><span data-stu-id="7a655-180">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-181">RTCP 统计信息中的来回行程时间。</span><span class="sxs-lookup"><span data-stu-id="7a655-181">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="7a655-182">为了获得可接受的质量，此数量应小于100毫秒。</span><span class="sxs-lookup"><span data-stu-id="7a655-182">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-183"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-183"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-184">int</span><span class="sxs-lookup"><span data-stu-id="7a655-184">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-185">音频流的最大来回行程时间。</span><span class="sxs-lookup"><span data-stu-id="7a655-185">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-186"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-186"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-187">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="7a655-187">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-188">呼叫的平均宽带网络 MOS。</span><span class="sxs-lookup"><span data-stu-id="7a655-188">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="7a655-189">此指标取决于所使用的数据包丢失、抖动和编解码器。</span><span class="sxs-lookup"><span data-stu-id="7a655-189">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="7a655-190">范围为 [1.0 至 5.0]。</span><span class="sxs-lookup"><span data-stu-id="7a655-190">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-191"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-191"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-192">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="7a655-192">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-193">呼叫的最小宽带网络 MOS。</span><span class="sxs-lookup"><span data-stu-id="7a655-193">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-194"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-194"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-195">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="7a655-195">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-196">平均预测的宽带侦听音频发送的 MOS 分数，包括语音级别、噪声级别和捕获设备特征。</span><span class="sxs-lookup"><span data-stu-id="7a655-196">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-197"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-197"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-198">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="7a655-198">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-199">呼叫的最小 SendListenMOS。</span><span class="sxs-lookup"><span data-stu-id="7a655-199">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-200"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-200"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-201">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="7a655-201">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-202">平均预测宽带侦听从网络接收的音频的 MOS 分数，包括语音级别、噪音级别、编解码器、网络条件和捕获设备特征。</span><span class="sxs-lookup"><span data-stu-id="7a655-202">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-203"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-203"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-204">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="7a655-204">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-205">呼叫的最小 RecvListenMOS。</span><span class="sxs-lookup"><span data-stu-id="7a655-205">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-206"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-206"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-207">位</span><span class="sxs-lookup"><span data-stu-id="7a655-207">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-208">指示是否已对呼叫使用音频 FEC 的标志。</span><span class="sxs-lookup"><span data-stu-id="7a655-208">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-209"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-209"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-210">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="7a655-210">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-211">通过音频康复对典型示例生成的隐藏样本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="7a655-211">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-212"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-212"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-213">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="7a655-213">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-214">由音频康复生成的一般示例中的延伸样本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="7a655-214">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-215"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-215"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-216">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="7a655-216">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-217">由音频康复生成的压缩样本的平均比率到典型示例。</span><span class="sxs-lookup"><span data-stu-id="7a655-217">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-218"><strong>进货</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-218"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-219">位</span><span class="sxs-lookup"><span data-stu-id="7a655-219">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-220">接收接收器端的数据流数据。</span><span class="sxs-lookup"><span data-stu-id="7a655-220">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-221"><strong>出站</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-221"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-222">位</span><span class="sxs-lookup"><span data-stu-id="7a655-222">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-223">接收发件人端上的数据流数据。</span><span class="sxs-lookup"><span data-stu-id="7a655-223">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-224"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-224"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-225">位</span><span class="sxs-lookup"><span data-stu-id="7a655-225">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7a655-226">1表示流方向从呼叫者到被叫方。</span><span class="sxs-lookup"><span data-stu-id="7a655-226">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="7a655-227">0 表示流方向是从被叫方到呼叫者。</span><span class="sxs-lookup"><span data-stu-id="7a655-227">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-228"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-228"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-229">float</span><span class="sxs-lookup"><span data-stu-id="7a655-229">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-230">抖动到达时间的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="7a655-230">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="7a655-231">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-231">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-232"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-232"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-233">float</span><span class="sxs-lookup"><span data-stu-id="7a655-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-234">由修复程序隐藏的数据包的最大比率。</span><span class="sxs-lookup"><span data-stu-id="7a655-234">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="7a655-235">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-235">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-236"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-236"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-237">float</span><span class="sxs-lookup"><span data-stu-id="7a655-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-238">修复程序隐藏的数据包比率的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="7a655-238">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="7a655-239">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-239">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-240"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-240"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-241">float</span><span class="sxs-lookup"><span data-stu-id="7a655-241">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-242">修复程序丢弃的数据包与接收的数据包总数的比率。</span><span class="sxs-lookup"><span data-stu-id="7a655-242">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="7a655-243">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-243">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-244"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-244"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-245">float</span><span class="sxs-lookup"><span data-stu-id="7a655-245">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-246">与接收的数据包总数相比使用的转发错误纠正数据包的比率。</span><span class="sxs-lookup"><span data-stu-id="7a655-246">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="7a655-247">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-247">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-248"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-248"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-249">float</span><span class="sxs-lookup"><span data-stu-id="7a655-249">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-250">由修复程序压缩的最大音频数据包数。</span><span class="sxs-lookup"><span data-stu-id="7a655-250">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="7a655-251">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-251">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-252"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-252"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-253">float</span><span class="sxs-lookup"><span data-stu-id="7a655-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-254">指示呼叫处于丢失拥塞状态的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="7a655-254">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="7a655-255">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-256"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-256"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-257">float</span><span class="sxs-lookup"><span data-stu-id="7a655-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-258">指示因网络数据包的延迟到达而导致拥塞的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="7a655-258">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="7a655-259">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-259">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-260"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-260"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-261">float</span><span class="sxs-lookup"><span data-stu-id="7a655-261">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-262">指示呼叫竞争网络资源的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="7a655-262">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="7a655-263">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-263">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-264"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-264"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-265">int</span><span class="sxs-lookup"><span data-stu-id="7a655-265">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-266">在呼叫过程中测量的最小带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="7a655-266">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="7a655-267">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-267">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-268"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-268"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-269">int</span><span class="sxs-lookup"><span data-stu-id="7a655-269">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-270">在呼叫过程中测量的最大带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="7a655-270">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="7a655-271">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-271">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-272"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-272"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-273">int</span><span class="sxs-lookup"><span data-stu-id="7a655-273">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-274">在呼叫过程中测量的带宽估计的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="7a655-274">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="7a655-275">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-275">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-276"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-276"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-277">int</span><span class="sxs-lookup"><span data-stu-id="7a655-277">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-278">呼叫期间衡量的平均带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="7a655-278">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="7a655-279">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-279">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-280"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-280"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-281">float</span><span class="sxs-lookup"><span data-stu-id="7a655-281">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-p105">单向延迟的总量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="7a655-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="7a655-284">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-285"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-285"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-286">float</span><span class="sxs-lookup"><span data-stu-id="7a655-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-p106">单向延迟的平均量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="7a655-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="7a655-289">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-289">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-290"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-290"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-291">float</span><span class="sxs-lookup"><span data-stu-id="7a655-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-p107">单向延迟的最大量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="7a655-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="7a655-294">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-294">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-295"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-295"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-296">int</span><span class="sxs-lookup"><span data-stu-id="7a655-296">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-p108">单向突发总发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="7a655-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7a655-300">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-301"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-301"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-302">float</span><span class="sxs-lookup"><span data-stu-id="7a655-302">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-p109">单向突发总密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="7a655-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7a655-306">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-306">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-307"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-307"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-308">float</span><span class="sxs-lookup"><span data-stu-id="7a655-308">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-p110">单向突发总持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="7a655-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7a655-312">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-312">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-313"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-313"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-314">int</span><span class="sxs-lookup"><span data-stu-id="7a655-314">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-p111">单向间隙总发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="7a655-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7a655-318">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-319"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-319"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-320">float</span><span class="sxs-lookup"><span data-stu-id="7a655-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-p112">单向间隙总密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="7a655-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7a655-324">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-324">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-325"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-325"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-326">float</span><span class="sxs-lookup"><span data-stu-id="7a655-326">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-p113">单向间隙总持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="7a655-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7a655-330">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-330">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-331"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-331"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-332">float</span><span class="sxs-lookup"><span data-stu-id="7a655-332">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-333">被解码为立体声的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="7a655-333">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="7a655-334">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-335"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-335"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-336">float</span><span class="sxs-lookup"><span data-stu-id="7a655-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-337">通过音响回声消除器呈现为立体声的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="7a655-337">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="7a655-338">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-338">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-339"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-339"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-340">float</span><span class="sxs-lookup"><span data-stu-id="7a655-340">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-341">应用转发错误纠正率后的数据包丢失率。</span><span class="sxs-lookup"><span data-stu-id="7a655-341">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="7a655-342">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-342">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7a655-343"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-343"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-344">float</span><span class="sxs-lookup"><span data-stu-id="7a655-344">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-345">编码为立体声的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="7a655-345">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="7a655-346">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-346">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7a655-347"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7a655-347"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7a655-348">float</span><span class="sxs-lookup"><span data-stu-id="7a655-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7a655-349">通过音响回声消除器以立体声形式捕获的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="7a655-349">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="7a655-350">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7a655-350">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

