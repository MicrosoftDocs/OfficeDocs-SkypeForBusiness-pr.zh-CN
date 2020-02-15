---
title: Lync Server 2013：会话视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session view
ms:assetid: 49e33f5b-45d0-4146-a5a4-76954d895a98
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688048(v=OCS.15)
ms:contentKeyID: 49733641
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d20d748f9c9754efab768a702f1272bc70d889e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42051294"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="735a9-102">Lync Server 2013 中的会话视图</span><span class="sxs-lookup"><span data-stu-id="735a9-102">Session view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="735a9-103">_**上次修改的主题：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="735a9-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="735a9-104">会话视图存储有关在数据库中具有记录的会话的信息。</span><span class="sxs-lookup"><span data-stu-id="735a9-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="735a9-105">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="735a9-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="735a9-106">列</span><span class="sxs-lookup"><span data-stu-id="735a9-106">Column</span></span></th>
<th><span data-ttu-id="735a9-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="735a9-107">Data Type</span></span></th>
<th><span data-ttu-id="735a9-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="735a9-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="735a9-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="735a9-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="735a9-110">datetime</span><span class="sxs-lookup"><span data-stu-id="735a9-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="735a9-111">引用自 MediaLine 表。</span><span class="sxs-lookup"><span data-stu-id="735a9-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="735a9-112">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="735a9-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="735a9-113">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="735a9-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="735a9-114">如果是会议，则是会议 URI；如果是点对点会话，则是 DialogID。</span><span class="sxs-lookup"><span data-stu-id="735a9-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="735a9-115">相关性</span><span class="sxs-lookup"><span data-stu-id="735a9-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="735a9-116">varchar （max）</span><span class="sxs-lookup"><span data-stu-id="735a9-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="735a9-117">会话的关联 ID。</span><span class="sxs-lookup"><span data-stu-id="735a9-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="735a9-118">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="735a9-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="735a9-119">位</span><span class="sxs-lookup"><span data-stu-id="735a9-119">bit</span></span></p></td>
<td><p><span data-ttu-id="735a9-120">对话框类别;0是 Lync Server 以进行中介服务器腿;1是中介服务器到 PSTN 网关腿。</span><span class="sxs-lookup"><span data-stu-id="735a9-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="735a9-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="735a9-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="735a9-122">位</span><span class="sxs-lookup"><span data-stu-id="735a9-122">bit</span></span></p></td>
<td><p><span data-ttu-id="735a9-123">指示是否旁路了呼叫。</span><span class="sxs-lookup"><span data-stu-id="735a9-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="735a9-124">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="735a9-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="735a9-125">int</span><span class="sxs-lookup"><span data-stu-id="735a9-125">int</span></span></p></td>
<td><p><span data-ttu-id="735a9-126">如果存在，此字段指示即使绕过 ID 相匹配也没有绕过呼叫的原因。</span><span class="sxs-lookup"><span data-stu-id="735a9-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="735a9-127">对于 Lync Server，仅定义了一个值：</span><span class="sxs-lookup"><span data-stu-id="735a9-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="735a9-128">0x0001 – 默认网络适配器的未知旁路 ID</span><span class="sxs-lookup"><span data-stu-id="735a9-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="735a9-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="735a9-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="735a9-130">datetime</span><span class="sxs-lookup"><span data-stu-id="735a9-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="735a9-131">呼叫开始时间。</span><span class="sxs-lookup"><span data-stu-id="735a9-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="735a9-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="735a9-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="735a9-133">datetime</span><span class="sxs-lookup"><span data-stu-id="735a9-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="735a9-134">呼叫结束时间。</span><span class="sxs-lookup"><span data-stu-id="735a9-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="735a9-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="735a9-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="735a9-136">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="735a9-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="735a9-137">呼叫者池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="735a9-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="735a9-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="735a9-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="735a9-139">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="735a9-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="735a9-140">被叫方池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="735a9-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="735a9-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="735a9-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="735a9-142">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="735a9-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="735a9-143">呼叫者的 p 已断言标识 URI。</span><span class="sxs-lookup"><span data-stu-id="735a9-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="735a9-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="735a9-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="735a9-145">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="735a9-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="735a9-146">被叫方的 p 已断言标识 URI。</span><span class="sxs-lookup"><span data-stu-id="735a9-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="735a9-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="735a9-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="735a9-148">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="735a9-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="735a9-149">呼叫者的终结点名称。</span><span class="sxs-lookup"><span data-stu-id="735a9-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="735a9-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="735a9-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="735a9-151">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="735a9-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="735a9-152">呼叫者的终结点名称。</span><span class="sxs-lookup"><span data-stu-id="735a9-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="735a9-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="735a9-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="735a9-154">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="735a9-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="735a9-155">呼叫者的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="735a9-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="735a9-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="735a9-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="735a9-157">smallint</span><span class="sxs-lookup"><span data-stu-id="735a9-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="735a9-158">呼叫者的用户代理类型。</span><span class="sxs-lookup"><span data-stu-id="735a9-158">Type of caller’s user agent.</span></span> <span data-ttu-id="735a9-159">有关详细信息，请参阅<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>。</span><span class="sxs-lookup"><span data-stu-id="735a9-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="735a9-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="735a9-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="735a9-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="735a9-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="735a9-162">呼叫者的用户代理的类别。</span><span class="sxs-lookup"><span data-stu-id="735a9-162">Category of caller’s user agent.</span></span> <span data-ttu-id="735a9-163">有关详细信息，请参阅<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表（QoE）</a> 。</span><span class="sxs-lookup"><span data-stu-id="735a9-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="735a9-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="735a9-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="735a9-165">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="735a9-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="735a9-166">被叫方的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="735a9-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="735a9-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="735a9-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="735a9-168">smallint</span><span class="sxs-lookup"><span data-stu-id="735a9-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="735a9-169">被叫方的用户代理的类型。</span><span class="sxs-lookup"><span data-stu-id="735a9-169">Type of user agent for the callee.</span></span> <span data-ttu-id="735a9-170">有关详细信息，请参阅<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>。</span><span class="sxs-lookup"><span data-stu-id="735a9-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="735a9-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="735a9-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="735a9-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="735a9-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="735a9-173">被叫方的用户代理类别。</span><span class="sxs-lookup"><span data-stu-id="735a9-173">User agent category for the callee.</span></span> <span data-ttu-id="735a9-174">有关详细信息，请参阅<a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表（QoE）</a> 。</span><span class="sxs-lookup"><span data-stu-id="735a9-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="735a9-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="735a9-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="735a9-176">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="735a9-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="735a9-177">呼叫者的 URI。</span><span class="sxs-lookup"><span data-stu-id="735a9-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="735a9-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="735a9-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="735a9-179">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="735a9-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="735a9-180">被叫方的 URI。</span><span class="sxs-lookup"><span data-stu-id="735a9-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="735a9-181">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="735a9-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="735a9-182">int</span><span class="sxs-lookup"><span data-stu-id="735a9-182">int</span></span></p></td>
<td><p><span data-ttu-id="735a9-183">呼叫的优先级。</span><span class="sxs-lookup"><span data-stu-id="735a9-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

