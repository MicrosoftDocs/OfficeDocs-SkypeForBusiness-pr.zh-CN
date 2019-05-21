---
title: VideoClientEvent 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 每条记录包含视频呼叫中一个终结点的客户端事件。 通常, 一个通话有两个记录, 一个用于呼叫方, 另一个用于被呼叫方。
ms.openlocfilehash: b8e93206ea30622baa82adcec5ee9a80235521c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294549"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="0e394-104">VideoClientEvent 表</span><span class="sxs-lookup"><span data-stu-id="0e394-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="0e394-105">每条记录包含视频呼叫中一个终结点的客户端事件。</span><span class="sxs-lookup"><span data-stu-id="0e394-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="0e394-106">通常, 一个通话有两个记录, 一个用于呼叫方, 另一个用于被呼叫方。</span><span class="sxs-lookup"><span data-stu-id="0e394-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="0e394-107">**列**</span><span class="sxs-lookup"><span data-stu-id="0e394-107">**Column**</span></span>|<span data-ttu-id="0e394-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="0e394-108">**Data Type**</span></span>|<span data-ttu-id="0e394-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="0e394-109">**Key/Index**</span></span>|<span data-ttu-id="0e394-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="0e394-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0e394-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="0e394-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="0e394-112">datetime</span><span class="sxs-lookup"><span data-stu-id="0e394-112">datetime</span></span>  <br/> |<span data-ttu-id="0e394-113">Primary</span><span class="sxs-lookup"><span data-stu-id="0e394-113">Primary</span></span>  <br/> |<span data-ttu-id="0e394-114">从[MediaLine 表](medialine-0.md)中引用。</span><span class="sxs-lookup"><span data-stu-id="0e394-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="0e394-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="0e394-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="0e394-116">int</span><span class="sxs-lookup"><span data-stu-id="0e394-116">int</span></span>  <br/> |<span data-ttu-id="0e394-117">Primary</span><span class="sxs-lookup"><span data-stu-id="0e394-117">Primary</span></span>  <br/> |<span data-ttu-id="0e394-118">从[MediaLine 表](medialine-0.md)中引用。</span><span class="sxs-lookup"><span data-stu-id="0e394-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="0e394-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="0e394-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="0e394-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="0e394-120">tinyint</span></span>  <br/> |<span data-ttu-id="0e394-121">Primary</span><span class="sxs-lookup"><span data-stu-id="0e394-121">Primary</span></span>  <br/> |<span data-ttu-id="0e394-122">从[MediaLine 表](medialine-0.md)中引用。</span><span class="sxs-lookup"><span data-stu-id="0e394-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="0e394-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="0e394-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="0e394-124">bit</span><span class="sxs-lookup"><span data-stu-id="0e394-124">bit</span></span>  <br/> |<span data-ttu-id="0e394-125">Primary</span><span class="sxs-lookup"><span data-stu-id="0e394-125">Primary</span></span>  <br/> |<span data-ttu-id="0e394-126">0: 被调用方的数据</span><span class="sxs-lookup"><span data-stu-id="0e394-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="0e394-127">1: 调用方的数据</span><span class="sxs-lookup"><span data-stu-id="0e394-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="0e394-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="0e394-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="0e394-129">会话百分比为 "坏" 状态引发 LowBandwidth 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="0e394-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="0e394-130">可用带宽不足以获得可接受的语音体验。</span><span class="sxs-lookup"><span data-stu-id="0e394-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="0e394-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="0e394-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="0e394-132">会话百分比为 "坏" 状态引发 ReceiveSendQuality 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="0e394-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="0e394-133">"抖动" 或 "数据包丢失" 方面的网络质量非常严重, 影响接收音频的质量。</span><span class="sxs-lookup"><span data-stu-id="0e394-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

