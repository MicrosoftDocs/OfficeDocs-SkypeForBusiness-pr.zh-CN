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
ms.openlocfilehash: 4a9abfbc214e72cf059250910ecec4ad3bcdba33
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515779"
---
# <a name="audiostreamdetail-view-in-lync-server-2013"></a><span data-ttu-id="f2ab7-102">Lync Server 2013 中的 AudioStreamDetail 视图</span><span class="sxs-lookup"><span data-stu-id="f2ab7-102">AudioStreamDetail view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f2ab7-103">_**上次修改的主题：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="f2ab7-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="f2ab7-104">AudioStreamDetail 视图存储有关数据库中每个音频流的信息。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-104">The AudioStreamDetail View stores information about each audio stream in the database.</span></span> <span data-ttu-id="f2ab7-105">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f2ab7-106">列</span><span class="sxs-lookup"><span data-stu-id="f2ab7-106">Column</span></span></th>
<th><span data-ttu-id="f2ab7-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="f2ab7-107">Data Type</span></span></th>
<th><span data-ttu-id="f2ab7-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="f2ab7-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-109">SessionTime</span><span class="sxs-lookup"><span data-stu-id="f2ab7-109">SessionTime</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-110">datetime</span><span class="sxs-lookup"><span data-stu-id="f2ab7-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-111"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-111">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-112">SessionSeq</span><span class="sxs-lookup"><span data-stu-id="f2ab7-112">SessionSeq</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-113">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-113">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-114"><a href="lync-server-2013-medialine-table.md">在 Lync Server 2013 中从 MediaLine 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-114">Referenced from the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-115">StreamId</span><span class="sxs-lookup"><span data-stu-id="f2ab7-115">StreamId</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-116">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-116">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-117">媒体行中的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-117">Unique ID within a media line.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-118">StartTime</span><span class="sxs-lookup"><span data-stu-id="f2ab7-118">StartTime</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-119">datetime</span><span class="sxs-lookup"><span data-stu-id="f2ab7-119">datetime</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-120">会话的开始时间。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-120">Start time of the session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-121">EndTime</span><span class="sxs-lookup"><span data-stu-id="f2ab7-121">EndTime</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-122">datetime</span><span class="sxs-lookup"><span data-stu-id="f2ab7-122">datetime</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-123">会话的结束时间。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-123">End time of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-124">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="f2ab7-124">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-125">位</span><span class="sxs-lookup"><span data-stu-id="f2ab7-125">bit</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-126">对话框类别：0是用于中介服务器腿的 Lync 服务器;1是中介服务器到 PSTN 网关腿。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-126">Dialog category: 0 is the Lync Server to Mediation Server leg; 1 is the Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-127">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="f2ab7-127">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-128">位</span><span class="sxs-lookup"><span data-stu-id="f2ab7-128">bit</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-129">指示是否绕过呼叫的标志。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-129">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-130">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="f2ab7-130">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-131">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-131">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-132">如果存在，则指示即使绕过 Id 匹配也不会绕过呼叫。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-132">If present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="f2ab7-133">仅定义了一个值：</span><span class="sxs-lookup"><span data-stu-id="f2ab7-133">Only one value is defined:</span></span></p>
<p><span data-ttu-id="f2ab7-134">0x0001 –默认网络适配器的绕过旁路 ID。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-134">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-135">CallPriority</span><span class="sxs-lookup"><span data-stu-id="f2ab7-135">CallPriority</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-136">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-136">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-137">呼叫的优先级。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-137">Priority of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-138">CallerPool</span><span class="sxs-lookup"><span data-stu-id="f2ab7-138">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-139">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-140">呼叫者池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-140">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-141">CalleePool</span><span class="sxs-lookup"><span data-stu-id="f2ab7-141">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-142">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-143">被叫方池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-143">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-144">Caller</span><span class="sxs-lookup"><span data-stu-id="f2ab7-144">Caller</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-145">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-146">呼叫者的 URI。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-146">Caller’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-147">约定</span><span class="sxs-lookup"><span data-stu-id="f2ab7-147">Callee</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-148">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-148">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-149">被叫方的 URI。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-149">Callee’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-150">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="f2ab7-150">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-151">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-152">呼叫者的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-152">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-153">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="f2ab7-153">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-154">smallint</span><span class="sxs-lookup"><span data-stu-id="f2ab7-154">smallint</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-155">呼叫者的用户代理的类型。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-155">Type of the caller’s user agent.</span></span> <span data-ttu-id="f2ab7-156">有关详细信息，请参阅 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-156">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-157">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="f2ab7-157">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-158">nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-158">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-159">呼叫者的用户代理的类别。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-159">Category of the caller’s user agent.</span></span> <span data-ttu-id="f2ab7-160">有关详细信息，请参阅 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表 (QoE) </a> 。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-160">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-161">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="f2ab7-161">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-162">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-162">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-163">被叫方的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-163">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-164">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="f2ab7-164">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-165">smallint</span><span class="sxs-lookup"><span data-stu-id="f2ab7-165">smallint</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-166">被叫方的用户代理类型。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-166">Type of callee’s user agent.</span></span> <span data-ttu-id="f2ab7-167">有关信息，请参阅 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-167">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-168">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="f2ab7-168">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-169">nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-169">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-170">被叫方的用户代理类别。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-170">Category of callee’s user agent.</span></span> <span data-ttu-id="f2ab7-171">有关信息，请参阅 <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef 表 (QoE) In Lync Server 2013</a> 。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-171">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-172">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="f2ab7-172">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-173">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-174">呼叫者的终结点名称。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-174">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-175">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="f2ab7-175">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-176">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-177">被叫方的终结点名称。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-177">Callee’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-178">CallerOS</span><span class="sxs-lookup"><span data-stu-id="f2ab7-178">CallerOS</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-179">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-179">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-180">呼叫者终结点的操作系统 (OS)。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-180">Operating system (OS) of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-181">CalleeOS</span><span class="sxs-lookup"><span data-stu-id="f2ab7-181">CalleeOS</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-182">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-182">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-183">被叫方终结点的操作系统 (OS)。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-183">Operating system (OS) of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-184">CallerCPUName</span><span class="sxs-lookup"><span data-stu-id="f2ab7-184">CallerCPUName</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-185">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-185">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-186">呼叫者终结点的 CPU 名称。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-186">CPU name of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-187">CalleeCPUName</span><span class="sxs-lookup"><span data-stu-id="f2ab7-187">CalleeCPUName</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-188">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-188">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-189">被叫方终结点的 CPU 名称。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-189">CPU name of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-190">CallerCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="f2ab7-190">CallerCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-191">smallint</span><span class="sxs-lookup"><span data-stu-id="f2ab7-191">smallint</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-192">呼叫者终结点中的 CPU 内核数。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-192">Number of CPU cores in the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-193">CalleeCPUNumberOfCores</span><span class="sxs-lookup"><span data-stu-id="f2ab7-193">CalleeCPUNumberOfCores</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-194">smallint</span><span class="sxs-lookup"><span data-stu-id="f2ab7-194">smallint</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-195">被叫方的终结点中的 CPU 内核数。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-195">Number of CPU cores in the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-196">CallerCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="f2ab7-196">CallerCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-197">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-197">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-198">呼叫者终结点的 CPU 处理器速度。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-198">CPU processor speed of the caller’s endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-199">CalleeCPUProcessorSpeed</span><span class="sxs-lookup"><span data-stu-id="f2ab7-199">CalleeCPUProcessorSpeed</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-200">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-200">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-201">被叫方终结点的 CPU 处理器速度。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-201">CPU processor speed of the callee’s endpoint.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-202">CallerVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="f2ab7-202">CallerVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-203">tinyint</span><span class="sxs-lookup"><span data-stu-id="f2ab7-203">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-204">指示呼叫者的系统是否正在虚拟化环境中运行。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-204">Indicates whether the caller’s system is running in a virtualized environment.</span></span> <span data-ttu-id="f2ab7-205">有关详细信息，请参阅 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的终结点表</a> 。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-205">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-206">CalleeVirtualizationFlag</span><span class="sxs-lookup"><span data-stu-id="f2ab7-206">CalleeVirtualizationFlag</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-207">tinyint</span><span class="sxs-lookup"><span data-stu-id="f2ab7-207">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-208">指示被叫方的系统是否正在虚拟化环境中运行。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-208">Indicates whether the callee’s system is running in a virtualized environment.</span></span> <span data-ttu-id="f2ab7-209">有关详细信息，请参阅 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的终结点表</a> 。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-209">See the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-210">CorrelationKey</span><span class="sxs-lookup"><span data-stu-id="f2ab7-210">CorrelationKey</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f2ab7-211">相关密钥。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-211">Correlation key.</span></span> <span data-ttu-id="f2ab7-212"><a href="lync-server-2013-sessioncorrelation-table.md">在 Lync Server 2013 中从 SessionCorrelation 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-212">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-213">ConnectivityIce</span><span class="sxs-lookup"><span data-stu-id="f2ab7-213">ConnectivityIce</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-214">tinyint</span><span class="sxs-lookup"><span data-stu-id="f2ab7-214">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-215">有关媒体路径的信息，例如 direct 或中继。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-215">Information about the media path, such as direct or relayed.</span></span> <span data-ttu-id="f2ab7-216">有关详细信息，请参阅 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-216">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-217">CallerIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="f2ab7-217">CallerIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-218">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-218">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-p111">关于呼叫者的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“用户体验质量监控服务器协议规范”。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-p111">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the caller. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-221">CalleeIceWarningFlags</span><span class="sxs-lookup"><span data-stu-id="f2ab7-221">CalleeIceWarningFlags</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-222">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-222">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-p112">关于被叫方的位标志中所述的互动式连接建立 (ICE) 过程的信息。有关详细信息，请参阅“用户体验质量监控服务器协议规范”。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-p112">Information about Interactive Connectivity Establishment (ICE) process described in bits flags for the callee. For details, refer to the Quality of Experience Monitoring Server Protocol Specification.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-225">Transport</span><span class="sxs-lookup"><span data-stu-id="f2ab7-225">Transport</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-226">tinyint</span><span class="sxs-lookup"><span data-stu-id="f2ab7-226">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-227">传输类型：0 是 UDP，1 是 TCP。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-227">Transport type: 0 is UDP, 1 is TCP.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-228">CallerIPAddr</span><span class="sxs-lookup"><span data-stu-id="f2ab7-228">CallerIPAddr</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-229">var (50) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-229">var(50)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-230">呼叫者的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-230">IP address of the caller.</span></span> <span data-ttu-id="f2ab7-231">这可能是 IPv4 或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-231">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-232">CallerPort</span><span class="sxs-lookup"><span data-stu-id="f2ab7-232">CallerPort</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-233">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-233">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-234">呼叫者使用的端口。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-234">Port used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-235">CallerInside</span><span class="sxs-lookup"><span data-stu-id="f2ab7-235">CallerInside</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-236">位</span><span class="sxs-lookup"><span data-stu-id="f2ab7-236">bit</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-237">指示呼叫者是否在间隔网络内：1表示呼叫者位于企业网络内，0表示呼叫者在网络外部。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-237">Indicates whether the caller is inside the interval network: 1 means caller is inside the enterprise network, 0 means the caller is outside the network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-238">CalleeIPAddr</span><span class="sxs-lookup"><span data-stu-id="f2ab7-238">CalleeIPAddr</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-239">var (50) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-239">var(50)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-240">被叫方的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-240">IP address of the callee.</span></span> <span data-ttu-id="f2ab7-241">这可能是 IPv4 或 IPv6 地址。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-241">This may be either an IPv4 or an IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-242">CalleePort</span><span class="sxs-lookup"><span data-stu-id="f2ab7-242">CalleePort</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-243">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-243">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-244">被叫方所使用的端口。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-244">Port used by the callee.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-245">CalleeInside</span><span class="sxs-lookup"><span data-stu-id="f2ab7-245">CalleeInside</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-246">位</span><span class="sxs-lookup"><span data-stu-id="f2ab7-246">bit</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-247">指示被叫方是否位于间隔网络内：1表示被呼叫者位于企业网络内，0表示被呼叫方位于网络外部。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-247">Indicates whether the callee is inside the interval network: 1 means callee is inside the enterprise network, 0 means the callee is outside the network.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-248">CallerUserSite</span><span class="sxs-lookup"><span data-stu-id="f2ab7-248">CallerUserSite</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-249">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-249">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-250">呼叫者的站点名称。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-250">Name of the caller’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-251">CallerRegion</span><span class="sxs-lookup"><span data-stu-id="f2ab7-251">CallerRegion</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-252">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-252">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-253">呼叫者站点的国家/地区名称。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-253">Name of the country/region of the caller’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-254">CalleeUserSite</span><span class="sxs-lookup"><span data-stu-id="f2ab7-254">CalleeUserSite</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-255">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-255">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-256">被叫方的站点名称。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-256">Name of the callee’s site.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-257">CalleeRegion</span><span class="sxs-lookup"><span data-stu-id="f2ab7-257">CalleeRegion</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-258">nvarchar (128) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-258">nvarchar(128)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-259">被叫方站点的国家/地区名称。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-259">Name of the country/region of the callee’s site.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-260">CallerRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="f2ab7-260">CallerRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-261">var (50) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-261">var(50)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-262">呼叫者所使用的 A/V 边缘服务的 IP 地址。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-262">IP Address of the A/V Edge service used by the caller.</span></span> <span data-ttu-id="f2ab7-263">有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-263">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-264">CallerRelayPort</span><span class="sxs-lookup"><span data-stu-id="f2ab7-264">CallerRelayPort</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-265">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-265">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-266">呼叫者在 A/V 边缘服务中使用的端口。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-266">Port used on the A/V Edge service used by the caller.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-267">CalleeRelayIPAddr</span><span class="sxs-lookup"><span data-stu-id="f2ab7-267">CalleeRelayIPAddr</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-268">var (50) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-268">var(50)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-269">被叫方所使用的 A/V 边缘服务的 IP 地址密钥。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-269">IP Address key of the A/V Edge service used by the callee.</span></span> <span data-ttu-id="f2ab7-270">有关详细信息，请参阅 <a href="lync-server-2013-ipaddress-table.md">Lync Server 2013 中的 "Ip 地址" 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-270">See the <a href="lync-server-2013-ipaddress-table.md">IPAddress table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-271">CalleeRelayPort</span><span class="sxs-lookup"><span data-stu-id="f2ab7-271">CalleeRelayPort</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-272">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-272">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-273">被叫方在 A/V 边缘服务中使用的端口。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-273">Port used on the A/V Edge service used by the callee.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-274">CallerCaptureDev</span><span class="sxs-lookup"><span data-stu-id="f2ab7-274">CallerCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-275">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-275">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-276">呼叫者的捕获设备名称。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-276">Caller’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-277">CallerRenderDev</span><span class="sxs-lookup"><span data-stu-id="f2ab7-277">CallerRenderDev</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-278">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-278">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-279">呼叫者的呈现设备名称。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-279">Caller’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-280">CallerCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="f2ab7-280">CallerCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-281">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-281">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-282">呼叫者的捕获设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-282">Caller’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-283">CallerRenderDriver</span><span class="sxs-lookup"><span data-stu-id="f2ab7-283">CallerRenderDriver</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-284">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-284">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-285">呼叫者的呈现设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-285">Caller’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-286">CalleeCaptureDev</span><span class="sxs-lookup"><span data-stu-id="f2ab7-286">CalleeCaptureDev</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-287">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-287">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-288">被叫方的捕获设备名称。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-288">Callee’s capture device name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-289">CalleeRenderDev</span><span class="sxs-lookup"><span data-stu-id="f2ab7-289">CalleeRenderDev</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-290">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-290">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-291">被叫方的呈现设备名称。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-291">Callee’s render device name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-292">CalleeCaptureDevDriver</span><span class="sxs-lookup"><span data-stu-id="f2ab7-292">CalleeCaptureDevDriver</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-293">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-293">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-294">被叫方的捕获设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-294">Callee’s capture device driver name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-295">CalleeRenderDevDriver</span><span class="sxs-lookup"><span data-stu-id="f2ab7-295">CalleeRenderDevDriver</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-296">varchar (256) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-296">varchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-297">被叫方的呈现设备驱动程序名称。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-297">Callee’s render device driver name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-298">CallerNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="f2ab7-298">CallerNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-299">tinyint</span><span class="sxs-lookup"><span data-stu-id="f2ab7-299">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-300">呼叫者的网络连接类型：0 是有线，1 是无线。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-300">Caller’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-301">CallerVPN</span><span class="sxs-lookup"><span data-stu-id="f2ab7-301">CallerVPN</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-302">位</span><span class="sxs-lookup"><span data-stu-id="f2ab7-302">bit</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-303">指示呼叫者是否通过虚拟专用网络连接：1是虚拟专用网络 (VPN) ，0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-303">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-304">CallerLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="f2ab7-304">CallerLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-305">十进制 (18，0) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-305">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-306">呼叫者终结点的网络链接速度（以 bps 为单位）。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-306">Network link speed for the caller's endpoint in bps.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-307">CalleeNetworkConnectionType</span><span class="sxs-lookup"><span data-stu-id="f2ab7-307">CalleeNetworkConnectionType</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-308">tinyint</span><span class="sxs-lookup"><span data-stu-id="f2ab7-308">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-309">被叫方的网络连接类型：0 是有线，1 是无线。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-309">Callee’s network connection type: 0 is wired, 1 is wireless.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-310">CalleeVPN</span><span class="sxs-lookup"><span data-stu-id="f2ab7-310">CalleeVPN</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-311">位</span><span class="sxs-lookup"><span data-stu-id="f2ab7-311">bit</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-312">指示呼叫者是否通过虚拟专用网络连接：1是虚拟专用网络 (VPN) ，0是非 VPN。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-312">Indicates whether the caller connected over a virtual private network: 1 is virtual private network (VPN), 0 is non-VPN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-313">CalleeLinkSpeed</span><span class="sxs-lookup"><span data-stu-id="f2ab7-313">CalleeLinkSpeed</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-314">十进制 (18，0) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-314">decimal(18,0)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-315">被呼叫方的终结点的网络链接速度（以 bps 为单位）。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-315">Network link speed for the callee's endpoint in bps.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-316">ConversationalMOS</span><span class="sxs-lookup"><span data-stu-id="f2ab7-316">ConversationalMOS</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-317">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-317">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-318">音频会话的窄带交谈 MOS（基于两个音频流）。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-318">Narrowband Conversational MOS of the audio sessions (based on both audio streams).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-319">AppliedBandwidthLimit</span><span class="sxs-lookup"><span data-stu-id="f2ab7-319">AppliedBandwidthLimit</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-320">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-320">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-321">应用于指定发送端流指定的多种策略设置（TURN、API、SDP、策略服务器等）的实际带宽。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-321">Actual bandwidth applied to the given send side stream given various policy settings (TURN, API, SDP, Policy Server, and so on).</span></span> <span data-ttu-id="f2ab7-322">不要将其与有效带宽混淆，因为根据带宽预估的不同，可能会降低带宽的有效性。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-322">This is not to be confused with the effective bandwidth because there can be a lower effective bandwidth based on the bandwidth estimate.</span></span> <span data-ttu-id="f2ab7-323">这基本上是发送流可以采用带宽估计设定限制的限制的最大带宽</span><span class="sxs-lookup"><span data-stu-id="f2ab7-323">This is basically the maximum bandwidth the send stream can take barring limits imposed by the bandwidth estimate</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-324">JitterInterArrival</span><span class="sxs-lookup"><span data-stu-id="f2ab7-324">JitterInterArrival</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-325">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-325">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-326">实时控制协议 (RTCP) 统计信息中的平均网络抖动。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-326">Average network jitter from Real Time Control Protocol (RTCP) statistics.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-327">JitterInterArrivalMax</span><span class="sxs-lookup"><span data-stu-id="f2ab7-327">JitterInterArrivalMax</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-328">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-328">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-329">呼叫期间的最大网络抖动。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-329">Maximum network jitter during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-330">PacketLossRate</span><span class="sxs-lookup"><span data-stu-id="f2ab7-330">PacketLossRate</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-331">十进制 (5、4) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-331">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-332">呼叫期间的平均数据包丢失率。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-332">Average packet loss rate during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-333">PacketLossRateMax</span><span class="sxs-lookup"><span data-stu-id="f2ab7-333">PacketLossRateMax</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-334">十进制 (5、4) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-334">decimal(5,4)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-335">呼叫期间观测到的数据包丢失最大值。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-335">Maximum packet loss observed during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-336">BurstDensity</span><span class="sxs-lookup"><span data-stu-id="f2ab7-336">BurstDensity</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-337">十进制 (9、4) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-337">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-338">呼叫期间出现猝发损失期间的数据包丢失的平均密度。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-338">Average density of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-339">BurstDuration</span><span class="sxs-lookup"><span data-stu-id="f2ab7-339">BurstDuration</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-340">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-340">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-341">呼叫期间出现猝发损失期间的数据包丢失的平均持续时间。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-341">Average duration of packet loss during bursts of losses during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-342">BurstGapDensity</span><span class="sxs-lookup"><span data-stu-id="f2ab7-342">BurstGapDensity</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-343">十进制 (9、4) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-343">decimal(9,4)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-344">在出现猝发数据包丢失之间间隔期间的数据包丢失的平均密度。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-344">Average density of packet loss during gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-345">BurstGapDuration</span><span class="sxs-lookup"><span data-stu-id="f2ab7-345">BurstGapDuration</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-346">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-346">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-347">猝发数据包丢失间隔的平均持续时间。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-347">Average duration of gaps between bursts of packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-348">PacketUtilization</span><span class="sxs-lookup"><span data-stu-id="f2ab7-348">PacketUtilization</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-349">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-349">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-350">音频流的数据包计数。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-350">Packet count for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-351">BandwidthEst</span><span class="sxs-lookup"><span data-stu-id="f2ab7-351">BandwidthEst</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-352">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-352">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-353">音频流的带宽预估。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-353">Bandwidth estimates for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-354">DegradationAvg</span><span class="sxs-lookup"><span data-stu-id="f2ab7-354">DegradationAvg</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-355">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-355">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-356">整个呼叫的网络 MOS 降级。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-356">Network MOS Degradation for the whole call.</span></span> <span data-ttu-id="f2ab7-357">范围是0.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-357">Range is 0.0 to 5.0.</span></span> <span data-ttu-id="f2ab7-358">此指标显示由于抖动和数据包丢失而导致网络 MOS 减少的量。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-358">This metric shows the amount the Network MOS was reduced because of jitter and packet loss.</span></span> <span data-ttu-id="f2ab7-359">对于可接受的质量，它应小于0.5。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-359">For acceptable quality it should less than 0.5.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-360">DegradationMax</span><span class="sxs-lookup"><span data-stu-id="f2ab7-360">DegradationMax</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-361">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-361">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-362">呼叫期间的最大网络 MOS 降级。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-362">Maximum Network MOS degradation during the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-363">DegradationJitterAvg</span><span class="sxs-lookup"><span data-stu-id="f2ab7-363">DegradationJitterAvg</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-364">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-364">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-365">由抖动引起的网络 MOS 性能下降。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-365">Network MOS degradation caused by jitter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-366">DegradationPacketLossAvg</span><span class="sxs-lookup"><span data-stu-id="f2ab7-366">DegradationPacketLossAvg</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-367">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-367">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-368">因数据包丢失而导致的网络 MOS 降级。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-368">Network MOS degradation caused by packet loss.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-369">PayloadDescription</span><span class="sxs-lookup"><span data-stu-id="f2ab7-369">PayloadDescription</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-370">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-370">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-371">用于呼叫的音频编解码器，从 <a href="lync-server-2013-payloaddescription-table.md">Lync Server 2013 中的 PayloadDescription 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-371">The audio codec used for the call, referenced from the <a href="lync-server-2013-payloaddescription-table.md">PayloadDescription table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-372">AudioSampleRate</span><span class="sxs-lookup"><span data-stu-id="f2ab7-372">AudioSampleRate</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-373">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-373">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-374">音频流的采样率。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-374">Sampling rate for the audio stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-375">CallerSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="f2ab7-375">CallerSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-376">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-376">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-377">呼叫者发送的音频的后模拟增益控制音频信号级别。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-377">Post-Analog Gain Control audio signal level for the audio the caller sent.</span></span> <span data-ttu-id="f2ab7-378">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-378">The unit for this metric is dBmo.</span></span> <span data-ttu-id="f2ab7-379">为获得可接受的质量，至少应为 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-379">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="f2ab7-380">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-380">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-381">CallerRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="f2ab7-381">CallerRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-382">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-382">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-383">呼叫者收到的音频的音频信号级别。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-383">Audio signal level for the audio the caller received.</span></span> <span data-ttu-id="f2ab7-384">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-384">The unit for this metric is dBmo.</span></span> <span data-ttu-id="f2ab7-385">为获得可接受的质量，至少应为 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-385">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="f2ab7-386">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-386">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-387">CallerSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="f2ab7-387">CallerSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-388">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-388">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-389">模拟声后，呼叫者发送的音频的音频噪音水平。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-389">Post-Analog Gain Control audio noise level for the audio the caller sent.</span></span> <span data-ttu-id="f2ab7-390">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-390">The unit for this metric is dBmo.</span></span> <span data-ttu-id="f2ab7-391">为获得可接受的质量，它应小于 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-391">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="f2ab7-392">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-392">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-393">CallerRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="f2ab7-393">CallerRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-394">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-394">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-395">呼叫者接收的音频的后模拟增益控制音频噪音水平。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-395">Post-Analog Gain Control audio noise level for the audio the caller received.</span></span> <span data-ttu-id="f2ab7-396">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-396">The unit for this metric is dBmo.</span></span> <span data-ttu-id="f2ab7-397">为获得可接受的质量，它应小于 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-397">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="f2ab7-398">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-398">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-399">CallerEchoReturn</span><span class="sxs-lookup"><span data-stu-id="f2ab7-399">CallerEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-400">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-400">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-401">呼叫者的回显返回丢失增强功能。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-401">Echo Return Loss Enhancement for the caller.</span></span> <span data-ttu-id="f2ab7-402">此指标的单位为 dB。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-402">The unit for this metric is dB.</span></span> <span data-ttu-id="f2ab7-403">值越低表示回显越少。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-403">Lower values represent less echo.</span></span> <span data-ttu-id="f2ab7-404">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-404">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-405">CallerSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="f2ab7-405">CallerSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-406">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-406">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-407">呼叫者的扬声器呈现每5分钟的平均故障。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-407">Average glitches per five minutes for the caller’s loudspeaker rendering.</span></span> <span data-ttu-id="f2ab7-408">为了获得较高的质量，这应小于每五分钟一次。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-408">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="f2ab7-409">不是由 A/V 会议服务器、中介服务器或 IP 电话报告。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-409">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-410">CallerMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="f2ab7-410">CallerMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-411">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-411">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-412">呼叫者的麦克风捕获每5分钟的平均故障。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-412">Average glitches per five minutes for the caller’s microphone capture.</span></span> <span data-ttu-id="f2ab7-413">若要获得较高的质量，这应小于每5分钟一次。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-413">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="f2ab7-414">不是由 A/V 会议服务器、中介服务器或 IP 电话报告。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-414">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-415">CallerTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="f2ab7-415">CallerTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-416">十进制 (9，2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-416">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-417">呼叫者的麦克风设备时钟相对于 CPU 时钟的速度偏移速率。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-417">Caller’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-418">CallerTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="f2ab7-418">CallerTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-419">十进制 (9，2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-419">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-420">呼叫者的扬声器设备时钟相对于 CPU 时钟的速度偏移速率。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-420">Caller’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-421">CallerTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="f2ab7-421">CallerTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-422">十进制 (9，2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-422">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-423">呼叫的最后20秒内的麦克风捕获流的平均时间戳错误（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-423">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-424">CallerTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="f2ab7-424">CallerTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-425">十进制 (9，2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-425">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-426">呼叫者的扬声器在最近20秒内呈现流时间戳错误的平均次数（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-426">Average of the caller’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-427">CallerVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="f2ab7-427">CallerVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-428">smallint</span><span class="sxs-lookup"><span data-stu-id="f2ab7-428">smallint</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-429">Voice switch 是一个半双工模式，具有更低的中断能力。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-429">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="f2ab7-430">有关详细信息，请参阅 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-430">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-431">CallerEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="f2ab7-431">CallerEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-432">tinyint</span><span class="sxs-lookup"><span data-stu-id="f2ab7-432">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-433">调用方的 echo 事件的原因。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-433">Causes of an echo event for the caller.</span></span> <span data-ttu-id="f2ab7-434">有关详细信息，请参阅 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-434">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-435">CallerEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="f2ab7-435">CallerEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-436">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-436">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-437">在呼叫者的麦克风捕获流中检测到回显的时间的百分比。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-437">Percentage of time when echo is detected in the caller’s microphone capture stream.</span></span> <span data-ttu-id="f2ab7-438">如果使用的是耳机，则该值应较低。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-438">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-439">CallerEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="f2ab7-439">CallerEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-440">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-440">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-441">在呼叫者的发送流中检测到回显的时间的百分比。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-441">Percentage of time when echo is detected in the caller’s sent stream.</span></span> <span data-ttu-id="f2ab7-442">发送流中的高回显百分比指示回声泄漏。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-442">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-443">CallerRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="f2ab7-443">CallerRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-444">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-444">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-445">从呼叫者音频的网关接收中介服务器上的信号级别;这仅适用于中介服务器。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-445">Received signal level on the Mediation Server from the Gateway for the caller’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="f2ab7-446">此指标的单位为 dBoV。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-446">The unit of this metric is dBoV.</span></span> <span data-ttu-id="f2ab7-447">为了获得良好的质量，可接受范围应为-30 到-18 dBoV。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-447">For good quality, the acceptable range should be -30 to -18 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-448">CallerRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="f2ab7-448">CallerRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-449">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-449">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-450">从呼叫者音频的网关接收中介服务器上的信号级别。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-450">Received signal level on the Mediation Server from the Gateway for the caller’s audio.</span></span> <span data-ttu-id="f2ab7-451">这仅适用于中介服务器。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-451">This applies only to the Mediation Server.</span></span> <span data-ttu-id="f2ab7-452">此指标的单位为 dBoV。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-452">The unit of this metric is dBoV.</span></span> <span data-ttu-id="f2ab7-453">为了获得良好的质量，可接受的范围应小于-50 dBoV。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-453">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-454">CallerRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="f2ab7-454">CallerRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-455">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-455">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-456"> (AGC) 在应用于呼叫者音频的中介服务器端上的自动增益控制。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-456">Automatic gain control (AGC) on the Mediation Server side applied to the caller’s audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-457">CallerInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="f2ab7-457">CallerInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-458">float</span><span class="sxs-lookup"><span data-stu-id="f2ab7-458">float</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-459">到呼叫者的传入信号的根平均平方 (RMS) ，最长为呼叫的前30秒。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-459">Root mean square (RMS) of the incoming signal to the caller for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-460">CalleeSendSignalLevel</span><span class="sxs-lookup"><span data-stu-id="f2ab7-460">CalleeSendSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-461">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-461">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-462">表示被呼叫者发送的音频的反电后增益控制音频信号级别。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-462">Represents the Post-Analog Gain Control audio signal level for the audio the callee sent.</span></span> <span data-ttu-id="f2ab7-463">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-463">The unit for this metric is dBmo.</span></span> <span data-ttu-id="f2ab7-464">为获得可接受的质量，至少应为 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-464">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="f2ab7-465">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-465">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-466">CalleeRecvSignalLevel</span><span class="sxs-lookup"><span data-stu-id="f2ab7-466">CalleeRecvSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-467">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-467">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-468">被呼叫者收到的音频的音频信号级别。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-468">Audio signal level for the audio the callee received.</span></span> <span data-ttu-id="f2ab7-469">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-469">The unit for this metric is dBmo.</span></span> <span data-ttu-id="f2ab7-470">为获得可接受的质量，至少应为 30 dBmo。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-470">For acceptable quality, it should be at least 30 dBmo.</span></span> <span data-ttu-id="f2ab7-471">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-471">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-472">CalleeSendNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="f2ab7-472">CalleeSendNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-473">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-473">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-474">对被呼叫者发送的音频进行模拟后增益控制音频噪音级别。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-474">Post-Analog Gain Control audio noise level for the audio the callee sent.</span></span> <span data-ttu-id="f2ab7-475">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-475">The unit for this metric is dBmo.</span></span> <span data-ttu-id="f2ab7-476">为获得可接受的质量，它应小于 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-476">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="f2ab7-477">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-477">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-478">CalleeRecvNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="f2ab7-478">CalleeRecvNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-479">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-479">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-480">被呼叫者接收的音频的模拟后增益控制音频噪音水平。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-480">Post-Analog Gain Control audio noise level for the audio the callee received.</span></span> <span data-ttu-id="f2ab7-481">此指标的单位为 dBmo。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-481">The unit for this metric is dBmo.</span></span> <span data-ttu-id="f2ab7-482">为获得可接受的质量，它应小于 35 dBmo。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-482">For acceptable quality, it should be less than 35 dBmo.</span></span> <span data-ttu-id="f2ab7-483">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-483">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-484">CalleeEchoReturn</span><span class="sxs-lookup"><span data-stu-id="f2ab7-484">CalleeEchoReturn</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-485">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-485">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-486">对被叫方的回显返回丢失增强。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-486">Echo Return Loss Enhancement for the callee.</span></span> <span data-ttu-id="f2ab7-487">此指标的单位为 dB。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-487">The unit for this metric is dB.</span></span> <span data-ttu-id="f2ab7-488">值越低表示回显越少。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-488">Lower values represent less echo.</span></span> <span data-ttu-id="f2ab7-489">A/V 会议服务器或 IP 电话不报告此指标。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-489">This metric is not reported by the A/V Conferencing Server or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-490">CalleeSpeakerGlitchRate</span><span class="sxs-lookup"><span data-stu-id="f2ab7-490">CalleeSpeakerGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-491">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-491">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-492">被呼叫者的扬声器呈现每5分钟的平均故障。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-492">Average glitches per five minutes for the callee’s loudspeaker rendering.</span></span> <span data-ttu-id="f2ab7-493">为了获得较高的质量，这应小于每五分钟一次。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-493">For good quality, this should be less than one per five minutes.</span></span> <span data-ttu-id="f2ab7-494">不是由 A/V 会议服务器、中介服务器或 IP 电话报告。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-494">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-495">CalleeMicGlitchRate</span><span class="sxs-lookup"><span data-stu-id="f2ab7-495">CalleeMicGlitchRate</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-496">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-496">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-497">被呼叫者的麦克风捕获每5分钟的平均故障。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-497">Average glitches per five minutes for the callee’s microphone capture.</span></span> <span data-ttu-id="f2ab7-498">若要获得较高的质量，这应小于每5分钟一次。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-498">For good quality this should be less than one per five minutes.</span></span> <span data-ttu-id="f2ab7-499">不是由 A/V 会议服务器、中介服务器或 IP 电话报告。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-499">Not reported by A/V Conferencing Servers, Mediation Servers, or IP phones.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-500">CalleeTimestampDriftRateMic</span><span class="sxs-lookup"><span data-stu-id="f2ab7-500">CalleeTimestampDriftRateMic</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-501">十进制 (9，2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-501">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-502">被叫方的麦克风设备时钟相对于 CPU 时钟的时钟偏移速度。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-502">Callee’s microphone device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-503">CalleeTimestampDriftRateSpk</span><span class="sxs-lookup"><span data-stu-id="f2ab7-503">CalleeTimestampDriftRateSpk</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-504">十进制 (9，2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-504">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-505">被叫方的扬声器设备时钟相对于 CPU 时钟的时钟偏移速度。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-505">Callee’s speaker device clock drift rate, relative to CPU clock.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-506">CalleeTimestampErrorMicMs</span><span class="sxs-lookup"><span data-stu-id="f2ab7-506">CalleeTimestampErrorMicMs</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-507">十进制 (9，2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-507">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-508">呼叫的最后20秒内的麦克风捕获流的平均时间戳错误（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-508">Average microphone capture stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-509">CalleeTimestampErrorSpkMs</span><span class="sxs-lookup"><span data-stu-id="f2ab7-509">CalleeTimestampErrorSpkMs</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-510">十进制 (9，2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-510">decimal(9,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-511">被呼叫者的发言人的平均呈现流时间戳错误（以毫秒为单位）在呼叫的最后20秒中。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-511">Average of the callee’s speaker render stream time stamp error, in milliseconds, in the last 20 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-512">CalleeVsEntryCauses</span><span class="sxs-lookup"><span data-stu-id="f2ab7-512">CalleeVsEntryCauses</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-513">smallint</span><span class="sxs-lookup"><span data-stu-id="f2ab7-513">smallint</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-514">Voice switch 是一个半双工模式，具有更低的中断能力。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-514">Voice switch is a half-duplex mode with reduced interruption ability.</span></span> <span data-ttu-id="f2ab7-515">有关详细信息，请参阅 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-515">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-516">CalleeEchoEventCauses</span><span class="sxs-lookup"><span data-stu-id="f2ab7-516">CalleeEchoEventCauses</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-517">tinyint</span><span class="sxs-lookup"><span data-stu-id="f2ab7-517">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-518">被调用方的 echo 事件的原因。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-518">Causes of an echo event for the callee.</span></span> <span data-ttu-id="f2ab7-519">有关详细信息，请参阅 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-519">See the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-520">CalleeEchoPercentMicIn</span><span class="sxs-lookup"><span data-stu-id="f2ab7-520">CalleeEchoPercentMicIn</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-521">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-521">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-522">在被呼叫者的麦克风捕获流中检测到回显的时间的百分比。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-522">Percentage of time when echo is detected in the callee’s microphone capture stream.</span></span> <span data-ttu-id="f2ab7-523">如果使用的是耳机，则该值应较低。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-523">If headset is used, the value should be low.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-524">CalleeEchoPercentSend</span><span class="sxs-lookup"><span data-stu-id="f2ab7-524">CalleeEchoPercentSend</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-525">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-525">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-526">在被呼叫方的已发送流中检测到回显的时间的百分比。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-526">Percentage of time when echo is detected in the callee’s sent stream.</span></span> <span data-ttu-id="f2ab7-527">发送流中的高回显百分比指示回声泄漏。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-527">High echo percentage in send streams an indication of echo leak.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-528">CalleeRxAGCSignalLevel</span><span class="sxs-lookup"><span data-stu-id="f2ab7-528">CalleeRxAGCSignalLevel</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-529">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-529">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-530">在中介服务器上从被呼叫者的音频的网关收到了信号级别;这仅适用于中介服务器。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-530">Received signal level on the Mediation Server from the Gateway for the callee’s audio; this applies only to the Mediation Server.</span></span> <span data-ttu-id="f2ab7-531">此指标的单位为 dBoV。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-531">The unit of this metric is dBoV.</span></span> <span data-ttu-id="f2ab7-532">为了获得良好的质量，可接受范围应为 [-30 至-18] dBoV。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-532">For good quality, the acceptable range should be [-30 to -18] dBoV.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-533">CalleeRxAGCNoiseLevel</span><span class="sxs-lookup"><span data-stu-id="f2ab7-533">CalleeRxAGCNoiseLevel</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-534">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-534">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-535">在中介服务器上从被呼叫者的音频的网关收到了信号级别。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-535">Received signal level on the Mediation Server from the Gateway for the callee’s audio.</span></span> <span data-ttu-id="f2ab7-536">这仅适用于中介服务器。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-536">This applies only to the Mediation Server.</span></span> <span data-ttu-id="f2ab7-537">此指标的单位为 dBoV。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-537">The unit of this metric is dBoV.</span></span> <span data-ttu-id="f2ab7-538">为了获得良好的质量，可接受的范围应小于-50 dBoV。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-538">For good quality, the acceptable range should be less than -50 dBoV.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-539">CalleeRxAGCGain</span><span class="sxs-lookup"><span data-stu-id="f2ab7-539">CalleeRxAGCGain</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-540">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-540">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-541"> (AGC) 在应用于被呼叫者的音频的中介服务器端上的自动增益控制。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-541">Automatic gain control (AGC) on the Mediation Server side applied to the callee’s audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-542">CalleeInitialSignalLevelRMS</span><span class="sxs-lookup"><span data-stu-id="f2ab7-542">CalleeInitialSignalLevelRMS</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-543">float</span><span class="sxs-lookup"><span data-stu-id="f2ab7-543">float</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-544">最长为呼叫者的传入信号的根均值 (RMS) ，最长为呼叫的前30秒。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-544">Root mean square (RMS) of the incoming signal to the callee for up to the first 30 seconds of the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-545">RatioConcealedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="f2ab7-545">RatioConcealedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-546">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-546">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-547">通过音频康复对典型示例生成的隐藏样本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-547">Average ratio of concealed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-548">RatioStretchedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="f2ab7-548">RatioStretchedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-549">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-549">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-550">由音频康复生成的一般示例中的延伸样本的平均比率。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-550">Average ratio of stretched samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-551">RatioCompressedSamplesAvg</span><span class="sxs-lookup"><span data-stu-id="f2ab7-551">RatioCompressedSamplesAvg</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-552">十进制 (5、2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-552">decimal(5,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-553">由音频康复生成的压缩样本的平均比率到典型示例。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-553">Average ratio of compressed samples generated by audio healing to typical samples.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-554">工程</span><span class="sxs-lookup"><span data-stu-id="f2ab7-554">RoundTrip</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-555">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-555">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-556">RTCP 统计信息中的来回行程时间。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-556">Round trip time from RTCP statistics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-557">RoundTripMax</span><span class="sxs-lookup"><span data-stu-id="f2ab7-557">RoundTripMax</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-558">int</span><span class="sxs-lookup"><span data-stu-id="f2ab7-558">int</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-559">音频流的最大来回行程时间。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-559">Maximum round trip time for the audio stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-560">OverallAvgNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="f2ab7-560">OverallAvgNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-561">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-561">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-562">呼叫的平均宽带网络 MOS。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-562">Average wideband Network MOS for the call.</span></span> <span data-ttu-id="f2ab7-563">此指标取决于所使用的数据包丢失、抖动和编解码器。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-563">This metric depends on the packet loss, jitter, and codec used.</span></span> <span data-ttu-id="f2ab7-564">范围是1.0 到5.0。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-564">Range is 1.0 to 5.0.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-565">OverallMinNetworkMOS</span><span class="sxs-lookup"><span data-stu-id="f2ab7-565">OverallMinNetworkMOS</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-566">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-566">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-567">用于呼叫的最小宽带网络 MOS。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-567">Minimum wideband Network MOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-568">SendListenMOS</span><span class="sxs-lookup"><span data-stu-id="f2ab7-568">SendListenMOS</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-569">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-569">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-570">平均预测宽带侦听发送音频的 MOS 分数，包括语音级别、噪声级别和捕获设备特征。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-570">Average predicted wideband Listening MOS score for audio sent, including speech level, noise level and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-571">SendListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="f2ab7-571">SendListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-572">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-572">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-573">呼叫的最小 SendListenMOS。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-573">Minimum SendListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-574">RecvListenMOS</span><span class="sxs-lookup"><span data-stu-id="f2ab7-574">RecvListenMOS</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-575">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-575">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-576">平均预测宽带侦听从网络接收的音频的 MOS 分数，包括语音级别、噪音级别、编解码器、网络状况和捕获设备特征。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-576">Average predicted wideband Listening MOS score for audio received from the network including speech level, noise level, codec, network conditions and capture device characteristics.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-577">RecvListenMOSMin</span><span class="sxs-lookup"><span data-stu-id="f2ab7-577">RecvListenMOSMin</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-578">十进制 (3、2) </span><span class="sxs-lookup"><span data-stu-id="f2ab7-578">decimal(3,2)</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-579">呼叫的最小 RecvListenMOS。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-579">Minimum RecvListenMOS for the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f2ab7-580">AudioFECUsed</span><span class="sxs-lookup"><span data-stu-id="f2ab7-580">AudioFECUsed</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-581">位</span><span class="sxs-lookup"><span data-stu-id="f2ab7-581">bit</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-582">指示是否对呼叫使用音频 FEC。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-582">Indicates whether audio FEC was used for the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f2ab7-583">SenderIsCallerPAI</span><span class="sxs-lookup"><span data-stu-id="f2ab7-583">SenderIsCallerPAI</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-584">位</span><span class="sxs-lookup"><span data-stu-id="f2ab7-584">bit</span></span></p></td>
<td><p><span data-ttu-id="f2ab7-585">指示 p 声明的标识信息的方向;1表示流方向来自调用方的调用者;0表示流方向从被呼叫方到调用方。</span><span class="sxs-lookup"><span data-stu-id="f2ab7-585">Indicates direction of the p-asserted identify information; 1 means the stream direction is from the caller to the callee; 0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

