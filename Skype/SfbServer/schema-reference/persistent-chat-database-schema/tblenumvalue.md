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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblEnumValue 是一个硬编码表，其中包含在节点表中使用的属性的可见性和行为值。
ms.openlocfilehash: accb9cb4801984bd4b3839cd44e5b7feb8d06baa
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814600"
---
# <a name="tblenumvalue"></a><span data-ttu-id="2e543-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="2e543-103">tblEnumValue</span></span>
 
<span data-ttu-id="2e543-104">tblEnumValue 是一个硬编码表，其中包含在节点表中使用的属性的可见性和行为值。</span><span class="sxs-lookup"><span data-stu-id="2e543-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="2e543-105">**多**</span><span class="sxs-lookup"><span data-stu-id="2e543-105">**Columns**</span></span>

|<span data-ttu-id="2e543-106">**列**</span><span class="sxs-lookup"><span data-stu-id="2e543-106">**Column**</span></span>|<span data-ttu-id="2e543-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="2e543-107">**Type**</span></span>|<span data-ttu-id="2e543-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="2e543-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2e543-109">valueID</span><span class="sxs-lookup"><span data-stu-id="2e543-109">valueID</span></span>  <br/> |<span data-ttu-id="2e543-110">smallint，not null</span><span class="sxs-lookup"><span data-stu-id="2e543-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="2e543-111">值的 ID。</span><span class="sxs-lookup"><span data-stu-id="2e543-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="2e543-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="2e543-112">attributeID</span></span>  <br/> |<span data-ttu-id="2e543-113">smallint，not null</span><span class="sxs-lookup"><span data-stu-id="2e543-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="2e543-114">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="2e543-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="2e543-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="2e543-115">attributeValue</span></span>  <br/> |<span data-ttu-id="2e543-116">nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="2e543-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="2e543-117">值的名称。</span><span class="sxs-lookup"><span data-stu-id="2e543-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="2e543-118">**标示**</span><span class="sxs-lookup"><span data-stu-id="2e543-118">**Keys**</span></span>

|<span data-ttu-id="2e543-119">**列**</span><span class="sxs-lookup"><span data-stu-id="2e543-119">**Column**</span></span>|<span data-ttu-id="2e543-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="2e543-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2e543-121">valueID</span><span class="sxs-lookup"><span data-stu-id="2e543-121">valueID</span></span>  <br/> |<span data-ttu-id="2e543-122">主键。</span><span class="sxs-lookup"><span data-stu-id="2e543-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="2e543-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="2e543-123">attributeID</span></span>  <br/> |<span data-ttu-id="2e543-124">TblEnumAttribute 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="2e543-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="2e543-125">**表值**</span><span class="sxs-lookup"><span data-stu-id="2e543-125">**Table Values**</span></span>

|<span data-ttu-id="2e543-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="2e543-126">**valueID**</span></span>|<span data-ttu-id="2e543-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="2e543-127">**attributeID**</span></span>|<span data-ttu-id="2e543-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="2e543-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2e543-129">ppls-2</span><span class="sxs-lookup"><span data-stu-id="2e543-129">2</span></span>  <br/> |<span data-ttu-id="2e543-130">1</span><span class="sxs-lookup"><span data-stu-id="2e543-130">1</span></span>  <br/> |<span data-ttu-id="2e543-131">专用</span><span class="sxs-lookup"><span data-stu-id="2e543-131">private</span></span>  <br/> |
|<span data-ttu-id="2e543-132">3</span><span class="sxs-lookup"><span data-stu-id="2e543-132">3</span></span>  <br/> |<span data-ttu-id="2e543-133">1</span><span class="sxs-lookup"><span data-stu-id="2e543-133">1</span></span>  <br/> |<span data-ttu-id="2e543-134">范畴</span><span class="sxs-lookup"><span data-stu-id="2e543-134">scope</span></span>  <br/> |
|<span data-ttu-id="2e543-135">4</span><span class="sxs-lookup"><span data-stu-id="2e543-135">4</span></span>  <br/> |<span data-ttu-id="2e543-136">ppls-2</span><span class="sxs-lookup"><span data-stu-id="2e543-136">2</span></span>  <br/> |<span data-ttu-id="2e543-137">垂直</span><span class="sxs-lookup"><span data-stu-id="2e543-137">normal</span></span>  <br/> |
|<span data-ttu-id="2e543-138">5</span><span class="sxs-lookup"><span data-stu-id="2e543-138">5</span></span>  <br/> |<span data-ttu-id="2e543-139">ppls-2</span><span class="sxs-lookup"><span data-stu-id="2e543-139">2</span></span>  <br/> |<span data-ttu-id="2e543-140">auditorium</span><span class="sxs-lookup"><span data-stu-id="2e543-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="2e543-141">6</span><span class="sxs-lookup"><span data-stu-id="2e543-141">6</span></span>  <br/> |<span data-ttu-id="2e543-142">1</span><span class="sxs-lookup"><span data-stu-id="2e543-142">1</span></span>  <br/> |<span data-ttu-id="2e543-143">公开</span><span class="sxs-lookup"><span data-stu-id="2e543-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="2e543-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2e543-144">See also</span></span>

[<span data-ttu-id="2e543-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="2e543-145">tblNode</span></span>](tblnode.md)
