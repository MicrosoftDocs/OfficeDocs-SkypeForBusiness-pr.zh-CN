---
title: Lync Server 2013： ProgressReport 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ProgressReport view
ms:assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721857(v=OCS.15)
ms:contentKeyID: 49733790
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4fa8d73981490503b26b77b79be6f42aab77703e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747241"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="570b3-102">Lync Server 2013 中的 ProgressReport 视图</span><span class="sxs-lookup"><span data-stu-id="570b3-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="570b3-103">_**主题上次修改时间：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="570b3-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="570b3-104">ProgressReport 视图存储有关已完成会话的信息。</span><span class="sxs-lookup"><span data-stu-id="570b3-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="570b3-105">将仅写入 Lync Server 2013 确定可能对诊断目的有用的通话和会话的进度报告。</span><span class="sxs-lookup"><span data-stu-id="570b3-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="570b3-106">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="570b3-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="570b3-107">"ErrorTime"、"ErrorReportSeq" 和 "ProgressReportSeq" 字段不一定是指错误，而是指示调用状态或消息的消息。</span><span class="sxs-lookup"><span data-stu-id="570b3-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="570b3-108">列</span><span class="sxs-lookup"><span data-stu-id="570b3-108">Column</span></span></th>
<th><span data-ttu-id="570b3-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="570b3-109">Data Type</span></span></th>
<th><span data-ttu-id="570b3-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="570b3-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="570b3-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="570b3-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="570b3-112">datetime</span><span class="sxs-lookup"><span data-stu-id="570b3-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="570b3-113">出现错误的时间。</span><span class="sxs-lookup"><span data-stu-id="570b3-113">Time of error occurred.</span></span> <span data-ttu-id="570b3-114">与 ErrorReportSeq 结合使用以唯一标识错误。</span><span class="sxs-lookup"><span data-stu-id="570b3-114">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="570b3-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="570b3-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="570b3-116">int</span><span class="sxs-lookup"><span data-stu-id="570b3-116">int</span></span></p></td>
<td><p><span data-ttu-id="570b3-117">标识错误的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="570b3-117">ID number to identify the error.</span></span> <span data-ttu-id="570b3-118">与 ErrorTime 结合使用以唯一标识错误。</span><span class="sxs-lookup"><span data-stu-id="570b3-118">Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="570b3-119"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="570b3-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="570b3-120">int</span><span class="sxs-lookup"><span data-stu-id="570b3-120">int</span></span></p></td>
<td><p><span data-ttu-id="570b3-121">标识进度报表的 ID。</span><span class="sxs-lookup"><span data-stu-id="570b3-121">ID to identify the progress report.</span></span> <span data-ttu-id="570b3-122">用于区分同一错误报告的进度报告。</span><span class="sxs-lookup"><span data-stu-id="570b3-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="570b3-123"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="570b3-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="570b3-124">int</span><span class="sxs-lookup"><span data-stu-id="570b3-124">int</span></span></p></td>
<td><p><span data-ttu-id="570b3-125">错误报告的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="570b3-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="570b3-126"><strong>来源</strong></span><span class="sxs-lookup"><span data-stu-id="570b3-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="570b3-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="570b3-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="570b3-128">产生错误的服务器的名称（如果报表是从服务器组件发送的）。</span><span class="sxs-lookup"><span data-stu-id="570b3-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="570b3-129"><strong>Application</strong></span><span class="sxs-lookup"><span data-stu-id="570b3-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="570b3-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="570b3-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="570b3-131">发出错误的应用程序的名称（如果报表是从服务器组件发送的）。</span><span class="sxs-lookup"><span data-stu-id="570b3-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="570b3-132"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="570b3-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="570b3-133">标识符</span><span class="sxs-lookup"><span data-stu-id="570b3-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="570b3-134">关联会议中涉及的不同组件的加入时间信息的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="570b3-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="570b3-135"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="570b3-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="570b3-136">int</span><span class="sxs-lookup"><span data-stu-id="570b3-136">int</span></span></p></td>
<td><p><span data-ttu-id="570b3-137">特定组件加入会议所需的时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="570b3-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="570b3-138"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="570b3-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="570b3-139">varchar （max）</span><span class="sxs-lookup"><span data-stu-id="570b3-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="570b3-140">其他错误信息。</span><span class="sxs-lookup"><span data-stu-id="570b3-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

