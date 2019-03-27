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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881020"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="a7603-104">IMReportSummary 表中的业务服务器 2015 Skype</span><span class="sxs-lookup"><span data-stu-id="a7603-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a7603-105">IMReportSummaryTable 的即时消息会话保留在组织中提供的全面报告。</span><span class="sxs-lookup"><span data-stu-id="a7603-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="a7603-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="a7603-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="a7603-107">**列**</span><span class="sxs-lookup"><span data-stu-id="a7603-107">**Column**</span></span>|<span data-ttu-id="a7603-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a7603-108">**Data Type**</span></span>|<span data-ttu-id="a7603-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="a7603-109">**Key/Index**</span></span>|<span data-ttu-id="a7603-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="a7603-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a7603-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="a7603-111">**StartTime**</span></span> <br/> |<span data-ttu-id="a7603-112">datetime</span><span class="sxs-lookup"><span data-stu-id="a7603-112">datetime</span></span>  <br/> |<span data-ttu-id="a7603-113">Primary</span><span class="sxs-lookup"><span data-stu-id="a7603-113">Primary</span></span>  <br/> |<span data-ttu-id="a7603-114">日期和即时消息会话开始的时间。</span><span class="sxs-lookup"><span data-stu-id="a7603-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="a7603-115">**时间段**</span><span class="sxs-lookup"><span data-stu-id="a7603-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="a7603-116">char （1)</span><span class="sxs-lookup"><span data-stu-id="a7603-116">char(1)</span></span>  <br/> |<span data-ttu-id="a7603-117">Primary</span><span class="sxs-lookup"><span data-stu-id="a7603-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="a7603-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="a7603-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="a7603-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="a7603-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="a7603-120">Primary</span><span class="sxs-lookup"><span data-stu-id="a7603-120">Primary</span></span>  <br/> |<span data-ttu-id="a7603-121">承载会话的池的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="a7603-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="a7603-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="a7603-122">**AuthType**</span></span> <br/> |<span data-ttu-id="a7603-123">int</span><span class="sxs-lookup"><span data-stu-id="a7603-123">int</span></span>  <br/> |<span data-ttu-id="a7603-124">Primary</span><span class="sxs-lookup"><span data-stu-id="a7603-124">Primary</span></span>  <br/> |<span data-ttu-id="a7603-125">呼叫的优先级 （例如，紧急或非紧迫）。</span><span class="sxs-lookup"><span data-stu-id="a7603-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="a7603-126">优先级信息存储[中的业务服务器 2015 Skype CallPriorities 表](callpriorities.md)中。</span><span class="sxs-lookup"><span data-stu-id="a7603-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="a7603-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="a7603-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="a7603-128">bigint</span><span class="sxs-lookup"><span data-stu-id="a7603-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="a7603-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="a7603-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="a7603-130">bigint</span><span class="sxs-lookup"><span data-stu-id="a7603-130">bigint</span></span>  <br/> ||<span data-ttu-id="a7603-131">在会话期间交换的即时消息的总数。</span><span class="sxs-lookup"><span data-stu-id="a7603-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

