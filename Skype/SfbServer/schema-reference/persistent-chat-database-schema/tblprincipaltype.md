---
title: tblPrincipalType
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType 包含主体的类型进行分类的 tblPrincipal 表中。
ms.openlocfilehash: 3d1ec9b83561f06d3f8b1871223aafdf5c0775cb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipaltype"></a><span data-ttu-id="1668b-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="1668b-103">tblPrincipalType</span></span>
 
<span data-ttu-id="1668b-104">tblPrincipalType 包含主体的类型进行分类的 tblPrincipal 表中。</span><span class="sxs-lookup"><span data-stu-id="1668b-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="1668b-105">**列**</span><span class="sxs-lookup"><span data-stu-id="1668b-105">**Columns**</span></span>

|<span data-ttu-id="1668b-106">**列**</span><span class="sxs-lookup"><span data-stu-id="1668b-106">**Column**</span></span>|<span data-ttu-id="1668b-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="1668b-107">**Type**</span></span>|<span data-ttu-id="1668b-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="1668b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1668b-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="1668b-109">ptypeID</span></span>  <br/> |<span data-ttu-id="1668b-110">smallint，不为空</span><span class="sxs-lookup"><span data-stu-id="1668b-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="1668b-111">主体的类型 id。</span><span class="sxs-lookup"><span data-stu-id="1668b-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="1668b-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="1668b-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="1668b-113">nvarchar (256) 不为空</span><span class="sxs-lookup"><span data-stu-id="1668b-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="1668b-114">类型的说明。</span><span class="sxs-lookup"><span data-stu-id="1668b-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="1668b-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="1668b-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="1668b-116">位，不为空</span><span class="sxs-lookup"><span data-stu-id="1668b-116">bit, not null</span></span>  <br/> |<span data-ttu-id="1668b-117">如果的类型对应于用于内部目的的主体，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="1668b-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="1668b-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="1668b-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="1668b-119">位，不为空</span><span class="sxs-lookup"><span data-stu-id="1668b-119">bit, not null</span></span>  <br/> |<span data-ttu-id="1668b-120">如果该类型是一种用户类型，则为 true。</span><span class="sxs-lookup"><span data-stu-id="1668b-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="1668b-121">**密钥**</span><span class="sxs-lookup"><span data-stu-id="1668b-121">**Key**</span></span>

|<span data-ttu-id="1668b-122">**列**</span><span class="sxs-lookup"><span data-stu-id="1668b-122">**Column**</span></span>|<span data-ttu-id="1668b-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="1668b-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1668b-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="1668b-124">ptypeID</span></span>  <br/> |<span data-ttu-id="1668b-125">为主键。</span><span class="sxs-lookup"><span data-stu-id="1668b-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="1668b-126">**主体的值**</span><span class="sxs-lookup"><span data-stu-id="1668b-126">**Principal Values**</span></span>

|<span data-ttu-id="1668b-127">**标识**</span><span class="sxs-lookup"><span data-stu-id="1668b-127">**ID**</span></span>|<span data-ttu-id="1668b-128">**角色**</span><span class="sxs-lookup"><span data-stu-id="1668b-128">**Role**</span></span>|<span data-ttu-id="1668b-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="1668b-129">**Description**</span></span>|<span data-ttu-id="1668b-130">**用户**</span><span class="sxs-lookup"><span data-stu-id="1668b-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1668b-131">1</span><span class="sxs-lookup"><span data-stu-id="1668b-131">1</span></span>  <br/> |<span data-ttu-id="1668b-132">任何</span><span class="sxs-lookup"><span data-stu-id="1668b-132">Any</span></span>  <br/> |<span data-ttu-id="1668b-133">与任何已知的类型的一般主体。</span><span class="sxs-lookup"><span data-stu-id="1668b-133">Generic principal with no known type.</span></span> <span data-ttu-id="1668b-134">不使用 tblPrincipal 表中。</span><span class="sxs-lookup"><span data-stu-id="1668b-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="1668b-135">2</span><span class="sxs-lookup"><span data-stu-id="1668b-135">2</span></span>  <br/> |<span data-ttu-id="1668b-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="1668b-136">AnyUser</span></span>  <br/> |<span data-ttu-id="1668b-137">用户类型的一般主体。</span><span class="sxs-lookup"><span data-stu-id="1668b-137">Generic principal of user type.</span></span> <span data-ttu-id="1668b-138">不使用 tblPrincipal 表中。</span><span class="sxs-lookup"><span data-stu-id="1668b-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="1668b-139">是</span><span class="sxs-lookup"><span data-stu-id="1668b-139">Yes</span></span>  <br/> |
|<span data-ttu-id="1668b-140">3</span><span class="sxs-lookup"><span data-stu-id="1668b-140">3</span></span>  <br/> |<span data-ttu-id="1668b-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="1668b-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="1668b-142">与组语义的一般主体。</span><span class="sxs-lookup"><span data-stu-id="1668b-142">Generic principal with group semantic.</span></span> <span data-ttu-id="1668b-143">不使用 tblPrincipal 表中。</span><span class="sxs-lookup"><span data-stu-id="1668b-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="1668b-144">4</span><span class="sxs-lookup"><span data-stu-id="1668b-144">4</span></span>  <br/> |<span data-ttu-id="1668b-145">系统用户</span><span class="sxs-lookup"><span data-stu-id="1668b-145">SystemUser</span></span>  <br/> |<span data-ttu-id="1668b-146">主体由持久聊天服务器内部使用。</span><span class="sxs-lookup"><span data-stu-id="1668b-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="1668b-147">5</span><span class="sxs-lookup"><span data-stu-id="1668b-147">5</span></span>  <br/> |<span data-ttu-id="1668b-148">用户</span><span class="sxs-lookup"><span data-stu-id="1668b-148">User</span></span>  <br/> |<span data-ttu-id="1668b-149">普通用户。</span><span class="sxs-lookup"><span data-stu-id="1668b-149">Regular user.</span></span>  <br/> |<span data-ttu-id="1668b-150">是</span><span class="sxs-lookup"><span data-stu-id="1668b-150">Yes</span></span>  <br/> |
|<span data-ttu-id="1668b-151">8</span><span class="sxs-lookup"><span data-stu-id="1668b-151">8</span></span>  <br/> |<span data-ttu-id="1668b-152">DC</span><span class="sxs-lookup"><span data-stu-id="1668b-152">DC</span></span>  <br/> |<span data-ttu-id="1668b-153">活动目录域服务域控制器。</span><span class="sxs-lookup"><span data-stu-id="1668b-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="1668b-154">9</span><span class="sxs-lookup"><span data-stu-id="1668b-154">9</span></span>  <br/> |<span data-ttu-id="1668b-155">组</span><span class="sxs-lookup"><span data-stu-id="1668b-155">Group</span></span>  <br/> |<span data-ttu-id="1668b-156">活动目录安全组。</span><span class="sxs-lookup"><span data-stu-id="1668b-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="1668b-157">10</span><span class="sxs-lookup"><span data-stu-id="1668b-157">10</span></span>  <br/> |<span data-ttu-id="1668b-158">文件夹</span><span class="sxs-lookup"><span data-stu-id="1668b-158">Folder</span></span>  <br/> |<span data-ttu-id="1668b-159">活动目录容器或组织单位。</span><span class="sxs-lookup"><span data-stu-id="1668b-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="1668b-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1668b-160">See also</span></span>

#### 

[<span data-ttu-id="1668b-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="1668b-161">tblPrincipal</span></span>](tblprincipal.md)

