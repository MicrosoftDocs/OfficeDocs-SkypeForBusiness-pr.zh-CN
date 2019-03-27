---
title: tblPrincipalType
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType 包含要分类 tblPrincipal 表中的主体类型。
ms.openlocfilehash: ab2cb28971f0564a082e0caed01e7fc622c41201
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30887433"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="f3764-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="f3764-103">tblPrincipalType</span></span>
 
<span data-ttu-id="f3764-104">tblPrincipalType 包含要分类 tblPrincipal 表中的主体类型。</span><span class="sxs-lookup"><span data-stu-id="f3764-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="f3764-105">**列**</span><span class="sxs-lookup"><span data-stu-id="f3764-105">**Columns**</span></span>

|<span data-ttu-id="f3764-106">**列**</span><span class="sxs-lookup"><span data-stu-id="f3764-106">**Column**</span></span>|<span data-ttu-id="f3764-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="f3764-107">**Type**</span></span>|<span data-ttu-id="f3764-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="f3764-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f3764-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="f3764-109">ptypeID</span></span>  <br/> |<span data-ttu-id="f3764-110">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="f3764-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="f3764-111">主体类型 id。</span><span class="sxs-lookup"><span data-stu-id="f3764-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="f3764-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="f3764-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="f3764-113">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="f3764-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="f3764-114">类型的说明。</span><span class="sxs-lookup"><span data-stu-id="f3764-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="f3764-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="f3764-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="f3764-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="f3764-116">bit, not null</span></span>  <br/> |<span data-ttu-id="f3764-117">如果类型对应于供内部使用的主体，则为 true。</span><span class="sxs-lookup"><span data-stu-id="f3764-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="f3764-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="f3764-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="f3764-119">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="f3764-119">bit, not null</span></span>  <br/> |<span data-ttu-id="f3764-120">如果类型为用户类型，则为 true。</span><span class="sxs-lookup"><span data-stu-id="f3764-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="f3764-121">**关键字**</span><span class="sxs-lookup"><span data-stu-id="f3764-121">**Key**</span></span>

|<span data-ttu-id="f3764-122">**列**</span><span class="sxs-lookup"><span data-stu-id="f3764-122">**Column**</span></span>|<span data-ttu-id="f3764-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="f3764-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f3764-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="f3764-124">ptypeID</span></span>  <br/> |<span data-ttu-id="f3764-125">主键。</span><span class="sxs-lookup"><span data-stu-id="f3764-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="f3764-126">**主体值**</span><span class="sxs-lookup"><span data-stu-id="f3764-126">**Principal Values**</span></span>

|<span data-ttu-id="f3764-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="f3764-127">**ID**</span></span>|<span data-ttu-id="f3764-128">**角色**</span><span class="sxs-lookup"><span data-stu-id="f3764-128">**Role**</span></span>|<span data-ttu-id="f3764-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="f3764-129">**Description**</span></span>|<span data-ttu-id="f3764-130">**User**</span><span class="sxs-lookup"><span data-stu-id="f3764-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f3764-131">1</span><span class="sxs-lookup"><span data-stu-id="f3764-131">1</span></span>  <br/> |<span data-ttu-id="f3764-132">任意</span><span class="sxs-lookup"><span data-stu-id="f3764-132">Any</span></span>  <br/> |<span data-ttu-id="f3764-133">没有已知类型的通用主体。</span><span class="sxs-lookup"><span data-stu-id="f3764-133">Generic principal with no known type.</span></span> <span data-ttu-id="f3764-134">不使用 tblPrincipal 表中。</span><span class="sxs-lookup"><span data-stu-id="f3764-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="f3764-135">2</span><span class="sxs-lookup"><span data-stu-id="f3764-135">2</span></span>  <br/> |<span data-ttu-id="f3764-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="f3764-136">AnyUser</span></span>  <br/> |<span data-ttu-id="f3764-137">用户类型的通用主体。</span><span class="sxs-lookup"><span data-stu-id="f3764-137">Generic principal of user type.</span></span> <span data-ttu-id="f3764-138">不使用 tblPrincipal 表中。</span><span class="sxs-lookup"><span data-stu-id="f3764-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="f3764-139">是</span><span class="sxs-lookup"><span data-stu-id="f3764-139">Yes</span></span>  <br/> |
|<span data-ttu-id="f3764-140">3</span><span class="sxs-lookup"><span data-stu-id="f3764-140">3</span></span>  <br/> |<span data-ttu-id="f3764-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="f3764-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="f3764-142">与语义组的通用主体。</span><span class="sxs-lookup"><span data-stu-id="f3764-142">Generic principal with group semantic.</span></span> <span data-ttu-id="f3764-143">不使用 tblPrincipal 表中。</span><span class="sxs-lookup"><span data-stu-id="f3764-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="f3764-144">4</span><span class="sxs-lookup"><span data-stu-id="f3764-144">4</span></span>  <br/> |<span data-ttu-id="f3764-145">系统用户</span><span class="sxs-lookup"><span data-stu-id="f3764-145">SystemUser</span></span>  <br/> |<span data-ttu-id="f3764-146">持久聊天服务器供内部使用的主体。</span><span class="sxs-lookup"><span data-stu-id="f3764-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="f3764-147">5</span><span class="sxs-lookup"><span data-stu-id="f3764-147">5</span></span>  <br/> |<span data-ttu-id="f3764-148">用户</span><span class="sxs-lookup"><span data-stu-id="f3764-148">User</span></span>  <br/> |<span data-ttu-id="f3764-149">常规用户。</span><span class="sxs-lookup"><span data-stu-id="f3764-149">Regular user.</span></span>  <br/> |<span data-ttu-id="f3764-150">是</span><span class="sxs-lookup"><span data-stu-id="f3764-150">Yes</span></span>  <br/> |
|<span data-ttu-id="f3764-151">8</span><span class="sxs-lookup"><span data-stu-id="f3764-151">8</span></span>  <br/> |<span data-ttu-id="f3764-152">DC</span><span class="sxs-lookup"><span data-stu-id="f3764-152">DC</span></span>  <br/> |<span data-ttu-id="f3764-153">Active Directory 域服务的域控制器。</span><span class="sxs-lookup"><span data-stu-id="f3764-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="f3764-154">9</span><span class="sxs-lookup"><span data-stu-id="f3764-154">9</span></span>  <br/> |<span data-ttu-id="f3764-155">组</span><span class="sxs-lookup"><span data-stu-id="f3764-155">Group</span></span>  <br/> |<span data-ttu-id="f3764-156">Active Directory 安全组。</span><span class="sxs-lookup"><span data-stu-id="f3764-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="f3764-157">10</span><span class="sxs-lookup"><span data-stu-id="f3764-157">10</span></span>  <br/> |<span data-ttu-id="f3764-158">文件夹</span><span class="sxs-lookup"><span data-stu-id="f3764-158">Folder</span></span>  <br/> |<span data-ttu-id="f3764-159">Active Directory 容器或组织单位。</span><span class="sxs-lookup"><span data-stu-id="f3764-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="f3764-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f3764-160">See also</span></span>

[<span data-ttu-id="f3764-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="f3764-161">tblPrincipal</span></span>](tblprincipal.md)
