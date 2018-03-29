---
title: 路由追踪表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: 路由追踪表包含来自呼叫路由信息。 在 Microsoft Lync Server 2013 引入了此表。
ms.openlocfilehash: e8796b164bd6a0f2809025b784ada9d12dda449b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="traceroute-table"></a><span data-ttu-id="fec11-104">路由追踪表</span><span class="sxs-lookup"><span data-stu-id="fec11-104">TraceRoute table</span></span>
 
<span data-ttu-id="fec11-105">路由追踪表包含来自呼叫路由信息。</span><span class="sxs-lookup"><span data-stu-id="fec11-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="fec11-106">在 Microsoft Lync Server 2013 引入了此表。</span><span class="sxs-lookup"><span data-stu-id="fec11-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="fec11-107">**列**</span><span class="sxs-lookup"><span data-stu-id="fec11-107">**Column**</span></span>|<span data-ttu-id="fec11-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="fec11-108">**Data Type**</span></span>|<span data-ttu-id="fec11-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="fec11-109">**Key/Index**</span></span>|<span data-ttu-id="fec11-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="fec11-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fec11-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="fec11-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="fec11-112">datetime</span><span class="sxs-lookup"><span data-stu-id="fec11-112">datetime</span></span>  <br/> |<span data-ttu-id="fec11-113">主键和外</span><span class="sxs-lookup"><span data-stu-id="fec11-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="fec11-114">日期和时间的呼叫开始。</span><span class="sxs-lookup"><span data-stu-id="fec11-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="fec11-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="fec11-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="fec11-116">int</span><span class="sxs-lookup"><span data-stu-id="fec11-116">int</span></span>  <br/> |<span data-ttu-id="fec11-117">主键和外</span><span class="sxs-lookup"><span data-stu-id="fec11-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="fec11-118">用来区分可能在同一日期，在同一时间开始的多个调用的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="fec11-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="fec11-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="fec11-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="fec11-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="fec11-120">tinyint</span></span>  <br/> |<span data-ttu-id="fec11-121">主键和外</span><span class="sxs-lookup"><span data-stu-id="fec11-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="fec11-122">表示在调用中使用的视频线的类型。</span><span class="sxs-lookup"><span data-stu-id="fec11-122">Represents the type of video line used in the call.</span></span> <span data-ttu-id="fec11-123">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="fec11-123">Allowed values are:</span></span>  <br/> <span data-ttu-id="fec11-124">0-音频</span><span class="sxs-lookup"><span data-stu-id="fec11-124">0 - Audio</span></span>  <br/> <span data-ttu-id="fec11-125">1-视频</span><span class="sxs-lookup"><span data-stu-id="fec11-125">1 - Video</span></span>  <br/> <span data-ttu-id="fec11-126">2-全景视频</span><span class="sxs-lookup"><span data-stu-id="fec11-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="fec11-127">3/桌面应用程序共享</span><span class="sxs-lookup"><span data-stu-id="fec11-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="fec11-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="fec11-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="fec11-129">bit</span><span class="sxs-lookup"><span data-stu-id="fec11-129">bit</span></span>  <br/> |<span data-ttu-id="fec11-130">Primary</span><span class="sxs-lookup"><span data-stu-id="fec11-130">Primary</span></span>  <br/> |<span data-ttu-id="fec11-131">将调用的终结点。</span><span class="sxs-lookup"><span data-stu-id="fec11-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="fec11-132">**跃点**</span><span class="sxs-lookup"><span data-stu-id="fec11-132">**Hop**</span></span> <br/> |<span data-ttu-id="fec11-133">int</span><span class="sxs-lookup"><span data-stu-id="fec11-133">int</span></span>  <br/> ||<span data-ttu-id="fec11-134">网络跃点 /</span><span class="sxs-lookup"><span data-stu-id="fec11-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="fec11-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="fec11-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="fec11-136">int</span><span class="sxs-lookup"><span data-stu-id="fec11-136">int</span></span>  <br/> |<span data-ttu-id="fec11-137">外</span><span class="sxs-lookup"><span data-stu-id="fec11-137">Foreign</span></span>  <br/> |<span data-ttu-id="fec11-138">IP 地址的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="fec11-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="fec11-139">[Ip 地址表](ipaddress.md)中存储 IP 地址信息。</span><span class="sxs-lookup"><span data-stu-id="fec11-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="fec11-140">**RTT**</span><span class="sxs-lookup"><span data-stu-id="fec11-140">**RTT**</span></span> <br/> |<span data-ttu-id="fec11-141">int</span><span class="sxs-lookup"><span data-stu-id="fec11-141">int</span></span>  <br/> ||<span data-ttu-id="fec11-142">往返时间。</span><span class="sxs-lookup"><span data-stu-id="fec11-142">Roundtrip time.</span></span> <span data-ttu-id="fec11-143">往返时间测量的语音数据包到达其目的地，然后发送回通知已被接收所花费的时间。</span><span class="sxs-lookup"><span data-stu-id="fec11-143">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

