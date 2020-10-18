---
title: Lync Server 2013： Session 表
description: Lync Server 2013： Session 表。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Session table
ms:assetid: 7f05529c-794d-41ed-bca4-2e85b87b2dec
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398635(v=OCS.15)
ms:contentKeyID: 48184626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e1a52813dfea808253cc934f71a9d4c846c2dbbd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576448"
---
# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="84ee3-103">Lync Server 2013 中的会话表</span><span class="sxs-lookup"><span data-stu-id="84ee3-103">Session table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84ee3-104">_**上次修改的主题：** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="84ee3-104">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="84ee3-105">每个记录代表一个涉及音频或音频和视频的会话。</span><span class="sxs-lookup"><span data-stu-id="84ee3-105">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="84ee3-106">它包含有关会话的总体信息。</span><span class="sxs-lookup"><span data-stu-id="84ee3-106">It contains overall information about the session.</span></span> <span data-ttu-id="84ee3-107">会话在两个终结点之间定义为 (SIP) 对话的音频或视频会话初始协议。</span><span class="sxs-lookup"><span data-stu-id="84ee3-107">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="84ee3-108"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-108"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="84ee3-109"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-109"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="84ee3-110"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-110"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="84ee3-111"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-111"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84ee3-112"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-112"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="84ee3-113">datetime</span><span class="sxs-lookup"><span data-stu-id="84ee3-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="84ee3-114">主</span><span class="sxs-lookup"><span data-stu-id="84ee3-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="84ee3-115">从 <a href="lync-server-2013-dialog-table.md">Lync Server 2013 的对话框表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="84ee3-115">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ee3-116"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-116"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="84ee3-117">int</span><span class="sxs-lookup"><span data-stu-id="84ee3-117">int</span></span></p></td>
<td><p><span data-ttu-id="84ee3-118">主</span><span class="sxs-lookup"><span data-stu-id="84ee3-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="84ee3-119">从 <a href="lync-server-2013-dialog-table.md">Lync Server 2013 的对话框表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="84ee3-119">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ee3-120"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-120"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="84ee3-121">int</span><span class="sxs-lookup"><span data-stu-id="84ee3-121">int</span></span></p></td>
<td><p><span data-ttu-id="84ee3-122">对外</span><span class="sxs-lookup"><span data-stu-id="84ee3-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="84ee3-123">会议密钥。</span><span class="sxs-lookup"><span data-stu-id="84ee3-123">Conference key.</span></span> <span data-ttu-id="84ee3-124">从 <a href="lync-server-2013-conference-table.md">Lync Server 2013 中的会议表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="84ee3-124">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ee3-125"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-125"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="84ee3-126">int</span><span class="sxs-lookup"><span data-stu-id="84ee3-126">int</span></span></p></td>
<td><p><span data-ttu-id="84ee3-127">对外</span><span class="sxs-lookup"><span data-stu-id="84ee3-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="84ee3-128">相关密钥。</span><span class="sxs-lookup"><span data-stu-id="84ee3-128">Correlation key.</span></span> <span data-ttu-id="84ee3-129"><a href="lync-server-2013-sessioncorrelation-table.md">在 Lync Server 2013 中从 SessionCorrelation 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="84ee3-129">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ee3-130"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-130"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="84ee3-131">位</span><span class="sxs-lookup"><span data-stu-id="84ee3-131">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84ee3-132">对话框类别;0是 Lync Server 以进行中介服务器腿;1是中介服务器到 PSTN 网关腿。</span><span class="sxs-lookup"><span data-stu-id="84ee3-132">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ee3-133"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-133"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="84ee3-134">位</span><span class="sxs-lookup"><span data-stu-id="84ee3-134">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84ee3-135">指示是否绕过呼叫的标志。</span><span class="sxs-lookup"><span data-stu-id="84ee3-135">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ee3-136"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-136"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="84ee3-137">int</span><span class="sxs-lookup"><span data-stu-id="84ee3-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84ee3-138">如果存在，此字段指示即使绕过 ID 相匹配也没有绕过呼叫的原因。</span><span class="sxs-lookup"><span data-stu-id="84ee3-138">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="84ee3-139">对于 Lync Server，只定义一个值。</span><span class="sxs-lookup"><span data-stu-id="84ee3-139">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="84ee3-140">0x0001 –默认网络适配器的绕过旁路 ID。</span><span class="sxs-lookup"><span data-stu-id="84ee3-140">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ee3-141"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-141"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="84ee3-142">datetime</span><span class="sxs-lookup"><span data-stu-id="84ee3-142">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84ee3-143">呼叫开始时间。</span><span class="sxs-lookup"><span data-stu-id="84ee3-143">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ee3-144"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-144"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="84ee3-145">datetime</span><span class="sxs-lookup"><span data-stu-id="84ee3-145">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="84ee3-146">呼叫结束时间。</span><span class="sxs-lookup"><span data-stu-id="84ee3-146">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ee3-147"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-147"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="84ee3-148">int</span><span class="sxs-lookup"><span data-stu-id="84ee3-148">int</span></span></p></td>
<td><p><span data-ttu-id="84ee3-149">对外</span><span class="sxs-lookup"><span data-stu-id="84ee3-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="84ee3-150">呼叫者的池。</span><span class="sxs-lookup"><span data-stu-id="84ee3-150">The pool of the caller.</span></span> <span data-ttu-id="84ee3-151">从 <a href="lync-server-2013-pool-table.md">Lync Server 2013 的 Pool 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="84ee3-151">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ee3-152"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-152"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="84ee3-153">int</span><span class="sxs-lookup"><span data-stu-id="84ee3-153">int</span></span></p></td>
<td><p><span data-ttu-id="84ee3-154">对外</span><span class="sxs-lookup"><span data-stu-id="84ee3-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="84ee3-155">呼叫接收器的池。</span><span class="sxs-lookup"><span data-stu-id="84ee3-155">The pool of the call receiver.</span></span> <span data-ttu-id="84ee3-156">从 <a href="lync-server-2013-pool-table.md">Lync Server 2013 的 Pool 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="84ee3-156">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ee3-157"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-157"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="84ee3-158">int</span><span class="sxs-lookup"><span data-stu-id="84ee3-158">int</span></span></p></td>
<td><p><span data-ttu-id="84ee3-159">对外</span><span class="sxs-lookup"><span data-stu-id="84ee3-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="84ee3-160">SIP p-声明标识 (PAI) 中接收终结点的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="84ee3-160">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="84ee3-161"><a href="lync-server-2013-user-table.md">在 Lync Server 2013 的用户表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="84ee3-161">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ee3-162"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-162"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="84ee3-163">int</span><span class="sxs-lookup"><span data-stu-id="84ee3-163">int</span></span></p></td>
<td><p><span data-ttu-id="84ee3-164">对外</span><span class="sxs-lookup"><span data-stu-id="84ee3-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="84ee3-165">呼叫者的 URI。</span><span class="sxs-lookup"><span data-stu-id="84ee3-165">Caller’s URI.</span></span> <span data-ttu-id="84ee3-166"><a href="lync-server-2013-user-table.md">在 Lync Server 2013 的用户表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="84ee3-166">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ee3-167"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-167"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="84ee3-168">int</span><span class="sxs-lookup"><span data-stu-id="84ee3-168">int</span></span></p></td>
<td><p><span data-ttu-id="84ee3-169">对外</span><span class="sxs-lookup"><span data-stu-id="84ee3-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="84ee3-170">调用方的终结点。</span><span class="sxs-lookup"><span data-stu-id="84ee3-170">Caller’s endpoint.</span></span> <span data-ttu-id="84ee3-171">从 <a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的终结点表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="84ee3-171">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ee3-172"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-172"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="84ee3-173">位</span><span class="sxs-lookup"><span data-stu-id="84ee3-173">bit</span></span></p></td>
<td><p><span data-ttu-id="84ee3-174">对外</span><span class="sxs-lookup"><span data-stu-id="84ee3-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="84ee3-175">呼叫者的用户代理。</span><span class="sxs-lookup"><span data-stu-id="84ee3-175">Caller’s user agent.</span></span> <span data-ttu-id="84ee3-176"><a href="lync-server-2013-useragent-table.md">在 Lync Server 2013 中从 UserAgent 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="84ee3-176">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ee3-177"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-177"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="84ee3-178">smallint</span><span class="sxs-lookup"><span data-stu-id="84ee3-178">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84ee3-179">此调用的优先级。</span><span class="sxs-lookup"><span data-stu-id="84ee3-179">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ee3-180"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-180"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="84ee3-181">位</span><span class="sxs-lookup"><span data-stu-id="84ee3-181">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="84ee3-182">此列已弃用，并且在 Microsoft Lync Server 2013 中未使用。</span><span class="sxs-lookup"><span data-stu-id="84ee3-182">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="84ee3-183">而是在每个媒体的行基上报告此信息。</span><span class="sxs-lookup"><span data-stu-id="84ee3-183">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="84ee3-184">有关详细信息，请参阅 <a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="84ee3-184">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ee3-185"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-185"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="84ee3-186">int</span><span class="sxs-lookup"><span data-stu-id="84ee3-186">int</span></span></p></td>
<td><p><span data-ttu-id="84ee3-187">对外</span><span class="sxs-lookup"><span data-stu-id="84ee3-187">Foreign</span></span></p></td>
<td><p><span data-ttu-id="84ee3-188">P-声明-发出呼叫的用户的标识。</span><span class="sxs-lookup"><span data-stu-id="84ee3-188">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="84ee3-189">P 声明标识 (PAI) 用于传达发出呼叫的用户的真实标识。</span><span class="sxs-lookup"><span data-stu-id="84ee3-189">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ee3-190"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-190"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="84ee3-191">int</span><span class="sxs-lookup"><span data-stu-id="84ee3-191">int</span></span></p></td>
<td><p><span data-ttu-id="84ee3-192">对外</span><span class="sxs-lookup"><span data-stu-id="84ee3-192">Foreign</span></span></p></td>
<td><p><span data-ttu-id="84ee3-193">接收呼叫的终结点。</span><span class="sxs-lookup"><span data-stu-id="84ee3-193">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84ee3-194"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-194"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="84ee3-195">int</span><span class="sxs-lookup"><span data-stu-id="84ee3-195">int</span></span></p></td>
<td><p><span data-ttu-id="84ee3-196">对外</span><span class="sxs-lookup"><span data-stu-id="84ee3-196">Foreign</span></span></p></td>
<td><p><span data-ttu-id="84ee3-197">接收呼叫的用户使用的用户代理。</span><span class="sxs-lookup"><span data-stu-id="84ee3-197">User agent employed by the user who received the call.</span></span> <span data-ttu-id="84ee3-198">用户代理代表客户端终结点设备。</span><span class="sxs-lookup"><span data-stu-id="84ee3-198">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84ee3-199"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="84ee3-199"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="84ee3-200">int</span><span class="sxs-lookup"><span data-stu-id="84ee3-200">int</span></span></p></td>
<td><p><span data-ttu-id="84ee3-201">对外</span><span class="sxs-lookup"><span data-stu-id="84ee3-201">Foreign</span></span></p></td>
<td><p><span data-ttu-id="84ee3-202">接收呼叫的用户的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="84ee3-202">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

