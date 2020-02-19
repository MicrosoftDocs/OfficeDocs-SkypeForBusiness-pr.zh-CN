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
ms.openlocfilehash: a1430ab1cc00b29ed834ff078cbe70a1265a2162
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137341"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="75f42-102">Lync Server 2013 中的 ErrorReport 视图</span><span class="sxs-lookup"><span data-stu-id="75f42-102">ErrorReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75f42-103">_**上次修改的主题：** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="75f42-103">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="75f42-104">ErrorReport 视图存储有关已报告的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="75f42-104">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="75f42-105">每条记录代表发生一次错误。</span><span class="sxs-lookup"><span data-stu-id="75f42-105">Each record is one error occurrence.</span></span> <span data-ttu-id="75f42-106">错误由在前端服务器上运行的 CDR 代理捕获或发送自客户端。</span><span class="sxs-lookup"><span data-stu-id="75f42-106">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="75f42-107">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="75f42-107">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="75f42-108">列</span><span class="sxs-lookup"><span data-stu-id="75f42-108">Column</span></span></th>
<th><span data-ttu-id="75f42-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="75f42-109">Data Type</span></span></th>
<th><span data-ttu-id="75f42-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="75f42-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="75f42-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-112">datetime</span><span class="sxs-lookup"><span data-stu-id="75f42-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="75f42-p102">发生错误的时间。与 ErrorReportSeq 结合使用来唯一地标识错误。</span><span class="sxs-lookup"><span data-stu-id="75f42-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75f42-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-116">int</span><span class="sxs-lookup"><span data-stu-id="75f42-116">int</span></span></p></td>
<td><p><span data-ttu-id="75f42-p103">用于标识错误的 ID 号。与 ErrorTime 结合使用来唯一地标识错误。</span><span class="sxs-lookup"><span data-stu-id="75f42-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75f42-119"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-119"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-120">int</span><span class="sxs-lookup"><span data-stu-id="75f42-120">int</span></span></p></td>
<td><p><span data-ttu-id="75f42-121">错误报告的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="75f42-121">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75f42-122"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-122"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-123">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="75f42-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="75f42-124">导致出错的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="75f42-124">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75f42-125"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-125"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-126">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="75f42-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="75f42-127">导致出错的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="75f42-127">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="75f42-128">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="75f42-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75f42-129"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-129"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-130">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="75f42-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="75f42-131">导致出错的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="75f42-131">Tenant of the user who originated the error.</span></span> <span data-ttu-id="75f42-132">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="75f42-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75f42-133"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-133"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-134">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="75f42-134">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="75f42-135">成为错误报告目标的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="75f42-135">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75f42-136"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-136"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-137">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="75f42-137">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="75f42-p106">成为错误报告目标的用户的 URI 类型。有关详细信息，请参阅 UriTypes 表。</span><span class="sxs-lookup"><span data-stu-id="75f42-p106">Type of URI of the user who target of the error report. See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75f42-140"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-140"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-141">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="75f42-141">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="75f42-142">成为错误报告目标的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="75f42-142">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="75f42-143">有关详细信息，请参阅<a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a>。</span><span class="sxs-lookup"><span data-stu-id="75f42-143">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75f42-144"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-144"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-145">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="75f42-145">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="75f42-146">成为错误报告目标的会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="75f42-146">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75f42-147"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-147"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-148">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="75f42-148">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="75f42-149">成为错误报告目标的会议的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="75f42-149">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="75f42-150">有关详细信息，请参阅<a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a>。</span><span class="sxs-lookup"><span data-stu-id="75f42-150">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75f42-151"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-151"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-152">datetime</span><span class="sxs-lookup"><span data-stu-id="75f42-152">datetime</span></span></p></td>
<td><p><span data-ttu-id="75f42-153">导致发出错误报告的会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="75f42-153">Time of session request that originated the error report.</span></span> <span data-ttu-id="75f42-154">与 SessionIdSeq 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="75f42-154">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="75f42-155">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="75f42-155">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75f42-156"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-156"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-157">int</span><span class="sxs-lookup"><span data-stu-id="75f42-157">int</span></span></p></td>
<td><p><span data-ttu-id="75f42-158">用于标识导致发出错误报告的会话请求的 ID 编号。</span><span class="sxs-lookup"><span data-stu-id="75f42-158">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="75f42-159">与 SessionIdTime 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="75f42-159">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="75f42-160">有关详细信息，请参阅<a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a>。</span><span class="sxs-lookup"><span data-stu-id="75f42-160">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75f42-161"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-161"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-162">varstring （775）</span><span class="sxs-lookup"><span data-stu-id="75f42-162">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="75f42-p111">导致出错的会话的 SIP 对话 ID。格式为：</span><span class="sxs-lookup"><span data-stu-id="75f42-p111">SIP dialog ID of session that originated the error. The format is:</span></span></p>
<p><span data-ttu-id="75f42-165">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="75f42-165">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="75f42-166">可以使用以下语法将此数据转换为文本格式：</span><span class="sxs-lookup"><span data-stu-id="75f42-166">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="75f42-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="75f42-167">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75f42-168"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-168"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-169">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="75f42-169">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="75f42-170">导致出错的用户所使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="75f42-170">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75f42-171"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-171"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-172">int</span><span class="sxs-lookup"><span data-stu-id="75f42-172">int</span></span></p></td>
<td><p><span data-ttu-id="75f42-173">导致出错的用户所使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="75f42-173">Client used by the user who originated the error.</span></span> <span data-ttu-id="75f42-174">有关更多详细信息，请参阅<a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a>。</span><span class="sxs-lookup"><span data-stu-id="75f42-174">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75f42-175"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-175"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-176">nvarchar （64）</span><span class="sxs-lookup"><span data-stu-id="75f42-176">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="75f42-177">导致出错的用户所使用的客户端的类别名称。</span><span class="sxs-lookup"><span data-stu-id="75f42-177">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75f42-178"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-178"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-179">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="75f42-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="75f42-180">导致出错的服务器的名称（如果报告发送自服务器组件）。</span><span class="sxs-lookup"><span data-stu-id="75f42-180">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75f42-181"><strong>应用程序</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-181"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-182">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="75f42-182">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="75f42-183">导致出错的应用程序的名称（如果报告发送自服务器组件）。</span><span class="sxs-lookup"><span data-stu-id="75f42-183">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75f42-184"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-184"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-185">int</span><span class="sxs-lookup"><span data-stu-id="75f42-185">int</span></span></p></td>
<td><p><span data-ttu-id="75f42-186">包含错误报告的 SIP 消息对话的 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="75f42-186">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75f42-187"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-187"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-188">varchar （max）</span><span class="sxs-lookup"><span data-stu-id="75f42-188">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="75f42-189">失败的请求的类型。</span><span class="sxs-lookup"><span data-stu-id="75f42-189">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75f42-190"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-190"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-191">varchar （max）</span><span class="sxs-lookup"><span data-stu-id="75f42-191">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="75f42-192">失败的请求的内容类型。</span><span class="sxs-lookup"><span data-stu-id="75f42-192">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75f42-193"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-193"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-194">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="75f42-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="75f42-195">会话类型。</span><span class="sxs-lookup"><span data-stu-id="75f42-195">Type of session.</span></span> <span data-ttu-id="75f42-196">有关详细信息，请参阅<a href="lync-server-2013-calltype-table.md">Lync Server 2013 中的 CallType 表</a>。</span><span class="sxs-lookup"><span data-stu-id="75f42-196">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75f42-197"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-197"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-198">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="75f42-198">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="75f42-199">关联会议中所涉及不同组件的加入时间信息的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="75f42-199">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75f42-200"><strong>SetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-200"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-201">int</span><span class="sxs-lookup"><span data-stu-id="75f42-201">int</span></span></p></td>
<td><p><span data-ttu-id="75f42-202">特定组件加入会议所需的时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="75f42-202">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75f42-203"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-203"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-204">位</span><span class="sxs-lookup"><span data-stu-id="75f42-204">bit</span></span></p></td>
<td><p><span data-ttu-id="75f42-205">指示错误报告是由在前端服务器上运行的 CDR 代理捕获的，还是客户端发送的。</span><span class="sxs-lookup"><span data-stu-id="75f42-205">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75f42-206"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-206"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-207">smallint</span><span class="sxs-lookup"><span data-stu-id="75f42-207">smallint</span></span></p></td>
<td><p><span data-ttu-id="75f42-208">保留以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="75f42-208">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75f42-209"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-209"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-210">varchar （max）</span><span class="sxs-lookup"><span data-stu-id="75f42-210">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="75f42-211">有关错误的其他信息。</span><span class="sxs-lookup"><span data-stu-id="75f42-211">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="75f42-212"><strong>前端</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-212"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-213">nvarchar</span><span class="sxs-lookup"><span data-stu-id="75f42-213">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="75f42-214">提交报告的前端服务器的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="75f42-214">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="75f42-215"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="75f42-215"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="75f42-216">nvarchar</span><span class="sxs-lookup"><span data-stu-id="75f42-216">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="75f42-217">包含提交报告的前端服务器的池的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="75f42-217">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

