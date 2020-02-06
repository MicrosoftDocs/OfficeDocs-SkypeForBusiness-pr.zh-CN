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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 17f8b87e-36a6-4f6a-8630-7c76b61a7595
description: tblEnumAttribute 是一个硬编码表，其中包含在节点表中使用的 Visibility 和行为属性。
ms.openlocfilehash: 8244e2fb6ace6c4ed73f017f52df0c85d1f02315
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814610"
---
# <a name="tblenumattribute"></a><span data-ttu-id="b4811-103">tblEnumAttribute</span><span class="sxs-lookup"><span data-stu-id="b4811-103">tblEnumAttribute</span></span>
 
<span data-ttu-id="b4811-104">tblEnumAttribute 是一个硬编码表，其中包含在节点表中使用的 Visibility 和行为属性。</span><span class="sxs-lookup"><span data-stu-id="b4811-104">tblEnumAttribute is a hardcoded table that contains the Visibility and Behavior attributes that are used in the Node table.</span></span>
  
<span data-ttu-id="b4811-105">**多**</span><span class="sxs-lookup"><span data-stu-id="b4811-105">**Columns**</span></span>

|<span data-ttu-id="b4811-106">**列**</span><span class="sxs-lookup"><span data-stu-id="b4811-106">**Column**</span></span>|<span data-ttu-id="b4811-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="b4811-107">**Type**</span></span>|<span data-ttu-id="b4811-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="b4811-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b4811-109">attributeID</span><span class="sxs-lookup"><span data-stu-id="b4811-109">attributeID</span></span>  <br/> |<span data-ttu-id="b4811-110">smallint，not null</span><span class="sxs-lookup"><span data-stu-id="b4811-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="b4811-111">属性的 ID。</span><span class="sxs-lookup"><span data-stu-id="b4811-111">ID of the attribute.</span></span>  <br/> |
|<span data-ttu-id="b4811-112">attributeName</span><span class="sxs-lookup"><span data-stu-id="b4811-112">attributeName</span></span>  <br/> |<span data-ttu-id="b4811-113">nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="b4811-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="b4811-114">属性的名称。</span><span class="sxs-lookup"><span data-stu-id="b4811-114">Name of the attribute.</span></span>  <br/> |
   
<span data-ttu-id="b4811-115">**Key**</span><span class="sxs-lookup"><span data-stu-id="b4811-115">**Key**</span></span>

|<span data-ttu-id="b4811-116">**列**</span><span class="sxs-lookup"><span data-stu-id="b4811-116">**Column**</span></span>|<span data-ttu-id="b4811-117">**说明**</span><span class="sxs-lookup"><span data-stu-id="b4811-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b4811-118">attributeID</span><span class="sxs-lookup"><span data-stu-id="b4811-118">attributeID</span></span>  <br/> |<span data-ttu-id="b4811-119">主键。</span><span class="sxs-lookup"><span data-stu-id="b4811-119">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="b4811-120">**表值**</span><span class="sxs-lookup"><span data-stu-id="b4811-120">**Table Values**</span></span>

|<span data-ttu-id="b4811-121">**attributeID**</span><span class="sxs-lookup"><span data-stu-id="b4811-121">**attributeID**</span></span>|<span data-ttu-id="b4811-122">**attributeName**</span><span class="sxs-lookup"><span data-stu-id="b4811-122">**attributeName**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b4811-123">1</span><span class="sxs-lookup"><span data-stu-id="b4811-123">1</span></span>  <br/> |<span data-ttu-id="b4811-124">了解.</span><span class="sxs-lookup"><span data-stu-id="b4811-124">Visibility.</span></span>  <br/> |
|<span data-ttu-id="b4811-125">ppls-2</span><span class="sxs-lookup"><span data-stu-id="b4811-125">2</span></span>  <br/> |<span data-ttu-id="b4811-126">现象.</span><span class="sxs-lookup"><span data-stu-id="b4811-126">Behavior.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="b4811-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b4811-127">See also</span></span>

[<span data-ttu-id="b4811-128">tblNode</span><span class="sxs-lookup"><span data-stu-id="b4811-128">tblNode</span></span>](tblnode.md)
