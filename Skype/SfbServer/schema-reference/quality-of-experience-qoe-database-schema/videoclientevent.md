---
title: VideoClientEvent 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 每个记录包含在视频呼叫的一个端点的客户端事件。 通常，一次调用具有两个记录，一个用于呼叫者，一个用于被叫方。
ms.openlocfilehash: 314e4df9313a3d111d71b6eaa06565edcbb765d1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891235"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="9d382-104">VideoClientEvent 表</span><span class="sxs-lookup"><span data-stu-id="9d382-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="9d382-105">每个记录包含在视频呼叫的一个端点的客户端事件。</span><span class="sxs-lookup"><span data-stu-id="9d382-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="9d382-106">通常，一次调用具有两个记录，一个用于呼叫者，一个用于被叫方。</span><span class="sxs-lookup"><span data-stu-id="9d382-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="9d382-107">**列**</span><span class="sxs-lookup"><span data-stu-id="9d382-107">**Column**</span></span>|<span data-ttu-id="9d382-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="9d382-108">**Data Type**</span></span>|<span data-ttu-id="9d382-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="9d382-109">**Key/Index**</span></span>|<span data-ttu-id="9d382-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="9d382-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9d382-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="9d382-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="9d382-112">datetime</span><span class="sxs-lookup"><span data-stu-id="9d382-112">datetime</span></span>  <br/> |<span data-ttu-id="9d382-113">Primary</span><span class="sxs-lookup"><span data-stu-id="9d382-113">Primary</span></span>  <br/> |<span data-ttu-id="9d382-114">引用[自 MediaLine table](medialine-0.md)。</span><span class="sxs-lookup"><span data-stu-id="9d382-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="9d382-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="9d382-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="9d382-116">int</span><span class="sxs-lookup"><span data-stu-id="9d382-116">int</span></span>  <br/> |<span data-ttu-id="9d382-117">Primary</span><span class="sxs-lookup"><span data-stu-id="9d382-117">Primary</span></span>  <br/> |<span data-ttu-id="9d382-118">引用[自 MediaLine table](medialine-0.md)。</span><span class="sxs-lookup"><span data-stu-id="9d382-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="9d382-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="9d382-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="9d382-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="9d382-120">tinyint</span></span>  <br/> |<span data-ttu-id="9d382-121">Primary</span><span class="sxs-lookup"><span data-stu-id="9d382-121">Primary</span></span>  <br/> |<span data-ttu-id="9d382-122">引用[自 MediaLine table](medialine-0.md)。</span><span class="sxs-lookup"><span data-stu-id="9d382-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="9d382-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="9d382-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="9d382-124">bit</span><span class="sxs-lookup"><span data-stu-id="9d382-124">bit</span></span>  <br/> |<span data-ttu-id="9d382-125">Primary</span><span class="sxs-lookup"><span data-stu-id="9d382-125">Primary</span></span>  <br/> |<span data-ttu-id="9d382-126">0： 被叫方的数据</span><span class="sxs-lookup"><span data-stu-id="9d382-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="9d382-127">1： 呼叫者的数据</span><span class="sxs-lookup"><span data-stu-id="9d382-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="9d382-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="9d382-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="9d382-129">会话 LowBandwidth 激发错误状态的百分比。</span><span class="sxs-lookup"><span data-stu-id="9d382-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="9d382-130">可用带宽不足以获得可接受语音体验。</span><span class="sxs-lookup"><span data-stu-id="9d382-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="9d382-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="9d382-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="9d382-132">错误状态触发 ReceiveSendQuality 事件的会话百分比。</span><span class="sxs-lookup"><span data-stu-id="9d382-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="9d382-133">网络质量抖动或数据包丢失非常严重，影响收到的音频的质量。</span><span class="sxs-lookup"><span data-stu-id="9d382-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

