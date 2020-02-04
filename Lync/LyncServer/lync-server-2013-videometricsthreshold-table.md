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
ms.openlocfilehash: 93dc2fd539ccc24717939ccfa2ca93032fd9f25b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741982"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videometricsthreshold-table-in-lync-server-2013"></a><span data-ttu-id="8b416-102">Lync Server 2013 中的 VideoMetricsThreshold 表</span><span class="sxs-lookup"><span data-stu-id="8b416-102">VideoMetricsThreshold table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b416-103">_**主题上次修改时间：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="8b416-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="8b416-104">VideoMetricsThreshold 表包含用于视频通话的体验指标质量的最佳值和可接受值。</span><span class="sxs-lookup"><span data-stu-id="8b416-104">The VideoMetricsThreshold table contains optimal and acceptable values for the Quality of Experience metrics used with video calls.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8b416-105"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="8b416-105"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="8b416-106"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="8b416-106"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="8b416-107"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="8b416-107"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="8b416-108"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="8b416-108"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8b416-109"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="8b416-109"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="8b416-110">int</span><span class="sxs-lookup"><span data-stu-id="8b416-110">int</span></span></p></td>
<td><p><span data-ttu-id="8b416-111">Primary</span><span class="sxs-lookup"><span data-stu-id="8b416-111">Primary</span></span></p></td>
<td><p><span data-ttu-id="8b416-112">所发出通话的类型。</span><span class="sxs-lookup"><span data-stu-id="8b416-112">Type of call that was placed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b416-113"><strong>VideoPostFECPLROptimal</strong></span><span class="sxs-lookup"><span data-stu-id="8b416-113"><strong>VideoPostFECPLROptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="8b416-114">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="8b416-114">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8b416-115">默认值为0.05。</span><span class="sxs-lookup"><span data-stu-id="8b416-115">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b416-116"><strong>VideoPostFECPLRAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="8b416-116"><strong>VideoPostFECPLRAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="8b416-117">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="8b416-117">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8b416-118">默认值为0.10。</span><span class="sxs-lookup"><span data-stu-id="8b416-118">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b416-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="8b416-119"><strong>VideoLocalFrameLostPercentageAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="8b416-120">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="8b416-120">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8b416-121">默认值为5.0。</span><span class="sxs-lookup"><span data-stu-id="8b416-121">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b416-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="8b416-122"><strong>VideoLocalFrameLostPercentageAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="8b416-123">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="8b416-123">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8b416-124">默认值为10.0。</span><span class="sxs-lookup"><span data-stu-id="8b416-124">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b416-125"><strong>RecvFrameRateAverageOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="8b416-125"><strong>RecvFrameRateAverageOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="8b416-126">十进制（9，4）</span><span class="sxs-lookup"><span data-stu-id="8b416-126">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8b416-127">默认值为12.0000。</span><span class="sxs-lookup"><span data-stu-id="8b416-127">The default value is 12.0000.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b416-128"><strong>RecvFramerateAverageAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="8b416-128"><strong>RecvFramerateAverageAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="8b416-129">十进制（9，4）</span><span class="sxs-lookup"><span data-stu-id="8b416-129">decimal(9,4)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8b416-130">默认值为7.0000。</span><span class="sxs-lookup"><span data-stu-id="8b416-130">The default value is 7.0000.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b416-131"><strong>LowFrameRateCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="8b416-131"><strong>LowFrameRateCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="8b416-132">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="8b416-132">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8b416-133">默认值为5.0。</span><span class="sxs-lookup"><span data-stu-id="8b416-133">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b416-134"><strong>LowFrameRateCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="8b416-134"><strong>LowFrameRateCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="8b416-135">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="8b416-135">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8b416-136">默认值为 10.0/</span><span class="sxs-lookup"><span data-stu-id="8b416-136">The default value is 10.0/</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b416-137"><strong>LowResolutionCallPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="8b416-137"><strong>LowResolutionCallPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="8b416-138">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="8b416-138">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8b416-139">默认值为5.0。</span><span class="sxs-lookup"><span data-stu-id="8b416-139">The default value is 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b416-140"><strong>LowResolutionCallPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="8b416-140"><strong>LowResolutionCallPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="8b416-141">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="8b416-141">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8b416-142">默认值为10.0。</span><span class="sxs-lookup"><span data-stu-id="8b416-142">The default value is 10.0.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b416-143"><strong>VideoPacketLossRateOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="8b416-143"><strong>VideoPacketLossRateOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="8b416-144">foat</span><span class="sxs-lookup"><span data-stu-id="8b416-144">foat</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8b416-145">默认值为0.05。</span><span class="sxs-lookup"><span data-stu-id="8b416-145">The default value is 0.05.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b416-146"><strong>VideoPacketLossRateAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="8b416-146"><strong>VideoPacketLossRateAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="8b416-147">float</span><span class="sxs-lookup"><span data-stu-id="8b416-147">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8b416-148">默认值为0.10。</span><span class="sxs-lookup"><span data-stu-id="8b416-148">The default value is 0.10.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b416-149"><strong>VideoFrameRateAvgOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="8b416-149"><strong>VideoFrameRateAvgOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="8b416-150">float</span><span class="sxs-lookup"><span data-stu-id="8b416-150">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8b416-151">默认值为12。</span><span class="sxs-lookup"><span data-stu-id="8b416-151">The default value is 12.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b416-152"><strong>VideoFrameRateAvgAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="8b416-152"><strong>VideoFrameRateAvgAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="8b416-153">float</span><span class="sxs-lookup"><span data-stu-id="8b416-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8b416-154">默认值为7。</span><span class="sxs-lookup"><span data-stu-id="8b416-154">The default value is 7.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8b416-155"><strong>DynamicCapabilityPercentOptimal</strong></span><span class="sxs-lookup"><span data-stu-id="8b416-155"><strong>DynamicCapabilityPercentOptimal</strong></span></span></p></td>
<td><p><span data-ttu-id="8b416-156">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="8b416-156">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8b416-157">默认值为5.00。</span><span class="sxs-lookup"><span data-stu-id="8b416-157">The default value is 5.00.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8b416-158"><strong>DynamicCapabilityPercentAcceptable</strong></span><span class="sxs-lookup"><span data-stu-id="8b416-158"><strong>DynamicCapabilityPercentAcceptable</strong></span></span></p></td>
<td><p><span data-ttu-id="8b416-159">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="8b416-159">decimal(5,2)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="8b416-160">默认值为10.00。</span><span class="sxs-lookup"><span data-stu-id="8b416-160">The default value is 10.00.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

