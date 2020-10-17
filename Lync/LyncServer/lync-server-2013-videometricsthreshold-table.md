---
title: Lync Server 2013： VideoMetricsThreshold 表
description: Lync Server 2013： VideoMetricsThreshold 表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 93cdd6fb4c3c54ac1470499490f36fee87ba283d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567998"
---
# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="6e462-103">Lync Server 2013 中的 VideoMetricsThreshold 表</span><span class="sxs-lookup"><span data-stu-id="6e462-103">VideoMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6e462-104">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="6e462-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="6e462-105">VideoMetricsThreshold 表包含用于视频呼叫的用户体验质量指标的最佳值和可接受值。</span><span class="sxs-lookup"><span data-stu-id="6e462-105">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="6e462-106"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="6e462-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="6e462-107"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="6e462-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="6e462-108"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="6e462-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="6e462-109"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="6e462-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="6e462-110"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="6e462-110"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="6e462-111">int</span><span class="sxs-lookup"><span data-stu-id="6e462-111">int</span></span></p></td>
<td><p><span data-ttu-id="6e462-112">主</span><span class="sxs-lookup"><span data-stu-id="6e462-112">Primary</span></span></p></td>
<td><p><span data-ttu-id="6e462-113">发出的呼叫的类型。</span><span class="sxs-lookup"><span data-stu-id="6e462-113">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e462-114"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6e462-114"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6e462-115">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="6e462-115">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6e462-116">默认值为 0.05。</span><span class="sxs-lookup"><span data-stu-id="6e462-116">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e462-117"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6e462-117"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6e462-118">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="6e462-118">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6e462-119">默认值为 0.10。</span><span class="sxs-lookup"><span data-stu-id="6e462-119">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e462-120"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6e462-120"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6e462-121">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="6e462-121">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6e462-122">默认值为 5.0。</span><span class="sxs-lookup"><span data-stu-id="6e462-122">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e462-123"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6e462-123"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6e462-124">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="6e462-124">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6e462-125">默认值为 10.0。</span><span class="sxs-lookup"><span data-stu-id="6e462-125">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e462-126"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6e462-126"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6e462-127">十进制 (9、4) </span><span class="sxs-lookup"><span data-stu-id="6e462-127">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6e462-128">默认值为 12.0000。</span><span class="sxs-lookup"><span data-stu-id="6e462-128">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e462-129"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6e462-129"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6e462-130">十进制 (9、4) </span><span class="sxs-lookup"><span data-stu-id="6e462-130">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6e462-131">默认值为 7.0000。</span><span class="sxs-lookup"><span data-stu-id="6e462-131">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e462-132"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6e462-132"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6e462-133">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="6e462-133">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6e462-134">默认值为 5.0。</span><span class="sxs-lookup"><span data-stu-id="6e462-134">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e462-135"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6e462-135"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6e462-136">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="6e462-136">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6e462-137">默认值为 10.0。</span><span class="sxs-lookup"><span data-stu-id="6e462-137">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e462-138"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6e462-138"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6e462-139">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="6e462-139">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6e462-140">默认值为 5.0。</span><span class="sxs-lookup"><span data-stu-id="6e462-140">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e462-141"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6e462-141"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6e462-142">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="6e462-142">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6e462-143">默认值为 10.0。</span><span class="sxs-lookup"><span data-stu-id="6e462-143">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e462-144"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6e462-144"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6e462-145">foat</span><span class="sxs-lookup"><span data-stu-id="6e462-145">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6e462-146">默认值为 0.05。</span><span class="sxs-lookup"><span data-stu-id="6e462-146">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e462-147"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6e462-147"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6e462-148">float</span><span class="sxs-lookup"><span data-stu-id="6e462-148">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6e462-149">默认值为 0.10。</span><span class="sxs-lookup"><span data-stu-id="6e462-149">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e462-150"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6e462-150"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6e462-151">float</span><span class="sxs-lookup"><span data-stu-id="6e462-151">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6e462-152">默认值为 12。</span><span class="sxs-lookup"><span data-stu-id="6e462-152">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e462-153"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6e462-153"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6e462-154">float</span><span class="sxs-lookup"><span data-stu-id="6e462-154">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6e462-155">默认值为 7。</span><span class="sxs-lookup"><span data-stu-id="6e462-155">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="6e462-156"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="6e462-156"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="6e462-157">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="6e462-157">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6e462-158">默认值为 5.00。</span><span class="sxs-lookup"><span data-stu-id="6e462-158">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="6e462-159"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="6e462-159"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="6e462-160">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="6e462-160">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="6e462-161">默认值为 10.00。</span><span class="sxs-lookup"><span data-stu-id="6e462-161">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

