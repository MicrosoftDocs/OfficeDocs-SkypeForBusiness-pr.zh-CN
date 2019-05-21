---
title: SessionCorrelation 表
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation 表是支持表。 每条记录表示一个 CorrelationID, 用于关联多个会话。
ms.openlocfilehash: 3c307b9542b9c1f37967a40ae63979d72e0504ae
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294654"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="85ac3-104">SessionCorrelation 表</span><span class="sxs-lookup"><span data-stu-id="85ac3-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="85ac3-105">SessionCorrelation 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="85ac3-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="85ac3-106">每条记录表示一个 CorrelationID, 用于关联多个会话。</span><span class="sxs-lookup"><span data-stu-id="85ac3-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="85ac3-107">**列**</span><span class="sxs-lookup"><span data-stu-id="85ac3-107">**Column**</span></span>|<span data-ttu-id="85ac3-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="85ac3-108">**Data Type**</span></span>|<span data-ttu-id="85ac3-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="85ac3-109">**Key/Index**</span></span>|<span data-ttu-id="85ac3-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="85ac3-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="85ac3-111">**检查**</span><span class="sxs-lookup"><span data-stu-id="85ac3-111">**Checksum**</span></span> <br/> |<span data-ttu-id="85ac3-112">int</span><span class="sxs-lookup"><span data-stu-id="85ac3-112">int</span></span>  <br/> |||
|<span data-ttu-id="85ac3-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="85ac3-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="85ac3-114">int</span><span class="sxs-lookup"><span data-stu-id="85ac3-114">int</span></span>  <br/> |<span data-ttu-id="85ac3-115">Primary</span><span class="sxs-lookup"><span data-stu-id="85ac3-115">Primary</span></span>  <br/> |<span data-ttu-id="85ac3-116">标识此 A/V 会议服务器的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="85ac3-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="85ac3-117">**True&correlationid**</span><span class="sxs-lookup"><span data-stu-id="85ac3-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="85ac3-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="85ac3-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="85ac3-119">唯一</span><span class="sxs-lookup"><span data-stu-id="85ac3-119">Unique</span></span>  <br/> |<span data-ttu-id="85ac3-120">关联的会话将具有相同的相关性 ID。</span><span class="sxs-lookup"><span data-stu-id="85ac3-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="85ac3-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="85ac3-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="85ac3-122">datetime</span><span class="sxs-lookup"><span data-stu-id="85ac3-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="85ac3-123">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="85ac3-123">For internal use only.</span></span>  <br/> |
   

