---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta 包含必须从 Active Directory 域服务刷新的主体。
ms.openlocfilehash: c76f4a74b3f627d360a2d745e46b6f2dac26bff0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813570"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="0753a-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="0753a-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="0753a-104">tblPrincipalMeta 包含必须从 Active Directory 域服务刷新的主体。</span><span class="sxs-lookup"><span data-stu-id="0753a-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="0753a-105">**多**</span><span class="sxs-lookup"><span data-stu-id="0753a-105">**Columns**</span></span>

|<span data-ttu-id="0753a-106">**列**</span><span class="sxs-lookup"><span data-stu-id="0753a-106">**Column**</span></span>|<span data-ttu-id="0753a-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="0753a-107">**Type**</span></span>|<span data-ttu-id="0753a-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="0753a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0753a-109">prinID</span><span class="sxs-lookup"><span data-stu-id="0753a-109">prinID</span></span>  <br/> |<span data-ttu-id="0753a-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="0753a-110">int, not null</span></span>  <br/> |<span data-ttu-id="0753a-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="0753a-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="0753a-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="0753a-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="0753a-113">位，not null</span><span class="sxs-lookup"><span data-stu-id="0753a-113">bit, not null</span></span>  <br/> |<span data-ttu-id="0753a-114">如果必须刷新主体隶属关系，则为 True。</span><span class="sxs-lookup"><span data-stu-id="0753a-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="0753a-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="0753a-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="0753a-116">位，not null</span><span class="sxs-lookup"><span data-stu-id="0753a-116">bit, not null</span></span>  <br/> |<span data-ttu-id="0753a-117">如果必须刷新主体属性，则为 True。</span><span class="sxs-lookup"><span data-stu-id="0753a-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="0753a-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="0753a-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="0753a-119">位，not null</span><span class="sxs-lookup"><span data-stu-id="0753a-119">bit, not null</span></span>  <br/> |<span data-ttu-id="0753a-120">如果主体已被删除，则为 True。</span><span class="sxs-lookup"><span data-stu-id="0753a-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="0753a-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="0753a-121">tryCount</span></span>  <br/> |<span data-ttu-id="0753a-122">int</span><span class="sxs-lookup"><span data-stu-id="0753a-122">int</span></span>  <br/> |<span data-ttu-id="0753a-123">尝试从目前为止发生的 AD DS 刷新主体的次数。</span><span class="sxs-lookup"><span data-stu-id="0753a-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="0753a-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="0753a-124">lastTry</span></span>  <br/> |<span data-ttu-id="0753a-125">datetime</span><span class="sxs-lookup"><span data-stu-id="0753a-125">datetime</span></span>  <br/> |<span data-ttu-id="0753a-126">从最新尝试刷新主体的时间戳。</span><span class="sxs-lookup"><span data-stu-id="0753a-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="0753a-127">如果尚未尝试刷新，则可以为 null。</span><span class="sxs-lookup"><span data-stu-id="0753a-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="0753a-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="0753a-128">nextTry</span></span>  <br/> |<span data-ttu-id="0753a-129">datetime</span><span class="sxs-lookup"><span data-stu-id="0753a-129">datetime</span></span>  <br/> |<span data-ttu-id="0753a-130">下一次计划刷新的时间戳。</span><span class="sxs-lookup"><span data-stu-id="0753a-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="0753a-131">如果尚未安排进一步刷新，则可以为 null。</span><span class="sxs-lookup"><span data-stu-id="0753a-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="0753a-132">**标示**</span><span class="sxs-lookup"><span data-stu-id="0753a-132">**Keys**</span></span>

|<span data-ttu-id="0753a-133">**列**</span><span class="sxs-lookup"><span data-stu-id="0753a-133">**Column**</span></span>|<span data-ttu-id="0753a-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="0753a-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0753a-135">prinID</span><span class="sxs-lookup"><span data-stu-id="0753a-135">prinID</span></span>  <br/> |<span data-ttu-id="0753a-136">主键。</span><span class="sxs-lookup"><span data-stu-id="0753a-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="0753a-137">prinID</span><span class="sxs-lookup"><span data-stu-id="0753a-137">prinID</span></span>  <br/> |<span data-ttu-id="0753a-138">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="0753a-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

