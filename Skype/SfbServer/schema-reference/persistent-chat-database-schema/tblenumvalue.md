---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue 是一个硬编码表, 其中包含在节点表中使用的属性的可见性和行为值。
ms.openlocfilehash: bf1ddf75fc7b7fd78c85f47626b465a4d74e5ca2
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295424"
---
# <a name="tblenumvalue"></a><span data-ttu-id="0e5eb-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="0e5eb-103">tblEnumValue</span></span>
 
<span data-ttu-id="0e5eb-104">tblEnumValue 是一个硬编码表, 其中包含在节点表中使用的属性的可见性和行为值。</span><span class="sxs-lookup"><span data-stu-id="0e5eb-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="0e5eb-105">**多**</span><span class="sxs-lookup"><span data-stu-id="0e5eb-105">**Columns**</span></span>

|<span data-ttu-id="0e5eb-106">**列**</span><span class="sxs-lookup"><span data-stu-id="0e5eb-106">**Column**</span></span>|<span data-ttu-id="0e5eb-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="0e5eb-107">**Type**</span></span>|<span data-ttu-id="0e5eb-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="0e5eb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0e5eb-109">valueID</span><span class="sxs-lookup"><span data-stu-id="0e5eb-109">valueID</span></span>  <br/> |<span data-ttu-id="0e5eb-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="0e5eb-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="0e5eb-111">值的 ID。</span><span class="sxs-lookup"><span data-stu-id="0e5eb-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="0e5eb-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="0e5eb-112">attributeID</span></span>  <br/> |<span data-ttu-id="0e5eb-113">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="0e5eb-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="0e5eb-114">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="0e5eb-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="0e5eb-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="0e5eb-115">attributeValue</span></span>  <br/> |<span data-ttu-id="0e5eb-116">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="0e5eb-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="0e5eb-117">值的名称。</span><span class="sxs-lookup"><span data-stu-id="0e5eb-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="0e5eb-118">**标示**</span><span class="sxs-lookup"><span data-stu-id="0e5eb-118">**Keys**</span></span>

|<span data-ttu-id="0e5eb-119">**列**</span><span class="sxs-lookup"><span data-stu-id="0e5eb-119">**Column**</span></span>|<span data-ttu-id="0e5eb-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="0e5eb-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0e5eb-121">valueID</span><span class="sxs-lookup"><span data-stu-id="0e5eb-121">valueID</span></span>  <br/> |<span data-ttu-id="0e5eb-122">主键。</span><span class="sxs-lookup"><span data-stu-id="0e5eb-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="0e5eb-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="0e5eb-123">attributeID</span></span>  <br/> |<span data-ttu-id="0e5eb-124">TblEnumAttribute 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="0e5eb-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="0e5eb-125">**表值**</span><span class="sxs-lookup"><span data-stu-id="0e5eb-125">**Table Values**</span></span>

|<span data-ttu-id="0e5eb-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="0e5eb-126">**valueID**</span></span>|<span data-ttu-id="0e5eb-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="0e5eb-127">**attributeID**</span></span>|<span data-ttu-id="0e5eb-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="0e5eb-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0e5eb-129">2</span><span class="sxs-lookup"><span data-stu-id="0e5eb-129">2</span></span>  <br/> |<span data-ttu-id="0e5eb-130">1</span><span class="sxs-lookup"><span data-stu-id="0e5eb-130">1</span></span>  <br/> |<span data-ttu-id="0e5eb-131">专用</span><span class="sxs-lookup"><span data-stu-id="0e5eb-131">private</span></span>  <br/> |
|<span data-ttu-id="0e5eb-132">3</span><span class="sxs-lookup"><span data-stu-id="0e5eb-132">3</span></span>  <br/> |<span data-ttu-id="0e5eb-133">1</span><span class="sxs-lookup"><span data-stu-id="0e5eb-133">1</span></span>  <br/> |<span data-ttu-id="0e5eb-134">范畴</span><span class="sxs-lookup"><span data-stu-id="0e5eb-134">scope</span></span>  <br/> |
|<span data-ttu-id="0e5eb-135">4</span><span class="sxs-lookup"><span data-stu-id="0e5eb-135">4</span></span>  <br/> |<span data-ttu-id="0e5eb-136">2</span><span class="sxs-lookup"><span data-stu-id="0e5eb-136">2</span></span>  <br/> |<span data-ttu-id="0e5eb-137">垂直</span><span class="sxs-lookup"><span data-stu-id="0e5eb-137">normal</span></span>  <br/> |
|<span data-ttu-id="0e5eb-138">5</span><span class="sxs-lookup"><span data-stu-id="0e5eb-138">5</span></span>  <br/> |<span data-ttu-id="0e5eb-139">2</span><span class="sxs-lookup"><span data-stu-id="0e5eb-139">2</span></span>  <br/> |<span data-ttu-id="0e5eb-140">auditorium</span><span class="sxs-lookup"><span data-stu-id="0e5eb-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="0e5eb-141">6</span><span class="sxs-lookup"><span data-stu-id="0e5eb-141">6</span></span>  <br/> |<span data-ttu-id="0e5eb-142">1</span><span class="sxs-lookup"><span data-stu-id="0e5eb-142">1</span></span>  <br/> |<span data-ttu-id="0e5eb-143">公开</span><span class="sxs-lookup"><span data-stu-id="0e5eb-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0e5eb-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0e5eb-144">See also</span></span>

[<span data-ttu-id="0e5eb-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="0e5eb-145">tblNode</span></span>](tblnode.md)
