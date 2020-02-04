---
title: Lync Server 2013： VideoStreamDetail 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfa754fbcc24377b07bab3b13473adb1c5e953ea
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741972"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="e71ab-102">Lync Server 2013 中的 VideoStreamDetail 视图</span><span class="sxs-lookup"><span data-stu-id="e71ab-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e71ab-103">_**主题上次修改时间：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="e71ab-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="e71ab-104">VideoStreamDetail 视图存储有关数据库中每个视频流的信息。</span><span class="sxs-lookup"><span data-stu-id="e71ab-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="e71ab-105">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="e71ab-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e71ab-106">列</span><span class="sxs-lookup"><span data-stu-id="e71ab-106">Column</span></span></th>
<th><span data-ttu-id="e71ab-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="e71ab-107">Data Type</span></span></th>
<th><span data-ttu-id="e71ab-108">说明</span><span class="sxs-lookup"><span data-stu-id="e71ab-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="e71ab-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="e71ab-110">datetime</span><span class="sxs-lookup"><span data-stu-id="e71ab-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="e71ab-111">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e71ab-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="e71ab-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="e71ab-113">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-113">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-114">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e71ab-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="e71ab-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="e71ab-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="e71ab-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e71ab-117">从<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e71ab-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-118">StreamId</span><span class="sxs-lookup"><span data-stu-id="e71ab-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="e71ab-119">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-119">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-120">媒体行内的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="e71ab-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="e71ab-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="e71ab-122">datetime</span><span class="sxs-lookup"><span data-stu-id="e71ab-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="e71ab-123">会话的开始时间。</span><span class="sxs-lookup"><span data-stu-id="e71ab-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="e71ab-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="e71ab-125">datetime</span><span class="sxs-lookup"><span data-stu-id="e71ab-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="e71ab-126">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="e71ab-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="e71ab-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="e71ab-128">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-128">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-129">通话的优先级。</span><span class="sxs-lookup"><span data-stu-id="e71ab-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="e71ab-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="e71ab-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e71ab-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-132">呼叫方池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e71ab-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="e71ab-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="e71ab-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e71ab-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-135">被调用池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="e71ab-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-136">呼叫者</span><span class="sxs-lookup"><span data-stu-id="e71ab-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="e71ab-137">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="e71ab-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-138">调用方的 URI。</span><span class="sxs-lookup"><span data-stu-id="e71ab-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-139">被叫方</span><span class="sxs-lookup"><span data-stu-id="e71ab-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="e71ab-140">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="e71ab-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-141">被调用方的 URI。</span><span class="sxs-lookup"><span data-stu-id="e71ab-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="e71ab-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="e71ab-143">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e71ab-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-144">呼叫方的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="e71ab-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="e71ab-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="e71ab-146">smallint</span><span class="sxs-lookup"><span data-stu-id="e71ab-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="e71ab-147">呼叫方的用户代理的类型。</span><span class="sxs-lookup"><span data-stu-id="e71ab-147">Type of caller’s user agent.</span></span> <span data-ttu-id="e71ab-148">有关详细信息，请参阅<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e71ab-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="e71ab-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="e71ab-150">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="e71ab-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-151">呼叫者的用户代理类别。</span><span class="sxs-lookup"><span data-stu-id="e71ab-151">Category of caller’s user agent.</span></span> <span data-ttu-id="e71ab-152">有关详细信息，请参阅<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表（QoE）</a> 。</span><span class="sxs-lookup"><span data-stu-id="e71ab-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="e71ab-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="e71ab-154">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e71ab-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-155">被呼叫方的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="e71ab-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="e71ab-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="e71ab-157">smallint</span><span class="sxs-lookup"><span data-stu-id="e71ab-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="e71ab-158">被调用方的用户代理的类型。</span><span class="sxs-lookup"><span data-stu-id="e71ab-158">Type of callee’s user agent.</span></span> <span data-ttu-id="e71ab-159">有关信息，请参阅<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e71ab-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="e71ab-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="e71ab-161">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="e71ab-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-162">被呼叫方的用户代理类别。</span><span class="sxs-lookup"><span data-stu-id="e71ab-162">Category of callee’s user agent.</span></span> <span data-ttu-id="e71ab-163">有关信息，请参阅<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表（QoE）</a> 。</span><span class="sxs-lookup"><span data-stu-id="e71ab-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="e71ab-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="e71ab-165">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e71ab-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-166">调用方的终结点名称。</span><span class="sxs-lookup"><span data-stu-id="e71ab-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="e71ab-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="e71ab-168">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e71ab-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-169">被调用方的终结点名称。</span><span class="sxs-lookup"><span data-stu-id="e71ab-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-170">CallerOS</span><span class="sxs-lookup"><span data-stu-id="e71ab-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="e71ab-171">nvarchar</span><span class="sxs-lookup"><span data-stu-id="e71ab-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-172">呼叫方终结点的操作系统（OS）。</span><span class="sxs-lookup"><span data-stu-id="e71ab-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="e71ab-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="e71ab-174">nvarchar</span><span class="sxs-lookup"><span data-stu-id="e71ab-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-175">被调用方终结点的操作系统（OS）。</span><span class="sxs-lookup"><span data-stu-id="e71ab-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="e71ab-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="e71ab-177">nvarchar</span><span class="sxs-lookup"><span data-stu-id="e71ab-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-178">呼叫方终结点的 CPU 名称。</span><span class="sxs-lookup"><span data-stu-id="e71ab-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="e71ab-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="e71ab-180">nvarchar</span><span class="sxs-lookup"><span data-stu-id="e71ab-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-181">被调用方终结点的 CPU 名称。</span><span class="sxs-lookup"><span data-stu-id="e71ab-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="e71ab-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="e71ab-183">smallint</span><span class="sxs-lookup"><span data-stu-id="e71ab-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="e71ab-184">呼叫方终结点的 CPU 内核数。</span><span class="sxs-lookup"><span data-stu-id="e71ab-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="e71ab-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="e71ab-186">smallint</span><span class="sxs-lookup"><span data-stu-id="e71ab-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="e71ab-187">被调用方终结点的 CPU 内核数。</span><span class="sxs-lookup"><span data-stu-id="e71ab-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-188">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="e71ab-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="e71ab-189">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-189">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-190">呼叫方终结点的 CPU 处理器速度。</span><span class="sxs-lookup"><span data-stu-id="e71ab-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="e71ab-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="e71ab-192">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-192">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-193">被调用方终结点的 CPU 处理器速度。</span><span class="sxs-lookup"><span data-stu-id="e71ab-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="e71ab-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="e71ab-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="e71ab-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e71ab-196">指示呼叫者的系统是否在虚拟化环境中运行。</span><span class="sxs-lookup"><span data-stu-id="e71ab-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="e71ab-197">有关详细信息，请参阅<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的终结点表</a>。</span><span class="sxs-lookup"><span data-stu-id="e71ab-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="e71ab-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="e71ab-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="e71ab-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e71ab-200">指示被调用方的系统是否在虚拟化环境中运行。</span><span class="sxs-lookup"><span data-stu-id="e71ab-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="e71ab-201">有关详细信息，请参阅<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的终结点表</a>。</span><span class="sxs-lookup"><span data-stu-id="e71ab-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="e71ab-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="e71ab-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="e71ab-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e71ab-204">有关媒体路径（如直接或中继）的信息。</span><span class="sxs-lookup"><span data-stu-id="e71ab-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="e71ab-205">有关详细信息，请参阅<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e71ab-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="e71ab-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="e71ab-207">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-207">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-208">有关在呼叫者的位标志中描述的交互式连接建立（ICE）流程的信息。</span><span class="sxs-lookup"><span data-stu-id="e71ab-208">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller.</span></span> <span data-ttu-id="e71ab-209">有关详细信息，请参阅体验质量监视服务器协议规范。</span><span class="sxs-lookup"><span data-stu-id="e71ab-209">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="e71ab-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="e71ab-211">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-211">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-212">有关被调用方的位标志中所述的交互式连接建立（ICE）流程的信息。</span><span class="sxs-lookup"><span data-stu-id="e71ab-212">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee.</span></span> <span data-ttu-id="e71ab-213">有关详细信息，请参阅体验质量监视服务器协议规范。</span><span class="sxs-lookup"><span data-stu-id="e71ab-213">For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-214">Transport</span><span class="sxs-lookup"><span data-stu-id="e71ab-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="e71ab-215">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-215">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-216">传输类型：0是 UDP，1是 TCP。</span><span class="sxs-lookup"><span data-stu-id="e71ab-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="e71ab-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e71ab-218">var （50）</span><span class="sxs-lookup"><span data-stu-id="e71ab-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-219">呼叫方的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e71ab-219">IP address of the caller.</span></span> <span data-ttu-id="e71ab-220">这可能是 IPv4 地址或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="e71ab-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="e71ab-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="e71ab-222">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-222">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-223">呼叫方使用的端口。</span><span class="sxs-lookup"><span data-stu-id="e71ab-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="e71ab-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="e71ab-225">bit</span><span class="sxs-lookup"><span data-stu-id="e71ab-225">bit</span></span></p></td>
<td><p><span data-ttu-id="e71ab-226">指示呼叫者是否在组织网络内。</span><span class="sxs-lookup"><span data-stu-id="e71ab-226">Indicates whether the caller is inside the organization network.</span></span> <span data-ttu-id="e71ab-227">1表示呼叫方位于企业网络内，0表示呼叫方位于网络外部。</span><span class="sxs-lookup"><span data-stu-id="e71ab-227">1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="e71ab-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e71ab-229">var （50）</span><span class="sxs-lookup"><span data-stu-id="e71ab-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-230">被呼叫方的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e71ab-230">IP address of the callee.</span></span> <span data-ttu-id="e71ab-231">这可能是 IPv4 地址或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="e71ab-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="e71ab-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="e71ab-233">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-233">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-234">被呼叫方使用的端口。</span><span class="sxs-lookup"><span data-stu-id="e71ab-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="e71ab-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="e71ab-236">bit</span><span class="sxs-lookup"><span data-stu-id="e71ab-236">bit</span></span></p></td>
<td><p><span data-ttu-id="e71ab-237">指示呼叫者是否在组织网络内。1表示被呼叫方位于企业网络内，0表示被呼叫方在网络外部。</span><span class="sxs-lookup"><span data-stu-id="e71ab-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="e71ab-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="e71ab-239">nvarchar</span><span class="sxs-lookup"><span data-stu-id="e71ab-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-240">呼叫者站点的名称。</span><span class="sxs-lookup"><span data-stu-id="e71ab-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="e71ab-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="e71ab-242">nvarchar</span><span class="sxs-lookup"><span data-stu-id="e71ab-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-243">呼叫方网站的国家/地区的名称。</span><span class="sxs-lookup"><span data-stu-id="e71ab-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="e71ab-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="e71ab-245">nvarchar</span><span class="sxs-lookup"><span data-stu-id="e71ab-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-246">被调用方的网站的名称。</span><span class="sxs-lookup"><span data-stu-id="e71ab-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="e71ab-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="e71ab-248">nvarchar</span><span class="sxs-lookup"><span data-stu-id="e71ab-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-249">被呼叫方网站的国家/地区的名称。</span><span class="sxs-lookup"><span data-stu-id="e71ab-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="e71ab-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e71ab-251">var （50）</span><span class="sxs-lookup"><span data-stu-id="e71ab-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-252">呼叫方使用的 A/V 边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="e71ab-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="e71ab-253">有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</span><span class="sxs-lookup"><span data-stu-id="e71ab-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="e71ab-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="e71ab-255">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-255">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-256">呼叫方使用的 A/V 边缘服务上的端口。</span><span class="sxs-lookup"><span data-stu-id="e71ab-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="e71ab-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="e71ab-258">var （50）</span><span class="sxs-lookup"><span data-stu-id="e71ab-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-259">被呼叫方使用的 A/V 边缘服务的 IP 地址密钥。</span><span class="sxs-lookup"><span data-stu-id="e71ab-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="e71ab-260">有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中</a>的 "IPAddress" 表。</span><span class="sxs-lookup"><span data-stu-id="e71ab-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="e71ab-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="e71ab-262">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-262">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-263">被呼叫方使用的 A/V 边缘服务上的端口。</span><span class="sxs-lookup"><span data-stu-id="e71ab-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="e71ab-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="e71ab-265">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="e71ab-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-266">呼叫方的捕获设备名称。</span><span class="sxs-lookup"><span data-stu-id="e71ab-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="e71ab-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="e71ab-268">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="e71ab-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-269">调用方的呈现设备名称。</span><span class="sxs-lookup"><span data-stu-id="e71ab-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="e71ab-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e71ab-271">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="e71ab-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-272">呼叫方的捕获设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="e71ab-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="e71ab-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e71ab-274">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="e71ab-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-275">呼叫方的呈现设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="e71ab-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-276">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="e71ab-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="e71ab-277">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="e71ab-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-278">被调用方的捕获设备名称。</span><span class="sxs-lookup"><span data-stu-id="e71ab-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="e71ab-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="e71ab-280">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="e71ab-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-281">被调用方的呈现设备名称。</span><span class="sxs-lookup"><span data-stu-id="e71ab-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-282">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="e71ab-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e71ab-283">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="e71ab-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-284">被调用方的捕获设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="e71ab-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="e71ab-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="e71ab-286">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="e71ab-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-287">被调用方的呈现设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="e71ab-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="e71ab-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="e71ab-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="e71ab-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e71ab-290">呼叫者的网络连接类型：0是 "有线"，1是 "无线"。</span><span class="sxs-lookup"><span data-stu-id="e71ab-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="e71ab-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="e71ab-292">bit</span><span class="sxs-lookup"><span data-stu-id="e71ab-292">bit</span></span></p></td>
<td><p><span data-ttu-id="e71ab-293">指示呼叫者是否通过虚拟专用网络连接。</span><span class="sxs-lookup"><span data-stu-id="e71ab-293">Indicates whether or not the caller connected over a virtual private network.</span></span> <span data-ttu-id="e71ab-294">1是虚拟专用网络（VPN），0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="e71ab-294">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="e71ab-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="e71ab-296">十进制（18，）</span><span class="sxs-lookup"><span data-stu-id="e71ab-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-297">呼叫方终结点的网络链接速度（以 bps 为实现）。</span><span class="sxs-lookup"><span data-stu-id="e71ab-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="e71ab-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="e71ab-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="e71ab-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="e71ab-300">被呼叫方的网络连接类型：0是 "有线"，1是 "无线"。</span><span class="sxs-lookup"><span data-stu-id="e71ab-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="e71ab-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="e71ab-302">bit</span><span class="sxs-lookup"><span data-stu-id="e71ab-302">bit</span></span></p></td>
<td><p><span data-ttu-id="e71ab-303">指示被呼叫方是否通过虚拟专用网络进行连接。</span><span class="sxs-lookup"><span data-stu-id="e71ab-303">Indicates whether or not the callee connected over a virtual private network.</span></span> <span data-ttu-id="e71ab-304">1是虚拟专用网络（VPN），0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="e71ab-304">1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="e71ab-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="e71ab-306">十进制（18，0）</span><span class="sxs-lookup"><span data-stu-id="e71ab-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-307">被调用方终结点的网络链接速度（以 bps 为 bps）。</span><span class="sxs-lookup"><span data-stu-id="e71ab-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="e71ab-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="e71ab-309">十进制（3，2）</span><span class="sxs-lookup"><span data-stu-id="e71ab-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-310">音频会话的 Narrowband 对话 MOS （基于两个音频流）。</span><span class="sxs-lookup"><span data-stu-id="e71ab-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="e71ab-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="e71ab-312">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-312">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-313">在给定各种策略设置（TURN、API、SDP、策略服务器等）的情况下，应用到给定发送端流的实际带宽。</span><span class="sxs-lookup"><span data-stu-id="e71ab-313">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="e71ab-314">此操作不会与有效的带宽混淆，因为根据带宽估计，可能会有较低的有效带宽。</span><span class="sxs-lookup"><span data-stu-id="e71ab-314">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="e71ab-315">这基本上是发送流可以通过带宽估计限制限制的最大带宽。</span><span class="sxs-lookup"><span data-stu-id="e71ab-315">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="e71ab-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="e71ab-317">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-317">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-318">实时控制协议（RTCP）统计信息的平均网络抖动。</span><span class="sxs-lookup"><span data-stu-id="e71ab-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="e71ab-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="e71ab-320">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-320">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-321">通话期间网络抖动的最大值。</span><span class="sxs-lookup"><span data-stu-id="e71ab-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-322">RoundTrip</span><span class="sxs-lookup"><span data-stu-id="e71ab-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="e71ab-323">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-323">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-324">从 RTCP 统计数据往返的时间。</span><span class="sxs-lookup"><span data-stu-id="e71ab-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="e71ab-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="e71ab-326">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-326">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-327">音频流的最大往返行程时间。</span><span class="sxs-lookup"><span data-stu-id="e71ab-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="e71ab-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="e71ab-329">十进制（5，4）</span><span class="sxs-lookup"><span data-stu-id="e71ab-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-330">通话期间平均数据包丢失速率。</span><span class="sxs-lookup"><span data-stu-id="e71ab-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="e71ab-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="e71ab-332">十进制（5，4）</span><span class="sxs-lookup"><span data-stu-id="e71ab-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-333">通话过程中观察到的最大数据包丢失。</span><span class="sxs-lookup"><span data-stu-id="e71ab-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="e71ab-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="e71ab-335">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-335">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-336">视频流的数据包计数（实时传输协议、RTP）。</span><span class="sxs-lookup"><span data-stu-id="e71ab-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-337">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="e71ab-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="e71ab-338">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-338">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-339">音频流的带宽估计。</span><span class="sxs-lookup"><span data-stu-id="e71ab-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="e71ab-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="e71ab-341">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-341">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-342">用于呼叫的音频编解码器，从<a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中的 PayloadDescription 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e71ab-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="e71ab-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="e71ab-344">char （9）</span><span class="sxs-lookup"><span data-stu-id="e71ab-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-345">以像素为单位的视频分辨率（以像素为单位）乘以像素高度。</span><span class="sxs-lookup"><span data-stu-id="e71ab-345">Resolution of the video in pixels width multiplied by pixels height.</span></span> <span data-ttu-id="e71ab-346">报告为字符串。</span><span class="sxs-lookup"><span data-stu-id="e71ab-346">Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="e71ab-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="e71ab-348">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-348">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-349">视频流的平均比特率。</span><span class="sxs-lookup"><span data-stu-id="e71ab-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="e71ab-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="e71ab-351">十进制（9，4）</span><span class="sxs-lookup"><span data-stu-id="e71ab-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-352">收到的视频的帧速率。</span><span class="sxs-lookup"><span data-stu-id="e71ab-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="e71ab-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="e71ab-354">十进制（9，4）</span><span class="sxs-lookup"><span data-stu-id="e71ab-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-355">已发送视频的帧速率。</span><span class="sxs-lookup"><span data-stu-id="e71ab-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="e71ab-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="e71ab-357">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-357">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-358">视频会话期间的最大视频比特率。</span><span class="sxs-lookup"><span data-stu-id="e71ab-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-359">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="e71ab-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="e71ab-360">十进制（9，4）</span><span class="sxs-lookup"><span data-stu-id="e71ab-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-361">视频数据包丢失的速率。</span><span class="sxs-lookup"><span data-stu-id="e71ab-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="e71ab-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="e71ab-363">十进制（9.4）</span><span class="sxs-lookup"><span data-stu-id="e71ab-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-364">丢失的视频帧总数的百分比。</span><span class="sxs-lookup"><span data-stu-id="e71ab-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="e71ab-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="e71ab-366">bit</span><span class="sxs-lookup"><span data-stu-id="e71ab-366">bit</span></span></p></td>
<td><p><span data-ttu-id="e71ab-367">未使用。</span><span class="sxs-lookup"><span data-stu-id="e71ab-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="e71ab-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="e71ab-369">int</span><span class="sxs-lookup"><span data-stu-id="e71ab-369">int</span></span></p></td>
<td><p><span data-ttu-id="e71ab-370">为视频分配的平均带宽量。</span><span class="sxs-lookup"><span data-stu-id="e71ab-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e71ab-371">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="e71ab-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="e71ab-372">十进制（9.4）</span><span class="sxs-lookup"><span data-stu-id="e71ab-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="e71ab-373">丢失的视频帧总数的百分比。</span><span class="sxs-lookup"><span data-stu-id="e71ab-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e71ab-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="e71ab-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="e71ab-375">bit</span><span class="sxs-lookup"><span data-stu-id="e71ab-375">bit</span></span></p></td>
<td><p><span data-ttu-id="e71ab-376">P 声明的标识信息的流方向。</span><span class="sxs-lookup"><span data-stu-id="e71ab-376">Stream direction for p-asserted identity information.</span></span> <span data-ttu-id="e71ab-377">1表示流方向从调用方到被调用方;0表示流方向来自被调用方的调用方。</span><span class="sxs-lookup"><span data-stu-id="e71ab-377">1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

