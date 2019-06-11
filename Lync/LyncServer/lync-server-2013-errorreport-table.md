---
title: Lync Server 2013：ErrorReport 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0fc30d4686ffcc1d1cda0474b3b01a645c94be5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830200"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="aa39a-102">Lync Server 2013 中的 ErrorReport 表</span><span class="sxs-lookup"><span data-stu-id="aa39a-102">ErrorReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="aa39a-103">_**主题上次修改时间:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="aa39a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="aa39a-104">ErrorReport 表存储发生的错误的相关信息。</span><span class="sxs-lookup"><span data-stu-id="aa39a-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="aa39a-105">每条记录是一个错误发生。</span><span class="sxs-lookup"><span data-stu-id="aa39a-105">Each record is one error occurrence.</span></span> <span data-ttu-id="aa39a-106">这些错误由前端服务器上运行的 CDR 代理或从客户端发送的 CDR 捕获。</span><span class="sxs-lookup"><span data-stu-id="aa39a-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="aa39a-107">列</span><span class="sxs-lookup"><span data-stu-id="aa39a-107">Column</span></span></th>
<th><span data-ttu-id="aa39a-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="aa39a-108">Data Type</span></span></th>
<th><span data-ttu-id="aa39a-109">键/索引</span><span class="sxs-lookup"><span data-stu-id="aa39a-109">Key/Index</span></span></th>
<th><span data-ttu-id="aa39a-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="aa39a-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="aa39a-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="aa39a-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="aa39a-112">datetime</span><span class="sxs-lookup"><span data-stu-id="aa39a-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="aa39a-113">Primary</span><span class="sxs-lookup"><span data-stu-id="aa39a-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="aa39a-114">出现错误的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="aa39a-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa39a-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="aa39a-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="aa39a-116">int</span><span class="sxs-lookup"><span data-stu-id="aa39a-116">int</span></span></p></td>
<td><p><span data-ttu-id="aa39a-117">Primary</span><span class="sxs-lookup"><span data-stu-id="aa39a-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="aa39a-118">标识错误报告的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="aa39a-118">ID number to identify the error report.</span></span> <span data-ttu-id="aa39a-119">与<strong>ErrorTime</strong>结合使用以唯一标识错误报告。</span><span class="sxs-lookup"><span data-stu-id="aa39a-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa39a-120"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="aa39a-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="aa39a-121">int</span><span class="sxs-lookup"><span data-stu-id="aa39a-121">int</span></span></p></td>
<td><p><span data-ttu-id="aa39a-122">外表</span><span class="sxs-lookup"><span data-stu-id="aa39a-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="aa39a-123">错误类型的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="aa39a-123">Unique ID of the error type.</span></span> <span data-ttu-id="aa39a-124">有关详细信息, 请参阅<a href="lync-server-2013-errordef-table.md">Lync Server 2013 中的 ErrorDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="aa39a-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa39a-125"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="aa39a-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="aa39a-126">int</span><span class="sxs-lookup"><span data-stu-id="aa39a-126">int</span></span></p></td>
<td><p><span data-ttu-id="aa39a-127">外表</span><span class="sxs-lookup"><span data-stu-id="aa39a-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="aa39a-128">发出导致错误的请求的用户。</span><span class="sxs-lookup"><span data-stu-id="aa39a-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="aa39a-129">有关详细信息, 请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 "用户" 表。</span><span class="sxs-lookup"><span data-stu-id="aa39a-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa39a-130"><strong>ToUserId</strong></span><span class="sxs-lookup"><span data-stu-id="aa39a-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="aa39a-131">int</span><span class="sxs-lookup"><span data-stu-id="aa39a-131">int</span></span></p></td>
<td><p><span data-ttu-id="aa39a-132">外表</span><span class="sxs-lookup"><span data-stu-id="aa39a-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="aa39a-133">导致错误的请求的目标用户。</span><span class="sxs-lookup"><span data-stu-id="aa39a-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="aa39a-134">有关详细信息, 请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中</a>的 "用户" 表。</span><span class="sxs-lookup"><span data-stu-id="aa39a-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa39a-135"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="aa39a-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="aa39a-136">int</span><span class="sxs-lookup"><span data-stu-id="aa39a-136">int</span></span></p></td>
<td><p><span data-ttu-id="aa39a-137">外表</span><span class="sxs-lookup"><span data-stu-id="aa39a-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="aa39a-138">与该错误相关的会议 URI。</span><span class="sxs-lookup"><span data-stu-id="aa39a-138">Conference URI related to the error.</span></span> <span data-ttu-id="aa39a-139">有关详细信息, 请参阅<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a>。</span><span class="sxs-lookup"><span data-stu-id="aa39a-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="aa39a-140">通常情况下, 如果 ConferenceUriId 不为 null, 则 FromUserId 或 ToUserId 将为 null。</span><span class="sxs-lookup"><span data-stu-id="aa39a-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa39a-141"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="aa39a-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="aa39a-142">datetime</span><span class="sxs-lookup"><span data-stu-id="aa39a-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="aa39a-143">外表</span><span class="sxs-lookup"><span data-stu-id="aa39a-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="aa39a-144">与<strong>SessionIdSeq</strong>结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="aa39a-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="aa39a-145">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="aa39a-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa39a-146"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="aa39a-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="aa39a-147">int</span><span class="sxs-lookup"><span data-stu-id="aa39a-147">int</span></span></p></td>
<td><p><span data-ttu-id="aa39a-148">外表</span><span class="sxs-lookup"><span data-stu-id="aa39a-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="aa39a-149">标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="aa39a-149">ID number to identify the session.</span></span> <span data-ttu-id="aa39a-150">与<strong>SessionIdTime</strong>结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="aa39a-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="aa39a-151">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="aa39a-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa39a-152"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="aa39a-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="aa39a-153">int</span><span class="sxs-lookup"><span data-stu-id="aa39a-153">int</span></span></p></td>
<td><p><span data-ttu-id="aa39a-154">外表</span><span class="sxs-lookup"><span data-stu-id="aa39a-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="aa39a-155">发送错误报告的服务器 (如果正在从服务器组件发送报表)。</span><span class="sxs-lookup"><span data-stu-id="aa39a-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="aa39a-156">有关详细信息, 请参阅<a href="lync-server-2013-servers-table.md">Lync Server 2013 中</a>的 "服务器" 表。</span><span class="sxs-lookup"><span data-stu-id="aa39a-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="aa39a-157">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="aa39a-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa39a-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="aa39a-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="aa39a-159">int</span><span class="sxs-lookup"><span data-stu-id="aa39a-159">int</span></span></p></td>
<td><p><span data-ttu-id="aa39a-160">外表</span><span class="sxs-lookup"><span data-stu-id="aa39a-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="aa39a-161">发送错误报告的服务器 (如果正在从服务器组件发送报表)。</span><span class="sxs-lookup"><span data-stu-id="aa39a-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="aa39a-162">有关详细信息, 请参阅<a href="lync-server-2013-application-table.md">Lync Server 2013 中的应用程序表</a>。</span><span class="sxs-lookup"><span data-stu-id="aa39a-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="aa39a-163">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="aa39a-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa39a-164"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="aa39a-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="aa39a-165">图像</span><span class="sxs-lookup"><span data-stu-id="aa39a-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="aa39a-166">有关错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="aa39a-166">More information about the error.</span></span></p>
<p><span data-ttu-id="aa39a-167">可以使用以下语法将此数据转换为文本格式:</span><span class="sxs-lookup"><span data-stu-id="aa39a-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa39a-168"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="aa39a-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="aa39a-169">int</span><span class="sxs-lookup"><span data-stu-id="aa39a-169">int</span></span></p></td>
<td><p><span data-ttu-id="aa39a-170">外表</span><span class="sxs-lookup"><span data-stu-id="aa39a-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="aa39a-171">发送错误报告的终结点的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="aa39a-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="aa39a-172">有关详细信息, 请参阅<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a>。</span><span class="sxs-lookup"><span data-stu-id="aa39a-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa39a-173"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="aa39a-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="aa39a-174">bit</span><span class="sxs-lookup"><span data-stu-id="aa39a-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aa39a-175">由前端服务器上运行的 CDR 代理捕获的错误报告, 或由客户端发送的错误报告。</span><span class="sxs-lookup"><span data-stu-id="aa39a-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa39a-176"><strong>旗</strong></span><span class="sxs-lookup"><span data-stu-id="aa39a-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="aa39a-177">smallint</span><span class="sxs-lookup"><span data-stu-id="aa39a-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aa39a-178">保留以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="aa39a-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa39a-179"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="aa39a-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="aa39a-180">标识符</span><span class="sxs-lookup"><span data-stu-id="aa39a-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aa39a-181">关联会议中涉及的不同组件的加入时间信息的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="aa39a-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="aa39a-182">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="aa39a-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa39a-183"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="aa39a-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="aa39a-184">int</span><span class="sxs-lookup"><span data-stu-id="aa39a-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="aa39a-185">特定组件加入会议所需的时间 (以毫秒为单位)。</span><span class="sxs-lookup"><span data-stu-id="aa39a-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="aa39a-186">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="aa39a-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="aa39a-187"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="aa39a-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="aa39a-188">int</span><span class="sxs-lookup"><span data-stu-id="aa39a-188">int</span></span></p></td>
<td><p><span data-ttu-id="aa39a-189">外表</span><span class="sxs-lookup"><span data-stu-id="aa39a-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="aa39a-190">表示生成错误报告的服务器的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="aa39a-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="aa39a-191"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="aa39a-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="aa39a-192">int</span><span class="sxs-lookup"><span data-stu-id="aa39a-192">int</span></span></p></td>
<td><p><span data-ttu-id="aa39a-193">外表</span><span class="sxs-lookup"><span data-stu-id="aa39a-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="aa39a-194">表示生成错误报告的池的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="aa39a-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

