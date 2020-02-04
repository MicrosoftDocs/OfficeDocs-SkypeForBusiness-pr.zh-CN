---
title: Lync Server 2013： ErrorReport 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a72b2f12c00248095b99198182b8c71bb945bfa3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735272"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="63f46-102">Lync Server 2013 中的 ErrorReport 视图</span><span class="sxs-lookup"><span data-stu-id="63f46-102">ErrorReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="63f46-103">_**主题上次修改时间：** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="63f46-103">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="63f46-104">ErrorReport 视图存储有关报告的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="63f46-104">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="63f46-105">每条记录是一个错误发生。</span><span class="sxs-lookup"><span data-stu-id="63f46-105">Each record is one error occurrence.</span></span> <span data-ttu-id="63f46-106">这些错误由前端服务器上运行的 CDR 代理或从客户端发送的 CDR 捕获。</span><span class="sxs-lookup"><span data-stu-id="63f46-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="63f46-107">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="63f46-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="63f46-108">列</span><span class="sxs-lookup"><span data-stu-id="63f46-108">Column</span></span></th>
<th><span data-ttu-id="63f46-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="63f46-109">Data Type</span></span></th>
<th><span data-ttu-id="63f46-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="63f46-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="63f46-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-112">datetime</span><span class="sxs-lookup"><span data-stu-id="63f46-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="63f46-113">出现错误的时间。</span><span class="sxs-lookup"><span data-stu-id="63f46-113">Time of error occurred.</span></span> <span data-ttu-id="63f46-114">与 ErrorReportSeq 结合使用以唯一标识错误。</span><span class="sxs-lookup"><span data-stu-id="63f46-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63f46-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-116">int</span><span class="sxs-lookup"><span data-stu-id="63f46-116">int</span></span></p></td>
<td><p><span data-ttu-id="63f46-117">标识错误的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="63f46-117">ID number to identify the error.</span></span> <span data-ttu-id="63f46-118">与 ErrorTime 结合使用以唯一标识错误。</span><span class="sxs-lookup"><span data-stu-id="63f46-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63f46-119"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-119"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-120">int</span><span class="sxs-lookup"><span data-stu-id="63f46-120">int</span></span></p></td>
<td><p><span data-ttu-id="63f46-121">错误报告的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="63f46-121">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63f46-122"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-122"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-123">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="63f46-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="63f46-124">发出错误的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="63f46-124">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63f46-125"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-125"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63f46-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63f46-127">发出错误的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="63f46-127">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="63f46-128">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="63f46-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63f46-129"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-129"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63f46-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63f46-131">发出错误的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="63f46-131">Tenant of the user who originated the error.</span></span> <span data-ttu-id="63f46-132">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="63f46-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63f46-133"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-133"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-134">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="63f46-134">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="63f46-135">错误报告目标用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="63f46-135">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63f46-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63f46-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63f46-138">错误报告目标用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="63f46-138">Type of URI of the user who target of the error report.</span></span> <span data-ttu-id="63f46-139">有关详细信息，请参阅 UriTypes 表。</span><span class="sxs-lookup"><span data-stu-id="63f46-139">See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63f46-140"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-140"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-141">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63f46-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63f46-142">错误报告面向的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="63f46-142">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="63f46-143">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="63f46-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63f46-144"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-144"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-145">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="63f46-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="63f46-146">错误报告目标的会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="63f46-146">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63f46-147"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-147"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63f46-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63f46-149">错误报告目标的会议的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="63f46-149">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="63f46-150">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="63f46-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63f46-151"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-151"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-152">datetime</span><span class="sxs-lookup"><span data-stu-id="63f46-152">datetime</span></span></p></td>
<td><p><span data-ttu-id="63f46-153">发出错误报告的会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="63f46-153">Time of session request that originated the error report.</span></span> <span data-ttu-id="63f46-154">与 SessionIdSeq 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="63f46-154">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="63f46-155">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="63f46-155">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63f46-156"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-156"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-157">int</span><span class="sxs-lookup"><span data-stu-id="63f46-157">int</span></span></p></td>
<td><p><span data-ttu-id="63f46-158">标识发出错误报告的会话请求的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="63f46-158">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="63f46-159">与 SessionIdTime 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="63f46-159">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="63f46-160">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="63f46-160">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63f46-161"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-161"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-162">varstring （775）</span><span class="sxs-lookup"><span data-stu-id="63f46-162">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="63f46-163">发出错误的会话的 SIP 对话框 ID。</span><span class="sxs-lookup"><span data-stu-id="63f46-163">SIP dialog ID of session that originated the error.</span></span> <span data-ttu-id="63f46-164">格式为：</span><span class="sxs-lookup"><span data-stu-id="63f46-164">The format is:</span></span></p>
<p><span data-ttu-id="63f46-165">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="63f46-165">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="63f46-166">可以使用以下语法将此数据转换为文本格式：</span><span class="sxs-lookup"><span data-stu-id="63f46-166">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="63f46-167">cast （cast （ExternalId 为 varbinary （max））作为 varchar （max））</span><span class="sxs-lookup"><span data-stu-id="63f46-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63f46-168"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-168"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-169">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63f46-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63f46-170">发出错误的用户使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="63f46-170">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63f46-171"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-171"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-172">int</span><span class="sxs-lookup"><span data-stu-id="63f46-172">int</span></span></p></td>
<td><p><span data-ttu-id="63f46-173">发出错误的用户所使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="63f46-173">Client used by the user who originated the error.</span></span> <span data-ttu-id="63f46-174">有关详细信息，请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="63f46-174">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63f46-175"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-175"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-176">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="63f46-176">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="63f46-177">发出错误的用户所使用的客户端类别的名称。</span><span class="sxs-lookup"><span data-stu-id="63f46-177">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63f46-178"><strong>来源</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-178"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-179">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63f46-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63f46-180">产生错误的服务器的名称（如果报表是从服务器组件发送的）。</span><span class="sxs-lookup"><span data-stu-id="63f46-180">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63f46-181"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-181"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-182">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63f46-182">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63f46-183">发出错误的应用程序的名称（如果报表是从服务器组件发送的）。</span><span class="sxs-lookup"><span data-stu-id="63f46-183">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63f46-184"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-184"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-185">int</span><span class="sxs-lookup"><span data-stu-id="63f46-185">int</span></span></p></td>
<td><p><span data-ttu-id="63f46-186">SIP 回复代码发送到包含错误报告的 SIP 邮件的会话。</span><span class="sxs-lookup"><span data-stu-id="63f46-186">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63f46-187"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-187"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-188">varchar （max）</span><span class="sxs-lookup"><span data-stu-id="63f46-188">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="63f46-189">失败的请求类型。</span><span class="sxs-lookup"><span data-stu-id="63f46-189">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63f46-190"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-190"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-191">varchar （max）</span><span class="sxs-lookup"><span data-stu-id="63f46-191">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="63f46-192">失败的请求的内容类型。</span><span class="sxs-lookup"><span data-stu-id="63f46-192">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63f46-193"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-193"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="63f46-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="63f46-195">会话类型。</span><span class="sxs-lookup"><span data-stu-id="63f46-195">Type of session.</span></span> <span data-ttu-id="63f46-196">有关详细信息，请参阅<a href="lync-server-2013-calltype-table.md">Lync Server 2013 中的 CallType 表</a>。</span><span class="sxs-lookup"><span data-stu-id="63f46-196">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63f46-197"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-197"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-198">标识符</span><span class="sxs-lookup"><span data-stu-id="63f46-198">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="63f46-199">关联会议中涉及的不同组件的加入时间信息的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="63f46-199">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63f46-200"><strong>SetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-200"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-201">int</span><span class="sxs-lookup"><span data-stu-id="63f46-201">int</span></span></p></td>
<td><p><span data-ttu-id="63f46-202">特定组件加入会议所需的时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="63f46-202">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63f46-203"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-203"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-204">bit</span><span class="sxs-lookup"><span data-stu-id="63f46-204">bit</span></span></p></td>
<td><p><span data-ttu-id="63f46-205">指示错误报告是由前端服务器上运行的 CDR 代理捕获的还是由客户端发送的。</span><span class="sxs-lookup"><span data-stu-id="63f46-205">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63f46-206"><strong>旗</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-206"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-207">smallint</span><span class="sxs-lookup"><span data-stu-id="63f46-207">smallint</span></span></p></td>
<td><p><span data-ttu-id="63f46-208">保留以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="63f46-208">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63f46-209"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-209"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-210">varchar （max）</span><span class="sxs-lookup"><span data-stu-id="63f46-210">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="63f46-211">有关错误的其他信息。</span><span class="sxs-lookup"><span data-stu-id="63f46-211">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="63f46-212"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-212"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-213">nvarchar</span><span class="sxs-lookup"><span data-stu-id="63f46-213">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="63f46-214">提交报表的前端服务器的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="63f46-214">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="63f46-215"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="63f46-215"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="63f46-216">nvarchar</span><span class="sxs-lookup"><span data-stu-id="63f46-216">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="63f46-217">包含提交报表的前端服务器的池的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="63f46-217">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

