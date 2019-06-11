---
title: 'Lync Server 2013: ErrorReport 视图'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ErrorReport view
ms:assetid: ca873f7e-b18b-4eaf-8db0-5f9d5a9b60a1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721887(v=OCS.15)
ms:contentKeyID: 49733821
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b50a2615fe83ed481d9642ac6895120f20b9fd0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830209"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="2ded5-102">Lync Server 2013 中的 ErrorReport 视图</span><span class="sxs-lookup"><span data-stu-id="2ded5-102">ErrorReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2ded5-103">_**主题上次修改时间:** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="2ded5-103">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="2ded5-104">ErrorReport 视图存储有关报告的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="2ded5-104">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="2ded5-105">每条记录是一个错误发生。</span><span class="sxs-lookup"><span data-stu-id="2ded5-105">Each record is one error occurrence.</span></span> <span data-ttu-id="2ded5-106">这些错误由前端服务器上运行的 CDR 代理或从客户端发送的 CDR 捕获。</span><span class="sxs-lookup"><span data-stu-id="2ded5-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="2ded5-107">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="2ded5-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2ded5-108">列</span><span class="sxs-lookup"><span data-stu-id="2ded5-108">Column</span></span></th>
<th><span data-ttu-id="2ded5-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="2ded5-109">Data Type</span></span></th>
<th><span data-ttu-id="2ded5-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="2ded5-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2ded5-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-112">datetime</span><span class="sxs-lookup"><span data-stu-id="2ded5-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="2ded5-113">出现错误的时间。</span><span class="sxs-lookup"><span data-stu-id="2ded5-113">Time of error occurred.</span></span> <span data-ttu-id="2ded5-114">与 ErrorReportSeq 结合使用以唯一标识错误。</span><span class="sxs-lookup"><span data-stu-id="2ded5-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ded5-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-116">int</span><span class="sxs-lookup"><span data-stu-id="2ded5-116">int</span></span></p></td>
<td><p><span data-ttu-id="2ded5-117">标识错误的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="2ded5-117">ID number to identify the error.</span></span> <span data-ttu-id="2ded5-118">与 ErrorTime 结合使用以唯一标识错误。</span><span class="sxs-lookup"><span data-stu-id="2ded5-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ded5-119"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-119"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-120">int</span><span class="sxs-lookup"><span data-stu-id="2ded5-120">int</span></span></p></td>
<td><p><span data-ttu-id="2ded5-121">错误报告的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="2ded5-121">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ded5-122"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-122"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2ded5-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2ded5-124">发出错误的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="2ded5-124">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ded5-125"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-125"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ded5-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2ded5-127">发出错误的用户的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="2ded5-127">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="2ded5-128">有关详细信息, 请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="2ded5-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ded5-129"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-129"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ded5-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2ded5-131">发出错误的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="2ded5-131">Tenant of the user who originated the error.</span></span> <span data-ttu-id="2ded5-132">有关详细信息, 请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="2ded5-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ded5-133"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-133"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-134">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2ded5-134">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2ded5-135">错误报告目标用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="2ded5-135">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ded5-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ded5-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2ded5-138">错误报告目标用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="2ded5-138">Type of URI of the user who target of the error report.</span></span> <span data-ttu-id="2ded5-139">有关详细信息, 请参阅 UriTypes 表。</span><span class="sxs-lookup"><span data-stu-id="2ded5-139">See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ded5-140"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-140"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-141">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ded5-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2ded5-142">错误报告面向的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="2ded5-142">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="2ded5-143">有关详细信息, 请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="2ded5-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ded5-144"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-144"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-145">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="2ded5-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="2ded5-146">错误报告目标的会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="2ded5-146">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ded5-147"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-147"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-148">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ded5-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2ded5-149">错误报告目标的会议的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="2ded5-149">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="2ded5-150">有关详细信息, 请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="2ded5-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ded5-151"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-151"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-152">datetime</span><span class="sxs-lookup"><span data-stu-id="2ded5-152">datetime</span></span></p></td>
<td><p><span data-ttu-id="2ded5-153">发出错误报告的会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="2ded5-153">Time of session request that originated the error report.</span></span> <span data-ttu-id="2ded5-154">与 SessionIdSeq 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="2ded5-154">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="2ded5-155">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="2ded5-155">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ded5-156"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-156"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-157">int</span><span class="sxs-lookup"><span data-stu-id="2ded5-157">int</span></span></p></td>
<td><p><span data-ttu-id="2ded5-158">标识发出错误报告的会话请求的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="2ded5-158">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="2ded5-159">与 SessionIdTime 结合使用以唯一标识会话。</span><span class="sxs-lookup"><span data-stu-id="2ded5-159">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="2ded5-160">有关详细信息, 请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="2ded5-160">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ded5-161"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-161"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-162">varstring (775)</span><span class="sxs-lookup"><span data-stu-id="2ded5-162">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="2ded5-163">发出错误的会话的 SIP 对话框 ID。</span><span class="sxs-lookup"><span data-stu-id="2ded5-163">SIP dialog ID of session that originated the error.</span></span> <span data-ttu-id="2ded5-164">格式为:</span><span class="sxs-lookup"><span data-stu-id="2ded5-164">The format is:</span></span></p>
<p><span data-ttu-id="2ded5-165">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="2ded5-165">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="2ded5-166">可以使用以下语法将此数据转换为文本格式:</span><span class="sxs-lookup"><span data-stu-id="2ded5-166">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="2ded5-167">cast (cast (ExternalId 为 varbinary (max)) 作为 varchar (max))</span><span class="sxs-lookup"><span data-stu-id="2ded5-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ded5-168"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-168"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-169">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ded5-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2ded5-170">发出错误的用户使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="2ded5-170">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ded5-171"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-171"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-172">int</span><span class="sxs-lookup"><span data-stu-id="2ded5-172">int</span></span></p></td>
<td><p><span data-ttu-id="2ded5-173">发出错误的用户所使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="2ded5-173">Client used by the user who originated the error.</span></span> <span data-ttu-id="2ded5-174">有关详细信息, 请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="2ded5-174">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ded5-175"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-175"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-176">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="2ded5-176">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="2ded5-177">发出错误的用户所使用的客户端类别的名称。</span><span class="sxs-lookup"><span data-stu-id="2ded5-177">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ded5-178"><strong>来源</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-178"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-179">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ded5-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2ded5-180">产生错误的服务器的名称 (如果报表是从服务器组件发送的)。</span><span class="sxs-lookup"><span data-stu-id="2ded5-180">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ded5-181"><strong>应用程序</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-181"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-182">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ded5-182">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2ded5-183">发出错误的应用程序的名称 (如果报表是从服务器组件发送的)。</span><span class="sxs-lookup"><span data-stu-id="2ded5-183">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ded5-184"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-184"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-185">int</span><span class="sxs-lookup"><span data-stu-id="2ded5-185">int</span></span></p></td>
<td><p><span data-ttu-id="2ded5-186">SIP 回复代码发送到包含错误报告的 SIP 邮件的会话。</span><span class="sxs-lookup"><span data-stu-id="2ded5-186">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ded5-187"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-187"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-188">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="2ded5-188">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="2ded5-189">失败的请求类型。</span><span class="sxs-lookup"><span data-stu-id="2ded5-189">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ded5-190"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-190"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-191">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="2ded5-191">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="2ded5-192">失败的请求的内容类型。</span><span class="sxs-lookup"><span data-stu-id="2ded5-192">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ded5-193"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-193"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2ded5-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="2ded5-195">会话类型。</span><span class="sxs-lookup"><span data-stu-id="2ded5-195">Type of session.</span></span> <span data-ttu-id="2ded5-196">有关详细信息, 请参阅<a href="lync-server-2013-calltype-table.md">Lync Server 2013 中的 CallType 表</a>。</span><span class="sxs-lookup"><span data-stu-id="2ded5-196">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ded5-197"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-197"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-198">标识符</span><span class="sxs-lookup"><span data-stu-id="2ded5-198">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="2ded5-199">关联会议中涉及的不同组件的加入时间信息的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="2ded5-199">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ded5-200"><strong>SetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-200"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-201">int</span><span class="sxs-lookup"><span data-stu-id="2ded5-201">int</span></span></p></td>
<td><p><span data-ttu-id="2ded5-202">特定组件加入会议所需的时间 (以毫秒为单位)。</span><span class="sxs-lookup"><span data-stu-id="2ded5-202">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ded5-203"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-203"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-204">bit</span><span class="sxs-lookup"><span data-stu-id="2ded5-204">bit</span></span></p></td>
<td><p><span data-ttu-id="2ded5-205">指示错误报告是由前端服务器上运行的 CDR 代理捕获的还是由客户端发送的。</span><span class="sxs-lookup"><span data-stu-id="2ded5-205">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ded5-206"><strong>旗</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-206"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-207">smallint</span><span class="sxs-lookup"><span data-stu-id="2ded5-207">smallint</span></span></p></td>
<td><p><span data-ttu-id="2ded5-208">保留以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="2ded5-208">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ded5-209"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-209"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-210">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="2ded5-210">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="2ded5-211">有关错误的其他信息。</span><span class="sxs-lookup"><span data-stu-id="2ded5-211">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2ded5-212"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-212"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-213">nvarchar</span><span class="sxs-lookup"><span data-stu-id="2ded5-213">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="2ded5-214">提交报表的前端服务器的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="2ded5-214">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2ded5-215"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="2ded5-215"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="2ded5-216">nvarchar</span><span class="sxs-lookup"><span data-stu-id="2ded5-216">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="2ded5-217">包含提交报表的前端服务器的池的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="2ded5-217">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

