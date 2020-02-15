---
title: Lync Server 2013： Session 表
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
ms.openlocfilehash: c252ef5cd96511875fa299f44ca2a707f766f59a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048943"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="session-table-in-lync-server-2013"></a><span data-ttu-id="de315-102">Lync Server 2013 中的会话表</span><span class="sxs-lookup"><span data-stu-id="de315-102">Session table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de315-103">_**上次修改的主题：** 2013-09-09_</span><span class="sxs-lookup"><span data-stu-id="de315-103">_**Topic Last Modified:** 2013-09-09_</span></span>

<span data-ttu-id="de315-104">每个记录代表一个涉及音频或音频和视频的会话。</span><span class="sxs-lookup"><span data-stu-id="de315-104">Each record represents one session which involves audio or audio and video.</span></span> <span data-ttu-id="de315-105">它包含有关会话的总体信息。</span><span class="sxs-lookup"><span data-stu-id="de315-105">It contains overall information about the session.</span></span> <span data-ttu-id="de315-106">会话定义为两个终结点之间的音频或视频会话初始协议（SIP）对话框。</span><span class="sxs-lookup"><span data-stu-id="de315-106">A session is defined as an audio or video Session Initiation Protocol (SIP) dialog between two endpoints.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="de315-107"><strong>列</strong></span><span class="sxs-lookup"><span data-stu-id="de315-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="de315-108"><strong>数据类型</strong></span><span class="sxs-lookup"><span data-stu-id="de315-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="de315-109"><strong>键/索引</strong></span><span class="sxs-lookup"><span data-stu-id="de315-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="de315-110"><strong>Details</strong></span><span class="sxs-lookup"><span data-stu-id="de315-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="de315-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="de315-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="de315-112">datetime</span><span class="sxs-lookup"><span data-stu-id="de315-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="de315-113">主</span><span class="sxs-lookup"><span data-stu-id="de315-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="de315-114">从<a href="lync-server-2013-dialog-table.md">Lync Server 2013 的对话框表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="de315-114">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de315-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="de315-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="de315-116">int</span><span class="sxs-lookup"><span data-stu-id="de315-116">int</span></span></p></td>
<td><p><span data-ttu-id="de315-117">主</span><span class="sxs-lookup"><span data-stu-id="de315-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="de315-118">从<a href="lync-server-2013-dialog-table.md">Lync Server 2013 的对话框表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="de315-118">Referenced from the <a href="lync-server-2013-dialog-table.md">Dialog table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de315-119"><strong>ConferenceKey</strong></span><span class="sxs-lookup"><span data-stu-id="de315-119"><strong>ConferenceKey</strong></span></span></p></td>
<td><p><span data-ttu-id="de315-120">int</span><span class="sxs-lookup"><span data-stu-id="de315-120">int</span></span></p></td>
<td><p><span data-ttu-id="de315-121">对外</span><span class="sxs-lookup"><span data-stu-id="de315-121">Foreign</span></span></p></td>
<td><p><span data-ttu-id="de315-122">会议密钥。</span><span class="sxs-lookup"><span data-stu-id="de315-122">Conference key.</span></span> <span data-ttu-id="de315-123">从<a href="lync-server-2013-conference-table.md">Lync Server 2013 中的会议表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="de315-123">Referenced from the <a href="lync-server-2013-conference-table.md">Conference table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de315-124"><strong>CorrelationKey</strong></span><span class="sxs-lookup"><span data-stu-id="de315-124"><strong>CorrelationKey</strong></span></span></p></td>
<td><p><span data-ttu-id="de315-125">int</span><span class="sxs-lookup"><span data-stu-id="de315-125">int</span></span></p></td>
<td><p><span data-ttu-id="de315-126">对外</span><span class="sxs-lookup"><span data-stu-id="de315-126">Foreign</span></span></p></td>
<td><p><span data-ttu-id="de315-127">相关密钥。</span><span class="sxs-lookup"><span data-stu-id="de315-127">Correlation key.</span></span> <span data-ttu-id="de315-128"><a href="lync-server-2013-sessioncorrelation-table.md">在 Lync Server 2013 中从 SessionCorrelation 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="de315-128">Referenced from the <a href="lync-server-2013-sessioncorrelation-table.md">SessionCorrelation table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de315-129"><strong>DialogCategory</strong></span><span class="sxs-lookup"><span data-stu-id="de315-129"><strong>DialogCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="de315-130">位</span><span class="sxs-lookup"><span data-stu-id="de315-130">bit</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="de315-131">对话框类别;0是 Lync Server 以进行中介服务器腿;1是中介服务器到 PSTN 网关腿。</span><span class="sxs-lookup"><span data-stu-id="de315-131">Dialog category; 0 is Lync Server to Mediation Server leg; 1 is Mediation Server to PSTN gateway leg.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de315-132"><strong>MediationServerBypassFlag</strong></span><span class="sxs-lookup"><span data-stu-id="de315-132"><strong>MediationServerBypassFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="de315-133">位</span><span class="sxs-lookup"><span data-stu-id="de315-133">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="de315-134">指示是否绕过呼叫的标志。</span><span class="sxs-lookup"><span data-stu-id="de315-134">Flag indicating if the call was bypassed or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de315-135"><strong>MediaBypassWarningFlag</strong></span><span class="sxs-lookup"><span data-stu-id="de315-135"><strong>MediaBypassWarningFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="de315-136">int</span><span class="sxs-lookup"><span data-stu-id="de315-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="de315-137">如果存在，此字段指示即使绕过 ID 相匹配也没有绕过呼叫的原因。</span><span class="sxs-lookup"><span data-stu-id="de315-137">This field, if present, indicates why a call was not bypassed even if the bypass IDs matched.</span></span> <span data-ttu-id="de315-138">对于 Lync Server，只定义一个值。</span><span class="sxs-lookup"><span data-stu-id="de315-138">For Lync Server, only one value is defined.</span></span></p>
<p><span data-ttu-id="de315-139">0x0001 –默认网络适配器的绕过旁路 ID。</span><span class="sxs-lookup"><span data-stu-id="de315-139">0x0001 – Unknown bypass ID for Default network adapter.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de315-140"><strong>StartTime</strong></span><span class="sxs-lookup"><span data-stu-id="de315-140"><strong>StartTime</strong></span></span></p></td>
<td><p><span data-ttu-id="de315-141">datetime</span><span class="sxs-lookup"><span data-stu-id="de315-141">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="de315-142">呼叫开始时间。</span><span class="sxs-lookup"><span data-stu-id="de315-142">Call start time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de315-143"><strong>EndTime</strong></span><span class="sxs-lookup"><span data-stu-id="de315-143"><strong>EndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="de315-144">datetime</span><span class="sxs-lookup"><span data-stu-id="de315-144">datetime</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="de315-145">呼叫结束时间。</span><span class="sxs-lookup"><span data-stu-id="de315-145">Call end time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de315-146"><strong>CallerPool</strong></span><span class="sxs-lookup"><span data-stu-id="de315-146"><strong>CallerPool</strong></span></span></p></td>
<td><p><span data-ttu-id="de315-147">int</span><span class="sxs-lookup"><span data-stu-id="de315-147">int</span></span></p></td>
<td><p><span data-ttu-id="de315-148">对外</span><span class="sxs-lookup"><span data-stu-id="de315-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="de315-149">呼叫者的池。</span><span class="sxs-lookup"><span data-stu-id="de315-149">The pool of the caller.</span></span> <span data-ttu-id="de315-150">从<a href="lync-server-2013-pool-table.md">Lync Server 2013 的 Pool 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="de315-150">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de315-151"><strong>CalleePool</strong></span><span class="sxs-lookup"><span data-stu-id="de315-151"><strong>CalleePool</strong></span></span></p></td>
<td><p><span data-ttu-id="de315-152">int</span><span class="sxs-lookup"><span data-stu-id="de315-152">int</span></span></p></td>
<td><p><span data-ttu-id="de315-153">对外</span><span class="sxs-lookup"><span data-stu-id="de315-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="de315-154">呼叫接收器的池。</span><span class="sxs-lookup"><span data-stu-id="de315-154">The pool of the call receiver.</span></span> <span data-ttu-id="de315-155">从<a href="lync-server-2013-pool-table.md">Lync Server 2013 的 Pool 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="de315-155">Referenced from the <a href="lync-server-2013-pool-table.md">Pool table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de315-156"><strong>CalleePAI</strong></span><span class="sxs-lookup"><span data-stu-id="de315-156"><strong>CalleePAI</strong></span></span></p></td>
<td><p><span data-ttu-id="de315-157">int</span><span class="sxs-lookup"><span data-stu-id="de315-157">int</span></span></p></td>
<td><p><span data-ttu-id="de315-158">对外</span><span class="sxs-lookup"><span data-stu-id="de315-158">Foreign</span></span></p></td>
<td><p><span data-ttu-id="de315-159">接收终结点的 SIP p 声明标识（PAI）中的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="de315-159">SIP URI in the SIP p-asserted identity (PAI) of the receiving endpoint.</span></span> <span data-ttu-id="de315-160"><a href="lync-server-2013-user-table.md">在 Lync Server 2013 的用户表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="de315-160">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de315-161"><strong>CallerURI</strong></span><span class="sxs-lookup"><span data-stu-id="de315-161"><strong>CallerURI</strong></span></span></p></td>
<td><p><span data-ttu-id="de315-162">int</span><span class="sxs-lookup"><span data-stu-id="de315-162">int</span></span></p></td>
<td><p><span data-ttu-id="de315-163">对外</span><span class="sxs-lookup"><span data-stu-id="de315-163">Foreign</span></span></p></td>
<td><p><span data-ttu-id="de315-164">呼叫者的 URI。</span><span class="sxs-lookup"><span data-stu-id="de315-164">Caller’s URI.</span></span> <span data-ttu-id="de315-165"><a href="lync-server-2013-user-table.md">在 Lync Server 2013 的用户表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="de315-165">Referenced from the <a href="lync-server-2013-user-table.md">User table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de315-166"><strong>CallerEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="de315-166"><strong>CallerEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="de315-167">int</span><span class="sxs-lookup"><span data-stu-id="de315-167">int</span></span></p></td>
<td><p><span data-ttu-id="de315-168">对外</span><span class="sxs-lookup"><span data-stu-id="de315-168">Foreign</span></span></p></td>
<td><p><span data-ttu-id="de315-169">调用方的终结点。</span><span class="sxs-lookup"><span data-stu-id="de315-169">Caller’s endpoint.</span></span> <span data-ttu-id="de315-170">从<a href="lync-server-2013-endpoint-table.md">Lync Server 2013 中的终结点表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="de315-170">Referenced from the <a href="lync-server-2013-endpoint-table.md">Endpoint table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de315-171"><strong>CallerUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="de315-171"><strong>CallerUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="de315-172">位</span><span class="sxs-lookup"><span data-stu-id="de315-172">bit</span></span></p></td>
<td><p><span data-ttu-id="de315-173">对外</span><span class="sxs-lookup"><span data-stu-id="de315-173">Foreign</span></span></p></td>
<td><p><span data-ttu-id="de315-174">呼叫者的用户代理。</span><span class="sxs-lookup"><span data-stu-id="de315-174">Caller’s user agent.</span></span> <span data-ttu-id="de315-175"><a href="lync-server-2013-useragent-table.md">在 Lync Server 2013 中从 UserAgent 表中</a>引用。</span><span class="sxs-lookup"><span data-stu-id="de315-175">Referenced from the <a href="lync-server-2013-useragent-table.md">UserAgent table in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de315-176"><strong>CallPriority</strong></span><span class="sxs-lookup"><span data-stu-id="de315-176"><strong>CallPriority</strong></span></span></p></td>
<td><p><span data-ttu-id="de315-177">smallint</span><span class="sxs-lookup"><span data-stu-id="de315-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="de315-178">此调用的优先级。</span><span class="sxs-lookup"><span data-stu-id="de315-178">The priority of this call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de315-179"><strong>ClassifiedPoorCall</strong></span><span class="sxs-lookup"><span data-stu-id="de315-179"><strong>ClassifiedPoorCall</strong></span></span></p></td>
<td><p><span data-ttu-id="de315-180">位</span><span class="sxs-lookup"><span data-stu-id="de315-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="de315-181">此列已弃用，并且在 Microsoft Lync Server 2013 中未使用。</span><span class="sxs-lookup"><span data-stu-id="de315-181">This column has been deprecated and is not used in Microsoft Lync Server 2013.</span></span> <span data-ttu-id="de315-182">而是在每个媒体的行基上报告此信息。</span><span class="sxs-lookup"><span data-stu-id="de315-182">Instead, this information is reported on a per-media line bases.</span></span> <span data-ttu-id="de315-183">有关详细信息，请参阅<a href="lync-server-2013-medialine-table.md">Lync Server 2013 中的 MediaLine 表</a>。</span><span class="sxs-lookup"><span data-stu-id="de315-183">Refer to the <a href="lync-server-2013-medialine-table.md">MediaLine table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de315-184"><strong>CallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="de315-184"><strong>CallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="de315-185">int</span><span class="sxs-lookup"><span data-stu-id="de315-185">int</span></span></p></td>
<td><p><span data-ttu-id="de315-186">对外</span><span class="sxs-lookup"><span data-stu-id="de315-186">Foreign</span></span></p></td>
<td><p><span data-ttu-id="de315-187">P-声明-发出呼叫的用户的标识。</span><span class="sxs-lookup"><span data-stu-id="de315-187">P-Asserted-Identity of the user who placed the call.</span></span> <span data-ttu-id="de315-188">P 声明标识（PAI）用于传达发出呼叫的用户的真实标识。</span><span class="sxs-lookup"><span data-stu-id="de315-188">The P-Asserted-Identity (PAI) is used to convey the true identity of the user who placed the call.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de315-189"><strong>CalleeEndpoint</strong></span><span class="sxs-lookup"><span data-stu-id="de315-189"><strong>CalleeEndpoint</strong></span></span></p></td>
<td><p><span data-ttu-id="de315-190">int</span><span class="sxs-lookup"><span data-stu-id="de315-190">int</span></span></p></td>
<td><p><span data-ttu-id="de315-191">对外</span><span class="sxs-lookup"><span data-stu-id="de315-191">Foreign</span></span></p></td>
<td><p><span data-ttu-id="de315-192">接收呼叫的终结点。</span><span class="sxs-lookup"><span data-stu-id="de315-192">Endpoint that received the call.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="de315-193"><strong>CalleeUserAgent</strong></span><span class="sxs-lookup"><span data-stu-id="de315-193"><strong>CalleeUserAgent</strong></span></span></p></td>
<td><p><span data-ttu-id="de315-194">int</span><span class="sxs-lookup"><span data-stu-id="de315-194">int</span></span></p></td>
<td><p><span data-ttu-id="de315-195">对外</span><span class="sxs-lookup"><span data-stu-id="de315-195">Foreign</span></span></p></td>
<td><p><span data-ttu-id="de315-196">接收呼叫的用户使用的用户代理。</span><span class="sxs-lookup"><span data-stu-id="de315-196">User agent employed by the user who received the call.</span></span> <span data-ttu-id="de315-197">用户代理代表客户端终结点设备。</span><span class="sxs-lookup"><span data-stu-id="de315-197">User agents represent the client endpoint device.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="de315-198"><strong>CalleeUri</strong></span><span class="sxs-lookup"><span data-stu-id="de315-198"><strong>CalleeUri</strong></span></span></p></td>
<td><p><span data-ttu-id="de315-199">int</span><span class="sxs-lookup"><span data-stu-id="de315-199">int</span></span></p></td>
<td><p><span data-ttu-id="de315-200">对外</span><span class="sxs-lookup"><span data-stu-id="de315-200">Foreign</span></span></p></td>
<td><p><span data-ttu-id="de315-201">接收呼叫的用户的 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="de315-201">SIP URI of the user who received the call.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

