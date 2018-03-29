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
description: tblEnumAttribute 是一个硬编码表包含节点表中使用的可见性和行为特性。
ms.openlocfilehash: 24208b56aba586af500a2f659a2d5cbf1a47234d
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblenumattribute"></a><span data-ttu-id="78664-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="78664-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="78664-104">tblEnumAttribute 是一个硬编码表包含节点表中使用的可见性和行为特性。</span><span class="sxs-lookup"><span data-stu-id="78664-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="78664-105">**列**</span><span class="sxs-lookup"><span data-stu-id="78664-105">**Columns**</span></span>

|<span data-ttu-id="78664-106">**列**</span><span class="sxs-lookup"><span data-stu-id="78664-106">**Column**</span></span>|<span data-ttu-id="78664-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="78664-107">**Type**</span></span>|<span data-ttu-id="78664-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="78664-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="78664-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="78664-109">attributeID</span></span>  <br/> |<span data-ttu-id="78664-110">smallint，不为空</span><span class="sxs-lookup"><span data-stu-id="78664-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="78664-111">该属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="78664-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="78664-112">属性名称</span><span class="sxs-lookup"><span data-stu-id="78664-112">attributeName</span></span>  <br/> |<span data-ttu-id="78664-113">nvarchar (256) 不为空</span><span class="sxs-lookup"><span data-stu-id="78664-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="78664-114">该属性的名称。</span><span class="sxs-lookup"><span data-stu-id="78664-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="78664-115">**密钥**</span><span class="sxs-lookup"><span data-stu-id="78664-115">**Key**</span></span>

|<span data-ttu-id="78664-116">**列**</span><span class="sxs-lookup"><span data-stu-id="78664-116">**Column**</span></span>|<span data-ttu-id="78664-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="78664-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="78664-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="78664-118">attributeID</span></span>  <br/> |<span data-ttu-id="78664-119">为主键。</span><span class="sxs-lookup"><span data-stu-id="78664-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="78664-120">**表值**</span><span class="sxs-lookup"><span data-stu-id="78664-120">**Table Values**</span></span>

|<span data-ttu-id="78664-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="78664-121">**attributeID**</span></span>|<span data-ttu-id="78664-122">**属性名称**</span><span class="sxs-lookup"><span data-stu-id="78664-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="78664-123">1</span><span class="sxs-lookup"><span data-stu-id="78664-123">1</span></span>  <br/> |<span data-ttu-id="78664-124">可见性。</span><span class="sxs-lookup"><span data-stu-id="78664-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="78664-125">2</span><span class="sxs-lookup"><span data-stu-id="78664-125">2</span></span>  <br/> |<span data-ttu-id="78664-126">行为。</span><span class="sxs-lookup"><span data-stu-id="78664-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="78664-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="78664-127">See also</span></span>

#### 

[<span data-ttu-id="78664-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="78664-128">tblNode</span></span>](tblnode.md)

