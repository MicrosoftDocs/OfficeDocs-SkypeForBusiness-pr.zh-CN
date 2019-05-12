---
title: tblEnumValue
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a33df20c-d19d-4f5c-b012-29dab8fb9200
description: tblenumvalue 表是一个硬编码表，包含节点表使用的属性的 Visibility 和 Behavior 值。
ms.openlocfilehash: 00ee5a7a7538fa620e438ead5e986f859ef25a6c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929866"
---
# <a name="tblenumvalue"></a><span data-ttu-id="f051f-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="f051f-103">tblEnumValue</span></span>
 
<span data-ttu-id="f051f-104">tblenumvalue 表是一个硬编码表，包含节点表使用的属性的 Visibility 和 Behavior 值。</span><span class="sxs-lookup"><span data-stu-id="f051f-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="f051f-105">**列**</span><span class="sxs-lookup"><span data-stu-id="f051f-105">**Columns**</span></span>

|<span data-ttu-id="f051f-106">**列**</span><span class="sxs-lookup"><span data-stu-id="f051f-106">**Column**</span></span>|<span data-ttu-id="f051f-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="f051f-107">**Type**</span></span>|<span data-ttu-id="f051f-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="f051f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f051f-109">valueID</span><span class="sxs-lookup"><span data-stu-id="f051f-109">valueID</span></span>  <br/> |<span data-ttu-id="f051f-110">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="f051f-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="f051f-111">值的 ID。</span><span class="sxs-lookup"><span data-stu-id="f051f-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="f051f-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="f051f-112">attributeID</span></span>  <br/> |<span data-ttu-id="f051f-113">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="f051f-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="f051f-114">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="f051f-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="f051f-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="f051f-115">attributeValue</span></span>  <br/> |<span data-ttu-id="f051f-116">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="f051f-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="f051f-117">值的名称。</span><span class="sxs-lookup"><span data-stu-id="f051f-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="f051f-118">**键**</span><span class="sxs-lookup"><span data-stu-id="f051f-118">**Keys**</span></span>

|<span data-ttu-id="f051f-119">**列**</span><span class="sxs-lookup"><span data-stu-id="f051f-119">**Column**</span></span>|<span data-ttu-id="f051f-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="f051f-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f051f-121">valueID</span><span class="sxs-lookup"><span data-stu-id="f051f-121">valueID</span></span>  <br/> |<span data-ttu-id="f051f-122">主键。</span><span class="sxs-lookup"><span data-stu-id="f051f-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f051f-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="f051f-123">attributeID</span></span>  <br/> |<span data-ttu-id="f051f-124">在 tblEnumAttribute.attributeID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="f051f-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="f051f-125">**表值**</span><span class="sxs-lookup"><span data-stu-id="f051f-125">**Table Values**</span></span>

|<span data-ttu-id="f051f-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="f051f-126">**valueID**</span></span>|<span data-ttu-id="f051f-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="f051f-127">**attributeID**</span></span>|<span data-ttu-id="f051f-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="f051f-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f051f-129">2</span><span class="sxs-lookup"><span data-stu-id="f051f-129">2</span></span>  <br/> |<span data-ttu-id="f051f-130">1</span><span class="sxs-lookup"><span data-stu-id="f051f-130">1</span></span>  <br/> |<span data-ttu-id="f051f-131">专用</span><span class="sxs-lookup"><span data-stu-id="f051f-131">private</span></span>  <br/> |
|<span data-ttu-id="f051f-132">3</span><span class="sxs-lookup"><span data-stu-id="f051f-132">3</span></span>  <br/> |<span data-ttu-id="f051f-133">1</span><span class="sxs-lookup"><span data-stu-id="f051f-133">1</span></span>  <br/> |<span data-ttu-id="f051f-134">范围</span><span class="sxs-lookup"><span data-stu-id="f051f-134">scope</span></span>  <br/> |
|<span data-ttu-id="f051f-135">4</span><span class="sxs-lookup"><span data-stu-id="f051f-135">4</span></span>  <br/> |<span data-ttu-id="f051f-136">2</span><span class="sxs-lookup"><span data-stu-id="f051f-136">2</span></span>  <br/> |<span data-ttu-id="f051f-137">普通</span><span class="sxs-lookup"><span data-stu-id="f051f-137">normal</span></span>  <br/> |
|<span data-ttu-id="f051f-138">5</span><span class="sxs-lookup"><span data-stu-id="f051f-138">5</span></span>  <br/> |<span data-ttu-id="f051f-139">2</span><span class="sxs-lookup"><span data-stu-id="f051f-139">2</span></span>  <br/> |<span data-ttu-id="f051f-140">大会堂</span><span class="sxs-lookup"><span data-stu-id="f051f-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="f051f-141">6</span><span class="sxs-lookup"><span data-stu-id="f051f-141">6</span></span>  <br/> |<span data-ttu-id="f051f-142">1</span><span class="sxs-lookup"><span data-stu-id="f051f-142">1</span></span>  <br/> |<span data-ttu-id="f051f-143">打开</span><span class="sxs-lookup"><span data-stu-id="f051f-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="f051f-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f051f-144">See also</span></span>

[<span data-ttu-id="f051f-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="f051f-145">tblNode</span></span>](tblnode.md)
