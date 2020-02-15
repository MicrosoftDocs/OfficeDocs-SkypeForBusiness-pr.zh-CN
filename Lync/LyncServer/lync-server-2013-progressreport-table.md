---
title: Lync Server 2013： ProgressReport 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport table
ms:assetid: 38e5f060-5e9b-4185-87b2-7ef61c4bb75f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425864(v=OCS.15)
ms:contentKeyID: 48183847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1aae907981e04d8966bb7eac4229232056d1004e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-table-in-lync-server-2013"></a><span data-ttu-id="ca54b-102">Lync Server 2013 中的 ProgressReport 表</span><span class="sxs-lookup"><span data-stu-id="ca54b-102">ProgressReport table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca54b-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ca54b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ca54b-104">进度报告基于呼叫或会话结束后客户端上载到数据库的数据。</span><span class="sxs-lookup"><span data-stu-id="ca54b-104">Progress reports are based on data uploaded by the client to the database after a call or session is completed.</span></span> <span data-ttu-id="ca54b-105">只会针对 Lync Server 2013 判定可能对诊断有用的呼叫和会话编写进度报告。</span><span class="sxs-lookup"><span data-stu-id="ca54b-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span>

<span data-ttu-id="ca54b-106">ErrorTime、ErrorReportSeq 和 ProgressReportSeq 字段不一定表示错误，而是表示指示呼叫或消息状态的消息。</span><span class="sxs-lookup"><span data-stu-id="ca54b-106">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca54b-107">列</span><span class="sxs-lookup"><span data-stu-id="ca54b-107">Column</span></span></th>
<th><span data-ttu-id="ca54b-108">数据类型</span><span class="sxs-lookup"><span data-stu-id="ca54b-108">Data Type</span></span></th>
<th><span data-ttu-id="ca54b-109">键/索引</span><span class="sxs-lookup"><span data-stu-id="ca54b-109">Key/Index</span></span></th>
<th><span data-ttu-id="ca54b-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="ca54b-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca54b-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="ca54b-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ca54b-112">datetime</span><span class="sxs-lookup"><span data-stu-id="ca54b-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="ca54b-113">主、外</span><span class="sxs-lookup"><span data-stu-id="ca54b-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ca54b-114">包含此进度报告的进度错误报告的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="ca54b-114">Date and time of the progress error report that contains this progress report.</span></span> <span data-ttu-id="ca54b-115">有关详细信息，请参阅<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ca54b-115">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca54b-116"><strong>ErrorId</strong></span><span class="sxs-lookup"><span data-stu-id="ca54b-116"><strong>ErrorId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca54b-117">int</span><span class="sxs-lookup"><span data-stu-id="ca54b-117">int</span></span></p></td>
<td><p><span data-ttu-id="ca54b-118">主、外</span><span class="sxs-lookup"><span data-stu-id="ca54b-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ca54b-119">与 ErrorTime 和 ProgressReportSeq 结合使用唯一地标识进度报告的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="ca54b-119">ID number used in conjunction with ErrorTime, ProgressReportSeq to uniquely identify a progress report.</span></span> <span data-ttu-id="ca54b-120">有关详细信息，请参阅<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表</a>。</span><span class="sxs-lookup"><span data-stu-id="ca54b-120">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca54b-121"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ca54b-121"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ca54b-122">int</span><span class="sxs-lookup"><span data-stu-id="ca54b-122">int</span></span></p></td>
<td><p><span data-ttu-id="ca54b-123">主、外</span><span class="sxs-lookup"><span data-stu-id="ca54b-123">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="ca54b-124">标识错误报告的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="ca54b-124">ID number that identifies the error report.</span></span> <span data-ttu-id="ca54b-125">ErrorReporSeq 与 ErrorTime 结合使用来唯一地标识错误报告。</span><span class="sxs-lookup"><span data-stu-id="ca54b-125">ErrorReporSeq is used in conjunction with ErrorTime to uniquely identify an error report.</span></span> <span data-ttu-id="ca54b-126">有关详细信息，请参阅<a href="lync-server-2013-errorreport-table.md">Lync Server 2013 中的 ErrorReport 表</a></span><span class="sxs-lookup"><span data-stu-id="ca54b-126">See the <a href="lync-server-2013-errorreport-table.md">ErrorReport table in Lync Server 2013</a> for more information</span></span></p>
<p><span data-ttu-id="ca54b-127">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ca54b-127">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca54b-128"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ca54b-128"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ca54b-129">int</span><span class="sxs-lookup"><span data-stu-id="ca54b-129">int</span></span></p></td>
<td><p><span data-ttu-id="ca54b-130">主</span><span class="sxs-lookup"><span data-stu-id="ca54b-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="ca54b-p105">标识进度报告的 ID 号。与 ErrorTime 和 ErrorReportSeq 结合使用可唯一地标识进度报告。</span><span class="sxs-lookup"><span data-stu-id="ca54b-p105">ID number to identify the progress report. Used in conjunction with ErrorTime and ErrorReportSeq to uniquely identify a progress report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca54b-133"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="ca54b-133"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca54b-134">int</span><span class="sxs-lookup"><span data-stu-id="ca54b-134">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ca54b-135">进度报告的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="ca54b-135">Diagnostic ID of the progress report.</span></span></p>
<p><span data-ttu-id="ca54b-136">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ca54b-136">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca54b-137"><strong>SourceId</strong></span><span class="sxs-lookup"><span data-stu-id="ca54b-137"><strong>SourceId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca54b-138">int</span><span class="sxs-lookup"><span data-stu-id="ca54b-138">int</span></span></p></td>
<td><p><span data-ttu-id="ca54b-139">对外</span><span class="sxs-lookup"><span data-stu-id="ca54b-139">Foreign</span></span></p></td>
<td><p><span data-ttu-id="ca54b-140">发送错误报告的服务器（如果报告是从服务器组件发送的）。</span><span class="sxs-lookup"><span data-stu-id="ca54b-140">Server that sent the error report (if the report was sent from a server component).</span></span> <span data-ttu-id="ca54b-141">有关详细信息，请参阅<a href="lync-server-2013-servers-table.md">Lync Server 2013 中的 Servers 表</a>。此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ca54b-141">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca54b-142"><strong>ApplicationId</strong></span><span class="sxs-lookup"><span data-stu-id="ca54b-142"><strong>ApplicationId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca54b-143">int</span><span class="sxs-lookup"><span data-stu-id="ca54b-143">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ca54b-p107">报告涉及的 Lync Server 进程。有关详细信息，请参阅 Application 表。</span><span class="sxs-lookup"><span data-stu-id="ca54b-p107">The Lync Server process that the report is about. See the Application Table for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca54b-146"><strong>详细信息</strong></span><span class="sxs-lookup"><span data-stu-id="ca54b-146"><strong>Detail</strong></span></span></p></td>
<td><p><span data-ttu-id="ca54b-147">image</span><span class="sxs-lookup"><span data-stu-id="ca54b-147">image</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ca54b-148">为节省空间而以二进制格式存储的进度报告详细信息。使用以下语法可将此数据转换为文本格式：</span><span class="sxs-lookup"><span data-stu-id="ca54b-148">Progress report details, stored in binary format to save space.This data can be converted to text format using this syntax:</span></span></p>
<p><span data-ttu-id="ca54b-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span><span class="sxs-lookup"><span data-stu-id="ca54b-149">cast(cast(Detail as varbinary(max)) as varchar(max))</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca54b-150"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="ca54b-150"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca54b-151">uniqueIdentifier</span><span class="sxs-lookup"><span data-stu-id="ca54b-151">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ca54b-152">与会议中所涉及不同组件的加入时间信息关联的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="ca54b-152">Unique identifier that correlates join time information for the different components involved in a conference.</span></span></p>
<p><span data-ttu-id="ca54b-153">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ca54b-153">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca54b-154"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="ca54b-154"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ca54b-155">int</span><span class="sxs-lookup"><span data-stu-id="ca54b-155">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="ca54b-156">特定组件加入会议的时间（以毫秒计）。</span><span class="sxs-lookup"><span data-stu-id="ca54b-156">Time (in milliseconds) for a specific component to join a conference.</span></span></p>
<p><span data-ttu-id="ca54b-157">此字段是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="ca54b-157">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

