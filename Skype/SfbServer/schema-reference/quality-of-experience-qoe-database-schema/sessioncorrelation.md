---
title: SessionCorrelation 表
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation 表是支持表。 每个记录都表示一个都会用来关联多个会话。
ms.openlocfilehash: 8a9c9661b10548bf3ebf402aa4654fced2ca709b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="77487-104">SessionCorrelation 表</span><span class="sxs-lookup"><span data-stu-id="77487-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="77487-105">SessionCorrelation 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="77487-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="77487-106">每个记录都表示一个都会用来关联多个会话。</span><span class="sxs-lookup"><span data-stu-id="77487-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="77487-107">**列**</span><span class="sxs-lookup"><span data-stu-id="77487-107">**Column**</span></span>|<span data-ttu-id="77487-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="77487-108">**Data Type**</span></span>|<span data-ttu-id="77487-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="77487-109">**Key/Index**</span></span>|<span data-ttu-id="77487-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="77487-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="77487-111">**校验和**</span><span class="sxs-lookup"><span data-stu-id="77487-111">**Checksum**</span></span> <br/> |<span data-ttu-id="77487-112">int</span><span class="sxs-lookup"><span data-stu-id="77487-112">int</span></span>  <br/> |||
|<span data-ttu-id="77487-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="77487-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="77487-114">int</span><span class="sxs-lookup"><span data-stu-id="77487-114">int</span></span>  <br/> |<span data-ttu-id="77487-115">Primary</span><span class="sxs-lookup"><span data-stu-id="77487-115">Primary</span></span>  <br/> |<span data-ttu-id="77487-116">唯一编号标识此 A / V 会议服务器。</span><span class="sxs-lookup"><span data-stu-id="77487-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="77487-117">**都会**</span><span class="sxs-lookup"><span data-stu-id="77487-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="77487-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="77487-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="77487-119">唯一</span><span class="sxs-lookup"><span data-stu-id="77487-119">Unique</span></span>  <br/> |<span data-ttu-id="77487-120">相关联的会话都将拥有相同的相关 id。</span><span class="sxs-lookup"><span data-stu-id="77487-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="77487-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="77487-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="77487-122">datetime</span><span class="sxs-lookup"><span data-stu-id="77487-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="77487-123">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="77487-123">For internal use only.</span></span>  <br/> |
   

