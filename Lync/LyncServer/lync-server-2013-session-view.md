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
ms.openlocfilehash: 30183ffde7380b5029ac458f102eaf81ecee914b
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48510089"
---
# <a name="session-view-in-lync-server-2013"></a><span data-ttu-id="b87af-102">Lync Server 2013 中的会话视图</span><span class="sxs-lookup"><span data-stu-id="b87af-102">Session view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b87af-103">_**上次修改的主题：** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="b87af-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="b87af-104">会话视图存储有关在数据库中具有记录的会话的信息。</span><span class="sxs-lookup"><span data-stu-id="b87af-104">The Session View stores information about sessions that have records in the database.</span></span> <span data-ttu-id="b87af-105">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="b87af-105">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b87af-106">列</span><span class="sxs-lookup"><span data-stu-id="b87af-106">Column</span></span></th>
<th><span data-ttu-id="b87af-107">数据类型</span><span class="sxs-lookup"><span data-stu-id="b87af-107">Data Type</span></span></th>
<th><span data-ttu-id="b87af-108">详细信息</span><span class="sxs-lookup"><span data-stu-id="b87af-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b87af-109">ConferenceDateTime</span><span class="sxs-lookup"><span data-stu-id="b87af-109">ConferenceDateTime</span></span></p></td>
<td><p><span data-ttu-id="b87af-110">datetime</span><span class="sxs-lookup"><span data-stu-id="b87af-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="b87af-111">引用自 MediaLine 表。</span><span class="sxs-lookup"><span data-stu-id="b87af-111">Referenced from the MediaLine Table.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b87af-112">ConferenceURI</span><span class="sxs-lookup"><span data-stu-id="b87af-112">ConferenceURI</span></span></p></td>
<td><p><span data-ttu-id="b87af-113">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="b87af-113">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b87af-114">如果是会议，则是会议 URI；如果是点对点会话，则是 DialogID。</span><span class="sxs-lookup"><span data-stu-id="b87af-114">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b87af-115">相关性</span><span class="sxs-lookup"><span data-stu-id="b87af-115">Correlation</span></span></p></td>
<td><p><span data-ttu-id="b87af-116">varchar (max) </span><span class="sxs-lookup"><span data-stu-id="b87af-116">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="b87af-117">会话的关联 ID。</span><span class="sxs-lookup"><span data-stu-id="b87af-117">Correlation ID of the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b87af-118">DialogCategory</span><span class="sxs-lookup"><span data-stu-id="b87af-118">DialogCategory</span></span></p></td>
<td><p><span data-ttu-id="b87af-119">位</span><span class="sxs-lookup"><span data-stu-id="b87af-119">bit</span></span></p></td>
<td><p><span data-ttu-id="b87af-120">对话框类别;0是 Lync Server 以进行中介服务器腿;1是中介服务器到 PSTN 网关腿。</span><span class="sxs-lookup"><span data-stu-id="b87af-120">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b87af-121">MediationServerBypassFlag</span><span class="sxs-lookup"><span data-stu-id="b87af-121">MediationServerBypassFlag</span></span></p></td>
<td><p><span data-ttu-id="b87af-122">位</span><span class="sxs-lookup"><span data-stu-id="b87af-122">bit</span></span></p></td>
<td><p><span data-ttu-id="b87af-123">指示是否旁路了呼叫。</span><span class="sxs-lookup"><span data-stu-id="b87af-123">Indicates whether or not the call was bypassed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b87af-124">MediaBypassWarningFlag</span><span class="sxs-lookup"><span data-stu-id="b87af-124">MediaBypassWarningFlag</span></span></p></td>
<td><p><span data-ttu-id="b87af-125">int</span><span class="sxs-lookup"><span data-stu-id="b87af-125">int</span></span></p></td>
<td><p><span data-ttu-id="b87af-126">如果存在，此字段指示即使绕过 ID 相匹配也没有绕过呼叫的原因。</span><span class="sxs-lookup"><span data-stu-id="b87af-126">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="b87af-127">对于 Lync Server，仅定义了一个值：</span><span class="sxs-lookup"><span data-stu-id="b87af-127">For Lync Server, only one value is defined:</span></span></p>
<p><span data-ttu-id="b87af-128">0x0001 – 默认网络适配器的未知旁路 ID</span><span class="sxs-lookup"><span data-stu-id="b87af-128">0x0001 – Unknown bypass ID for Default network adapter</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b87af-129">StartTime</span><span class="sxs-lookup"><span data-stu-id="b87af-129">StartTime</span></span></p></td>
<td><p><span data-ttu-id="b87af-130">datetime</span><span class="sxs-lookup"><span data-stu-id="b87af-130">datetime</span></span></p></td>
<td><p><span data-ttu-id="b87af-131">呼叫开始时间。</span><span class="sxs-lookup"><span data-stu-id="b87af-131">Call start time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b87af-132">EndTime</span><span class="sxs-lookup"><span data-stu-id="b87af-132">EndTime</span></span></p></td>
<td><p><span data-ttu-id="b87af-133">datetime</span><span class="sxs-lookup"><span data-stu-id="b87af-133">datetime</span></span></p></td>
<td><p><span data-ttu-id="b87af-134">呼叫结束时间。</span><span class="sxs-lookup"><span data-stu-id="b87af-134">Call end time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b87af-135">CallerPool</span><span class="sxs-lookup"><span data-stu-id="b87af-135">CallerPool</span></span></p></td>
<td><p><span data-ttu-id="b87af-136">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b87af-136">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b87af-137">呼叫者池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b87af-137">Caller pool FQDN.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b87af-138">CalleePool</span><span class="sxs-lookup"><span data-stu-id="b87af-138">CalleePool</span></span></p></td>
<td><p><span data-ttu-id="b87af-139">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b87af-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b87af-140">被叫方池 FQDN。</span><span class="sxs-lookup"><span data-stu-id="b87af-140">Callee pool FQDN.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b87af-141">CallerPAI</span><span class="sxs-lookup"><span data-stu-id="b87af-141">CallerPAI</span></span></p></td>
<td><p><span data-ttu-id="b87af-142">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="b87af-142">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b87af-143">呼叫者的 p 已断言标识 URI。</span><span class="sxs-lookup"><span data-stu-id="b87af-143">Caller’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b87af-144">CalleePAI</span><span class="sxs-lookup"><span data-stu-id="b87af-144">CalleePAI</span></span></p></td>
<td><p><span data-ttu-id="b87af-145">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="b87af-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b87af-146">被叫方的 p 已断言标识 URI。</span><span class="sxs-lookup"><span data-stu-id="b87af-146">Callee’s p-asserted identity URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b87af-147">CallerEndpoint</span><span class="sxs-lookup"><span data-stu-id="b87af-147">CallerEndpoint</span></span></p></td>
<td><p><span data-ttu-id="b87af-148">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b87af-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b87af-149">呼叫者的终结点名称。</span><span class="sxs-lookup"><span data-stu-id="b87af-149">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b87af-150">CalleeEndpoint</span><span class="sxs-lookup"><span data-stu-id="b87af-150">CalleeEndpoint</span></span></p></td>
<td><p><span data-ttu-id="b87af-151">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b87af-151">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b87af-152">呼叫者的终结点名称。</span><span class="sxs-lookup"><span data-stu-id="b87af-152">Caller’s endpoint name.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b87af-153">CallerUserAgent</span><span class="sxs-lookup"><span data-stu-id="b87af-153">CallerUserAgent</span></span></p></td>
<td><p><span data-ttu-id="b87af-154">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b87af-154">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b87af-155">呼叫者的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="b87af-155">Caller’s user agent string.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b87af-156">CallerUserAgentType</span><span class="sxs-lookup"><span data-stu-id="b87af-156">CallerUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="b87af-157">smallint</span><span class="sxs-lookup"><span data-stu-id="b87af-157">smallint</span></span></p></td>
<td><p><span data-ttu-id="b87af-158">呼叫者的用户代理类型。</span><span class="sxs-lookup"><span data-stu-id="b87af-158">Type of caller’s user agent.</span></span> <span data-ttu-id="b87af-159">有关详细信息，请参阅 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="b87af-159">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b87af-160">CallerUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="b87af-160">CallerUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="b87af-161">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b87af-161">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="b87af-162">呼叫者的用户代理的类别。</span><span class="sxs-lookup"><span data-stu-id="b87af-162">Category of caller’s user agent.</span></span> <span data-ttu-id="b87af-163">有关详细信息，请参阅 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表 (QoE) </a> 。</span><span class="sxs-lookup"><span data-stu-id="b87af-163">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b87af-164">CalleeUserAgent</span><span class="sxs-lookup"><span data-stu-id="b87af-164">CalleeUserAgent</span></span></p></td>
<td><p><span data-ttu-id="b87af-165">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b87af-165">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="b87af-166">被叫方的用户代理字符串。</span><span class="sxs-lookup"><span data-stu-id="b87af-166">Callee’s user agent string.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b87af-167">CalleeUserAgentType</span><span class="sxs-lookup"><span data-stu-id="b87af-167">CalleeUserAgentType</span></span></p></td>
<td><p><span data-ttu-id="b87af-168">smallint</span><span class="sxs-lookup"><span data-stu-id="b87af-168">smallint</span></span></p></td>
<td><p><span data-ttu-id="b87af-169">被叫方的用户代理的类型。</span><span class="sxs-lookup"><span data-stu-id="b87af-169">Type of user agent for the callee.</span></span> <span data-ttu-id="b87af-170">有关详细信息，请参阅 <a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="b87af-170">See the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b87af-171">CalleeUserAgentCategory</span><span class="sxs-lookup"><span data-stu-id="b87af-171">CalleeUserAgentCategory</span></span></p></td>
<td><p><span data-ttu-id="b87af-172">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="b87af-172">nvarchar (64)</span></span></p></td>
<td><p><span data-ttu-id="b87af-173">被叫方的用户代理类别。</span><span class="sxs-lookup"><span data-stu-id="b87af-173">User agent category for the callee.</span></span> <span data-ttu-id="b87af-174">有关详细信息，请参阅 <a href="lync-server-2013-useragentdef-table-qoe.md">Lync Server 2013 中的 UserAgentDef 表 (QoE) </a> 。</span><span class="sxs-lookup"><span data-stu-id="b87af-174">See the <a href="lync-server-2013-useragentdef-table-qoe.md">UserAgentDef table (QoE) in Lync Server 2013</a> for details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b87af-175">CallerURI</span><span class="sxs-lookup"><span data-stu-id="b87af-175">CallerURI</span></span></p></td>
<td><p><span data-ttu-id="b87af-176">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="b87af-176">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b87af-177">呼叫者的 URI。</span><span class="sxs-lookup"><span data-stu-id="b87af-177">Caller’s URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b87af-178">CalleeURI</span><span class="sxs-lookup"><span data-stu-id="b87af-178">CalleeURI</span></span></p></td>
<td><p><span data-ttu-id="b87af-179">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="b87af-179">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="b87af-180">被叫方的 URI。</span><span class="sxs-lookup"><span data-stu-id="b87af-180">Callee’s URI.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b87af-181">CallPrioirty</span><span class="sxs-lookup"><span data-stu-id="b87af-181">CallPrioirty</span></span></p></td>
<td><p><span data-ttu-id="b87af-182">int</span><span class="sxs-lookup"><span data-stu-id="b87af-182">int</span></span></p></td>
<td><p><span data-ttu-id="b87af-183">呼叫的优先级。</span><span class="sxs-lookup"><span data-stu-id="b87af-183">Priority of the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

