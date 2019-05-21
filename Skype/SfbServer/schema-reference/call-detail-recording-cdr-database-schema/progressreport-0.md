---
title: ProgressReport 视图
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: ProgressReport 视图存储有关已完成会话的信息。 将仅写入 Lync Server 2013 确定可能对诊断目的有用的通话和会话的进度报告。 此视图已在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: e5ad388c2845be63926f2172f944abc08f58481e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295956"
---
# <a name="progressreport-view"></a><span data-ttu-id="1e194-105">ProgressReport 视图</span><span class="sxs-lookup"><span data-stu-id="1e194-105">ProgressReport view</span></span>
 
<span data-ttu-id="1e194-106">ProgressReport 视图存储有关已完成会话的信息。</span><span class="sxs-lookup"><span data-stu-id="1e194-106">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="1e194-107">将仅写入 Lync Server 2013 确定可能对诊断目的有用的通话和会话的进度报告。</span><span class="sxs-lookup"><span data-stu-id="1e194-107">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="1e194-108">此视图已在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="1e194-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1e194-109">"ErrorTime"、"ErrorReportSeq" 和 "ProgressReportSeq" 字段不一定是指错误, 而是指示调用状态或消息的消息。</span><span class="sxs-lookup"><span data-stu-id="1e194-109">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don't necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span> 
  
|<span data-ttu-id="1e194-110">**列**</span><span class="sxs-lookup"><span data-stu-id="1e194-110">**Column**</span></span>|<span data-ttu-id="1e194-111">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="1e194-111">**Data Type**</span></span>|<span data-ttu-id="1e194-112">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="1e194-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1e194-113">**ErrorTime**</span><span class="sxs-lookup"><span data-stu-id="1e194-113">**ErrorTime**</span></span> <br/> |<span data-ttu-id="1e194-114">datetime</span><span class="sxs-lookup"><span data-stu-id="1e194-114">datetime</span></span>  <br/> |<span data-ttu-id="1e194-115">出现错误的时间。</span><span class="sxs-lookup"><span data-stu-id="1e194-115">Time of error occurred.</span></span> <span data-ttu-id="1e194-116">与 ErrorReportSeq 结合使用以唯一标识错误。</span><span class="sxs-lookup"><span data-stu-id="1e194-116">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="1e194-117">**ErrorReportSeq**</span><span class="sxs-lookup"><span data-stu-id="1e194-117">**ErrorReportSeq**</span></span> <br/> |<span data-ttu-id="1e194-118">int</span><span class="sxs-lookup"><span data-stu-id="1e194-118">int</span></span>  <br/> |<span data-ttu-id="1e194-119">标识错误的 ID 号。</span><span class="sxs-lookup"><span data-stu-id="1e194-119">ID number to identify the error.</span></span> <span data-ttu-id="1e194-120">与 ErrorTime 结合使用以唯一标识错误。</span><span class="sxs-lookup"><span data-stu-id="1e194-120">Used in conjunction with ErrorTime to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="1e194-121">**ProgressReportSeq**</span><span class="sxs-lookup"><span data-stu-id="1e194-121">**ProgressReportSeq**</span></span> <br/> |<span data-ttu-id="1e194-122">int</span><span class="sxs-lookup"><span data-stu-id="1e194-122">int</span></span>  <br/> |<span data-ttu-id="1e194-123">标识进度报表的 ID。</span><span class="sxs-lookup"><span data-stu-id="1e194-123">ID to identify the progress report.</span></span> <span data-ttu-id="1e194-124">用于区分同一错误报告的进度报告。</span><span class="sxs-lookup"><span data-stu-id="1e194-124">Used to distinguish progress reports of the same error report.</span></span>  <br/> |
|<span data-ttu-id="1e194-125">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="1e194-125">**MsDiagId**</span></span> <br/> |<span data-ttu-id="1e194-126">int</span><span class="sxs-lookup"><span data-stu-id="1e194-126">int</span></span>  <br/> |<span data-ttu-id="1e194-127">错误报告的诊断 ID。</span><span class="sxs-lookup"><span data-stu-id="1e194-127">Diagnostic ID for the error report.</span></span>  <br/> |
|<span data-ttu-id="1e194-128">**来源**</span><span class="sxs-lookup"><span data-stu-id="1e194-128">**Source**</span></span> <br/> |<span data-ttu-id="1e194-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1e194-129">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1e194-130">产生错误的服务器的名称 (如果报表是从服务器组件发送的)。</span><span class="sxs-lookup"><span data-stu-id="1e194-130">Name of server that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="1e194-131">**应用程序**</span><span class="sxs-lookup"><span data-stu-id="1e194-131">**Application**</span></span> <br/> |<span data-ttu-id="1e194-132">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1e194-132">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1e194-133">发出错误的应用程序的名称 (如果报表是从服务器组件发送的)。</span><span class="sxs-lookup"><span data-stu-id="1e194-133">Name of application that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="1e194-134">**TelemetryId**</span><span class="sxs-lookup"><span data-stu-id="1e194-134">**TelemetryId**</span></span> <br/> |<span data-ttu-id="1e194-135">标识符</span><span class="sxs-lookup"><span data-stu-id="1e194-135">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="1e194-136">关联会议中涉及的不同组件的加入时间信息的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="1e194-136">Unique identifier correlating join time information for the different components involved in a conference.</span></span>  <br/> |
|<span data-ttu-id="1e194-137">**SessionSetupTime**</span><span class="sxs-lookup"><span data-stu-id="1e194-137">**SessionSetupTime**</span></span> <br/> |<span data-ttu-id="1e194-138">int</span><span class="sxs-lookup"><span data-stu-id="1e194-138">int</span></span>  <br/> |<span data-ttu-id="1e194-139">特定组件加入会议所需的时间 (以毫秒为单位)。</span><span class="sxs-lookup"><span data-stu-id="1e194-139">Time (in milliseconds) required for a specific component to join a conference.</span></span>  <br/> |
|<span data-ttu-id="1e194-140">**MsDiagHeader**</span><span class="sxs-lookup"><span data-stu-id="1e194-140">**MsDiagHeader**</span></span> <br/> |<span data-ttu-id="1e194-141">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="1e194-141">varchar(max)</span></span>  <br/> |<span data-ttu-id="1e194-142">其他错误信息。</span><span class="sxs-lookup"><span data-stu-id="1e194-142">Additional error information.</span></span>  <br/> |
   

