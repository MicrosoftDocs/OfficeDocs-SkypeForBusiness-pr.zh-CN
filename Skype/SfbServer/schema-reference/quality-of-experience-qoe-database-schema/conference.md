---
title: Conference 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: 会议表是支持表。 每个记录均代表一个会议或对等会话。
ms.openlocfilehash: 0390f1f9da264ab5269c7bfdcb4a86c08097b835
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="conference-table"></a><span data-ttu-id="7fcd3-104">Conference 表</span><span class="sxs-lookup"><span data-stu-id="7fcd3-104">Conference table</span></span>
 
<span data-ttu-id="7fcd3-105">会议表是支持表。</span><span class="sxs-lookup"><span data-stu-id="7fcd3-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="7fcd3-106">每个记录均代表一个会议或对等会话。</span><span class="sxs-lookup"><span data-stu-id="7fcd3-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="7fcd3-107">**列**</span><span class="sxs-lookup"><span data-stu-id="7fcd3-107">**Column**</span></span>|<span data-ttu-id="7fcd3-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="7fcd3-108">**Data Type**</span></span>|<span data-ttu-id="7fcd3-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="7fcd3-109">**Key/Index**</span></span>|<span data-ttu-id="7fcd3-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="7fcd3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7fcd3-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="7fcd3-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="7fcd3-112">int</span><span class="sxs-lookup"><span data-stu-id="7fcd3-112">int</span></span>  <br/> |<span data-ttu-id="7fcd3-113">Primary</span><span class="sxs-lookup"><span data-stu-id="7fcd3-113">Primary</span></span>  <br/> |<span data-ttu-id="7fcd3-114">标识此会议记录的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="7fcd3-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="7fcd3-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="7fcd3-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="7fcd3-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="7fcd3-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="7fcd3-117">唯一</span><span class="sxs-lookup"><span data-stu-id="7fcd3-117">unique</span></span>  <br/> |<span data-ttu-id="7fcd3-118">如果这是 DialogID 的会议，如果此 URI 会议是对等会话。</span><span class="sxs-lookup"><span data-stu-id="7fcd3-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="7fcd3-119">**校验和**</span><span class="sxs-lookup"><span data-stu-id="7fcd3-119">**Checksum**</span></span> <br/> |<span data-ttu-id="7fcd3-120">int</span><span class="sxs-lookup"><span data-stu-id="7fcd3-120">int</span></span>  <br/> |<span data-ttu-id="7fcd3-121">索引</span><span class="sxs-lookup"><span data-stu-id="7fcd3-121">index</span></span>  <br/> |<span data-ttu-id="7fcd3-122">该会议的 URI 的校验和。</span><span class="sxs-lookup"><span data-stu-id="7fcd3-122">Checksum of the conference URI.</span></span> <span data-ttu-id="7fcd3-123">这是在内部使用。</span><span class="sxs-lookup"><span data-stu-id="7fcd3-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="7fcd3-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="7fcd3-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="7fcd3-125">datetime</span><span class="sxs-lookup"><span data-stu-id="7fcd3-125">datetime</span></span>  <br/> ||<span data-ttu-id="7fcd3-126">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="7fcd3-126">For internal use only.</span></span>  <br/> |
   

