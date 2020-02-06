---
title: Skype for Business Server 2015 中的 IMReportSummary 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable 提供组织中的即时消息会话的整体报告。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: f845a882bb8bd6ba5ca434ffc42a34725cfeac51
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815140"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="7addd-104">Skype for Business Server 2015 中的 IMReportSummary 表</span><span class="sxs-lookup"><span data-stu-id="7addd-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7addd-105">IMReportSummaryTable 提供组织中的即时消息会话的整体报告。</span><span class="sxs-lookup"><span data-stu-id="7addd-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="7addd-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="7addd-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="7addd-107">**列**</span><span class="sxs-lookup"><span data-stu-id="7addd-107">**Column**</span></span>|<span data-ttu-id="7addd-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="7addd-108">**Data Type**</span></span>|<span data-ttu-id="7addd-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="7addd-109">**Key/Index**</span></span>|<span data-ttu-id="7addd-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="7addd-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7addd-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="7addd-111">**StartTime**</span></span> <br/> |<span data-ttu-id="7addd-112">datetime</span><span class="sxs-lookup"><span data-stu-id="7addd-112">datetime</span></span>  <br/> |<span data-ttu-id="7addd-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7addd-113">Primary</span></span>  <br/> |<span data-ttu-id="7addd-114">即时消息会话开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="7addd-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="7addd-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="7addd-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="7addd-116">char （1）</span><span class="sxs-lookup"><span data-stu-id="7addd-116">char(1)</span></span>  <br/> |<span data-ttu-id="7addd-117">Primary</span><span class="sxs-lookup"><span data-stu-id="7addd-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="7addd-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="7addd-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="7addd-119">nvarchar （257）</span><span class="sxs-lookup"><span data-stu-id="7addd-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="7addd-120">Primary</span><span class="sxs-lookup"><span data-stu-id="7addd-120">Primary</span></span>  <br/> |<span data-ttu-id="7addd-121">托管会话的池的完全限定的域名。</span><span class="sxs-lookup"><span data-stu-id="7addd-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="7addd-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="7addd-122">**AuthType**</span></span> <br/> |<span data-ttu-id="7addd-123">int</span><span class="sxs-lookup"><span data-stu-id="7addd-123">int</span></span>  <br/> |<span data-ttu-id="7addd-124">Primary</span><span class="sxs-lookup"><span data-stu-id="7addd-124">Primary</span></span>  <br/> |<span data-ttu-id="7addd-125">通话的优先级（例如，紧急或非紧急）。</span><span class="sxs-lookup"><span data-stu-id="7addd-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="7addd-126">优先级信息存储在[Skype For Business Server 2015 的 CallPriorities 表中](callpriorities.md)。</span><span class="sxs-lookup"><span data-stu-id="7addd-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="7addd-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="7addd-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="7addd-128">bigint</span><span class="sxs-lookup"><span data-stu-id="7addd-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="7addd-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="7addd-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="7addd-130">bigint</span><span class="sxs-lookup"><span data-stu-id="7addd-130">bigint</span></span>  <br/> ||<span data-ttu-id="7addd-131">会话期间交换的即时消息总数。</span><span class="sxs-lookup"><span data-stu-id="7addd-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

