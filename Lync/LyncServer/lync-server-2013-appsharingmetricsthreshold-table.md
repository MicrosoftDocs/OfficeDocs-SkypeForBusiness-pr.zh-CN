---
title: Lync Server 2013： AppSharingMetricsThreshold 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7e247f83b00d226024f9fc671f2d744f1ee7fdf0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="1eff7-102">Lync Server 2013 中的 AppSharingMetricsThreshold 表</span><span class="sxs-lookup"><span data-stu-id="1eff7-102">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1eff7-103">_**主题上次修改时间：** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="1eff7-103">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="1eff7-104">AppSharingMetricsThreshold 表包含与应用程序共享一起使用的体验质量指标的最佳值和可接受值。</span><span class="sxs-lookup"><span data-stu-id="1eff7-104">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span> <span data-ttu-id="1eff7-105">这些阈值用于确定应用程序共享体验是否应归类为较差。</span><span class="sxs-lookup"><span data-stu-id="1eff7-105">These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="1eff7-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1eff7-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1eff7-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="1eff7-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1eff7-108"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="1eff7-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1eff7-109"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="1eff7-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1eff7-110"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="1eff7-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1eff7-111"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="1eff7-111"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="1eff7-112">int</span><span class="sxs-lookup"><span data-stu-id="1eff7-112">int</span></span></p></td>
<td><p><span data-ttu-id="1eff7-113">Primary</span><span class="sxs-lookup"><span data-stu-id="1eff7-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="1eff7-114">所发出通话的类型。</span><span class="sxs-lookup"><span data-stu-id="1eff7-114">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eff7-115"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="1eff7-115"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1eff7-116">int</span><span class="sxs-lookup"><span data-stu-id="1eff7-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1eff7-117">应用程序共享的最佳带宽限制。</span><span class="sxs-lookup"><span data-stu-id="1eff7-117">Optimal bandwidth limitation for application sharing.</span></span> <span data-ttu-id="1eff7-118">默认值为1000000。</span><span class="sxs-lookup"><span data-stu-id="1eff7-118">The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eff7-119"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="1eff7-119"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1eff7-120">int</span><span class="sxs-lookup"><span data-stu-id="1eff7-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1eff7-121">应用程序共享的可接受带宽限制。</span><span class="sxs-lookup"><span data-stu-id="1eff7-121">Acceptable bandwidth limitation for application sharing.</span></span> <span data-ttu-id="1eff7-122">默认值为500000。</span><span class="sxs-lookup"><span data-stu-id="1eff7-122">The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eff7-123"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="1eff7-123"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1eff7-124">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="1eff7-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1eff7-125">用于对应用程序共享质量进行分类的 "损坏" 图块的最佳百分比费率。</span><span class="sxs-lookup"><span data-stu-id="1eff7-125">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="1eff7-126">此值表示来自共享者的未到达查看者的内容百分比。</span><span class="sxs-lookup"><span data-stu-id="1eff7-126">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="1eff7-127">当共享者丢弃来自图形源或 ASMCU 磁贴的磁贴时，可能会放弃内容（或损坏）。</span><span class="sxs-lookup"><span data-stu-id="1eff7-127">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="1eff7-128">默认值为11%。</span><span class="sxs-lookup"><span data-stu-id="1eff7-128">The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eff7-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="1eff7-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1eff7-130">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="1eff7-130">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1eff7-131">用于对应用程序共享质量进行分类的 "损坏" 图块的 cceptable 百分比费率。</span><span class="sxs-lookup"><span data-stu-id="1eff7-131">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="1eff7-132">此值表示来自共享者的未到达查看者的内容百分比。</span><span class="sxs-lookup"><span data-stu-id="1eff7-132">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="1eff7-133">当共享者丢弃来自图形源或 ASMCU 磁贴的磁贴时，可能会放弃内容（或损坏）。</span><span class="sxs-lookup"><span data-stu-id="1eff7-133">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="1eff7-134">默认值为36%。</span><span class="sxs-lookup"><span data-stu-id="1eff7-134">The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eff7-135"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="1eff7-135"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1eff7-136">int</span><span class="sxs-lookup"><span data-stu-id="1eff7-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1eff7-137">Microsoft Lync Server 2013 中不使用此列。</span><span class="sxs-lookup"><span data-stu-id="1eff7-137">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eff7-138"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="1eff7-138"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1eff7-139">int</span><span class="sxs-lookup"><span data-stu-id="1eff7-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1eff7-140">Microsoft Lync Server 2013 中不使用此列。</span><span class="sxs-lookup"><span data-stu-id="1eff7-140">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eff7-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="1eff7-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1eff7-142">float</span><span class="sxs-lookup"><span data-stu-id="1eff7-142">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1eff7-143">Microsoft Lync Server 2013 中不使用此列。</span><span class="sxs-lookup"><span data-stu-id="1eff7-143">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eff7-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="1eff7-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1eff7-145">float</span><span class="sxs-lookup"><span data-stu-id="1eff7-145">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1eff7-146">Microsoft Lync Server 2013 中不使用此列。</span><span class="sxs-lookup"><span data-stu-id="1eff7-146">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eff7-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="1eff7-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1eff7-148">float</span><span class="sxs-lookup"><span data-stu-id="1eff7-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1eff7-149">Microsoft Lync Server 2013 中不使用此列。</span><span class="sxs-lookup"><span data-stu-id="1eff7-149">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eff7-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="1eff7-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1eff7-151">float</span><span class="sxs-lookup"><span data-stu-id="1eff7-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1eff7-152">Microsoft Lync Server 2013 中不使用此列。</span><span class="sxs-lookup"><span data-stu-id="1eff7-152">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eff7-153"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="1eff7-153"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1eff7-154">float</span><span class="sxs-lookup"><span data-stu-id="1eff7-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1eff7-155">应用程序共享中涉及的两个媒体终结点之间的相对单向延迟的最佳值。</span><span class="sxs-lookup"><span data-stu-id="1eff7-155">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="1eff7-156">这是单跃点延迟度量。</span><span class="sxs-lookup"><span data-stu-id="1eff7-156">This is a single-hop latency measure.</span></span> <span data-ttu-id="1eff7-157">默认值为1.0 秒。</span><span class="sxs-lookup"><span data-stu-id="1eff7-157">The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="1eff7-158">在 Microsoft Lync Server 2013 中引入了该列。</span><span class="sxs-lookup"><span data-stu-id="1eff7-158">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eff7-159"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="1eff7-159"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1eff7-160">float</span><span class="sxs-lookup"><span data-stu-id="1eff7-160">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1eff7-161">应用程序共享中涉及的两个媒体终结点之间的相对单向延迟的最佳值。</span><span class="sxs-lookup"><span data-stu-id="1eff7-161">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="1eff7-162">这是单跃点延迟度量。</span><span class="sxs-lookup"><span data-stu-id="1eff7-162">This is a single-hop latency measure.</span></span> <span data-ttu-id="1eff7-163">默认值为1.75 秒。</span><span class="sxs-lookup"><span data-stu-id="1eff7-163">The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="1eff7-164">在 Microsoft Lync Server 2013 中引入了该列。</span><span class="sxs-lookup"><span data-stu-id="1eff7-164">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1eff7-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="1eff7-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1eff7-166">float</span><span class="sxs-lookup"><span data-stu-id="1eff7-166">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1eff7-167">在查看会话期间作为会议服务器中的平均 RDP 磁贴处理延迟的最佳值。</span><span class="sxs-lookup"><span data-stu-id="1eff7-167">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="1eff7-168">滞后时间是在服务器上编码起始帧时的时间差（共享者或 MCU 取决于方案），并且在查看器上对同一开始帧进行解码。</span><span class="sxs-lookup"><span data-stu-id="1eff7-168">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="1eff7-169">高平均值反映了查看体验中的延迟较长。</span><span class="sxs-lookup"><span data-stu-id="1eff7-169">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="1eff7-170">过载的会议服务器可能会遇到更长的平均延迟。</span><span class="sxs-lookup"><span data-stu-id="1eff7-170">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="1eff7-171">默认值为200ms。</span><span class="sxs-lookup"><span data-stu-id="1eff7-171">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="1eff7-172">在 Microsoft Lync Server 2013 中引入了该列。</span><span class="sxs-lookup"><span data-stu-id="1eff7-172">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1eff7-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="1eff7-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1eff7-174">float</span><span class="sxs-lookup"><span data-stu-id="1eff7-174">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1eff7-175">在查看会话期间作为会议服务器中的平均 RDP 磁贴处理延迟的可接受值。</span><span class="sxs-lookup"><span data-stu-id="1eff7-175">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="1eff7-176">滞后时间是在服务器上编码起始帧时的时间差（共享者或 MCU 取决于方案），并且在查看器上对同一开始帧进行解码。</span><span class="sxs-lookup"><span data-stu-id="1eff7-176">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="1eff7-177">高平均值反映了查看体验中的延迟较长。</span><span class="sxs-lookup"><span data-stu-id="1eff7-177">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="1eff7-178">过载的会议服务器可能会遇到更长的平均延迟。</span><span class="sxs-lookup"><span data-stu-id="1eff7-178">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="1eff7-179">默认值为200ms。</span><span class="sxs-lookup"><span data-stu-id="1eff7-179">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="1eff7-180">在 Microsoft Lync Server 2013 中引入了该列。</span><span class="sxs-lookup"><span data-stu-id="1eff7-180">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

