---
title: VideoClientEvent 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 每个记录包含一个终结点，视频通话的客户端事件。 通常，一个电话有两个记录、 调用方和被调用方。
ms.openlocfilehash: b0c73cb3bc07a3e258f66555993698c21a978250
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="videoclientevent-table"></a><span data-ttu-id="54864-104">VideoClientEvent 表</span><span class="sxs-lookup"><span data-stu-id="54864-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="54864-105">每个记录包含一个终结点，视频通话的客户端事件。</span><span class="sxs-lookup"><span data-stu-id="54864-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="54864-106">通常，一个电话有两个记录、 调用方和被调用方。</span><span class="sxs-lookup"><span data-stu-id="54864-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="54864-107">**列**</span><span class="sxs-lookup"><span data-stu-id="54864-107">**Column**</span></span>|<span data-ttu-id="54864-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="54864-108">**Data Type**</span></span>|<span data-ttu-id="54864-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="54864-109">**Key/Index**</span></span>|<span data-ttu-id="54864-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="54864-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="54864-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="54864-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="54864-112">datetime</span><span class="sxs-lookup"><span data-stu-id="54864-112">datetime</span></span>  <br/> |<span data-ttu-id="54864-113">Primary</span><span class="sxs-lookup"><span data-stu-id="54864-113">Primary</span></span>  <br/> |<span data-ttu-id="54864-114">从[MediaLine 表](medialine-0.md)引用。</span><span class="sxs-lookup"><span data-stu-id="54864-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="54864-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="54864-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="54864-116">int</span><span class="sxs-lookup"><span data-stu-id="54864-116">int</span></span>  <br/> |<span data-ttu-id="54864-117">Primary</span><span class="sxs-lookup"><span data-stu-id="54864-117">Primary</span></span>  <br/> |<span data-ttu-id="54864-118">从[MediaLine 表](medialine-0.md)引用。</span><span class="sxs-lookup"><span data-stu-id="54864-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="54864-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="54864-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="54864-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="54864-120">tinyint</span></span>  <br/> |<span data-ttu-id="54864-121">Primary</span><span class="sxs-lookup"><span data-stu-id="54864-121">Primary</span></span>  <br/> |<span data-ttu-id="54864-122">从[MediaLine 表](medialine-0.md)引用。</span><span class="sxs-lookup"><span data-stu-id="54864-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="54864-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="54864-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="54864-124">bit</span><span class="sxs-lookup"><span data-stu-id="54864-124">bit</span></span>  <br/> |<span data-ttu-id="54864-125">Primary</span><span class="sxs-lookup"><span data-stu-id="54864-125">Primary</span></span>  <br/> |<span data-ttu-id="54864-126">0： 被调用方的数据</span><span class="sxs-lookup"><span data-stu-id="54864-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="54864-127">1： 呼叫者的数据</span><span class="sxs-lookup"><span data-stu-id="54864-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="54864-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="54864-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="54864-129">错误状态的会话触发 LowBandwidth 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="54864-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="54864-130">可用的带宽不足以可接受的声音体验。</span><span class="sxs-lookup"><span data-stu-id="54864-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="54864-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="54864-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="54864-132">错误状态的会话触发 ReceiveSendQuality 事件的百分比。</span><span class="sxs-lookup"><span data-stu-id="54864-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="54864-133">根据抖动或数据包丢失的网络质量严重，而且影响所接收到的音频的质量。</span><span class="sxs-lookup"><span data-stu-id="54864-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

