---
title: 'Lync Server 2013: 会话视图'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a90d6a3f066caccb20b141daa485cabea29e2352
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822032"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="128fd-102">Lync Server 2013 中的 "会话" 视图</span><span class="sxs-lookup"><span data-stu-id="128fd-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="128fd-103">_**主题上次修改时间:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="128fd-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="128fd-104">"会话" 视图存储有关具有数据库中的记录的会话的信息。</span><span class="sxs-lookup"><span data-stu-id="128fd-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="128fd-105">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="128fd-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="128fd-106">列</span><span class="sxs-lookup"><span data-stu-id="128fd-106">Column</span></span></th>
<th><span data-ttu-id="128fd-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="128fd-107">Data Type</span></span></th>
<th><span data-ttu-id="128fd-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="128fd-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="128fd-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="128fd-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="128fd-110">datetime</span><span class="sxs-lookup"><span data-stu-id="128fd-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="128fd-111">从 MediaLine 表中引用。</span><span class="sxs-lookup"><span data-stu-id="128fd-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="128fd-112">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="128fd-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="128fd-113">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="128fd-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="128fd-114">会议 URI (如果这是会议) 或 DialogID (如果这是对等会话)。</span><span class="sxs-lookup"><span data-stu-id="128fd-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="128fd-115">关系</span><span class="sxs-lookup"><span data-stu-id="128fd-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="128fd-116">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="128fd-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="128fd-117">会话的相关 ID。</span><span class="sxs-lookup"><span data-stu-id="128fd-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="128fd-118">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="128fd-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="128fd-119">bit</span><span class="sxs-lookup"><span data-stu-id="128fd-119">bit</span></span></p></td>
<td><p><span data-ttu-id="128fd-120">对话框类别;0是 Lync 服务器以中介服务器腿;1是中介服务器到 PSTN 网关腿。</span><span class="sxs-lookup"><span data-stu-id="128fd-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="128fd-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="128fd-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="128fd-122">bit</span><span class="sxs-lookup"><span data-stu-id="128fd-122">bit</span></span></p></td>
<td><p><span data-ttu-id="128fd-123">指示是否跳过呼叫。</span><span class="sxs-lookup"><span data-stu-id="128fd-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="128fd-124">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="128fd-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="128fd-125">int</span><span class="sxs-lookup"><span data-stu-id="128fd-125">int</span></span></p></td>
<td><p><span data-ttu-id="128fd-126">此字段 (如果存在) 指示无法跳过呼叫的原因, 即使旁路 Id 匹配也是如此。</span><span class="sxs-lookup"><span data-stu-id="128fd-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="128fd-127">对于 Lync Server, 只定义一个值:</span><span class="sxs-lookup"><span data-stu-id="128fd-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="128fd-128">0x0001-默认网络适配器的未知旁路 ID</span><span class="sxs-lookup"><span data-stu-id="128fd-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="128fd-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="128fd-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="128fd-130">datetime</span><span class="sxs-lookup"><span data-stu-id="128fd-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="128fd-131">通话开始时间。</span><span class="sxs-lookup"><span data-stu-id="128fd-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="128fd-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="128fd-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="128fd-133">datetime</span><span class="sxs-lookup"><span data-stu-id="128fd-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="128fd-134">通话结束时间。</span><span class="sxs-lookup"><span data-stu-id="128fd-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="128fd-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="128fd-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="128fd-136">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="128fd-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="128fd-137">呼叫方池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="128fd-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="128fd-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="128fd-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="128fd-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="128fd-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="128fd-140">被调用池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="128fd-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="128fd-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="128fd-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="128fd-142">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="128fd-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="128fd-143">调用方的 p 声明标识 URI。</span><span class="sxs-lookup"><span data-stu-id="128fd-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="128fd-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="128fd-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="128fd-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="128fd-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="128fd-146">被调用方的 p 声明标识 URI。</span><span class="sxs-lookup"><span data-stu-id="128fd-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="128fd-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="128fd-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="128fd-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="128fd-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="128fd-149">调用方的终结点名称。</span><span class="sxs-lookup"><span data-stu-id="128fd-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="128fd-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="128fd-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="128fd-151">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="128fd-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="128fd-152">调用方的终结点名称。</span><span class="sxs-lookup"><span data-stu-id="128fd-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="128fd-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="128fd-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="128fd-154">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="128fd-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="128fd-155">呼叫方的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="128fd-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="128fd-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="128fd-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="128fd-157">smallint</span><span class="sxs-lookup"><span data-stu-id="128fd-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="128fd-158">呼叫方的用户代理的类型。</span><span class="sxs-lookup"><span data-stu-id="128fd-158">Type of caller’s user agent.</span></span> <span data-ttu-id="128fd-159">有关详细信息, 请参阅<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>。</span><span class="sxs-lookup"><span data-stu-id="128fd-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="128fd-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="128fd-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="128fd-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="128fd-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="128fd-162">呼叫者的用户代理类别。</span><span class="sxs-lookup"><span data-stu-id="128fd-162">Category of caller’s user agent.</span></span> <span data-ttu-id="128fd-163">有关详细信息, 请参阅<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表 (QoE)</a> 。</span><span class="sxs-lookup"><span data-stu-id="128fd-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="128fd-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="128fd-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="128fd-165">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="128fd-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="128fd-166">被呼叫方的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="128fd-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="128fd-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="128fd-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="128fd-168">smallint</span><span class="sxs-lookup"><span data-stu-id="128fd-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="128fd-169">被呼叫方的用户代理类型。</span><span class="sxs-lookup"><span data-stu-id="128fd-169">Type of user agent for the callee.</span></span> <span data-ttu-id="128fd-170">有关详细信息, 请参阅<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>。</span><span class="sxs-lookup"><span data-stu-id="128fd-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="128fd-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="128fd-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="128fd-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="128fd-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="128fd-173">被呼叫方的用户代理类别。</span><span class="sxs-lookup"><span data-stu-id="128fd-173">User agent category for the callee.</span></span> <span data-ttu-id="128fd-174">有关详细信息, 请参阅<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表 (QoE)</a> 。</span><span class="sxs-lookup"><span data-stu-id="128fd-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="128fd-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="128fd-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="128fd-176">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="128fd-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="128fd-177">调用方的 URI。</span><span class="sxs-lookup"><span data-stu-id="128fd-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="128fd-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="128fd-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="128fd-179">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="128fd-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="128fd-180">被调用方的 URI。</span><span class="sxs-lookup"><span data-stu-id="128fd-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="128fd-181">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="128fd-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="128fd-182">int</span><span class="sxs-lookup"><span data-stu-id="128fd-182">int</span></span></p></td>
<td><p><span data-ttu-id="128fd-183">通话的优先级。</span><span class="sxs-lookup"><span data-stu-id="128fd-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

