---
title: Lync Server 2013： VideoStream 表
description: Lync Server 2013： VideoStream 表。
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
ms.openlocfilehash: 0d741478e1f6290685181bff471f143e41ce9ca1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567988"
---
# <a name="videostream-table-in-lync-server-2013"></a><span data-ttu-id="096da-103">Lync Server 2013 中的 VideoStream 表</span><span class="sxs-lookup"><span data-stu-id="096da-103">VideoStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="096da-104">_**上次修改的主题：** 2013-12-13_</span><span class="sxs-lookup"><span data-stu-id="096da-104">_**Topic Last Modified:** 2013-12-13_</span></span>

<span data-ttu-id="096da-105">每个记录代表一个视频流。</span><span class="sxs-lookup"><span data-stu-id="096da-105">Each record represents one video stream.</span></span> <span data-ttu-id="096da-106">一个视频媒体线路通常包含两个视频流。</span><span class="sxs-lookup"><span data-stu-id="096da-106">One video media line usually contains two video streams.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="096da-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="096da-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="096da-108"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="096da-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="096da-109"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="096da-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="096da-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="096da-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="096da-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="096da-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-112">datetime</span><span class="sxs-lookup"><span data-stu-id="096da-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="096da-113">主</span><span class="sxs-lookup"><span data-stu-id="096da-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="096da-114"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="096da-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="096da-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-116">int</span><span class="sxs-lookup"><span data-stu-id="096da-116">int</span></span></p></td>
<td><p><span data-ttu-id="096da-117">主</span><span class="sxs-lookup"><span data-stu-id="096da-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="096da-118"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表</a>引用 R。</span><span class="sxs-lookup"><span data-stu-id="096da-118">R Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="096da-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="096da-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="096da-121">主</span><span class="sxs-lookup"><span data-stu-id="096da-121">Primary</span></span></p></td>
<td><p><span data-ttu-id="096da-122"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="096da-122">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-123"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="096da-123"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-124">int</span><span class="sxs-lookup"><span data-stu-id="096da-124">int</span></span></p></td>
<td><p><span data-ttu-id="096da-125">主</span><span class="sxs-lookup"><span data-stu-id="096da-125">Primary</span></span></p></td>
<td><p><span data-ttu-id="096da-126">媒体行中的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="096da-126">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-127"><strong>VideoPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="096da-127"><strong>VideoPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-128">smallint</span><span class="sxs-lookup"><span data-stu-id="096da-128">smallint</span></span></p></td>
<td><p><span data-ttu-id="096da-129">外部、主</span><span class="sxs-lookup"><span data-stu-id="096da-129">Foreign, Primary</span></span></p></td>
<td><p><span data-ttu-id="096da-130">有效负载说明。</span><span class="sxs-lookup"><span data-stu-id="096da-130">Payload description.</span></span> <span data-ttu-id="096da-131">有关详细信息，请参阅 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中的 PayloadDescription 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="096da-131">See the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-132"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="096da-132"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-133">int</span><span class="sxs-lookup"><span data-stu-id="096da-133">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="096da-134">实时控制协议 (RTCP) 统计信息中的平均网络抖动。</span><span class="sxs-lookup"><span data-stu-id="096da-134">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="096da-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-136">int</span><span class="sxs-lookup"><span data-stu-id="096da-136">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="096da-137">视频会话过程中的最大网络抖动。</span><span class="sxs-lookup"><span data-stu-id="096da-137">Maximum network jitter during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-138"><strong>工程</strong></span><span class="sxs-lookup"><span data-stu-id="096da-138"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-139">int</span><span class="sxs-lookup"><span data-stu-id="096da-139">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="096da-140">RTCP 统计信息中的来回行程时间。</span><span class="sxs-lookup"><span data-stu-id="096da-140">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-141"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="096da-141"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-142">int</span><span class="sxs-lookup"><span data-stu-id="096da-142">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="096da-143">视频流的最长往返时间。</span><span class="sxs-lookup"><span data-stu-id="096da-143">Maximum round trip time for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-144"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="096da-144"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-145">十进制 (5、4) </span><span class="sxs-lookup"><span data-stu-id="096da-145">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="096da-146">呼叫期间的平均数据包丢失率。</span><span class="sxs-lookup"><span data-stu-id="096da-146">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-147"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="096da-147"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-148">十进制 (5、4) </span><span class="sxs-lookup"><span data-stu-id="096da-148">decimal(5,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="096da-149">呼叫期间观测到的数据包丢失最大值。</span><span class="sxs-lookup"><span data-stu-id="096da-149">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-150"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="096da-150"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-151">int</span><span class="sxs-lookup"><span data-stu-id="096da-151">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="096da-152">视频流的数据包计数（实时传输协议，RTP）。</span><span class="sxs-lookup"><span data-stu-id="096da-152">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-153"><strong>BandwidthEst</strong></span><span class="sxs-lookup"><span data-stu-id="096da-153"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-154">int</span><span class="sxs-lookup"><span data-stu-id="096da-154">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="096da-155">视频流的带宽估计。</span><span class="sxs-lookup"><span data-stu-id="096da-155">Bandwidth estimates for the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-156"><strong>VideoResolution</strong></span><span class="sxs-lookup"><span data-stu-id="096da-156"><strong>VideoResolution</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-157">char (9) </span><span class="sxs-lookup"><span data-stu-id="096da-157">char(9)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="096da-p103">视频的分辨率（像素宽乘以像素高）。报告为字符串。</span><span class="sxs-lookup"><span data-stu-id="096da-p103">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-160"><strong>VideoBitRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="096da-160"><strong>VideoBitRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-161">int</span><span class="sxs-lookup"><span data-stu-id="096da-161">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="096da-162">视频流的平均比特率。</span><span class="sxs-lookup"><span data-stu-id="096da-162">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-163"><strong>InboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="096da-163"><strong>InboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-164">十进制 (9、4) </span><span class="sxs-lookup"><span data-stu-id="096da-164">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="096da-165">收到的视频帧速率。</span><span class="sxs-lookup"><span data-stu-id="096da-165">The video frame rate received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-166"><strong>OutboundVideoFrameRateAvg</strong></span><span class="sxs-lookup"><span data-stu-id="096da-166"><strong>OutboundVideoFrameRateAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-167">十进制 (9、4) </span><span class="sxs-lookup"><span data-stu-id="096da-167">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="096da-168">发送的视频帧速率。</span><span class="sxs-lookup"><span data-stu-id="096da-168">The video frame rate sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-169"><strong>VideoBitRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="096da-169"><strong>VideoBitRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-170">int</span><span class="sxs-lookup"><span data-stu-id="096da-170">int</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="096da-171">视频会话期间的最大视频比特率。</span><span class="sxs-lookup"><span data-stu-id="096da-171">The maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-172"><strong>VideoFrameLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="096da-172"><strong>VideoFrameLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-173">十进制 (9、4) </span><span class="sxs-lookup"><span data-stu-id="096da-173">decimal(9,4)</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="096da-174">丢失的视频帧总数的百分比。</span><span class="sxs-lookup"><span data-stu-id="096da-174">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-175"><strong>VideoFEC</strong></span><span class="sxs-lookup"><span data-stu-id="096da-175"><strong>VideoFEC</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-176">位</span><span class="sxs-lookup"><span data-stu-id="096da-176">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="096da-177">不可用。</span><span class="sxs-lookup"><span data-stu-id="096da-177">Not available.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-178"><strong>VideoLocalFrameLossPercentageAvg</strong></span><span class="sxs-lookup"><span data-stu-id="096da-178"><strong>VideoLocalFrameLossPercentageAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-179">十进制 (9、4) </span><span class="sxs-lookup"><span data-stu-id="096da-179">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-180">丢失的视频帧总数的百分比。</span><span class="sxs-lookup"><span data-stu-id="096da-180">The percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-181"><strong>CIFQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="096da-181"><strong>CIFQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-182">tinyint</span><span class="sxs-lookup"><span data-stu-id="096da-182">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-183"> (CIF) 分辨率的常见交换格式的呼叫百分比。</span><span class="sxs-lookup"><span data-stu-id="096da-183">The percentage of the call that was at the Common Interchange Format (CIF) resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-184"><strong>VGAQualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="096da-184"><strong>VGAQualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-185">tinyint</span><span class="sxs-lookup"><span data-stu-id="096da-185">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-186">以 VGA 分辨率表示的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="096da-186">The percentage of the call that was at VGA resolution.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-187"><strong>HD720QualityRatio</strong></span><span class="sxs-lookup"><span data-stu-id="096da-187"><strong>HD720QualityRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-188">tinyint</span><span class="sxs-lookup"><span data-stu-id="096da-188">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-189">呼叫的百分比，以 HD720 的分辨率为依据。</span><span class="sxs-lookup"><span data-stu-id="096da-189">The percentage of the call that was at HD720 resolution.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-190"><strong>NoneDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="096da-190"><strong>NoneDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-191">tinyint</span><span class="sxs-lookup"><span data-stu-id="096da-191">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-192">不放置帧的呼叫持续时间百分比。</span><span class="sxs-lookup"><span data-stu-id="096da-192">Percentage of call duration with no frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-193"><strong>BDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="096da-193"><strong>BDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-194">tinyint</span><span class="sxs-lookup"><span data-stu-id="096da-194">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-195">B 帧删除的呼叫持续时间百分比。</span><span class="sxs-lookup"><span data-stu-id="096da-195">Percentage of call duration with B frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-196"><strong>BPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="096da-196"><strong>BPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-197">tinyint</span><span class="sxs-lookup"><span data-stu-id="096da-197">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-198">具有 BP 框架丢弃的呼叫持续时间百分比。</span><span class="sxs-lookup"><span data-stu-id="096da-198">Percentage of call duration with BP frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-199"><strong>BPSPDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="096da-199"><strong>BPSPDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-200">tinyint</span><span class="sxs-lookup"><span data-stu-id="096da-200">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-201">带有 BPSP 框架丢弃的呼叫持续时间的百分比。</span><span class="sxs-lookup"><span data-stu-id="096da-201">Percentage of call duration with BPSP frame drop.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-202"><strong>BPSPIDropRatio</strong></span><span class="sxs-lookup"><span data-stu-id="096da-202"><strong>BPSPIDropRatio</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="096da-203">tinyint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-204">带有 BPSPI 框架丢弃的呼叫持续时间的百分比。</span><span class="sxs-lookup"><span data-stu-id="096da-204">Percentage of call duration with BPSPI frame drop.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-205"><strong>进货</strong></span><span class="sxs-lookup"><span data-stu-id="096da-205"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-206">位</span><span class="sxs-lookup"><span data-stu-id="096da-206">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="096da-207">接收接收器端的数据流数据。</span><span class="sxs-lookup"><span data-stu-id="096da-207">Stream data on receiver side is received.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-208"><strong>出站</strong></span><span class="sxs-lookup"><span data-stu-id="096da-208"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-209">位</span><span class="sxs-lookup"><span data-stu-id="096da-209">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="096da-210">接收发件人端上的数据流数据。</span><span class="sxs-lookup"><span data-stu-id="096da-210">Stream data on sender side is received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-211"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="096da-211"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-212">位</span><span class="sxs-lookup"><span data-stu-id="096da-212">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="096da-213">1 表示流方向是从呼叫者到被叫方。</span><span class="sxs-lookup"><span data-stu-id="096da-213">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="096da-214">0 表示流方向是从被叫方到呼叫者。</span><span class="sxs-lookup"><span data-stu-id="096da-214">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-215"><strong>LossCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="096da-215"><strong>LossCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-216">float</span><span class="sxs-lookup"><span data-stu-id="096da-216">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-217">指示呼叫处于丢失拥塞状态的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="096da-217">Indicates the percentage of the time when the call was in a loss congestion state.</span></span></p>
<p><span data-ttu-id="096da-218">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-218">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-219"><strong>DelayCongestionPercent</strong></span><span class="sxs-lookup"><span data-stu-id="096da-219"><strong>DelayCongestionPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-220">float</span><span class="sxs-lookup"><span data-stu-id="096da-220">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-221">指示因网络数据包的延迟到达而导致拥塞的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="096da-221">Indicates the percentage of the call during which congestion was caused by the delayed arrival of network packets.</span></span></p>
<p><span data-ttu-id="096da-222">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-222">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-223"><strong>ContentionDetectedPercent</strong></span><span class="sxs-lookup"><span data-stu-id="096da-223"><strong>ContentionDetectedPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-224">float</span><span class="sxs-lookup"><span data-stu-id="096da-224">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-225">指示呼叫竞争网络资源的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="096da-225">Indicates the percentage of the time when the call was competing for network resources.</span></span></p>
<p><span data-ttu-id="096da-226">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-226">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-227"><strong>BandwidthEstMin</strong></span><span class="sxs-lookup"><span data-stu-id="096da-227"><strong>BandwidthEstMin</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-228">int</span><span class="sxs-lookup"><span data-stu-id="096da-228">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-229">在呼叫过程中测量的最小带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="096da-229">Minimum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="096da-230">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-230">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-231"><strong>BandwidthEstMax</strong></span><span class="sxs-lookup"><span data-stu-id="096da-231"><strong>BandwidthEstMax</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-232">int</span><span class="sxs-lookup"><span data-stu-id="096da-232">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-233">在呼叫过程中测量的最大带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="096da-233">Maximum amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="096da-234">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-234">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-235"><strong>BandwidthEstStdDev</strong></span><span class="sxs-lookup"><span data-stu-id="096da-235"><strong>BandwidthEstStdDev</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-236">int</span><span class="sxs-lookup"><span data-stu-id="096da-236">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-237">在呼叫过程中测量的带宽估计的标准偏差。</span><span class="sxs-lookup"><span data-stu-id="096da-237">Standard deviation of the bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="096da-238">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-238">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-239"><strong>BandwidthEstAvge</strong></span><span class="sxs-lookup"><span data-stu-id="096da-239"><strong>BandwidthEstAvge</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-240">int</span><span class="sxs-lookup"><span data-stu-id="096da-240">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-241">呼叫期间衡量的平均带宽估计量。</span><span class="sxs-lookup"><span data-stu-id="096da-241">Average amount of bandwidth estimation measured during the call.</span></span></p>
<p><span data-ttu-id="096da-242">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-242">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-243"><strong>LowBandwidthForMultiview</strong></span><span class="sxs-lookup"><span data-stu-id="096da-243"><strong>LowBandwidthForMultiview</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-244">float</span><span class="sxs-lookup"><span data-stu-id="096da-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-245">终结点确定网络连接无法支持多种显示视频的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="096da-245">Percentage of the call where the endpoint determined that the network connection could not support multiview video.</span></span></p>
<p><span data-ttu-id="096da-246">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-246">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-247"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="096da-247"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-248">float</span><span class="sxs-lookup"><span data-stu-id="096da-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-p104">单向延迟的总量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="096da-p104">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="096da-251">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-251">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-252"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="096da-252"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-253">float</span><span class="sxs-lookup"><span data-stu-id="096da-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-p105">单向延迟的平均量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="096da-p105">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="096da-256">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-256">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-257"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="096da-257"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-258">float</span><span class="sxs-lookup"><span data-stu-id="096da-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-p106">单向延迟的最大量。相对单向延迟用于度量客户端和服务器之间的延迟。</span><span class="sxs-lookup"><span data-stu-id="096da-p106">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p>
<p><span data-ttu-id="096da-261">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-261">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-262"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="096da-262"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-263">int</span><span class="sxs-lookup"><span data-stu-id="096da-263">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-p107">单向突发总发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="096da-p107">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="096da-267">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-267">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-268"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="096da-268"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-269">int</span><span class="sxs-lookup"><span data-stu-id="096da-269">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-p108">单向突发总密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="096da-p108">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="096da-273">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-273">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-274"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="096da-274"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-275">float</span><span class="sxs-lookup"><span data-stu-id="096da-275">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-p109">单向突发总持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="096da-p109">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="096da-279">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-279">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-280"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="096da-280"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-281">int</span><span class="sxs-lookup"><span data-stu-id="096da-281">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-p110">单向间隙总发生次数。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="096da-p110">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="096da-285">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-285">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-286"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="096da-286"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-287">float</span><span class="sxs-lookup"><span data-stu-id="096da-287">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-p111">单向间隙总密度。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="096da-p111">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="096da-291">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-291">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-292"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="096da-292"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-293">float</span><span class="sxs-lookup"><span data-stu-id="096da-293">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-p112">单向间隙总持续时间。“突发”传输是指数据流以不可预知的突发方式进行的传输（与稳定流相反）；间隙是指各个突发之间的延迟。此指标用于度量客户端和服务器之间的数据流。</span><span class="sxs-lookup"><span data-stu-id="096da-p112">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p>
<p><span data-ttu-id="096da-297">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-297">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-298"><strong>VideoPacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="096da-298"><strong>VideoPacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-299">十进制 (9、4) </span><span class="sxs-lookup"><span data-stu-id="096da-299">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-300">视频数据包丢失的比特率。</span><span class="sxs-lookup"><span data-stu-id="096da-300">Rate at which video packets were lost.</span></span></p>
<p><span data-ttu-id="096da-301">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-301">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-302"><strong>VideoAllocateBWAvg</strong></span><span class="sxs-lookup"><span data-stu-id="096da-302"><strong>VideoAllocateBWAvg</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-303">int</span><span class="sxs-lookup"><span data-stu-id="096da-303">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-304">为视频分配的平均带宽量。</span><span class="sxs-lookup"><span data-stu-id="096da-304">Average amount of bandwidth allocated for video.</span></span></p>
<p><span data-ttu-id="096da-305">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-305">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-306"><strong>SendCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="096da-306"><strong>SendCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-307">smallint</span><span class="sxs-lookup"><span data-stu-id="096da-307">smallint</span></span></p></td>
<td><p><span data-ttu-id="096da-308">对外</span><span class="sxs-lookup"><span data-stu-id="096da-308">Foreign</span></span></p></td>
<td><p><span data-ttu-id="096da-309">发件人使用的视频编解码器类型。</span><span class="sxs-lookup"><span data-stu-id="096da-309">Type of video codecs used by the sender.</span></span> <span data-ttu-id="096da-310">有关详细信息，请参阅 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="096da-310">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="096da-311">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-311">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-312"><strong>SendResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="096da-312"><strong>SendResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-313">int</span><span class="sxs-lookup"><span data-stu-id="096da-313">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-314">发件人使用的分辨率宽度。</span><span class="sxs-lookup"><span data-stu-id="096da-314">Resolution width used by the sender.</span></span></p>
<p><span data-ttu-id="096da-315">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-315">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-316"><strong>SendResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="096da-316"><strong>SendResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-317">int</span><span class="sxs-lookup"><span data-stu-id="096da-317">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-318">发件人使用的分辨率高度。</span><span class="sxs-lookup"><span data-stu-id="096da-318">Resolution height used by the sender.</span></span></p>
<p><span data-ttu-id="096da-319">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-319">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-320"><strong>SendFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="096da-320"><strong>SendFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-321">float</span><span class="sxs-lookup"><span data-stu-id="096da-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-322">发件人使用的平均视频帧速率传输。</span><span class="sxs-lookup"><span data-stu-id="096da-322">Average video frame rate transmission used by the sender.</span></span></p>
<p><span data-ttu-id="096da-323">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-323">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-324"><strong>SendBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="096da-324"><strong>SendBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-325">int</span><span class="sxs-lookup"><span data-stu-id="096da-325">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-326">发件人的最大比特率。</span><span class="sxs-lookup"><span data-stu-id="096da-326">Maximum bit rate for the sender.</span></span></p>
<p><span data-ttu-id="096da-327">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-327">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-328"><strong>SendBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="096da-328"><strong>SendBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-329">int</span><span class="sxs-lookup"><span data-stu-id="096da-329">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-330">发件人的平均比特率。</span><span class="sxs-lookup"><span data-stu-id="096da-330">Average bit rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-331"><strong>SendVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="096da-331"><strong>SendVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-332">int</span><span class="sxs-lookup"><span data-stu-id="096da-332">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-333">发件人使用的视频流的最大数量。</span><span class="sxs-lookup"><span data-stu-id="096da-333">Maximum number of video streams used by the sender.</span></span></p>
<p><span data-ttu-id="096da-334">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-334">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-335"><strong>RecvCodecTypes</strong></span><span class="sxs-lookup"><span data-stu-id="096da-335"><strong>RecvCodecTypes</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-336">smallint</span><span class="sxs-lookup"><span data-stu-id="096da-336">smallint</span></span></p></td>
<td><p><span data-ttu-id="096da-337">对外</span><span class="sxs-lookup"><span data-stu-id="096da-337">Foreign</span></span></p></td>
<td><p><span data-ttu-id="096da-338">接收器使用的视频代码。</span><span class="sxs-lookup"><span data-stu-id="096da-338">Video codes used by the receiver.</span></span> <span data-ttu-id="096da-339">有关详细信息，请参阅 <a href="lync-server-2013-codecdescription-table.md">Lync Server 2013 中的 CodecDescription 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="096da-339">See the <a href="lync-server-2013-codecdescription-table.md">CodecDescription table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="096da-340">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-340">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-341"><strong>RecvResolutionWidth</strong></span><span class="sxs-lookup"><span data-stu-id="096da-341"><strong>RecvResolutionWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-342">int</span><span class="sxs-lookup"><span data-stu-id="096da-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-343">接收器使用的分辨率宽度。</span><span class="sxs-lookup"><span data-stu-id="096da-343">Resolution width used by the receiver.</span></span></p>
<p><span data-ttu-id="096da-344">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-344">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-345"><strong>RecvResolutionHeight</strong></span><span class="sxs-lookup"><span data-stu-id="096da-345"><strong>RecvResolutionHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-346">int</span><span class="sxs-lookup"><span data-stu-id="096da-346">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-347">接收器使用的分辨率高度。</span><span class="sxs-lookup"><span data-stu-id="096da-347">Resolution height used by the receiver.</span></span></p>
<p><span data-ttu-id="096da-348">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-348">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-349"><strong>RecvFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="096da-349"><strong>RecvFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-350">float</span><span class="sxs-lookup"><span data-stu-id="096da-350">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-351">接收器使用的平均视频帧速率。</span><span class="sxs-lookup"><span data-stu-id="096da-351">Average video frame rate used by the receiver.</span></span></p>
<p><span data-ttu-id="096da-352">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-352">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-353"><strong>RecvBitRateMaximum</strong></span><span class="sxs-lookup"><span data-stu-id="096da-353"><strong>RecvBitRateMaximum</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-354">int</span><span class="sxs-lookup"><span data-stu-id="096da-354">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-355">接收器的最大比特率。</span><span class="sxs-lookup"><span data-stu-id="096da-355">Maximum bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="096da-356">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-356">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-357"><strong>RecvBitRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="096da-357"><strong>RecvBitRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-358">int</span><span class="sxs-lookup"><span data-stu-id="096da-358">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-359">接收器的平均比特率。</span><span class="sxs-lookup"><span data-stu-id="096da-359">Average bit rate for the receiver.</span></span></p>
<p><span data-ttu-id="096da-360">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-360">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-361"><strong>RecvVideoStreamsMax</strong></span><span class="sxs-lookup"><span data-stu-id="096da-361"><strong>RecvVideoStreamsMax</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-362">int</span><span class="sxs-lookup"><span data-stu-id="096da-362">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-363">接收器的最大视频流。</span><span class="sxs-lookup"><span data-stu-id="096da-363">Maximum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="096da-364">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-364">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-365"><strong>RecvVideoStreamsMin</strong></span><span class="sxs-lookup"><span data-stu-id="096da-365"><strong>RecvVideoStreamsMin</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-366">int</span><span class="sxs-lookup"><span data-stu-id="096da-366">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-367">接收器的最小视频流。</span><span class="sxs-lookup"><span data-stu-id="096da-367">Minimum video streams for the receiver.</span></span></p>
<p><span data-ttu-id="096da-368">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-368">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-369"><strong>RecvVideoStreamsMode</strong></span><span class="sxs-lookup"><span data-stu-id="096da-369"><strong>RecvVideoStreamsMode</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-370">int</span><span class="sxs-lookup"><span data-stu-id="096da-370">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-371">视频模式 (例如，收件人的库或单数据流) 。</span><span class="sxs-lookup"><span data-stu-id="096da-371">Video mode (for example, gallery or single stream) for the receiver.</span></span></p>
<p><span data-ttu-id="096da-372">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-372">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-373"><strong>VideoPostFECPLR</strong></span><span class="sxs-lookup"><span data-stu-id="096da-373"><strong>VideoPostFECPLR</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-374">float</span><span class="sxs-lookup"><span data-stu-id="096da-374">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-375">应用转发错误纠正率后的数据包丢失率。</span><span class="sxs-lookup"><span data-stu-id="096da-375">Packet loss rate after forward error correction has been applied.</span></span></p>
<p><span data-ttu-id="096da-376">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-376">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-377"><strong>DynamicCapabilityPercent</strong></span><span class="sxs-lookup"><span data-stu-id="096da-377"><strong>DynamicCapabilityPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-378">float</span><span class="sxs-lookup"><span data-stu-id="096da-378">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-379">动态功能标志处于活动状态的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="096da-379">Percentage of time that the dynamic capability flag was active.</span></span></p>
<p><span data-ttu-id="096da-380">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-380">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-381"><strong>ResolutionMin</strong></span><span class="sxs-lookup"><span data-stu-id="096da-381"><strong>ResolutionMin</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-382">char (9) </span><span class="sxs-lookup"><span data-stu-id="096da-382">char(9)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-383">呼叫期间衡量的最低分辨率。</span><span class="sxs-lookup"><span data-stu-id="096da-383">Minimum resolution measured during the call.</span></span></p>
<p><span data-ttu-id="096da-384">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-384">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-385"><strong>LowBitRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="096da-385"><strong>LowBitRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-386">float</span><span class="sxs-lookup"><span data-stu-id="096da-386">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-387">低于低比特率阈值的呼叫百分比 (每秒 70 kbps) 。</span><span class="sxs-lookup"><span data-stu-id="096da-387">Percentage of the call below the low bit rate threshold (70 kilobits per second).</span></span></p>
<p><span data-ttu-id="096da-388">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-388">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-389"><strong>LowFrameRateCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="096da-389"><strong>LowFrameRateCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-390">float</span><span class="sxs-lookup"><span data-stu-id="096da-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-391">呼叫低于低帧速率阈值的百分比 (每秒7.5 帧，入站) 。</span><span class="sxs-lookup"><span data-stu-id="096da-391">Percentage of the call below the low frame rate threshold (7.5 frames per second, inbound).</span></span></p>
<p><span data-ttu-id="096da-392">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-392">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-393"><strong>LowResolutionCallPercent</strong></span><span class="sxs-lookup"><span data-stu-id="096da-393"><strong>LowResolutionCallPercent</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-394">float</span><span class="sxs-lookup"><span data-stu-id="096da-394">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-395">最低分辨率发生的呼叫的百分比。</span><span class="sxs-lookup"><span data-stu-id="096da-395">Percentage of the call that occurred at the lowest resolution.</span></span></p>
<p><span data-ttu-id="096da-396">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-396">This column was introduced in Microsoft Lync Server 2013.</span></span></p>
<p><span data-ttu-id="096da-397">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-397">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="096da-398"><strong>DurationSeconds</strong></span><span class="sxs-lookup"><span data-stu-id="096da-398"><strong>DurationSeconds</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-399">float</span><span class="sxs-lookup"><span data-stu-id="096da-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-400">以秒为单位的呼叫长度。</span><span class="sxs-lookup"><span data-stu-id="096da-400">Length of the call in seconds.</span></span></p>
<p><span data-ttu-id="096da-401">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-401">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="096da-402"><strong>IsAggregatedData</strong></span><span class="sxs-lookup"><span data-stu-id="096da-402"><strong>IsAggregatedData</strong></span></span></p></td>
<td><p><span data-ttu-id="096da-403">位</span><span class="sxs-lookup"><span data-stu-id="096da-403">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="096da-404">指示是否已从多个调用中聚合数据。</span><span class="sxs-lookup"><span data-stu-id="096da-404">Indicates whether the data has been aggregated from multiple calls.</span></span></p>
<p><span data-ttu-id="096da-405">本专栏是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="096da-405">This column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

