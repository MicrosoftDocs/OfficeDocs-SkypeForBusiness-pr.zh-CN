---
title: Lync Server 2013： VideoMetricsThreshold 表
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
ms.openlocfilehash: 2f1f1fc7ca86c10fa9c409c73c2f4b54ee2777a1
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48508509"
---
# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="5d3de-102">Lync Server 2013 中的 VideoMetricsThreshold 表</span><span class="sxs-lookup"><span data-stu-id="5d3de-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5d3de-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="5d3de-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="5d3de-104">VideoMetricsThreshold 表包含用于视频呼叫的用户体验质量指标的最佳值和可接受值。</span><span class="sxs-lookup"><span data-stu-id="5d3de-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5d3de-105"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="5d3de-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="5d3de-106"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="5d3de-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="5d3de-107"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="5d3de-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="5d3de-108"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="5d3de-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5d3de-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="5d3de-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="5d3de-110">int</span><span class="sxs-lookup"><span data-stu-id="5d3de-110">int</span></span></p></td>
<td><p><span data-ttu-id="5d3de-111">主</span><span class="sxs-lookup"><span data-stu-id="5d3de-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="5d3de-112">发出的呼叫的类型。</span><span class="sxs-lookup"><span data-stu-id="5d3de-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d3de-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5d3de-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5d3de-114">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="5d3de-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d3de-115">默认值为 0.05。</span><span class="sxs-lookup"><span data-stu-id="5d3de-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d3de-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5d3de-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5d3de-117">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="5d3de-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d3de-118">默认值为 0.10。</span><span class="sxs-lookup"><span data-stu-id="5d3de-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d3de-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5d3de-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5d3de-120">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="5d3de-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d3de-121">默认值为 5.0。</span><span class="sxs-lookup"><span data-stu-id="5d3de-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d3de-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5d3de-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5d3de-123">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="5d3de-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d3de-124">默认值为 10.0。</span><span class="sxs-lookup"><span data-stu-id="5d3de-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d3de-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5d3de-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5d3de-126">十进制 (9、4) </span><span class="sxs-lookup"><span data-stu-id="5d3de-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d3de-127">默认值为 12.0000。</span><span class="sxs-lookup"><span data-stu-id="5d3de-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d3de-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5d3de-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5d3de-129">十进制 (9、4) </span><span class="sxs-lookup"><span data-stu-id="5d3de-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d3de-130">默认值为 7.0000。</span><span class="sxs-lookup"><span data-stu-id="5d3de-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d3de-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5d3de-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5d3de-132">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="5d3de-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d3de-133">默认值为 5.0。</span><span class="sxs-lookup"><span data-stu-id="5d3de-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d3de-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5d3de-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5d3de-135">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="5d3de-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d3de-136">默认值为 10.0。</span><span class="sxs-lookup"><span data-stu-id="5d3de-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d3de-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5d3de-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5d3de-138">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="5d3de-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d3de-139">默认值为 5.0。</span><span class="sxs-lookup"><span data-stu-id="5d3de-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d3de-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5d3de-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5d3de-141">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="5d3de-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d3de-142">默认值为 10.0。</span><span class="sxs-lookup"><span data-stu-id="5d3de-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d3de-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5d3de-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5d3de-144">foat</span><span class="sxs-lookup"><span data-stu-id="5d3de-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d3de-145">默认值为 0.05。</span><span class="sxs-lookup"><span data-stu-id="5d3de-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d3de-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5d3de-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5d3de-147">float</span><span class="sxs-lookup"><span data-stu-id="5d3de-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d3de-148">默认值为 0.10。</span><span class="sxs-lookup"><span data-stu-id="5d3de-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d3de-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5d3de-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5d3de-150">float</span><span class="sxs-lookup"><span data-stu-id="5d3de-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d3de-151">默认值为 12。</span><span class="sxs-lookup"><span data-stu-id="5d3de-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d3de-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5d3de-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5d3de-153">float</span><span class="sxs-lookup"><span data-stu-id="5d3de-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d3de-154">默认值为 7。</span><span class="sxs-lookup"><span data-stu-id="5d3de-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5d3de-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="5d3de-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="5d3de-156">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="5d3de-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d3de-157">默认值为 5.00。</span><span class="sxs-lookup"><span data-stu-id="5d3de-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5d3de-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="5d3de-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="5d3de-159">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="5d3de-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="5d3de-160">默认值为 10.00。</span><span class="sxs-lookup"><span data-stu-id="5d3de-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

