---
title: TraceRoute 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: TraceRoute 表包含来自呼叫的路由信息。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: e257bf6d89d04cd0f4784e62e7ac2876b6ede7e5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805110"
---
# <a name="traceroute-table"></a><span data-ttu-id="a25d7-104">TraceRoute 表</span><span class="sxs-lookup"><span data-stu-id="a25d7-104">TraceRoute table</span></span>
 
<span data-ttu-id="a25d7-105">TraceRoute 表包含来自呼叫的路由信息。</span><span class="sxs-lookup"><span data-stu-id="a25d7-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="a25d7-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="a25d7-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="a25d7-107">**列**</span><span class="sxs-lookup"><span data-stu-id="a25d7-107">**Column**</span></span>|<span data-ttu-id="a25d7-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="a25d7-108">**Data Type**</span></span>|<span data-ttu-id="a25d7-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="a25d7-109">**Key/Index**</span></span>|<span data-ttu-id="a25d7-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="a25d7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a25d7-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="a25d7-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="a25d7-112">datetime</span><span class="sxs-lookup"><span data-stu-id="a25d7-112">datetime</span></span>  <br/> |<span data-ttu-id="a25d7-113">主、外部</span><span class="sxs-lookup"><span data-stu-id="a25d7-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="a25d7-114">通话开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="a25d7-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="a25d7-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="a25d7-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="a25d7-116">int</span><span class="sxs-lookup"><span data-stu-id="a25d7-116">int</span></span>  <br/> |<span data-ttu-id="a25d7-117">主、外部</span><span class="sxs-lookup"><span data-stu-id="a25d7-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="a25d7-118">用于区分可能在同一日期和同一时间开始的多个通话的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="a25d7-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="a25d7-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="a25d7-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="a25d7-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="a25d7-120">tinyint</span></span>  <br/> |<span data-ttu-id="a25d7-121">主、外部</span><span class="sxs-lookup"><span data-stu-id="a25d7-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="a25d7-122">表示通话中使用的视频线路类型。</span><span class="sxs-lookup"><span data-stu-id="a25d7-122">Represents the type of video line used in the call.</span></span> <span data-ttu-id="a25d7-123">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="a25d7-123">Allowed values are:</span></span>  <br/> <span data-ttu-id="a25d7-124">0-音频</span><span class="sxs-lookup"><span data-stu-id="a25d7-124">0 - Audio</span></span>  <br/> <span data-ttu-id="a25d7-125">1-视频</span><span class="sxs-lookup"><span data-stu-id="a25d7-125">1 - Video</span></span>  <br/> <span data-ttu-id="a25d7-126">2全景视频</span><span class="sxs-lookup"><span data-stu-id="a25d7-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="a25d7-127">3-应用程序/桌面共享</span><span class="sxs-lookup"><span data-stu-id="a25d7-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="a25d7-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="a25d7-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="a25d7-129">bit</span><span class="sxs-lookup"><span data-stu-id="a25d7-129">bit</span></span>  <br/> |<span data-ttu-id="a25d7-130">Primary</span><span class="sxs-lookup"><span data-stu-id="a25d7-130">Primary</span></span>  <br/> |<span data-ttu-id="a25d7-131">发出呼叫的终结点。</span><span class="sxs-lookup"><span data-stu-id="a25d7-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="a25d7-132">**跳**</span><span class="sxs-lookup"><span data-stu-id="a25d7-132">**Hop**</span></span> <br/> |<span data-ttu-id="a25d7-133">int</span><span class="sxs-lookup"><span data-stu-id="a25d7-133">int</span></span>  <br/> ||<span data-ttu-id="a25d7-134">网络跃点/</span><span class="sxs-lookup"><span data-stu-id="a25d7-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="a25d7-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="a25d7-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="a25d7-136">int</span><span class="sxs-lookup"><span data-stu-id="a25d7-136">int</span></span>  <br/> |<span data-ttu-id="a25d7-137">外表</span><span class="sxs-lookup"><span data-stu-id="a25d7-137">Foreign</span></span>  <br/> |<span data-ttu-id="a25d7-138">IP 地址的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="a25d7-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="a25d7-139">IP 地址信息存储在 "ip 地址"[表](ipaddress.md)中。</span><span class="sxs-lookup"><span data-stu-id="a25d7-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="a25d7-140">**RTT**</span><span class="sxs-lookup"><span data-stu-id="a25d7-140">**RTT**</span></span> <br/> |<span data-ttu-id="a25d7-141">int</span><span class="sxs-lookup"><span data-stu-id="a25d7-141">int</span></span>  <br/> ||<span data-ttu-id="a25d7-142">往返时间。</span><span class="sxs-lookup"><span data-stu-id="a25d7-142">Roundtrip time.</span></span> <span data-ttu-id="a25d7-143">往返时间测量语音数据包到达其目标所需的时间量，然后发送发送回收到通知的时间。</span><span class="sxs-lookup"><span data-stu-id="a25d7-143">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

