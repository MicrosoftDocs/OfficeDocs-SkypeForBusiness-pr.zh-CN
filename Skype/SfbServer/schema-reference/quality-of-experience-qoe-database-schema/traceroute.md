---
title: TraceRoute 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: TraceRoute 表包含来自呼叫路由信息。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 741eaabbe94ee1849bd5a7d5e516714861658d7e
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212072"
---
# <a name="traceroute-table"></a><span data-ttu-id="5f154-104">TraceRoute 表</span><span class="sxs-lookup"><span data-stu-id="5f154-104">TraceRoute table</span></span>
 
<span data-ttu-id="5f154-105">TraceRoute 表包含来自呼叫路由信息。</span><span class="sxs-lookup"><span data-stu-id="5f154-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="5f154-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="5f154-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="5f154-107">**列**</span><span class="sxs-lookup"><span data-stu-id="5f154-107">**Column**</span></span>|<span data-ttu-id="5f154-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="5f154-108">**Data Type**</span></span>|<span data-ttu-id="5f154-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="5f154-109">**Key/Index**</span></span>|<span data-ttu-id="5f154-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="5f154-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5f154-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="5f154-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="5f154-112">datetime</span><span class="sxs-lookup"><span data-stu-id="5f154-112">datetime</span></span>  <br/> |<span data-ttu-id="5f154-113">主、 外</span><span class="sxs-lookup"><span data-stu-id="5f154-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="5f154-114">日期和呼叫开始的时间。</span><span class="sxs-lookup"><span data-stu-id="5f154-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="5f154-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="5f154-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="5f154-116">int</span><span class="sxs-lookup"><span data-stu-id="5f154-116">int</span></span>  <br/> |<span data-ttu-id="5f154-117">主、 外</span><span class="sxs-lookup"><span data-stu-id="5f154-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="5f154-118">用来区分可能在相同日期和相同时间开始的多个呼叫的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="5f154-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="5f154-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="5f154-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="5f154-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="5f154-120">tinyint</span></span>  <br/> |<span data-ttu-id="5f154-121">主、 外</span><span class="sxs-lookup"><span data-stu-id="5f154-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="5f154-122">代表在呼叫中使用的视频线的类型。</span><span class="sxs-lookup"><span data-stu-id="5f154-122">Represents the type of video line used in the call.</span></span> <span data-ttu-id="5f154-123">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="5f154-123">Allowed values are:</span></span>  <br/> <span data-ttu-id="5f154-124">0-音频</span><span class="sxs-lookup"><span data-stu-id="5f154-124">0 - Audio</span></span>  <br/> <span data-ttu-id="5f154-125">1-视频</span><span class="sxs-lookup"><span data-stu-id="5f154-125">1 - Video</span></span>  <br/> <span data-ttu-id="5f154-126">2-全景视频</span><span class="sxs-lookup"><span data-stu-id="5f154-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="5f154-127">3-应用程序/桌面共享</span><span class="sxs-lookup"><span data-stu-id="5f154-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="5f154-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="5f154-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="5f154-129">bit</span><span class="sxs-lookup"><span data-stu-id="5f154-129">bit</span></span>  <br/> |<span data-ttu-id="5f154-130">Primary</span><span class="sxs-lookup"><span data-stu-id="5f154-130">Primary</span></span>  <br/> |<span data-ttu-id="5f154-131">发出呼叫的终结点。</span><span class="sxs-lookup"><span data-stu-id="5f154-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="5f154-132">**跃点**</span><span class="sxs-lookup"><span data-stu-id="5f154-132">**Hop**</span></span> <br/> |<span data-ttu-id="5f154-133">int</span><span class="sxs-lookup"><span data-stu-id="5f154-133">int</span></span>  <br/> ||<span data-ttu-id="5f154-134">网络跃点 /</span><span class="sxs-lookup"><span data-stu-id="5f154-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="5f154-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="5f154-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="5f154-136">int</span><span class="sxs-lookup"><span data-stu-id="5f154-136">int</span></span>  <br/> |<span data-ttu-id="5f154-137">外</span><span class="sxs-lookup"><span data-stu-id="5f154-137">Foreign</span></span>  <br/> |<span data-ttu-id="5f154-138">IP 地址的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="5f154-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="5f154-139">[IPAddress 表](ipaddress.md)中存储的 IP 地址信息。</span><span class="sxs-lookup"><span data-stu-id="5f154-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="5f154-140">**RTT**</span><span class="sxs-lookup"><span data-stu-id="5f154-140">**RTT**</span></span> <br/> |<span data-ttu-id="5f154-141">int</span><span class="sxs-lookup"><span data-stu-id="5f154-141">int</span></span>  <br/> ||<span data-ttu-id="5f154-142">往返时间。</span><span class="sxs-lookup"><span data-stu-id="5f154-142">Roundtrip time.</span></span> <span data-ttu-id="5f154-143">往返时间度量语音数据包可以到达其目标，然后发送后已被接收的通知所需的时间量。</span><span class="sxs-lookup"><span data-stu-id="5f154-143">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

