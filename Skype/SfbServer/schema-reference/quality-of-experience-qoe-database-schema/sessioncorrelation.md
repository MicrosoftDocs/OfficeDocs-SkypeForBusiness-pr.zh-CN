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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation 表是支持表。 每条记录表示一个 CorrelationID，用于关联多个会话。
ms.openlocfilehash: cd9f477ad71b836fb204aab651aceb7bbb5832f8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805740"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="71158-104">SessionCorrelation 表</span><span class="sxs-lookup"><span data-stu-id="71158-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="71158-105">SessionCorrelation 表是支持表。</span><span class="sxs-lookup"><span data-stu-id="71158-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="71158-106">每条记录表示一个 CorrelationID，用于关联多个会话。</span><span class="sxs-lookup"><span data-stu-id="71158-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="71158-107">**列**</span><span class="sxs-lookup"><span data-stu-id="71158-107">**Column**</span></span>|<span data-ttu-id="71158-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="71158-108">**Data Type**</span></span>|<span data-ttu-id="71158-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="71158-109">**Key/Index**</span></span>|<span data-ttu-id="71158-110">**详细信息**</span><span class="sxs-lookup"><span data-stu-id="71158-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="71158-111">**检查**</span><span class="sxs-lookup"><span data-stu-id="71158-111">**Checksum**</span></span> <br/> |<span data-ttu-id="71158-112">int</span><span class="sxs-lookup"><span data-stu-id="71158-112">int</span></span>  <br/> |||
|<span data-ttu-id="71158-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="71158-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="71158-114">int</span><span class="sxs-lookup"><span data-stu-id="71158-114">int</span></span>  <br/> |<span data-ttu-id="71158-115">Primary</span><span class="sxs-lookup"><span data-stu-id="71158-115">Primary</span></span>  <br/> |<span data-ttu-id="71158-116">标识此 A/V 会议服务器的唯一号码。</span><span class="sxs-lookup"><span data-stu-id="71158-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="71158-117">**True&correlationid**</span><span class="sxs-lookup"><span data-stu-id="71158-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="71158-118">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="71158-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="71158-119">唯一</span><span class="sxs-lookup"><span data-stu-id="71158-119">Unique</span></span>  <br/> |<span data-ttu-id="71158-120">关联的会话将具有相同的相关性 ID。</span><span class="sxs-lookup"><span data-stu-id="71158-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="71158-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="71158-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="71158-122">datetime</span><span class="sxs-lookup"><span data-stu-id="71158-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="71158-123">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="71158-123">For internal use only.</span></span>  <br/> |
   

