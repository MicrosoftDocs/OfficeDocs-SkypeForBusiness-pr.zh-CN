---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblprincipalmeta 表包含必须从 Active Directory 域服务刷新的主体。
ms.openlocfilehash: 049a273f7134ecb945e62da39469bcaf0defbffb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889605"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="ea2ff-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="ea2ff-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="ea2ff-104">tblprincipalmeta 表包含必须从 Active Directory 域服务刷新的主体。</span><span class="sxs-lookup"><span data-stu-id="ea2ff-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="ea2ff-105">**列**</span><span class="sxs-lookup"><span data-stu-id="ea2ff-105">**Columns**</span></span>

|<span data-ttu-id="ea2ff-106">**列**</span><span class="sxs-lookup"><span data-stu-id="ea2ff-106">**Column**</span></span>|<span data-ttu-id="ea2ff-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="ea2ff-107">**Type**</span></span>|<span data-ttu-id="ea2ff-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="ea2ff-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ea2ff-109">prinID</span><span class="sxs-lookup"><span data-stu-id="ea2ff-109">prinID</span></span>  <br/> |<span data-ttu-id="ea2ff-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="ea2ff-110">int, not null</span></span>  <br/> |<span data-ttu-id="ea2ff-111">主体 id。</span><span class="sxs-lookup"><span data-stu-id="ea2ff-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="ea2ff-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="ea2ff-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="ea2ff-113">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="ea2ff-113">bit, not null</span></span>  <br/> |<span data-ttu-id="ea2ff-114">如果主体附属关系必须刷新。</span><span class="sxs-lookup"><span data-stu-id="ea2ff-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="ea2ff-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="ea2ff-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="ea2ff-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="ea2ff-116">bit, not null</span></span>  <br/> |<span data-ttu-id="ea2ff-117">如果主体属性必须刷新。</span><span class="sxs-lookup"><span data-stu-id="ea2ff-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="ea2ff-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="ea2ff-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="ea2ff-119">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="ea2ff-119">bit, not null</span></span>  <br/> |<span data-ttu-id="ea2ff-120">如果主体已被删除，则为 true。</span><span class="sxs-lookup"><span data-stu-id="ea2ff-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="ea2ff-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="ea2ff-121">tryCount</span></span>  <br/> |<span data-ttu-id="ea2ff-122">int</span><span class="sxs-lookup"><span data-stu-id="ea2ff-122">int</span></span>  <br/> |<span data-ttu-id="ea2ff-123">若要刷新的主体从 AD DS 到目前为止已发生的次数。</span><span class="sxs-lookup"><span data-stu-id="ea2ff-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="ea2ff-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="ea2ff-124">lastTry</span></span>  <br/> |<span data-ttu-id="ea2ff-125">datetime</span><span class="sxs-lookup"><span data-stu-id="ea2ff-125">datetime</span></span>  <br/> |<span data-ttu-id="ea2ff-126">从最新尝试刷新主体的时间戳。</span><span class="sxs-lookup"><span data-stu-id="ea2ff-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="ea2ff-127">可以为 null，如果尚未已尝试了任何一次刷新。</span><span class="sxs-lookup"><span data-stu-id="ea2ff-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="ea2ff-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="ea2ff-128">nextTry</span></span>  <br/> |<span data-ttu-id="ea2ff-129">datetime</span><span class="sxs-lookup"><span data-stu-id="ea2ff-129">datetime</span></span>  <br/> |<span data-ttu-id="ea2ff-130">下一计划刷新的时间戳。</span><span class="sxs-lookup"><span data-stu-id="ea2ff-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="ea2ff-131">可以为 null，如果没有进一步已计划刷新。</span><span class="sxs-lookup"><span data-stu-id="ea2ff-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="ea2ff-132">**键**</span><span class="sxs-lookup"><span data-stu-id="ea2ff-132">**Keys**</span></span>

|<span data-ttu-id="ea2ff-133">**列**</span><span class="sxs-lookup"><span data-stu-id="ea2ff-133">**Column**</span></span>|<span data-ttu-id="ea2ff-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="ea2ff-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ea2ff-135">prinID</span><span class="sxs-lookup"><span data-stu-id="ea2ff-135">prinID</span></span>  <br/> |<span data-ttu-id="ea2ff-136">主键。</span><span class="sxs-lookup"><span data-stu-id="ea2ff-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="ea2ff-137">prinID</span><span class="sxs-lookup"><span data-stu-id="ea2ff-137">prinID</span></span>  <br/> |<span data-ttu-id="ea2ff-138">在 tblPrincipal.prinID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="ea2ff-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

