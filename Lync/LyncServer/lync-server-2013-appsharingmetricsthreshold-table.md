---
title: 'Lync Server 2013: AppSharingMetricsThreshold 表'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: AppSharingMetricsThreshold table
ms:assetid: 782cfab9-01a6-4843-aea1-28f47b0b51f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205018(v=OCS.15)
ms:contentKeyID: 48184556
ms.date: 12/09/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0f8dc1dac3dc7a9ec362473221d36191dd7dd0f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845978"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="1d7de-102">Lync Server 2013 中的 AppSharingMetricsThreshold 表</span><span class="sxs-lookup"><span data-stu-id="1d7de-102">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d7de-103">_**主题上次修改时间:** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="1d7de-103">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="1d7de-104">AppSharingMetricsThreshold 表包含与应用程序共享一起使用的体验质量指标的最佳值和可接受值。</span><span class="sxs-lookup"><span data-stu-id="1d7de-104">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing.</span></span> <span data-ttu-id="1d7de-105">这些阈值用于确定应用程序共享体验是否应归类为较差。</span><span class="sxs-lookup"><span data-stu-id="1d7de-105">These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="1d7de-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1d7de-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d7de-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="1d7de-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="1d7de-108"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="1d7de-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="1d7de-109"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="1d7de-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="1d7de-110"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="1d7de-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d7de-111"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="1d7de-111"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="1d7de-112">int</span><span class="sxs-lookup"><span data-stu-id="1d7de-112">int</span></span></p></td>
<td><p><span data-ttu-id="1d7de-113">Primary</span><span class="sxs-lookup"><span data-stu-id="1d7de-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="1d7de-114">所发出通话的类型。</span><span class="sxs-lookup"><span data-stu-id="1d7de-114">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d7de-115"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="1d7de-115"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1d7de-116">int</span><span class="sxs-lookup"><span data-stu-id="1d7de-116">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d7de-117">应用程序共享的最佳带宽限制。</span><span class="sxs-lookup"><span data-stu-id="1d7de-117">Optimal bandwidth limitation for application sharing.</span></span> <span data-ttu-id="1d7de-118">默认值为1000000。</span><span class="sxs-lookup"><span data-stu-id="1d7de-118">The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d7de-119"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="1d7de-119"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1d7de-120">int</span><span class="sxs-lookup"><span data-stu-id="1d7de-120">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d7de-121">应用程序共享的可接受带宽限制。</span><span class="sxs-lookup"><span data-stu-id="1d7de-121">Acceptable bandwidth limitation for application sharing.</span></span> <span data-ttu-id="1d7de-122">默认值为500000。</span><span class="sxs-lookup"><span data-stu-id="1d7de-122">The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d7de-123"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="1d7de-123"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1d7de-124">十进制 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="1d7de-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d7de-125">用于对应用程序共享质量进行分类的 "损坏" 图块的最佳百分比费率。</span><span class="sxs-lookup"><span data-stu-id="1d7de-125">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="1d7de-126">此值表示来自共享者的未到达查看者的内容百分比。</span><span class="sxs-lookup"><span data-stu-id="1d7de-126">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="1d7de-127">当共享者丢弃来自图形源或 ASMCU 磁贴的磁贴时, 可能会放弃内容 (或损坏)。</span><span class="sxs-lookup"><span data-stu-id="1d7de-127">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="1d7de-128">默认值为 11%。</span><span class="sxs-lookup"><span data-stu-id="1d7de-128">The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d7de-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="1d7de-129"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1d7de-130">十进制 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="1d7de-130">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d7de-131">用于对应用程序共享质量进行分类的 "损坏" 图块的 cceptable 百分比费率。</span><span class="sxs-lookup"><span data-stu-id="1d7de-131">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality.</span></span> <span data-ttu-id="1d7de-132">此值表示来自共享者的未到达查看者的内容百分比。</span><span class="sxs-lookup"><span data-stu-id="1d7de-132">This value is the percentage of the content from the sharer that did not reach the viewer.</span></span> <span data-ttu-id="1d7de-133">当共享者丢弃来自图形源或 ASMCU 磁贴的磁贴时, 可能会放弃内容 (或损坏)。</span><span class="sxs-lookup"><span data-stu-id="1d7de-133">Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively.</span></span> <span data-ttu-id="1d7de-134">默认值为 36%。</span><span class="sxs-lookup"><span data-stu-id="1d7de-134">The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d7de-135"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="1d7de-135"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1d7de-136">int</span><span class="sxs-lookup"><span data-stu-id="1d7de-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d7de-137">Microsoft Lync Server 2013 中不使用此列。</span><span class="sxs-lookup"><span data-stu-id="1d7de-137">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d7de-138"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="1d7de-138"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1d7de-139">int</span><span class="sxs-lookup"><span data-stu-id="1d7de-139">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d7de-140">Microsoft Lync Server 2013 中不使用此列。</span><span class="sxs-lookup"><span data-stu-id="1d7de-140">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d7de-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="1d7de-141"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1d7de-142">float</span><span class="sxs-lookup"><span data-stu-id="1d7de-142">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d7de-143">Microsoft Lync Server 2013 中不使用此列。</span><span class="sxs-lookup"><span data-stu-id="1d7de-143">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d7de-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="1d7de-144"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1d7de-145">float</span><span class="sxs-lookup"><span data-stu-id="1d7de-145">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d7de-146">Microsoft Lync Server 2013 中不使用此列。</span><span class="sxs-lookup"><span data-stu-id="1d7de-146">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d7de-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="1d7de-147"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1d7de-148">float</span><span class="sxs-lookup"><span data-stu-id="1d7de-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d7de-149">Microsoft Lync Server 2013 中不使用此列。</span><span class="sxs-lookup"><span data-stu-id="1d7de-149">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d7de-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="1d7de-150"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1d7de-151">float</span><span class="sxs-lookup"><span data-stu-id="1d7de-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d7de-152">Microsoft Lync Server 2013 中不使用此列。</span><span class="sxs-lookup"><span data-stu-id="1d7de-152">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d7de-153"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="1d7de-153"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1d7de-154">float</span><span class="sxs-lookup"><span data-stu-id="1d7de-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d7de-155">应用程序共享中涉及的两个媒体终结点之间的相对单向延迟的最佳值。</span><span class="sxs-lookup"><span data-stu-id="1d7de-155">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="1d7de-156">这是单跃点延迟度量。</span><span class="sxs-lookup"><span data-stu-id="1d7de-156">This is a single-hop latency measure.</span></span> <span data-ttu-id="1d7de-157">默认值为1.0 秒。</span><span class="sxs-lookup"><span data-stu-id="1d7de-157">The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="1d7de-158">在 Microsoft Lync Server 2013 中引入了该列。</span><span class="sxs-lookup"><span data-stu-id="1d7de-158">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d7de-159"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="1d7de-159"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1d7de-160">float</span><span class="sxs-lookup"><span data-stu-id="1d7de-160">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d7de-161">应用程序共享中涉及的两个媒体终结点之间的相对单向延迟的最佳值。</span><span class="sxs-lookup"><span data-stu-id="1d7de-161">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing.</span></span> <span data-ttu-id="1d7de-162">这是单跃点延迟度量。</span><span class="sxs-lookup"><span data-stu-id="1d7de-162">This is a single-hop latency measure.</span></span> <span data-ttu-id="1d7de-163">默认值为1.75 秒。</span><span class="sxs-lookup"><span data-stu-id="1d7de-163">The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="1d7de-164">在 Microsoft Lync Server 2013 中引入了该列。</span><span class="sxs-lookup"><span data-stu-id="1d7de-164">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d7de-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="1d7de-165"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="1d7de-166">float</span><span class="sxs-lookup"><span data-stu-id="1d7de-166">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d7de-167">在查看会话期间作为会议服务器中的平均 RDP 磁贴处理延迟的最佳值。</span><span class="sxs-lookup"><span data-stu-id="1d7de-167">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="1d7de-168">滞后时间是在服务器上编码起始帧时的时间差 (共享者或 MCU 取决于方案), 并且在查看器上对同一开始帧进行解码。</span><span class="sxs-lookup"><span data-stu-id="1d7de-168">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="1d7de-169">高平均值反映了查看体验中的延迟较长。</span><span class="sxs-lookup"><span data-stu-id="1d7de-169">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="1d7de-170">过载的会议服务器可能会遇到更长的平均延迟。</span><span class="sxs-lookup"><span data-stu-id="1d7de-170">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="1d7de-171">默认值为200ms。</span><span class="sxs-lookup"><span data-stu-id="1d7de-171">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="1d7de-172">在 Microsoft Lync Server 2013 中引入了该列。</span><span class="sxs-lookup"><span data-stu-id="1d7de-172">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d7de-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="1d7de-173"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="1d7de-174">float</span><span class="sxs-lookup"><span data-stu-id="1d7de-174">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1d7de-175">在查看会话期间作为会议服务器中的平均 RDP 磁贴处理延迟的可接受值。</span><span class="sxs-lookup"><span data-stu-id="1d7de-175">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="1d7de-176">滞后时间是在服务器上编码起始帧时的时间差 (共享者或 MCU 取决于方案), 并且在查看器上对同一开始帧进行解码。</span><span class="sxs-lookup"><span data-stu-id="1d7de-176">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="1d7de-177">高平均值反映了查看体验中的延迟较长。</span><span class="sxs-lookup"><span data-stu-id="1d7de-177">A high average reflects a longer delay in the viewing experience.</span></span> <span data-ttu-id="1d7de-178">过载的会议服务器可能会遇到更长的平均延迟。</span><span class="sxs-lookup"><span data-stu-id="1d7de-178">An overloaded conferencing server may experience higher average delays.</span></span> <span data-ttu-id="1d7de-179">默认值为200ms。</span><span class="sxs-lookup"><span data-stu-id="1d7de-179">The default value is 200ms.</span></span></p>
<p><span data-ttu-id="1d7de-180">在 Microsoft Lync Server 2013 中引入了该列。</span><span class="sxs-lookup"><span data-stu-id="1d7de-180">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

