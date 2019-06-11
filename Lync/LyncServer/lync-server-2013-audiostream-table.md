---
title: Lync Server 2013：AudioStream 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AudioStream table
ms:assetid: 49ccbbc3-2f73-45fc-80a6-e612535cbc10
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425961(v=OCS.15)
ms:contentKeyID: 48184077
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f9412001652f4f323bdd3fb5722d0d7222535fd2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837902"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="73a18-102">Lync Server 2013 中的 AudioStream 表</span><span class="sxs-lookup"><span data-stu-id="73a18-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73a18-103">_**主题上次修改时间:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="73a18-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="73a18-104">每条记录表示一个音频流。</span><span class="sxs-lookup"><span data-stu-id="73a18-104">Each record represents one audio stream.</span></span> <span data-ttu-id="73a18-105">一个音频媒体行通常包含两个音频流。</span><span class="sxs-lookup"><span data-stu-id="73a18-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="73a18-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="73a18-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="73a18-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="73a18-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73a18-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-111">datetime</span><span class="sxs-lookup"><span data-stu-id="73a18-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="73a18-112">Primary</span><span class="sxs-lookup"><span data-stu-id="73a18-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="73a18-113">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="73a18-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-115">int</span><span class="sxs-lookup"><span data-stu-id="73a18-115">int</span></span></p></td>
<td><p><span data-ttu-id="73a18-116">Primary</span><span class="sxs-lookup"><span data-stu-id="73a18-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="73a18-117">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="73a18-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="73a18-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="73a18-120">Primary</span><span class="sxs-lookup"><span data-stu-id="73a18-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="73a18-121">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="73a18-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-123">int</span><span class="sxs-lookup"><span data-stu-id="73a18-123">int</span></span></p></td>
<td><p><span data-ttu-id="73a18-124">Primary</span><span class="sxs-lookup"><span data-stu-id="73a18-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="73a18-125">媒体行内的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="73a18-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-127">int</span><span class="sxs-lookup"><span data-stu-id="73a18-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-128">实时控制协议 (RTCP) 统计信息的平均网络抖动。</span><span class="sxs-lookup"><span data-stu-id="73a18-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-130">int</span><span class="sxs-lookup"><span data-stu-id="73a18-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-131">通话期间网络抖动的最大值。</span><span class="sxs-lookup"><span data-stu-id="73a18-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-133">十进制 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="73a18-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-134">通话期间平均数据包丢失速率。</span><span class="sxs-lookup"><span data-stu-id="73a18-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-136">十进制 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="73a18-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-137">通话过程中观察到的最大数据包丢失。</span><span class="sxs-lookup"><span data-stu-id="73a18-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-138"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-139">十进制 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="73a18-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-140">通话期间出现猝发损失期间的数据包丢失的平均密度。</span><span class="sxs-lookup"><span data-stu-id="73a18-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-142">int</span><span class="sxs-lookup"><span data-stu-id="73a18-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-143">通话期间出现猝发损失期间的数据包丢失的平均持续时间。</span><span class="sxs-lookup"><span data-stu-id="73a18-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-145">十进制 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="73a18-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-146">出现猝发数据包丢失之间的平均数据包损失的平均密度。</span><span class="sxs-lookup"><span data-stu-id="73a18-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-148">int</span><span class="sxs-lookup"><span data-stu-id="73a18-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-149">爆发数据包损失之间的平均持续时间。</span><span class="sxs-lookup"><span data-stu-id="73a18-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-151">整形</span><span class="sxs-lookup"><span data-stu-id="73a18-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-152">音频流的数据包计数。</span><span class="sxs-lookup"><span data-stu-id="73a18-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-153"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-154">整形</span><span class="sxs-lookup"><span data-stu-id="73a18-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-155">音频流的带宽估计。</span><span class="sxs-lookup"><span data-stu-id="73a18-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-157">十进制 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="73a18-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-158">整个通话的网络 MOS 降级。</span><span class="sxs-lookup"><span data-stu-id="73a18-158">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="73a18-159">范围为0.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="73a18-159">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="73a18-160">此指标显示由于抖动和数据包丢失, 网络 MOS 的减少量。</span><span class="sxs-lookup"><span data-stu-id="73a18-160">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="73a18-161">对于可接受的质量, 它应小于0.5。</span><span class="sxs-lookup"><span data-stu-id="73a18-161">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-163">十进制 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="73a18-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-164">通话期间最大网络 MOS 性能下降。</span><span class="sxs-lookup"><span data-stu-id="73a18-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-166">十进制 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="73a18-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-167">由抖动导致的网络 MOS 性能下降。</span><span class="sxs-lookup"><span data-stu-id="73a18-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-169">十进制 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="73a18-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-170">由于数据包丢失导致网络 MOS 性能下降。</span><span class="sxs-lookup"><span data-stu-id="73a18-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-172">int</span><span class="sxs-lookup"><span data-stu-id="73a18-172">int</span></span></p></td>
<td><p><span data-ttu-id="73a18-173">外表</span><span class="sxs-lookup"><span data-stu-id="73a18-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="73a18-174">用于呼叫的音频编解码器, 从 PayloadDescription 表中引用。</span><span class="sxs-lookup"><span data-stu-id="73a18-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-176">int</span><span class="sxs-lookup"><span data-stu-id="73a18-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-177">音频流的采样率。</span><span class="sxs-lookup"><span data-stu-id="73a18-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-178"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-179">int</span><span class="sxs-lookup"><span data-stu-id="73a18-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-180">从 RTCP 统计数据往返的时间。</span><span class="sxs-lookup"><span data-stu-id="73a18-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="73a18-181">为获得可接受的质量, 这应该小于100ms。</span><span class="sxs-lookup"><span data-stu-id="73a18-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-183">int</span><span class="sxs-lookup"><span data-stu-id="73a18-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-184">音频流的最大往返行程时间。</span><span class="sxs-lookup"><span data-stu-id="73a18-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-186">十进制 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="73a18-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-187">通话的平均宽带网络 MOS。</span><span class="sxs-lookup"><span data-stu-id="73a18-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="73a18-188">此指标取决于所使用的数据包丢失、抖动和编解码器。</span><span class="sxs-lookup"><span data-stu-id="73a18-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="73a18-189">范围为 [1.0 到 5.0]。</span><span class="sxs-lookup"><span data-stu-id="73a18-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-191">十进制 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="73a18-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-192">通话的最低宽带网络 MOS。</span><span class="sxs-lookup"><span data-stu-id="73a18-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-194">十进制 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="73a18-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-195">平均预测宽带的 MOS 分数, 包括语音级别、噪声级别和捕获设备特征。</span><span class="sxs-lookup"><span data-stu-id="73a18-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-197">十进制 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="73a18-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-198">通话的最低 SendListenMOS。</span><span class="sxs-lookup"><span data-stu-id="73a18-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-200">十进制 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="73a18-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-201">平均预测宽带从网络接收的音频的 MOS 分数, 包括语音级别、噪音级别、编解码器、网络条件和捕获设备特征。</span><span class="sxs-lookup"><span data-stu-id="73a18-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-203">十进制 (3, 2)</span><span class="sxs-lookup"><span data-stu-id="73a18-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-204">通话的最低 RecvListenMOS。</span><span class="sxs-lookup"><span data-stu-id="73a18-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-206">bit</span><span class="sxs-lookup"><span data-stu-id="73a18-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-207">指示是否已将音频 FEC 用于呼叫的标志。</span><span class="sxs-lookup"><span data-stu-id="73a18-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-209">十进制 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="73a18-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-210">通过音频康复为典型示例生成的隐藏样本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="73a18-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-212">十进制 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="73a18-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-213">通过音频康复为典型示例生成的拉伸样本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="73a18-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-215">十进制 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="73a18-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-216">从音频修复到典型示例生成的压缩样本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="73a18-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-217"><strong>封</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-218">bit</span><span class="sxs-lookup"><span data-stu-id="73a18-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-219">接收接收方的数据流数据。</span><span class="sxs-lookup"><span data-stu-id="73a18-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-220"><strong>出站</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-221">bit</span><span class="sxs-lookup"><span data-stu-id="73a18-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-222">接收发件人端的数据流数据。</span><span class="sxs-lookup"><span data-stu-id="73a18-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-224">bit</span><span class="sxs-lookup"><span data-stu-id="73a18-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="73a18-225">1表示流方向从调用方到被调用方。</span><span class="sxs-lookup"><span data-stu-id="73a18-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="73a18-226">0表示流方向来自被调用方的调用方。</span><span class="sxs-lookup"><span data-stu-id="73a18-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-228">float</span><span class="sxs-lookup"><span data-stu-id="73a18-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-229">抖动到达时间的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="73a18-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="73a18-230">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-232">float</span><span class="sxs-lookup"><span data-stu-id="73a18-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-233">由 healer 隐藏的数据包的最大比率。</span><span class="sxs-lookup"><span data-stu-id="73a18-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="73a18-234">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-236">float</span><span class="sxs-lookup"><span data-stu-id="73a18-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-237">由 healer 隐藏的数据包比率的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="73a18-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="73a18-238">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-240">float</span><span class="sxs-lookup"><span data-stu-id="73a18-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-241">Healer 丢弃的数据包与接收的总数据包数之比。</span><span class="sxs-lookup"><span data-stu-id="73a18-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="73a18-242">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-244">float</span><span class="sxs-lookup"><span data-stu-id="73a18-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-245">与接收的总数据包数相比已使用的转发纠错数据包的比率。</span><span class="sxs-lookup"><span data-stu-id="73a18-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="73a18-246">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-248">float</span><span class="sxs-lookup"><span data-stu-id="73a18-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-249">由 healer 压缩的音频数据包的最大数量。</span><span class="sxs-lookup"><span data-stu-id="73a18-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="73a18-250">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-252">float</span><span class="sxs-lookup"><span data-stu-id="73a18-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-253">指示通话处于损失拥塞状态的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="73a18-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="73a18-254">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-256">float</span><span class="sxs-lookup"><span data-stu-id="73a18-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-257">指示由于网络数据包的延迟到达而导致的阻塞的调用百分比。</span><span class="sxs-lookup"><span data-stu-id="73a18-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="73a18-258">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-260">float</span><span class="sxs-lookup"><span data-stu-id="73a18-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-261">表示呼叫竞争网络资源的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="73a18-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="73a18-262">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-264">int</span><span class="sxs-lookup"><span data-stu-id="73a18-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-265">在通话期间测量的最小带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="73a18-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="73a18-266">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-268">int</span><span class="sxs-lookup"><span data-stu-id="73a18-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-269">在通话期间测量的最大带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="73a18-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="73a18-270">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-272">int</span><span class="sxs-lookup"><span data-stu-id="73a18-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-273">在通话过程中测量的带宽估计的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="73a18-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="73a18-274">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-276">int</span><span class="sxs-lookup"><span data-stu-id="73a18-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-277">通话期间测量的平均估计带宽量。</span><span class="sxs-lookup"><span data-stu-id="73a18-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="73a18-278">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-280">float</span><span class="sxs-lookup"><span data-stu-id="73a18-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-281">单向延迟的总金额。</span><span class="sxs-lookup"><span data-stu-id="73a18-281">Total amount of one-way latency.</span></span> <span data-ttu-id="73a18-282">相对单向延迟测量客户端与服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="73a18-282">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="73a18-283">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-285">float</span><span class="sxs-lookup"><span data-stu-id="73a18-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-286">单向延迟的平均量。</span><span class="sxs-lookup"><span data-stu-id="73a18-286">Average amount of one-way latency.</span></span> <span data-ttu-id="73a18-287">相对单向延迟测量客户端与服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="73a18-287">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="73a18-288">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-290">float</span><span class="sxs-lookup"><span data-stu-id="73a18-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-291">单向延迟的最大值。</span><span class="sxs-lookup"><span data-stu-id="73a18-291">Maximum amount of one-way latency.</span></span> <span data-ttu-id="73a18-292">相对单向延迟测量客户端与服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="73a18-292">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="73a18-293">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-295">int</span><span class="sxs-lookup"><span data-stu-id="73a18-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-296">总单向爆发次数。</span><span class="sxs-lookup"><span data-stu-id="73a18-296">Total one-way burst occurrences.</span></span> <span data-ttu-id="73a18-297">"Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 数据流处于不可预知的突发流量。</span><span class="sxs-lookup"><span data-stu-id="73a18-297">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="73a18-298">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="73a18-298">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="73a18-299">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-301">float</span><span class="sxs-lookup"><span data-stu-id="73a18-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-302">总单向脉冲密度。</span><span class="sxs-lookup"><span data-stu-id="73a18-302">Total one-way burst density.</span></span> <span data-ttu-id="73a18-303">"Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 数据流处于不可预知的突发流量。</span><span class="sxs-lookup"><span data-stu-id="73a18-303">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="73a18-304">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="73a18-304">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="73a18-305">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-307">float</span><span class="sxs-lookup"><span data-stu-id="73a18-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-308">总的单向脉冲持续时间。</span><span class="sxs-lookup"><span data-stu-id="73a18-308">Total one-way burst duration.</span></span> <span data-ttu-id="73a18-309">"Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 数据流处于不可预知的突发流量。</span><span class="sxs-lookup"><span data-stu-id="73a18-309">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="73a18-310">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="73a18-310">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="73a18-311">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-313">int</span><span class="sxs-lookup"><span data-stu-id="73a18-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-314">总的单向间隔发生次数。</span><span class="sxs-lookup"><span data-stu-id="73a18-314">Total one-way gap occurrences.</span></span> <span data-ttu-id="73a18-315">"Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 其数据流可预料的猝发。间隙表示这些猝发之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="73a18-315">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="73a18-316">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="73a18-316">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="73a18-317">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-319">float</span><span class="sxs-lookup"><span data-stu-id="73a18-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-320">总单向间距密度。</span><span class="sxs-lookup"><span data-stu-id="73a18-320">Total one-way gap density.</span></span> <span data-ttu-id="73a18-321">"Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 其数据流可预料的猝发。间隙表示这些猝发之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="73a18-321">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="73a18-322">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="73a18-322">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="73a18-323">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-325">float</span><span class="sxs-lookup"><span data-stu-id="73a18-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-326">总的单间隔持续时间。</span><span class="sxs-lookup"><span data-stu-id="73a18-326">Total one-way gap duration.</span></span> <span data-ttu-id="73a18-327">"Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 其数据流可预料的猝发。间隙表示这些猝发之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="73a18-327">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="73a18-328">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="73a18-328">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="73a18-329">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-331">float</span><span class="sxs-lookup"><span data-stu-id="73a18-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-332">解码为立体声的通话百分比。</span><span class="sxs-lookup"><span data-stu-id="73a18-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="73a18-333">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-335">float</span><span class="sxs-lookup"><span data-stu-id="73a18-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-336">通过音响回声抵消器呈现为立体声的通话百分比。</span><span class="sxs-lookup"><span data-stu-id="73a18-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="73a18-337">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-339">float</span><span class="sxs-lookup"><span data-stu-id="73a18-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-340">已应用转发纠错后的数据包丢失率。</span><span class="sxs-lookup"><span data-stu-id="73a18-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="73a18-341">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73a18-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-343">float</span><span class="sxs-lookup"><span data-stu-id="73a18-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-344">编码为立体声的通话百分比。</span><span class="sxs-lookup"><span data-stu-id="73a18-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="73a18-345">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73a18-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="73a18-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="73a18-347">float</span><span class="sxs-lookup"><span data-stu-id="73a18-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="73a18-348">通过音响回声抵消器以立体声形式捕获的通话百分比。</span><span class="sxs-lookup"><span data-stu-id="73a18-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="73a18-349">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="73a18-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

