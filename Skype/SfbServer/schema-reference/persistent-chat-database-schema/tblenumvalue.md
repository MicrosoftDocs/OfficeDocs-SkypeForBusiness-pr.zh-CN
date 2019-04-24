---
title: tblEnumValue
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblenumvalue 表是一个硬编码表，包含节点表使用的属性的 Visibility 和 Behavior 值。
ms.openlocfilehash: 579b2747ea753b8a701d11dd806178427cbb27b3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212878"
---
# <a name="tblenumvalue"></a><span data-ttu-id="46aa1-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="46aa1-103">tblEnumValue</span></span>
 
<span data-ttu-id="46aa1-104">tblenumvalue 表是一个硬编码表，包含节点表使用的属性的 Visibility 和 Behavior 值。</span><span class="sxs-lookup"><span data-stu-id="46aa1-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="46aa1-105">**列**</span><span class="sxs-lookup"><span data-stu-id="46aa1-105">**Columns**</span></span>

|<span data-ttu-id="46aa1-106">**列**</span><span class="sxs-lookup"><span data-stu-id="46aa1-106">**Column**</span></span>|<span data-ttu-id="46aa1-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="46aa1-107">**Type**</span></span>|<span data-ttu-id="46aa1-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="46aa1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="46aa1-109">valueID</span><span class="sxs-lookup"><span data-stu-id="46aa1-109">valueID</span></span>  <br/> |<span data-ttu-id="46aa1-110">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="46aa1-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="46aa1-111">值的 ID。</span><span class="sxs-lookup"><span data-stu-id="46aa1-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="46aa1-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="46aa1-112">attributeID</span></span>  <br/> |<span data-ttu-id="46aa1-113">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="46aa1-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="46aa1-114">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="46aa1-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="46aa1-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="46aa1-115">attributeValue</span></span>  <br/> |<span data-ttu-id="46aa1-116">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="46aa1-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="46aa1-117">值的名称。</span><span class="sxs-lookup"><span data-stu-id="46aa1-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="46aa1-118">**键**</span><span class="sxs-lookup"><span data-stu-id="46aa1-118">**Keys**</span></span>

|<span data-ttu-id="46aa1-119">**列**</span><span class="sxs-lookup"><span data-stu-id="46aa1-119">**Column**</span></span>|<span data-ttu-id="46aa1-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="46aa1-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="46aa1-121">valueID</span><span class="sxs-lookup"><span data-stu-id="46aa1-121">valueID</span></span>  <br/> |<span data-ttu-id="46aa1-122">主键。</span><span class="sxs-lookup"><span data-stu-id="46aa1-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="46aa1-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="46aa1-123">attributeID</span></span>  <br/> |<span data-ttu-id="46aa1-124">在 tblEnumAttribute.attributeID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="46aa1-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="46aa1-125">**表值**</span><span class="sxs-lookup"><span data-stu-id="46aa1-125">**Table Values**</span></span>

|<span data-ttu-id="46aa1-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="46aa1-126">**valueID**</span></span>|<span data-ttu-id="46aa1-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="46aa1-127">**attributeID**</span></span>|<span data-ttu-id="46aa1-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="46aa1-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="46aa1-129">2</span><span class="sxs-lookup"><span data-stu-id="46aa1-129">2</span></span>  <br/> |<span data-ttu-id="46aa1-130">1</span><span class="sxs-lookup"><span data-stu-id="46aa1-130">1</span></span>  <br/> |<span data-ttu-id="46aa1-131">专用</span><span class="sxs-lookup"><span data-stu-id="46aa1-131">private</span></span>  <br/> |
|<span data-ttu-id="46aa1-132">3</span><span class="sxs-lookup"><span data-stu-id="46aa1-132">3</span></span>  <br/> |<span data-ttu-id="46aa1-133">1</span><span class="sxs-lookup"><span data-stu-id="46aa1-133">1</span></span>  <br/> |<span data-ttu-id="46aa1-134">范围</span><span class="sxs-lookup"><span data-stu-id="46aa1-134">scope</span></span>  <br/> |
|<span data-ttu-id="46aa1-135">4</span><span class="sxs-lookup"><span data-stu-id="46aa1-135">4</span></span>  <br/> |<span data-ttu-id="46aa1-136">2</span><span class="sxs-lookup"><span data-stu-id="46aa1-136">2</span></span>  <br/> |<span data-ttu-id="46aa1-137">普通</span><span class="sxs-lookup"><span data-stu-id="46aa1-137">normal</span></span>  <br/> |
|<span data-ttu-id="46aa1-138">5</span><span class="sxs-lookup"><span data-stu-id="46aa1-138">5</span></span>  <br/> |<span data-ttu-id="46aa1-139">2</span><span class="sxs-lookup"><span data-stu-id="46aa1-139">2</span></span>  <br/> |<span data-ttu-id="46aa1-140">大会堂</span><span class="sxs-lookup"><span data-stu-id="46aa1-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="46aa1-141">6</span><span class="sxs-lookup"><span data-stu-id="46aa1-141">6</span></span>  <br/> |<span data-ttu-id="46aa1-142">1</span><span class="sxs-lookup"><span data-stu-id="46aa1-142">1</span></span>  <br/> |<span data-ttu-id="46aa1-143">打开</span><span class="sxs-lookup"><span data-stu-id="46aa1-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="46aa1-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="46aa1-144">See also</span></span>

[<span data-ttu-id="46aa1-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="46aa1-145">tblNode</span></span>](tblnode.md)
