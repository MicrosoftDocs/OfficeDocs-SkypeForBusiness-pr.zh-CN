---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta 包含必须从 Active Directory 域服务刷新的主体。
ms.openlocfilehash: e10b56a8a3a1c25f73cd1a07f4fdcde18c6f1215
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831542"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="c081c-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="c081c-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="c081c-104">tblPrincipalMeta 包含必须从 Active Directory 域服务刷新的主体。</span><span class="sxs-lookup"><span data-stu-id="c081c-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="c081c-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="c081c-105">**Columns**</span></span>

|<span data-ttu-id="c081c-106">**列**</span><span class="sxs-lookup"><span data-stu-id="c081c-106">**Column**</span></span>|<span data-ttu-id="c081c-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="c081c-107">**Type**</span></span>|<span data-ttu-id="c081c-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="c081c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c081c-109">prinID</span><span class="sxs-lookup"><span data-stu-id="c081c-109">prinID</span></span>  <br/> |<span data-ttu-id="c081c-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="c081c-110">int, not null</span></span>  <br/> |<span data-ttu-id="c081c-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="c081c-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="c081c-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="c081c-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="c081c-113">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="c081c-113">bit, not null</span></span>  <br/> |<span data-ttu-id="c081c-114">如果必须刷新主体附属关系，则为 True。</span><span class="sxs-lookup"><span data-stu-id="c081c-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="c081c-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="c081c-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="c081c-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="c081c-116">bit, not null</span></span>  <br/> |<span data-ttu-id="c081c-117">如果必须刷新主体属性，则为 True。</span><span class="sxs-lookup"><span data-stu-id="c081c-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="c081c-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="c081c-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="c081c-119">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="c081c-119">bit, not null</span></span>  <br/> |<span data-ttu-id="c081c-120">如果主体已删除，则为 True。</span><span class="sxs-lookup"><span data-stu-id="c081c-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="c081c-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="c081c-121">tryCount</span></span>  <br/> |<span data-ttu-id="c081c-122">int</span><span class="sxs-lookup"><span data-stu-id="c081c-122">int</span></span>  <br/> |<span data-ttu-id="c081c-123">截止目前，已发生的尝试从 AD DS 刷新主体的次数。</span><span class="sxs-lookup"><span data-stu-id="c081c-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="c081c-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="c081c-124">lastTry</span></span>  <br/> |<span data-ttu-id="c081c-125">datetime</span><span class="sxs-lookup"><span data-stu-id="c081c-125">datetime</span></span>  <br/> |<span data-ttu-id="c081c-p101">最近尝试刷新主体的时间戳。如果尚未尝试任何刷新，可以为 null。</span><span class="sxs-lookup"><span data-stu-id="c081c-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="c081c-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="c081c-128">nextTry</span></span>  <br/> |<span data-ttu-id="c081c-129">datetime</span><span class="sxs-lookup"><span data-stu-id="c081c-129">datetime</span></span>  <br/> |<span data-ttu-id="c081c-p102">计划的下一次刷新的时间戳。如果尚未计划进一步刷新，可以为 null。</span><span class="sxs-lookup"><span data-stu-id="c081c-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="c081c-132">**Keys**</span><span class="sxs-lookup"><span data-stu-id="c081c-132">**Keys**</span></span>

|<span data-ttu-id="c081c-133">**列**</span><span class="sxs-lookup"><span data-stu-id="c081c-133">**Column**</span></span>|<span data-ttu-id="c081c-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="c081c-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c081c-135">prinID</span><span class="sxs-lookup"><span data-stu-id="c081c-135">prinID</span></span>  <br/> |<span data-ttu-id="c081c-136">主键。</span><span class="sxs-lookup"><span data-stu-id="c081c-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="c081c-137">prinID</span><span class="sxs-lookup"><span data-stu-id="c081c-137">prinID</span></span>  <br/> |<span data-ttu-id="c081c-138">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="c081c-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

