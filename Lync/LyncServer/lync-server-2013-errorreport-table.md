---
title: Lync Server 2013： ErrorReport 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport table
ms:assetid: ae0287b4-e8ca-4f8c-84ef-502897dcaa2a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412826(v=OCS.15)
ms:contentKeyID: 48185129
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6c2a0b85e905bc7e00488c667a242965e169872b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137351"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="4b850-102">Lync Server 2013 中的 ErrorReport 表</span><span class="sxs-lookup"><span data-stu-id="4b850-102">ErrorReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b850-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="4b850-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="4b850-104">ErrorReport 表存储有关已发生的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="4b850-104">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="4b850-105">每条记录代表发生一次错误。</span><span class="sxs-lookup"><span data-stu-id="4b850-105">Each record is one error occurrence.</span></span> <span data-ttu-id="4b850-106">错误由在前端服务器上运行的 CDR 代理捕获或发送自客户端。</span><span class="sxs-lookup"><span data-stu-id="4b850-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4b850-107">列</span><span class="sxs-lookup"><span data-stu-id="4b850-107">Column</span></span></th>
<th><span data-ttu-id="4b850-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="4b850-108">Data Type</span></span></th>
<th><span data-ttu-id="4b850-109">键/索引</span><span class="sxs-lookup"><span data-stu-id="4b850-109">Key/Index</span></span></th>
<th><span data-ttu-id="4b850-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="4b850-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4b850-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="4b850-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4b850-112">datetime</span><span class="sxs-lookup"><span data-stu-id="4b850-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="4b850-113">主</span><span class="sxs-lookup"><span data-stu-id="4b850-113">Primary</span></span></p></td>
<td><p><span data-ttu-id="4b850-114">错误发生的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="4b850-114">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b850-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4b850-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4b850-116">int</span><span class="sxs-lookup"><span data-stu-id="4b850-116">int</span></span></p></td>
<td><p><span data-ttu-id="4b850-117">主</span><span class="sxs-lookup"><span data-stu-id="4b850-117">Primary</span></span></p></td>
<td><p><span data-ttu-id="4b850-118">标识错误报告的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="4b850-118">ID number to identify the error report.</span></span> <span data-ttu-id="4b850-119">与<strong>ErrorTime</strong>结合使用，以唯一标识错误报告。</span><span class="sxs-lookup"><span data-stu-id="4b850-119">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b850-120"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="4b850-120"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="4b850-121">int</span><span class="sxs-lookup"><span data-stu-id="4b850-121">int</span></span></p></td>
<td><p><span data-ttu-id="4b850-122">对外</span><span class="sxs-lookup"><span data-stu-id="4b850-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4b850-123">错误类型的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="4b850-123">Unique ID of the error type.</span></span> <span data-ttu-id="4b850-124">有关详细信息，请参阅<a href="lync-server-2013-errordef-table.md">Lync Server 2013 中的 ErrorDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="4b850-124">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b850-125"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="4b850-125"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="4b850-126">int</span><span class="sxs-lookup"><span data-stu-id="4b850-126">int</span></span></p></td>
<td><p><span data-ttu-id="4b850-127">对外</span><span class="sxs-lookup"><span data-stu-id="4b850-127">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4b850-128">发出导致错误的请求的用户。</span><span class="sxs-lookup"><span data-stu-id="4b850-128">User who originated the request that caused the error.</span></span> <span data-ttu-id="4b850-129">有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</span><span class="sxs-lookup"><span data-stu-id="4b850-129">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b850-130"><strong>ToUserId</strong></span><span class="sxs-lookup"><span data-stu-id="4b850-130"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="4b850-131">int</span><span class="sxs-lookup"><span data-stu-id="4b850-131">int</span></span></p></td>
<td><p><span data-ttu-id="4b850-132">对外</span><span class="sxs-lookup"><span data-stu-id="4b850-132">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4b850-133">导致错误的请求的目标用户。</span><span class="sxs-lookup"><span data-stu-id="4b850-133">Destination user for the request that caused the error.</span></span> <span data-ttu-id="4b850-134">有关详细信息，请参阅<a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a>。</span><span class="sxs-lookup"><span data-stu-id="4b850-134">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b850-135"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="4b850-135"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="4b850-136">int</span><span class="sxs-lookup"><span data-stu-id="4b850-136">int</span></span></p></td>
<td><p><span data-ttu-id="4b850-137">对外</span><span class="sxs-lookup"><span data-stu-id="4b850-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4b850-138">与错误相关的会议 URI。</span><span class="sxs-lookup"><span data-stu-id="4b850-138">Conference URI related to the error.</span></span> <span data-ttu-id="4b850-139">有关详细信息，请参阅<a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a>。</span><span class="sxs-lookup"><span data-stu-id="4b850-139">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="4b850-140">通常情况下，如果 ConferenceUriId 不为 null，则 FromUserId 或 ToUserId 将为 null。</span><span class="sxs-lookup"><span data-stu-id="4b850-140">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b850-141"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="4b850-141"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4b850-142">datetime</span><span class="sxs-lookup"><span data-stu-id="4b850-142">datetime</span></span></p></td>
<td><p><span data-ttu-id="4b850-143">对外</span><span class="sxs-lookup"><span data-stu-id="4b850-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4b850-144">与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="4b850-144">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="4b850-145">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="4b850-145">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b850-146"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="4b850-146"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="4b850-147">int</span><span class="sxs-lookup"><span data-stu-id="4b850-147">int</span></span></p></td>
<td><p><span data-ttu-id="4b850-148">对外</span><span class="sxs-lookup"><span data-stu-id="4b850-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4b850-149">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="4b850-149">ID number to identify the session.</span></span> <span data-ttu-id="4b850-150">与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="4b850-150">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="4b850-151">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="4b850-151">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b850-152"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="4b850-152"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="4b850-153">int</span><span class="sxs-lookup"><span data-stu-id="4b850-153">int</span></span></p></td>
<td><p><span data-ttu-id="4b850-154">对外</span><span class="sxs-lookup"><span data-stu-id="4b850-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4b850-155">发送错误报告的服务器（如果正在从服务器组件发送报告）。</span><span class="sxs-lookup"><span data-stu-id="4b850-155">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="4b850-156">有关详细信息，请参阅<a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 表</a>。</span><span class="sxs-lookup"><span data-stu-id="4b850-156">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="4b850-157">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="4b850-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b850-158"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="4b850-158"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="4b850-159">int</span><span class="sxs-lookup"><span data-stu-id="4b850-159">int</span></span></p></td>
<td><p><span data-ttu-id="4b850-160">对外</span><span class="sxs-lookup"><span data-stu-id="4b850-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4b850-161">发送错误报告的服务器（如果正在从服务器组件发送报告）。</span><span class="sxs-lookup"><span data-stu-id="4b850-161">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="4b850-162">有关详细信息，请参阅<a href="lync-server-2013-application-table.md">Lync Server 2013 中的应用程序表</a>。</span><span class="sxs-lookup"><span data-stu-id="4b850-162">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="4b850-163">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="4b850-163">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b850-164"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="4b850-164"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="4b850-165">image</span><span class="sxs-lookup"><span data-stu-id="4b850-165">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="4b850-166">有关错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="4b850-166">More information about the error.</span></span></p>
<p><span data-ttu-id="4b850-167">可以使用以下语法将此数据转换为文本格式：</span><span class="sxs-lookup"><span data-stu-id="4b850-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b850-168"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="4b850-168"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="4b850-169">int</span><span class="sxs-lookup"><span data-stu-id="4b850-169">int</span></span></p></td>
<td><p><span data-ttu-id="4b850-170">对外</span><span class="sxs-lookup"><span data-stu-id="4b850-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4b850-171">发送错误报告的终结点的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="4b850-171">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="4b850-172">有关详细信息，请参阅<a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a>。</span><span class="sxs-lookup"><span data-stu-id="4b850-172">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b850-173"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="4b850-173"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="4b850-174">位</span><span class="sxs-lookup"><span data-stu-id="4b850-174">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4b850-175">是由在前端服务器上运行的 CDR 代理捕获的或由客户端发送的错误报告。</span><span class="sxs-lookup"><span data-stu-id="4b850-175">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b850-176"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="4b850-176"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="4b850-177">smallint</span><span class="sxs-lookup"><span data-stu-id="4b850-177">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4b850-178">保留以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="4b850-178">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b850-179"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="4b850-179"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="4b850-180">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="4b850-180">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4b850-181">关联会议中所涉及不同组件的加入时间信息的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="4b850-181">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="4b850-182">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="4b850-182">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b850-183"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="4b850-183"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="4b850-184">int</span><span class="sxs-lookup"><span data-stu-id="4b850-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="4b850-185">特定组件加入会议所需的时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="4b850-185">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="4b850-186">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="4b850-186">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4b850-187"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="4b850-187"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="4b850-188">int</span><span class="sxs-lookup"><span data-stu-id="4b850-188">int</span></span></p></td>
<td><p><span data-ttu-id="4b850-189">对外</span><span class="sxs-lookup"><span data-stu-id="4b850-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4b850-190">表示生成错误报告的服务器的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="4b850-190">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4b850-191"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="4b850-191"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="4b850-192">int</span><span class="sxs-lookup"><span data-stu-id="4b850-192">int</span></span></p></td>
<td><p><span data-ttu-id="4b850-193">对外</span><span class="sxs-lookup"><span data-stu-id="4b850-193">Foreign</span></span></p></td>
<td><p><span data-ttu-id="4b850-194">表示生成错误报告的池的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="4b850-194">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

