---
title: Lync Server 2013：VideoStream 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoStream table
ms:assetid: 4275ede7-5467-4a97-b8c8-a4b00917bf32
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425928(v=OCS.15)
ms:contentKeyID: 48184014
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 98e0ad3f7c18032dd903d2f8d1d41428ccc12cf9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845369"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="f1f6b-102">Lync Server 2013 中的 VideoStream 表</span><span class="sxs-lookup"><span data-stu-id="f1f6b-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f1f6b-103">_**主题上次修改时间:** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="f1f6b-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="f1f6b-104">每条记录表示一个视频流。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-104">Each record represents one video stream.</span></span> <span data-ttu-id="f1f6b-105">一个视频媒体线通常包含两个视频流。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f1f6b-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f1f6b-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f1f6b-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f1f6b-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-111">datetime</span><span class="sxs-lookup"><span data-stu-id="f1f6b-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="f1f6b-112">Primary</span><span class="sxs-lookup"><span data-stu-id="f1f6b-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="f1f6b-113">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-115">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-115">int</span></span></p></td>
<td><p><span data-ttu-id="f1f6b-116">Primary</span><span class="sxs-lookup"><span data-stu-id="f1f6b-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="f1f6b-117"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表</a>引用的 R。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="f1f6b-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f1f6b-120">Primary</span><span class="sxs-lookup"><span data-stu-id="f1f6b-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="f1f6b-121">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-123">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-123">int</span></span></p></td>
<td><p><span data-ttu-id="f1f6b-124">Primary</span><span class="sxs-lookup"><span data-stu-id="f1f6b-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="f1f6b-125">媒体行内的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-127">smallint</span><span class="sxs-lookup"><span data-stu-id="f1f6b-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="f1f6b-128">外部、主要</span><span class="sxs-lookup"><span data-stu-id="f1f6b-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="f1f6b-129">负载说明。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-129">Payload description.</span></span> <span data-ttu-id="f1f6b-130">有关详细信息, 请参阅<a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中的 PayloadDescription 表</a>。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-132">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f1f6b-133">实时控制协议 (RTCP) 统计信息的平均网络抖动。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-135">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f1f6b-136">视频会话期间的最大网络抖动。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-137"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-138">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f1f6b-139">从 RTCP 统计数据往返的时间。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-141">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f1f6b-142">视频流的最大往返行程时间。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-144">十进制 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="f1f6b-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f1f6b-145">通话期间平均数据包丢失速率。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-147">十进制 (5, 4)</span><span class="sxs-lookup"><span data-stu-id="f1f6b-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f1f6b-148">通话过程中观察到的最大数据包丢失。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-150">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f1f6b-151">视频流的数据包计数 (实时传输协议、RTP)。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-152"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-153">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f1f6b-154">视频流的带宽估计。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-156">char (9)</span><span class="sxs-lookup"><span data-stu-id="f1f6b-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f1f6b-157">以像素为单位的视频分辨率 (以像素为单位) 乘以像素高度。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-157">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="f1f6b-158">报告为字符串。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-158">Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-160">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f1f6b-161">视频流的平均比特率。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-163">十进制 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f1f6b-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f1f6b-164">收到的视频帧速率。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-166">十进制 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f1f6b-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f1f6b-167">已发送视频帧速率。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-169">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f1f6b-170">视频会话期间的最大视频比特率。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-172">十进制 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f1f6b-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f1f6b-173">丢失的视频帧总数的百分比。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-175">bit</span><span class="sxs-lookup"><span data-stu-id="f1f6b-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f1f6b-176">不可用。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-178">十进制 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f1f6b-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-179">丢失的视频帧总数的百分比。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="f1f6b-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-182">以通用交换格式 (CIF) 分辨率表示的通话百分比。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="f1f6b-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-185">以 VGA 分辨率表示的通话百分比。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="f1f6b-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-188">以 HD720 分辨率表示的通话百分比。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="f1f6b-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-191">不带帧丢弃的通话持续时间百分比。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="f1f6b-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-194">B 帧丢弃的通话持续时间百分比。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="f1f6b-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-197">具有 BP 帧丢弃的通话持续百分比。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="f1f6b-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-200">带有 BPSP 帧丢弃的通话持续时间百分比。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="f1f6b-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-203">带有 BPSPI 帧丢弃的通话持续时间百分比。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-204"><strong>封</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-205">bit</span><span class="sxs-lookup"><span data-stu-id="f1f6b-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f1f6b-206">接收接收方的数据流数据。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-207"><strong>出站</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-208">bit</span><span class="sxs-lookup"><span data-stu-id="f1f6b-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f1f6b-209">接收发件人端的数据流数据。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-211">bit</span><span class="sxs-lookup"><span data-stu-id="f1f6b-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="f1f6b-212">1表示流方向来自调用方的调用方。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="f1f6b-213">0表示流方向来自被调用方的调用方。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-215">float</span><span class="sxs-lookup"><span data-stu-id="f1f6b-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-216">指示通话处于损失拥塞状态的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="f1f6b-217">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-219">float</span><span class="sxs-lookup"><span data-stu-id="f1f6b-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-220">指示由于网络数据包的延迟到达而导致的阻塞的调用百分比。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="f1f6b-221">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-223">float</span><span class="sxs-lookup"><span data-stu-id="f1f6b-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-224">表示呼叫竞争网络资源的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="f1f6b-225">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-227">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-228">在通话期间测量的最小带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f1f6b-229">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-231">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-232">在通话期间测量的最大带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f1f6b-233">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-235">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-236">在通话过程中测量的带宽估计的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f1f6b-237">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-239">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-240">通话期间测量的平均估计带宽量。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="f1f6b-241">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-243">float</span><span class="sxs-lookup"><span data-stu-id="f1f6b-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-244">终结点确定网络连接无法支持多种显示视频的调用的百分比。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="f1f6b-245">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-247">float</span><span class="sxs-lookup"><span data-stu-id="f1f6b-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-248">单向延迟的总金额。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-248">Total amount of one-way latency.</span></span> <span data-ttu-id="f1f6b-249">相对单向延迟测量客户端与服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-249">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f1f6b-250">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-252">float</span><span class="sxs-lookup"><span data-stu-id="f1f6b-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-253">单向延迟的平均量。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-253">Average amount of one-way latency.</span></span> <span data-ttu-id="f1f6b-254">相对单向延迟测量客户端与服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-254">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f1f6b-255">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-257">float</span><span class="sxs-lookup"><span data-stu-id="f1f6b-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-258">单向延迟的最大值。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-258">Maximum amount of one-way latency.</span></span> <span data-ttu-id="f1f6b-259">相对单向延迟测量客户端与服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-259">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="f1f6b-260">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-262">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-263">总单向爆发次数。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-263">Total one-way burst occurrences.</span></span> <span data-ttu-id="f1f6b-264">"Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 数据流处于不可预知的突发流量。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-264">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="f1f6b-265">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-265">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f1f6b-266">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-268">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-269">总单向脉冲密度。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-269">Total one-way burst density.</span></span> <span data-ttu-id="f1f6b-270">"Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 数据流处于不可预知的突发流量。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-270">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="f1f6b-271">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-271">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f1f6b-272">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-274">float</span><span class="sxs-lookup"><span data-stu-id="f1f6b-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-275">总的单向脉冲持续时间。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-275">Total one-way burst duration.</span></span> <span data-ttu-id="f1f6b-276">"Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 数据流处于不可预知的突发流量。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-276">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="f1f6b-277">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-277">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f1f6b-278">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-280">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-281">总的单向间隔发生次数。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-281">Total one-way gap occurrences.</span></span> <span data-ttu-id="f1f6b-282">"Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 其数据流可预料的猝发。间隙表示这些猝发之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-282">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="f1f6b-283">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-283">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f1f6b-284">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-286">float</span><span class="sxs-lookup"><span data-stu-id="f1f6b-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-287">总单向间距密度。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-287">Total one-way gap density.</span></span> <span data-ttu-id="f1f6b-288">"Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 其数据流可预料的猝发。间隙表示这些猝发之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-288">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="f1f6b-289">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-289">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f1f6b-290">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-292">float</span><span class="sxs-lookup"><span data-stu-id="f1f6b-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-293">总的单间隔持续时间。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-293">Total one-way gap duration.</span></span> <span data-ttu-id="f1f6b-294">"Bursty" 传输是一种传输方式, 其中的数据流与稳定流相反, 其数据流可预料的猝发。间隙表示这些猝发之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-294">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="f1f6b-295">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-295">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="f1f6b-296">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-298">十进制 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="f1f6b-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-299">视频数据包丢失的速率。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="f1f6b-300">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-302">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-303">为视频分配的平均带宽量。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="f1f6b-304">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-306">smallint</span><span class="sxs-lookup"><span data-stu-id="f1f6b-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="f1f6b-307">外表</span><span class="sxs-lookup"><span data-stu-id="f1f6b-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f1f6b-308">发件人使用的视频编解码器类型。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="f1f6b-309">有关详细信息, 请参阅<a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表</a>。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="f1f6b-310">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-312">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-313">发件人使用的分辨率宽度。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="f1f6b-314">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-316">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-317">发件人使用的分辨率高度。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="f1f6b-318">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-320">float</span><span class="sxs-lookup"><span data-stu-id="f1f6b-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-321">发件人使用的平均视频帧速率传输。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="f1f6b-322">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-324">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-325">发件人的最大比特率。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="f1f6b-326">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-328">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-329">发件人的平均比特率。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-331">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-332">发件人使用的视频流的最大数量。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="f1f6b-333">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-335">smallint</span><span class="sxs-lookup"><span data-stu-id="f1f6b-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="f1f6b-336">外表</span><span class="sxs-lookup"><span data-stu-id="f1f6b-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="f1f6b-337">接收方使用的视频代码。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-337">Video codes used by the receiver.</span></span> <span data-ttu-id="f1f6b-338">有关详细信息, 请参阅<a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表</a>。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="f1f6b-339">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-341">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-342">接收器使用的分辨率宽度。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="f1f6b-343">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-345">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-346">接收方使用的分辨率高度。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="f1f6b-347">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-349">float</span><span class="sxs-lookup"><span data-stu-id="f1f6b-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-350">接收方使用的平均视频帧速率。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="f1f6b-351">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-353">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-354">接收方的最大比特率。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="f1f6b-355">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-357">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-358">接收方的平均比特率。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="f1f6b-359">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-361">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-362">接收方的最大视频流。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="f1f6b-363">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-365">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-366">接收方的最小视频流。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="f1f6b-367">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-369">int</span><span class="sxs-lookup"><span data-stu-id="f1f6b-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-370">接收方的视频模式 (例如, 库或单流)。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="f1f6b-371">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-373">float</span><span class="sxs-lookup"><span data-stu-id="f1f6b-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-374">已应用转发纠错后的数据包丢失率。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="f1f6b-375">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-377">float</span><span class="sxs-lookup"><span data-stu-id="f1f6b-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-378">动态功能标志处于活动状态的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="f1f6b-379">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-381">char (9)</span><span class="sxs-lookup"><span data-stu-id="f1f6b-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-382">通话过程中测量的最低分辨率。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="f1f6b-383">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-385">float</span><span class="sxs-lookup"><span data-stu-id="f1f6b-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-386">低于低比特率阈值的通话百分比 (70 千位/秒)。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="f1f6b-387">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-389">float</span><span class="sxs-lookup"><span data-stu-id="f1f6b-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-390">低于低帧速率阈值 (每秒7.5 帧, 入站) 的通话百分比。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="f1f6b-391">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-393">float</span><span class="sxs-lookup"><span data-stu-id="f1f6b-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-394">以最低分辨率发生的通话的百分比。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="f1f6b-395">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="f1f6b-396">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f1f6b-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-398">float</span><span class="sxs-lookup"><span data-stu-id="f1f6b-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-399">通话长度 (以秒为单位)。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="f1f6b-400">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f1f6b-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="f1f6b-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="f1f6b-402">bit</span><span class="sxs-lookup"><span data-stu-id="f1f6b-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f1f6b-403">指示数据是否已从多个调用聚合。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="f1f6b-404">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="f1f6b-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

