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
ms.openlocfilehash: 916fb459e71460249b47719ab4a4c07f8d082e4d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049614"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="progressreport-view-in-lync-server-2013"></a><span data-ttu-id="1def7-102">Lync Server 2013 中的 ProgressReport 视图</span><span class="sxs-lookup"><span data-stu-id="1def7-102">ProgressReport view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1def7-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="1def7-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="1def7-104">ProgressReport 视图会存储有关已完成的会话的信息。</span><span class="sxs-lookup"><span data-stu-id="1def7-104">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="1def7-105">只会针对 Lync Server 2013 判定可能对诊断有用的呼叫和会话编写进度报告。</span><span class="sxs-lookup"><span data-stu-id="1def7-105">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="1def7-106">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="1def7-106">This view was introduced in Microsoft Lync Server 2013.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="1def7-107">ErrorTime、ErrorReportSeq 和 ProgressReportSeq 字段不一定表示错误，而是表示指示呼叫或消息状态的消息。</span><span class="sxs-lookup"><span data-stu-id="1def7-107">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don’t necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span>



</div>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1def7-108">列</span><span class="sxs-lookup"><span data-stu-id="1def7-108">Column</span></span></th>
<th><span data-ttu-id="1def7-109">数据类型</span><span class="sxs-lookup"><span data-stu-id="1def7-109">Data Type</span></span></th>
<th><span data-ttu-id="1def7-110">详细信息</span><span class="sxs-lookup"><span data-stu-id="1def7-110">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1def7-111"><strong>ErrorTime</strong></span><span class="sxs-lookup"><span data-stu-id="1def7-111"><strong>ErrorTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1def7-112">datetime</span><span class="sxs-lookup"><span data-stu-id="1def7-112">datetime</span></span></p></td>
<td><p><span data-ttu-id="1def7-p102">发生错误的时间。与 ErrorReportSeq 结合使用来唯一地标识错误。</span><span class="sxs-lookup"><span data-stu-id="1def7-p102">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1def7-115"><strong>ErrorReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1def7-115"><strong>ErrorReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1def7-116">int</span><span class="sxs-lookup"><span data-stu-id="1def7-116">int</span></span></p></td>
<td><p><span data-ttu-id="1def7-p103">用于标识错误的 ID 号。与 ErrorTime 结合使用来唯一地标识错误。</span><span class="sxs-lookup"><span data-stu-id="1def7-p103">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1def7-119"><strong>ProgressReportSeq</strong></span><span class="sxs-lookup"><span data-stu-id="1def7-119"><strong>ProgressReportSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="1def7-120">int</span><span class="sxs-lookup"><span data-stu-id="1def7-120">int</span></span></p></td>
<td><p><span data-ttu-id="1def7-121">用于标识进度报告的 ID。</span><span class="sxs-lookup"><span data-stu-id="1def7-121">ID to identify the progress report.</span></span> <span data-ttu-id="1def7-122">用来区分相同错误报告的进度报告。</span><span class="sxs-lookup"><span data-stu-id="1def7-122">Used to distinguish progress reports of the same error report.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1def7-123"><strong>MsDiagId</strong></span><span class="sxs-lookup"><span data-stu-id="1def7-123"><strong>MsDiagId</strong></span></span></p></td>
<td><p><span data-ttu-id="1def7-124">int</span><span class="sxs-lookup"><span data-stu-id="1def7-124">int</span></span></p></td>
<td><p><span data-ttu-id="1def7-125">错误报告的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="1def7-125">Diagnostic ID for the error report.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1def7-126"><strong>Source</strong></span><span class="sxs-lookup"><span data-stu-id="1def7-126"><strong>Source</strong></span></span></p></td>
<td><p><span data-ttu-id="1def7-127">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="1def7-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1def7-128">导致出错的服务器的名称（如果报告发送自服务器组件）。</span><span class="sxs-lookup"><span data-stu-id="1def7-128">Name of server that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1def7-129"><strong>应用程序</strong></span><span class="sxs-lookup"><span data-stu-id="1def7-129"><strong>Application</strong></span></span></p></td>
<td><p><span data-ttu-id="1def7-130">nvarchar （256）</span><span class="sxs-lookup"><span data-stu-id="1def7-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="1def7-131">产生错误的应用程序的名称（如果报告是从服务器组件发送的）。</span><span class="sxs-lookup"><span data-stu-id="1def7-131">Name of application that originated the error (if report was sent from a server component).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1def7-132"><strong>TelemetryId</strong></span><span class="sxs-lookup"><span data-stu-id="1def7-132"><strong>TelemetryId</strong></span></span></p></td>
<td><p><span data-ttu-id="1def7-133">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="1def7-133">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="1def7-134">关联会议中所涉及不同组件的加入时间信息的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="1def7-134">Unique identifier correlating join time information for the different components involved in a conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1def7-135"><strong>SessionSetupTime</strong></span><span class="sxs-lookup"><span data-stu-id="1def7-135"><strong>SessionSetupTime</strong></span></span></p></td>
<td><p><span data-ttu-id="1def7-136">int</span><span class="sxs-lookup"><span data-stu-id="1def7-136">int</span></span></p></td>
<td><p><span data-ttu-id="1def7-137">特定组件加入会议所需的时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="1def7-137">Time (in milliseconds) required for a specific component to join a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1def7-138"><strong>MsDiagHeader</strong></span><span class="sxs-lookup"><span data-stu-id="1def7-138"><strong>MsDiagHeader</strong></span></span></p></td>
<td><p><span data-ttu-id="1def7-139">varchar （max）</span><span class="sxs-lookup"><span data-stu-id="1def7-139">varchar(max)</span></span></p></td>
<td><p><span data-ttu-id="1def7-140">其他错误信息。</span><span class="sxs-lookup"><span data-stu-id="1def7-140">Additional error information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

