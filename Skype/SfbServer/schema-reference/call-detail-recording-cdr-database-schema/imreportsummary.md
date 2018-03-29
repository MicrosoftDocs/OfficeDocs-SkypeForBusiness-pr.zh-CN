---
title: 在业务服务器 2015年的 Skype 的 IMReportSummary 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable 提供即时消息会话保存在一个组织的总体报告。 在 Microsoft Lync Server 2013 引入了此表。
ms.openlocfilehash: f716a7406f4cf3562e2fa9244e8a766ef8537f53
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="025cb-104">在业务服务器 2015年的 Skype 的 IMReportSummary 表</span><span class="sxs-lookup"><span data-stu-id="025cb-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="025cb-105">IMReportSummaryTable 提供即时消息会话保存在一个组织的总体报告。</span><span class="sxs-lookup"><span data-stu-id="025cb-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="025cb-106">在 Microsoft Lync Server 2013 引入了此表。</span><span class="sxs-lookup"><span data-stu-id="025cb-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="025cb-107">**列**</span><span class="sxs-lookup"><span data-stu-id="025cb-107">**Column**</span></span>|<span data-ttu-id="025cb-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="025cb-108">**Data Type**</span></span>|<span data-ttu-id="025cb-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="025cb-109">**Key/Index**</span></span>|<span data-ttu-id="025cb-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="025cb-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="025cb-111">**开始时间**</span><span class="sxs-lookup"><span data-stu-id="025cb-111">**StartTime**</span></span> <br/> |<span data-ttu-id="025cb-112">datetime</span><span class="sxs-lookup"><span data-stu-id="025cb-112">datetime</span></span>  <br/> |<span data-ttu-id="025cb-113">Primary</span><span class="sxs-lookup"><span data-stu-id="025cb-113">Primary</span></span>  <br/> |<span data-ttu-id="025cb-114">日期和即时消息会话开始的时间。</span><span class="sxs-lookup"><span data-stu-id="025cb-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="025cb-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="025cb-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="025cb-116">char （1)</span><span class="sxs-lookup"><span data-stu-id="025cb-116">char(1)</span></span>  <br/> |<span data-ttu-id="025cb-117">Primary</span><span class="sxs-lookup"><span data-stu-id="025cb-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="025cb-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="025cb-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="025cb-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="025cb-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="025cb-120">Primary</span><span class="sxs-lookup"><span data-stu-id="025cb-120">Primary</span></span>  <br/> |<span data-ttu-id="025cb-121">发起会话池的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="025cb-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="025cb-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="025cb-122">**AuthType**</span></span> <br/> |<span data-ttu-id="025cb-123">int</span><span class="sxs-lookup"><span data-stu-id="025cb-123">int</span></span>  <br/> |<span data-ttu-id="025cb-124">Primary</span><span class="sxs-lookup"><span data-stu-id="025cb-124">Primary</span></span>  <br/> |<span data-ttu-id="025cb-125">调用的 （例如，紧急或非紧急） 优先级。</span><span class="sxs-lookup"><span data-stu-id="025cb-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="025cb-126">优先级信息存储[在业务服务器 2015年的 Skype 的 CallPriorities 表](callpriorities.md)中。</span><span class="sxs-lookup"><span data-stu-id="025cb-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="025cb-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="025cb-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="025cb-128">bigint</span><span class="sxs-lookup"><span data-stu-id="025cb-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="025cb-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="025cb-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="025cb-130">bigint</span><span class="sxs-lookup"><span data-stu-id="025cb-130">bigint</span></span>  <br/> ||<span data-ttu-id="025cb-131">在会话期间交换的即时消息总数。</span><span class="sxs-lookup"><span data-stu-id="025cb-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

