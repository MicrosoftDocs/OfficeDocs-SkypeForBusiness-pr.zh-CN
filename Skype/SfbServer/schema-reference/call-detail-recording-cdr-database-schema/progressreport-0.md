---
title: ProgressReport 视图
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: ProgressReport 视图存储有关已完成会话的信息。 仅对呼叫和 Lync Server 2013 确定用于进行诊断下可能有用的会话将写入进度报告。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 5f7cbba2580b83a65dbce00588f3c567317f4df4
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891115"
---
# <a name="progressreport-view"></a><span data-ttu-id="14bd6-105">ProgressReport 视图</span><span class="sxs-lookup"><span data-stu-id="14bd6-105">ProgressReport view</span></span>
 
<span data-ttu-id="14bd6-106">ProgressReport 视图存储有关已完成会话的信息。</span><span class="sxs-lookup"><span data-stu-id="14bd6-106">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="14bd6-107">仅对呼叫和 Lync Server 2013 确定用于进行诊断下可能有用的会话将写入进度报告。</span><span class="sxs-lookup"><span data-stu-id="14bd6-107">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="14bd6-108">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="14bd6-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="14bd6-109">ErrorTime、 ErrorReportSeq 和 ProgressReportSeq 字段不一定引用，而对错误消息，以表明的呼叫或消息状态。</span><span class="sxs-lookup"><span data-stu-id="14bd6-109">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don't necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span> 
  
|<span data-ttu-id="14bd6-110">**列**</span><span class="sxs-lookup"><span data-stu-id="14bd6-110">**Column**</span></span>|<span data-ttu-id="14bd6-111">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="14bd6-111">**Data Type**</span></span>|<span data-ttu-id="14bd6-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="14bd6-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="14bd6-113">**ErrorTime**</span><span class="sxs-lookup"><span data-stu-id="14bd6-113">**ErrorTime**</span></span> <br/> |<span data-ttu-id="14bd6-114">datetime</span><span class="sxs-lookup"><span data-stu-id="14bd6-114">datetime</span></span>  <br/> |<span data-ttu-id="14bd6-115">发生的错误的时间。</span><span class="sxs-lookup"><span data-stu-id="14bd6-115">Time of error occurred.</span></span> <span data-ttu-id="14bd6-116">与 ErrorReportSeq 结合使用，来唯一地标识错误。</span><span class="sxs-lookup"><span data-stu-id="14bd6-116">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="14bd6-117">**ErrorReportSeq**</span><span class="sxs-lookup"><span data-stu-id="14bd6-117">**ErrorReportSeq**</span></span> <br/> |<span data-ttu-id="14bd6-118">int</span><span class="sxs-lookup"><span data-stu-id="14bd6-118">int</span></span>  <br/> |<span data-ttu-id="14bd6-119">若要确定错误的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="14bd6-119">ID number to identify the error.</span></span> <span data-ttu-id="14bd6-120">与 ErrorTime 结合使用，来唯一地标识错误。</span><span class="sxs-lookup"><span data-stu-id="14bd6-120">Used in conjunction with ErrorTime to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="14bd6-121">**ProgressReportSeq**</span><span class="sxs-lookup"><span data-stu-id="14bd6-121">**ProgressReportSeq**</span></span> <br/> |<span data-ttu-id="14bd6-122">int</span><span class="sxs-lookup"><span data-stu-id="14bd6-122">int</span></span>  <br/> |<span data-ttu-id="14bd6-123">若要确定进度报告的 ID。</span><span class="sxs-lookup"><span data-stu-id="14bd6-123">ID to identify the progress report.</span></span> <span data-ttu-id="14bd6-124">用于区分相同的错误报告的进度报告。</span><span class="sxs-lookup"><span data-stu-id="14bd6-124">Used to distinguish progress reports of the same error report.</span></span>  <br/> |
|<span data-ttu-id="14bd6-125">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="14bd6-125">**MsDiagId**</span></span> <br/> |<span data-ttu-id="14bd6-126">int</span><span class="sxs-lookup"><span data-stu-id="14bd6-126">int</span></span>  <br/> |<span data-ttu-id="14bd6-127">错误报告的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="14bd6-127">Diagnostic ID for the error report.</span></span>  <br/> |
|<span data-ttu-id="14bd6-128">**来源**</span><span class="sxs-lookup"><span data-stu-id="14bd6-128">**Source**</span></span> <br/> |<span data-ttu-id="14bd6-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="14bd6-129">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="14bd6-130">产生错误 （如果报告发送自服务器组件） 的服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="14bd6-130">Name of server that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="14bd6-131">**应用程序**</span><span class="sxs-lookup"><span data-stu-id="14bd6-131">**Application**</span></span> <br/> |<span data-ttu-id="14bd6-132">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="14bd6-132">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="14bd6-133">产生错误 （如果报告发送自服务器组件） 的应用程序的名称。</span><span class="sxs-lookup"><span data-stu-id="14bd6-133">Name of application that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="14bd6-134">**TelemetryId**</span><span class="sxs-lookup"><span data-stu-id="14bd6-134">**TelemetryId**</span></span> <br/> |<span data-ttu-id="14bd6-135">唯一标识符</span><span class="sxs-lookup"><span data-stu-id="14bd6-135">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="14bd6-136">关联会议中所涉及的不同组件的加入时间信息的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="14bd6-136">Unique identifier correlating join time information for the different components involved in a conference.</span></span>  <br/> |
|<span data-ttu-id="14bd6-137">**SessionSetupTime**</span><span class="sxs-lookup"><span data-stu-id="14bd6-137">**SessionSetupTime**</span></span> <br/> |<span data-ttu-id="14bd6-138">int</span><span class="sxs-lookup"><span data-stu-id="14bd6-138">int</span></span>  <br/> |<span data-ttu-id="14bd6-139">时间 （以毫秒为单位） 所需的特定组件加入会议。</span><span class="sxs-lookup"><span data-stu-id="14bd6-139">Time (in milliseconds) required for a specific component to join a conference.</span></span>  <br/> |
|<span data-ttu-id="14bd6-140">**MsDiagHeader**</span><span class="sxs-lookup"><span data-stu-id="14bd6-140">**MsDiagHeader**</span></span> <br/> |<span data-ttu-id="14bd6-141">varchar(max)</span><span class="sxs-lookup"><span data-stu-id="14bd6-141">varchar(max)</span></span>  <br/> |<span data-ttu-id="14bd6-142">其他错误信息。</span><span class="sxs-lookup"><span data-stu-id="14bd6-142">Additional error information.</span></span>  <br/> |
   

