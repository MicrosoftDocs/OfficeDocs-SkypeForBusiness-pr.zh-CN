---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute 是一个硬编码表, 其中包含在节点表中使用的 Visibility 和行为属性。
ms.openlocfilehash: b326ebe98592daccf7560dc90e299f31c158cd5c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295417"
---
# <a name="tblenumattribute"></a><span data-ttu-id="ee084-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="ee084-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="ee084-104">tblEnumAttribute 是一个硬编码表, 其中包含在节点表中使用的 Visibility 和行为属性。</span><span class="sxs-lookup"><span data-stu-id="ee084-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="ee084-105">**多**</span><span class="sxs-lookup"><span data-stu-id="ee084-105">**Columns**</span></span>

|<span data-ttu-id="ee084-106">**列**</span><span class="sxs-lookup"><span data-stu-id="ee084-106">**Column**</span></span>|<span data-ttu-id="ee084-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="ee084-107">**Type**</span></span>|<span data-ttu-id="ee084-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="ee084-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ee084-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="ee084-109">attributeID</span></span>  <br/> |<span data-ttu-id="ee084-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="ee084-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="ee084-111">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="ee084-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="ee084-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="ee084-112">attributeName</span></span>  <br/> |<span data-ttu-id="ee084-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="ee084-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="ee084-114">属性的名称。</span><span class="sxs-lookup"><span data-stu-id="ee084-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="ee084-115">**关键字**</span><span class="sxs-lookup"><span data-stu-id="ee084-115">**Key**</span></span>

|<span data-ttu-id="ee084-116">**列**</span><span class="sxs-lookup"><span data-stu-id="ee084-116">**Column**</span></span>|<span data-ttu-id="ee084-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="ee084-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ee084-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="ee084-118">attributeID</span></span>  <br/> |<span data-ttu-id="ee084-119">主键。</span><span class="sxs-lookup"><span data-stu-id="ee084-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="ee084-120">**表值**</span><span class="sxs-lookup"><span data-stu-id="ee084-120">**Table Values**</span></span>

|<span data-ttu-id="ee084-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="ee084-121">**attributeID**</span></span>|<span data-ttu-id="ee084-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="ee084-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ee084-123">1</span><span class="sxs-lookup"><span data-stu-id="ee084-123">1</span></span>  <br/> |<span data-ttu-id="ee084-124">了解.</span><span class="sxs-lookup"><span data-stu-id="ee084-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="ee084-125">2</span><span class="sxs-lookup"><span data-stu-id="ee084-125">2</span></span>  <br/> |<span data-ttu-id="ee084-126">现象.</span><span class="sxs-lookup"><span data-stu-id="ee084-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="ee084-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ee084-127">See also</span></span>

[<span data-ttu-id="ee084-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="ee084-128">tblNode</span></span>](tblnode.md)
