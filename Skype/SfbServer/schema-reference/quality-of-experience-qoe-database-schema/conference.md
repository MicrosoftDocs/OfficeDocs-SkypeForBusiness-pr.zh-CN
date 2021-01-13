---
title: Conference 表
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
ms.assetid: 2a2c327c-4719-42dc-a3bb-6dbc0864d9af
description: 会议表是一个支持表。 每条记录代表一个会议或点对点会话。
ms.openlocfilehash: 3840ad9bb4f9b0ff0aea5068c73d307d5bd0cf5e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802782"
---
# <a name="conference-table"></a><span data-ttu-id="65aa6-104">Conference 表</span><span class="sxs-lookup"><span data-stu-id="65aa6-104">Conference table</span></span>
 
<span data-ttu-id="65aa6-p102">会议表是一个支持表。每条记录代表一个会议或点对点会话。</span><span class="sxs-lookup"><span data-stu-id="65aa6-p102">The Conference table is a supporting table. Each record represents one conference or peer-to-peer session.</span></span>
  
|<span data-ttu-id="65aa6-107">**列**</span><span class="sxs-lookup"><span data-stu-id="65aa6-107">**Column**</span></span>|<span data-ttu-id="65aa6-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="65aa6-108">**Data Type**</span></span>|<span data-ttu-id="65aa6-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="65aa6-109">**Key/Index**</span></span>|<span data-ttu-id="65aa6-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="65aa6-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="65aa6-111">**ConferenceKey**</span><span class="sxs-lookup"><span data-stu-id="65aa6-111">**ConferenceKey**</span></span> <br/> |<span data-ttu-id="65aa6-112">int</span><span class="sxs-lookup"><span data-stu-id="65aa6-112">int</span></span>  <br/> |<span data-ttu-id="65aa6-113">主</span><span class="sxs-lookup"><span data-stu-id="65aa6-113">Primary</span></span>  <br/> |<span data-ttu-id="65aa6-114">标识该会议记录的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="65aa6-114">Unique number identifying this conference record.</span></span>  <br/> |
|<span data-ttu-id="65aa6-115">**ConfURI**</span><span class="sxs-lookup"><span data-stu-id="65aa6-115">**ConfURI**</span></span> <br/> |<span data-ttu-id="65aa6-116">nvarchar (450) </span><span class="sxs-lookup"><span data-stu-id="65aa6-116">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="65aa6-117">unique</span><span class="sxs-lookup"><span data-stu-id="65aa6-117">unique</span></span>  <br/> |<span data-ttu-id="65aa6-118">如果是会议，则是会议 URI；如果是点对点会话，则是 DialogID。</span><span class="sxs-lookup"><span data-stu-id="65aa6-118">Conference URI if this is a conference, or DialogID if this is a peer-to-peer session.</span></span>  <br/> |
|<span data-ttu-id="65aa6-119">**校验和**</span><span class="sxs-lookup"><span data-stu-id="65aa6-119">**Checksum**</span></span> <br/> |<span data-ttu-id="65aa6-120">int</span><span class="sxs-lookup"><span data-stu-id="65aa6-120">int</span></span>  <br/> |<span data-ttu-id="65aa6-121">index</span><span class="sxs-lookup"><span data-stu-id="65aa6-121">index</span></span>  <br/> |<span data-ttu-id="65aa6-p103">会议 URI 的校验和。该项仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="65aa6-p103">Checksum of the conference URI. This is used internally.</span></span>  <br/> |
|<span data-ttu-id="65aa6-124">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="65aa6-124">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="65aa6-125">datetime</span><span class="sxs-lookup"><span data-stu-id="65aa6-125">datetime</span></span>  <br/> ||<span data-ttu-id="65aa6-126">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="65aa6-126">For internal use only.</span></span>  <br/> |
   

