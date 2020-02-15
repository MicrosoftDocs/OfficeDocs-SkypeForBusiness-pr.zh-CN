---
title: Lync Server 2013： VideoStream 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 00abc61fc7ba83b94f3228de91eb9fa6810fc93c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="871c8-102">Lync Server 2013 中的 VideoStream 表</span><span class="sxs-lookup"><span data-stu-id="871c8-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="871c8-103">_**上次修改的主题：** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="871c8-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="871c8-104">每个记录代表一个视频流。</span><span class="sxs-lookup"><span data-stu-id="871c8-104">Each record represents one video stream.</span></span> <span data-ttu-id="871c8-105">一个视频媒体线路通常包含两个视频流。</span><span class="sxs-lookup"><span data-stu-id="871c8-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="871c8-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="871c8-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="871c8-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="871c8-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="871c8-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-111">datetime</span><span class="sxs-lookup"><span data-stu-id="871c8-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="871c8-112">主</span><span class="sxs-lookup"><span data-stu-id="871c8-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="871c8-113"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="871c8-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-115">int</span><span class="sxs-lookup"><span data-stu-id="871c8-115">int</span></span></p></td>
<td><p><span data-ttu-id="871c8-116">主</span><span class="sxs-lookup"><span data-stu-id="871c8-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="871c8-117"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表</a>引用 R。</span><span class="sxs-lookup"><span data-stu-id="871c8-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="871c8-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="871c8-120">主</span><span class="sxs-lookup"><span data-stu-id="871c8-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="871c8-121"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="871c8-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-123">int</span><span class="sxs-lookup"><span data-stu-id="871c8-123">int</span></span></p></td>
<td><p><span data-ttu-id="871c8-124">主</span><span class="sxs-lookup"><span data-stu-id="871c8-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="871c8-125">媒体行中的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="871c8-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-127">smallint</span><span class="sxs-lookup"><span data-stu-id="871c8-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="871c8-128">外部、主</span><span class="sxs-lookup"><span data-stu-id="871c8-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="871c8-129">有效负载说明。</span><span class="sxs-lookup"><span data-stu-id="871c8-129">Payload description.</span></span> <span data-ttu-id="871c8-130">有关详细信息，请参阅<a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中的 PayloadDescription 表</a>。</span><span class="sxs-lookup"><span data-stu-id="871c8-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-132">int</span><span class="sxs-lookup"><span data-stu-id="871c8-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="871c8-133">实时控制协议 (RTCP) 统计信息中的平均网络抖动。</span><span class="sxs-lookup"><span data-stu-id="871c8-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-135">int</span><span class="sxs-lookup"><span data-stu-id="871c8-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="871c8-136">视频会话过程中的最大网络抖动。</span><span class="sxs-lookup"><span data-stu-id="871c8-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-137"><strong>工程</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-138">int</span><span class="sxs-lookup"><span data-stu-id="871c8-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="871c8-139">RTCP 统计信息中的来回行程时间。</span><span class="sxs-lookup"><span data-stu-id="871c8-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-141">int</span><span class="sxs-lookup"><span data-stu-id="871c8-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="871c8-142">视频流的最长往返时间。</span><span class="sxs-lookup"><span data-stu-id="871c8-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-144">decimal （5，4）</span><span class="sxs-lookup"><span data-stu-id="871c8-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="871c8-145">呼叫期间的平均数据包丢失率。</span><span class="sxs-lookup"><span data-stu-id="871c8-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-147">decimal （5，4）</span><span class="sxs-lookup"><span data-stu-id="871c8-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="871c8-148">呼叫期间观测到的数据包丢失最大值。</span><span class="sxs-lookup"><span data-stu-id="871c8-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-150">int</span><span class="sxs-lookup"><span data-stu-id="871c8-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="871c8-151">视频流的数据包计数（实时传输协议，RTP）。</span><span class="sxs-lookup"><span data-stu-id="871c8-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-152"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-153">int</span><span class="sxs-lookup"><span data-stu-id="871c8-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="871c8-154">视频流的带宽估计。</span><span class="sxs-lookup"><span data-stu-id="871c8-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-156">char （9）</span><span class="sxs-lookup"><span data-stu-id="871c8-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="871c8-p103">视频的分辨率（像素宽乘以像素高）。报告为字符串。</span><span class="sxs-lookup"><span data-stu-id="871c8-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-160">int</span><span class="sxs-lookup"><span data-stu-id="871c8-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="871c8-161">视频流的平均比特率。</span><span class="sxs-lookup"><span data-stu-id="871c8-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-163">小数（9，4）</span><span class="sxs-lookup"><span data-stu-id="871c8-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="871c8-164">收到的视频帧速率。</span><span class="sxs-lookup"><span data-stu-id="871c8-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-166">小数（9，4）</span><span class="sxs-lookup"><span data-stu-id="871c8-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="871c8-167">发送的视频帧速率。</span><span class="sxs-lookup"><span data-stu-id="871c8-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-169">int</span><span class="sxs-lookup"><span data-stu-id="871c8-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="871c8-170">视频会话期间的最大视频比特率。</span><span class="sxs-lookup"><span data-stu-id="871c8-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-172">小数（9，4）</span><span class="sxs-lookup"><span data-stu-id="871c8-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="871c8-173">丢失的视频帧总数的百分比。</span><span class="sxs-lookup"><span data-stu-id="871c8-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-175">位</span><span class="sxs-lookup"><span data-stu-id="871c8-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="871c8-176">不可用。</span><span class="sxs-lookup"><span data-stu-id="871c8-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-178">小数（9，4）</span><span class="sxs-lookup"><span data-stu-id="871c8-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-179">丢失的视频帧总数的百分比。</span><span class="sxs-lookup"><span data-stu-id="871c8-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="871c8-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-182">以通用交换格式（CIF）分辨率表示的呼叫百分比。</span><span class="sxs-lookup"><span data-stu-id="871c8-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="871c8-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-185">以 VGA 分辨率表示的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="871c8-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="871c8-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-188">呼叫的百分比，以 HD720 的分辨率为依据。</span><span class="sxs-lookup"><span data-stu-id="871c8-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="871c8-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-191">不放置帧的呼叫持续时间百分比。</span><span class="sxs-lookup"><span data-stu-id="871c8-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="871c8-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-194">B 帧删除的呼叫持续时间百分比。</span><span class="sxs-lookup"><span data-stu-id="871c8-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="871c8-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-197">具有 BP 框架丢弃的呼叫持续时间百分比。</span><span class="sxs-lookup"><span data-stu-id="871c8-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="871c8-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-200">带有 BPSP 框架丢弃的呼叫持续时间的百分比。</span><span class="sxs-lookup"><span data-stu-id="871c8-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="871c8-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-203">带有 BPSPI 框架丢弃的呼叫持续时间的百分比。</span><span class="sxs-lookup"><span data-stu-id="871c8-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-204"><strong>进货</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-205">位</span><span class="sxs-lookup"><span data-stu-id="871c8-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="871c8-206">接收接收器端的数据流数据。</span><span class="sxs-lookup"><span data-stu-id="871c8-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-207"><strong>出站</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-208">位</span><span class="sxs-lookup"><span data-stu-id="871c8-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="871c8-209">接收发件人端上的数据流数据。</span><span class="sxs-lookup"><span data-stu-id="871c8-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-211">位</span><span class="sxs-lookup"><span data-stu-id="871c8-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="871c8-212">1 表示流方向是从呼叫者到被叫方。</span><span class="sxs-lookup"><span data-stu-id="871c8-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="871c8-213">0 表示流方向是从被叫方到呼叫者。</span><span class="sxs-lookup"><span data-stu-id="871c8-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-215">点数</span><span class="sxs-lookup"><span data-stu-id="871c8-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-216">指示呼叫处于丢失拥塞状态的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="871c8-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="871c8-217">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-219">点数</span><span class="sxs-lookup"><span data-stu-id="871c8-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-220">指示因网络数据包的延迟到达而导致拥塞的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="871c8-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="871c8-221">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-223">点数</span><span class="sxs-lookup"><span data-stu-id="871c8-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-224">指示呼叫竞争网络资源的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="871c8-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="871c8-225">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-227">int</span><span class="sxs-lookup"><span data-stu-id="871c8-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-228">在呼叫过程中测量的最小带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="871c8-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="871c8-229">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-231">int</span><span class="sxs-lookup"><span data-stu-id="871c8-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-232">在呼叫过程中测量的最大带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="871c8-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="871c8-233">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-235">int</span><span class="sxs-lookup"><span data-stu-id="871c8-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-236">在呼叫过程中测量的带宽估计的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="871c8-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="871c8-237">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-239">int</span><span class="sxs-lookup"><span data-stu-id="871c8-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-240">呼叫期间衡量的平均带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="871c8-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="871c8-241">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-243">点数</span><span class="sxs-lookup"><span data-stu-id="871c8-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-244">终结点确定网络连接无法支持多种显示视频的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="871c8-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="871c8-245">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-247">点数</span><span class="sxs-lookup"><span data-stu-id="871c8-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-p104">单向延迟的总量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="871c8-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="871c8-250">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-252">点数</span><span class="sxs-lookup"><span data-stu-id="871c8-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-p105">单向延迟的平均量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="871c8-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="871c8-255">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-257">点数</span><span class="sxs-lookup"><span data-stu-id="871c8-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-p106">单向延迟的最大量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="871c8-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="871c8-260">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-262">int</span><span class="sxs-lookup"><span data-stu-id="871c8-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-p107">单向突发总发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="871c8-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="871c8-266">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-268">int</span><span class="sxs-lookup"><span data-stu-id="871c8-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-p108">单向突发总密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="871c8-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="871c8-272">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-274">点数</span><span class="sxs-lookup"><span data-stu-id="871c8-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-p109">单向突发总持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="871c8-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="871c8-278">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-280">int</span><span class="sxs-lookup"><span data-stu-id="871c8-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-p110">单向间隙总发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="871c8-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="871c8-284">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-286">点数</span><span class="sxs-lookup"><span data-stu-id="871c8-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-p111">单向间隙总密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="871c8-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="871c8-290">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-292">点数</span><span class="sxs-lookup"><span data-stu-id="871c8-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-p112">单向间隙总持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="871c8-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="871c8-296">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-298">小数（9，4）</span><span class="sxs-lookup"><span data-stu-id="871c8-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-299">视频数据包丢失的比特率。</span><span class="sxs-lookup"><span data-stu-id="871c8-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="871c8-300">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-302">int</span><span class="sxs-lookup"><span data-stu-id="871c8-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-303">为视频分配的平均带宽量。</span><span class="sxs-lookup"><span data-stu-id="871c8-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="871c8-304">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-306">smallint</span><span class="sxs-lookup"><span data-stu-id="871c8-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="871c8-307">对外</span><span class="sxs-lookup"><span data-stu-id="871c8-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="871c8-308">发件人使用的视频编解码器类型。</span><span class="sxs-lookup"><span data-stu-id="871c8-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="871c8-309">有关详细信息，请参阅<a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表</a>。</span><span class="sxs-lookup"><span data-stu-id="871c8-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="871c8-310">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-312">int</span><span class="sxs-lookup"><span data-stu-id="871c8-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-313">发件人使用的分辨率宽度。</span><span class="sxs-lookup"><span data-stu-id="871c8-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="871c8-314">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-316">int</span><span class="sxs-lookup"><span data-stu-id="871c8-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-317">发件人使用的分辨率高度。</span><span class="sxs-lookup"><span data-stu-id="871c8-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="871c8-318">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-320">点数</span><span class="sxs-lookup"><span data-stu-id="871c8-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-321">发件人使用的平均视频帧速率传输。</span><span class="sxs-lookup"><span data-stu-id="871c8-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="871c8-322">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-324">int</span><span class="sxs-lookup"><span data-stu-id="871c8-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-325">发件人的最大比特率。</span><span class="sxs-lookup"><span data-stu-id="871c8-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="871c8-326">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-328">int</span><span class="sxs-lookup"><span data-stu-id="871c8-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-329">发件人的平均比特率。</span><span class="sxs-lookup"><span data-stu-id="871c8-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-331">int</span><span class="sxs-lookup"><span data-stu-id="871c8-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-332">发件人使用的视频流的最大数量。</span><span class="sxs-lookup"><span data-stu-id="871c8-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="871c8-333">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-335">smallint</span><span class="sxs-lookup"><span data-stu-id="871c8-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="871c8-336">对外</span><span class="sxs-lookup"><span data-stu-id="871c8-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="871c8-337">接收器使用的视频代码。</span><span class="sxs-lookup"><span data-stu-id="871c8-337">Video codes used by the receiver.</span></span> <span data-ttu-id="871c8-338">有关详细信息，请参阅<a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表</a>。</span><span class="sxs-lookup"><span data-stu-id="871c8-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="871c8-339">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-341">int</span><span class="sxs-lookup"><span data-stu-id="871c8-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-342">接收器使用的分辨率宽度。</span><span class="sxs-lookup"><span data-stu-id="871c8-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="871c8-343">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-345">int</span><span class="sxs-lookup"><span data-stu-id="871c8-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-346">接收器使用的分辨率高度。</span><span class="sxs-lookup"><span data-stu-id="871c8-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="871c8-347">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-349">点数</span><span class="sxs-lookup"><span data-stu-id="871c8-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-350">接收器使用的平均视频帧速率。</span><span class="sxs-lookup"><span data-stu-id="871c8-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="871c8-351">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-353">int</span><span class="sxs-lookup"><span data-stu-id="871c8-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-354">接收器的最大比特率。</span><span class="sxs-lookup"><span data-stu-id="871c8-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="871c8-355">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-357">int</span><span class="sxs-lookup"><span data-stu-id="871c8-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-358">接收器的平均比特率。</span><span class="sxs-lookup"><span data-stu-id="871c8-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="871c8-359">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-361">int</span><span class="sxs-lookup"><span data-stu-id="871c8-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-362">接收器的最大视频流。</span><span class="sxs-lookup"><span data-stu-id="871c8-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="871c8-363">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-365">int</span><span class="sxs-lookup"><span data-stu-id="871c8-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-366">接收器的最小视频流。</span><span class="sxs-lookup"><span data-stu-id="871c8-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="871c8-367">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-369">int</span><span class="sxs-lookup"><span data-stu-id="871c8-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-370">接收器的视频模式（例如，库或单个流）。</span><span class="sxs-lookup"><span data-stu-id="871c8-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="871c8-371">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-373">点数</span><span class="sxs-lookup"><span data-stu-id="871c8-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-374">应用转发错误纠正率后的数据包丢失率。</span><span class="sxs-lookup"><span data-stu-id="871c8-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="871c8-375">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-377">点数</span><span class="sxs-lookup"><span data-stu-id="871c8-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-378">动态功能标志处于活动状态的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="871c8-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="871c8-379">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-381">char （9）</span><span class="sxs-lookup"><span data-stu-id="871c8-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-382">呼叫期间衡量的最低分辨率。</span><span class="sxs-lookup"><span data-stu-id="871c8-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="871c8-383">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-385">点数</span><span class="sxs-lookup"><span data-stu-id="871c8-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-386">低于低比特率阈值（每秒 70 kb）的呼叫百分比。</span><span class="sxs-lookup"><span data-stu-id="871c8-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="871c8-387">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-389">点数</span><span class="sxs-lookup"><span data-stu-id="871c8-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-390">呼叫百分比低于低帧速率阈值（每秒7.5 帧，入站）。</span><span class="sxs-lookup"><span data-stu-id="871c8-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="871c8-391">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-393">点数</span><span class="sxs-lookup"><span data-stu-id="871c8-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-394">最低分辨率发生的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="871c8-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="871c8-395">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="871c8-396">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="871c8-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-398">点数</span><span class="sxs-lookup"><span data-stu-id="871c8-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-399">以秒为单位的呼叫长度。</span><span class="sxs-lookup"><span data-stu-id="871c8-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="871c8-400">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="871c8-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="871c8-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="871c8-402">位</span><span class="sxs-lookup"><span data-stu-id="871c8-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="871c8-403">指示是否已从多个调用中聚合数据。</span><span class="sxs-lookup"><span data-stu-id="871c8-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="871c8-404">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="871c8-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

