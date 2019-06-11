---
title: 'Lync Server 2013: VideoMetricsThreshold 表'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoMetricsThreshold table
ms:assetid: 2e2f4711-35ba-48c6-b15b-5aba61c4eb75
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204778(v=OCS.15)
ms:contentKeyID: 48183736
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c15910f6478f3df12bf906f04aee82c89a822de
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845368"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="bad30-102">Lync Server 2013 中的 VideoMetricsThreshold 表</span><span class="sxs-lookup"><span data-stu-id="bad30-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bad30-103">_**主题上次修改时间:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="bad30-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="bad30-104">VideoMetricsThreshold 表包含用于视频通话的体验指标质量的最佳值和可接受值。</span><span class="sxs-lookup"><span data-stu-id="bad30-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bad30-105"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="bad30-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="bad30-106"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="bad30-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="bad30-107"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="bad30-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="bad30-108"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="bad30-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bad30-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="bad30-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="bad30-110">int</span><span class="sxs-lookup"><span data-stu-id="bad30-110">int</span></span></p></td>
<td><p><span data-ttu-id="bad30-111">Primary</span><span class="sxs-lookup"><span data-stu-id="bad30-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="bad30-112">所发出通话的类型。</span><span class="sxs-lookup"><span data-stu-id="bad30-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bad30-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="bad30-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="bad30-114">十进制 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="bad30-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bad30-115">默认值为0.05。</span><span class="sxs-lookup"><span data-stu-id="bad30-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bad30-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="bad30-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="bad30-117">十进制 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="bad30-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bad30-118">默认值为0.10。</span><span class="sxs-lookup"><span data-stu-id="bad30-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bad30-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="bad30-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="bad30-120">十进制 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="bad30-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bad30-121">默认值为5.0。</span><span class="sxs-lookup"><span data-stu-id="bad30-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bad30-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="bad30-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="bad30-123">十进制 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="bad30-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bad30-124">默认值为10.0。</span><span class="sxs-lookup"><span data-stu-id="bad30-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bad30-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="bad30-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="bad30-126">十进制 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="bad30-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bad30-127">默认值为12.0000。</span><span class="sxs-lookup"><span data-stu-id="bad30-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bad30-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="bad30-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="bad30-129">十进制 (9, 4)</span><span class="sxs-lookup"><span data-stu-id="bad30-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bad30-130">默认值为7.0000。</span><span class="sxs-lookup"><span data-stu-id="bad30-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bad30-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="bad30-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="bad30-132">十进制 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="bad30-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bad30-133">默认值为5.0。</span><span class="sxs-lookup"><span data-stu-id="bad30-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bad30-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="bad30-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="bad30-135">十进制 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="bad30-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bad30-136">默认值为 10.0/</span><span class="sxs-lookup"><span data-stu-id="bad30-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bad30-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="bad30-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="bad30-138">十进制 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="bad30-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bad30-139">默认值为5.0。</span><span class="sxs-lookup"><span data-stu-id="bad30-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bad30-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="bad30-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="bad30-141">十进制 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="bad30-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bad30-142">默认值为10.0。</span><span class="sxs-lookup"><span data-stu-id="bad30-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bad30-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="bad30-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="bad30-144">foat</span><span class="sxs-lookup"><span data-stu-id="bad30-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bad30-145">默认值为0.05。</span><span class="sxs-lookup"><span data-stu-id="bad30-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bad30-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="bad30-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="bad30-147">float</span><span class="sxs-lookup"><span data-stu-id="bad30-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bad30-148">默认值为0.10。</span><span class="sxs-lookup"><span data-stu-id="bad30-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bad30-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="bad30-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="bad30-150">float</span><span class="sxs-lookup"><span data-stu-id="bad30-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bad30-151">默认值为12。</span><span class="sxs-lookup"><span data-stu-id="bad30-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bad30-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="bad30-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="bad30-153">float</span><span class="sxs-lookup"><span data-stu-id="bad30-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bad30-154">默认值为7。</span><span class="sxs-lookup"><span data-stu-id="bad30-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bad30-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="bad30-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="bad30-156">十进制 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="bad30-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bad30-157">默认值为5.00。</span><span class="sxs-lookup"><span data-stu-id="bad30-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bad30-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="bad30-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="bad30-159">十进制 (5, 2)</span><span class="sxs-lookup"><span data-stu-id="bad30-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="bad30-160">默认值为10.00。</span><span class="sxs-lookup"><span data-stu-id="bad30-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

