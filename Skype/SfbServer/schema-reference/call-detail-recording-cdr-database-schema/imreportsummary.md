---
title: Skype for Business Server 2015 中的 IMReportSummary 表
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
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable 提供有关组织中进行的即时消息会话的总体报告。 此表在 Microsoft Lync Server 2013 中引入。
ms.openlocfilehash: 6a80918376440c13d60e059744d88c09c2705853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821522"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="b54c2-104">Skype for Business Server 2015 中的 IMReportSummary 表</span><span class="sxs-lookup"><span data-stu-id="b54c2-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="b54c2-105">IMReportSummaryTable 提供有关组织中进行的即时消息会话的总体报告。</span><span class="sxs-lookup"><span data-stu-id="b54c2-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="b54c2-106">此表在 Microsoft Lync Server 2013 中引入。</span><span class="sxs-lookup"><span data-stu-id="b54c2-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="b54c2-107">**列**</span><span class="sxs-lookup"><span data-stu-id="b54c2-107">**Column**</span></span>|<span data-ttu-id="b54c2-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="b54c2-108">**Data Type**</span></span>|<span data-ttu-id="b54c2-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="b54c2-109">**Key/Index**</span></span>|<span data-ttu-id="b54c2-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="b54c2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b54c2-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="b54c2-111">**StartTime**</span></span> <br/> |<span data-ttu-id="b54c2-112">datetime</span><span class="sxs-lookup"><span data-stu-id="b54c2-112">datetime</span></span>  <br/> |<span data-ttu-id="b54c2-113">主</span><span class="sxs-lookup"><span data-stu-id="b54c2-113">Primary</span></span>  <br/> |<span data-ttu-id="b54c2-114">即时消息会话开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="b54c2-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="b54c2-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="b54c2-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="b54c2-116">char (1) </span><span class="sxs-lookup"><span data-stu-id="b54c2-116">char(1)</span></span>  <br/> |<span data-ttu-id="b54c2-117">主</span><span class="sxs-lookup"><span data-stu-id="b54c2-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="b54c2-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="b54c2-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="b54c2-119">nvarchar (257) </span><span class="sxs-lookup"><span data-stu-id="b54c2-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="b54c2-120">主</span><span class="sxs-lookup"><span data-stu-id="b54c2-120">Primary</span></span>  <br/> |<span data-ttu-id="b54c2-121">承载会话的池的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="b54c2-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="b54c2-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="b54c2-122">**AuthType**</span></span> <br/> |<span data-ttu-id="b54c2-123">int</span><span class="sxs-lookup"><span data-stu-id="b54c2-123">int</span></span>  <br/> |<span data-ttu-id="b54c2-124">主</span><span class="sxs-lookup"><span data-stu-id="b54c2-124">Primary</span></span>  <br/> |<span data-ttu-id="b54c2-125">呼叫的优先级（例如，紧急或非紧急）。</span><span class="sxs-lookup"><span data-stu-id="b54c2-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="b54c2-126">优先级信息存储在 [Skype for Business Server 2015 中的 CallPriorities](callpriorities.md)表中。</span><span class="sxs-lookup"><span data-stu-id="b54c2-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="b54c2-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="b54c2-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="b54c2-128">bigint</span><span class="sxs-lookup"><span data-stu-id="b54c2-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="b54c2-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="b54c2-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="b54c2-130">bigint</span><span class="sxs-lookup"><span data-stu-id="b54c2-130">bigint</span></span>  <br/> ||<span data-ttu-id="b54c2-131">会话期间交换的即时消息总数。</span><span class="sxs-lookup"><span data-stu-id="b54c2-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

