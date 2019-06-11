---
title: Lync Server 2013：ProgressReport 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa8ca0341cd5b85418ef5f71234870ae4171af27
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823719"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="fb52f-102">Lync Server 2013 中的 ProgressReport 表</span><span class="sxs-lookup"><span data-stu-id="fb52f-102">ProgressReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fb52f-103">_**主题上次修改时间:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="fb52f-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="fb52f-104">进度报告基于客户端在通话或会话完成后上载到数据库的数据。</span><span class="sxs-lookup"><span data-stu-id="fb52f-104">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="fb52f-105">将仅写入 Lync Server 2013 确定可能对诊断目的有用的通话和会话的进度报告。</span><span class="sxs-lookup"><span data-stu-id="fb52f-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="fb52f-106">"ErrorTime"、"ErrorReportSeq" 和 "ProgressReportSeq" 字段不一定是指错误, 而是指示调用状态或消息的消息。</span><span class="sxs-lookup"><span data-stu-id="fb52f-106">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fb52f-107">列</span><span class="sxs-lookup"><span data-stu-id="fb52f-107">Column</span></span></th>
<th><span data-ttu-id="fb52f-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="fb52f-108">Data Type</span></span></th>
<th><span data-ttu-id="fb52f-109">键/索引</span><span class="sxs-lookup"><span data-stu-id="fb52f-109">Key/Index</span></span></th>
<th><span data-ttu-id="fb52f-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="fb52f-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fb52f-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="fb52f-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fb52f-112">datetime</span><span class="sxs-lookup"><span data-stu-id="fb52f-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="fb52f-113">主、外部</span><span class="sxs-lookup"><span data-stu-id="fb52f-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="fb52f-114">包含此进度报表的 "进度错误" 报表的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="fb52f-114">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="fb52f-115">有关详细信息, 请参阅<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表</a>。</span><span class="sxs-lookup"><span data-stu-id="fb52f-115">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb52f-116"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="fb52f-116"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="fb52f-117">int</span><span class="sxs-lookup"><span data-stu-id="fb52f-117">int</span></span></p></td>
<td><p><span data-ttu-id="fb52f-118">主、外部</span><span class="sxs-lookup"><span data-stu-id="fb52f-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="fb52f-119">与 ErrorTime 和 ProgressReportSeq 结合使用的 ID 号, 用于唯一标识进度报告。</span><span class="sxs-lookup"><span data-stu-id="fb52f-119">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="fb52f-120">有关详细信息, 请参阅<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表</a>。</span><span class="sxs-lookup"><span data-stu-id="fb52f-120">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb52f-121"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fb52f-121"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fb52f-122">int</span><span class="sxs-lookup"><span data-stu-id="fb52f-122">int</span></span></p></td>
<td><p><span data-ttu-id="fb52f-123">主、外部</span><span class="sxs-lookup"><span data-stu-id="fb52f-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="fb52f-124">标识错误报告的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="fb52f-124">ID number that identifies the error report.</span></span> <span data-ttu-id="fb52f-125">ErrorReporSeq 与 ErrorTime 结合使用, 以唯一标识错误报告。</span><span class="sxs-lookup"><span data-stu-id="fb52f-125">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="fb52f-126">有关详细信息, 请参阅<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表</a>。</span><span class="sxs-lookup"><span data-stu-id="fb52f-126">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="fb52f-127">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="fb52f-127">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb52f-128"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="fb52f-128"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="fb52f-129">int</span><span class="sxs-lookup"><span data-stu-id="fb52f-129">int</span></span></p></td>
<td><p><span data-ttu-id="fb52f-130">Primary</span><span class="sxs-lookup"><span data-stu-id="fb52f-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="fb52f-131">标识进度报表的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="fb52f-131">ID number to identify the progress report.</span></span> <span data-ttu-id="fb52f-132">与 ErrorTime 和 ErrorReportSeq 结合使用, 以唯一标识进度报表。</span><span class="sxs-lookup"><span data-stu-id="fb52f-132">Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb52f-133"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="fb52f-133"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="fb52f-134">int</span><span class="sxs-lookup"><span data-stu-id="fb52f-134">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fb52f-135">进度报表的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="fb52f-135">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="fb52f-136">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="fb52f-136">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb52f-137"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="fb52f-137"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="fb52f-138">int</span><span class="sxs-lookup"><span data-stu-id="fb52f-138">int</span></span></p></td>
<td><p><span data-ttu-id="fb52f-139">外表</span><span class="sxs-lookup"><span data-stu-id="fb52f-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="fb52f-140">发送错误报告的服务器 (如果报表是从服务器组件发送的)。</span><span class="sxs-lookup"><span data-stu-id="fb52f-140">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="fb52f-141">有关详细信息, 请参阅<a href="lync-server-2013-servers-table.md">Lync Server 2013 中</a>的 "服务器" 表。此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="fb52f-141">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb52f-142"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="fb52f-142"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="fb52f-143">int</span><span class="sxs-lookup"><span data-stu-id="fb52f-143">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fb52f-144">报表所针对的 Lync Server 进程。</span><span class="sxs-lookup"><span data-stu-id="fb52f-144">The Lync Server process that the report is about.</span></span> <span data-ttu-id="fb52f-145">有关详细信息, 请参阅应用程序表。</span><span class="sxs-lookup"><span data-stu-id="fb52f-145">See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb52f-146"><strong>详情</strong></span><span class="sxs-lookup"><span data-stu-id="fb52f-146"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="fb52f-147">图像</span><span class="sxs-lookup"><span data-stu-id="fb52f-147">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fb52f-148">进度报告详细信息, 以二进制格式存储以节省空间。此数据可以使用以下语法转换为文本格式:</span><span class="sxs-lookup"><span data-stu-id="fb52f-148">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="fb52f-149">转换 (cast (作为 varbinary (max) 的详细信息) 作为 varchar (max))</span><span class="sxs-lookup"><span data-stu-id="fb52f-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fb52f-150"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="fb52f-150"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="fb52f-151">标识符</span><span class="sxs-lookup"><span data-stu-id="fb52f-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fb52f-152">关联会议中涉及的不同组件的联接时间信息的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="fb52f-152">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="fb52f-153">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="fb52f-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fb52f-154"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="fb52f-154"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="fb52f-155">int</span><span class="sxs-lookup"><span data-stu-id="fb52f-155">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="fb52f-156">特定组件加入会议的时间 (以毫秒为单位)。</span><span class="sxs-lookup"><span data-stu-id="fb52f-156">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="fb52f-157">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="fb52f-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

