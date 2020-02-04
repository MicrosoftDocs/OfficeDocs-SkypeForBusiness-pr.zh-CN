---
title: Lync Server 2013： AudioStreamDetail 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 77cebcd47d735f1779396c0272877c0ec64a6189
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="e74e7-102">Lync Server 2013 中的 AudioStreamDetail 视图</span><span class="sxs-lookup"><span data-stu-id="e74e7-102">AudioStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e74e7-103">_**主题上次修改时间：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e74e7-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e74e7-104">AudioStreamDetail 视图存储有关数据库中每个音频流的信息。</span><span class="sxs-lookup"><span data-stu-id="e74e7-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="e74e7-105">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="e74e7-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e74e7-106">列</span><span class="sxs-lookup"><span data-stu-id="e74e7-106">Column</span></span></th>
<th><span data-ttu-id="e74e7-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="e74e7-107">Data Type</span></span></th>
<th><span data-ttu-id="e74e7-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="e74e7-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="e74e7-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="e74e7-110">datetime</span><span class="sxs-lookup"><span data-stu-id="e74e7-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="e74e7-111">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e74e7-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="e74e7-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="e74e7-113">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-113">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-114">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e74e7-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-115">StreamId</span><span class="sxs-lookup"><span data-stu-id="e74e7-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="e74e7-116">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-116">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-117">媒体行内的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="e74e7-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="e74e7-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="e74e7-119">datetime</span><span class="sxs-lookup"><span data-stu-id="e74e7-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="e74e7-120">会话的开始时间。</span><span class="sxs-lookup"><span data-stu-id="e74e7-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="e74e7-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="e74e7-122">datetime</span><span class="sxs-lookup"><span data-stu-id="e74e7-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="e74e7-123">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="e74e7-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-124">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="e74e7-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="e74e7-125">bit</span><span class="sxs-lookup"><span data-stu-id="e74e7-125">bit</span></span></p></td>
<td><p><span data-ttu-id="e74e7-126">对话框类别：0是 Lync 服务器，用于采集服务器腿;1是中介服务器到 PSTN 网关腿。</span><span class="sxs-lookup"><span data-stu-id="e74e7-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="e74e7-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="e74e7-128">bit</span><span class="sxs-lookup"><span data-stu-id="e74e7-128">bit</span></span></p></td>
<td><p><span data-ttu-id="e74e7-129">指示是否已绕过呼叫的标志。</span><span class="sxs-lookup"><span data-stu-id="e74e7-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-130">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="e74e7-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="e74e7-131">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-131">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-132">如果存在，则指示未跳过呼叫的原因，即使旁路 Id 匹配也是如此。</span><span class="sxs-lookup"><span data-stu-id="e74e7-132">If present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="e74e7-133">仅定义了一个值：</span><span class="sxs-lookup"><span data-stu-id="e74e7-133">Only one value is defined:</span></span></p>
<p><span data-ttu-id="e74e7-134">0x0001-默认网络适配器的旁路 ID 未知。</span><span class="sxs-lookup"><span data-stu-id="e74e7-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="e74e7-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="e74e7-136">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-136">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-137">通话的优先级。</span><span class="sxs-lookup"><span data-stu-id="e74e7-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="e74e7-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="e74e7-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e74e7-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-140">呼叫方池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e74e7-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="e74e7-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="e74e7-142">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e74e7-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-143">被调用池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e74e7-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-144">呼叫者</span><span class="sxs-lookup"><span data-stu-id="e74e7-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="e74e7-145">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="e74e7-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-146">调用方的 URI。</span><span class="sxs-lookup"><span data-stu-id="e74e7-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-147">被叫方</span><span class="sxs-lookup"><span data-stu-id="e74e7-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="e74e7-148">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="e74e7-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-149">被调用方的 URI。</span><span class="sxs-lookup"><span data-stu-id="e74e7-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="e74e7-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="e74e7-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e74e7-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-152">呼叫方的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="e74e7-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="e74e7-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="e74e7-154">smallint</span><span class="sxs-lookup"><span data-stu-id="e74e7-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="e74e7-155">呼叫方的用户代理的类型。</span><span class="sxs-lookup"><span data-stu-id="e74e7-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="e74e7-156">有关详细信息，请参阅<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e74e7-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="e74e7-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="e74e7-158">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="e74e7-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-159">呼叫方的用户代理类别。</span><span class="sxs-lookup"><span data-stu-id="e74e7-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="e74e7-160">有关详细信息，请参阅<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表（QoE）</a> 。</span><span class="sxs-lookup"><span data-stu-id="e74e7-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="e74e7-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="e74e7-162">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e74e7-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-163">被呼叫方的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="e74e7-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="e74e7-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="e74e7-165">smallint</span><span class="sxs-lookup"><span data-stu-id="e74e7-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="e74e7-166">被调用方的用户代理的类型。</span><span class="sxs-lookup"><span data-stu-id="e74e7-166">Type of callee’s user agent.</span></span> <span data-ttu-id="e74e7-167">有关信息，请参阅<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e74e7-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="e74e7-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="e74e7-169">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="e74e7-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-170">被呼叫方的用户代理类别。</span><span class="sxs-lookup"><span data-stu-id="e74e7-170">Category of callee’s user agent.</span></span> <span data-ttu-id="e74e7-171">有关信息，请参阅<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表（QoE）</a> 。</span><span class="sxs-lookup"><span data-stu-id="e74e7-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="e74e7-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="e74e7-173">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e74e7-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-174">调用方的终结点名称。</span><span class="sxs-lookup"><span data-stu-id="e74e7-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="e74e7-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="e74e7-176">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e74e7-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-177">被调用方的终结点名称。</span><span class="sxs-lookup"><span data-stu-id="e74e7-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-178">CallerOS</span><span class="sxs-lookup"><span data-stu-id="e74e7-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="e74e7-179">nvarchar</span><span class="sxs-lookup"><span data-stu-id="e74e7-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-180">呼叫方终结点的操作系统（OS）。</span><span class="sxs-lookup"><span data-stu-id="e74e7-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="e74e7-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="e74e7-182">nvarchar</span><span class="sxs-lookup"><span data-stu-id="e74e7-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-183">被调用方终结点的操作系统（OS）。</span><span class="sxs-lookup"><span data-stu-id="e74e7-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="e74e7-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="e74e7-185">nvarchar</span><span class="sxs-lookup"><span data-stu-id="e74e7-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-186">呼叫方终结点的 CPU 名称。</span><span class="sxs-lookup"><span data-stu-id="e74e7-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="e74e7-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="e74e7-188">nvarchar</span><span class="sxs-lookup"><span data-stu-id="e74e7-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-189">被调用方终结点的 CPU 名称。</span><span class="sxs-lookup"><span data-stu-id="e74e7-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="e74e7-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="e74e7-191">smallint</span><span class="sxs-lookup"><span data-stu-id="e74e7-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="e74e7-192">呼叫方终结点中的 CPU 内核数。</span><span class="sxs-lookup"><span data-stu-id="e74e7-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="e74e7-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="e74e7-194">smallint</span><span class="sxs-lookup"><span data-stu-id="e74e7-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="e74e7-195">被调用方的终结点中的 CPU 内核数。</span><span class="sxs-lookup"><span data-stu-id="e74e7-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-196">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="e74e7-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="e74e7-197">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-197">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-198">呼叫方终结点的 CPU 处理器速度。</span><span class="sxs-lookup"><span data-stu-id="e74e7-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="e74e7-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="e74e7-200">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-200">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-201">被调用方终结点的 CPU 处理器速度。</span><span class="sxs-lookup"><span data-stu-id="e74e7-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="e74e7-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="e74e7-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="e74e7-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e74e7-204">指示呼叫者的系统是否在虚拟化环境中运行。</span><span class="sxs-lookup"><span data-stu-id="e74e7-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="e74e7-205">有关详细信息，请参阅<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的终结点表</a>。</span><span class="sxs-lookup"><span data-stu-id="e74e7-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="e74e7-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="e74e7-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="e74e7-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e74e7-208">指示被调用方的系统是否在虚拟化环境中运行。</span><span class="sxs-lookup"><span data-stu-id="e74e7-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="e74e7-209">有关详细信息，请参阅<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的终结点表</a>。</span><span class="sxs-lookup"><span data-stu-id="e74e7-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="e74e7-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e74e7-211">相关密钥。</span><span class="sxs-lookup"><span data-stu-id="e74e7-211">Correlation key.</span></span> <span data-ttu-id="e74e7-212">从<a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 中的 SessionCorrelation 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e74e7-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="e74e7-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="e74e7-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="e74e7-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e74e7-215">有关媒体路径（如直接或中继）的信息。</span><span class="sxs-lookup"><span data-stu-id="e74e7-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="e74e7-216">有关详细信息，请参阅<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e74e7-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="e74e7-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="e74e7-218">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-218">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-219">有关在呼叫者的位标志中描述的交互式连接建立（ICE）流程的信息。</span><span class="sxs-lookup"><span data-stu-id="e74e7-219">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="e74e7-220">有关详细信息，请参阅体验质量监视服务器协议规范。</span><span class="sxs-lookup"><span data-stu-id="e74e7-220">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="e74e7-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="e74e7-222">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-222">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-223">有关被调用方的位标志中所述的交互式连接建立（ICE）流程的信息。</span><span class="sxs-lookup"><span data-stu-id="e74e7-223">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="e74e7-224">有关详细信息，请参阅体验质量监视服务器协议规范。</span><span class="sxs-lookup"><span data-stu-id="e74e7-224">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-225">Transport</span><span class="sxs-lookup"><span data-stu-id="e74e7-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="e74e7-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="e74e7-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e74e7-227">传输类型：0是 UDP，1是 TCP。</span><span class="sxs-lookup"><span data-stu-id="e74e7-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="e74e7-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e74e7-229">var （50）</span><span class="sxs-lookup"><span data-stu-id="e74e7-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-230">呼叫方的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e74e7-230">IP address of the caller.</span></span> <span data-ttu-id="e74e7-231">这可能是 IPv4 地址或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="e74e7-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="e74e7-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="e74e7-233">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-233">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-234">呼叫方使用的端口。</span><span class="sxs-lookup"><span data-stu-id="e74e7-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="e74e7-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="e74e7-236">bit</span><span class="sxs-lookup"><span data-stu-id="e74e7-236">bit</span></span></p></td>
<td><p><span data-ttu-id="e74e7-237">指示呼叫者是否在间隔网络内：1表示呼叫方位于企业网络内，0表示呼叫方位于网络外部。</span><span class="sxs-lookup"><span data-stu-id="e74e7-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="e74e7-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e74e7-239">var （50）</span><span class="sxs-lookup"><span data-stu-id="e74e7-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-240">被呼叫方的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e74e7-240">IP address of the callee.</span></span> <span data-ttu-id="e74e7-241">这可能是 IPv4 地址或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="e74e7-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="e74e7-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="e74e7-243">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-243">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-244">被呼叫方使用的端口。</span><span class="sxs-lookup"><span data-stu-id="e74e7-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="e74e7-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="e74e7-246">bit</span><span class="sxs-lookup"><span data-stu-id="e74e7-246">bit</span></span></p></td>
<td><p><span data-ttu-id="e74e7-247">指示被调用方是否在间隔网络内：1表示被呼叫方位于企业网络内，0表示被呼叫方位于网络外部。</span><span class="sxs-lookup"><span data-stu-id="e74e7-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="e74e7-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="e74e7-249">nvarchar</span><span class="sxs-lookup"><span data-stu-id="e74e7-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-250">呼叫者站点的名称。</span><span class="sxs-lookup"><span data-stu-id="e74e7-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="e74e7-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="e74e7-252">nvarchar</span><span class="sxs-lookup"><span data-stu-id="e74e7-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-253">呼叫方网站的国家/地区的名称。</span><span class="sxs-lookup"><span data-stu-id="e74e7-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="e74e7-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="e74e7-255">nvarchar</span><span class="sxs-lookup"><span data-stu-id="e74e7-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-256">被调用方的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="e74e7-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="e74e7-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="e74e7-258">nvarchar</span><span class="sxs-lookup"><span data-stu-id="e74e7-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-259">被呼叫方网站的国家/地区的名称。</span><span class="sxs-lookup"><span data-stu-id="e74e7-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="e74e7-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e74e7-261">var （50）</span><span class="sxs-lookup"><span data-stu-id="e74e7-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-262">呼叫方使用的 A/V 边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e74e7-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="e74e7-263">有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</span><span class="sxs-lookup"><span data-stu-id="e74e7-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="e74e7-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="e74e7-265">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-265">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-266">由呼叫方使用的 A/V 边缘服务使用的端口。</span><span class="sxs-lookup"><span data-stu-id="e74e7-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="e74e7-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e74e7-268">var （50）</span><span class="sxs-lookup"><span data-stu-id="e74e7-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-269">被呼叫方使用的 A/V 边缘服务的 IP 地址密钥。</span><span class="sxs-lookup"><span data-stu-id="e74e7-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="e74e7-270">有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</span><span class="sxs-lookup"><span data-stu-id="e74e7-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="e74e7-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="e74e7-272">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-272">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-273">用于由被呼叫方使用的 A/V 边缘服务的端口。</span><span class="sxs-lookup"><span data-stu-id="e74e7-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="e74e7-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="e74e7-275">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="e74e7-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-276">呼叫方的捕获设备名称。</span><span class="sxs-lookup"><span data-stu-id="e74e7-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="e74e7-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="e74e7-278">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="e74e7-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-279">调用方的呈现设备名称。</span><span class="sxs-lookup"><span data-stu-id="e74e7-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="e74e7-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e74e7-281">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="e74e7-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-282">呼叫方的捕获设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="e74e7-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="e74e7-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="e74e7-284">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="e74e7-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-285">呼叫方的呈现设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="e74e7-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-286">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="e74e7-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="e74e7-287">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="e74e7-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-288">被调用方的捕获设备名称。</span><span class="sxs-lookup"><span data-stu-id="e74e7-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="e74e7-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="e74e7-290">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="e74e7-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-291">被调用方的呈现设备名称。</span><span class="sxs-lookup"><span data-stu-id="e74e7-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-292">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="e74e7-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e74e7-293">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="e74e7-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-294">被调用方的捕获设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="e74e7-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="e74e7-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e74e7-296">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="e74e7-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-297">被调用方的呈现设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="e74e7-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="e74e7-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="e74e7-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="e74e7-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e74e7-300">呼叫者的网络连接类型：0是 "有线"，1是 "无线"。</span><span class="sxs-lookup"><span data-stu-id="e74e7-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="e74e7-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="e74e7-302">bit</span><span class="sxs-lookup"><span data-stu-id="e74e7-302">bit</span></span></p></td>
<td><p><span data-ttu-id="e74e7-303">指示呼叫者是否通过虚拟专用网络连接：1是虚拟专用网（VPN），0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="e74e7-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="e74e7-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="e74e7-305">十进制（18，0）</span><span class="sxs-lookup"><span data-stu-id="e74e7-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-306">呼叫方终结点的网络链接速度（以 bps 为实现）。</span><span class="sxs-lookup"><span data-stu-id="e74e7-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="e74e7-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="e74e7-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="e74e7-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e74e7-309">被呼叫方的网络连接类型：0是 "有线"，1是 "无线"。</span><span class="sxs-lookup"><span data-stu-id="e74e7-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="e74e7-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="e74e7-311">bit</span><span class="sxs-lookup"><span data-stu-id="e74e7-311">bit</span></span></p></td>
<td><p><span data-ttu-id="e74e7-312">指示呼叫者是否通过虚拟专用网络连接：1是虚拟专用网（VPN），0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="e74e7-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="e74e7-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="e74e7-314">十进制（18，0）</span><span class="sxs-lookup"><span data-stu-id="e74e7-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-315">被呼叫方终结点的网络链接速度，以 bps 为限。</span><span class="sxs-lookup"><span data-stu-id="e74e7-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="e74e7-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="e74e7-317">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-318">音频会话的 Narrowband 对话 MOS （基于两个音频流）。</span><span class="sxs-lookup"><span data-stu-id="e74e7-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="e74e7-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="e74e7-320">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-320">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-321">在给定各种策略设置（TURN、API、SDP、策略服务器等）的情况下，应用到给定发送端流的实际带宽。</span><span class="sxs-lookup"><span data-stu-id="e74e7-321">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="e74e7-322">此操作不会与有效的带宽混淆，因为根据带宽估计，可能会有较低的有效带宽。</span><span class="sxs-lookup"><span data-stu-id="e74e7-322">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="e74e7-323">这基本上是发送流对带宽估计所施加限制限制的最大带宽</span><span class="sxs-lookup"><span data-stu-id="e74e7-323">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="e74e7-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="e74e7-325">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-325">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-326">实时控制协议（RTCP）统计信息的平均网络抖动。</span><span class="sxs-lookup"><span data-stu-id="e74e7-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="e74e7-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="e74e7-328">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-328">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-329">通话期间网络抖动的最大值。</span><span class="sxs-lookup"><span data-stu-id="e74e7-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="e74e7-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="e74e7-331">十进制（5，4）</span><span class="sxs-lookup"><span data-stu-id="e74e7-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-332">通话期间平均数据包丢失速率。</span><span class="sxs-lookup"><span data-stu-id="e74e7-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="e74e7-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="e74e7-334">十进制（5，4）</span><span class="sxs-lookup"><span data-stu-id="e74e7-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-335">通话过程中观察到的最大数据包丢失。</span><span class="sxs-lookup"><span data-stu-id="e74e7-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-336">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="e74e7-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="e74e7-337">十进制（9，4）</span><span class="sxs-lookup"><span data-stu-id="e74e7-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-338">通话期间出现猝发损失期间的数据包丢失的平均密度。</span><span class="sxs-lookup"><span data-stu-id="e74e7-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="e74e7-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="e74e7-340">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-340">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-341">通话期间出现猝发损失期间的数据包丢失的平均持续时间。</span><span class="sxs-lookup"><span data-stu-id="e74e7-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="e74e7-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="e74e7-343">十进制（9，4）</span><span class="sxs-lookup"><span data-stu-id="e74e7-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-344">出现猝发数据包丢失之间的平均数据包损失的平均密度。</span><span class="sxs-lookup"><span data-stu-id="e74e7-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="e74e7-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="e74e7-346">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-346">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-347">爆发数据包损失之间的平均持续时间。</span><span class="sxs-lookup"><span data-stu-id="e74e7-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="e74e7-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="e74e7-349">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-349">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-350">音频流的数据包计数。</span><span class="sxs-lookup"><span data-stu-id="e74e7-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-351">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="e74e7-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="e74e7-352">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-352">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-353">音频流的带宽估计。</span><span class="sxs-lookup"><span data-stu-id="e74e7-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="e74e7-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="e74e7-355">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-356">整个通话的网络 MOS 降级。</span><span class="sxs-lookup"><span data-stu-id="e74e7-356">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="e74e7-357">范围为0.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="e74e7-357">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="e74e7-358">此指标显示由于抖动和数据包丢失，网络 MOS 的减少量。</span><span class="sxs-lookup"><span data-stu-id="e74e7-358">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="e74e7-359">对于可接受的质量，它应小于0.5。</span><span class="sxs-lookup"><span data-stu-id="e74e7-359">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="e74e7-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="e74e7-361">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-362">通话期间最大网络 MOS 性能下降。</span><span class="sxs-lookup"><span data-stu-id="e74e7-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="e74e7-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="e74e7-364">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-365">由抖动导致的网络 MOS 性能下降。</span><span class="sxs-lookup"><span data-stu-id="e74e7-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="e74e7-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="e74e7-367">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-368">由于数据包丢失导致网络 MOS 性能下降。</span><span class="sxs-lookup"><span data-stu-id="e74e7-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="e74e7-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="e74e7-370">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-370">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-371">用于呼叫的音频编解码器，从<a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中的 PayloadDescription 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e74e7-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="e74e7-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="e74e7-373">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-373">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-374">音频流的采样率。</span><span class="sxs-lookup"><span data-stu-id="e74e7-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e74e7-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e74e7-376">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-376">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-377">呼叫者发送的音频的模拟增益控制音频信号级别。</span><span class="sxs-lookup"><span data-stu-id="e74e7-377">Post-Analog Gain Control audio signal level for the audio the caller sent.</span></span> <span data-ttu-id="e74e7-378">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e74e7-378">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e74e7-379">为获得可接受的质量，它至少应为 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e74e7-379">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="e74e7-380">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="e74e7-380">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e74e7-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e74e7-382">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-382">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-383">呼叫者收到的音频的音频信号级别。</span><span class="sxs-lookup"><span data-stu-id="e74e7-383">Audio signal level for the audio the caller received.</span></span> <span data-ttu-id="e74e7-384">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e74e7-384">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e74e7-385">为获得可接受的质量，它至少应为 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e74e7-385">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="e74e7-386">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="e74e7-386">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e74e7-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e74e7-388">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-388">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-389">为呼叫者发送的音频的模拟后增益控制音频噪音级别。</span><span class="sxs-lookup"><span data-stu-id="e74e7-389">Post-Analog Gain Control audio noise level for the audio the caller sent.</span></span> <span data-ttu-id="e74e7-390">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e74e7-390">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e74e7-391">为获得可接受的质量，它应小于 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e74e7-391">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="e74e7-392">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="e74e7-392">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e74e7-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e74e7-394">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-394">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-395">呼叫者收到的音频的后模拟增益控制音频噪音级别。</span><span class="sxs-lookup"><span data-stu-id="e74e7-395">Post-Analog Gain Control audio noise level for the audio the caller received.</span></span> <span data-ttu-id="e74e7-396">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e74e7-396">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e74e7-397">为获得可接受的质量，它应小于 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e74e7-397">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="e74e7-398">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="e74e7-398">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="e74e7-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="e74e7-400">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-400">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-401">呼叫方的回音返回损失增强。</span><span class="sxs-lookup"><span data-stu-id="e74e7-401">Echo Return Loss Enhancement for the caller.</span></span> <span data-ttu-id="e74e7-402">此指标的单位为 dB。</span><span class="sxs-lookup"><span data-stu-id="e74e7-402">The unit for this metric is dB.</span></span> <span data-ttu-id="e74e7-403">较低的值表示较少的回声。</span><span class="sxs-lookup"><span data-stu-id="e74e7-403">Lower values represent less echo.</span></span> <span data-ttu-id="e74e7-404">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="e74e7-404">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="e74e7-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="e74e7-406">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-406">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-407">呼叫者的扬声器呈现每五分钟的平均故障。</span><span class="sxs-lookup"><span data-stu-id="e74e7-407">Average glitches per five minutes for the caller’s loudspeaker rendering.</span></span> <span data-ttu-id="e74e7-408">为了获得良好的质量，这应该小于每五分钟一次。</span><span class="sxs-lookup"><span data-stu-id="e74e7-408">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="e74e7-409">不由 A/V 式会议服务器、中介服务器或 IP 电话报告。</span><span class="sxs-lookup"><span data-stu-id="e74e7-409">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="e74e7-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="e74e7-411">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-411">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-412">呼叫者的麦克风捕获每五分钟的平均故障。</span><span class="sxs-lookup"><span data-stu-id="e74e7-412">Average glitches per five minutes for the caller’s microphone capture.</span></span> <span data-ttu-id="e74e7-413">为了获得良好的质量，这应该小于每五分钟一次。</span><span class="sxs-lookup"><span data-stu-id="e74e7-413">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="e74e7-414">不由 A/V 式会议服务器、中介服务器或 IP 电话报告。</span><span class="sxs-lookup"><span data-stu-id="e74e7-414">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="e74e7-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="e74e7-416">十进制（9，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-417">呼叫者的麦克风设备时钟偏移速率，相对于 CPU 时钟。</span><span class="sxs-lookup"><span data-stu-id="e74e7-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="e74e7-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="e74e7-419">十进制（9，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-420">呼叫者的扬声器设备时钟偏移率（相对于 CPU 时钟）。</span><span class="sxs-lookup"><span data-stu-id="e74e7-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="e74e7-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="e74e7-422">十进制（9，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-423">在呼叫的最后20秒内，麦克风捕获流时间戳的平均时间戳错误（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="e74e7-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="e74e7-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="e74e7-425">十进制（9，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-426">呼叫者最近20秒内呼叫者的扬声器渲染流时间戳错误的平均值。</span><span class="sxs-lookup"><span data-stu-id="e74e7-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="e74e7-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="e74e7-428">smallint</span><span class="sxs-lookup"><span data-stu-id="e74e7-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="e74e7-429">语音开关是一种具有更低中断能力的半双工模式。</span><span class="sxs-lookup"><span data-stu-id="e74e7-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="e74e7-430">有关详细信息，请参阅<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e74e7-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="e74e7-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="e74e7-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="e74e7-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e74e7-433">呼叫方的 echo 事件的原因。</span><span class="sxs-lookup"><span data-stu-id="e74e7-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="e74e7-434">有关详细信息，请参阅<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e74e7-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="e74e7-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="e74e7-436">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-437">在呼叫者的麦克风捕获流中检测到回声的时间的百分比。</span><span class="sxs-lookup"><span data-stu-id="e74e7-437">Percentage of time when echo is detected in the caller’s microphone capture stream.</span></span> <span data-ttu-id="e74e7-438">如果使用耳机，则该值应较低。</span><span class="sxs-lookup"><span data-stu-id="e74e7-438">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="e74e7-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="e74e7-440">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-441">在呼叫方的发送流中检测到回显的时间的百分比。</span><span class="sxs-lookup"><span data-stu-id="e74e7-441">Percentage of time when echo is detected in the caller’s sent stream.</span></span> <span data-ttu-id="e74e7-442">发送流中的高回显百分比表示回声泄漏。</span><span class="sxs-lookup"><span data-stu-id="e74e7-442">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e74e7-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e74e7-444">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-444">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-445">在中介服务器上收到来自呼叫者音频的网关的信号级别;这仅适用于中介服务器。</span><span class="sxs-lookup"><span data-stu-id="e74e7-445">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="e74e7-446">此指标的单位为 dBoV。</span><span class="sxs-lookup"><span data-stu-id="e74e7-446">The unit of this metric is dBoV.</span></span> <span data-ttu-id="e74e7-447">为了获得优质，可接受范围应为-30 至-18 dBoV。</span><span class="sxs-lookup"><span data-stu-id="e74e7-447">For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e74e7-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e74e7-449">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-449">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-450">在中介服务器上从呼叫方音频的网关接收的信号级别。</span><span class="sxs-lookup"><span data-stu-id="e74e7-450">Received signal level on the Mediation Server from the Gateway for the caller’s audio.</span></span> <span data-ttu-id="e74e7-451">这仅适用于中介服务器。</span><span class="sxs-lookup"><span data-stu-id="e74e7-451">This applies only to the Mediation Server.</span></span> <span data-ttu-id="e74e7-452">此指标的单位为 dBoV。</span><span class="sxs-lookup"><span data-stu-id="e74e7-452">The unit of this metric is dBoV.</span></span> <span data-ttu-id="e74e7-453">为了获得优质，可接受范围应小于-50 dBoV。</span><span class="sxs-lookup"><span data-stu-id="e74e7-453">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="e74e7-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="e74e7-455">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-455">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-456">在中介服务器端应用于呼叫方音频的自动增益控制（AGC）。</span><span class="sxs-lookup"><span data-stu-id="e74e7-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="e74e7-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="e74e7-458">float</span><span class="sxs-lookup"><span data-stu-id="e74e7-458">float</span></span></p></td>
<td><p><span data-ttu-id="e74e7-459">呼叫方的传入信号的根平均值平方（RMS），最多可拨出前30秒。</span><span class="sxs-lookup"><span data-stu-id="e74e7-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e74e7-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e74e7-461">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-461">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-462">表示被呼叫者发送的音频的后模拟增益控制音频信号级别。</span><span class="sxs-lookup"><span data-stu-id="e74e7-462">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent.</span></span> <span data-ttu-id="e74e7-463">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e74e7-463">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e74e7-464">为获得可接受的质量，它至少应为 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e74e7-464">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="e74e7-465">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="e74e7-465">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e74e7-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e74e7-467">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-467">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-468">被呼叫方收到的音频的音频信号级别。</span><span class="sxs-lookup"><span data-stu-id="e74e7-468">Audio signal level for the audio the callee received.</span></span> <span data-ttu-id="e74e7-469">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e74e7-469">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e74e7-470">为获得可接受的质量，它至少应为 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e74e7-470">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="e74e7-471">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="e74e7-471">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e74e7-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e74e7-473">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-473">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-474">对被呼叫者发送的音频进行模拟提升控制音频噪音级别。</span><span class="sxs-lookup"><span data-stu-id="e74e7-474">Post-Analog Gain Control audio noise level for the audio the callee sent.</span></span> <span data-ttu-id="e74e7-475">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e74e7-475">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e74e7-476">为获得可接受的质量，它应小于 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e74e7-476">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="e74e7-477">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="e74e7-477">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e74e7-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e74e7-479">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-479">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-480">被呼叫方接收的音频的模拟后增益控制音频噪音级别。</span><span class="sxs-lookup"><span data-stu-id="e74e7-480">Post-Analog Gain Control audio noise level for the audio the callee received.</span></span> <span data-ttu-id="e74e7-481">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e74e7-481">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e74e7-482">为获得可接受的质量，它应小于 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e74e7-482">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="e74e7-483">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="e74e7-483">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="e74e7-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="e74e7-485">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-485">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-486">被调用方的回音返回损失增强。</span><span class="sxs-lookup"><span data-stu-id="e74e7-486">Echo Return Loss Enhancement for the callee.</span></span> <span data-ttu-id="e74e7-487">此指标的单位为 dB。</span><span class="sxs-lookup"><span data-stu-id="e74e7-487">The unit for this metric is dB.</span></span> <span data-ttu-id="e74e7-488">较低的值表示较少的回声。</span><span class="sxs-lookup"><span data-stu-id="e74e7-488">Lower values represent less echo.</span></span> <span data-ttu-id="e74e7-489">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="e74e7-489">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="e74e7-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="e74e7-491">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-491">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-492">被调用方的扬声器呈现每五分钟的平均故障。</span><span class="sxs-lookup"><span data-stu-id="e74e7-492">Average glitches per five minutes for the callee’s loudspeaker rendering.</span></span> <span data-ttu-id="e74e7-493">为了获得良好的质量，这应该小于每五分钟一次。</span><span class="sxs-lookup"><span data-stu-id="e74e7-493">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="e74e7-494">不由 A/V 式会议服务器、中介服务器或 IP 电话报告。</span><span class="sxs-lookup"><span data-stu-id="e74e7-494">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="e74e7-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="e74e7-496">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-496">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-497">被呼叫者的麦克风捕获每五分钟的平均故障。</span><span class="sxs-lookup"><span data-stu-id="e74e7-497">Average glitches per five minutes for the callee’s microphone capture.</span></span> <span data-ttu-id="e74e7-498">为了获得良好的质量，这应该小于每五分钟一次。</span><span class="sxs-lookup"><span data-stu-id="e74e7-498">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="e74e7-499">不由 A/V 式会议服务器、中介服务器或 IP 电话报告。</span><span class="sxs-lookup"><span data-stu-id="e74e7-499">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="e74e7-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="e74e7-501">十进制（9，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-502">被呼叫者的麦克风设备时钟偏移速率，相对于 CPU 时钟。</span><span class="sxs-lookup"><span data-stu-id="e74e7-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="e74e7-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="e74e7-504">十进制（9，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-505">被呼叫者的扬声器设备时钟偏移速率，相对于 CPU 时钟。</span><span class="sxs-lookup"><span data-stu-id="e74e7-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="e74e7-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="e74e7-507">十进制（9，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-508">在呼叫的最后20秒内，麦克风捕获流时间戳的平均时间戳错误（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="e74e7-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="e74e7-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="e74e7-510">十进制（9，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-511">在呼叫的最后20秒内，被调用方的扬声器的平均呈现流时间戳错误（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="e74e7-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="e74e7-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="e74e7-513">smallint</span><span class="sxs-lookup"><span data-stu-id="e74e7-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="e74e7-514">语音开关是一种具有更低中断能力的半双工模式。</span><span class="sxs-lookup"><span data-stu-id="e74e7-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="e74e7-515">有关详细信息，请参阅<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e74e7-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="e74e7-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="e74e7-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="e74e7-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e74e7-518">被调用方的 echo 事件的原因。</span><span class="sxs-lookup"><span data-stu-id="e74e7-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="e74e7-519">有关详细信息，请参阅<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e74e7-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="e74e7-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="e74e7-521">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-522">在被呼叫者的麦克风捕获流中检测到回显的时间百分比。</span><span class="sxs-lookup"><span data-stu-id="e74e7-522">Percentage of time when echo is detected in the callee’s microphone capture stream.</span></span> <span data-ttu-id="e74e7-523">如果使用耳机，则该值应较低。</span><span class="sxs-lookup"><span data-stu-id="e74e7-523">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="e74e7-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="e74e7-525">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-526">在被调用方的发送流中检测到回显的时间的百分比。</span><span class="sxs-lookup"><span data-stu-id="e74e7-526">Percentage of time when echo is detected in the callee’s sent stream.</span></span> <span data-ttu-id="e74e7-527">发送流中的高回显百分比表示回声泄漏。</span><span class="sxs-lookup"><span data-stu-id="e74e7-527">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e74e7-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e74e7-529">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-529">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-530">在中介服务器上从被呼叫方的音频的网关接收的信号级别;这仅适用于中介服务器。</span><span class="sxs-lookup"><span data-stu-id="e74e7-530">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="e74e7-531">此指标的单位为 dBoV。</span><span class="sxs-lookup"><span data-stu-id="e74e7-531">The unit of this metric is dBoV.</span></span> <span data-ttu-id="e74e7-532">为了获得良好的质量，可接受的范围应为 [-30 至-18] dBoV。</span><span class="sxs-lookup"><span data-stu-id="e74e7-532">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e74e7-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e74e7-534">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-534">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-535">在中介服务器上从被呼叫方的音频的网关接收的信号级别。</span><span class="sxs-lookup"><span data-stu-id="e74e7-535">Received signal level on the Mediation Server from the Gateway for the callee’s audio.</span></span> <span data-ttu-id="e74e7-536">这仅适用于中介服务器。</span><span class="sxs-lookup"><span data-stu-id="e74e7-536">This applies only to the Mediation Server.</span></span> <span data-ttu-id="e74e7-537">此指标的单位为 dBoV。</span><span class="sxs-lookup"><span data-stu-id="e74e7-537">The unit of this metric is dBoV.</span></span> <span data-ttu-id="e74e7-538">为了获得优质，可接受范围应小于-50 dBoV。</span><span class="sxs-lookup"><span data-stu-id="e74e7-538">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="e74e7-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="e74e7-540">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-540">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-541">在中介服务器端应用于被呼叫方的音频的自动增益控制（AGC）。</span><span class="sxs-lookup"><span data-stu-id="e74e7-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="e74e7-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="e74e7-543">float</span><span class="sxs-lookup"><span data-stu-id="e74e7-543">float</span></span></p></td>
<td><p><span data-ttu-id="e74e7-544">到达呼叫的前30秒内被呼叫方的传入信号的根平均值方块（RMS）。</span><span class="sxs-lookup"><span data-stu-id="e74e7-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="e74e7-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="e74e7-546">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-547">通过音频康复为典型示例生成的隐藏样本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="e74e7-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="e74e7-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="e74e7-549">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-550">通过音频康复为典型示例生成的拉伸样本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="e74e7-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="e74e7-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="e74e7-552">十进制（5，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-553">从音频修复到典型示例生成的压缩样本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="e74e7-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-554">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="e74e7-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="e74e7-555">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-555">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-556">从 RTCP 统计数据往返的时间。</span><span class="sxs-lookup"><span data-stu-id="e74e7-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="e74e7-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="e74e7-558">int</span><span class="sxs-lookup"><span data-stu-id="e74e7-558">int</span></span></p></td>
<td><p><span data-ttu-id="e74e7-559">音频流的最大往返行程时间。</span><span class="sxs-lookup"><span data-stu-id="e74e7-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="e74e7-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="e74e7-561">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-562">通话的平均宽带网络 MOS。</span><span class="sxs-lookup"><span data-stu-id="e74e7-562">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="e74e7-563">此指标取决于所使用的数据包丢失、抖动和编解码器。</span><span class="sxs-lookup"><span data-stu-id="e74e7-563">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="e74e7-564">范围为1.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="e74e7-564">Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="e74e7-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="e74e7-566">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-567">通话最少宽带网络 MOS。</span><span class="sxs-lookup"><span data-stu-id="e74e7-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="e74e7-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="e74e7-569">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-570">平均预测宽带为已发送音频的 MOS 分数，包括语音级别、噪声级别和捕获设备特征。</span><span class="sxs-lookup"><span data-stu-id="e74e7-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="e74e7-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="e74e7-572">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-573">通话的最低 SendListenMOS。</span><span class="sxs-lookup"><span data-stu-id="e74e7-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="e74e7-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="e74e7-575">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-576">平均预测宽带从网络接收的音频的 MOS 分数，包括语音级别、噪音级别、编解码器、网络条件和捕获设备特征。</span><span class="sxs-lookup"><span data-stu-id="e74e7-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="e74e7-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="e74e7-578">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="e74e7-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e74e7-579">通话的最低 RecvListenMOS。</span><span class="sxs-lookup"><span data-stu-id="e74e7-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e74e7-580">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="e74e7-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="e74e7-581">bit</span><span class="sxs-lookup"><span data-stu-id="e74e7-581">bit</span></span></p></td>
<td><p><span data-ttu-id="e74e7-582">指示是否已将音频 FEC 用于呼叫。</span><span class="sxs-lookup"><span data-stu-id="e74e7-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e74e7-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="e74e7-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="e74e7-584">bit</span><span class="sxs-lookup"><span data-stu-id="e74e7-584">bit</span></span></p></td>
<td><p><span data-ttu-id="e74e7-585">指示 p 声明的标识信息的方向;1表示流方向从调用方到被调用方;0表示流方向来自被调用方的调用方。</span><span class="sxs-lookup"><span data-stu-id="e74e7-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

