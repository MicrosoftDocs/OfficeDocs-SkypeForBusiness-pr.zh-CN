---
title: Lync Server 2013： AppSharingMetricsThreshold 表
description: Lync Server 2013： AppSharingMetricsThreshold 表。
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
ms.openlocfilehash: 092c7d08026e6b736b81043a71b4ecaabc4d5f1b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546808"
---
# <a name="appsharingmetricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="9a2c5-103">Lync Server 2013 中的 AppSharingMetricsThreshold 表</span><span class="sxs-lookup"><span data-stu-id="9a2c5-103">AppSharingMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9a2c5-104">_**上次修改的主题：** 2015-12-08_</span><span class="sxs-lookup"><span data-stu-id="9a2c5-104">_**Topic Last Modified:** 2015-12-08_</span></span>

<span data-ttu-id="9a2c5-p101">AppSharingMetricsThreshold 表包含用于应用程序共享的用户体验质量指标的最佳值和可接受的值。这些阈值用于确定是否应将应用程序共享体验归类为质量欠佳。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-p101">The AppSharingMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with application sharing. These thresholds are used to determine if the application sharing experience should be classified as poor.</span></span>

<span data-ttu-id="9a2c5-107">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-107">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9a2c5-108"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="9a2c5-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="9a2c5-109"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="9a2c5-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="9a2c5-110"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="9a2c5-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="9a2c5-111"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="9a2c5-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9a2c5-112"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="9a2c5-112"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="9a2c5-113">int</span><span class="sxs-lookup"><span data-stu-id="9a2c5-113">int</span></span></p></td>
<td><p><span data-ttu-id="9a2c5-114">主</span><span class="sxs-lookup"><span data-stu-id="9a2c5-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="9a2c5-115">已发出的呼叫的类型。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-115">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a2c5-116"><strong>AppliedBandwidthLimitOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="9a2c5-116"><strong>AppliedBandwidthLimitOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="9a2c5-117">int</span><span class="sxs-lookup"><span data-stu-id="9a2c5-117">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a2c5-p102">应用程序共享的最佳带宽限制。默认值为 1000000。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-p102">Optimal bandwidth limitation for application sharing. The default value is 1000000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a2c5-120"><strong>AppliedBandwidthLimitAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="9a2c5-120"><strong>AppliedBandwidthLimitAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="9a2c5-121">int</span><span class="sxs-lookup"><span data-stu-id="9a2c5-121">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a2c5-p103">应用程序共享的可接受带宽限制。默认值为 500000。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-p103">Acceptable bandwidth limitation for application sharing. The default value is 500000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a2c5-124"><strong>SpoiledTilePercentTotalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="9a2c5-124"><strong>SpoiledTilePercentTotalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="9a2c5-125">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="9a2c5-125">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a2c5-p104">用于归类应用程序共享质量的“已损坏”图块的最佳百分率。此值是共享方中未到达查看方的内容的百分比。当共享方丢弃图形源中的图块或 ASMCU 图块丢弃共享方中的图块时，内容可能被丢弃（或被损坏）。默认值为 11%。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-p104">Optimal percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 11 percent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a2c5-130"><strong>SpoiledTilePercentTotalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="9a2c5-130"><strong>SpoiledTilePercentTotalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="9a2c5-131">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="9a2c5-131">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a2c5-p105">用于归类应用程序共享质量的“已损坏”图块的可接受百分率。此值是共享方中未到达查看方的内容的百分比。当共享方丢弃图形源中的图块或 ASMCU 图块丢弃共享方中的图块时，内容可能被丢弃（或被损坏）。默认值为 36%。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-p105">cceptable percentage rate for “spoiled” tiles for classifying an Application Sharing quality. This value is the percentage of the content from the sharer that did not reach the viewer. Content may be discarded (or spoiled) when the sharer discards tiles from the graphics source or the ASMCU tiles discards tiles from Sharer respectively. The default value is 36 percent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a2c5-136"><strong>JitterInterArrivalOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="9a2c5-136"><strong>JitterInterArrivalOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="9a2c5-137">int</span><span class="sxs-lookup"><span data-stu-id="9a2c5-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a2c5-138">Microsoft Lync Server 2013 中未使用此列。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-138">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a2c5-139"><strong>JitterInterArrivalAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="9a2c5-139"><strong>JitterInterArrivalAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="9a2c5-140">int</span><span class="sxs-lookup"><span data-stu-id="9a2c5-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a2c5-141">Microsoft Lync Server 2013 中未使用此列。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-141">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a2c5-142"><strong>RelativeOneWayBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="9a2c5-142"><strong>RelativeOneWayBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="9a2c5-143">float</span><span class="sxs-lookup"><span data-stu-id="9a2c5-143">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a2c5-144">Microsoft Lync Server 2013 中未使用此列。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-144">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a2c5-145"><strong>RelativeOneWayBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="9a2c5-145"><strong>RelativeOneWayBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="9a2c5-146">float</span><span class="sxs-lookup"><span data-stu-id="9a2c5-146">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a2c5-147">Microsoft Lync Server 2013 中未使用此列。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-147">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a2c5-148"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="9a2c5-148"><strong>RDPTileProcessingLatencyBurstDensityOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="9a2c5-149">float</span><span class="sxs-lookup"><span data-stu-id="9a2c5-149">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a2c5-150">Microsoft Lync Server 2013 中未使用此列。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-150">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a2c5-151"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="9a2c5-151"><strong>RDPTileProcessingLatencyBurstDensityAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="9a2c5-152">float</span><span class="sxs-lookup"><span data-stu-id="9a2c5-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a2c5-153">Microsoft Lync Server 2013 中未使用此列。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-153">This column is not used in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a2c5-154"><strong>RelativeOneWayAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="9a2c5-154"><strong>RelativeOneWayAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="9a2c5-155">float</span><span class="sxs-lookup"><span data-stu-id="9a2c5-155">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a2c5-p106">应用程序共享中涉及的两个媒体终结点之间的相对单向延迟的最佳值。这是单跃点延迟度量。默认值为 1.0 秒。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-p106">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.0 seconds.</span></span></p>
<p><span data-ttu-id="9a2c5-159">列是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-159">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a2c5-160"><strong>RelativeOneWayAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="9a2c5-160"><strong>RelativeOneWayAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="9a2c5-161">float</span><span class="sxs-lookup"><span data-stu-id="9a2c5-161">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a2c5-p107">应用程序共享中涉及的两个媒体终结点之间的相对单向延迟的最佳值。这是单跃点延迟度量。默认值为 1.75 秒。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-p107">Optimal value for the relative one-way delay between the two media endpoints involved in the application sharing. This is a single-hop latency measure. The default value is 1.75 seconds.</span></span></p>
<p><span data-ttu-id="9a2c5-165">列是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-165">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9a2c5-166"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="9a2c5-166"><strong>RDPTileProcessingLatencyAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="9a2c5-167">float</span><span class="sxs-lookup"><span data-stu-id="9a2c5-167">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a2c5-168">查看会话持续时间内 AS 会议服务器中的平均 RDP 图块处理延迟的最佳值。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-168">Optimal value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="9a2c5-169">滞后时间是在服务器 (共享器或 MCU 上对启动帧进行编码的时间之间的时间差，具体取决于应用场景) 并在查看器上解码相同的起始帧。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-169">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="9a2c5-p109">高平均值反映了查看体验中的延迟较长。过载的会议服务器可能会遇到更长的平均延迟。默认值为 200 毫秒。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-p109">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="9a2c5-173">列是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-173">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9a2c5-174"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="9a2c5-174"><strong>RDPTileProcessingLatencyAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="9a2c5-175">float</span><span class="sxs-lookup"><span data-stu-id="9a2c5-175">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="9a2c5-176">查看会话持续时间内 AS 会议服务器中的平均 RDP 图块处理延迟的可接受值。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-176">Acceptable value of the average RDP tile processing latency in the AS Conferencing Server over the duration of the viewing session.</span></span> <span data-ttu-id="9a2c5-177">滞后时间是在服务器 (共享器或 MCU 上对启动帧进行编码的时间之间的时间差，具体取决于应用场景) 并在查看器上解码相同的起始帧。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-177">Latency is the time difference between when the Start Frame is encoded on the server (sharer or MCU depending on the scenario) and the same Start Frame is decoded on the viewer.</span></span></p>
<p><span data-ttu-id="9a2c5-p111">高平均值反映了查看体验中的延迟较长。过载的会议服务器可能会遇到更长的平均延迟。默认值为 200 毫秒。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-p111">A high average reflects a longer delay in the viewing experience. An overloaded conferencing server may experience higher average delays. The default value is 200ms.</span></span></p>
<p><span data-ttu-id="9a2c5-181">列是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="9a2c5-181">The column was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

