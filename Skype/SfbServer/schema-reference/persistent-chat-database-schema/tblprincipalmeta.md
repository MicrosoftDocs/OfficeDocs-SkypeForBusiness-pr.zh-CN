---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblprincipalmeta 表包含必须从 Active Directory 域服务刷新的主体。
ms.openlocfilehash: a13fdcf705075188ae4febd5a2e0c3bc93a4738f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924540"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="a5f55-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="a5f55-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="a5f55-104">tblprincipalmeta 表包含必须从 Active Directory 域服务刷新的主体。</span><span class="sxs-lookup"><span data-stu-id="a5f55-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="a5f55-105">**列**</span><span class="sxs-lookup"><span data-stu-id="a5f55-105">**Columns**</span></span>

|<span data-ttu-id="a5f55-106">**列**</span><span class="sxs-lookup"><span data-stu-id="a5f55-106">**Column**</span></span>|<span data-ttu-id="a5f55-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="a5f55-107">**Type**</span></span>|<span data-ttu-id="a5f55-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="a5f55-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a5f55-109">prinID</span><span class="sxs-lookup"><span data-stu-id="a5f55-109">prinID</span></span>  <br/> |<span data-ttu-id="a5f55-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="a5f55-110">int, not null</span></span>  <br/> |<span data-ttu-id="a5f55-111">主体 id。</span><span class="sxs-lookup"><span data-stu-id="a5f55-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="a5f55-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="a5f55-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="a5f55-113">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="a5f55-113">bit, not null</span></span>  <br/> |<span data-ttu-id="a5f55-114">如果主体附属关系必须刷新。</span><span class="sxs-lookup"><span data-stu-id="a5f55-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="a5f55-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="a5f55-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="a5f55-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="a5f55-116">bit, not null</span></span>  <br/> |<span data-ttu-id="a5f55-117">如果主体属性必须刷新。</span><span class="sxs-lookup"><span data-stu-id="a5f55-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="a5f55-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="a5f55-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="a5f55-119">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="a5f55-119">bit, not null</span></span>  <br/> |<span data-ttu-id="a5f55-120">如果主体已被删除，则为 true。</span><span class="sxs-lookup"><span data-stu-id="a5f55-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="a5f55-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="a5f55-121">tryCount</span></span>  <br/> |<span data-ttu-id="a5f55-122">int</span><span class="sxs-lookup"><span data-stu-id="a5f55-122">int</span></span>  <br/> |<span data-ttu-id="a5f55-123">若要刷新的主体从 AD DS 到目前为止已发生的次数。</span><span class="sxs-lookup"><span data-stu-id="a5f55-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="a5f55-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="a5f55-124">lastTry</span></span>  <br/> |<span data-ttu-id="a5f55-125">datetime</span><span class="sxs-lookup"><span data-stu-id="a5f55-125">datetime</span></span>  <br/> |<span data-ttu-id="a5f55-126">从最新尝试刷新主体的时间戳。</span><span class="sxs-lookup"><span data-stu-id="a5f55-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="a5f55-127">可以为 null，如果尚未已尝试了任何一次刷新。</span><span class="sxs-lookup"><span data-stu-id="a5f55-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="a5f55-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="a5f55-128">nextTry</span></span>  <br/> |<span data-ttu-id="a5f55-129">datetime</span><span class="sxs-lookup"><span data-stu-id="a5f55-129">datetime</span></span>  <br/> |<span data-ttu-id="a5f55-130">下一计划刷新的时间戳。</span><span class="sxs-lookup"><span data-stu-id="a5f55-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="a5f55-131">可以为 null，如果没有进一步已计划刷新。</span><span class="sxs-lookup"><span data-stu-id="a5f55-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="a5f55-132">**键**</span><span class="sxs-lookup"><span data-stu-id="a5f55-132">**Keys**</span></span>

|<span data-ttu-id="a5f55-133">**列**</span><span class="sxs-lookup"><span data-stu-id="a5f55-133">**Column**</span></span>|<span data-ttu-id="a5f55-134">**说明**</span><span class="sxs-lookup"><span data-stu-id="a5f55-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a5f55-135">prinID</span><span class="sxs-lookup"><span data-stu-id="a5f55-135">prinID</span></span>  <br/> |<span data-ttu-id="a5f55-136">主键。</span><span class="sxs-lookup"><span data-stu-id="a5f55-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a5f55-137">prinID</span><span class="sxs-lookup"><span data-stu-id="a5f55-137">prinID</span></span>  <br/> |<span data-ttu-id="a5f55-138">在 tblPrincipal.prinID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="a5f55-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

