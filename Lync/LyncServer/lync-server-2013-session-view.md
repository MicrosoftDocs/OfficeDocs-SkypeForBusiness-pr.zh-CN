---
title: Lync Server 2013：会话视图
description: Lync Server 2013：会话视图。
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
ms.openlocfilehash: ff4bc4abbd55e073006693d28f092f077698ef75
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545008"
---
# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="a1b62-103">Lync Server 2013 中的会话视图</span><span class="sxs-lookup"><span data-stu-id="a1b62-103">Session view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a1b62-104">_**上次修改的主题：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="a1b62-104">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="a1b62-105">会话视图存储有关在数据库中具有记录的会话的信息。</span><span class="sxs-lookup"><span data-stu-id="a1b62-105">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="a1b62-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="a1b62-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="a1b62-107">列</span><span class="sxs-lookup"><span data-stu-id="a1b62-107">Column</span></span></th>
<th><span data-ttu-id="a1b62-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="a1b62-108">Data Type</span></span></th>
<th><span data-ttu-id="a1b62-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="a1b62-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="a1b62-110">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="a1b62-110">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="a1b62-111">datetime</span><span class="sxs-lookup"><span data-stu-id="a1b62-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="a1b62-112">引用自 MediaLine 表。</span><span class="sxs-lookup"><span data-stu-id="a1b62-112">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1b62-113">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="a1b62-113">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="a1b62-114">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="a1b62-114">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a1b62-115">如果是会议，则是会议 URI；如果是点对点会话，则是 DialogID。</span><span class="sxs-lookup"><span data-stu-id="a1b62-115">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1b62-116">相关性</span><span class="sxs-lookup"><span data-stu-id="a1b62-116">Correlation</span></span></p></td>
<td><p><span data-ttu-id="a1b62-117">varchar (max) </span><span class="sxs-lookup"><span data-stu-id="a1b62-117">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="a1b62-118">会话的关联 ID。</span><span class="sxs-lookup"><span data-stu-id="a1b62-118">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1b62-119">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="a1b62-119">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="a1b62-120">位</span><span class="sxs-lookup"><span data-stu-id="a1b62-120">bit</span></span></p></td>
<td><p><span data-ttu-id="a1b62-121">对话框类别;0是 Lync Server 以进行中介服务器腿;1是中介服务器到 PSTN 网关腿。</span><span class="sxs-lookup"><span data-stu-id="a1b62-121">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1b62-122">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="a1b62-122">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="a1b62-123">位</span><span class="sxs-lookup"><span data-stu-id="a1b62-123">bit</span></span></p></td>
<td><p><span data-ttu-id="a1b62-124">指示是否旁路了呼叫。</span><span class="sxs-lookup"><span data-stu-id="a1b62-124">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1b62-125">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="a1b62-125">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="a1b62-126">int</span><span class="sxs-lookup"><span data-stu-id="a1b62-126">int</span></span></p></td>
<td><p><span data-ttu-id="a1b62-127">如果存在，此字段指示即使绕过 ID 相匹配也没有绕过呼叫的原因。</span><span class="sxs-lookup"><span data-stu-id="a1b62-127">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="a1b62-128">对于 Lync Server，仅定义了一个值：</span><span class="sxs-lookup"><span data-stu-id="a1b62-128">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="a1b62-129">0x0001 – 默认网络适配器的未知旁路 ID</span><span class="sxs-lookup"><span data-stu-id="a1b62-129">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1b62-130">StartTime</span><span class="sxs-lookup"><span data-stu-id="a1b62-130">StartTime</span></span></p></td>
<td><p><span data-ttu-id="a1b62-131">datetime</span><span class="sxs-lookup"><span data-stu-id="a1b62-131">datetime</span></span></p></td>
<td><p><span data-ttu-id="a1b62-132">呼叫开始时间。</span><span class="sxs-lookup"><span data-stu-id="a1b62-132">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1b62-133">EndTime</span><span class="sxs-lookup"><span data-stu-id="a1b62-133">EndTime</span></span></p></td>
<td><p><span data-ttu-id="a1b62-134">datetime</span><span class="sxs-lookup"><span data-stu-id="a1b62-134">datetime</span></span></p></td>
<td><p><span data-ttu-id="a1b62-135">呼叫结束时间。</span><span class="sxs-lookup"><span data-stu-id="a1b62-135">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1b62-136">CallerPool</span><span class="sxs-lookup"><span data-stu-id="a1b62-136">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="a1b62-137">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="a1b62-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a1b62-138">呼叫者池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a1b62-138">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1b62-139">CalleePool</span><span class="sxs-lookup"><span data-stu-id="a1b62-139">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="a1b62-140">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="a1b62-140">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a1b62-141">被叫方池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="a1b62-141">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1b62-142">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="a1b62-142">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="a1b62-143">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="a1b62-143">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a1b62-144">呼叫者的 p 已断言标识 URI。</span><span class="sxs-lookup"><span data-stu-id="a1b62-144">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1b62-145">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="a1b62-145">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="a1b62-146">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="a1b62-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a1b62-147">被叫方的 p 已断言标识 URI。</span><span class="sxs-lookup"><span data-stu-id="a1b62-147">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1b62-148">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="a1b62-148">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="a1b62-149">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="a1b62-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a1b62-150">呼叫者的终结点名称。</span><span class="sxs-lookup"><span data-stu-id="a1b62-150">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1b62-151">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="a1b62-151">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="a1b62-152">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="a1b62-152">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a1b62-153">呼叫者的终结点名称。</span><span class="sxs-lookup"><span data-stu-id="a1b62-153">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1b62-154">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="a1b62-154">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="a1b62-155">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="a1b62-155">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a1b62-156">呼叫者的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="a1b62-156">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1b62-157">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="a1b62-157">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="a1b62-158">smallint</span><span class="sxs-lookup"><span data-stu-id="a1b62-158">smallint</span></span></p></td>
<td><p><span data-ttu-id="a1b62-159">呼叫者的用户代理类型。</span><span class="sxs-lookup"><span data-stu-id="a1b62-159">Type of caller’s user agent.</span></span> <span data-ttu-id="a1b62-160">有关详细信息，请参阅 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="a1b62-160">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1b62-161">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="a1b62-161">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="a1b62-162">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="a1b62-162">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="a1b62-163">呼叫者的用户代理的类别。</span><span class="sxs-lookup"><span data-stu-id="a1b62-163">Category of caller’s user agent.</span></span> <span data-ttu-id="a1b62-164">有关详细信息，请参阅 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表 (QoE) </a> 。</span><span class="sxs-lookup"><span data-stu-id="a1b62-164">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1b62-165">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="a1b62-165">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="a1b62-166">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="a1b62-166">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="a1b62-167">被叫方的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="a1b62-167">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1b62-168">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="a1b62-168">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="a1b62-169">smallint</span><span class="sxs-lookup"><span data-stu-id="a1b62-169">smallint</span></span></p></td>
<td><p><span data-ttu-id="a1b62-170">被叫方的用户代理的类型。</span><span class="sxs-lookup"><span data-stu-id="a1b62-170">Type of user agent for the callee.</span></span> <span data-ttu-id="a1b62-171">有关详细信息，请参阅 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="a1b62-171">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1b62-172">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="a1b62-172">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="a1b62-173">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="a1b62-173">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="a1b62-174">被叫方的用户代理类别。</span><span class="sxs-lookup"><span data-stu-id="a1b62-174">User agent category for the callee.</span></span> <span data-ttu-id="a1b62-175">有关详细信息，请参阅 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表 (QoE) </a> 。</span><span class="sxs-lookup"><span data-stu-id="a1b62-175">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1b62-176">CallerURI</span><span class="sxs-lookup"><span data-stu-id="a1b62-176">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="a1b62-177">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="a1b62-177">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a1b62-178">呼叫者的 URI。</span><span class="sxs-lookup"><span data-stu-id="a1b62-178">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="a1b62-179">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="a1b62-179">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="a1b62-180">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="a1b62-180">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="a1b62-181">被叫方的 URI。</span><span class="sxs-lookup"><span data-stu-id="a1b62-181">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="a1b62-182">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="a1b62-182">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="a1b62-183">int</span><span class="sxs-lookup"><span data-stu-id="a1b62-183">int</span></span></p></td>
<td><p><span data-ttu-id="a1b62-184">呼叫的优先级。</span><span class="sxs-lookup"><span data-stu-id="a1b62-184">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

