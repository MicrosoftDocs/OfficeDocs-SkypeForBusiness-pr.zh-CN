---
title: tblEnumAttribute
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
ms.openlocfilehash: bd386bc77d15c627597a5680277235a05d0c8039
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2018
ms.locfileid: "19504864"
---
# <a name="tblenumattribute"></a><span data-ttu-id="e2e4c-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="e2e4c-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="e2e4c-104">tblEnumAttribute 是一个硬编码表，包含用于节点表的 Visibility 和 Behavior 属性。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="e2e4c-105">**列**</span><span class="sxs-lookup"><span data-stu-id="e2e4c-105">**Columns**</span></span>

|<span data-ttu-id="e2e4c-106">**列**</span><span class="sxs-lookup"><span data-stu-id="e2e4c-106">**Column**</span></span>|<span data-ttu-id="e2e4c-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="e2e4c-107">**Type**</span></span>|<span data-ttu-id="e2e4c-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="e2e4c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e2e4c-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="e2e4c-109">attributeID</span></span>  <br/> |<span data-ttu-id="e2e4c-110">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="e2e4c-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="e2e4c-111">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="e2e4c-112">属性名称</span><span class="sxs-lookup"><span data-stu-id="e2e4c-112">attributeName</span></span>  <br/> |<span data-ttu-id="e2e4c-113">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="e2e4c-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="e2e4c-114">属性的名称。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="e2e4c-115">**关键字**</span><span class="sxs-lookup"><span data-stu-id="e2e4c-115">**Key**</span></span>

|<span data-ttu-id="e2e4c-116">**列**</span><span class="sxs-lookup"><span data-stu-id="e2e4c-116">**Column**</span></span>|<span data-ttu-id="e2e4c-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="e2e4c-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e2e4c-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="e2e4c-118">attributeID</span></span>  <br/> |<span data-ttu-id="e2e4c-119">主键。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="e2e4c-120">**表值**</span><span class="sxs-lookup"><span data-stu-id="e2e4c-120">**Table Values**</span></span>

|<span data-ttu-id="e2e4c-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="e2e4c-121">**attributeID**</span></span>|<span data-ttu-id="e2e4c-122">**属性名称**</span><span class="sxs-lookup"><span data-stu-id="e2e4c-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e2e4c-123">1</span><span class="sxs-lookup"><span data-stu-id="e2e4c-123">1</span></span>  <br/> |<span data-ttu-id="e2e4c-124">可见性。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="e2e4c-125">2</span><span class="sxs-lookup"><span data-stu-id="e2e4c-125">2</span></span>  <br/> |<span data-ttu-id="e2e4c-126">行为。</span><span class="sxs-lookup"><span data-stu-id="e2e4c-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e2e4c-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e2e4c-127">See also</span></span>

[<span data-ttu-id="e2e4c-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="e2e4c-128">tblNode</span></span>](tblnode.md)