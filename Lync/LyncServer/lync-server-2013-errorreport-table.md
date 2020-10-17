---
title: Lync Server 2013： ErrorReport 表
description: Lync Server 2013： ErrorReport 表。
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
ms.openlocfilehash: 9c1cc65c396c16dc137255438f7ef7c32b2d0b78
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572008"
---
# <a name="errorreport-table-in-lync-server-2013"></a><span data-ttu-id="1ebcd-103">Lync Server 2013 中的 ErrorReport 表</span><span class="sxs-lookup"><span data-stu-id="1ebcd-103">ErrorReport table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ebcd-104">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="1ebcd-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="1ebcd-105">ErrorReport 表存储有关已发生的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-105">The ErrorReport table stores information about errors that have occurred.</span></span> <span data-ttu-id="1ebcd-106">每条记录代表发生一次错误。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-106">Each record is one error occurrence.</span></span> <span data-ttu-id="1ebcd-107">错误由在前端服务器上运行的 CDR 代理捕获或发送自客户端。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-107">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1ebcd-108">列</span><span class="sxs-lookup"><span data-stu-id="1ebcd-108">Column</span></span></th>
<th><span data-ttu-id="1ebcd-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="1ebcd-109">Data Type</span></span></th>
<th><span data-ttu-id="1ebcd-110">键/索引</span><span class="sxs-lookup"><span data-stu-id="1ebcd-110">Key/Index</span></span></th>
<th><span data-ttu-id="1ebcd-111">详细信息</span><span class="sxs-lookup"><span data-stu-id="1ebcd-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1ebcd-112"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="1ebcd-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1ebcd-113">datetime</span><span class="sxs-lookup"><span data-stu-id="1ebcd-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-114">主</span><span class="sxs-lookup"><span data-stu-id="1ebcd-114">Primary</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-115">错误发生的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-115">Date and time the error occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ebcd-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1ebcd-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1ebcd-117">int</span><span class="sxs-lookup"><span data-stu-id="1ebcd-117">int</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-118">主</span><span class="sxs-lookup"><span data-stu-id="1ebcd-118">Primary</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-119">标识错误报告的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-119">ID number to identify the error report.</span></span> <span data-ttu-id="1ebcd-120">与 <strong>ErrorTime</strong> 结合使用，以唯一标识错误报告。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-120">Used in conjunction with <strong>ErrorTime</strong> to uniquely identify an error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ebcd-121"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="1ebcd-121"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ebcd-122">int</span><span class="sxs-lookup"><span data-stu-id="1ebcd-122">int</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-123">对外</span><span class="sxs-lookup"><span data-stu-id="1ebcd-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-124">错误类型的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-124">Unique ID of the error type.</span></span> <span data-ttu-id="1ebcd-125">有关详细信息，请参阅 <a href="lync-server-2013-errordef-table.md">Lync Server 2013 中的 ErrorDef 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-125">See the <a href="lync-server-2013-errordef-table.md">ErrorDef table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ebcd-126"><strong>FromUserId</strong></span><span class="sxs-lookup"><span data-stu-id="1ebcd-126"><strong>FromUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ebcd-127">int</span><span class="sxs-lookup"><span data-stu-id="1ebcd-127">int</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-128">对外</span><span class="sxs-lookup"><span data-stu-id="1ebcd-128">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-129">发出导致错误的请求的用户。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-129">User who originated the request that caused the error.</span></span> <span data-ttu-id="1ebcd-130">有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-130">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ebcd-131"><strong>ToUserId</strong></span><span class="sxs-lookup"><span data-stu-id="1ebcd-131"><strong>ToUserId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ebcd-132">int</span><span class="sxs-lookup"><span data-stu-id="1ebcd-132">int</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-133">对外</span><span class="sxs-lookup"><span data-stu-id="1ebcd-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-134">导致错误的请求的目标用户。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-134">Destination user for the request that caused the error.</span></span> <span data-ttu-id="1ebcd-135">有关详细信息，请参阅 <a href="lync-server-2013-users-table.md">Lync Server 2013 中的 Users 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-135">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ebcd-136"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="1ebcd-136"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ebcd-137">int</span><span class="sxs-lookup"><span data-stu-id="1ebcd-137">int</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-138">对外</span><span class="sxs-lookup"><span data-stu-id="1ebcd-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-139">与错误相关的会议 URI。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-139">Conference URI related to the error.</span></span> <span data-ttu-id="1ebcd-140">有关详细信息，请参阅 <a href="lync-server-2013-conferenceuris-table.md">Lync Server 2013 中的 ConferenceUris 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-140">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="1ebcd-141">通常情况下，如果 ConferenceUriId 不为 null，则 FromUserId 或 ToUserId 将为 null。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-141">Typically, if ConferenceUriId is not null, then either FromUserId or ToUserId will be null.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ebcd-142"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="1ebcd-142"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1ebcd-143">datetime</span><span class="sxs-lookup"><span data-stu-id="1ebcd-143">datetime</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-144">对外</span><span class="sxs-lookup"><span data-stu-id="1ebcd-144">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-145">与 <strong>SessionIdSeq</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-145">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="1ebcd-146">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-146">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ebcd-147"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1ebcd-147"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1ebcd-148">int</span><span class="sxs-lookup"><span data-stu-id="1ebcd-148">int</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-149">对外</span><span class="sxs-lookup"><span data-stu-id="1ebcd-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-150">用于标识会话的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-150">ID number to identify the session.</span></span> <span data-ttu-id="1ebcd-151">与 <strong>SessionIdTime</strong> 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-151">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="1ebcd-152">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-152">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ebcd-153"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="1ebcd-153"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ebcd-154">int</span><span class="sxs-lookup"><span data-stu-id="1ebcd-154">int</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-155">对外</span><span class="sxs-lookup"><span data-stu-id="1ebcd-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-156">发送错误报告的服务器 (如果正在从服务器组件) 发送报告。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-156">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="1ebcd-157">有关详细信息，请参阅 <a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-157">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="1ebcd-158">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-158">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ebcd-159"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="1ebcd-159"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ebcd-160">int</span><span class="sxs-lookup"><span data-stu-id="1ebcd-160">int</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-161">对外</span><span class="sxs-lookup"><span data-stu-id="1ebcd-161">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-162">发送错误报告的服务器 (如果正在从服务器组件) 发送报告。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-162">Server that sent the error report (if the report is being sent from a server component).</span></span> <span data-ttu-id="1ebcd-163">有关详细信息，请参阅 <a href="lync-server-2013-application-table.md">Lync Server 2013 中的应用程序表</a> 。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-163">See the <a href="lync-server-2013-application-table.md">Application table in Lync Server 2013</a> for more information.</span></span></p>
<p><span data-ttu-id="1ebcd-164">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-164">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ebcd-165"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="1ebcd-165"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="1ebcd-166">image</span><span class="sxs-lookup"><span data-stu-id="1ebcd-166">image</span></span></p></td>
<td><p> </p></td>
<td><p><span data-ttu-id="1ebcd-167">有关错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-167">More information about the error.</span></span></p>
<p><span data-ttu-id="1ebcd-168">可以使用以下语法将此数据转换为文本格式：</span><span class="sxs-lookup"><span data-stu-id="1ebcd-168">This data can be converted to text format by using this syntax:</span></span></p>
<p><code>cast(cast(Detail as varbinary(max)) as varchar(max)) </code></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ebcd-169"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="1ebcd-169"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ebcd-170">int</span><span class="sxs-lookup"><span data-stu-id="1ebcd-170">int</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-171">对外</span><span class="sxs-lookup"><span data-stu-id="1ebcd-171">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-172">发送错误报告的终结点的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-172">The client version of endpoint that sends the error report.</span></span> <span data-ttu-id="1ebcd-173">有关详细信息，请参阅 <a href="lync-server-2013-clientversions-table.md">Lync Server 2013 中的 ClientVersions 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-173">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ebcd-174"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="1ebcd-174"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="1ebcd-175">位</span><span class="sxs-lookup"><span data-stu-id="1ebcd-175">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ebcd-176">是由在前端服务器上运行的 CDR 代理捕获的或由客户端发送的错误报告。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-176">Is the error report captured by the CDR agent running on the front-end server, or sent by the client.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ebcd-177"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="1ebcd-177"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="1ebcd-178">smallint</span><span class="sxs-lookup"><span data-stu-id="1ebcd-178">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ebcd-179">保留以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-179">Reserved for future use.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ebcd-180"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="1ebcd-180"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ebcd-181">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="1ebcd-181">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ebcd-182">关联会议中所涉及不同组件的加入时间信息的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-182">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="1ebcd-183">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-183">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ebcd-184"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="1ebcd-184"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1ebcd-185">int</span><span class="sxs-lookup"><span data-stu-id="1ebcd-185">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="1ebcd-186">特定组件加入会议所需的时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-186">Time (in milliseconds) required for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="1ebcd-187">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-187">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1ebcd-188"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="1ebcd-188"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ebcd-189">int</span><span class="sxs-lookup"><span data-stu-id="1ebcd-189">int</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-190">对外</span><span class="sxs-lookup"><span data-stu-id="1ebcd-190">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-191">表示生成错误报告的服务器的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-191">Represents the fully qualified domain name of the server that generated the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1ebcd-192"><strong>PoolId</strong></span><span class="sxs-lookup"><span data-stu-id="1ebcd-192"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="1ebcd-193">int</span><span class="sxs-lookup"><span data-stu-id="1ebcd-193">int</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-194">对外</span><span class="sxs-lookup"><span data-stu-id="1ebcd-194">Foreign</span></span></p></td>
<td><p><span data-ttu-id="1ebcd-195">表示生成错误报告的池的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="1ebcd-195">Represents the fully qualified domain name of the pool where the error report was generated.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

