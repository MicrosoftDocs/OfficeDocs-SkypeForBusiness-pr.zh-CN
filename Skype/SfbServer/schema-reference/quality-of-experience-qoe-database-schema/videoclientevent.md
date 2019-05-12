---
title: VideoClientEvent 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8ab963b-fe1d-45b3-b9bd-66a5f44c1629
description: 每个记录包含在视频呼叫的一个端点的客户端事件。 通常，一次调用具有两个记录，一个用于呼叫者，一个用于被叫方。
ms.openlocfilehash: 58179630534733985e062bbe0fafa1bbfd8499db
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33906824"
---
# <a name="videoclientevent-table"></a><span data-ttu-id="b4569-104">VideoClientEvent 表</span><span class="sxs-lookup"><span data-stu-id="b4569-104">VideoClientEvent table</span></span>
 
<span data-ttu-id="b4569-105">每个记录包含在视频呼叫的一个端点的客户端事件。</span><span class="sxs-lookup"><span data-stu-id="b4569-105">Each record contains client event for one endpoint in a video call.</span></span> <span data-ttu-id="b4569-106">通常，一次调用具有两个记录，一个用于呼叫者，一个用于被叫方。</span><span class="sxs-lookup"><span data-stu-id="b4569-106">Usually, one call has two records, one for caller and one for callee.</span></span>
  
|<span data-ttu-id="b4569-107">**列**</span><span class="sxs-lookup"><span data-stu-id="b4569-107">**Column**</span></span>|<span data-ttu-id="b4569-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="b4569-108">**Data Type**</span></span>|<span data-ttu-id="b4569-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="b4569-109">**Key/Index**</span></span>|<span data-ttu-id="b4569-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="b4569-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b4569-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="b4569-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="b4569-112">datetime</span><span class="sxs-lookup"><span data-stu-id="b4569-112">datetime</span></span>  <br/> |<span data-ttu-id="b4569-113">Primary</span><span class="sxs-lookup"><span data-stu-id="b4569-113">Primary</span></span>  <br/> |<span data-ttu-id="b4569-114">引用[自 MediaLine table](medialine-0.md)。</span><span class="sxs-lookup"><span data-stu-id="b4569-114">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="b4569-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="b4569-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="b4569-116">int</span><span class="sxs-lookup"><span data-stu-id="b4569-116">int</span></span>  <br/> |<span data-ttu-id="b4569-117">Primary</span><span class="sxs-lookup"><span data-stu-id="b4569-117">Primary</span></span>  <br/> |<span data-ttu-id="b4569-118">引用[自 MediaLine table](medialine-0.md)。</span><span class="sxs-lookup"><span data-stu-id="b4569-118">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="b4569-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="b4569-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="b4569-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="b4569-120">tinyint</span></span>  <br/> |<span data-ttu-id="b4569-121">Primary</span><span class="sxs-lookup"><span data-stu-id="b4569-121">Primary</span></span>  <br/> |<span data-ttu-id="b4569-122">引用[自 MediaLine table](medialine-0.md)。</span><span class="sxs-lookup"><span data-stu-id="b4569-122">Referenced from the [MediaLine table](medialine-0.md).</span></span>  <br/> |
|<span data-ttu-id="b4569-123">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="b4569-123">**FromCaller**</span></span> <br/> |<span data-ttu-id="b4569-124">bit</span><span class="sxs-lookup"><span data-stu-id="b4569-124">bit</span></span>  <br/> |<span data-ttu-id="b4569-125">Primary</span><span class="sxs-lookup"><span data-stu-id="b4569-125">Primary</span></span>  <br/> |<span data-ttu-id="b4569-126">0： 被叫方的数据</span><span class="sxs-lookup"><span data-stu-id="b4569-126">0: Callee's data</span></span>  <br/> <span data-ttu-id="b4569-127">1： 呼叫者的数据</span><span class="sxs-lookup"><span data-stu-id="b4569-127">1: Caller's data</span></span>  <br/> |
|<span data-ttu-id="b4569-128">**NetworkBandwidthLowEventRatio**</span><span class="sxs-lookup"><span data-stu-id="b4569-128">**NetworkBandwidthLowEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="b4569-129">会话 LowBandwidth 激发错误状态的百分比。</span><span class="sxs-lookup"><span data-stu-id="b4569-129">Percentage of session the LowBandwidth event was fired for 'Bad' state.</span></span> <span data-ttu-id="b4569-130">可用带宽不足以获得可接受语音体验。</span><span class="sxs-lookup"><span data-stu-id="b4569-130">The available bandwidth is insufficient for an acceptable voice experience.</span></span>  <br/> |
|<span data-ttu-id="b4569-131">**NetworkReceiveQualityEventRatio**</span><span class="sxs-lookup"><span data-stu-id="b4569-131">**NetworkReceiveQualityEventRatio**</span></span> <br/> || <br/> |<span data-ttu-id="b4569-132">错误状态触发 ReceiveSendQuality 事件的会话百分比。</span><span class="sxs-lookup"><span data-stu-id="b4569-132">Percentage of session the ReceiveSendQuality event was fired for 'Bad' state.</span></span>  <br/> <span data-ttu-id="b4569-133">网络质量抖动或数据包丢失非常严重，影响收到的音频的质量。</span><span class="sxs-lookup"><span data-stu-id="b4569-133">Network quality in terms of jitter or packet loss is severe and impacts the quality of audio being received.</span></span>  <br/> |
   

