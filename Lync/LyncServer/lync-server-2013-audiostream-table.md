---
title: Lync Server 2013：AudioStream 表
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
ms.openlocfilehash: 97a8015bce118991b21b541faf588dd4d76ac784
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738342"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="f0635-102">Lync Server 2013 中的 AudioStream 表</span><span class="sxs-lookup"><span data-stu-id="f0635-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f0635-103">_**主题上次修改时间：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f0635-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f0635-104">每条记录表示一个音频流。</span><span class="sxs-lookup"><span data-stu-id="f0635-104">Each record represents one audio stream.</span></span> <span data-ttu-id="f0635-105">一个音频媒体行通常包含两个音频流。</span><span class="sxs-lookup"><span data-stu-id="f0635-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f0635-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f0635-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f0635-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f0635-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f0635-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-111">datetime</span><span class="sxs-lookup"><span data-stu-id="f0635-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="f0635-112">Primary</span><span class="sxs-lookup"><span data-stu-id="f0635-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f0635-113">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="f0635-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-115">int</span><span class="sxs-lookup"><span data-stu-id="f0635-115">int</span></span></p></td>
<td><p><span data-ttu-id="f0635-116">Primary</span><span class="sxs-lookup"><span data-stu-id="f0635-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="f0635-117">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="f0635-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="f0635-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f0635-120">Primary</span><span class="sxs-lookup"><span data-stu-id="f0635-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="f0635-121">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="f0635-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-123">int</span><span class="sxs-lookup"><span data-stu-id="f0635-123">int</span></span></p></td>
<td><p><span data-ttu-id="f0635-124">Primary</span><span class="sxs-lookup"><span data-stu-id="f0635-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="f0635-125">媒体行内的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="f0635-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-127">int</span><span class="sxs-lookup"><span data-stu-id="f0635-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-128">实时控制协议（RTCP）统计信息的平均网络抖动。</span><span class="sxs-lookup"><span data-stu-id="f0635-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-130">int</span><span class="sxs-lookup"><span data-stu-id="f0635-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-131">通话期间网络抖动的最大值。</span><span class="sxs-lookup"><span data-stu-id="f0635-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-133">十进制（5，4）</span><span class="sxs-lookup"><span data-stu-id="f0635-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-134">通话期间平均数据包丢失速率。</span><span class="sxs-lookup"><span data-stu-id="f0635-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-136">十进制（5，4）</span><span class="sxs-lookup"><span data-stu-id="f0635-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-137">通话过程中观察到的最大数据包丢失。</span><span class="sxs-lookup"><span data-stu-id="f0635-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-138"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-139">十进制（9，4）</span><span class="sxs-lookup"><span data-stu-id="f0635-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-140">通话期间出现猝发损失期间的数据包丢失的平均密度。</span><span class="sxs-lookup"><span data-stu-id="f0635-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-142">int</span><span class="sxs-lookup"><span data-stu-id="f0635-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-143">通话期间出现猝发损失期间的数据包丢失的平均持续时间。</span><span class="sxs-lookup"><span data-stu-id="f0635-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-145">十进制（9，4）</span><span class="sxs-lookup"><span data-stu-id="f0635-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-146">出现猝发数据包丢失之间的平均数据包损失的平均密度。</span><span class="sxs-lookup"><span data-stu-id="f0635-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-148">int</span><span class="sxs-lookup"><span data-stu-id="f0635-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-149">爆发数据包损失之间的平均持续时间。</span><span class="sxs-lookup"><span data-stu-id="f0635-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-151">整形</span><span class="sxs-lookup"><span data-stu-id="f0635-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-152">音频流的数据包计数。</span><span class="sxs-lookup"><span data-stu-id="f0635-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-153"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-154">整形</span><span class="sxs-lookup"><span data-stu-id="f0635-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-155">音频流的带宽估计。</span><span class="sxs-lookup"><span data-stu-id="f0635-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-157">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="f0635-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-158">整个通话的网络 MOS 降级。</span><span class="sxs-lookup"><span data-stu-id="f0635-158">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="f0635-159">范围为0.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="f0635-159">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="f0635-160">此指标显示由于抖动和数据包丢失，网络 MOS 的减少量。</span><span class="sxs-lookup"><span data-stu-id="f0635-160">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="f0635-161">对于可接受的质量，它应小于0.5。</span><span class="sxs-lookup"><span data-stu-id="f0635-161">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-163">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="f0635-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-164">通话期间最大网络 MOS 性能下降。</span><span class="sxs-lookup"><span data-stu-id="f0635-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-166">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="f0635-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-167">由抖动导致的网络 MOS 性能下降。</span><span class="sxs-lookup"><span data-stu-id="f0635-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-169">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="f0635-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-170">由于数据包丢失导致网络 MOS 性能下降。</span><span class="sxs-lookup"><span data-stu-id="f0635-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-172">int</span><span class="sxs-lookup"><span data-stu-id="f0635-172">int</span></span></p></td>
<td><p><span data-ttu-id="f0635-173">外表</span><span class="sxs-lookup"><span data-stu-id="f0635-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f0635-174">用于呼叫的音频编解码器，从 PayloadDescription 表中引用。</span><span class="sxs-lookup"><span data-stu-id="f0635-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-176">int</span><span class="sxs-lookup"><span data-stu-id="f0635-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-177">音频流的采样率。</span><span class="sxs-lookup"><span data-stu-id="f0635-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-178"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-179">int</span><span class="sxs-lookup"><span data-stu-id="f0635-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-180">从 RTCP 统计数据往返的时间。</span><span class="sxs-lookup"><span data-stu-id="f0635-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="f0635-181">为获得可接受的质量，这应该小于100ms。</span><span class="sxs-lookup"><span data-stu-id="f0635-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-183">int</span><span class="sxs-lookup"><span data-stu-id="f0635-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-184">音频流的最大往返行程时间。</span><span class="sxs-lookup"><span data-stu-id="f0635-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-186">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="f0635-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-187">通话的平均宽带网络 MOS。</span><span class="sxs-lookup"><span data-stu-id="f0635-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="f0635-188">此指标取决于所使用的数据包丢失、抖动和编解码器。</span><span class="sxs-lookup"><span data-stu-id="f0635-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="f0635-189">范围为 [1.0 到 5.0]。</span><span class="sxs-lookup"><span data-stu-id="f0635-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-191">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="f0635-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-192">通话的最低宽带网络 MOS。</span><span class="sxs-lookup"><span data-stu-id="f0635-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-194">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="f0635-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-195">平均预测宽带的 MOS 分数，包括语音级别、噪声级别和捕获设备特征。</span><span class="sxs-lookup"><span data-stu-id="f0635-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-197">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="f0635-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-198">通话的最低 SendListenMOS。</span><span class="sxs-lookup"><span data-stu-id="f0635-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-200">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="f0635-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-201">平均预测宽带从网络接收的音频的 MOS 分数，包括语音级别、噪音级别、编解码器、网络条件和捕获设备特征。</span><span class="sxs-lookup"><span data-stu-id="f0635-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-203">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="f0635-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-204">通话的最低 RecvListenMOS。</span><span class="sxs-lookup"><span data-stu-id="f0635-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-206">bit</span><span class="sxs-lookup"><span data-stu-id="f0635-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-207">指示是否已将音频 FEC 用于呼叫的标志。</span><span class="sxs-lookup"><span data-stu-id="f0635-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-209">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="f0635-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-210">通过音频康复为典型示例生成的隐藏样本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="f0635-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-212">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="f0635-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-213">通过音频康复为典型示例生成的拉伸样本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="f0635-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-215">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="f0635-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-216">从音频修复到典型示例生成的压缩样本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="f0635-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-217"><strong>封</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-218">bit</span><span class="sxs-lookup"><span data-stu-id="f0635-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-219">接收接收方的数据流数据。</span><span class="sxs-lookup"><span data-stu-id="f0635-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-220"><strong>出站</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-221">bit</span><span class="sxs-lookup"><span data-stu-id="f0635-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-222">接收发件人端的数据流数据。</span><span class="sxs-lookup"><span data-stu-id="f0635-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-224">bit</span><span class="sxs-lookup"><span data-stu-id="f0635-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f0635-225">1表示流方向从调用方到被调用方。</span><span class="sxs-lookup"><span data-stu-id="f0635-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="f0635-226">0表示流方向来自被调用方的调用方。</span><span class="sxs-lookup"><span data-stu-id="f0635-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-228">float</span><span class="sxs-lookup"><span data-stu-id="f0635-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-229">抖动到达时间的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="f0635-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="f0635-230">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-232">float</span><span class="sxs-lookup"><span data-stu-id="f0635-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-233">由 healer 隐藏的数据包的最大比率。</span><span class="sxs-lookup"><span data-stu-id="f0635-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="f0635-234">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-236">float</span><span class="sxs-lookup"><span data-stu-id="f0635-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-237">由 healer 隐藏的数据包比率的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="f0635-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="f0635-238">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-240">float</span><span class="sxs-lookup"><span data-stu-id="f0635-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-241">Healer 丢弃的数据包与接收的总数据包数之比。</span><span class="sxs-lookup"><span data-stu-id="f0635-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="f0635-242">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-244">float</span><span class="sxs-lookup"><span data-stu-id="f0635-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-245">与接收的总数据包数相比已使用的转发纠错数据包的比率。</span><span class="sxs-lookup"><span data-stu-id="f0635-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="f0635-246">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-248">float</span><span class="sxs-lookup"><span data-stu-id="f0635-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-249">由 healer 压缩的音频数据包的最大数量。</span><span class="sxs-lookup"><span data-stu-id="f0635-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="f0635-250">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-252">float</span><span class="sxs-lookup"><span data-stu-id="f0635-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-253">指示通话处于损失拥塞状态的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="f0635-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="f0635-254">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-256">float</span><span class="sxs-lookup"><span data-stu-id="f0635-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-257">指示由于网络数据包的延迟到达而导致的阻塞的调用百分比。</span><span class="sxs-lookup"><span data-stu-id="f0635-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="f0635-258">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-260">float</span><span class="sxs-lookup"><span data-stu-id="f0635-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-261">表示呼叫竞争网络资源的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="f0635-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="f0635-262">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-264">int</span><span class="sxs-lookup"><span data-stu-id="f0635-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-265">在通话期间测量的最小带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="f0635-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f0635-266">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-268">int</span><span class="sxs-lookup"><span data-stu-id="f0635-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-269">在通话期间测量的最大带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="f0635-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f0635-270">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-272">int</span><span class="sxs-lookup"><span data-stu-id="f0635-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-273">在通话过程中测量的带宽估计的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="f0635-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f0635-274">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-276">int</span><span class="sxs-lookup"><span data-stu-id="f0635-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-277">通话期间测量的平均估计带宽量。</span><span class="sxs-lookup"><span data-stu-id="f0635-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f0635-278">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-280">float</span><span class="sxs-lookup"><span data-stu-id="f0635-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-281">单向延迟的总金额。</span><span class="sxs-lookup"><span data-stu-id="f0635-281">Total amount of one-way latency.</span></span> <span data-ttu-id="f0635-282">相对单向延迟测量客户端与服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="f0635-282">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f0635-283">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-285">float</span><span class="sxs-lookup"><span data-stu-id="f0635-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-286">单向延迟的平均量。</span><span class="sxs-lookup"><span data-stu-id="f0635-286">Average amount of one-way latency.</span></span> <span data-ttu-id="f0635-287">相对单向延迟测量客户端与服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="f0635-287">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f0635-288">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-290">float</span><span class="sxs-lookup"><span data-stu-id="f0635-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-291">单向延迟的最大值。</span><span class="sxs-lookup"><span data-stu-id="f0635-291">Maximum amount of one-way latency.</span></span> <span data-ttu-id="f0635-292">相对单向延迟测量客户端与服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="f0635-292">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f0635-293">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-295">int</span><span class="sxs-lookup"><span data-stu-id="f0635-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-296">总单向爆发次数。</span><span class="sxs-lookup"><span data-stu-id="f0635-296">Total one-way burst occurrences.</span></span> <span data-ttu-id="f0635-297">"Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，数据流处于不可预知的突发流量。</span><span class="sxs-lookup"><span data-stu-id="f0635-297">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="f0635-298">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="f0635-298">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f0635-299">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-301">float</span><span class="sxs-lookup"><span data-stu-id="f0635-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-302">总单向脉冲密度。</span><span class="sxs-lookup"><span data-stu-id="f0635-302">Total one-way burst density.</span></span> <span data-ttu-id="f0635-303">"Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，数据流处于不可预知的突发流量。</span><span class="sxs-lookup"><span data-stu-id="f0635-303">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="f0635-304">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="f0635-304">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f0635-305">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-307">float</span><span class="sxs-lookup"><span data-stu-id="f0635-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-308">总的单向脉冲持续时间。</span><span class="sxs-lookup"><span data-stu-id="f0635-308">Total one-way burst duration.</span></span> <span data-ttu-id="f0635-309">"Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，数据流处于不可预知的突发流量。</span><span class="sxs-lookup"><span data-stu-id="f0635-309">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="f0635-310">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="f0635-310">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f0635-311">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-313">int</span><span class="sxs-lookup"><span data-stu-id="f0635-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-314">总的单向间隔发生次数。</span><span class="sxs-lookup"><span data-stu-id="f0635-314">Total one-way gap occurrences.</span></span> <span data-ttu-id="f0635-315">"Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，其数据流可预料的猝发。间隙表示这些猝发之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="f0635-315">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="f0635-316">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="f0635-316">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f0635-317">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-319">float</span><span class="sxs-lookup"><span data-stu-id="f0635-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-320">总单向间距密度。</span><span class="sxs-lookup"><span data-stu-id="f0635-320">Total one-way gap density.</span></span> <span data-ttu-id="f0635-321">"Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，其数据流可预料的猝发。间隙表示这些猝发之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="f0635-321">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="f0635-322">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="f0635-322">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f0635-323">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-325">float</span><span class="sxs-lookup"><span data-stu-id="f0635-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-326">总的单间隔持续时间。</span><span class="sxs-lookup"><span data-stu-id="f0635-326">Total one-way gap duration.</span></span> <span data-ttu-id="f0635-327">"Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，其数据流可预料的猝发。间隙表示这些猝发之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="f0635-327">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="f0635-328">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="f0635-328">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f0635-329">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-331">float</span><span class="sxs-lookup"><span data-stu-id="f0635-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-332">解码为立体声的通话百分比。</span><span class="sxs-lookup"><span data-stu-id="f0635-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="f0635-333">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-335">float</span><span class="sxs-lookup"><span data-stu-id="f0635-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-336">通过音响回声抵消器呈现为立体声的通话百分比。</span><span class="sxs-lookup"><span data-stu-id="f0635-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="f0635-337">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-339">float</span><span class="sxs-lookup"><span data-stu-id="f0635-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-340">已应用转发纠错后的数据包丢失率。</span><span class="sxs-lookup"><span data-stu-id="f0635-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="f0635-341">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f0635-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-343">float</span><span class="sxs-lookup"><span data-stu-id="f0635-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-344">编码为立体声的通话百分比。</span><span class="sxs-lookup"><span data-stu-id="f0635-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="f0635-345">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f0635-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f0635-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f0635-347">float</span><span class="sxs-lookup"><span data-stu-id="f0635-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f0635-348">通过音响回声抵消器以立体声形式捕获的通话百分比。</span><span class="sxs-lookup"><span data-stu-id="f0635-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="f0635-349">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f0635-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

