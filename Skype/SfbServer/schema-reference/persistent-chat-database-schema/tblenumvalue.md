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
description: tblenumvalue 表是一个硬编码表，包含节点表使用的属性的 Visibility 和 Behavior 值。
ms.openlocfilehash: 4e17e5fc167342c106e7b5354d90c7fc284785c3
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505074"
---
# <a name="tblenumvalue"></a><span data-ttu-id="5bb19-103">tblEnumValue</span><span class="sxs-lookup"><span data-stu-id="5bb19-103">tblEnumValue</span></span>
 
<span data-ttu-id="5bb19-104">tblenumvalue 表是一个硬编码表，包含节点表使用的属性的 Visibility 和 Behavior 值。</span><span class="sxs-lookup"><span data-stu-id="5bb19-104">tblEnumValue is a hardcoded table that contains the Visibility and Behavior values of the attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="5bb19-105">**列**</span><span class="sxs-lookup"><span data-stu-id="5bb19-105">**Columns**</span></span>

|<span data-ttu-id="5bb19-106">**列**</span><span class="sxs-lookup"><span data-stu-id="5bb19-106">**Column**</span></span>|<span data-ttu-id="5bb19-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="5bb19-107">**Type**</span></span>|<span data-ttu-id="5bb19-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="5bb19-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5bb19-109">valueID</span><span class="sxs-lookup"><span data-stu-id="5bb19-109">valueID</span></span>  <br/> |<span data-ttu-id="5bb19-110">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="5bb19-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="5bb19-111">值的 ID。</span><span class="sxs-lookup"><span data-stu-id="5bb19-111">ID of the value.</span></span>  <br/> |
|<span data-ttu-id="5bb19-112">attributeID</span><span class="sxs-lookup"><span data-stu-id="5bb19-112">attributeID</span></span>  <br/> |<span data-ttu-id="5bb19-113">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="5bb19-113">smallint, not null</span></span>  <br/> |<span data-ttu-id="5bb19-114">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="5bb19-114">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="5bb19-115">attributeValue</span><span class="sxs-lookup"><span data-stu-id="5bb19-115">attributeValue</span></span>  <br/> |<span data-ttu-id="5bb19-116">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="5bb19-116">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="5bb19-117">值的名称。</span><span class="sxs-lookup"><span data-stu-id="5bb19-117">Name of the value.</span></span>  <br/> |
   
<span data-ttu-id="5bb19-118">**键**</span><span class="sxs-lookup"><span data-stu-id="5bb19-118">**Keys**</span></span>

|<span data-ttu-id="5bb19-119">**列**</span><span class="sxs-lookup"><span data-stu-id="5bb19-119">**Column**</span></span>|<span data-ttu-id="5bb19-120">**说明**</span><span class="sxs-lookup"><span data-stu-id="5bb19-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5bb19-121">valueID</span><span class="sxs-lookup"><span data-stu-id="5bb19-121">valueID</span></span>  <br/> |<span data-ttu-id="5bb19-122">主键。</span><span class="sxs-lookup"><span data-stu-id="5bb19-122">Primary key.</span></span>  <br/> |
|<span data-ttu-id="5bb19-123">attributeID</span><span class="sxs-lookup"><span data-stu-id="5bb19-123">attributeID</span></span>  <br/> |<span data-ttu-id="5bb19-124">在 tblEnumAttribute.attributeID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="5bb19-124">Foreign key with lookup in tblEnumAttribute.attributeID table.</span></span>  <br/> |
   
<span data-ttu-id="5bb19-125">**表值**</span><span class="sxs-lookup"><span data-stu-id="5bb19-125">**Table Values**</span></span>

|<span data-ttu-id="5bb19-126">**valueID**</span><span class="sxs-lookup"><span data-stu-id="5bb19-126">**valueID**</span></span>|<span data-ttu-id="5bb19-127">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="5bb19-127">**attributeID**</span></span>|<span data-ttu-id="5bb19-128">**attributeValue**</span><span class="sxs-lookup"><span data-stu-id="5bb19-128">**attributeValue**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5bb19-129">2</span><span class="sxs-lookup"><span data-stu-id="5bb19-129">2</span></span>  <br/> |<span data-ttu-id="5bb19-130">1</span><span class="sxs-lookup"><span data-stu-id="5bb19-130">1</span></span>  <br/> |<span data-ttu-id="5bb19-131">专用</span><span class="sxs-lookup"><span data-stu-id="5bb19-131">private</span></span>  <br/> |
|<span data-ttu-id="5bb19-132">3</span><span class="sxs-lookup"><span data-stu-id="5bb19-132">3</span></span>  <br/> |<span data-ttu-id="5bb19-133">1</span><span class="sxs-lookup"><span data-stu-id="5bb19-133">1</span></span>  <br/> |<span data-ttu-id="5bb19-134">范围</span><span class="sxs-lookup"><span data-stu-id="5bb19-134">scope</span></span>  <br/> |
|<span data-ttu-id="5bb19-135">4</span><span class="sxs-lookup"><span data-stu-id="5bb19-135">4</span></span>  <br/> |<span data-ttu-id="5bb19-136">2</span><span class="sxs-lookup"><span data-stu-id="5bb19-136">2</span></span>  <br/> |<span data-ttu-id="5bb19-137">普通</span><span class="sxs-lookup"><span data-stu-id="5bb19-137">normal</span></span>  <br/> |
|<span data-ttu-id="5bb19-138">5</span><span class="sxs-lookup"><span data-stu-id="5bb19-138">5</span></span>  <br/> |<span data-ttu-id="5bb19-139">2</span><span class="sxs-lookup"><span data-stu-id="5bb19-139">2</span></span>  <br/> |<span data-ttu-id="5bb19-140">大会堂</span><span class="sxs-lookup"><span data-stu-id="5bb19-140">auditorium</span></span>  <br/> |
|<span data-ttu-id="5bb19-141">6</span><span class="sxs-lookup"><span data-stu-id="5bb19-141">6</span></span>  <br/> |<span data-ttu-id="5bb19-142">1</span><span class="sxs-lookup"><span data-stu-id="5bb19-142">1</span></span>  <br/> |<span data-ttu-id="5bb19-143">打开</span><span class="sxs-lookup"><span data-stu-id="5bb19-143">open</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="5bb19-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5bb19-144">See also</span></span>

[<span data-ttu-id="5bb19-145">tblNode</span><span class="sxs-lookup"><span data-stu-id="5bb19-145">tblNode</span></span>](tblnode.md)