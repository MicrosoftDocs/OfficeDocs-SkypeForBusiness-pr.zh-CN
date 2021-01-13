---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue 表是一个硬编码表，包含节点表使用的属性的“可见性”值和“行为”值。
ms.openlocfilehash: a13bfbe79d1eb118f0727f390816a26d35a508d0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816022"
---
# <a name="tblenumvalue"></a><span data-ttu-id="29d28-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="29d28-103">tblEnumValue</span></span>
 
<span data-ttu-id="29d28-104">tblEnumValue 表是一个硬编码表，包含节点表使用的属性的“可见性”值和“行为”值。</span><span class="sxs-lookup"><span data-stu-id="29d28-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="29d28-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="29d28-105">**Columns**</span></span>

|<span data-ttu-id="29d28-106">**列**</span><span class="sxs-lookup"><span data-stu-id="29d28-106">**Column**</span></span>|<span data-ttu-id="29d28-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="29d28-107">**Type**</span></span>|<span data-ttu-id="29d28-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="29d28-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="29d28-109">valueID</span><span class="sxs-lookup"><span data-stu-id="29d28-109">valueID</span></span>  <br/> |<span data-ttu-id="29d28-110">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="29d28-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="29d28-111">值的 ID。</span><span class="sxs-lookup"><span data-stu-id="29d28-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="29d28-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="29d28-112">attributeID</span></span>  <br/> |<span data-ttu-id="29d28-113">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="29d28-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="29d28-114">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="29d28-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="29d28-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="29d28-115">attributeValue</span></span>  <br/> |<span data-ttu-id="29d28-116">nvarchar  (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="29d28-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="29d28-117">值名称。</span><span class="sxs-lookup"><span data-stu-id="29d28-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="29d28-118">**Keys**</span><span class="sxs-lookup"><span data-stu-id="29d28-118">**Keys**</span></span>

|<span data-ttu-id="29d28-119">**列**</span><span class="sxs-lookup"><span data-stu-id="29d28-119">**Column**</span></span>|<span data-ttu-id="29d28-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="29d28-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="29d28-121">valueID</span><span class="sxs-lookup"><span data-stu-id="29d28-121">valueID</span></span>  <br/> |<span data-ttu-id="29d28-122">主键。</span><span class="sxs-lookup"><span data-stu-id="29d28-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="29d28-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="29d28-123">attributeID</span></span>  <br/> |<span data-ttu-id="29d28-124">其查找包含在 tblEnumAttribute.attributeID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="29d28-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="29d28-125">**表值**</span><span class="sxs-lookup"><span data-stu-id="29d28-125">**Table Values**</span></span>

|<span data-ttu-id="29d28-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="29d28-126">**valueID**</span></span>|<span data-ttu-id="29d28-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="29d28-127">**attributeID**</span></span>|<span data-ttu-id="29d28-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="29d28-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="29d28-129">2 </span><span class="sxs-lookup"><span data-stu-id="29d28-129">2</span></span>  <br/> |<span data-ttu-id="29d28-130">1 </span><span class="sxs-lookup"><span data-stu-id="29d28-130">1</span></span>  <br/> |<span data-ttu-id="29d28-131">private</span><span class="sxs-lookup"><span data-stu-id="29d28-131">private</span></span>  <br/> |
|<span data-ttu-id="29d28-132">3 </span><span class="sxs-lookup"><span data-stu-id="29d28-132">3</span></span>  <br/> |<span data-ttu-id="29d28-133">1 </span><span class="sxs-lookup"><span data-stu-id="29d28-133">1</span></span>  <br/> |<span data-ttu-id="29d28-134">范围</span><span class="sxs-lookup"><span data-stu-id="29d28-134">scope</span></span>  <br/> |
|<span data-ttu-id="29d28-135">4 </span><span class="sxs-lookup"><span data-stu-id="29d28-135">4</span></span>  <br/> |<span data-ttu-id="29d28-136">2 </span><span class="sxs-lookup"><span data-stu-id="29d28-136">2</span></span>  <br/> |<span data-ttu-id="29d28-137">normal</span><span class="sxs-lookup"><span data-stu-id="29d28-137">normal</span></span>  <br/> |
|<span data-ttu-id="29d28-138">5 </span><span class="sxs-lookup"><span data-stu-id="29d28-138">5</span></span>  <br/> |<span data-ttu-id="29d28-139">2 </span><span class="sxs-lookup"><span data-stu-id="29d28-139">2</span></span>  <br/> |<span data-ttu-id="29d28-140">大会堂</span><span class="sxs-lookup"><span data-stu-id="29d28-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="29d28-141">6 </span><span class="sxs-lookup"><span data-stu-id="29d28-141">6</span></span>  <br/> |<span data-ttu-id="29d28-142">1 </span><span class="sxs-lookup"><span data-stu-id="29d28-142">1</span></span>  <br/> |<span data-ttu-id="29d28-143">open</span><span class="sxs-lookup"><span data-stu-id="29d28-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="29d28-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="29d28-144">See also</span></span>

[<span data-ttu-id="29d28-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="29d28-145">tblNode</span></span>](tblnode.md)
