---
title: Lync Server 2013： AudioStream 表
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
ms.openlocfilehash: e2da0884915f44246e316f80cb9fd35fb7aecaad
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195765"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiostream-table-in-lync-server-2013"></a><span data-ttu-id="7eb89-102">Lync Server 2013 中的 AudioStream 表</span><span class="sxs-lookup"><span data-stu-id="7eb89-102">AudioStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7eb89-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="7eb89-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="7eb89-104">每个记录表示一个音频流。</span><span class="sxs-lookup"><span data-stu-id="7eb89-104">Each record represents one audio stream.</span></span> <span data-ttu-id="7eb89-105">一个音频媒体行通常包含两个音频流。</span><span class="sxs-lookup"><span data-stu-id="7eb89-105">One audio media line usually contains two audio streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="7eb89-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="7eb89-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="7eb89-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="7eb89-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-111">datetime</span><span class="sxs-lookup"><span data-stu-id="7eb89-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="7eb89-112">主</span><span class="sxs-lookup"><span data-stu-id="7eb89-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="7eb89-113"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="7eb89-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-115">int</span><span class="sxs-lookup"><span data-stu-id="7eb89-115">int</span></span></p></td>
<td><p><span data-ttu-id="7eb89-116">主</span><span class="sxs-lookup"><span data-stu-id="7eb89-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="7eb89-117"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="7eb89-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="7eb89-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="7eb89-120">主</span><span class="sxs-lookup"><span data-stu-id="7eb89-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="7eb89-121"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="7eb89-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-123">int</span><span class="sxs-lookup"><span data-stu-id="7eb89-123">int</span></span></p></td>
<td><p><span data-ttu-id="7eb89-124">主</span><span class="sxs-lookup"><span data-stu-id="7eb89-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="7eb89-125">媒体行中的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="7eb89-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-126"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-126"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-127">int</span><span class="sxs-lookup"><span data-stu-id="7eb89-127">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-128">实时控制协议 (RTCP) 统计信息中的平均网络抖动。</span><span class="sxs-lookup"><span data-stu-id="7eb89-128">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-129"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-129"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-130">int</span><span class="sxs-lookup"><span data-stu-id="7eb89-130">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-131">呼叫期间的最大网络抖动。</span><span class="sxs-lookup"><span data-stu-id="7eb89-131">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-132"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-132"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-133">decimal （5，4）</span><span class="sxs-lookup"><span data-stu-id="7eb89-133">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-134">呼叫期间的平均数据包丢失率。</span><span class="sxs-lookup"><span data-stu-id="7eb89-134">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-135"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-135"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-136">decimal （5，4）</span><span class="sxs-lookup"><span data-stu-id="7eb89-136">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-137">呼叫期间观测到的数据包丢失最大值。</span><span class="sxs-lookup"><span data-stu-id="7eb89-137">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-138"><strong>BurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-138"><strong>BurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-139">小数（9，4）</span><span class="sxs-lookup"><span data-stu-id="7eb89-139">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-140">呼叫期间出现猝发损失期间的数据包丢失的平均密度。</span><span class="sxs-lookup"><span data-stu-id="7eb89-140">Average density of packet Loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-141"><strong>BurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-141"><strong>BurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-142">int</span><span class="sxs-lookup"><span data-stu-id="7eb89-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-143">呼叫期间出现猝发损失期间的数据包丢失的平均持续时间。</span><span class="sxs-lookup"><span data-stu-id="7eb89-143">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-144"><strong>BurstGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-144"><strong>BurstGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-145">小数（9，4）</span><span class="sxs-lookup"><span data-stu-id="7eb89-145">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-146">在出现猝发数据包丢失之间间隔期间的数据包丢失的平均密度。</span><span class="sxs-lookup"><span data-stu-id="7eb89-146">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-147"><strong>BurstGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-147"><strong>BurstGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-148">int</span><span class="sxs-lookup"><span data-stu-id="7eb89-148">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-149">猝发数据包丢失间隔的平均持续时间。</span><span class="sxs-lookup"><span data-stu-id="7eb89-149">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-151">Int</span><span class="sxs-lookup"><span data-stu-id="7eb89-151">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-152">音频流的数据包计数。</span><span class="sxs-lookup"><span data-stu-id="7eb89-152">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-153"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-154">Int</span><span class="sxs-lookup"><span data-stu-id="7eb89-154">Int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-155">音频流的带宽预估。</span><span class="sxs-lookup"><span data-stu-id="7eb89-155">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-156"><strong>DegradationAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-156"><strong>DegradationAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-157">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="7eb89-157">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-158">整个呼叫的网络 MOS 降级。</span><span class="sxs-lookup"><span data-stu-id="7eb89-158">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="7eb89-159">范围是0.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="7eb89-159">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="7eb89-160">此指标显示由于抖动和数据包丢失而导致网络 MOS 减少的量。</span><span class="sxs-lookup"><span data-stu-id="7eb89-160">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="7eb89-161">对于可接受的质量，它应小于0.5。</span><span class="sxs-lookup"><span data-stu-id="7eb89-161">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-162"><strong>DegradationMax</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-162"><strong>DegradationMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-163">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="7eb89-163">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-164">呼叫期间的最大网络 MOS 降级。</span><span class="sxs-lookup"><span data-stu-id="7eb89-164">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-165"><strong>DegradationJitterAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-165"><strong>DegradationJitterAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-166">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="7eb89-166">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-167">由抖动引起的网络 MOS 性能下降。</span><span class="sxs-lookup"><span data-stu-id="7eb89-167">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-168"><strong>DegradationPacketLossAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-168"><strong>DegradationPacketLossAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-169">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="7eb89-169">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-170">因数据包丢失而导致的网络 MOS 降级。</span><span class="sxs-lookup"><span data-stu-id="7eb89-170">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-171"><strong>AudioPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-171"><strong>AudioPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-172">int</span><span class="sxs-lookup"><span data-stu-id="7eb89-172">int</span></span></p></td>
<td><p><span data-ttu-id="7eb89-173">对外</span><span class="sxs-lookup"><span data-stu-id="7eb89-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="7eb89-174">用于呼叫的音频编解码器，从 PayloadDescription 表中引用。</span><span class="sxs-lookup"><span data-stu-id="7eb89-174">The audio Codec used for the call, referenced from PayloadDescription Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-175"><strong>AudioSampleRate</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-175"><strong>AudioSampleRate</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-176">int</span><span class="sxs-lookup"><span data-stu-id="7eb89-176">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-177">音频流的采样率。</span><span class="sxs-lookup"><span data-stu-id="7eb89-177">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-178"><strong>工程</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-178"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-179">int</span><span class="sxs-lookup"><span data-stu-id="7eb89-179">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-180">RTCP 统计信息中的来回行程时间。</span><span class="sxs-lookup"><span data-stu-id="7eb89-180">Round trip time from RTCP statistics.</span></span> <span data-ttu-id="7eb89-181">为了获得可接受的质量，此数量应小于100毫秒。</span><span class="sxs-lookup"><span data-stu-id="7eb89-181">For acceptable quality this should be less than 100ms.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-182"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-182"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-183">int</span><span class="sxs-lookup"><span data-stu-id="7eb89-183">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-184">音频流的最大来回行程时间。</span><span class="sxs-lookup"><span data-stu-id="7eb89-184">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-185"><strong>OverallAvgNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-185"><strong>OverallAvgNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-186">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="7eb89-186">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-187">呼叫的平均宽带网络 MOS。</span><span class="sxs-lookup"><span data-stu-id="7eb89-187">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="7eb89-188">此指标取决于所使用的数据包丢失、抖动和编解码器。</span><span class="sxs-lookup"><span data-stu-id="7eb89-188">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="7eb89-189">范围为 [1.0 至 5.0]。</span><span class="sxs-lookup"><span data-stu-id="7eb89-189">Range is [1.0 to 5.0].</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-190"><strong>OverallMinNetworkMOS</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-190"><strong>OverallMinNetworkMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-191">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="7eb89-191">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-192">呼叫的最小宽带网络 MOS。</span><span class="sxs-lookup"><span data-stu-id="7eb89-192">The minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-193"><strong>SendListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-193"><strong>SendListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-194">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="7eb89-194">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-195">平均预测的宽带侦听音频发送的 MOS 分数，包括语音级别、噪声级别和捕获设备特征。</span><span class="sxs-lookup"><span data-stu-id="7eb89-195">The average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-196"><strong>SendListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-196"><strong>SendListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-197">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="7eb89-197">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-198">呼叫的最小 SendListenMOS。</span><span class="sxs-lookup"><span data-stu-id="7eb89-198">The minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-199"><strong>RecvListenMOS</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-199"><strong>RecvListenMOS</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-200">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="7eb89-200">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-201">平均预测宽带侦听从网络接收的音频的 MOS 分数，包括语音级别、噪音级别、编解码器、网络条件和捕获设备特征。</span><span class="sxs-lookup"><span data-stu-id="7eb89-201">The average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-202"><strong>RecvListenMOSMin</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-202"><strong>RecvListenMOSMin</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-203">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="7eb89-203">decimal(3,2)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-204">呼叫的最小 RecvListenMOS。</span><span class="sxs-lookup"><span data-stu-id="7eb89-204">The minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-205"><strong>AudioFECUsed</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-205"><strong>AudioFECUsed</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-206">位</span><span class="sxs-lookup"><span data-stu-id="7eb89-206">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-207">指示是否已对呼叫使用音频 FEC 的标志。</span><span class="sxs-lookup"><span data-stu-id="7eb89-207">Flag indicating if audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-208"><strong>RatioConcealedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-208"><strong>RatioConcealedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-209">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="7eb89-209">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-210">通过音频康复对典型示例生成的隐藏样本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="7eb89-210">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-211"><strong>RatioStretchedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-211"><strong>RatioStretchedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-212">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="7eb89-212">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-213">由音频康复生成的一般示例中的延伸样本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="7eb89-213">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-214"><strong>RatioCompressedSamplesAvg</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-214"><strong>RatioCompressedSamplesAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-215">decimal （5，2）</span><span class="sxs-lookup"><span data-stu-id="7eb89-215">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-216">由音频康复生成的压缩样本的平均比率到典型示例。</span><span class="sxs-lookup"><span data-stu-id="7eb89-216">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-217"><strong>进货</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-217"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-218">位</span><span class="sxs-lookup"><span data-stu-id="7eb89-218">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-219">接收接收器端的数据流数据。</span><span class="sxs-lookup"><span data-stu-id="7eb89-219">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-220"><strong>出站</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-220"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-221">位</span><span class="sxs-lookup"><span data-stu-id="7eb89-221">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-222">接收发件人端上的数据流数据。</span><span class="sxs-lookup"><span data-stu-id="7eb89-222">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-223"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-223"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-224">位</span><span class="sxs-lookup"><span data-stu-id="7eb89-224">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="7eb89-225">1表示流方向从呼叫者到被叫方。</span><span class="sxs-lookup"><span data-stu-id="7eb89-225">1 means the stream direction is from the caller to the callee.</span></span></p>
<p><span data-ttu-id="7eb89-226">0 表示流方向是从被叫方到呼叫者。</span><span class="sxs-lookup"><span data-stu-id="7eb89-226">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-227"><strong>JitterInterArrivalSD</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-227"><strong>JitterInterArrivalSD</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-228">点数</span><span class="sxs-lookup"><span data-stu-id="7eb89-228">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-229">抖动到达时间的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="7eb89-229">Standard deviation for jitter arrival times.</span></span></p>
<p><span data-ttu-id="7eb89-230">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-231"><strong>ConcealRatioMax</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-231"><strong>ConcealRatioMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-232">点数</span><span class="sxs-lookup"><span data-stu-id="7eb89-232">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-233">由修复程序隐藏的数据包的最大比率。</span><span class="sxs-lookup"><span data-stu-id="7eb89-233">Maximum ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="7eb89-234">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-235"><strong>ConcealRatioSD</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-235"><strong>ConcealRatioSD</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-236">点数</span><span class="sxs-lookup"><span data-stu-id="7eb89-236">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-237">修复程序隐藏的数据包比率的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="7eb89-237">Standard deviation for the ratio of packets concealed by the healer.</span></span></p>
<p><span data-ttu-id="7eb89-238">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-239"><strong>HealerPacketDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-239"><strong>HealerPacketDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-240">点数</span><span class="sxs-lookup"><span data-stu-id="7eb89-240">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-241">修复程序丢弃的数据包与接收的数据包总数的比率。</span><span class="sxs-lookup"><span data-stu-id="7eb89-241">Ratio of packets dropped by the healer compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="7eb89-242">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-243"><strong>HealerFECPacketUsedRatio</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-243"><strong>HealerFECPacketUsedRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-244">点数</span><span class="sxs-lookup"><span data-stu-id="7eb89-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-245">与接收的数据包总数相比使用的转发错误纠正数据包的比率。</span><span class="sxs-lookup"><span data-stu-id="7eb89-245">Ratio of used forward error correction packets compared to the total number of packets received.</span></span></p>
<p><span data-ttu-id="7eb89-246">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-247"><strong>MaxCompressedSamples</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-247"><strong>MaxCompressedSamples</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-248">点数</span><span class="sxs-lookup"><span data-stu-id="7eb89-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-249">由修复程序压缩的最大音频数据包数。</span><span class="sxs-lookup"><span data-stu-id="7eb89-249">Maximum number of audio packets that were compressed by the healer.</span></span></p>
<p><span data-ttu-id="7eb89-250">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-251"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-251"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-252">点数</span><span class="sxs-lookup"><span data-stu-id="7eb89-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-253">指示呼叫处于丢失拥塞状态的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="7eb89-253">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="7eb89-254">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-254">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-255"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-255"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-256">点数</span><span class="sxs-lookup"><span data-stu-id="7eb89-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-257">指示因网络数据包的延迟到达而导致拥塞的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="7eb89-257">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="7eb89-258">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-258">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-259"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-259"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-260">点数</span><span class="sxs-lookup"><span data-stu-id="7eb89-260">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-261">指示呼叫竞争网络资源的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="7eb89-261">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="7eb89-262">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-262">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-263"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-263"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-264">int</span><span class="sxs-lookup"><span data-stu-id="7eb89-264">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-265">在呼叫过程中测量的最小带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="7eb89-265">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="7eb89-266">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-267"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-267"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-268">int</span><span class="sxs-lookup"><span data-stu-id="7eb89-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-269">在呼叫过程中测量的最大带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="7eb89-269">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="7eb89-270">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-270">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-271"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-271"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-272">int</span><span class="sxs-lookup"><span data-stu-id="7eb89-272">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-273">在呼叫过程中测量的带宽估计的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="7eb89-273">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="7eb89-274">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-274">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-275"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-275"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-276">int</span><span class="sxs-lookup"><span data-stu-id="7eb89-276">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-277">呼叫期间衡量的平均带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="7eb89-277">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="7eb89-278">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-279"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-279"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-280">点数</span><span class="sxs-lookup"><span data-stu-id="7eb89-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-p105">单向延迟的总量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="7eb89-p105">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="7eb89-283">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-283">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-284"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-284"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-285">点数</span><span class="sxs-lookup"><span data-stu-id="7eb89-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-p106">单向延迟的平均量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="7eb89-p106">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="7eb89-288">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-288">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-289"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-289"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-290">点数</span><span class="sxs-lookup"><span data-stu-id="7eb89-290">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-p107">单向延迟的最大量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="7eb89-p107">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="7eb89-293">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-293">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-294"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-294"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-295">int</span><span class="sxs-lookup"><span data-stu-id="7eb89-295">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-p108">单向突发总发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="7eb89-p108">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7eb89-299">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-299">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-300"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-300"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-301">点数</span><span class="sxs-lookup"><span data-stu-id="7eb89-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-p109">单向突发总密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="7eb89-p109">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7eb89-305">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-306"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-306"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-307">点数</span><span class="sxs-lookup"><span data-stu-id="7eb89-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-p110">单向突发总持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="7eb89-p110">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7eb89-311">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-312"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-312"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-313">int</span><span class="sxs-lookup"><span data-stu-id="7eb89-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-p111">单向间隙总发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="7eb89-p111">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7eb89-317">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-317">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-318"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-318"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-319">点数</span><span class="sxs-lookup"><span data-stu-id="7eb89-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-p112">单向间隙总密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="7eb89-p112">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7eb89-323">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-324"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-324"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-325">点数</span><span class="sxs-lookup"><span data-stu-id="7eb89-325">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-p113">单向间隙总持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="7eb89-p113">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="7eb89-329">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-329">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-330"><strong>DecodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-330"><strong>DecodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-331">点数</span><span class="sxs-lookup"><span data-stu-id="7eb89-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-332">被解码为立体声的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="7eb89-332">Percentage of the call decoded as stereo.</span></span></p>
<p><span data-ttu-id="7eb89-333">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-334"><strong>AecRenderStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-334"><strong>AecRenderStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-335">点数</span><span class="sxs-lookup"><span data-stu-id="7eb89-335">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-336">通过音响回声消除器呈现为立体声的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="7eb89-336">Percentage of the call rendered as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="7eb89-337">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-337">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-338"><strong>AudioPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-338"><strong>AudioPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-339">点数</span><span class="sxs-lookup"><span data-stu-id="7eb89-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-340">应用转发错误纠正率后的数据包丢失率。</span><span class="sxs-lookup"><span data-stu-id="7eb89-340">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="7eb89-341">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-341">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="7eb89-342"><strong>EncodeStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-342"><strong>EncodeStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-343">点数</span><span class="sxs-lookup"><span data-stu-id="7eb89-343">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-344">编码为立体声的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="7eb89-344">Percentage of the call encoded as stereo.</span></span></p>
<p><span data-ttu-id="7eb89-345">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-345">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="7eb89-346"><strong>AecCaptureStereoPercent</strong></span><span class="sxs-lookup"><span data-stu-id="7eb89-346"><strong>AecCaptureStereoPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="7eb89-347">点数</span><span class="sxs-lookup"><span data-stu-id="7eb89-347">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="7eb89-348">通过音响回声消除器以立体声形式捕获的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="7eb89-348">Percentage of the call captured as stereo by the acoustic echo canceller.</span></span></p>
<p><span data-ttu-id="7eb89-349">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7eb89-349">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

