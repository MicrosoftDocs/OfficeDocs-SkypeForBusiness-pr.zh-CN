---
title: tblEnumValue
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue 是一个包含节点表中使用的属性的可见性和行为的值的硬编码表。
ms.openlocfilehash: 4957f87401dc93cc98d18fa5b1844e13daaefabd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblenumvalue"></a><span data-ttu-id="6c316-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="6c316-103">tblEnumValue</span></span>
 
<span data-ttu-id="6c316-104">tblEnumValue 是一个包含节点表中使用的属性的可见性和行为的值的硬编码表。</span><span class="sxs-lookup"><span data-stu-id="6c316-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="6c316-105">**列**</span><span class="sxs-lookup"><span data-stu-id="6c316-105">**Columns**</span></span>

|<span data-ttu-id="6c316-106">**列**</span><span class="sxs-lookup"><span data-stu-id="6c316-106">**Column**</span></span>|<span data-ttu-id="6c316-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="6c316-107">**Type**</span></span>|<span data-ttu-id="6c316-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="6c316-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6c316-109">valueID</span><span class="sxs-lookup"><span data-stu-id="6c316-109">valueID</span></span>  <br/> |<span data-ttu-id="6c316-110">smallint，不为空</span><span class="sxs-lookup"><span data-stu-id="6c316-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="6c316-111">ID 的值。</span><span class="sxs-lookup"><span data-stu-id="6c316-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="6c316-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="6c316-112">attributeID</span></span>  <br/> |<span data-ttu-id="6c316-113">smallint，不为空</span><span class="sxs-lookup"><span data-stu-id="6c316-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="6c316-114">该属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="6c316-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="6c316-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="6c316-115">attributeValue</span></span>  <br/> |<span data-ttu-id="6c316-116">nvarchar (256) 不为空</span><span class="sxs-lookup"><span data-stu-id="6c316-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="6c316-117">值的名称。</span><span class="sxs-lookup"><span data-stu-id="6c316-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="6c316-118">**密钥**</span><span class="sxs-lookup"><span data-stu-id="6c316-118">**Keys**</span></span>

|<span data-ttu-id="6c316-119">**列**</span><span class="sxs-lookup"><span data-stu-id="6c316-119">**Column**</span></span>|<span data-ttu-id="6c316-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="6c316-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6c316-121">valueID</span><span class="sxs-lookup"><span data-stu-id="6c316-121">valueID</span></span>  <br/> |<span data-ttu-id="6c316-122">为主键。</span><span class="sxs-lookup"><span data-stu-id="6c316-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="6c316-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="6c316-123">attributeID</span></span>  <br/> |<span data-ttu-id="6c316-124">TblEnumAttribute.attributeID 表中查找与外键。</span><span class="sxs-lookup"><span data-stu-id="6c316-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="6c316-125">**表值**</span><span class="sxs-lookup"><span data-stu-id="6c316-125">**Table Values**</span></span>

|<span data-ttu-id="6c316-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="6c316-126">**valueID**</span></span>|<span data-ttu-id="6c316-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="6c316-127">**attributeID**</span></span>|<span data-ttu-id="6c316-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="6c316-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6c316-129">2</span><span class="sxs-lookup"><span data-stu-id="6c316-129">2</span></span>  <br/> |<span data-ttu-id="6c316-130">1</span><span class="sxs-lookup"><span data-stu-id="6c316-130">1</span></span>  <br/> |<span data-ttu-id="6c316-131">专用</span><span class="sxs-lookup"><span data-stu-id="6c316-131">private</span></span>  <br/> |
|<span data-ttu-id="6c316-132">3</span><span class="sxs-lookup"><span data-stu-id="6c316-132">3</span></span>  <br/> |<span data-ttu-id="6c316-133">1</span><span class="sxs-lookup"><span data-stu-id="6c316-133">1</span></span>  <br/> |<span data-ttu-id="6c316-134">作用域</span><span class="sxs-lookup"><span data-stu-id="6c316-134">scope</span></span>  <br/> |
|<span data-ttu-id="6c316-135">4</span><span class="sxs-lookup"><span data-stu-id="6c316-135">4</span></span>  <br/> |<span data-ttu-id="6c316-136">2</span><span class="sxs-lookup"><span data-stu-id="6c316-136">2</span></span>  <br/> |<span data-ttu-id="6c316-137">正常</span><span class="sxs-lookup"><span data-stu-id="6c316-137">normal</span></span>  <br/> |
|<span data-ttu-id="6c316-138">5</span><span class="sxs-lookup"><span data-stu-id="6c316-138">5</span></span>  <br/> |<span data-ttu-id="6c316-139">2</span><span class="sxs-lookup"><span data-stu-id="6c316-139">2</span></span>  <br/> |<span data-ttu-id="6c316-140">大会堂</span><span class="sxs-lookup"><span data-stu-id="6c316-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="6c316-141">6</span><span class="sxs-lookup"><span data-stu-id="6c316-141">6</span></span>  <br/> |<span data-ttu-id="6c316-142">1</span><span class="sxs-lookup"><span data-stu-id="6c316-142">1</span></span>  <br/> |<span data-ttu-id="6c316-143">打开</span><span class="sxs-lookup"><span data-stu-id="6c316-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6c316-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6c316-144">See also</span></span>

#### 

[<span data-ttu-id="6c316-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="6c316-145">tblNode</span></span>](tblnode.md)

