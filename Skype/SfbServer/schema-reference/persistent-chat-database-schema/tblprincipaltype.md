---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType 包含用于对 tblPrincipal 表中的内容进行分类的主体类型。
ms.openlocfilehash: 473b718a8a863432a71ff04d709bef4c0ac1327f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295242"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="1856e-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="1856e-103">tblPrincipalType</span></span>
 
<span data-ttu-id="1856e-104">tblPrincipalType 包含用于对 tblPrincipal 表中的内容进行分类的主体类型。</span><span class="sxs-lookup"><span data-stu-id="1856e-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="1856e-105">**多**</span><span class="sxs-lookup"><span data-stu-id="1856e-105">**Columns**</span></span>

|<span data-ttu-id="1856e-106">**列**</span><span class="sxs-lookup"><span data-stu-id="1856e-106">**Column**</span></span>|<span data-ttu-id="1856e-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="1856e-107">**Type**</span></span>|<span data-ttu-id="1856e-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="1856e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1856e-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="1856e-109">ptypeID</span></span>  <br/> |<span data-ttu-id="1856e-110">smallint, not null</span><span class="sxs-lookup"><span data-stu-id="1856e-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="1856e-111">主体类型 ID。</span><span class="sxs-lookup"><span data-stu-id="1856e-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="1856e-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="1856e-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="1856e-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="1856e-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="1856e-114">类型的说明。</span><span class="sxs-lookup"><span data-stu-id="1856e-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="1856e-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="1856e-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="1856e-116">位, not null</span><span class="sxs-lookup"><span data-stu-id="1856e-116">bit, not null</span></span>  <br/> |<span data-ttu-id="1856e-117">如果类型对应于用于内部用途的主体, 则为 True。</span><span class="sxs-lookup"><span data-stu-id="1856e-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="1856e-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="1856e-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="1856e-119">位, not null</span><span class="sxs-lookup"><span data-stu-id="1856e-119">bit, not null</span></span>  <br/> |<span data-ttu-id="1856e-120">如果类型为用户类型, 则为 True。</span><span class="sxs-lookup"><span data-stu-id="1856e-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="1856e-121">**关键字**</span><span class="sxs-lookup"><span data-stu-id="1856e-121">**Key**</span></span>

|<span data-ttu-id="1856e-122">**列**</span><span class="sxs-lookup"><span data-stu-id="1856e-122">**Column**</span></span>|<span data-ttu-id="1856e-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="1856e-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1856e-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="1856e-124">ptypeID</span></span>  <br/> |<span data-ttu-id="1856e-125">主键。</span><span class="sxs-lookup"><span data-stu-id="1856e-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="1856e-126">**主体值**</span><span class="sxs-lookup"><span data-stu-id="1856e-126">**Principal Values**</span></span>

|<span data-ttu-id="1856e-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="1856e-127">**ID**</span></span>|<span data-ttu-id="1856e-128">**角色**</span><span class="sxs-lookup"><span data-stu-id="1856e-128">**Role**</span></span>|<span data-ttu-id="1856e-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="1856e-129">**Description**</span></span>|<span data-ttu-id="1856e-130">**User**</span><span class="sxs-lookup"><span data-stu-id="1856e-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1856e-131">1</span><span class="sxs-lookup"><span data-stu-id="1856e-131">1</span></span>  <br/> |<span data-ttu-id="1856e-132">任意</span><span class="sxs-lookup"><span data-stu-id="1856e-132">Any</span></span>  <br/> |<span data-ttu-id="1856e-133">没有已知类型的泛型主体。</span><span class="sxs-lookup"><span data-stu-id="1856e-133">Generic principal with no known type.</span></span> <span data-ttu-id="1856e-134">未在 tblPrincipal 表中使用。</span><span class="sxs-lookup"><span data-stu-id="1856e-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="1856e-135">2</span><span class="sxs-lookup"><span data-stu-id="1856e-135">2</span></span>  <br/> |<span data-ttu-id="1856e-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="1856e-136">AnyUser</span></span>  <br/> |<span data-ttu-id="1856e-137">用户类型的一般主体。</span><span class="sxs-lookup"><span data-stu-id="1856e-137">Generic principal of user type.</span></span> <span data-ttu-id="1856e-138">未在 tblPrincipal 表中使用。</span><span class="sxs-lookup"><span data-stu-id="1856e-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="1856e-139">是</span><span class="sxs-lookup"><span data-stu-id="1856e-139">Yes</span></span>  <br/> |
|<span data-ttu-id="1856e-140">3</span><span class="sxs-lookup"><span data-stu-id="1856e-140">3</span></span>  <br/> |<span data-ttu-id="1856e-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="1856e-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="1856e-142">具有组语义的常规主体。</span><span class="sxs-lookup"><span data-stu-id="1856e-142">Generic principal with group semantic.</span></span> <span data-ttu-id="1856e-143">未在 tblPrincipal 表中使用。</span><span class="sxs-lookup"><span data-stu-id="1856e-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="1856e-144">4</span><span class="sxs-lookup"><span data-stu-id="1856e-144">4</span></span>  <br/> |<span data-ttu-id="1856e-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="1856e-145">SystemUser</span></span>  <br/> |<span data-ttu-id="1856e-146">持久聊天服务器在内部使用的主体。</span><span class="sxs-lookup"><span data-stu-id="1856e-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="1856e-147">5</span><span class="sxs-lookup"><span data-stu-id="1856e-147">5</span></span>  <br/> |<span data-ttu-id="1856e-148">用户</span><span class="sxs-lookup"><span data-stu-id="1856e-148">User</span></span>  <br/> |<span data-ttu-id="1856e-149">普通用户。</span><span class="sxs-lookup"><span data-stu-id="1856e-149">Regular user.</span></span>  <br/> |<span data-ttu-id="1856e-150">是</span><span class="sxs-lookup"><span data-stu-id="1856e-150">Yes</span></span>  <br/> |
|<span data-ttu-id="1856e-151">个</span><span class="sxs-lookup"><span data-stu-id="1856e-151">8</span></span>  <br/> |<span data-ttu-id="1856e-152">电源</span><span class="sxs-lookup"><span data-stu-id="1856e-152">DC</span></span>  <br/> |<span data-ttu-id="1856e-153">Active Directory 域服务域控制器。</span><span class="sxs-lookup"><span data-stu-id="1856e-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="1856e-154">db-9</span><span class="sxs-lookup"><span data-stu-id="1856e-154">9</span></span>  <br/> |<span data-ttu-id="1856e-155">团队</span><span class="sxs-lookup"><span data-stu-id="1856e-155">Group</span></span>  <br/> |<span data-ttu-id="1856e-156">Active Directory 安全组。</span><span class="sxs-lookup"><span data-stu-id="1856e-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="1856e-157">10</span><span class="sxs-lookup"><span data-stu-id="1856e-157">10</span></span>  <br/> |<span data-ttu-id="1856e-158">收藏夹</span><span class="sxs-lookup"><span data-stu-id="1856e-158">Folder</span></span>  <br/> |<span data-ttu-id="1856e-159">Active Directory 容器或组织单位。</span><span class="sxs-lookup"><span data-stu-id="1856e-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="1856e-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1856e-160">See also</span></span>

[<span data-ttu-id="1856e-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="1856e-161">tblPrincipal</span></span>](tblprincipal.md)
