---
title: IMReportSummary 表中的业务服务器 2015 Skype
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable 的即时消息会话保留在组织中提供的全面报告。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: fd907165f7db131e94d09d2b9a531eeb20812734
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213030"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="4e1be-104">IMReportSummary 表中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="4e1be-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="4e1be-105">IMReportSummaryTable 的即时消息会话保留在组织中提供的全面报告。</span><span class="sxs-lookup"><span data-stu-id="4e1be-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="4e1be-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="4e1be-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="4e1be-107">**列**</span><span class="sxs-lookup"><span data-stu-id="4e1be-107">**Column**</span></span>|<span data-ttu-id="4e1be-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="4e1be-108">**Data Type**</span></span>|<span data-ttu-id="4e1be-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="4e1be-109">**Key/Index**</span></span>|<span data-ttu-id="4e1be-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="4e1be-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4e1be-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="4e1be-111">**StartTime**</span></span> <br/> |<span data-ttu-id="4e1be-112">datetime</span><span class="sxs-lookup"><span data-stu-id="4e1be-112">datetime</span></span>  <br/> |<span data-ttu-id="4e1be-113">Primary</span><span class="sxs-lookup"><span data-stu-id="4e1be-113">Primary</span></span>  <br/> |<span data-ttu-id="4e1be-114">日期和即时消息会话开始的时间。</span><span class="sxs-lookup"><span data-stu-id="4e1be-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="4e1be-115">**时间段**</span><span class="sxs-lookup"><span data-stu-id="4e1be-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="4e1be-116">char （1)</span><span class="sxs-lookup"><span data-stu-id="4e1be-116">char(1)</span></span>  <br/> |<span data-ttu-id="4e1be-117">Primary</span><span class="sxs-lookup"><span data-stu-id="4e1be-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="4e1be-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="4e1be-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="4e1be-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="4e1be-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="4e1be-120">Primary</span><span class="sxs-lookup"><span data-stu-id="4e1be-120">Primary</span></span>  <br/> |<span data-ttu-id="4e1be-121">承载会话的池的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="4e1be-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="4e1be-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="4e1be-122">**AuthType**</span></span> <br/> |<span data-ttu-id="4e1be-123">int</span><span class="sxs-lookup"><span data-stu-id="4e1be-123">int</span></span>  <br/> |<span data-ttu-id="4e1be-124">Primary</span><span class="sxs-lookup"><span data-stu-id="4e1be-124">Primary</span></span>  <br/> |<span data-ttu-id="4e1be-125">呼叫的优先级 （例如，紧急或非紧迫）。</span><span class="sxs-lookup"><span data-stu-id="4e1be-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="4e1be-126">优先级信息存储[中的业务服务器 2015 Skype CallPriorities 表](callpriorities.md)中。</span><span class="sxs-lookup"><span data-stu-id="4e1be-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="4e1be-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="4e1be-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="4e1be-128">bigint</span><span class="sxs-lookup"><span data-stu-id="4e1be-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="4e1be-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="4e1be-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="4e1be-130">bigint</span><span class="sxs-lookup"><span data-stu-id="4e1be-130">bigint</span></span>  <br/> ||<span data-ttu-id="4e1be-131">在会话期间交换的即时消息的总数。</span><span class="sxs-lookup"><span data-stu-id="4e1be-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

