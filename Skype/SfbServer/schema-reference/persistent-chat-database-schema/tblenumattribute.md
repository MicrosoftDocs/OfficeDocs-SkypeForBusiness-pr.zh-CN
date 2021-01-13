---
title: tblEnumAttribute
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
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute 是一个硬编码表，包含用于节点表的 Visibility 和 Behavior 属性。
ms.openlocfilehash: 698eda1e6e815ad4de4042312be1738a3a41d1f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809712"
---
# <a name="tblenumattribute"></a><span data-ttu-id="30f58-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="30f58-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="30f58-104">tblEnumAttribute 是一个硬编码表，包含用于节点表的 Visibility 和 Behavior 属性。</span><span class="sxs-lookup"><span data-stu-id="30f58-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="30f58-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="30f58-105">**Columns**</span></span>

|<span data-ttu-id="30f58-106">**列**</span><span class="sxs-lookup"><span data-stu-id="30f58-106">**Column**</span></span>|<span data-ttu-id="30f58-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="30f58-107">**Type**</span></span>|<span data-ttu-id="30f58-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="30f58-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="30f58-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="30f58-109">attributeID</span></span>  <br/> |<span data-ttu-id="30f58-110">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="30f58-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="30f58-111">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="30f58-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="30f58-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="30f58-112">attributeName</span></span>  <br/> |<span data-ttu-id="30f58-113">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="30f58-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="30f58-114">属性的名称。</span><span class="sxs-lookup"><span data-stu-id="30f58-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="30f58-115">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="30f58-115">**Key**</span></span>

|<span data-ttu-id="30f58-116">**列**</span><span class="sxs-lookup"><span data-stu-id="30f58-116">**Column**</span></span>|<span data-ttu-id="30f58-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="30f58-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="30f58-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="30f58-118">attributeID</span></span>  <br/> |<span data-ttu-id="30f58-119">主键。</span><span class="sxs-lookup"><span data-stu-id="30f58-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="30f58-120">**表值**</span><span class="sxs-lookup"><span data-stu-id="30f58-120">**Table Values**</span></span>

|<span data-ttu-id="30f58-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="30f58-121">**attributeID**</span></span>|<span data-ttu-id="30f58-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="30f58-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="30f58-123">1 </span><span class="sxs-lookup"><span data-stu-id="30f58-123">1</span></span>  <br/> |<span data-ttu-id="30f58-124">可见性。</span><span class="sxs-lookup"><span data-stu-id="30f58-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="30f58-125">2 </span><span class="sxs-lookup"><span data-stu-id="30f58-125">2</span></span>  <br/> |<span data-ttu-id="30f58-126">行为。</span><span class="sxs-lookup"><span data-stu-id="30f58-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="30f58-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="30f58-127">See also</span></span>

[<span data-ttu-id="30f58-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="30f58-128">tblNode</span></span>](tblnode.md)
