---
title: Conference 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: 会议表是支持表。 每条记录表示一个会议或对等会话。
ms.openlocfilehash: 61e9667d235ed9ab8f3696f55e676bfc60ab69e3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295011"
---
# <a name="conference-table"></a><span data-ttu-id="52e14-104">Conference 表</span><span class="sxs-lookup"><span data-stu-id="52e14-104">Conference table</span></span>
 
<span data-ttu-id="52e14-105">会议表是支持表。</span><span class="sxs-lookup"><span data-stu-id="52e14-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="52e14-106">每条记录表示一个会议或对等会话。</span><span class="sxs-lookup"><span data-stu-id="52e14-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="52e14-107">**列**</span><span class="sxs-lookup"><span data-stu-id="52e14-107">**Column**</span></span>|<span data-ttu-id="52e14-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="52e14-108">**Data Type**</span></span>|<span data-ttu-id="52e14-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="52e14-109">**Key/Index**</span></span>|<span data-ttu-id="52e14-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="52e14-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="52e14-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="52e14-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="52e14-112">int</span><span class="sxs-lookup"><span data-stu-id="52e14-112">int</span></span>  <br/> |<span data-ttu-id="52e14-113">Primary</span><span class="sxs-lookup"><span data-stu-id="52e14-113">Primary</span></span>  <br/> |<span data-ttu-id="52e14-114">标识此会议记录的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="52e14-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="52e14-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="52e14-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="52e14-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="52e14-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="52e14-117">唯一</span><span class="sxs-lookup"><span data-stu-id="52e14-117">unique</span></span>  <br/> |<span data-ttu-id="52e14-118">会议 URI (如果这是会议) 或 DialogID (如果这是对等会话)。</span><span class="sxs-lookup"><span data-stu-id="52e14-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="52e14-119">**检查**</span><span class="sxs-lookup"><span data-stu-id="52e14-119">**Checksum**</span></span> <br/> |<span data-ttu-id="52e14-120">int</span><span class="sxs-lookup"><span data-stu-id="52e14-120">int</span></span>  <br/> |<span data-ttu-id="52e14-121">食指</span><span class="sxs-lookup"><span data-stu-id="52e14-121">index</span></span>  <br/> |<span data-ttu-id="52e14-122">会议 URI 的校验和。</span><span class="sxs-lookup"><span data-stu-id="52e14-122">Checksum of the conference URI.</span></span> <span data-ttu-id="52e14-123">此功能在内部使用。</span><span class="sxs-lookup"><span data-stu-id="52e14-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="52e14-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="52e14-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="52e14-125">datetime</span><span class="sxs-lookup"><span data-stu-id="52e14-125">datetime</span></span>  <br/> ||<span data-ttu-id="52e14-126">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="52e14-126">For internal use only.</span></span>  <br/> |
   

