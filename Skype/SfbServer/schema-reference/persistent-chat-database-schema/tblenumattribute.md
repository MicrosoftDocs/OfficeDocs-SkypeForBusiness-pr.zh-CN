---
title: tblEnumAttribute
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute 是一个硬编码表，包含用于节点表的 Visibility 和 Behavior 属性。
ms.openlocfilehash: 7555656f02fa7808e54100c03de8f80e0e078678
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879697"
---
# <a name="tblenumattribute"></a><span data-ttu-id="b8f33-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="b8f33-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="b8f33-104">tblEnumAttribute 是一个硬编码表，包含用于节点表的 Visibility 和 Behavior 属性。</span><span class="sxs-lookup"><span data-stu-id="b8f33-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="b8f33-105">**列**</span><span class="sxs-lookup"><span data-stu-id="b8f33-105">**Columns**</span></span>

|<span data-ttu-id="b8f33-106">**列**</span><span class="sxs-lookup"><span data-stu-id="b8f33-106">**Column**</span></span>|<span data-ttu-id="b8f33-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="b8f33-107">**Type**</span></span>|<span data-ttu-id="b8f33-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="b8f33-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b8f33-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="b8f33-109">attributeID</span></span>  <br/> |<span data-ttu-id="b8f33-110">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="b8f33-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="b8f33-111">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="b8f33-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="b8f33-112">属性名称</span><span class="sxs-lookup"><span data-stu-id="b8f33-112">attributeName</span></span>  <br/> |<span data-ttu-id="b8f33-113">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="b8f33-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="b8f33-114">属性的名称。</span><span class="sxs-lookup"><span data-stu-id="b8f33-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="b8f33-115">**关键字**</span><span class="sxs-lookup"><span data-stu-id="b8f33-115">**Key**</span></span>

|<span data-ttu-id="b8f33-116">**列**</span><span class="sxs-lookup"><span data-stu-id="b8f33-116">**Column**</span></span>|<span data-ttu-id="b8f33-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="b8f33-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b8f33-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="b8f33-118">attributeID</span></span>  <br/> |<span data-ttu-id="b8f33-119">主键。</span><span class="sxs-lookup"><span data-stu-id="b8f33-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="b8f33-120">**表值**</span><span class="sxs-lookup"><span data-stu-id="b8f33-120">**Table Values**</span></span>

|<span data-ttu-id="b8f33-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="b8f33-121">**attributeID**</span></span>|<span data-ttu-id="b8f33-122">**属性名称**</span><span class="sxs-lookup"><span data-stu-id="b8f33-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b8f33-123">1</span><span class="sxs-lookup"><span data-stu-id="b8f33-123">1</span></span>  <br/> |<span data-ttu-id="b8f33-124">可见性。</span><span class="sxs-lookup"><span data-stu-id="b8f33-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="b8f33-125">2</span><span class="sxs-lookup"><span data-stu-id="b8f33-125">2</span></span>  <br/> |<span data-ttu-id="b8f33-126">行为。</span><span class="sxs-lookup"><span data-stu-id="b8f33-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b8f33-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b8f33-127">See also</span></span>

[<span data-ttu-id="b8f33-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="b8f33-128">tblNode</span></span>](tblnode.md)
