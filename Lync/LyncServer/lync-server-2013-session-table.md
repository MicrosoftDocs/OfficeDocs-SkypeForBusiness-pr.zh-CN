---
title: Lync Server 2013：Session 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ab4eb63b95ecdf08c1967babba39cff2b2abf19
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822046"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="e1f1a-102">Lync Server 2013 中的 Session 表</span><span class="sxs-lookup"><span data-stu-id="e1f1a-102">Session table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1f1a-103">_**主题上次修改时间:** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="e1f1a-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="e1f1a-104">每条记录表示一个包含音频或音频和视频的会话。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="e1f1a-105">它包含有关会话的整体信息。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-105">It contains overall information about the session.</span></span> <span data-ttu-id="e1f1a-106">会话在两个终结点之间定义为音频或视频会话初始协议 (SIP) 对话框。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="e1f1a-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="e1f1a-108"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="e1f1a-109"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="e1f1a-110"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="e1f1a-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e1f1a-112">datetime</span><span class="sxs-lookup"><span data-stu-id="e1f1a-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e1f1a-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-114">从<a href="lync-server-2013-dialog-table.md">Lync Server 2013 的对话框表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1f1a-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="e1f1a-116">int</span><span class="sxs-lookup"><span data-stu-id="e1f1a-116">int</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-117">Primary</span><span class="sxs-lookup"><span data-stu-id="e1f1a-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-118">从<a href="lync-server-2013-dialog-table.md">Lync Server 2013 的对话框表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1f1a-119"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e1f1a-120">int</span><span class="sxs-lookup"><span data-stu-id="e1f1a-120">int</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-121">外表</span><span class="sxs-lookup"><span data-stu-id="e1f1a-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-122">会议密钥。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-122">Conference key.</span></span> <span data-ttu-id="e1f1a-123">从<a href="lync-server-2013-conference-table.md">Lync Server 2013 中的 "会议" 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1f1a-124"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="e1f1a-125">int</span><span class="sxs-lookup"><span data-stu-id="e1f1a-125">int</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-126">外表</span><span class="sxs-lookup"><span data-stu-id="e1f1a-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-127">相关密钥。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-127">Correlation key.</span></span> <span data-ttu-id="e1f1a-128">从<a href="lync-server-2013-sessioncorrelation-table.md">Lync Server 2013 中的 SessionCorrelation 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1f1a-129"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="e1f1a-130">bit</span><span class="sxs-lookup"><span data-stu-id="e1f1a-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e1f1a-131">对话框类别;0是 Lync 服务器以中介服务器腿;1是中介服务器到 PSTN 网关腿。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1f1a-132"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e1f1a-133">bit</span><span class="sxs-lookup"><span data-stu-id="e1f1a-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e1f1a-134">指示是否已绕过呼叫的标志。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1f1a-135"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="e1f1a-136">int</span><span class="sxs-lookup"><span data-stu-id="e1f1a-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e1f1a-137">此字段 (如果存在) 指示无法跳过呼叫的原因, 即使旁路 Id 匹配也是如此。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="e1f1a-138">对于 Lync Server, 只定义一个值。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="e1f1a-139">0x0001-默认网络适配器的旁路 ID 未知。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1f1a-140"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e1f1a-141">datetime</span><span class="sxs-lookup"><span data-stu-id="e1f1a-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e1f1a-142">通话开始时间。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1f1a-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="e1f1a-144">datetime</span><span class="sxs-lookup"><span data-stu-id="e1f1a-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="e1f1a-145">通话结束时间。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1f1a-146"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="e1f1a-147">int</span><span class="sxs-lookup"><span data-stu-id="e1f1a-147">int</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-148">外表</span><span class="sxs-lookup"><span data-stu-id="e1f1a-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-149">呼叫方的池。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-149">The pool of the caller.</span></span> <span data-ttu-id="e1f1a-150">从<a href="lync-server-2013-pool-table.md">Lync Server 2013 的 Pool 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1f1a-151"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="e1f1a-152">int</span><span class="sxs-lookup"><span data-stu-id="e1f1a-152">int</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-153">外表</span><span class="sxs-lookup"><span data-stu-id="e1f1a-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-154">呼叫接收器的池。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-154">The pool of the call receiver.</span></span> <span data-ttu-id="e1f1a-155">从<a href="lync-server-2013-pool-table.md">Lync Server 2013 的 Pool 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1f1a-156"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="e1f1a-157">int</span><span class="sxs-lookup"><span data-stu-id="e1f1a-157">int</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-158">外表</span><span class="sxs-lookup"><span data-stu-id="e1f1a-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-159">接收终结点的 SIP p 声明标识 (PAI) 中的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="e1f1a-160">从<a href="lync-server-2013-user-table.md">Lync Server 2013 中的用户表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1f1a-161"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="e1f1a-162">int</span><span class="sxs-lookup"><span data-stu-id="e1f1a-162">int</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-163">外表</span><span class="sxs-lookup"><span data-stu-id="e1f1a-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-164">调用方的 URI。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-164">Caller’s URI.</span></span> <span data-ttu-id="e1f1a-165">从<a href="lync-server-2013-user-table.md">Lync Server 2013 中的用户表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1f1a-166"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="e1f1a-167">int</span><span class="sxs-lookup"><span data-stu-id="e1f1a-167">int</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-168">外表</span><span class="sxs-lookup"><span data-stu-id="e1f1a-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-169">调用方的终结点。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-169">Caller’s endpoint.</span></span> <span data-ttu-id="e1f1a-170">从<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 的终结点表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1f1a-171"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="e1f1a-172">bit</span><span class="sxs-lookup"><span data-stu-id="e1f1a-172">bit</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-173">外表</span><span class="sxs-lookup"><span data-stu-id="e1f1a-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-174">呼叫方的用户代理。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-174">Caller’s user agent.</span></span> <span data-ttu-id="e1f1a-175">从<a href="lync-server-2013-useragent-table.md">Lync Server 2013 中的 UserAgent 表</a>引用。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1f1a-176"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="e1f1a-177">smallint</span><span class="sxs-lookup"><span data-stu-id="e1f1a-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e1f1a-178">此通话的优先级。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1f1a-179"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="e1f1a-180">bit</span><span class="sxs-lookup"><span data-stu-id="e1f1a-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="e1f1a-181">此列已弃用, 并且未在 Microsoft Lync Server 2013 中使用。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="e1f1a-182">而是报告每个媒体行基础上的此信息。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="e1f1a-183">有关详细信息, 请参阅<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1f1a-184"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="e1f1a-185">int</span><span class="sxs-lookup"><span data-stu-id="e1f1a-185">int</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-186">外表</span><span class="sxs-lookup"><span data-stu-id="e1f1a-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-187">P-声明-发出呼叫的用户的标识。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="e1f1a-188">P 声明的标识 (PAI) 用于传达发出呼叫的用户的真实标识。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1f1a-189"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="e1f1a-190">int</span><span class="sxs-lookup"><span data-stu-id="e1f1a-190">int</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-191">外表</span><span class="sxs-lookup"><span data-stu-id="e1f1a-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-192">接收呼叫的终结点。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="e1f1a-193"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="e1f1a-194">int</span><span class="sxs-lookup"><span data-stu-id="e1f1a-194">int</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-195">外表</span><span class="sxs-lookup"><span data-stu-id="e1f1a-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-196">接收呼叫的用户所使用的用户代理。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="e1f1a-197">用户代理代表客户端终结点设备。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="e1f1a-198"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="e1f1a-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="e1f1a-199">int</span><span class="sxs-lookup"><span data-stu-id="e1f1a-199">int</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-200">外表</span><span class="sxs-lookup"><span data-stu-id="e1f1a-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="e1f1a-201">接收呼叫的用户的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="e1f1a-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

