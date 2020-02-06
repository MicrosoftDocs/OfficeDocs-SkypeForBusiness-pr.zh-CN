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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: 会议表是支持表。 每条记录表示一个会议或对等会话。
ms.openlocfilehash: 95e08861adaca2e76144f35037626e7b03afd962
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810300"
---
# <a name="conference-table"></a><span data-ttu-id="35a4d-104">Conference 表</span><span class="sxs-lookup"><span data-stu-id="35a4d-104">Conference table</span></span>
 
<span data-ttu-id="35a4d-105">会议表是支持表。</span><span class="sxs-lookup"><span data-stu-id="35a4d-105">The Conference table is a supporting table.</span></span> <span data-ttu-id="35a4d-106">每条记录表示一个会议或对等会话。</span><span class="sxs-lookup"><span data-stu-id="35a4d-106">Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="35a4d-107">**列**</span><span class="sxs-lookup"><span data-stu-id="35a4d-107">**Column**</span></span>|<span data-ttu-id="35a4d-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="35a4d-108">**Data Type**</span></span>|<span data-ttu-id="35a4d-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="35a4d-109">**Key/Index**</span></span>|<span data-ttu-id="35a4d-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="35a4d-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="35a4d-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="35a4d-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="35a4d-112">int</span><span class="sxs-lookup"><span data-stu-id="35a4d-112">int</span></span>  <br/> |<span data-ttu-id="35a4d-113">Primary</span><span class="sxs-lookup"><span data-stu-id="35a4d-113">Primary</span></span>  <br/> |<span data-ttu-id="35a4d-114">标识此会议记录的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="35a4d-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="35a4d-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="35a4d-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="35a4d-116">nvarchar （450）</span><span class="sxs-lookup"><span data-stu-id="35a4d-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="35a4d-117">唯一</span><span class="sxs-lookup"><span data-stu-id="35a4d-117">unique</span></span>  <br/> |<span data-ttu-id="35a4d-118">会议 URI （如果这是会议）或 DialogID （如果这是对等会话）。</span><span class="sxs-lookup"><span data-stu-id="35a4d-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="35a4d-119">**检查**</span><span class="sxs-lookup"><span data-stu-id="35a4d-119">**Checksum**</span></span> <br/> |<span data-ttu-id="35a4d-120">int</span><span class="sxs-lookup"><span data-stu-id="35a4d-120">int</span></span>  <br/> |<span data-ttu-id="35a4d-121">食指</span><span class="sxs-lookup"><span data-stu-id="35a4d-121">index</span></span>  <br/> |<span data-ttu-id="35a4d-122">会议 URI 的校验和。</span><span class="sxs-lookup"><span data-stu-id="35a4d-122">Checksum of the conference URI.</span></span> <span data-ttu-id="35a4d-123">此功能在内部使用。</span><span class="sxs-lookup"><span data-stu-id="35a4d-123">This is used internally.</span></span>  <br/> |
|<span data-ttu-id="35a4d-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="35a4d-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="35a4d-125">datetime</span><span class="sxs-lookup"><span data-stu-id="35a4d-125">datetime</span></span>  <br/> ||<span data-ttu-id="35a4d-126">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="35a4d-126">For internal use only.</span></span>  <br/> |
   

