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
ms.openlocfilehash: e9b6cc13721ff249d9f8bd8bc0c38260c4ca7f55
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42211618"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="61730-102">Lync Server 2013 中的 VideoStreamDetail 视图</span><span class="sxs-lookup"><span data-stu-id="61730-102">VideoStreamDetail view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="61730-103">_**上次修改的主题：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="61730-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="61730-104">VideoStreamDetail 视图存储有关每个数据库中视频流的信息。</span><span class="sxs-lookup"><span data-stu-id="61730-104">The VideoStreamDetail View stores information about each video stream in the database.</span></span> <span data-ttu-id="61730-105">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="61730-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="61730-106">列</span><span class="sxs-lookup"><span data-stu-id="61730-106">Column</span></span></th>
<th><span data-ttu-id="61730-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="61730-107">Data Type</span></span></th>
<th><span data-ttu-id="61730-108">说明</span><span class="sxs-lookup"><span data-stu-id="61730-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="61730-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="61730-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="61730-110">datetime</span><span class="sxs-lookup"><span data-stu-id="61730-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="61730-111"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="61730-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="61730-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="61730-113">int</span><span class="sxs-lookup"><span data-stu-id="61730-113">int</span></span></p></td>
<td><p><span data-ttu-id="61730-114"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="61730-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-115">MediaLineLabel</span><span class="sxs-lookup"><span data-stu-id="61730-115">MediaLineLabel</span></span></p></td>
<td><p><span data-ttu-id="61730-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="61730-116">tinyint</span></span></p></td>
<td><p><span data-ttu-id="61730-117"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="61730-117">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-118">StreamId</span><span class="sxs-lookup"><span data-stu-id="61730-118">StreamId</span></span></p></td>
<td><p><span data-ttu-id="61730-119">int</span><span class="sxs-lookup"><span data-stu-id="61730-119">int</span></span></p></td>
<td><p><span data-ttu-id="61730-120">媒体行中的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="61730-120">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-121">StartTime</span><span class="sxs-lookup"><span data-stu-id="61730-121">StartTime</span></span></p></td>
<td><p><span data-ttu-id="61730-122">datetime</span><span class="sxs-lookup"><span data-stu-id="61730-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="61730-123">会话的开始时间。</span><span class="sxs-lookup"><span data-stu-id="61730-123">Start time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-124">EndTime</span><span class="sxs-lookup"><span data-stu-id="61730-124">EndTime</span></span></p></td>
<td><p><span data-ttu-id="61730-125">datetime</span><span class="sxs-lookup"><span data-stu-id="61730-125">datetime</span></span></p></td>
<td><p><span data-ttu-id="61730-126">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="61730-126">End time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-127">CallPriority</span><span class="sxs-lookup"><span data-stu-id="61730-127">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="61730-128">int</span><span class="sxs-lookup"><span data-stu-id="61730-128">int</span></span></p></td>
<td><p><span data-ttu-id="61730-129">呼叫的优先级。</span><span class="sxs-lookup"><span data-stu-id="61730-129">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-130">CallerPool</span><span class="sxs-lookup"><span data-stu-id="61730-130">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="61730-131">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="61730-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61730-132">呼叫者池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="61730-132">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-133">CalleePool</span><span class="sxs-lookup"><span data-stu-id="61730-133">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="61730-134">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="61730-134">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61730-135">被叫方池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="61730-135">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-136">Caller</span><span class="sxs-lookup"><span data-stu-id="61730-136">Caller</span></span></p></td>
<td><p><span data-ttu-id="61730-137">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="61730-137">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="61730-138">呼叫者的 URI。</span><span class="sxs-lookup"><span data-stu-id="61730-138">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-139">约定</span><span class="sxs-lookup"><span data-stu-id="61730-139">Callee</span></span></p></td>
<td><p><span data-ttu-id="61730-140">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="61730-140">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="61730-141">被叫方的 URI。</span><span class="sxs-lookup"><span data-stu-id="61730-141">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-142">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="61730-142">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="61730-143">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="61730-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61730-144">呼叫者的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="61730-144">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-145">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="61730-145">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="61730-146">smallint</span><span class="sxs-lookup"><span data-stu-id="61730-146">smallint</span></span></p></td>
<td><p><span data-ttu-id="61730-147">呼叫者的用户代理类型。</span><span class="sxs-lookup"><span data-stu-id="61730-147">Type of caller’s user agent.</span></span> <span data-ttu-id="61730-148">有关详细信息，请参阅<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>。</span><span class="sxs-lookup"><span data-stu-id="61730-148">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-149">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="61730-149">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="61730-150">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="61730-150">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="61730-151">呼叫者的用户代理类别。</span><span class="sxs-lookup"><span data-stu-id="61730-151">Category of caller’s user agent.</span></span> <span data-ttu-id="61730-152">有关详细信息，请参阅<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表（QoE）</a> 。</span><span class="sxs-lookup"><span data-stu-id="61730-152">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-153">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="61730-153">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="61730-154">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="61730-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61730-155">被叫方的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="61730-155">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-156">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="61730-156">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="61730-157">smallint</span><span class="sxs-lookup"><span data-stu-id="61730-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="61730-158">被叫方的用户代理类型。</span><span class="sxs-lookup"><span data-stu-id="61730-158">Type of callee’s user agent.</span></span> <span data-ttu-id="61730-159">有关信息，请参阅<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>。</span><span class="sxs-lookup"><span data-stu-id="61730-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-160">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="61730-160">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="61730-161">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="61730-161">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="61730-162">被叫方的用户代理类别。</span><span class="sxs-lookup"><span data-stu-id="61730-162">Category of callee’s user agent.</span></span> <span data-ttu-id="61730-163">有关信息，请参阅<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表（QoE）</a> 。</span><span class="sxs-lookup"><span data-stu-id="61730-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-164">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="61730-164">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="61730-165">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="61730-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61730-166">呼叫者的终结点名称。</span><span class="sxs-lookup"><span data-stu-id="61730-166">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-167">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="61730-167">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="61730-168">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="61730-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61730-169">被叫方的终结点名称。</span><span class="sxs-lookup"><span data-stu-id="61730-169">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-170">CallerOS</span><span class="sxs-lookup"><span data-stu-id="61730-170">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="61730-171">nvarchar</span><span class="sxs-lookup"><span data-stu-id="61730-171">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61730-172">呼叫者终结点的操作系统 (OS)。</span><span class="sxs-lookup"><span data-stu-id="61730-172">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-173">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="61730-173">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="61730-174">nvarchar</span><span class="sxs-lookup"><span data-stu-id="61730-174">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61730-175">被叫方终结点的操作系统 (OS)。</span><span class="sxs-lookup"><span data-stu-id="61730-175">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-176">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="61730-176">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="61730-177">nvarchar</span><span class="sxs-lookup"><span data-stu-id="61730-177">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61730-178">呼叫者终结点的 CPU 名称。</span><span class="sxs-lookup"><span data-stu-id="61730-178">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-179">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="61730-179">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="61730-180">nvarchar</span><span class="sxs-lookup"><span data-stu-id="61730-180">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61730-181">被叫方终结点的 CPU 名称。</span><span class="sxs-lookup"><span data-stu-id="61730-181">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-182">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="61730-182">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="61730-183">smallint</span><span class="sxs-lookup"><span data-stu-id="61730-183">smallint</span></span></p></td>
<td><p><span data-ttu-id="61730-184">呼叫者的终结点的 CPU 内核数。</span><span class="sxs-lookup"><span data-stu-id="61730-184">Number of CPU cores of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-185">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="61730-185">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="61730-186">smallint</span><span class="sxs-lookup"><span data-stu-id="61730-186">smallint</span></span></p></td>
<td><p><span data-ttu-id="61730-187">被叫方的终结点的 CPU 内核数。</span><span class="sxs-lookup"><span data-stu-id="61730-187">Number of CPU cores of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-188">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="61730-188">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="61730-189">int</span><span class="sxs-lookup"><span data-stu-id="61730-189">int</span></span></p></td>
<td><p><span data-ttu-id="61730-190">呼叫者终结点的 CPU 处理器速度。</span><span class="sxs-lookup"><span data-stu-id="61730-190">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-191">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="61730-191">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="61730-192">int</span><span class="sxs-lookup"><span data-stu-id="61730-192">int</span></span></p></td>
<td><p><span data-ttu-id="61730-193">被叫方终结点的 CPU 处理器速度。</span><span class="sxs-lookup"><span data-stu-id="61730-193">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-194">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="61730-194">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="61730-195">tinyint</span><span class="sxs-lookup"><span data-stu-id="61730-195">tinyint</span></span></p></td>
<td><p><span data-ttu-id="61730-196">指示呼叫者的系统是否正在虚拟化环境中运行。</span><span class="sxs-lookup"><span data-stu-id="61730-196">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="61730-197">有关详细信息，请参阅<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的终结点表</a>。</span><span class="sxs-lookup"><span data-stu-id="61730-197">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-198">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="61730-198">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="61730-199">tinyint</span><span class="sxs-lookup"><span data-stu-id="61730-199">tinyint</span></span></p></td>
<td><p><span data-ttu-id="61730-200">指示被叫方的系统是否正在虚拟化环境中运行。</span><span class="sxs-lookup"><span data-stu-id="61730-200">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="61730-201">有关详细信息，请参阅<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的终结点表</a>。</span><span class="sxs-lookup"><span data-stu-id="61730-201">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-202">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="61730-202">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="61730-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="61730-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="61730-204">有关媒体路径的信息，例如直接或中继。</span><span class="sxs-lookup"><span data-stu-id="61730-204">Information about media path, such as direct or relayed.</span></span> <span data-ttu-id="61730-205">有关详细信息，请参阅<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</span><span class="sxs-lookup"><span data-stu-id="61730-205">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-206">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="61730-206">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="61730-207">int</span><span class="sxs-lookup"><span data-stu-id="61730-207">int</span></span></p></td>
<td><p><span data-ttu-id="61730-p109">关于呼叫者的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“用户体验质量监控服务器协议规范”。</span><span class="sxs-lookup"><span data-stu-id="61730-p109">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-210">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="61730-210">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="61730-211">int</span><span class="sxs-lookup"><span data-stu-id="61730-211">int</span></span></p></td>
<td><p><span data-ttu-id="61730-p110">关于被叫方的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“用户体验质量监控服务器协议规范”。</span><span class="sxs-lookup"><span data-stu-id="61730-p110">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-214">Transport</span><span class="sxs-lookup"><span data-stu-id="61730-214">Transport</span></span></p></td>
<td><p><span data-ttu-id="61730-215">int</span><span class="sxs-lookup"><span data-stu-id="61730-215">int</span></span></p></td>
<td><p><span data-ttu-id="61730-216">传输类型：0 是 UDP，1 是 TCP。</span><span class="sxs-lookup"><span data-stu-id="61730-216">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-217">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="61730-217">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="61730-218">var （50）</span><span class="sxs-lookup"><span data-stu-id="61730-218">var(50)</span></span></p></td>
<td><p><span data-ttu-id="61730-219">呼叫者的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="61730-219">IP address of the caller.</span></span> <span data-ttu-id="61730-220">这可能是 IPv4 地址或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="61730-220">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-221">CallerPort</span><span class="sxs-lookup"><span data-stu-id="61730-221">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="61730-222">int</span><span class="sxs-lookup"><span data-stu-id="61730-222">int</span></span></p></td>
<td><p><span data-ttu-id="61730-223">呼叫者使用的端口。</span><span class="sxs-lookup"><span data-stu-id="61730-223">Port used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-224">CallerInside</span><span class="sxs-lookup"><span data-stu-id="61730-224">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="61730-225">位</span><span class="sxs-lookup"><span data-stu-id="61730-225">bit</span></span></p></td>
<td><p><span data-ttu-id="61730-p112">指示呼叫者是否位于组织网络的内部。1 表示呼叫者位于企业网络内部，0 表示呼叫者位于该网络外部。</span><span class="sxs-lookup"><span data-stu-id="61730-p112">Indicates whether the caller is inside the organization network. 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-228">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="61730-228">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="61730-229">var （50）</span><span class="sxs-lookup"><span data-stu-id="61730-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="61730-230">被叫方的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="61730-230">IP address of the callee.</span></span> <span data-ttu-id="61730-231">这可能是 IPv4 或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="61730-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-232">CalleePort</span><span class="sxs-lookup"><span data-stu-id="61730-232">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="61730-233">int</span><span class="sxs-lookup"><span data-stu-id="61730-233">int</span></span></p></td>
<td><p><span data-ttu-id="61730-234">被叫方所使用的端口。</span><span class="sxs-lookup"><span data-stu-id="61730-234">Port used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-235">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="61730-235">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="61730-236">位</span><span class="sxs-lookup"><span data-stu-id="61730-236">bit</span></span></p></td>
<td><p><span data-ttu-id="61730-237">指示呼叫者是否位于组织网络的内部。1 表示被叫方位于企业网络内部，0 表示被叫方位于该网络外部。</span><span class="sxs-lookup"><span data-stu-id="61730-237">Indicates whether the caller is inside the organization network.1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-238">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="61730-238">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="61730-239">nvarchar</span><span class="sxs-lookup"><span data-stu-id="61730-239">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61730-240">呼叫者的站点名称。</span><span class="sxs-lookup"><span data-stu-id="61730-240">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-241">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="61730-241">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="61730-242">nvarchar</span><span class="sxs-lookup"><span data-stu-id="61730-242">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61730-243">呼叫者站点的国家/地区名称。</span><span class="sxs-lookup"><span data-stu-id="61730-243">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-244">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="61730-244">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="61730-245">nvarchar</span><span class="sxs-lookup"><span data-stu-id="61730-245">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61730-246">被叫方的站点名称。</span><span class="sxs-lookup"><span data-stu-id="61730-246">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-247">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="61730-247">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="61730-248">nvarchar</span><span class="sxs-lookup"><span data-stu-id="61730-248">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="61730-249">被叫方站点的国家/地区名称。</span><span class="sxs-lookup"><span data-stu-id="61730-249">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-250">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="61730-250">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="61730-251">var （50）</span><span class="sxs-lookup"><span data-stu-id="61730-251">var(50)</span></span></p></td>
<td><p><span data-ttu-id="61730-252">呼叫者所使用的 A/V 边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="61730-252">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="61730-253">有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a>。</span><span class="sxs-lookup"><span data-stu-id="61730-253">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-254">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="61730-254">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="61730-255">int</span><span class="sxs-lookup"><span data-stu-id="61730-255">int</span></span></p></td>
<td><p><span data-ttu-id="61730-256">呼叫者使用的 A/V 边缘服务上的端口。</span><span class="sxs-lookup"><span data-stu-id="61730-256">Port on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-257">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="61730-257">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="61730-258">var （50）</span><span class="sxs-lookup"><span data-stu-id="61730-258">var(50)</span></span></p></td>
<td><p><span data-ttu-id="61730-259">被叫方所使用的 A/V 边缘服务的 IP 地址密钥。</span><span class="sxs-lookup"><span data-stu-id="61730-259">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="61730-260">有关详细信息，请参阅<a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a>。</span><span class="sxs-lookup"><span data-stu-id="61730-260">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-261">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="61730-261">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="61730-262">int</span><span class="sxs-lookup"><span data-stu-id="61730-262">int</span></span></p></td>
<td><p><span data-ttu-id="61730-263">被叫方使用的 A/V 边缘服务上的端口。</span><span class="sxs-lookup"><span data-stu-id="61730-263">Port on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-264">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="61730-264">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="61730-265">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="61730-265">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61730-266">呼叫者的捕获设备名称。</span><span class="sxs-lookup"><span data-stu-id="61730-266">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-267">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="61730-267">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="61730-268">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="61730-268">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61730-269">呼叫者的呈现设备名称。</span><span class="sxs-lookup"><span data-stu-id="61730-269">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-270">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="61730-270">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="61730-271">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="61730-271">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61730-272">呼叫者的捕获设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="61730-272">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-273">CallerRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="61730-273">CallerRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="61730-274">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="61730-274">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61730-275">呼叫者的呈现设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="61730-275">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-276">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="61730-276">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="61730-277">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="61730-277">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61730-278">被叫方的捕获设备名称。</span><span class="sxs-lookup"><span data-stu-id="61730-278">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-279">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="61730-279">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="61730-280">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="61730-280">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61730-281">被叫方的呈现设备名称。</span><span class="sxs-lookup"><span data-stu-id="61730-281">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-282">CalleCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="61730-282">CalleCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="61730-283">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="61730-283">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61730-284">被叫方的捕获设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="61730-284">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-285">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="61730-285">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="61730-286">varchar （256）</span><span class="sxs-lookup"><span data-stu-id="61730-286">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="61730-287">被叫方的呈现设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="61730-287">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-288">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="61730-288">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="61730-289">tinyint</span><span class="sxs-lookup"><span data-stu-id="61730-289">tinyint</span></span></p></td>
<td><p><span data-ttu-id="61730-290">呼叫者的网络连接类型：0 是有线，1 是无线。</span><span class="sxs-lookup"><span data-stu-id="61730-290">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-291">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="61730-291">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="61730-292">位</span><span class="sxs-lookup"><span data-stu-id="61730-292">bit</span></span></p></td>
<td><p><span data-ttu-id="61730-p116">指示呼叫者是否通过虚拟专用网络连接：1 是虚拟专用网络 (VPN)，0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="61730-p116">Indicates whether or not the caller connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-295">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="61730-295">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="61730-296">小数（18，）</span><span class="sxs-lookup"><span data-stu-id="61730-296">decimal(18,)</span></span></p></td>
<td><p><span data-ttu-id="61730-297">呼叫者终结点的网络链接速度（以 bps 为单位）。</span><span class="sxs-lookup"><span data-stu-id="61730-297">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-298">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="61730-298">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="61730-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="61730-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="61730-300">被叫方的网络连接类型：0 是有线，1 是无线。</span><span class="sxs-lookup"><span data-stu-id="61730-300">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-301">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="61730-301">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="61730-302">位</span><span class="sxs-lookup"><span data-stu-id="61730-302">bit</span></span></p></td>
<td><p><span data-ttu-id="61730-p117">指示被叫方是否通过虚拟专用网络连接：1 是虚拟专用网络 (VPN)，0 是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="61730-p117">Indicates whether or not the callee connected over a virtual private network. 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-305">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="61730-305">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="61730-306">小数（18，0）</span><span class="sxs-lookup"><span data-stu-id="61730-306">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="61730-307">被叫方终结点的网络链接速度（以 bps 为单位）。</span><span class="sxs-lookup"><span data-stu-id="61730-307">Network link speed for the callee’s endpoint (in bps).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-308">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="61730-308">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="61730-309">decimal （3，2）</span><span class="sxs-lookup"><span data-stu-id="61730-309">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="61730-310">音频会话的窄带交谈 MOS（基于两个音频流）。</span><span class="sxs-lookup"><span data-stu-id="61730-310">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-311">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="61730-311">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="61730-312">int</span><span class="sxs-lookup"><span data-stu-id="61730-312">int</span></span></p></td>
<td><p><span data-ttu-id="61730-p118">应用于指定发送端流指定的多种策略设置（TURN、API、SDP、策略服务器等）的实际带宽。不要将其与有效带宽混淆，因为根据带宽预估的不同，可能会降低带宽的有效性。这基本上是发送流可禁止带宽预估设定的限制的最大带宽。</span><span class="sxs-lookup"><span data-stu-id="61730-p118">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on). This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate. This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-316">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="61730-316">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="61730-317">int</span><span class="sxs-lookup"><span data-stu-id="61730-317">int</span></span></p></td>
<td><p><span data-ttu-id="61730-318">实时控制协议 (RTCP) 统计信息中的平均网络抖动。</span><span class="sxs-lookup"><span data-stu-id="61730-318">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-319">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="61730-319">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="61730-320">int</span><span class="sxs-lookup"><span data-stu-id="61730-320">int</span></span></p></td>
<td><p><span data-ttu-id="61730-321">呼叫期间的最大网络抖动。</span><span class="sxs-lookup"><span data-stu-id="61730-321">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-322">工程</span><span class="sxs-lookup"><span data-stu-id="61730-322">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="61730-323">int</span><span class="sxs-lookup"><span data-stu-id="61730-323">int</span></span></p></td>
<td><p><span data-ttu-id="61730-324">RTCP 统计信息中的来回行程时间。</span><span class="sxs-lookup"><span data-stu-id="61730-324">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-325">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="61730-325">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="61730-326">int</span><span class="sxs-lookup"><span data-stu-id="61730-326">int</span></span></p></td>
<td><p><span data-ttu-id="61730-327">音频流的最大来回行程时间。</span><span class="sxs-lookup"><span data-stu-id="61730-327">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-328">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="61730-328">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="61730-329">decimal （5，4）</span><span class="sxs-lookup"><span data-stu-id="61730-329">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="61730-330">呼叫期间的平均数据包丢失率。</span><span class="sxs-lookup"><span data-stu-id="61730-330">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-331">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="61730-331">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="61730-332">decimal （5，4）</span><span class="sxs-lookup"><span data-stu-id="61730-332">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="61730-333">呼叫期间观测到的数据包丢失最大值。</span><span class="sxs-lookup"><span data-stu-id="61730-333">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-334">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="61730-334">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="61730-335">int</span><span class="sxs-lookup"><span data-stu-id="61730-335">int</span></span></p></td>
<td><p><span data-ttu-id="61730-336">视频流的数据包计数（实时传输协议，RTP）。</span><span class="sxs-lookup"><span data-stu-id="61730-336">Packet count for the video stream (Real Time Transport Protocol, RTP).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-337">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="61730-337">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="61730-338">int</span><span class="sxs-lookup"><span data-stu-id="61730-338">int</span></span></p></td>
<td><p><span data-ttu-id="61730-339">音频流的带宽预估。</span><span class="sxs-lookup"><span data-stu-id="61730-339">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-340">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="61730-340">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="61730-341">int</span><span class="sxs-lookup"><span data-stu-id="61730-341">int</span></span></p></td>
<td><p><span data-ttu-id="61730-342">用于呼叫的音频编解码器，从<a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中的 PayloadDescription 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="61730-342">Audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-343">VideoResolution</span><span class="sxs-lookup"><span data-stu-id="61730-343">VideoResolution</span></span></p></td>
<td><p><span data-ttu-id="61730-344">char （9）</span><span class="sxs-lookup"><span data-stu-id="61730-344">char(9)</span></span></p></td>
<td><p><span data-ttu-id="61730-p119">视频的分辨率（像素宽乘以像素高）。报告为字符串。</span><span class="sxs-lookup"><span data-stu-id="61730-p119">Resolution of the video in pixels width multiplied by pixels height. Reported as a string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-347">VideoBitRateAvg</span><span class="sxs-lookup"><span data-stu-id="61730-347">VideoBitRateAvg</span></span></p></td>
<td><p><span data-ttu-id="61730-348">int</span><span class="sxs-lookup"><span data-stu-id="61730-348">int</span></span></p></td>
<td><p><span data-ttu-id="61730-349">视频流的平均比特率。</span><span class="sxs-lookup"><span data-stu-id="61730-349">Average bit rate of the video stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-350">InboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="61730-350">InboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="61730-351">小数（9，4）</span><span class="sxs-lookup"><span data-stu-id="61730-351">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="61730-352">接收的视频帧速率。</span><span class="sxs-lookup"><span data-stu-id="61730-352">Frame rate of video received.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-353">OutboundVideoFrameRateAvg</span><span class="sxs-lookup"><span data-stu-id="61730-353">OutboundVideoFrameRateAvg</span></span></p></td>
<td><p><span data-ttu-id="61730-354">小数（9，4）</span><span class="sxs-lookup"><span data-stu-id="61730-354">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="61730-355">发送的视频帧速率。</span><span class="sxs-lookup"><span data-stu-id="61730-355">Frame rate of video sent.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-356">ViideoBitRateMax</span><span class="sxs-lookup"><span data-stu-id="61730-356">ViideoBitRateMax</span></span></p></td>
<td><p><span data-ttu-id="61730-357">int</span><span class="sxs-lookup"><span data-stu-id="61730-357">int</span></span></p></td>
<td><p><span data-ttu-id="61730-358">视频会话期间的最大视频比特率。</span><span class="sxs-lookup"><span data-stu-id="61730-358">Maximum video bit rate during the video session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-359">VideoPacketLossRate</span><span class="sxs-lookup"><span data-stu-id="61730-359">VideoPacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="61730-360">小数（9，4）</span><span class="sxs-lookup"><span data-stu-id="61730-360">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="61730-361">视频数据包丢失的比特率。</span><span class="sxs-lookup"><span data-stu-id="61730-361">Rate at which video packets were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-362">VideoFrameLossRate</span><span class="sxs-lookup"><span data-stu-id="61730-362">VideoFrameLossRate</span></span></p></td>
<td><p><span data-ttu-id="61730-363">decimal （9.4）</span><span class="sxs-lookup"><span data-stu-id="61730-363">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="61730-364">丢失的全部视频帧的百分比。</span><span class="sxs-lookup"><span data-stu-id="61730-364">Percentage of total video frames that are lost.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-365">VideoFEC</span><span class="sxs-lookup"><span data-stu-id="61730-365">VideoFEC</span></span></p></td>
<td><p><span data-ttu-id="61730-366">位</span><span class="sxs-lookup"><span data-stu-id="61730-366">bit</span></span></p></td>
<td><p><span data-ttu-id="61730-367">未使用。</span><span class="sxs-lookup"><span data-stu-id="61730-367">Not used.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-368">VideoAllocateBWAvg</span><span class="sxs-lookup"><span data-stu-id="61730-368">VideoAllocateBWAvg</span></span></p></td>
<td><p><span data-ttu-id="61730-369">int</span><span class="sxs-lookup"><span data-stu-id="61730-369">int</span></span></p></td>
<td><p><span data-ttu-id="61730-370">为视频分配的平均带宽量。</span><span class="sxs-lookup"><span data-stu-id="61730-370">Average amount of bandwidth allocated for video.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="61730-371">VideoLocalFrameLossPercentageAvg</span><span class="sxs-lookup"><span data-stu-id="61730-371">VideoLocalFrameLossPercentageAvg</span></span></p></td>
<td><p><span data-ttu-id="61730-372">decimal （9.4）</span><span class="sxs-lookup"><span data-stu-id="61730-372">decimal(9.4)</span></span></p></td>
<td><p><span data-ttu-id="61730-373">丢失的全部视频帧的百分比。</span><span class="sxs-lookup"><span data-stu-id="61730-373">Percentage of total video frames that were lost.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="61730-374">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="61730-374">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="61730-375">位</span><span class="sxs-lookup"><span data-stu-id="61730-375">bit</span></span></p></td>
<td><p><span data-ttu-id="61730-p120">已断言标识信息的流方向。1 表示流方向从呼叫者到被叫方；0 表示流方向从被叫方到呼叫者。</span><span class="sxs-lookup"><span data-stu-id="61730-p120">Stream direction for p-asserted identity information. 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

