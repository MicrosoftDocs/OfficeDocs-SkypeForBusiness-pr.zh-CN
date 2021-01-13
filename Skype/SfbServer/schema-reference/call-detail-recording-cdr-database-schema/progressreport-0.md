---
title: ProgressReport 视图
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: ProgressReport 视图会存储有关已完成的会话的信息。 只会针对 Lync Server 2013 判定可能对诊断有用的呼叫和会话编写进度报告。 此视图是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 6cc8295e73463fff9d4913efbf9d4844f9316149
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823182"
---
# <a name="progressreport-view"></a><span data-ttu-id="af379-105">ProgressReport 视图</span><span class="sxs-lookup"><span data-stu-id="af379-105">ProgressReport view</span></span>
 
<span data-ttu-id="af379-106">ProgressReport 视图会存储有关已完成的会话的信息。</span><span class="sxs-lookup"><span data-stu-id="af379-106">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="af379-107">只会针对 Lync Server 2013 判定可能对诊断有用的呼叫和会话编写进度报告。</span><span class="sxs-lookup"><span data-stu-id="af379-107">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="af379-108">此视图是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="af379-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="af379-109">ErrorTime、ErrorReportSeq 和 ProgressReportSeq 字段不一定指错误，而是指指示呼叫或消息状态的消息。</span><span class="sxs-lookup"><span data-stu-id="af379-109">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don't necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span> 
  
|<span data-ttu-id="af379-110">**列**</span><span class="sxs-lookup"><span data-stu-id="af379-110">**Column**</span></span>|<span data-ttu-id="af379-111">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="af379-111">**Data Type**</span></span>|<span data-ttu-id="af379-112">**Details**</span><span class="sxs-lookup"><span data-stu-id="af379-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="af379-113">**ErrorTime**</span><span class="sxs-lookup"><span data-stu-id="af379-113">**ErrorTime**</span></span> <br/> |<span data-ttu-id="af379-114">datetime</span><span class="sxs-lookup"><span data-stu-id="af379-114">datetime</span></span>  <br/> |<span data-ttu-id="af379-p103">发生错误的时间。与 ErrorReportSeq 结合使用来唯一地标识错误。</span><span class="sxs-lookup"><span data-stu-id="af379-p103">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="af379-117">**ErrorReportSeq**</span><span class="sxs-lookup"><span data-stu-id="af379-117">**ErrorReportSeq**</span></span> <br/> |<span data-ttu-id="af379-118">int</span><span class="sxs-lookup"><span data-stu-id="af379-118">int</span></span>  <br/> |<span data-ttu-id="af379-p104">用于标识错误的 ID 号。与 ErrorTime 结合使用来唯一地标识错误。</span><span class="sxs-lookup"><span data-stu-id="af379-p104">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="af379-121">**ProgressReportSeq**</span><span class="sxs-lookup"><span data-stu-id="af379-121">**ProgressReportSeq**</span></span> <br/> |<span data-ttu-id="af379-122">int</span><span class="sxs-lookup"><span data-stu-id="af379-122">int</span></span>  <br/> |<span data-ttu-id="af379-123">用于标识进度报告的 ID。</span><span class="sxs-lookup"><span data-stu-id="af379-123">ID to identify the progress report.</span></span> <span data-ttu-id="af379-124">用来区分相同错误报告的进度报告。</span><span class="sxs-lookup"><span data-stu-id="af379-124">Used to distinguish progress reports of the same error report.</span></span>  <br/> |
|<span data-ttu-id="af379-125">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="af379-125">**MsDiagId**</span></span> <br/> |<span data-ttu-id="af379-126">int</span><span class="sxs-lookup"><span data-stu-id="af379-126">int</span></span>  <br/> |<span data-ttu-id="af379-127">错误报告的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="af379-127">Diagnostic ID for the error report.</span></span>  <br/> |
|<span data-ttu-id="af379-128">**Source**</span><span class="sxs-lookup"><span data-stu-id="af379-128">**Source**</span></span> <br/> |<span data-ttu-id="af379-129">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="af379-129">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="af379-130">导致出错的服务器的名称（如果报告发送自服务器组件）。</span><span class="sxs-lookup"><span data-stu-id="af379-130">Name of server that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="af379-131">**应用程序**</span><span class="sxs-lookup"><span data-stu-id="af379-131">**Application**</span></span> <br/> |<span data-ttu-id="af379-132">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="af379-132">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="af379-133">产生错误的应用程序的名称（如果报告是从服务器组件发送的）。</span><span class="sxs-lookup"><span data-stu-id="af379-133">Name of application that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="af379-134">**TelemetryId**</span><span class="sxs-lookup"><span data-stu-id="af379-134">**TelemetryId**</span></span> <br/> |<span data-ttu-id="af379-135">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="af379-135">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="af379-136">关联会议中所涉及不同组件的加入时间信息的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="af379-136">Unique identifier correlating join time information for the different components involved in a conference.</span></span>  <br/> |
|<span data-ttu-id="af379-137">**SessionSetupTime**</span><span class="sxs-lookup"><span data-stu-id="af379-137">**SessionSetupTime**</span></span> <br/> |<span data-ttu-id="af379-138">int</span><span class="sxs-lookup"><span data-stu-id="af379-138">int</span></span>  <br/> |<span data-ttu-id="af379-139">特定组件加入会议所需的时间（以毫秒为单位）。</span><span class="sxs-lookup"><span data-stu-id="af379-139">Time (in milliseconds) required for a specific component to join a conference.</span></span>  <br/> |
|<span data-ttu-id="af379-140">**MsDiagHeader**</span><span class="sxs-lookup"><span data-stu-id="af379-140">**MsDiagHeader**</span></span> <br/> |<span data-ttu-id="af379-141">varchar (max) </span><span class="sxs-lookup"><span data-stu-id="af379-141">varchar(max)</span></span>  <br/> |<span data-ttu-id="af379-142">其他错误信息。</span><span class="sxs-lookup"><span data-stu-id="af379-142">Additional error information.</span></span>  <br/> |
   

