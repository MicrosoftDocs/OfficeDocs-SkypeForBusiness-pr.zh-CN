---
title: Lync Server 2013： VideoStreamDetail 视图
description: Lync Server 2013： VideoStreamDetail 视图。
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
ms.openlocfilehash: a3f420c292627d15fd0d54f2eba01c565a49a72d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48567968"
---
# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="c887f-103">Lync Server 2013 中的 VideoStreamDetail 视图</span><span class="sxs-lookup"><span data-stu-id="c887f-103">VideoStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c887f-104">_**上次修改的主题：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="c887f-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="c887f-105">VideoStreamDetail 视图存储有关每个数据库中视频流的信息。</span><span class="sxs-lookup"><span data-stu-id="c887f-105">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="c887f-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="c887f-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c887f-107">列</span><span class="sxs-lookup"><span data-stu-id="c887f-107">Column</span></span></th>
<th><span data-ttu-id="c887f-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="c887f-108">Data Type</span></span></th>
<th><span data-ttu-id="c887f-109">说明</span><span class="sxs-lookup"><span data-stu-id="c887f-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c887f-110">SessionTime</span><span class="sxs-lookup"><span data-stu-id="c887f-110">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="c887f-111">datetime</span><span class="sxs-lookup"><span data-stu-id="c887f-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="c887f-112"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="c887f-112">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-113">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="c887f-113">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="c887f-114">int</span><span class="sxs-lookup"><span data-stu-id="c887f-114">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-115"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="c887f-115">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-116">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="c887f-116">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="c887f-117">tinyint</span><span class="sxs-lookup"><span data-stu-id="c887f-117">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c887f-118"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="c887f-118">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-119">StreamId</span><span class="sxs-lookup"><span data-stu-id="c887f-119">StreamId</span></span></p></td>
<td><p><span data-ttu-id="c887f-120">int</span><span class="sxs-lookup"><span data-stu-id="c887f-120">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-121">媒体行中的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="c887f-121">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-122">StartTime</span><span class="sxs-lookup"><span data-stu-id="c887f-122">StartTime</span></span></p></td>
<td><p><span data-ttu-id="c887f-123">datetime</span><span class="sxs-lookup"><span data-stu-id="c887f-123">datetime</span></span></p></td>
<td><p><span data-ttu-id="c887f-124">会话的开始时间。</span><span class="sxs-lookup"><span data-stu-id="c887f-124">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-125">EndTime</span><span class="sxs-lookup"><span data-stu-id="c887f-125">EndTime</span></span></p></td>
<td><p><span data-ttu-id="c887f-126">datetime</span><span class="sxs-lookup"><span data-stu-id="c887f-126">datetime</span></span></p></td>
<td><p><span data-ttu-id="c887f-127">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="c887f-127">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-128">CallPriority</span><span class="sxs-lookup"><span data-stu-id="c887f-128">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="c887f-129">int</span><span class="sxs-lookup"><span data-stu-id="c887f-129">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-130">呼叫的优先级。</span><span class="sxs-lookup"><span data-stu-id="c887f-130">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-131">CallerPool</span><span class="sxs-lookup"><span data-stu-id="c887f-131">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="c887f-132">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="c887f-132">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c887f-133">呼叫者池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c887f-133">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-134">CalleePool</span><span class="sxs-lookup"><span data-stu-id="c887f-134">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="c887f-135">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="c887f-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c887f-136">被叫方池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="c887f-136">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-137">Caller</span><span class="sxs-lookup"><span data-stu-id="c887f-137">Caller</span></span></p></td>
<td><p><span data-ttu-id="c887f-138">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="c887f-138">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c887f-139">呼叫者的 URI。</span><span class="sxs-lookup"><span data-stu-id="c887f-139">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-140">约定</span><span class="sxs-lookup"><span data-stu-id="c887f-140">Callee</span></span></p></td>
<td><p><span data-ttu-id="c887f-141">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="c887f-141">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="c887f-142">被叫方的 URI。</span><span class="sxs-lookup"><span data-stu-id="c887f-142">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-143">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="c887f-143">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="c887f-144">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="c887f-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c887f-145">呼叫者的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="c887f-145">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-146">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="c887f-146">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="c887f-147">smallint</span><span class="sxs-lookup"><span data-stu-id="c887f-147">smallint</span></span></p></td>
<td><p><span data-ttu-id="c887f-148">呼叫者的用户代理类型。</span><span class="sxs-lookup"><span data-stu-id="c887f-148">Type of caller’s user agent.</span></span> <span data-ttu-id="c887f-149">有关详细信息，请参阅 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="c887f-149">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-150">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="c887f-150">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="c887f-151">nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="c887f-151">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="c887f-152">呼叫者的用户代理类别。</span><span class="sxs-lookup"><span data-stu-id="c887f-152">Category of caller’s user agent.</span></span> <span data-ttu-id="c887f-153">有关详细信息，请参阅 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表 (QoE) </a> 。</span><span class="sxs-lookup"><span data-stu-id="c887f-153">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-154">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="c887f-154">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="c887f-155">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="c887f-155">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c887f-156">被叫方的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="c887f-156">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-157">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="c887f-157">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="c887f-158">smallint</span><span class="sxs-lookup"><span data-stu-id="c887f-158">smallint</span></span></p></td>
<td><p><span data-ttu-id="c887f-159">被叫方的用户代理类型。</span><span class="sxs-lookup"><span data-stu-id="c887f-159">Type of callee’s user agent.</span></span> <span data-ttu-id="c887f-160">有关信息，请参阅 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="c887f-160">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-161">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="c887f-161">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="c887f-162">nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="c887f-162">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="c887f-163">被叫方的用户代理类别。</span><span class="sxs-lookup"><span data-stu-id="c887f-163">Category of callee’s user agent.</span></span> <span data-ttu-id="c887f-164">有关信息，请参阅 <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef 表 (QoE) In Lync Server 2013</a> 。</span><span class="sxs-lookup"><span data-stu-id="c887f-164">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-165">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="c887f-165">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="c887f-166">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="c887f-166">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c887f-167">呼叫者的终结点名称。</span><span class="sxs-lookup"><span data-stu-id="c887f-167">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-168">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="c887f-168">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="c887f-169">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="c887f-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c887f-170">被叫方的终结点名称。</span><span class="sxs-lookup"><span data-stu-id="c887f-170">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-171">CallerOS</span><span class="sxs-lookup"><span data-stu-id="c887f-171">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="c887f-172">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="c887f-172">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c887f-173">呼叫者终结点的操作系统 (OS)。</span><span class="sxs-lookup"><span data-stu-id="c887f-173">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-174">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="c887f-174">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="c887f-175">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="c887f-175">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c887f-176">被叫方终结点的操作系统 (OS)。</span><span class="sxs-lookup"><span data-stu-id="c887f-176">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-177">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="c887f-177">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="c887f-178">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="c887f-178">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c887f-179">呼叫者终结点的 CPU 名称。</span><span class="sxs-lookup"><span data-stu-id="c887f-179">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-180">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="c887f-180">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="c887f-181">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="c887f-181">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c887f-182">被叫方终结点的 CPU 名称。</span><span class="sxs-lookup"><span data-stu-id="c887f-182">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-183">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="c887f-183">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="c887f-184">smallint</span><span class="sxs-lookup"><span data-stu-id="c887f-184">smallint</span></span></p></td>
<td><p><span data-ttu-id="c887f-185">呼叫者的终结点的 CPU 内核数。</span><span class="sxs-lookup"><span data-stu-id="c887f-185">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-186">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="c887f-186">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="c887f-187">smallint</span><span class="sxs-lookup"><span data-stu-id="c887f-187">smallint</span></span></p></td>
<td><p><span data-ttu-id="c887f-188">被叫方的终结点的 CPU 内核数。</span><span class="sxs-lookup"><span data-stu-id="c887f-188">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-189">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="c887f-189">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="c887f-190">int</span><span class="sxs-lookup"><span data-stu-id="c887f-190">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-191">呼叫者终结点的 CPU 处理器速度。</span><span class="sxs-lookup"><span data-stu-id="c887f-191">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-192">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="c887f-192">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="c887f-193">int</span><span class="sxs-lookup"><span data-stu-id="c887f-193">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-194">被叫方终结点的 CPU 处理器速度。</span><span class="sxs-lookup"><span data-stu-id="c887f-194">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-195">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="c887f-195">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="c887f-196">tinyint</span><span class="sxs-lookup"><span data-stu-id="c887f-196">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c887f-197">指示呼叫者的系统是否正在虚拟化环境中运行。</span><span class="sxs-lookup"><span data-stu-id="c887f-197">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="c887f-198">有关详细信息，请参阅 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的终结点表</a> 。</span><span class="sxs-lookup"><span data-stu-id="c887f-198">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-199">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="c887f-199">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="c887f-200">tinyint</span><span class="sxs-lookup"><span data-stu-id="c887f-200">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c887f-201">指示被叫方的系统是否正在虚拟化环境中运行。</span><span class="sxs-lookup"><span data-stu-id="c887f-201">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="c887f-202">有关详细信息，请参阅 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的终结点表</a> 。</span><span class="sxs-lookup"><span data-stu-id="c887f-202">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-203">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="c887f-203">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="c887f-204">tinyint</span><span class="sxs-lookup"><span data-stu-id="c887f-204">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c887f-205">有关媒体路径的信息，例如直接或中继。</span><span class="sxs-lookup"><span data-stu-id="c887f-205">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="c887f-206">有关详细信息，请参阅 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="c887f-206">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-207">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="c887f-207">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="c887f-208">int</span><span class="sxs-lookup"><span data-stu-id="c887f-208">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-p109">关于呼叫者的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“用户体验质量监控服务器协议规范”。</span><span class="sxs-lookup"><span data-stu-id="c887f-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-211">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="c887f-211">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="c887f-212">int</span><span class="sxs-lookup"><span data-stu-id="c887f-212">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-p110">关于被叫方的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“用户体验质量监控服务器协议规范”。</span><span class="sxs-lookup"><span data-stu-id="c887f-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-215">Transport</span><span class="sxs-lookup"><span data-stu-id="c887f-215">Transport</span></span></p></td>
<td><p><span data-ttu-id="c887f-216">int</span><span class="sxs-lookup"><span data-stu-id="c887f-216">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-217">传输类型：0 是 UDP，1 是 TCP。</span><span class="sxs-lookup"><span data-stu-id="c887f-217">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-218">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="c887f-218">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="c887f-219">var (50) </span><span class="sxs-lookup"><span data-stu-id="c887f-219">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c887f-220">呼叫者的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c887f-220">IP address of the caller.</span></span> <span data-ttu-id="c887f-221">这可能是 IPv4 或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="c887f-221">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-222">CallerPort</span><span class="sxs-lookup"><span data-stu-id="c887f-222">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="c887f-223">int</span><span class="sxs-lookup"><span data-stu-id="c887f-223">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-224">呼叫者使用的端口。</span><span class="sxs-lookup"><span data-stu-id="c887f-224">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-225">CallerInside</span><span class="sxs-lookup"><span data-stu-id="c887f-225">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="c887f-226">位</span><span class="sxs-lookup"><span data-stu-id="c887f-226">bit</span></span></p></td>
<td><p><span data-ttu-id="c887f-p112">指示呼叫者是否位于组织网络的内部。1 表示呼叫者位于企业网络内部，0 表示呼叫者位于该网络外部。</span><span class="sxs-lookup"><span data-stu-id="c887f-p112">Indicates whether the caller is inside the organization network. 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-229">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="c887f-229">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="c887f-230">var (50) </span><span class="sxs-lookup"><span data-stu-id="c887f-230">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c887f-231">被叫方的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c887f-231">IP address of the callee.</span></span> <span data-ttu-id="c887f-232">这可能是 IPv4 或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="c887f-232">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-233">CalleePort</span><span class="sxs-lookup"><span data-stu-id="c887f-233">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="c887f-234">int</span><span class="sxs-lookup"><span data-stu-id="c887f-234">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-235">被叫方所使用的端口。</span><span class="sxs-lookup"><span data-stu-id="c887f-235">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-236">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="c887f-236">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="c887f-237">位</span><span class="sxs-lookup"><span data-stu-id="c887f-237">bit</span></span></p></td>
<td><p><span data-ttu-id="c887f-238">指示呼叫者是否位于组织网络的内部。1 表示被叫方位于企业网络内部，0 表示被叫方位于该网络外部。</span><span class="sxs-lookup"><span data-stu-id="c887f-238">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-239">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="c887f-239">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="c887f-240">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="c887f-240">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c887f-241">呼叫者的站点名称。</span><span class="sxs-lookup"><span data-stu-id="c887f-241">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-242">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="c887f-242">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="c887f-243">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="c887f-243">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c887f-244">呼叫者站点的国家/地区名称。</span><span class="sxs-lookup"><span data-stu-id="c887f-244">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-245">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="c887f-245">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="c887f-246">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="c887f-246">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c887f-247">被叫方的站点名称。</span><span class="sxs-lookup"><span data-stu-id="c887f-247">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-248">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="c887f-248">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="c887f-249">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="c887f-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="c887f-250">被叫方站点的国家/地区名称。</span><span class="sxs-lookup"><span data-stu-id="c887f-250">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-251">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="c887f-251">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="c887f-252">var (50) </span><span class="sxs-lookup"><span data-stu-id="c887f-252">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c887f-253">呼叫者所使用的 A/V 边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="c887f-253">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="c887f-254">有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="c887f-254">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-255">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="c887f-255">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="c887f-256">int</span><span class="sxs-lookup"><span data-stu-id="c887f-256">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-257">呼叫者使用的 A/V 边缘服务上的端口。</span><span class="sxs-lookup"><span data-stu-id="c887f-257">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-258">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="c887f-258">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="c887f-259">var (50) </span><span class="sxs-lookup"><span data-stu-id="c887f-259">var(50)</span></span></p></td>
<td><p><span data-ttu-id="c887f-260">被叫方所使用的 A/V 边缘服务的 IP 地址密钥。</span><span class="sxs-lookup"><span data-stu-id="c887f-260">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="c887f-261">有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="c887f-261">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-262">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="c887f-262">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="c887f-263">int</span><span class="sxs-lookup"><span data-stu-id="c887f-263">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-264">被叫方使用的 A/V 边缘服务上的端口。</span><span class="sxs-lookup"><span data-stu-id="c887f-264">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-265">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="c887f-265">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="c887f-266">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="c887f-266">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c887f-267">呼叫者的捕获设备名称。</span><span class="sxs-lookup"><span data-stu-id="c887f-267">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-268">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="c887f-268">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="c887f-269">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="c887f-269">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c887f-270">呼叫者的呈现设备名称。</span><span class="sxs-lookup"><span data-stu-id="c887f-270">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-271">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="c887f-271">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="c887f-272">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="c887f-272">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c887f-273">呼叫者的捕获设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="c887f-273">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-274">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="c887f-274">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="c887f-275">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="c887f-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c887f-276">呼叫者的呈现设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="c887f-276">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-277">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="c887f-277">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="c887f-278">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="c887f-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c887f-279">被叫方的捕获设备名称。</span><span class="sxs-lookup"><span data-stu-id="c887f-279">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-280">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="c887f-280">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="c887f-281">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="c887f-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c887f-282">被叫方的呈现设备名称。</span><span class="sxs-lookup"><span data-stu-id="c887f-282">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-283">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="c887f-283">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="c887f-284">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="c887f-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c887f-285">被叫方的捕获设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="c887f-285">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-286">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="c887f-286">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="c887f-287">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="c887f-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="c887f-288">被叫方的呈现设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="c887f-288">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-289">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="c887f-289">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="c887f-290">tinyint</span><span class="sxs-lookup"><span data-stu-id="c887f-290">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c887f-291">呼叫者的网络连接类型：0 是有线，1 是无线。</span><span class="sxs-lookup"><span data-stu-id="c887f-291">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-292">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="c887f-292">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="c887f-293">位</span><span class="sxs-lookup"><span data-stu-id="c887f-293">bit</span></span></p></td>
<td><p><span data-ttu-id="c887f-p116">指示呼叫者是否通过虚拟专用网络连接：1 是虚拟专用网络 (VPN)，0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="c887f-p116">Indicates whether or not the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-296">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="c887f-296">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="c887f-297">十进制 (18，) </span><span class="sxs-lookup"><span data-stu-id="c887f-297">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="c887f-298">呼叫者终结点的网络链接速度（以 bps 为单位）。</span><span class="sxs-lookup"><span data-stu-id="c887f-298">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-299">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="c887f-299">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="c887f-300">tinyint</span><span class="sxs-lookup"><span data-stu-id="c887f-300">tinyint</span></span></p></td>
<td><p><span data-ttu-id="c887f-301">被叫方的网络连接类型：0 是有线，1 是无线。</span><span class="sxs-lookup"><span data-stu-id="c887f-301">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-302">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="c887f-302">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="c887f-303">位</span><span class="sxs-lookup"><span data-stu-id="c887f-303">bit</span></span></p></td>
<td><p><span data-ttu-id="c887f-p117">指示被叫方是否通过虚拟专用网络连接：1 是虚拟专用网络 (VPN)，0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="c887f-p117">Indicates whether or not the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-306">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="c887f-306">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="c887f-307">十进制 (18，0) </span><span class="sxs-lookup"><span data-stu-id="c887f-307">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="c887f-308">被叫方终结点的网络链接速度（以 bps 为单位）。</span><span class="sxs-lookup"><span data-stu-id="c887f-308">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-309">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="c887f-309">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="c887f-310">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="c887f-310">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="c887f-311">音频会话的窄带交谈 MOS（基于两个音频流）。</span><span class="sxs-lookup"><span data-stu-id="c887f-311">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-312">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="c887f-312">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="c887f-313">int</span><span class="sxs-lookup"><span data-stu-id="c887f-313">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-p118">应用于指定发送端流指定的多种策略设置（TURN、API、SDP、策略服务器等）的实际带宽。不要将其与有效带宽混淆，因为根据带宽预估的不同，可能会降低带宽的有效性。这基本上是发送流可禁止带宽预估设定的限制的最大带宽。</span><span class="sxs-lookup"><span data-stu-id="c887f-p118">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-317">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="c887f-317">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="c887f-318">int</span><span class="sxs-lookup"><span data-stu-id="c887f-318">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-319">实时控制协议 (RTCP) 统计信息中的平均网络抖动。</span><span class="sxs-lookup"><span data-stu-id="c887f-319">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-320">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="c887f-320">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="c887f-321">int</span><span class="sxs-lookup"><span data-stu-id="c887f-321">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-322">呼叫期间的最大网络抖动。</span><span class="sxs-lookup"><span data-stu-id="c887f-322">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-323">工程</span><span class="sxs-lookup"><span data-stu-id="c887f-323">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="c887f-324">int</span><span class="sxs-lookup"><span data-stu-id="c887f-324">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-325">RTCP 统计信息中的来回行程时间。</span><span class="sxs-lookup"><span data-stu-id="c887f-325">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-326">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="c887f-326">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="c887f-327">int</span><span class="sxs-lookup"><span data-stu-id="c887f-327">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-328">音频流的最大来回行程时间。</span><span class="sxs-lookup"><span data-stu-id="c887f-328">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-329">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="c887f-329">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="c887f-330">十进制 (5、4) </span><span class="sxs-lookup"><span data-stu-id="c887f-330">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="c887f-331">呼叫期间的平均数据包丢失率。</span><span class="sxs-lookup"><span data-stu-id="c887f-331">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-332">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="c887f-332">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="c887f-333">十进制 (5、4) </span><span class="sxs-lookup"><span data-stu-id="c887f-333">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="c887f-334">呼叫期间观测到的数据包丢失最大值。</span><span class="sxs-lookup"><span data-stu-id="c887f-334">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-335">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="c887f-335">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="c887f-336">int</span><span class="sxs-lookup"><span data-stu-id="c887f-336">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-337">视频流的数据包计数（实时传输协议，RTP）。</span><span class="sxs-lookup"><span data-stu-id="c887f-337">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-338">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="c887f-338">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="c887f-339">int</span><span class="sxs-lookup"><span data-stu-id="c887f-339">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-340">音频流的带宽预估。</span><span class="sxs-lookup"><span data-stu-id="c887f-340">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-341">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="c887f-341">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="c887f-342">int</span><span class="sxs-lookup"><span data-stu-id="c887f-342">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-343">用于呼叫的音频编解码器，从 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中的 PayloadDescription 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="c887f-343">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-344">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="c887f-344">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="c887f-345">char (9) </span><span class="sxs-lookup"><span data-stu-id="c887f-345">char(9)</span></span></p></td>
<td><p><span data-ttu-id="c887f-p119">视频的分辨率（像素宽乘以像素高）。报告为字符串。</span><span class="sxs-lookup"><span data-stu-id="c887f-p119">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-348">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="c887f-348">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="c887f-349">int</span><span class="sxs-lookup"><span data-stu-id="c887f-349">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-350">视频流的平均比特率。</span><span class="sxs-lookup"><span data-stu-id="c887f-350">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-351">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="c887f-351">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="c887f-352">十进制 (9、4) </span><span class="sxs-lookup"><span data-stu-id="c887f-352">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="c887f-353">接收的视频帧速率。</span><span class="sxs-lookup"><span data-stu-id="c887f-353">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-354">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="c887f-354">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="c887f-355">十进制 (9、4) </span><span class="sxs-lookup"><span data-stu-id="c887f-355">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="c887f-356">发送的视频帧速率。</span><span class="sxs-lookup"><span data-stu-id="c887f-356">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-357">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="c887f-357">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="c887f-358">int</span><span class="sxs-lookup"><span data-stu-id="c887f-358">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-359">视频会话期间的最大视频比特率。</span><span class="sxs-lookup"><span data-stu-id="c887f-359">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-360">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="c887f-360">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="c887f-361">十进制 (9、4) </span><span class="sxs-lookup"><span data-stu-id="c887f-361">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="c887f-362">视频数据包丢失的比特率。</span><span class="sxs-lookup"><span data-stu-id="c887f-362">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-363">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="c887f-363">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="c887f-364">十进制 (9.4) </span><span class="sxs-lookup"><span data-stu-id="c887f-364">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="c887f-365">丢失的全部视频帧的百分比。</span><span class="sxs-lookup"><span data-stu-id="c887f-365">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-366">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="c887f-366">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="c887f-367">位</span><span class="sxs-lookup"><span data-stu-id="c887f-367">bit</span></span></p></td>
<td><p><span data-ttu-id="c887f-368">未使用。</span><span class="sxs-lookup"><span data-stu-id="c887f-368">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-369">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="c887f-369">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="c887f-370">int</span><span class="sxs-lookup"><span data-stu-id="c887f-370">int</span></span></p></td>
<td><p><span data-ttu-id="c887f-371">为视频分配的平均带宽量。</span><span class="sxs-lookup"><span data-stu-id="c887f-371">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c887f-372">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="c887f-372">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="c887f-373">十进制 (9.4) </span><span class="sxs-lookup"><span data-stu-id="c887f-373">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="c887f-374">丢失的全部视频帧的百分比。</span><span class="sxs-lookup"><span data-stu-id="c887f-374">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c887f-375">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="c887f-375">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="c887f-376">位</span><span class="sxs-lookup"><span data-stu-id="c887f-376">bit</span></span></p></td>
<td><p><span data-ttu-id="c887f-p120">已断言标识信息的流方向。1 表示流方向从呼叫者到被叫方；0 表示流方向从被叫方到呼叫者。</span><span class="sxs-lookup"><span data-stu-id="c887f-p120">Stream direction for p-asserted identity information. 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

