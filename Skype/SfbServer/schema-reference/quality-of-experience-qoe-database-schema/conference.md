---
title: Conference 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: Conference 表是一个支持表。 每条记录代表一个会议或对等会话。
ms.openlocfilehash: bae144ff574f19155e11b8a2fbfd3548df356c2a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212261"
---
# <a name="conference-table"></a><span data-ttu-id="e315e-104">Conference 表</span><span class="sxs-lookup"><span data-stu-id="e315e-104">Conference table</span></span>
 
<span data-ttu-id="e315e-105">Conference 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="e315e-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="e315e-106">每条记录代表一个会议或对等会话。</span><span class="sxs-lookup"><span data-stu-id="e315e-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="e315e-107">**列**</span><span class="sxs-lookup"><span data-stu-id="e315e-107">**Column**</span></span>|<span data-ttu-id="e315e-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="e315e-108">**Data Type**</span></span>|<span data-ttu-id="e315e-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="e315e-109">**Key/Index**</span></span>|<span data-ttu-id="e315e-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="e315e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e315e-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="e315e-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="e315e-112">int</span><span class="sxs-lookup"><span data-stu-id="e315e-112">int</span></span>  <br/> |<span data-ttu-id="e315e-113">Primary</span><span class="sxs-lookup"><span data-stu-id="e315e-113">Primary</span></span>  <br/> |<span data-ttu-id="e315e-114">标识此会议记录的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="e315e-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="e315e-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="e315e-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="e315e-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="e315e-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="e315e-117">唯一</span><span class="sxs-lookup"><span data-stu-id="e315e-117">unique</span></span>  <br/> |<span data-ttu-id="e315e-118">会议 URI 如果这是 dialogid 会议，如果它是对等会话。</span><span class="sxs-lookup"><span data-stu-id="e315e-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="e315e-119">**校验和**</span><span class="sxs-lookup"><span data-stu-id="e315e-119">**Checksum**</span></span> <br/> |<span data-ttu-id="e315e-120">int</span><span class="sxs-lookup"><span data-stu-id="e315e-120">int</span></span>  <br/> |<span data-ttu-id="e315e-121">索引</span><span class="sxs-lookup"><span data-stu-id="e315e-121">index</span></span>  <br/> |<span data-ttu-id="e315e-122">会议 URI 的校验和。</span><span class="sxs-lookup"><span data-stu-id="e315e-122">Checksum of the conference URI.</span></span> <span data-ttu-id="e315e-123">这是在内部使用。</span><span class="sxs-lookup"><span data-stu-id="e315e-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="e315e-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="e315e-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="e315e-125">datetime</span><span class="sxs-lookup"><span data-stu-id="e315e-125">datetime</span></span>  <br/> ||<span data-ttu-id="e315e-126">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="e315e-126">For internal use only.</span></span>  <br/> |
   

