---
title: SessionCorrelation 表
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation 表是一个支持表。 每条记录代表一个 CorrelationID 用于关联多个会话。
ms.openlocfilehash: 8c41ab5c52c6b4d06a3c3953e8d969488680e8d3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884661"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="bab54-104">SessionCorrelation 表</span><span class="sxs-lookup"><span data-stu-id="bab54-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="bab54-105">SessionCorrelation 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="bab54-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="bab54-106">每条记录代表一个 CorrelationID 用于关联多个会话。</span><span class="sxs-lookup"><span data-stu-id="bab54-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="bab54-107">**列**</span><span class="sxs-lookup"><span data-stu-id="bab54-107">**Column**</span></span>|<span data-ttu-id="bab54-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="bab54-108">**Data Type**</span></span>|<span data-ttu-id="bab54-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="bab54-109">**Key/Index**</span></span>|<span data-ttu-id="bab54-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="bab54-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bab54-111">**校验和**</span><span class="sxs-lookup"><span data-stu-id="bab54-111">**Checksum**</span></span> <br/> |<span data-ttu-id="bab54-112">int</span><span class="sxs-lookup"><span data-stu-id="bab54-112">int</span></span>  <br/> |||
|<span data-ttu-id="bab54-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="bab54-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="bab54-114">int</span><span class="sxs-lookup"><span data-stu-id="bab54-114">int</span></span>  <br/> |<span data-ttu-id="bab54-115">Primary</span><span class="sxs-lookup"><span data-stu-id="bab54-115">Primary</span></span>  <br/> |<span data-ttu-id="bab54-116">唯一编号标识该 A / V 会议服务器。</span><span class="sxs-lookup"><span data-stu-id="bab54-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="bab54-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="bab54-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="bab54-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bab54-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="bab54-119">唯一</span><span class="sxs-lookup"><span data-stu-id="bab54-119">Unique</span></span>  <br/> |<span data-ttu-id="bab54-120">关联的会话将具有同一关联 id。</span><span class="sxs-lookup"><span data-stu-id="bab54-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="bab54-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="bab54-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="bab54-122">datetime</span><span class="sxs-lookup"><span data-stu-id="bab54-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="bab54-123">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="bab54-123">For internal use only.</span></span>  <br/> |
   

