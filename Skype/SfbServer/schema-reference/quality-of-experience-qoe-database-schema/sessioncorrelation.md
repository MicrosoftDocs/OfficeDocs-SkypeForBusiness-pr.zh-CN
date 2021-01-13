---
title: SessionCorrelation 表
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
ms.assetid: 041705e1-7290-464f-95f8-96256cfa2e3e
description: SessionCorrelation 表是一个支持表。 每条记录表示一个 CorrelationID，用于关联多个会话。
ms.openlocfilehash: 36b617517f3642a2150c72369db858eee62a4a87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802652"
---
# <a name="sessioncorrelation-table"></a><span data-ttu-id="b3d81-104">SessionCorrelation 表</span><span class="sxs-lookup"><span data-stu-id="b3d81-104">SessionCorrelation table</span></span>
 
<span data-ttu-id="b3d81-105">SessionCorrelation 表是一个支持表。</span><span class="sxs-lookup"><span data-stu-id="b3d81-105">The SessionCorrelation table is a supporting table.</span></span> <span data-ttu-id="b3d81-106">每条记录表示一个 CorrelationID，用于关联多个会话。</span><span class="sxs-lookup"><span data-stu-id="b3d81-106">Each record represents one CorrelationID which is used to correlate multiple sessions.</span></span> 
  
|<span data-ttu-id="b3d81-107">**列**</span><span class="sxs-lookup"><span data-stu-id="b3d81-107">**Column**</span></span>|<span data-ttu-id="b3d81-108">**数据类型**</span><span class="sxs-lookup"><span data-stu-id="b3d81-108">**Data Type**</span></span>|<span data-ttu-id="b3d81-109">**键/索引**</span><span class="sxs-lookup"><span data-stu-id="b3d81-109">**Key/Index**</span></span>|<span data-ttu-id="b3d81-110">**Details**</span><span class="sxs-lookup"><span data-stu-id="b3d81-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b3d81-111">**校验和**</span><span class="sxs-lookup"><span data-stu-id="b3d81-111">**Checksum**</span></span> <br/> |<span data-ttu-id="b3d81-112">int</span><span class="sxs-lookup"><span data-stu-id="b3d81-112">int</span></span>  <br/> |||
|<span data-ttu-id="b3d81-113">**CorrelationKey**</span><span class="sxs-lookup"><span data-stu-id="b3d81-113">**CorrelationKey**</span></span> <br/> |<span data-ttu-id="b3d81-114">int</span><span class="sxs-lookup"><span data-stu-id="b3d81-114">int</span></span>  <br/> |<span data-ttu-id="b3d81-115">主</span><span class="sxs-lookup"><span data-stu-id="b3d81-115">Primary</span></span>  <br/> |<span data-ttu-id="b3d81-116">标识此 A/V 会议服务器的唯一编号。</span><span class="sxs-lookup"><span data-stu-id="b3d81-116">Unique number identifying this A/V Conferencing Server.</span></span>  <br/> |
|<span data-ttu-id="b3d81-117">**CorrelationID**</span><span class="sxs-lookup"><span data-stu-id="b3d81-117">**CorrelationID**</span></span> <br/> |<span data-ttu-id="b3d81-118">nvarchar (256) </span><span class="sxs-lookup"><span data-stu-id="b3d81-118">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="b3d81-119">独特</span><span class="sxs-lookup"><span data-stu-id="b3d81-119">Unique</span></span>  <br/> |<span data-ttu-id="b3d81-120">关联的会话将具有相同的关联 ID。</span><span class="sxs-lookup"><span data-stu-id="b3d81-120">Sessions that are correlated will have the same correlation ID.</span></span>  <br/> |
|<span data-ttu-id="b3d81-121">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="b3d81-121">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="b3d81-122">datetime</span><span class="sxs-lookup"><span data-stu-id="b3d81-122">datetime</span></span>  <br/> | <br/> |<span data-ttu-id="b3d81-123">仅供内部使用。</span><span class="sxs-lookup"><span data-stu-id="b3d81-123">For internal use only.</span></span>  <br/> |
   

