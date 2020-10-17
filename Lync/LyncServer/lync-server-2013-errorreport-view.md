---
title: Lync Server 2013： ErrorReport 视图
description: Lync Server 2013： ErrorReport 视图。
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
ms.openlocfilehash: 50fb0a362c71d8dfb5873157e7b1ed3d3eb680ae
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572038"
---
# <a name="errorreport-view-in-lync-server-2013"></a><span data-ttu-id="5f9fd-103">Lync Server 2013 中的 ErrorReport 视图</span><span class="sxs-lookup"><span data-stu-id="5f9fd-103">ErrorReport view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5f9fd-104">_**上次修改的主题：** 2013-01-22_</span><span class="sxs-lookup"><span data-stu-id="5f9fd-104">_**Topic Last Modified:** 2013-01-22_</span></span>

<span data-ttu-id="5f9fd-105">ErrorReport 视图存储有关已报告的错误的信息。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-105">The ErrorReport view stores information about errors reported.</span></span> <span data-ttu-id="5f9fd-106">每条记录代表发生一次错误。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-106">Each record is one error occurrence.</span></span> <span data-ttu-id="5f9fd-107">错误由在前端服务器上运行的 CDR 代理捕获或发送自客户端。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-107">The errors are captured either by the CDR agent running on the front-end server or sent from the client.</span></span> <span data-ttu-id="5f9fd-108">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-108">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5f9fd-109">列</span><span class="sxs-lookup"><span data-stu-id="5f9fd-109">Column</span></span></th>
<th><span data-ttu-id="5f9fd-110">数据类型</span><span class="sxs-lookup"><span data-stu-id="5f9fd-110">Data Type</span></span></th>
<th><span data-ttu-id="5f9fd-111">详细信息</span><span class="sxs-lookup"><span data-stu-id="5f9fd-111">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5f9fd-112"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-112"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-113">datetime</span><span class="sxs-lookup"><span data-stu-id="5f9fd-113">datetime</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-p102">发生错误的时间。与 ErrorReportSeq 结合使用来唯一地标识错误。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f9fd-116"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-116"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-117">int</span><span class="sxs-lookup"><span data-stu-id="5f9fd-117">int</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-p103">用于标识错误的 ID 号。与 ErrorTime 结合使用来唯一地标识错误。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f9fd-120"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-120"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-121">int</span><span class="sxs-lookup"><span data-stu-id="5f9fd-121">int</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-122">错误报告的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-122">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f9fd-123"><strong>FromUri</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-123"><strong>FromUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-124">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="5f9fd-124">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-125">导致出错的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-125">URI of the user who originated the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f9fd-126"><strong>FromUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-126"><strong>FromUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-127">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="5f9fd-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-128">导致出错的用户的 URI 的类型。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-128">Type of URI of the user who originated the error.</span></span> <span data-ttu-id="5f9fd-129">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f9fd-130"><strong>FromTenant</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-130"><strong>FromTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-131">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="5f9fd-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-132">导致出错的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-132">Tenant of the user who originated the error.</span></span> <span data-ttu-id="5f9fd-133">有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a> 。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-133">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f9fd-134"><strong>ToUri</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-134"><strong>ToUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-135">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="5f9fd-135">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-136">成为错误报告目标的用户的 URI。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-136">URI of the user who was the target of the error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f9fd-137"><strong>ToUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-137"><strong>ToUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-138">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="5f9fd-138">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-p106">成为错误报告目标的用户的 URI 类型。有关详细信息，请参阅 UriTypes 表。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-p106">Type of URI of the user who target of the error report. See the UriTypes Table for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f9fd-141"><strong>ToTenant</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-141"><strong>ToTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-142">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="5f9fd-142">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-143">成为错误报告目标的用户的租户。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-143">Tenant of the user who target of the error report.</span></span> <span data-ttu-id="5f9fd-144">有关详细信息，请参阅 <a href="lync-server-2013-tenants-table.md">Lync Server 2013 中的租户表</a> 。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-144">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f9fd-145"><strong>ConferenceUri</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-145"><strong>ConferenceUri</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-146">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="5f9fd-146">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-147">成为错误报告目标的会议的 URI。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-147">URI of the conference that was the target of the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f9fd-148"><strong>ConferenceUriType</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-148"><strong>ConferenceUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-149">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="5f9fd-149">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-150">成为错误报告目标的会议的 URI 类型。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-150">URI type of the conference that was the target of the error report.</span></span> <span data-ttu-id="5f9fd-151">有关详细信息，请参阅 <a href="lync-server-2013-uritypes-table.md">Lync Server 2013 中的 UriTypes 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-151">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f9fd-152"><strong>SessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-152"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-153">datetime</span><span class="sxs-lookup"><span data-stu-id="5f9fd-153">datetime</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-154">导致发出错误报告的会话请求的时间。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-154">Time of session request that originated the error report.</span></span> <span data-ttu-id="5f9fd-155">与 SessionIdSeq 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-155">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="5f9fd-156">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-156">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f9fd-157"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-157"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-158">int</span><span class="sxs-lookup"><span data-stu-id="5f9fd-158">int</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-159">用于标识导致发出错误报告的会话请求的 ID 编号。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-159">ID number to identify the session request that originated the error report.</span></span> <span data-ttu-id="5f9fd-160">与 SessionIdTime 结合使用来唯一地标识会话。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-160">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="5f9fd-161">有关详细信息，请参阅 <a href="lync-server-2013-dialogs-table.md">Lync Server 2013 中的对话框表</a> 。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-161">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f9fd-162"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-162"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-163">varstring (775) </span><span class="sxs-lookup"><span data-stu-id="5f9fd-163">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-p111">导致出错的会话的 SIP 对话 ID。格式为：</span><span class="sxs-lookup"><span data-stu-id="5f9fd-p111">SIP dialog ID of session that originated the error. The format is:</span></span></p>
<p><span data-ttu-id="5f9fd-166">对话框; 从-标签; 到-标记</span><span class="sxs-lookup"><span data-stu-id="5f9fd-166">dialog;from-tag;to-tag</span></span></p>
<p><span data-ttu-id="5f9fd-167">可以使用以下语法将此数据转换为文本格式：</span><span class="sxs-lookup"><span data-stu-id="5f9fd-167">This data can be converted to text format by using this syntax:</span></span></p>
<p><span data-ttu-id="5f9fd-168">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="5f9fd-168">cast(cast(ExternalId as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f9fd-169"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-169"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-170">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="5f9fd-170">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-171">导致出错的用户所使用的客户端版本。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-171">Version of client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f9fd-172"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-172"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-173">int</span><span class="sxs-lookup"><span data-stu-id="5f9fd-173">int</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-174">导致出错的用户所使用的客户端。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-174">Client used by the user who originated the error.</span></span> <span data-ttu-id="5f9fd-175">有关更多详细信息，请参阅 <a href="lync-server-2013-useragentdef-table.md">Lync Server 2013 中的 UserAgentDef 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-175">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f9fd-176"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-176"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-177">nvarchar (64) </span><span class="sxs-lookup"><span data-stu-id="5f9fd-177">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-178">导致出错的用户所使用的客户端的类别名称。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-178">Name of the category of the client used by the user who originated the error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f9fd-179"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-179"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-180">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="5f9fd-180">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-181">导致出错的服务器的名称（如果报告发送自服务器组件）。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-181">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f9fd-182"><strong>应用程序</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-182"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-183">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="5f9fd-183">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-184">导致出错的应用程序的名称（如果报告发送自服务器组件）。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-184">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f9fd-185"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-185"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-186">int</span><span class="sxs-lookup"><span data-stu-id="5f9fd-186">int</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-187">包含错误报告的 SIP 消息对话的 SIP 响应代码。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-187">SIP response code to the session of the SIP message containing the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f9fd-188"><strong>RequestType</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-188"><strong>RequestType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-189">varchar (max) </span><span class="sxs-lookup"><span data-stu-id="5f9fd-189">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-190">失败的请求的类型。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-190">Type of request that failed.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f9fd-191"><strong>ContentType</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-191"><strong>ContentType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-192">varchar (max) </span><span class="sxs-lookup"><span data-stu-id="5f9fd-192">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-193">失败的请求的内容类型。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-193">Content type of the request that failed.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f9fd-194"><strong>CallType</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-194"><strong>CallType</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-195">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="5f9fd-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-196">会话类型。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-196">Type of session.</span></span> <span data-ttu-id="5f9fd-197">有关详细信息，请参阅 <a href="lync-server-2013-calltype-table.md">Lync Server 2013 中的 CallType 表</a> 。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-197">See the <a href="lync-server-2013-calltype-table.md">CallType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f9fd-198"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-198"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-199">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="5f9fd-199">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-200">关联会议中所涉及不同组件的加入时间信息的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-200">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f9fd-201"><strong>SetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-201"><strong>SetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-202">int</span><span class="sxs-lookup"><span data-stu-id="5f9fd-202">int</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-203">特定组件加入会议所需的时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-203">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f9fd-204"><strong>IsCapturedByServer</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-204"><strong>IsCapturedByServer</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-205">位</span><span class="sxs-lookup"><span data-stu-id="5f9fd-205">bit</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-206">指示错误报告是由在前端服务器上运行的 CDR 代理捕获的，还是客户端发送的。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-206">Indicates whether the error report was captured by the CDR agent running on the Front End server, or sent by the client.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f9fd-207"><strong>Flag</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-207"><strong>Flag</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-208">smallint</span><span class="sxs-lookup"><span data-stu-id="5f9fd-208">smallint</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-209">保留以供将来使用。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-209">Reserved for future use.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f9fd-210"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-210"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-211">varchar (max) </span><span class="sxs-lookup"><span data-stu-id="5f9fd-211">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-212">有关错误的其他信息。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-212">Additional information about the error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5f9fd-213"><strong>FrontEnd</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-213"><strong>FrontEnd</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-214">nvarchar</span><span class="sxs-lookup"><span data-stu-id="5f9fd-214">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-215">提交报告的前端服务器的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-215">Fully qualified domain name of the Front End server that submitted the report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5f9fd-216"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="5f9fd-216"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="5f9fd-217">nvarchar</span><span class="sxs-lookup"><span data-stu-id="5f9fd-217">nvarchar</span></span></p></td>
<td><p><span data-ttu-id="5f9fd-218">包含提交报告的前端服务器的池的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="5f9fd-218">Fully qualified domain name of the pool containing the Front End server that submitted the report.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

