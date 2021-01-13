---
title: VideoClientEvent 表
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 每条记录都包含视频呼叫中一个终结点的客户端事件。 通常，一个呼叫有两条记录，一条用于呼叫者，另一条用于被叫方。
ms.openlocfilehash: bb4a9feca562bed7bdb0080e7f9181003952f5d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821392"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="d068d-104">VideoClientEvent 表</span><span class="sxs-lookup"><span data-stu-id="d068d-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="d068d-105">每条记录都包含视频呼叫中一个终结点的客户端事件。</span><span class="sxs-lookup"><span data-stu-id="d068d-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="d068d-106">通常，一个呼叫有两条记录，一条用于呼叫者，另一条用于被叫方。</span><span class="sxs-lookup"><span data-stu-id="d068d-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="d068d-107">**列**</span><span class="sxs-lookup"><span data-stu-id="d068d-107">**Column**</span></span>|<span data-ttu-id="d068d-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="d068d-108">**Data Type**</span></span>|<span data-ttu-id="d068d-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="d068d-109">**Key/Index**</span></span>|<span data-ttu-id="d068d-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="d068d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d068d-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="d068d-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="d068d-112">datetime</span><span class="sxs-lookup"><span data-stu-id="d068d-112">datetime</span></span>  <br/> |<span data-ttu-id="d068d-113">主</span><span class="sxs-lookup"><span data-stu-id="d068d-113">Primary</span></span>  <br/> |<span data-ttu-id="d068d-114">从 [MediaLine 表引用](medialine-0.md)。</span><span class="sxs-lookup"><span data-stu-id="d068d-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="d068d-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="d068d-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="d068d-116">int</span><span class="sxs-lookup"><span data-stu-id="d068d-116">int</span></span>  <br/> |<span data-ttu-id="d068d-117">主</span><span class="sxs-lookup"><span data-stu-id="d068d-117">Primary</span></span>  <br/> |<span data-ttu-id="d068d-118">从 [MediaLine 表引用](medialine-0.md)。</span><span class="sxs-lookup"><span data-stu-id="d068d-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="d068d-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="d068d-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="d068d-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="d068d-120">tinyint</span></span>  <br/> |<span data-ttu-id="d068d-121">主</span><span class="sxs-lookup"><span data-stu-id="d068d-121">Primary</span></span>  <br/> |<span data-ttu-id="d068d-122">从 [MediaLine 表引用](medialine-0.md)。</span><span class="sxs-lookup"><span data-stu-id="d068d-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="d068d-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="d068d-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="d068d-124">bit</span><span class="sxs-lookup"><span data-stu-id="d068d-124">bit</span></span>  <br/> |<span data-ttu-id="d068d-125">主</span><span class="sxs-lookup"><span data-stu-id="d068d-125">Primary</span></span>  <br/> |<span data-ttu-id="d068d-126">0：被叫方的数据</span><span class="sxs-lookup"><span data-stu-id="d068d-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="d068d-127">1：呼叫者的数据</span><span class="sxs-lookup"><span data-stu-id="d068d-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="d068d-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="d068d-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="d068d-129">因"错误"状态触发 LowBandwidth 事件的会话百分比。</span><span class="sxs-lookup"><span data-stu-id="d068d-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="d068d-130">可用带宽不足，无法提供可接受的语音体验。</span><span class="sxs-lookup"><span data-stu-id="d068d-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="d068d-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="d068d-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="d068d-132">因"错误"状态触发 ReceiveSendQuality 事件的会话百分比。</span><span class="sxs-lookup"><span data-stu-id="d068d-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="d068d-133">抖动或数据包丢失方面的网络质量十分严重，并影响所接收音频的质量。</span><span class="sxs-lookup"><span data-stu-id="d068d-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

