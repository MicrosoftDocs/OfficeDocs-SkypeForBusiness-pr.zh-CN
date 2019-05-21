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
localization_priority: Normal
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: TraceRoute 表包含来自呼叫的路由信息。 此表是在 Microsoft Lync Server 2013 中引入的。
ms.openlocfilehash: 323f8160e7543c2fa08bebe9d1805355469acfd9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294626"
---
# <a name="traceroute-table"></a><span data-ttu-id="38974-104">TraceRoute 表</span><span class="sxs-lookup"><span data-stu-id="38974-104">TraceRoute table</span></span>
 
<span data-ttu-id="38974-105">TraceRoute 表包含来自呼叫的路由信息。</span><span class="sxs-lookup"><span data-stu-id="38974-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="38974-106">此表是在 Microsoft Lync Server 2013 中引入的。</span><span class="sxs-lookup"><span data-stu-id="38974-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="38974-107">**列**</span><span class="sxs-lookup"><span data-stu-id="38974-107">**Column**</span></span>|<span data-ttu-id="38974-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="38974-108">**Data Type**</span></span>|<span data-ttu-id="38974-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="38974-109">**Key/Index**</span></span>|<span data-ttu-id="38974-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="38974-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="38974-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="38974-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="38974-112">datetime</span><span class="sxs-lookup"><span data-stu-id="38974-112">datetime</span></span>  <br/> |<span data-ttu-id="38974-113">主、外部</span><span class="sxs-lookup"><span data-stu-id="38974-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="38974-114">通话开始的日期和时间。</span><span class="sxs-lookup"><span data-stu-id="38974-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="38974-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="38974-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="38974-116">int</span><span class="sxs-lookup"><span data-stu-id="38974-116">int</span></span>  <br/> |<span data-ttu-id="38974-117">主、外部</span><span class="sxs-lookup"><span data-stu-id="38974-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="38974-118">用于区分可能在同一日期和同一时间开始的多个通话的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="38974-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="38974-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="38974-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="38974-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="38974-120">tinyint</span></span>  <br/> |<span data-ttu-id="38974-121">主、外部</span><span class="sxs-lookup"><span data-stu-id="38974-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="38974-122">表示通话中使用的视频线路类型。</span><span class="sxs-lookup"><span data-stu-id="38974-122">Represents the type of video line used in the call.</span></span> <span data-ttu-id="38974-123">允许的值包括：</span><span class="sxs-lookup"><span data-stu-id="38974-123">Allowed values are:</span></span>  <br/> <span data-ttu-id="38974-124">0-音频</span><span class="sxs-lookup"><span data-stu-id="38974-124">0 - Audio</span></span>  <br/> <span data-ttu-id="38974-125">1-视频</span><span class="sxs-lookup"><span data-stu-id="38974-125">1 - Video</span></span>  <br/> <span data-ttu-id="38974-126">2全景视频</span><span class="sxs-lookup"><span data-stu-id="38974-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="38974-127">3-应用程序/桌面共享</span><span class="sxs-lookup"><span data-stu-id="38974-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="38974-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="38974-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="38974-129">bit</span><span class="sxs-lookup"><span data-stu-id="38974-129">bit</span></span>  <br/> |<span data-ttu-id="38974-130">Primary</span><span class="sxs-lookup"><span data-stu-id="38974-130">Primary</span></span>  <br/> |<span data-ttu-id="38974-131">发出呼叫的终结点。</span><span class="sxs-lookup"><span data-stu-id="38974-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="38974-132">**跳**</span><span class="sxs-lookup"><span data-stu-id="38974-132">**Hop**</span></span> <br/> |<span data-ttu-id="38974-133">int</span><span class="sxs-lookup"><span data-stu-id="38974-133">int</span></span>  <br/> ||<span data-ttu-id="38974-134">网络跃点/</span><span class="sxs-lookup"><span data-stu-id="38974-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="38974-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="38974-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="38974-136">int</span><span class="sxs-lookup"><span data-stu-id="38974-136">int</span></span>  <br/> |<span data-ttu-id="38974-137">外表</span><span class="sxs-lookup"><span data-stu-id="38974-137">Foreign</span></span>  <br/> |<span data-ttu-id="38974-138">IP 地址的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="38974-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="38974-139">IP 地址信息存储在 "ip 地址"[表](ipaddress.md)中。</span><span class="sxs-lookup"><span data-stu-id="38974-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="38974-140">**RTT**</span><span class="sxs-lookup"><span data-stu-id="38974-140">**RTT**</span></span> <br/> |<span data-ttu-id="38974-141">int</span><span class="sxs-lookup"><span data-stu-id="38974-141">int</span></span>  <br/> ||<span data-ttu-id="38974-142">往返时间。</span><span class="sxs-lookup"><span data-stu-id="38974-142">Roundtrip time.</span></span> <span data-ttu-id="38974-143">往返时间测量语音数据包到达其目标所需的时间量, 然后发送发送回收到通知的时间。</span><span class="sxs-lookup"><span data-stu-id="38974-143">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

