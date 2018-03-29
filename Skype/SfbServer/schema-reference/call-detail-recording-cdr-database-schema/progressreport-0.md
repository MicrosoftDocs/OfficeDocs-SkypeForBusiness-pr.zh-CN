---
title: ProgressReport 视图
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: ProgressReport 视图存储有关已完成的会话信息。 进度报告将仅对呼叫和 Lync Server 2013 确定可用于诊断目的的会话写入。 在 Microsoft Lync Server 2013 引入了此视图。
ms.openlocfilehash: 7dab41202eb098e2e49e5d4960b0c7b4e4c6570d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="progressreport-view"></a><span data-ttu-id="1c3ef-105">ProgressReport 视图</span><span class="sxs-lookup"><span data-stu-id="1c3ef-105">ProgressReport view</span></span>
 
<span data-ttu-id="1c3ef-106">ProgressReport 视图存储有关已完成的会话信息。</span><span class="sxs-lookup"><span data-stu-id="1c3ef-106">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="1c3ef-107">进度报告将仅对呼叫和 Lync Server 2013 确定可用于诊断目的的会话写入。</span><span class="sxs-lookup"><span data-stu-id="1c3ef-107">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="1c3ef-108">在 Microsoft Lync Server 2013 引入了此视图。</span><span class="sxs-lookup"><span data-stu-id="1c3ef-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1c3ef-109">ErrorTime、 ErrorReportSeq 和 ProgressReportSeq 字段一定不请而对错误消息，以表明通话或邮件的状态。</span><span class="sxs-lookup"><span data-stu-id="1c3ef-109">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don't necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span> 
  
|<span data-ttu-id="1c3ef-110">**列**</span><span class="sxs-lookup"><span data-stu-id="1c3ef-110">**Column**</span></span>|<span data-ttu-id="1c3ef-111">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1c3ef-111">**Data Type**</span></span>|<span data-ttu-id="1c3ef-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="1c3ef-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1c3ef-113">**ErrorTime**</span><span class="sxs-lookup"><span data-stu-id="1c3ef-113">**ErrorTime**</span></span> <br/> |<span data-ttu-id="1c3ef-114">datetime</span><span class="sxs-lookup"><span data-stu-id="1c3ef-114">datetime</span></span>  <br/> |<span data-ttu-id="1c3ef-115">发生错误的时间。</span><span class="sxs-lookup"><span data-stu-id="1c3ef-115">Time of error occurred.</span></span> <span data-ttu-id="1c3ef-116">与 ErrorReportSeq 配合使用，以唯一地标识错误。</span><span class="sxs-lookup"><span data-stu-id="1c3ef-116">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="1c3ef-117">**ErrorReportSeq**</span><span class="sxs-lookup"><span data-stu-id="1c3ef-117">**ErrorReportSeq**</span></span> <br/> |<span data-ttu-id="1c3ef-118">int</span><span class="sxs-lookup"><span data-stu-id="1c3ef-118">int</span></span>  <br/> |<span data-ttu-id="1c3ef-119">若要确定错误的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="1c3ef-119">ID number to identify the error.</span></span> <span data-ttu-id="1c3ef-120">与 ErrorTime 配合使用，以唯一地标识错误。</span><span class="sxs-lookup"><span data-stu-id="1c3ef-120">Used in conjunction with ErrorTime to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="1c3ef-121">**ProgressReportSeq**</span><span class="sxs-lookup"><span data-stu-id="1c3ef-121">**ProgressReportSeq**</span></span> <br/> |<span data-ttu-id="1c3ef-122">int</span><span class="sxs-lookup"><span data-stu-id="1c3ef-122">int</span></span>  <br/> |<span data-ttu-id="1c3ef-123">ID 来标识进度报表。</span><span class="sxs-lookup"><span data-stu-id="1c3ef-123">ID to identify the progress report.</span></span> <span data-ttu-id="1c3ef-124">用于区分同一错误报告的进度报告。</span><span class="sxs-lookup"><span data-stu-id="1c3ef-124">Used to distinguish progress reports of the same error report.</span></span>  <br/> |
|<span data-ttu-id="1c3ef-125">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="1c3ef-125">**MsDiagId**</span></span> <br/> |<span data-ttu-id="1c3ef-126">int</span><span class="sxs-lookup"><span data-stu-id="1c3ef-126">int</span></span>  <br/> |<span data-ttu-id="1c3ef-127">有关错误报告的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="1c3ef-127">Diagnostic ID for the error report.</span></span>  <br/> |
|<span data-ttu-id="1c3ef-128">**来源**</span><span class="sxs-lookup"><span data-stu-id="1c3ef-128">**Source**</span></span> <br/> |<span data-ttu-id="1c3ef-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1c3ef-129">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1c3ef-130">（如果报表的服务器组件发送） 发出了错误的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="1c3ef-130">Name of server that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="1c3ef-131">**应用程序**</span><span class="sxs-lookup"><span data-stu-id="1c3ef-131">**Application**</span></span> <br/> |<span data-ttu-id="1c3ef-132">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1c3ef-132">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1c3ef-133">（如果报表的服务器组件发送） 发出了错误的应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="1c3ef-133">Name of application that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="1c3ef-134">**TelemetryId**</span><span class="sxs-lookup"><span data-stu-id="1c3ef-134">**TelemetryId**</span></span> <br/> |<span data-ttu-id="1c3ef-135">唯一标识符</span><span class="sxs-lookup"><span data-stu-id="1c3ef-135">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="1c3ef-136">将在会议中所涉及的不同部分的加入时间信息关联起来的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="1c3ef-136">Unique identifier correlating join time information for the different components involved in a conference.</span></span>  <br/> |
|<span data-ttu-id="1c3ef-137">**SessionSetupTime**</span><span class="sxs-lookup"><span data-stu-id="1c3ef-137">**SessionSetupTime**</span></span> <br/> |<span data-ttu-id="1c3ef-138">int</span><span class="sxs-lookup"><span data-stu-id="1c3ef-138">int</span></span>  <br/> |<span data-ttu-id="1c3ef-139">时间 （以毫秒为单位） 所需的特定组件加入会议。</span><span class="sxs-lookup"><span data-stu-id="1c3ef-139">Time (in milliseconds) required for a specific component to join a conference.</span></span>  <br/> |
|<span data-ttu-id="1c3ef-140">**MsDiagHeader**</span><span class="sxs-lookup"><span data-stu-id="1c3ef-140">**MsDiagHeader**</span></span> <br/> |<span data-ttu-id="1c3ef-141">varchar(max)</span><span class="sxs-lookup"><span data-stu-id="1c3ef-141">varchar(max)</span></span>  <br/> |<span data-ttu-id="1c3ef-142">其他错误的信息。</span><span class="sxs-lookup"><span data-stu-id="1c3ef-142">Additional error information.</span></span>  <br/> |
   

