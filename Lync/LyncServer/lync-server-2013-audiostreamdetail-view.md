---
title: Lync Server 2013： AudioStreamDetail 视图
description: Lync Server 2013： AudioStreamDetail 视图。
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
ms.openlocfilehash: 92c4c9bbb4f126e242e28d835222f6ba2af89d8b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573045"
---
# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="e5e4c-103">Lync Server 2013 中的 AudioStreamDetail 视图</span><span class="sxs-lookup"><span data-stu-id="e5e4c-103">AudioStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5e4c-104">_**上次修改的主题：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e5e4c-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e5e4c-105">AudioStreamDetail 视图存储有关数据库中每个音频流的信息。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-105">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="e5e4c-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e5e4c-107">列</span><span class="sxs-lookup"><span data-stu-id="e5e4c-107">Column</span></span></th>
<th><span data-ttu-id="e5e4c-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="e5e4c-108">Data Type</span></span></th>
<th><span data-ttu-id="e5e4c-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="e5e4c-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-110">SessionTime</span><span class="sxs-lookup"><span data-stu-id="e5e4c-110">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-111">datetime</span><span class="sxs-lookup"><span data-stu-id="e5e4c-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-112"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-112">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-113">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="e5e4c-113">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-114">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-114">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-115"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-115">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-116">StreamId</span><span class="sxs-lookup"><span data-stu-id="e5e4c-116">StreamId</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-117">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-117">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-118">媒体行中的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-118">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-119">StartTime</span><span class="sxs-lookup"><span data-stu-id="e5e4c-119">StartTime</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-120">datetime</span><span class="sxs-lookup"><span data-stu-id="e5e4c-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-121">会话的开始时间。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-121">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-122">EndTime</span><span class="sxs-lookup"><span data-stu-id="e5e4c-122">EndTime</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-123">datetime</span><span class="sxs-lookup"><span data-stu-id="e5e4c-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-124">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-124">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-125">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="e5e4c-125">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-126">位</span><span class="sxs-lookup"><span data-stu-id="e5e4c-126">bit</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-127">对话框类别：0是用于中介服务器腿的 Lync 服务器;1是中介服务器到 PSTN 网关腿。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-127">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-128">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="e5e4c-128">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-129">位</span><span class="sxs-lookup"><span data-stu-id="e5e4c-129">bit</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-130">指示是否绕过呼叫的标志。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-130">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-131">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="e5e4c-131">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-132">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-132">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-133">如果存在，则指示即使绕过 Id 匹配也不会绕过呼叫。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-133">If present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="e5e4c-134">仅定义了一个值：</span><span class="sxs-lookup"><span data-stu-id="e5e4c-134">Only one value is defined:</span></span></p>
<p><span data-ttu-id="e5e4c-135">0x0001 –默认网络适配器的绕过旁路 ID。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-135">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-136">CallPriority</span><span class="sxs-lookup"><span data-stu-id="e5e4c-136">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-137">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-137">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-138">呼叫的优先级。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-138">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-139">CallerPool</span><span class="sxs-lookup"><span data-stu-id="e5e4c-139">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-140">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-141">呼叫者池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-141">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-142">CalleePool</span><span class="sxs-lookup"><span data-stu-id="e5e4c-142">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-143">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-144">被叫方池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-144">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-145">Caller</span><span class="sxs-lookup"><span data-stu-id="e5e4c-145">Caller</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-146">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-147">呼叫者的 URI。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-147">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-148">约定</span><span class="sxs-lookup"><span data-stu-id="e5e4c-148">Callee</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-149">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-149">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-150">被叫方的 URI。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-150">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-151">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="e5e4c-151">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-152">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-153">呼叫者的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-153">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-154">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="e5e4c-154">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-155">smallint</span><span class="sxs-lookup"><span data-stu-id="e5e4c-155">smallint</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-156">呼叫者的用户代理的类型。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-156">Type of the caller’s user agent.</span></span> <span data-ttu-id="e5e4c-157">有关详细信息，请参阅 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-157">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-158">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="e5e4c-158">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-159">nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-159">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-160">呼叫者的用户代理的类别。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-160">Category of the caller’s user agent.</span></span> <span data-ttu-id="e5e4c-161">有关详细信息，请参阅 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表 (QoE) </a> 。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-161">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-162">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="e5e4c-162">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-163">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-163">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-164">被叫方的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-164">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-165">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="e5e4c-165">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-166">smallint</span><span class="sxs-lookup"><span data-stu-id="e5e4c-166">smallint</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-167">被叫方的用户代理类型。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-167">Type of callee’s user agent.</span></span> <span data-ttu-id="e5e4c-168">有关信息，请参阅 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-168">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-169">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="e5e4c-169">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-170">nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-170">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-171">被叫方的用户代理类别。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-171">Category of callee’s user agent.</span></span> <span data-ttu-id="e5e4c-172">有关信息，请参阅 <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef 表 (QoE) In Lync Server 2013</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-172">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-173">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="e5e4c-173">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-174">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-175">呼叫者的终结点名称。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-175">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-176">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="e5e4c-176">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-177">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-177">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-178">被叫方的终结点名称。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-178">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-179">CallerOS</span><span class="sxs-lookup"><span data-stu-id="e5e4c-179">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-180">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-181">呼叫者终结点的操作系统 (OS)。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-181">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-182">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="e5e4c-182">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-183">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-183">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-184">被叫方终结点的操作系统 (OS)。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-184">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-185">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="e5e4c-185">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-186">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-186">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-187">呼叫者终结点的 CPU 名称。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-187">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-188">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="e5e4c-188">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-189">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-189">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-190">被叫方终结点的 CPU 名称。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-190">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-191">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="e5e4c-191">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-192">smallint</span><span class="sxs-lookup"><span data-stu-id="e5e4c-192">smallint</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-193">呼叫者终结点中的 CPU 内核数。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-193">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-194">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="e5e4c-194">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-195">smallint</span><span class="sxs-lookup"><span data-stu-id="e5e4c-195">smallint</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-196">被叫方的终结点中的 CPU 内核数。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-196">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-197">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="e5e4c-197">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-198">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-198">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-199">呼叫者终结点的 CPU 处理器速度。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-199">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-200">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="e5e4c-200">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-201">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-201">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-202">被叫方终结点的 CPU 处理器速度。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-202">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-203">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="e5e4c-203">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-204">tinyint</span><span class="sxs-lookup"><span data-stu-id="e5e4c-204">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-205">指示呼叫者的系统是否正在虚拟化环境中运行。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-205">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="e5e4c-206">有关详细信息，请参阅 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的终结点表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-206">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-207">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="e5e4c-207">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-208">tinyint</span><span class="sxs-lookup"><span data-stu-id="e5e4c-208">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-209">指示被叫方的系统是否正在虚拟化环境中运行。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-209">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="e5e4c-210">有关详细信息，请参阅 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的终结点表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-210">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-211">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="e5e4c-211">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e5e4c-212">相关密钥。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-212">Correlation key.</span></span> <span data-ttu-id="e5e4c-213"><a href="lync-server-2013-sessioncorrelation-table.md">在 Lync Server 2013 中从 SessionCorrelation 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-213">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-214">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="e5e4c-214">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-215">tinyint</span><span class="sxs-lookup"><span data-stu-id="e5e4c-215">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-216">有关媒体路径的信息，例如 direct 或中继。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-216">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="e5e4c-217">有关详细信息，请参阅 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-217">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-218">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="e5e4c-218">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-219">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-219">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-p111">关于呼叫者的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“用户体验质量监控服务器协议规范”。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-222">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="e5e4c-222">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-223">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-223">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-p112">关于被叫方的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“用户体验质量监控服务器协议规范”。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-226">Transport</span><span class="sxs-lookup"><span data-stu-id="e5e4c-226">Transport</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-227">tinyint</span><span class="sxs-lookup"><span data-stu-id="e5e4c-227">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-228">传输类型：0 是 UDP，1 是 TCP。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-228">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-229">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="e5e4c-229">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-230">var (50) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-230">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-231">呼叫者的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-231">IP address of the caller.</span></span> <span data-ttu-id="e5e4c-232">这可能是 IPv4 或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-232">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-233">CallerPort</span><span class="sxs-lookup"><span data-stu-id="e5e4c-233">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-234">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-234">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-235">呼叫者使用的端口。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-235">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-236">CallerInside</span><span class="sxs-lookup"><span data-stu-id="e5e4c-236">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-237">位</span><span class="sxs-lookup"><span data-stu-id="e5e4c-237">bit</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-238">指示呼叫者是否在间隔网络内：1表示呼叫者位于企业网络内，0表示呼叫者在网络外部。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-238">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-239">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="e5e4c-239">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-240">var (50) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-240">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-241">被叫方的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-241">IP address of the callee.</span></span> <span data-ttu-id="e5e4c-242">这可能是 IPv4 或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-242">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-243">CalleePort</span><span class="sxs-lookup"><span data-stu-id="e5e4c-243">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-244">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-244">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-245">被叫方所使用的端口。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-245">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-246">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="e5e4c-246">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-247">位</span><span class="sxs-lookup"><span data-stu-id="e5e4c-247">bit</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-248">指示被叫方是否位于间隔网络内：1表示被呼叫者位于企业网络内，0表示被呼叫方位于网络外部。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-248">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-249">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="e5e4c-249">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-250">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-250">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-251">呼叫者的站点名称。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-251">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-252">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="e5e4c-252">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-253">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-253">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-254">呼叫者站点的国家/地区名称。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-254">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-255">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="e5e4c-255">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-256">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-256">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-257">被叫方的站点名称。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-257">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-258">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="e5e4c-258">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-259">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-259">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-260">被叫方站点的国家/地区名称。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-260">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-261">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="e5e4c-261">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-262">var (50) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-262">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-263">呼叫者所使用的 A/V 边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-263">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="e5e4c-264">有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-264">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-265">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="e5e4c-265">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-266">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-266">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-267">呼叫者在 A/V 边缘服务中使用的端口。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-267">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-268">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="e5e4c-268">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-269">var (50) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-269">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-270">被叫方所使用的 A/V 边缘服务的 IP 地址密钥。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-270">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="e5e4c-271">有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-271">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-272">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="e5e4c-272">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-273">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-273">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-274">被叫方在 A/V 边缘服务中使用的端口。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-274">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-275">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="e5e4c-275">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-276">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-276">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-277">呼叫者的捕获设备名称。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-277">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-278">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="e5e4c-278">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-279">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-279">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-280">呼叫者的呈现设备名称。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-280">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-281">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="e5e4c-281">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-282">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-282">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-283">呼叫者的捕获设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-283">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-284">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="e5e4c-284">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-285">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-285">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-286">呼叫者的呈现设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-286">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-287">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="e5e4c-287">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-288">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-288">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-289">被叫方的捕获设备名称。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-289">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-290">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="e5e4c-290">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-291">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-291">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-292">被叫方的呈现设备名称。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-292">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-293">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="e5e4c-293">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-294">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-294">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-295">被叫方的捕获设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-295">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-296">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="e5e4c-296">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-297">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-297">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-298">被叫方的呈现设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-298">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-299">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="e5e4c-299">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-300">tinyint</span><span class="sxs-lookup"><span data-stu-id="e5e4c-300">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-301">呼叫者的网络连接类型：0 是有线，1 是无线。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-301">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-302">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="e5e4c-302">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-303">位</span><span class="sxs-lookup"><span data-stu-id="e5e4c-303">bit</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-304">指示呼叫者是否通过虚拟专用网络连接：1是虚拟专用网络 (VPN) ，0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-304">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-305">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="e5e4c-305">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-306">十进制 (18，0) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-307">呼叫者终结点的网络链接速度（以 bps 为单位）。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-307">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-308">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="e5e4c-308">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-309">tinyint</span><span class="sxs-lookup"><span data-stu-id="e5e4c-309">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-310">被叫方的网络连接类型：0 是有线，1 是无线。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-310">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-311">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="e5e4c-311">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-312">位</span><span class="sxs-lookup"><span data-stu-id="e5e4c-312">bit</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-313">指示呼叫者是否通过虚拟专用网络连接：1是虚拟专用网络 (VPN) ，0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-313">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-314">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="e5e4c-314">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-315">十进制 (18，0) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-315">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-316">被呼叫方的终结点的网络链接速度（以 bps 为单位）。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-316">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-317">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="e5e4c-317">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-318">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-318">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-319">音频会话的窄带交谈 MOS（基于两个音频流）。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-319">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-320">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="e5e4c-320">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-321">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-321">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-322">应用于指定发送端流指定的多种策略设置（TURN、API、SDP、策略服务器等）的实际带宽。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-322">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="e5e4c-323">不要将其与有效带宽混淆，因为根据带宽预估的不同，可能会降低带宽的有效性。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-323">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="e5e4c-324">这基本上是发送流可以采用带宽估计设定限制的限制的最大带宽</span><span class="sxs-lookup"><span data-stu-id="e5e4c-324">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-325">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="e5e4c-325">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-326">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-326">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-327">实时控制协议 (RTCP) 统计信息中的平均网络抖动。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-327">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-328">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="e5e4c-328">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-329">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-329">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-330">呼叫期间的最大网络抖动。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-330">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-331">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="e5e4c-331">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-332">十进制 (5、4) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-333">呼叫期间的平均数据包丢失率。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-333">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-334">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="e5e4c-334">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-335">十进制 (5、4) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-335">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-336">呼叫期间观测到的数据包丢失最大值。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-336">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-337">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="e5e4c-337">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-338">十进制 (9、4) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-338">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-339">呼叫期间出现猝发损失期间的数据包丢失的平均密度。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-339">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-340">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="e5e4c-340">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-341">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-341">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-342">呼叫期间出现猝发损失期间的数据包丢失的平均持续时间。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-342">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-343">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="e5e4c-343">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-344">十进制 (9、4) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-344">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-345">在出现猝发数据包丢失之间间隔期间的数据包丢失的平均密度。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-345">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-346">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="e5e4c-346">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-347">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-347">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-348">猝发数据包丢失间隔的平均持续时间。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-348">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-349">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="e5e4c-349">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-350">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-350">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-351">音频流的数据包计数。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-351">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-352">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="e5e4c-352">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-353">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-353">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-354">音频流的带宽预估。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-354">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-355">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="e5e4c-355">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-356">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-356">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-357">整个呼叫的网络 MOS 降级。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-357">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="e5e4c-358">范围是0.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-358">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="e5e4c-359">此指标显示由于抖动和数据包丢失而导致网络 MOS 减少的量。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-359">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="e5e4c-360">对于可接受的质量，它应小于0.5。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-360">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-361">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="e5e4c-361">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-362">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-362">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-363">呼叫期间的最大网络 MOS 降级。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-363">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-364">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="e5e4c-364">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-365">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-365">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-366">由抖动引起的网络 MOS 性能下降。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-366">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-367">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="e5e4c-367">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-368">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-368">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-369">因数据包丢失而导致的网络 MOS 降级。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-369">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-370">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="e5e4c-370">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-371">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-371">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-372">用于呼叫的音频编解码器，从 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中的 PayloadDescription 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-372">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-373">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="e5e4c-373">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-374">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-374">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-375">音频流的采样率。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-375">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-376">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e5e4c-376">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-377">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-377">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-378">呼叫者发送的音频的后模拟增益控制音频信号级别。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-378">Post-Analog Gain Control audio signal level for the audio the caller sent.</span></span> <span data-ttu-id="e5e4c-379">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-379">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e5e4c-380">为获得可接受的质量，至少应为 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-380">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="e5e4c-381">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-381">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-382">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e5e4c-382">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-383">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-383">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-384">呼叫者收到的音频的音频信号级别。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-384">Audio signal level for the audio the caller received.</span></span> <span data-ttu-id="e5e4c-385">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-385">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e5e4c-386">为获得可接受的质量，至少应为 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-386">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="e5e4c-387">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-387">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-388">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e5e4c-388">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-389">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-389">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-390">模拟声后，呼叫者发送的音频的音频噪音水平。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-390">Post-Analog Gain Control audio noise level for the audio the caller sent.</span></span> <span data-ttu-id="e5e4c-391">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-391">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e5e4c-392">为获得可接受的质量，它应小于 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-392">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="e5e4c-393">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-393">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-394">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e5e4c-394">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-395">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-395">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-396">呼叫者接收的音频的后模拟增益控制音频噪音水平。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-396">Post-Analog Gain Control audio noise level for the audio the caller received.</span></span> <span data-ttu-id="e5e4c-397">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-397">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e5e4c-398">为获得可接受的质量，它应小于 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-398">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="e5e4c-399">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-399">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-400">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="e5e4c-400">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-401">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-401">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-402">呼叫者的回显返回丢失增强功能。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-402">Echo Return Loss Enhancement for the caller.</span></span> <span data-ttu-id="e5e4c-403">此指标的单位为 dB。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-403">The unit for this metric is dB.</span></span> <span data-ttu-id="e5e4c-404">值越低表示回显越少。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-404">Lower values represent less echo.</span></span> <span data-ttu-id="e5e4c-405">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-405">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-406">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="e5e4c-406">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-407">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-407">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-408">呼叫者的扬声器呈现每5分钟的平均故障。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-408">Average glitches per five minutes for the caller’s loudspeaker rendering.</span></span> <span data-ttu-id="e5e4c-409">为了获得较高的质量，这应小于每五分钟一次。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-409">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="e5e4c-410">不是由 A/V 会议服务器、中介服务器或 IP 电话报告。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-410">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-411">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="e5e4c-411">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-412">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-412">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-413">呼叫者的麦克风捕获每5分钟的平均故障。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-413">Average glitches per five minutes for the caller’s microphone capture.</span></span> <span data-ttu-id="e5e4c-414">若要获得较高的质量，这应小于每5分钟一次。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-414">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="e5e4c-415">不是由 A/V 会议服务器、中介服务器或 IP 电话报告。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-415">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-416">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="e5e4c-416">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-417">十进制 (9，2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-417">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-418">呼叫者的麦克风设备时钟相对于 CPU 时钟的速度偏移速率。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-418">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-419">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="e5e4c-419">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-420">十进制 (9，2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-420">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-421">呼叫者的扬声器设备时钟相对于 CPU 时钟的速度偏移速率。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-421">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-422">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="e5e4c-422">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-423">十进制 (9，2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-423">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-424">呼叫的最后20秒内的麦克风捕获流的平均时间戳错误（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-424">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-425">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="e5e4c-425">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-426">十进制 (9，2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-426">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-427">呼叫者的扬声器在最近20秒内呈现流时间戳错误的平均次数（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-427">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-428">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="e5e4c-428">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-429">smallint</span><span class="sxs-lookup"><span data-stu-id="e5e4c-429">smallint</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-430">Voice switch 是一个半双工模式，具有更低的中断能力。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-430">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="e5e4c-431">有关详细信息，请参阅 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-431">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-432">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="e5e4c-432">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-433">tinyint</span><span class="sxs-lookup"><span data-stu-id="e5e4c-433">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-434">调用方的 echo 事件的原因。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-434">Causes of an echo event for the caller.</span></span> <span data-ttu-id="e5e4c-435">有关详细信息，请参阅 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-435">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-436">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="e5e4c-436">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-437">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-437">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-438">在呼叫者的麦克风捕获流中检测到回显的时间的百分比。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-438">Percentage of time when echo is detected in the caller’s microphone capture stream.</span></span> <span data-ttu-id="e5e4c-439">如果使用的是耳机，则该值应较低。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-439">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-440">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="e5e4c-440">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-441">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-441">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-442">在呼叫者的发送流中检测到回显的时间的百分比。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-442">Percentage of time when echo is detected in the caller’s sent stream.</span></span> <span data-ttu-id="e5e4c-443">发送流中的高回显百分比指示回声泄漏。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-443">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-444">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e5e4c-444">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-445">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-445">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-446">从呼叫者音频的网关接收中介服务器上的信号级别;这仅适用于中介服务器。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-446">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="e5e4c-447">此指标的单位为 dBoV。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-447">The unit of this metric is dBoV.</span></span> <span data-ttu-id="e5e4c-448">为了获得良好的质量，可接受范围应为-30 到-18 dBoV。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-448">For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-449">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e5e4c-449">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-450">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-450">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-451">从呼叫者音频的网关接收中介服务器上的信号级别。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-451">Received signal level on the Mediation Server from the Gateway for the caller’s audio.</span></span> <span data-ttu-id="e5e4c-452">这仅适用于中介服务器。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-452">This applies only to the Mediation Server.</span></span> <span data-ttu-id="e5e4c-453">此指标的单位为 dBoV。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-453">The unit of this metric is dBoV.</span></span> <span data-ttu-id="e5e4c-454">为了获得良好的质量，可接受的范围应小于-50 dBoV。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-454">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-455">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="e5e4c-455">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-456">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-456">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-457"> (AGC) 在应用于呼叫者音频的中介服务器端上的自动增益控制。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-457">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-458">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="e5e4c-458">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-459">float</span><span class="sxs-lookup"><span data-stu-id="e5e4c-459">float</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-460">到呼叫者的传入信号的根平均平方 (RMS) ，最长为呼叫的前30秒。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-460">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-461">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e5e4c-461">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-462">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-462">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-463">表示被呼叫者发送的音频的反电后增益控制音频信号级别。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-463">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent.</span></span> <span data-ttu-id="e5e4c-464">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-464">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e5e4c-465">为获得可接受的质量，至少应为 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-465">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="e5e4c-466">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-466">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-467">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e5e4c-467">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-468">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-468">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-469">被呼叫者收到的音频的音频信号级别。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-469">Audio signal level for the audio the callee received.</span></span> <span data-ttu-id="e5e4c-470">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-470">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e5e4c-471">为获得可接受的质量，至少应为 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-471">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="e5e4c-472">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-472">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-473">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e5e4c-473">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-474">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-474">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-475">对被呼叫者发送的音频进行模拟后增益控制音频噪音级别。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-475">Post-Analog Gain Control audio noise level for the audio the callee sent.</span></span> <span data-ttu-id="e5e4c-476">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-476">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e5e4c-477">为获得可接受的质量，它应小于 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-477">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="e5e4c-478">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-478">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-479">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e5e4c-479">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-480">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-480">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-481">被呼叫者接收的音频的模拟后增益控制音频噪音水平。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-481">Post-Analog Gain Control audio noise level for the audio the callee received.</span></span> <span data-ttu-id="e5e4c-482">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-482">The unit for this metric is dBmo.</span></span> <span data-ttu-id="e5e4c-483">为获得可接受的质量，它应小于 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-483">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="e5e4c-484">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-484">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-485">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="e5e4c-485">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-486">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-486">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-487">对被叫方的回显返回丢失增强。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-487">Echo Return Loss Enhancement for the callee.</span></span> <span data-ttu-id="e5e4c-488">此指标的单位为 dB。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-488">The unit for this metric is dB.</span></span> <span data-ttu-id="e5e4c-489">值越低表示回显越少。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-489">Lower values represent less echo.</span></span> <span data-ttu-id="e5e4c-490">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-490">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-491">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="e5e4c-491">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-492">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-492">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-493">被呼叫者的扬声器呈现每5分钟的平均故障。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-493">Average glitches per five minutes for the callee’s loudspeaker rendering.</span></span> <span data-ttu-id="e5e4c-494">为了获得较高的质量，这应小于每五分钟一次。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-494">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="e5e4c-495">不是由 A/V 会议服务器、中介服务器或 IP 电话报告。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-495">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-496">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="e5e4c-496">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-497">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-497">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-498">被呼叫者的麦克风捕获每5分钟的平均故障。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-498">Average glitches per five minutes for the callee’s microphone capture.</span></span> <span data-ttu-id="e5e4c-499">若要获得较高的质量，这应小于每5分钟一次。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-499">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="e5e4c-500">不是由 A/V 会议服务器、中介服务器或 IP 电话报告。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-500">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-501">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="e5e4c-501">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-502">十进制 (9，2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-502">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-503">被叫方的麦克风设备时钟相对于 CPU 时钟的时钟偏移速度。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-503">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-504">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="e5e4c-504">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-505">十进制 (9，2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-505">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-506">被叫方的扬声器设备时钟相对于 CPU 时钟的时钟偏移速度。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-506">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-507">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="e5e4c-507">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-508">十进制 (9，2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-508">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-509">呼叫的最后20秒内的麦克风捕获流的平均时间戳错误（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-509">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-510">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="e5e4c-510">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-511">十进制 (9，2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-511">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-512">被呼叫者的发言人的平均呈现流时间戳错误（以毫秒为单位）在呼叫的最后20秒中。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-512">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-513">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="e5e4c-513">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-514">smallint</span><span class="sxs-lookup"><span data-stu-id="e5e4c-514">smallint</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-515">Voice switch 是一个半双工模式，具有更低的中断能力。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-515">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="e5e4c-516">有关详细信息，请参阅 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-516">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-517">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="e5e4c-517">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-518">tinyint</span><span class="sxs-lookup"><span data-stu-id="e5e4c-518">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-519">被调用方的 echo 事件的原因。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-519">Causes of an echo event for the callee.</span></span> <span data-ttu-id="e5e4c-520">有关详细信息，请参阅 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-520">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-521">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="e5e4c-521">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-522">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-522">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-523">在被呼叫者的麦克风捕获流中检测到回显的时间的百分比。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-523">Percentage of time when echo is detected in the callee’s microphone capture stream.</span></span> <span data-ttu-id="e5e4c-524">如果使用的是耳机，则该值应较低。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-524">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-525">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="e5e4c-525">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-526">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-526">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-527">在被呼叫方的已发送流中检测到回显的时间的百分比。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-527">Percentage of time when echo is detected in the callee’s sent stream.</span></span> <span data-ttu-id="e5e4c-528">发送流中的高回显百分比指示回声泄漏。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-528">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-529">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="e5e4c-529">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-530">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-530">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-531">在中介服务器上从被呼叫者的音频的网关收到了信号级别;这仅适用于中介服务器。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-531">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="e5e4c-532">此指标的单位为 dBoV。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-532">The unit of this metric is dBoV.</span></span> <span data-ttu-id="e5e4c-533">为了获得良好的质量，可接受范围应为 [-30 至-18] dBoV。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-533">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-534">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="e5e4c-534">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-535">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-535">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-536">在中介服务器上从被呼叫者的音频的网关收到了信号级别。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-536">Received signal level on the Mediation Server from the Gateway for the callee’s audio.</span></span> <span data-ttu-id="e5e4c-537">这仅适用于中介服务器。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-537">This applies only to the Mediation Server.</span></span> <span data-ttu-id="e5e4c-538">此指标的单位为 dBoV。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-538">The unit of this metric is dBoV.</span></span> <span data-ttu-id="e5e4c-539">为了获得良好的质量，可接受的范围应小于-50 dBoV。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-539">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-540">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="e5e4c-540">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-541">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-541">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-542"> (AGC) 在应用于被呼叫者的音频的中介服务器端上的自动增益控制。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-542">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-543">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="e5e4c-543">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-544">float</span><span class="sxs-lookup"><span data-stu-id="e5e4c-544">float</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-545">最长为呼叫者的传入信号的根均值 (RMS) ，最长为呼叫的前30秒。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-545">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-546">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="e5e4c-546">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-547">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-547">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-548">通过音频康复对典型示例生成的隐藏样本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-548">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-549">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="e5e4c-549">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-550">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-550">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-551">由音频康复生成的一般示例中的延伸样本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-551">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-552">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="e5e4c-552">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-553">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-553">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-554">由音频康复生成的压缩样本的平均比率到典型示例。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-554">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-555">工程</span><span class="sxs-lookup"><span data-stu-id="e5e4c-555">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-556">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-556">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-557">RTCP 统计信息中的来回行程时间。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-557">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-558">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="e5e4c-558">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-559">int</span><span class="sxs-lookup"><span data-stu-id="e5e4c-559">int</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-560">音频流的最大来回行程时间。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-560">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-561">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="e5e4c-561">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-562">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-562">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-563">呼叫的平均宽带网络 MOS。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-563">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="e5e4c-564">此指标取决于所使用的数据包丢失、抖动和编解码器。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-564">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="e5e4c-565">范围是1.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-565">Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-566">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="e5e4c-566">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-567">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-567">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-568">用于呼叫的最小宽带网络 MOS。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-568">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-569">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="e5e4c-569">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-570">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-570">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-571">平均预测宽带侦听发送音频的 MOS 分数，包括语音级别、噪声级别和捕获设备特征。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-571">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-572">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="e5e4c-572">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-573">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-573">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-574">呼叫的最小 SendListenMOS。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-574">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-575">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="e5e4c-575">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-576">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-576">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-577">平均预测宽带侦听从网络接收的音频的 MOS 分数，包括语音级别、噪音级别、编解码器、网络状况和捕获设备特征。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-577">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-578">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="e5e4c-578">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-579">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="e5e4c-579">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-580">呼叫的最小 RecvListenMOS。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-580">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e5e4c-581">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="e5e4c-581">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-582">位</span><span class="sxs-lookup"><span data-stu-id="e5e4c-582">bit</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-583">指示是否对呼叫使用音频 FEC。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-583">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e5e4c-584">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="e5e4c-584">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-585">位</span><span class="sxs-lookup"><span data-stu-id="e5e4c-585">bit</span></span></p></td>
<td><p><span data-ttu-id="e5e4c-586">指示 p 声明的标识信息的方向;1表示流方向来自调用方的调用者;0表示流方向从被呼叫方到调用方。</span><span class="sxs-lookup"><span data-stu-id="e5e4c-586">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

