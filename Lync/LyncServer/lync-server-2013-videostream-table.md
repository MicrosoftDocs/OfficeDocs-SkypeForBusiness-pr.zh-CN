---
title: Lync Server 2013：VideoStream 表
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
ms.openlocfilehash: 674d013faca3b43db04d2c5b4802103def83dbd8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757916"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="fdca7-102">Lync Server 2013 中的 VideoStream 表</span><span class="sxs-lookup"><span data-stu-id="fdca7-102">VideoStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdca7-103">_**主题上次修改时间：** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="fdca7-103">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="fdca7-104">每条记录表示一个视频流。</span><span class="sxs-lookup"><span data-stu-id="fdca7-104">Each record represents one video stream.</span></span> <span data-ttu-id="fdca7-105">一个视频媒体线通常包含两个视频流。</span><span class="sxs-lookup"><span data-stu-id="fdca7-105">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fdca7-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="fdca7-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="fdca7-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="fdca7-109"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-111">datetime</span><span class="sxs-lookup"><span data-stu-id="fdca7-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="fdca7-112">Primary</span><span class="sxs-lookup"><span data-stu-id="fdca7-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="fdca7-113">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="fdca7-113">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-115">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-115">int</span></span></p></td>
<td><p><span data-ttu-id="fdca7-116">Primary</span><span class="sxs-lookup"><span data-stu-id="fdca7-116">Primary</span></span></p></td>
<td><p><span data-ttu-id="fdca7-117"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表</a>引用的 R。</span><span class="sxs-lookup"><span data-stu-id="fdca7-117">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="fdca7-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="fdca7-120">Primary</span><span class="sxs-lookup"><span data-stu-id="fdca7-120">Primary</span></span></p></td>
<td><p><span data-ttu-id="fdca7-121">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="fdca7-121">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-122"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-122"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-123">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-123">int</span></span></p></td>
<td><p><span data-ttu-id="fdca7-124">Primary</span><span class="sxs-lookup"><span data-stu-id="fdca7-124">Primary</span></span></p></td>
<td><p><span data-ttu-id="fdca7-125">媒体行内的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="fdca7-125">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-126"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-126"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-127">smallint</span><span class="sxs-lookup"><span data-stu-id="fdca7-127">smallint</span></span></p></td>
<td><p><span data-ttu-id="fdca7-128">外部、主要</span><span class="sxs-lookup"><span data-stu-id="fdca7-128">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="fdca7-129">负载说明。</span><span class="sxs-lookup"><span data-stu-id="fdca7-129">Payload description.</span></span> <span data-ttu-id="fdca7-130">有关详细信息，请参阅<a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中的 PayloadDescription 表</a>。</span><span class="sxs-lookup"><span data-stu-id="fdca7-130">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-132">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-132">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdca7-133">实时控制协议（RTCP）统计信息的平均网络抖动。</span><span class="sxs-lookup"><span data-stu-id="fdca7-133">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-134"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-134"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-135">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-135">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdca7-136">视频会话期间的最大网络抖动。</span><span class="sxs-lookup"><span data-stu-id="fdca7-136">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-137"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-137"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-138">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-138">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdca7-139">从 RTCP 统计数据往返的时间。</span><span class="sxs-lookup"><span data-stu-id="fdca7-139">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-140"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-140"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-141">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-141">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdca7-142">视频流的最大往返行程时间。</span><span class="sxs-lookup"><span data-stu-id="fdca7-142">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-143"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-143"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-144">十进制（5，4）</span><span class="sxs-lookup"><span data-stu-id="fdca7-144">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdca7-145">通话期间平均数据包丢失速率。</span><span class="sxs-lookup"><span data-stu-id="fdca7-145">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-146"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-146"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-147">十进制（5，4）</span><span class="sxs-lookup"><span data-stu-id="fdca7-147">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdca7-148">通话过程中观察到的最大数据包丢失。</span><span class="sxs-lookup"><span data-stu-id="fdca7-148">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-149"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-149"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-150">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-150">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdca7-151">视频流的数据包计数（实时传输协议、RTP）。</span><span class="sxs-lookup"><span data-stu-id="fdca7-151">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-152"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-152"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-153">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-153">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdca7-154">视频流的带宽估计。</span><span class="sxs-lookup"><span data-stu-id="fdca7-154">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-155"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-155"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-156">char （9）</span><span class="sxs-lookup"><span data-stu-id="fdca7-156">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdca7-157">以像素为单位的视频分辨率（以像素为单位）乘以像素高度。</span><span class="sxs-lookup"><span data-stu-id="fdca7-157">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="fdca7-158">报告为字符串。</span><span class="sxs-lookup"><span data-stu-id="fdca7-158">Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-159"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-159"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-160">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-160">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdca7-161">视频流的平均比特率。</span><span class="sxs-lookup"><span data-stu-id="fdca7-161">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-162"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-162"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-163">十进制（9，4）</span><span class="sxs-lookup"><span data-stu-id="fdca7-163">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdca7-164">收到的视频帧速率。</span><span class="sxs-lookup"><span data-stu-id="fdca7-164">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-165"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-165"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-166">十进制（9，4）</span><span class="sxs-lookup"><span data-stu-id="fdca7-166">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdca7-167">已发送视频帧速率。</span><span class="sxs-lookup"><span data-stu-id="fdca7-167">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-168"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-168"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-169">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-169">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdca7-170">视频会话期间的最大视频比特率。</span><span class="sxs-lookup"><span data-stu-id="fdca7-170">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-171"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-171"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-172">十进制（9，4）</span><span class="sxs-lookup"><span data-stu-id="fdca7-172">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdca7-173">丢失的视频帧总数的百分比。</span><span class="sxs-lookup"><span data-stu-id="fdca7-173">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-174"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-174"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-175">bit</span><span class="sxs-lookup"><span data-stu-id="fdca7-175">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdca7-176">不可用。</span><span class="sxs-lookup"><span data-stu-id="fdca7-176">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-177"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-178">十进制（9，4）</span><span class="sxs-lookup"><span data-stu-id="fdca7-178">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-179">丢失的视频帧总数的百分比。</span><span class="sxs-lookup"><span data-stu-id="fdca7-179">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-180"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-180"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-181">tinyint</span><span class="sxs-lookup"><span data-stu-id="fdca7-181">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-182">以通用交换格式（CIF）分辨率表示的通话百分比。</span><span class="sxs-lookup"><span data-stu-id="fdca7-182">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-183"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-183"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-184">tinyint</span><span class="sxs-lookup"><span data-stu-id="fdca7-184">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-185">以 VGA 分辨率表示的通话百分比。</span><span class="sxs-lookup"><span data-stu-id="fdca7-185">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-186"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-186"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="fdca7-187">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-188">以 HD720 分辨率表示的通话百分比。</span><span class="sxs-lookup"><span data-stu-id="fdca7-188">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-189"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-189"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-190">tinyint</span><span class="sxs-lookup"><span data-stu-id="fdca7-190">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-191">不带帧丢弃的通话持续时间百分比。</span><span class="sxs-lookup"><span data-stu-id="fdca7-191">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-192"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-192"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-193">tinyint</span><span class="sxs-lookup"><span data-stu-id="fdca7-193">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-194">B 帧丢弃的通话持续时间百分比。</span><span class="sxs-lookup"><span data-stu-id="fdca7-194">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-195"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-195"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="fdca7-196">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-197">具有 BP 帧丢弃的通话持续百分比。</span><span class="sxs-lookup"><span data-stu-id="fdca7-197">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-198"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-198"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="fdca7-199">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-200">带有 BPSP 帧丢弃的通话持续时间百分比。</span><span class="sxs-lookup"><span data-stu-id="fdca7-200">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-201"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-201"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-202">tinyint</span><span class="sxs-lookup"><span data-stu-id="fdca7-202">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-203">带有 BPSPI 帧丢弃的通话持续时间百分比。</span><span class="sxs-lookup"><span data-stu-id="fdca7-203">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-204"><strong>封</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-204"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-205">bit</span><span class="sxs-lookup"><span data-stu-id="fdca7-205">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdca7-206">接收接收方的数据流数据。</span><span class="sxs-lookup"><span data-stu-id="fdca7-206">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-207"><strong>出站</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-207"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-208">bit</span><span class="sxs-lookup"><span data-stu-id="fdca7-208">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdca7-209">接收发件人端的数据流数据。</span><span class="sxs-lookup"><span data-stu-id="fdca7-209">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-210"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-210"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-211">bit</span><span class="sxs-lookup"><span data-stu-id="fdca7-211">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="fdca7-212">1表示流方向来自调用方的调用方。</span><span class="sxs-lookup"><span data-stu-id="fdca7-212">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="fdca7-213">0表示流方向来自被调用方的调用方。</span><span class="sxs-lookup"><span data-stu-id="fdca7-213">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-214"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-214"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-215">float</span><span class="sxs-lookup"><span data-stu-id="fdca7-215">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-216">指示通话处于损失拥塞状态的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="fdca7-216">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="fdca7-217">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-217">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-218"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-218"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-219">float</span><span class="sxs-lookup"><span data-stu-id="fdca7-219">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-220">指示由于网络数据包的延迟到达而导致的阻塞的调用百分比。</span><span class="sxs-lookup"><span data-stu-id="fdca7-220">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="fdca7-221">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-221">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-222"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-222"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-223">float</span><span class="sxs-lookup"><span data-stu-id="fdca7-223">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-224">表示呼叫竞争网络资源的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="fdca7-224">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="fdca7-225">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-225">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-226"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-226"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-227">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-227">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-228">在通话期间测量的最小带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="fdca7-228">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="fdca7-229">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-229">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-230"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-230"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-231">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-231">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-232">在通话期间测量的最大带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="fdca7-232">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="fdca7-233">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-233">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-234"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-234"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-235">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-235">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-236">在通话过程中测量的带宽估计的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="fdca7-236">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="fdca7-237">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-237">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-238"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-238"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-239">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-239">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-240">通话期间测量的平均估计带宽量。</span><span class="sxs-lookup"><span data-stu-id="fdca7-240">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="fdca7-241">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-241">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-242"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-242"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-243">float</span><span class="sxs-lookup"><span data-stu-id="fdca7-243">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-244">终结点确定网络连接无法支持多种显示视频的调用的百分比。</span><span class="sxs-lookup"><span data-stu-id="fdca7-244">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="fdca7-245">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-245">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-246"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-246"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-247">float</span><span class="sxs-lookup"><span data-stu-id="fdca7-247">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-248">单向延迟的总金额。</span><span class="sxs-lookup"><span data-stu-id="fdca7-248">Total amount of one-way latency.</span></span> <span data-ttu-id="fdca7-249">相对单向延迟测量客户端与服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="fdca7-249">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="fdca7-250">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-250">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-251"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-251"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-252">float</span><span class="sxs-lookup"><span data-stu-id="fdca7-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-253">单向延迟的平均量。</span><span class="sxs-lookup"><span data-stu-id="fdca7-253">Average amount of one-way latency.</span></span> <span data-ttu-id="fdca7-254">相对单向延迟测量客户端与服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="fdca7-254">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="fdca7-255">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-255">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-256"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-256"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-257">float</span><span class="sxs-lookup"><span data-stu-id="fdca7-257">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-258">单向延迟的最大值。</span><span class="sxs-lookup"><span data-stu-id="fdca7-258">Maximum amount of one-way latency.</span></span> <span data-ttu-id="fdca7-259">相对单向延迟测量客户端与服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="fdca7-259">Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="fdca7-260">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-260">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-261"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-261"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-262">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-262">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-263">总单向爆发次数。</span><span class="sxs-lookup"><span data-stu-id="fdca7-263">Total one-way burst occurrences.</span></span> <span data-ttu-id="fdca7-264">"Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，数据流处于不可预知的突发流量。</span><span class="sxs-lookup"><span data-stu-id="fdca7-264">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="fdca7-265">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="fdca7-265">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fdca7-266">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-266">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-267"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-267"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-268">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-268">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-269">总单向脉冲密度。</span><span class="sxs-lookup"><span data-stu-id="fdca7-269">Total one-way burst density.</span></span> <span data-ttu-id="fdca7-270">"Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，数据流处于不可预知的突发流量。</span><span class="sxs-lookup"><span data-stu-id="fdca7-270">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="fdca7-271">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="fdca7-271">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fdca7-272">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-272">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-273"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-273"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-274">float</span><span class="sxs-lookup"><span data-stu-id="fdca7-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-275">总的单向脉冲持续时间。</span><span class="sxs-lookup"><span data-stu-id="fdca7-275">Total one-way burst duration.</span></span> <span data-ttu-id="fdca7-276">"Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，数据流处于不可预知的突发流量。</span><span class="sxs-lookup"><span data-stu-id="fdca7-276">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="fdca7-277">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="fdca7-277">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fdca7-278">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-278">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-279"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-279"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-280">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-280">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-281">总的单向间隔发生次数。</span><span class="sxs-lookup"><span data-stu-id="fdca7-281">Total one-way gap occurrences.</span></span> <span data-ttu-id="fdca7-282">"Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，其数据流可预料的猝发。间隙表示这些猝发之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="fdca7-282">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="fdca7-283">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="fdca7-283">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fdca7-284">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-284">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-285"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-285"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-286">float</span><span class="sxs-lookup"><span data-stu-id="fdca7-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-287">总单向间距密度。</span><span class="sxs-lookup"><span data-stu-id="fdca7-287">Total one-way gap density.</span></span> <span data-ttu-id="fdca7-288">"Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，其数据流可预料的猝发。间隙表示这些猝发之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="fdca7-288">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="fdca7-289">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="fdca7-289">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fdca7-290">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-290">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-291"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-291"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-292">float</span><span class="sxs-lookup"><span data-stu-id="fdca7-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-293">总的单间隔持续时间。</span><span class="sxs-lookup"><span data-stu-id="fdca7-293">Total one-way gap duration.</span></span> <span data-ttu-id="fdca7-294">"Bursty" 传输是一种传输方式，其中的数据流与稳定流相反，其数据流可预料的猝发。间隙表示这些猝发之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="fdca7-294">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="fdca7-295">此指标测量客户端与服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="fdca7-295">This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="fdca7-296">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-296">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-297"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-297"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-298">十进制（9，4）</span><span class="sxs-lookup"><span data-stu-id="fdca7-298">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-299">视频数据包丢失的速率。</span><span class="sxs-lookup"><span data-stu-id="fdca7-299">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="fdca7-300">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-300">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-301"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-301"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-302">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-302">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-303">为视频分配的平均带宽量。</span><span class="sxs-lookup"><span data-stu-id="fdca7-303">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="fdca7-304">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-304">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-305"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-305"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-306">smallint</span><span class="sxs-lookup"><span data-stu-id="fdca7-306">smallint</span></span></p></td>
<td><p><span data-ttu-id="fdca7-307">外表</span><span class="sxs-lookup"><span data-stu-id="fdca7-307">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fdca7-308">发件人使用的视频编解码器类型。</span><span class="sxs-lookup"><span data-stu-id="fdca7-308">Type of video codecs used by the sender.</span></span> <span data-ttu-id="fdca7-309">有关详细信息，请参阅<a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表</a>。</span><span class="sxs-lookup"><span data-stu-id="fdca7-309">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="fdca7-310">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-310">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-311"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-311"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-312">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-312">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-313">发件人使用的分辨率宽度。</span><span class="sxs-lookup"><span data-stu-id="fdca7-313">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="fdca7-314">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-314">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-315"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-315"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-316">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-317">发件人使用的分辨率高度。</span><span class="sxs-lookup"><span data-stu-id="fdca7-317">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="fdca7-318">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-318">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-319"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-319"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-320">float</span><span class="sxs-lookup"><span data-stu-id="fdca7-320">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-321">发件人使用的平均视频帧速率传输。</span><span class="sxs-lookup"><span data-stu-id="fdca7-321">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="fdca7-322">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-322">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-323"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-323"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-324">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-325">发件人的最大比特率。</span><span class="sxs-lookup"><span data-stu-id="fdca7-325">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="fdca7-326">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-326">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-327"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-327"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-328">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-328">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-329">发件人的平均比特率。</span><span class="sxs-lookup"><span data-stu-id="fdca7-329">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-330"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-330"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-331">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-331">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-332">发件人使用的视频流的最大数量。</span><span class="sxs-lookup"><span data-stu-id="fdca7-332">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="fdca7-333">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-333">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-334"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-334"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-335">smallint</span><span class="sxs-lookup"><span data-stu-id="fdca7-335">smallint</span></span></p></td>
<td><p><span data-ttu-id="fdca7-336">外表</span><span class="sxs-lookup"><span data-stu-id="fdca7-336">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fdca7-337">接收方使用的视频代码。</span><span class="sxs-lookup"><span data-stu-id="fdca7-337">Video codes used by the receiver.</span></span> <span data-ttu-id="fdca7-338">有关详细信息，请参阅<a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表</a>。</span><span class="sxs-lookup"><span data-stu-id="fdca7-338">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="fdca7-339">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-339">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-340"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-340"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-341">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-341">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-342">接收器使用的分辨率宽度。</span><span class="sxs-lookup"><span data-stu-id="fdca7-342">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="fdca7-343">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-343">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-344"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-344"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-345">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-345">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-346">接收方使用的分辨率高度。</span><span class="sxs-lookup"><span data-stu-id="fdca7-346">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="fdca7-347">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-347">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-348"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-348"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-349">float</span><span class="sxs-lookup"><span data-stu-id="fdca7-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-350">接收方使用的平均视频帧速率。</span><span class="sxs-lookup"><span data-stu-id="fdca7-350">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="fdca7-351">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-351">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-352"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-352"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-353">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-353">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-354">接收方的最大比特率。</span><span class="sxs-lookup"><span data-stu-id="fdca7-354">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="fdca7-355">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-355">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-356"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-356"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-357">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-357">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-358">接收方的平均比特率。</span><span class="sxs-lookup"><span data-stu-id="fdca7-358">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="fdca7-359">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-359">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-360"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-360"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-361">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-361">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-362">接收方的最大视频流。</span><span class="sxs-lookup"><span data-stu-id="fdca7-362">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="fdca7-363">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-363">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-364"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-364"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-365">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-365">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-366">接收方的最小视频流。</span><span class="sxs-lookup"><span data-stu-id="fdca7-366">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="fdca7-367">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-367">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-368"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-368"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-369">int</span><span class="sxs-lookup"><span data-stu-id="fdca7-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-370">接收方的视频模式（例如，库或单流）。</span><span class="sxs-lookup"><span data-stu-id="fdca7-370">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="fdca7-371">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-371">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-372"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-372"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-373">float</span><span class="sxs-lookup"><span data-stu-id="fdca7-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-374">已应用转发纠错后的数据包丢失率。</span><span class="sxs-lookup"><span data-stu-id="fdca7-374">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="fdca7-375">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-375">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-376"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-376"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-377">float</span><span class="sxs-lookup"><span data-stu-id="fdca7-377">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-378">动态功能标志处于活动状态的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="fdca7-378">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="fdca7-379">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-379">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-380"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-380"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-381">char （9）</span><span class="sxs-lookup"><span data-stu-id="fdca7-381">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-382">通话过程中测量的最低分辨率。</span><span class="sxs-lookup"><span data-stu-id="fdca7-382">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="fdca7-383">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-383">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-384"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-384"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-385">float</span><span class="sxs-lookup"><span data-stu-id="fdca7-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-386">低于低比特率阈值的通话百分比（70千位/秒）。</span><span class="sxs-lookup"><span data-stu-id="fdca7-386">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="fdca7-387">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-387">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-388"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-388"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-389">float</span><span class="sxs-lookup"><span data-stu-id="fdca7-389">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-390">低于低帧速率阈值（每秒7.5 帧，入站）的通话百分比。</span><span class="sxs-lookup"><span data-stu-id="fdca7-390">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="fdca7-391">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-391">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-392"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-392"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-393">float</span><span class="sxs-lookup"><span data-stu-id="fdca7-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-394">以最低分辨率发生的通话的百分比。</span><span class="sxs-lookup"><span data-stu-id="fdca7-394">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="fdca7-395">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-395">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="fdca7-396">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdca7-397"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-397"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-398">float</span><span class="sxs-lookup"><span data-stu-id="fdca7-398">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-399">通话长度（以秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="fdca7-399">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="fdca7-400">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-400">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdca7-401"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="fdca7-401"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="fdca7-402">bit</span><span class="sxs-lookup"><span data-stu-id="fdca7-402">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fdca7-403">指示数据是否已从多个调用聚合。</span><span class="sxs-lookup"><span data-stu-id="fdca7-403">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="fdca7-404">此列已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="fdca7-404">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

