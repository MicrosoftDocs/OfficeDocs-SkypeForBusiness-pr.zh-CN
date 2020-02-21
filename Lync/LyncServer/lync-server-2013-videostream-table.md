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
ms.openlocfilehash: a313419ca4072fe4d1841ba66a9cb603671e6c56
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211639"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="c3752-102">Lync Server 2013 中的 VideoStream 表</span><span class="sxs-lookup"><span data-stu-id="c3752-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3752-103">_**上次修改的主题：** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="c3752-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="c3752-104">每个记录代表一个视频流。</span><span class="sxs-lookup"><span data-stu-id="c3752-104">Each record represents one video stream.</span></span> <span data-ttu-id="c3752-105">一个视频媒体线路通常包含两个视频流。</span><span class="sxs-lookup"><span data-stu-id="c3752-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c3752-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="c3752-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="c3752-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="c3752-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c3752-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-111">datetime</span><span class="sxs-lookup"><span data-stu-id="c3752-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="c3752-112">主</span><span class="sxs-lookup"><span data-stu-id="c3752-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="c3752-113"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="c3752-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-115">int</span><span class="sxs-lookup"><span data-stu-id="c3752-115">int</span></span></p></td>
<td><p><span data-ttu-id="c3752-116">主</span><span class="sxs-lookup"><span data-stu-id="c3752-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="c3752-117"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表</a>引用 R。</span><span class="sxs-lookup"><span data-stu-id="c3752-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="c3752-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c3752-120">主</span><span class="sxs-lookup"><span data-stu-id="c3752-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="c3752-121"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="c3752-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-123">int</span><span class="sxs-lookup"><span data-stu-id="c3752-123">int</span></span></p></td>
<td><p><span data-ttu-id="c3752-124">主</span><span class="sxs-lookup"><span data-stu-id="c3752-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="c3752-125">媒体行中的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="c3752-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-127">smallint</span><span class="sxs-lookup"><span data-stu-id="c3752-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="c3752-128">外部、主</span><span class="sxs-lookup"><span data-stu-id="c3752-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="c3752-129">有效负载说明。</span><span class="sxs-lookup"><span data-stu-id="c3752-129">Payload description.</span></span> <span data-ttu-id="c3752-130">有关详细信息，请参阅<a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中的 PayloadDescription 表</a>。</span><span class="sxs-lookup"><span data-stu-id="c3752-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-132">int</span><span class="sxs-lookup"><span data-stu-id="c3752-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c3752-133">实时控制协议 (RTCP) 统计信息中的平均网络抖动。</span><span class="sxs-lookup"><span data-stu-id="c3752-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-135">int</span><span class="sxs-lookup"><span data-stu-id="c3752-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c3752-136">视频会话过程中的最大网络抖动。</span><span class="sxs-lookup"><span data-stu-id="c3752-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-137"><strong>工程</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-138">int</span><span class="sxs-lookup"><span data-stu-id="c3752-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c3752-139">RTCP 统计信息中的来回行程时间。</span><span class="sxs-lookup"><span data-stu-id="c3752-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-141">int</span><span class="sxs-lookup"><span data-stu-id="c3752-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c3752-142">视频流的最长往返时间。</span><span class="sxs-lookup"><span data-stu-id="c3752-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-144">decimal （5，4）</span><span class="sxs-lookup"><span data-stu-id="c3752-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c3752-145">呼叫期间的平均数据包丢失率。</span><span class="sxs-lookup"><span data-stu-id="c3752-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-147">decimal （5，4）</span><span class="sxs-lookup"><span data-stu-id="c3752-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c3752-148">呼叫期间观测到的数据包丢失最大值。</span><span class="sxs-lookup"><span data-stu-id="c3752-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-150">int</span><span class="sxs-lookup"><span data-stu-id="c3752-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c3752-151">视频流的数据包计数（实时传输协议，RTP）。</span><span class="sxs-lookup"><span data-stu-id="c3752-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-152"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-153">int</span><span class="sxs-lookup"><span data-stu-id="c3752-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c3752-154">视频流的带宽估计。</span><span class="sxs-lookup"><span data-stu-id="c3752-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-156">char （9）</span><span class="sxs-lookup"><span data-stu-id="c3752-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c3752-p103">视频的分辨率（像素宽乘以像素高）。报告为字符串。</span><span class="sxs-lookup"><span data-stu-id="c3752-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-160">int</span><span class="sxs-lookup"><span data-stu-id="c3752-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c3752-161">视频流的平均比特率。</span><span class="sxs-lookup"><span data-stu-id="c3752-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-163">小数（9，4）</span><span class="sxs-lookup"><span data-stu-id="c3752-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c3752-164">收到的视频帧速率。</span><span class="sxs-lookup"><span data-stu-id="c3752-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-166">小数（9，4）</span><span class="sxs-lookup"><span data-stu-id="c3752-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c3752-167">发送的视频帧速率。</span><span class="sxs-lookup"><span data-stu-id="c3752-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-169">int</span><span class="sxs-lookup"><span data-stu-id="c3752-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c3752-170">视频会话期间的最大视频比特率。</span><span class="sxs-lookup"><span data-stu-id="c3752-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-172">小数（9，4）</span><span class="sxs-lookup"><span data-stu-id="c3752-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c3752-173">丢失的视频帧总数的百分比。</span><span class="sxs-lookup"><span data-stu-id="c3752-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-175">位</span><span class="sxs-lookup"><span data-stu-id="c3752-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c3752-176">不可用。</span><span class="sxs-lookup"><span data-stu-id="c3752-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-178">小数（9，4）</span><span class="sxs-lookup"><span data-stu-id="c3752-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-179">丢失的视频帧总数的百分比。</span><span class="sxs-lookup"><span data-stu-id="c3752-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="c3752-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-182">以通用交换格式（CIF）分辨率表示的呼叫百分比。</span><span class="sxs-lookup"><span data-stu-id="c3752-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="c3752-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-185">以 VGA 分辨率表示的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="c3752-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="c3752-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-188">呼叫的百分比，以 HD720 的分辨率为依据。</span><span class="sxs-lookup"><span data-stu-id="c3752-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="c3752-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-191">不放置帧的呼叫持续时间百分比。</span><span class="sxs-lookup"><span data-stu-id="c3752-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="c3752-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-194">B 帧删除的呼叫持续时间百分比。</span><span class="sxs-lookup"><span data-stu-id="c3752-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="c3752-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-197">具有 BP 框架丢弃的呼叫持续时间百分比。</span><span class="sxs-lookup"><span data-stu-id="c3752-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="c3752-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-200">带有 BPSP 框架丢弃的呼叫持续时间的百分比。</span><span class="sxs-lookup"><span data-stu-id="c3752-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="c3752-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-203">带有 BPSPI 框架丢弃的呼叫持续时间的百分比。</span><span class="sxs-lookup"><span data-stu-id="c3752-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-204"><strong>进货</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-205">位</span><span class="sxs-lookup"><span data-stu-id="c3752-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c3752-206">接收接收器端的数据流数据。</span><span class="sxs-lookup"><span data-stu-id="c3752-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-207"><strong>出站</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-208">位</span><span class="sxs-lookup"><span data-stu-id="c3752-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c3752-209">接收发件人端上的数据流数据。</span><span class="sxs-lookup"><span data-stu-id="c3752-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-211">位</span><span class="sxs-lookup"><span data-stu-id="c3752-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="c3752-212">1 表示流方向是从呼叫者到被叫方。</span><span class="sxs-lookup"><span data-stu-id="c3752-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="c3752-213">0 表示流方向是从被叫方到呼叫者。</span><span class="sxs-lookup"><span data-stu-id="c3752-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-215">点数</span><span class="sxs-lookup"><span data-stu-id="c3752-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-216">指示呼叫处于丢失拥塞状态的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="c3752-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="c3752-217">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-219">点数</span><span class="sxs-lookup"><span data-stu-id="c3752-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-220">指示因网络数据包的延迟到达而导致拥塞的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="c3752-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="c3752-221">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-223">点数</span><span class="sxs-lookup"><span data-stu-id="c3752-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-224">指示呼叫竞争网络资源的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="c3752-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="c3752-225">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-227">int</span><span class="sxs-lookup"><span data-stu-id="c3752-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-228">在呼叫过程中测量的最小带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="c3752-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="c3752-229">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-231">int</span><span class="sxs-lookup"><span data-stu-id="c3752-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-232">在呼叫过程中测量的最大带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="c3752-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="c3752-233">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-235">int</span><span class="sxs-lookup"><span data-stu-id="c3752-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-236">在呼叫过程中测量的带宽估计的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="c3752-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="c3752-237">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-239">int</span><span class="sxs-lookup"><span data-stu-id="c3752-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-240">呼叫期间衡量的平均带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="c3752-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="c3752-241">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-243">点数</span><span class="sxs-lookup"><span data-stu-id="c3752-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-244">终结点确定网络连接无法支持多种显示视频的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="c3752-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="c3752-245">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-247">点数</span><span class="sxs-lookup"><span data-stu-id="c3752-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-p104">单向延迟的总量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="c3752-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="c3752-250">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-252">点数</span><span class="sxs-lookup"><span data-stu-id="c3752-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-p105">单向延迟的平均量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="c3752-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="c3752-255">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-257">点数</span><span class="sxs-lookup"><span data-stu-id="c3752-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-p106">单向延迟的最大量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="c3752-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="c3752-260">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-262">int</span><span class="sxs-lookup"><span data-stu-id="c3752-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-p107">单向突发总发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="c3752-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="c3752-266">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-268">int</span><span class="sxs-lookup"><span data-stu-id="c3752-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-p108">单向突发总密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="c3752-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="c3752-272">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-274">点数</span><span class="sxs-lookup"><span data-stu-id="c3752-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-p109">单向突发总持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="c3752-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="c3752-278">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-280">int</span><span class="sxs-lookup"><span data-stu-id="c3752-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-p110">单向间隙总发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="c3752-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="c3752-284">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-286">点数</span><span class="sxs-lookup"><span data-stu-id="c3752-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-p111">单向间隙总密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="c3752-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="c3752-290">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-292">点数</span><span class="sxs-lookup"><span data-stu-id="c3752-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-p112">单向间隙总持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="c3752-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="c3752-296">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-298">小数（9，4）</span><span class="sxs-lookup"><span data-stu-id="c3752-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-299">视频数据包丢失的比特率。</span><span class="sxs-lookup"><span data-stu-id="c3752-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="c3752-300">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-302">int</span><span class="sxs-lookup"><span data-stu-id="c3752-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-303">为视频分配的平均带宽量。</span><span class="sxs-lookup"><span data-stu-id="c3752-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="c3752-304">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-306">smallint</span><span class="sxs-lookup"><span data-stu-id="c3752-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="c3752-307">对外</span><span class="sxs-lookup"><span data-stu-id="c3752-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c3752-308">发件人使用的视频编解码器类型。</span><span class="sxs-lookup"><span data-stu-id="c3752-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="c3752-309">有关详细信息，请参阅<a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表</a>。</span><span class="sxs-lookup"><span data-stu-id="c3752-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="c3752-310">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-312">int</span><span class="sxs-lookup"><span data-stu-id="c3752-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-313">发件人使用的分辨率宽度。</span><span class="sxs-lookup"><span data-stu-id="c3752-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="c3752-314">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-316">int</span><span class="sxs-lookup"><span data-stu-id="c3752-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-317">发件人使用的分辨率高度。</span><span class="sxs-lookup"><span data-stu-id="c3752-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="c3752-318">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-320">点数</span><span class="sxs-lookup"><span data-stu-id="c3752-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-321">发件人使用的平均视频帧速率传输。</span><span class="sxs-lookup"><span data-stu-id="c3752-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="c3752-322">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-324">int</span><span class="sxs-lookup"><span data-stu-id="c3752-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-325">发件人的最大比特率。</span><span class="sxs-lookup"><span data-stu-id="c3752-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="c3752-326">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-328">int</span><span class="sxs-lookup"><span data-stu-id="c3752-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-329">发件人的平均比特率。</span><span class="sxs-lookup"><span data-stu-id="c3752-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-331">int</span><span class="sxs-lookup"><span data-stu-id="c3752-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-332">发件人使用的视频流的最大数量。</span><span class="sxs-lookup"><span data-stu-id="c3752-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="c3752-333">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-335">smallint</span><span class="sxs-lookup"><span data-stu-id="c3752-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="c3752-336">对外</span><span class="sxs-lookup"><span data-stu-id="c3752-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="c3752-337">接收器使用的视频代码。</span><span class="sxs-lookup"><span data-stu-id="c3752-337">Video codes used by the receiver.</span></span> <span data-ttu-id="c3752-338">有关详细信息，请参阅<a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表</a>。</span><span class="sxs-lookup"><span data-stu-id="c3752-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="c3752-339">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-341">int</span><span class="sxs-lookup"><span data-stu-id="c3752-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-342">接收器使用的分辨率宽度。</span><span class="sxs-lookup"><span data-stu-id="c3752-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="c3752-343">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-345">int</span><span class="sxs-lookup"><span data-stu-id="c3752-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-346">接收器使用的分辨率高度。</span><span class="sxs-lookup"><span data-stu-id="c3752-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="c3752-347">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-349">点数</span><span class="sxs-lookup"><span data-stu-id="c3752-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-350">接收器使用的平均视频帧速率。</span><span class="sxs-lookup"><span data-stu-id="c3752-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="c3752-351">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-353">int</span><span class="sxs-lookup"><span data-stu-id="c3752-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-354">接收器的最大比特率。</span><span class="sxs-lookup"><span data-stu-id="c3752-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="c3752-355">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-357">int</span><span class="sxs-lookup"><span data-stu-id="c3752-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-358">接收器的平均比特率。</span><span class="sxs-lookup"><span data-stu-id="c3752-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="c3752-359">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-361">int</span><span class="sxs-lookup"><span data-stu-id="c3752-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-362">接收器的最大视频流。</span><span class="sxs-lookup"><span data-stu-id="c3752-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="c3752-363">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-365">int</span><span class="sxs-lookup"><span data-stu-id="c3752-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-366">接收器的最小视频流。</span><span class="sxs-lookup"><span data-stu-id="c3752-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="c3752-367">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-369">int</span><span class="sxs-lookup"><span data-stu-id="c3752-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-370">接收器的视频模式（例如，库或单个流）。</span><span class="sxs-lookup"><span data-stu-id="c3752-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="c3752-371">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-373">点数</span><span class="sxs-lookup"><span data-stu-id="c3752-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-374">应用转发错误纠正率后的数据包丢失率。</span><span class="sxs-lookup"><span data-stu-id="c3752-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="c3752-375">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-377">点数</span><span class="sxs-lookup"><span data-stu-id="c3752-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-378">动态功能标志处于活动状态的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="c3752-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="c3752-379">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-381">char （9）</span><span class="sxs-lookup"><span data-stu-id="c3752-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-382">呼叫期间衡量的最低分辨率。</span><span class="sxs-lookup"><span data-stu-id="c3752-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="c3752-383">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-385">点数</span><span class="sxs-lookup"><span data-stu-id="c3752-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-386">低于低比特率阈值（每秒 70 kb）的呼叫百分比。</span><span class="sxs-lookup"><span data-stu-id="c3752-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="c3752-387">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-389">点数</span><span class="sxs-lookup"><span data-stu-id="c3752-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-390">呼叫百分比低于低帧速率阈值（每秒7.5 帧，入站）。</span><span class="sxs-lookup"><span data-stu-id="c3752-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="c3752-391">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-393">点数</span><span class="sxs-lookup"><span data-stu-id="c3752-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-394">最低分辨率发生的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="c3752-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="c3752-395">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="c3752-396">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c3752-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-398">点数</span><span class="sxs-lookup"><span data-stu-id="c3752-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-399">以秒为单位的呼叫长度。</span><span class="sxs-lookup"><span data-stu-id="c3752-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="c3752-400">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c3752-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="c3752-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="c3752-402">位</span><span class="sxs-lookup"><span data-stu-id="c3752-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="c3752-403">指示是否已从多个调用中聚合数据。</span><span class="sxs-lookup"><span data-stu-id="c3752-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="c3752-404">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c3752-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

