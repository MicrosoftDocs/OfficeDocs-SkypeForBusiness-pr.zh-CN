---
title: tblPrincipalMeta
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta 包含需要刷新从 Active Directory 域服务的主体。
ms.openlocfilehash: cfbff018167a3cde68061c3e04eb65d2742e51e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="1640d-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="1640d-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="1640d-104">tblPrincipalMeta 包含需要刷新从 Active Directory 域服务的主体。</span><span class="sxs-lookup"><span data-stu-id="1640d-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="1640d-105">**列**</span><span class="sxs-lookup"><span data-stu-id="1640d-105">**Columns**</span></span>

|<span data-ttu-id="1640d-106">**列**</span><span class="sxs-lookup"><span data-stu-id="1640d-106">**Column**</span></span>|<span data-ttu-id="1640d-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="1640d-107">**Type**</span></span>|<span data-ttu-id="1640d-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="1640d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1640d-109">prinID</span><span class="sxs-lookup"><span data-stu-id="1640d-109">prinID</span></span>  <br/> |<span data-ttu-id="1640d-110">int，不为空</span><span class="sxs-lookup"><span data-stu-id="1640d-110">int, not null</span></span>  <br/> |<span data-ttu-id="1640d-111">主体标识。</span><span class="sxs-lookup"><span data-stu-id="1640d-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="1640d-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="1640d-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="1640d-113">位，不为空</span><span class="sxs-lookup"><span data-stu-id="1640d-113">bit, not null</span></span>  <br/> |<span data-ttu-id="1640d-114">如果主要附属机构需要被刷新。</span><span class="sxs-lookup"><span data-stu-id="1640d-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="1640d-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="1640d-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="1640d-116">位，不为空</span><span class="sxs-lookup"><span data-stu-id="1640d-116">bit, not null</span></span>  <br/> |<span data-ttu-id="1640d-117">如果主体属性必须被刷新。</span><span class="sxs-lookup"><span data-stu-id="1640d-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="1640d-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="1640d-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="1640d-119">位，不为空</span><span class="sxs-lookup"><span data-stu-id="1640d-119">bit, not null</span></span>  <br/> |<span data-ttu-id="1640d-120">如果主体已被删除，则为 true。</span><span class="sxs-lookup"><span data-stu-id="1640d-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="1640d-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="1640d-121">tryCount</span></span>  <br/> |<span data-ttu-id="1640d-122">int</span><span class="sxs-lookup"><span data-stu-id="1640d-122">int</span></span>  <br/> |<span data-ttu-id="1640d-123">若要刷新到目前为止发生的 AD ds 主体的尝试次数。</span><span class="sxs-lookup"><span data-stu-id="1640d-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="1640d-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="1640d-124">lastTry</span></span>  <br/> |<span data-ttu-id="1640d-125">datetime</span><span class="sxs-lookup"><span data-stu-id="1640d-125">datetime</span></span>  <br/> |<span data-ttu-id="1640d-126">从最新尝试刷新主体的时间戳。</span><span class="sxs-lookup"><span data-stu-id="1640d-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="1640d-127">可以为 null，如果尚未已尝试了任何一次刷新。</span><span class="sxs-lookup"><span data-stu-id="1640d-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="1640d-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="1640d-128">nextTry</span></span>  <br/> |<span data-ttu-id="1640d-129">datetime</span><span class="sxs-lookup"><span data-stu-id="1640d-129">datetime</span></span>  <br/> |<span data-ttu-id="1640d-130">下次计划更新的时间戳。</span><span class="sxs-lookup"><span data-stu-id="1640d-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="1640d-131">可以刷新已没有进一步安排的情况下为 null。</span><span class="sxs-lookup"><span data-stu-id="1640d-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="1640d-132">**密钥**</span><span class="sxs-lookup"><span data-stu-id="1640d-132">**Keys**</span></span>

|<span data-ttu-id="1640d-133">**列**</span><span class="sxs-lookup"><span data-stu-id="1640d-133">**Column**</span></span>|<span data-ttu-id="1640d-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="1640d-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1640d-135">prinID</span><span class="sxs-lookup"><span data-stu-id="1640d-135">prinID</span></span>  <br/> |<span data-ttu-id="1640d-136">为主键。</span><span class="sxs-lookup"><span data-stu-id="1640d-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="1640d-137">prinID</span><span class="sxs-lookup"><span data-stu-id="1640d-137">prinID</span></span>  <br/> |<span data-ttu-id="1640d-138">TblPrincipal.prinID 表中查找与外键。</span><span class="sxs-lookup"><span data-stu-id="1640d-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

