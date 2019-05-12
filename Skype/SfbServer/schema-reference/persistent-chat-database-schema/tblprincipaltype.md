---
title: tblPrincipalType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType 包含要分类 tblPrincipal 表中的主体类型。
ms.openlocfilehash: 804997c0cb25dff6566d21a26626550982d0075f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924456"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="14365-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="14365-103">tblPrincipalType</span></span>
 
<span data-ttu-id="14365-104">tblPrincipalType 包含要分类 tblPrincipal 表中的主体类型。</span><span class="sxs-lookup"><span data-stu-id="14365-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="14365-105">**列**</span><span class="sxs-lookup"><span data-stu-id="14365-105">**Columns**</span></span>

|<span data-ttu-id="14365-106">**列**</span><span class="sxs-lookup"><span data-stu-id="14365-106">**Column**</span></span>|<span data-ttu-id="14365-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="14365-107">**Type**</span></span>|<span data-ttu-id="14365-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="14365-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="14365-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="14365-109">ptypeID</span></span>  <br/> |<span data-ttu-id="14365-110">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="14365-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="14365-111">主体类型 id。</span><span class="sxs-lookup"><span data-stu-id="14365-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="14365-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="14365-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="14365-113">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="14365-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="14365-114">类型的说明。</span><span class="sxs-lookup"><span data-stu-id="14365-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="14365-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="14365-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="14365-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="14365-116">bit, not null</span></span>  <br/> |<span data-ttu-id="14365-117">如果类型对应于供内部使用的主体，则为 true。</span><span class="sxs-lookup"><span data-stu-id="14365-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="14365-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="14365-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="14365-119">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="14365-119">bit, not null</span></span>  <br/> |<span data-ttu-id="14365-120">如果类型为用户类型，则为 true。</span><span class="sxs-lookup"><span data-stu-id="14365-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="14365-121">**关键字**</span><span class="sxs-lookup"><span data-stu-id="14365-121">**Key**</span></span>

|<span data-ttu-id="14365-122">**列**</span><span class="sxs-lookup"><span data-stu-id="14365-122">**Column**</span></span>|<span data-ttu-id="14365-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="14365-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="14365-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="14365-124">ptypeID</span></span>  <br/> |<span data-ttu-id="14365-125">主键。</span><span class="sxs-lookup"><span data-stu-id="14365-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="14365-126">**主体值**</span><span class="sxs-lookup"><span data-stu-id="14365-126">**Principal Values**</span></span>

|<span data-ttu-id="14365-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="14365-127">**ID**</span></span>|<span data-ttu-id="14365-128">**角色**</span><span class="sxs-lookup"><span data-stu-id="14365-128">**Role**</span></span>|<span data-ttu-id="14365-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="14365-129">**Description**</span></span>|<span data-ttu-id="14365-130">**User**</span><span class="sxs-lookup"><span data-stu-id="14365-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="14365-131">1</span><span class="sxs-lookup"><span data-stu-id="14365-131">1</span></span>  <br/> |<span data-ttu-id="14365-132">任意</span><span class="sxs-lookup"><span data-stu-id="14365-132">Any</span></span>  <br/> |<span data-ttu-id="14365-133">没有已知类型的通用主体。</span><span class="sxs-lookup"><span data-stu-id="14365-133">Generic principal with no known type.</span></span> <span data-ttu-id="14365-134">不使用 tblPrincipal 表中。</span><span class="sxs-lookup"><span data-stu-id="14365-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="14365-135">2</span><span class="sxs-lookup"><span data-stu-id="14365-135">2</span></span>  <br/> |<span data-ttu-id="14365-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="14365-136">AnyUser</span></span>  <br/> |<span data-ttu-id="14365-137">用户类型的通用主体。</span><span class="sxs-lookup"><span data-stu-id="14365-137">Generic principal of user type.</span></span> <span data-ttu-id="14365-138">不使用 tblPrincipal 表中。</span><span class="sxs-lookup"><span data-stu-id="14365-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="14365-139">是</span><span class="sxs-lookup"><span data-stu-id="14365-139">Yes</span></span>  <br/> |
|<span data-ttu-id="14365-140">3</span><span class="sxs-lookup"><span data-stu-id="14365-140">3</span></span>  <br/> |<span data-ttu-id="14365-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="14365-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="14365-142">与语义组的通用主体。</span><span class="sxs-lookup"><span data-stu-id="14365-142">Generic principal with group semantic.</span></span> <span data-ttu-id="14365-143">不使用 tblPrincipal 表中。</span><span class="sxs-lookup"><span data-stu-id="14365-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="14365-144">4</span><span class="sxs-lookup"><span data-stu-id="14365-144">4</span></span>  <br/> |<span data-ttu-id="14365-145">系统用户</span><span class="sxs-lookup"><span data-stu-id="14365-145">SystemUser</span></span>  <br/> |<span data-ttu-id="14365-146">持久聊天服务器供内部使用的主体。</span><span class="sxs-lookup"><span data-stu-id="14365-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="14365-147">5</span><span class="sxs-lookup"><span data-stu-id="14365-147">5</span></span>  <br/> |<span data-ttu-id="14365-148">用户</span><span class="sxs-lookup"><span data-stu-id="14365-148">User</span></span>  <br/> |<span data-ttu-id="14365-149">常规用户。</span><span class="sxs-lookup"><span data-stu-id="14365-149">Regular user.</span></span>  <br/> |<span data-ttu-id="14365-150">是</span><span class="sxs-lookup"><span data-stu-id="14365-150">Yes</span></span>  <br/> |
|<span data-ttu-id="14365-151">8</span><span class="sxs-lookup"><span data-stu-id="14365-151">8</span></span>  <br/> |<span data-ttu-id="14365-152">DC</span><span class="sxs-lookup"><span data-stu-id="14365-152">DC</span></span>  <br/> |<span data-ttu-id="14365-153">Active Directory 域服务的域控制器。</span><span class="sxs-lookup"><span data-stu-id="14365-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="14365-154">9</span><span class="sxs-lookup"><span data-stu-id="14365-154">9</span></span>  <br/> |<span data-ttu-id="14365-155">组</span><span class="sxs-lookup"><span data-stu-id="14365-155">Group</span></span>  <br/> |<span data-ttu-id="14365-156">Active Directory 安全组。</span><span class="sxs-lookup"><span data-stu-id="14365-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="14365-157">10</span><span class="sxs-lookup"><span data-stu-id="14365-157">10</span></span>  <br/> |<span data-ttu-id="14365-158">文件夹</span><span class="sxs-lookup"><span data-stu-id="14365-158">Folder</span></span>  <br/> |<span data-ttu-id="14365-159">Active Directory 容器或组织单位。</span><span class="sxs-lookup"><span data-stu-id="14365-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="14365-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="14365-160">See also</span></span>

[<span data-ttu-id="14365-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="14365-161">tblPrincipal</span></span>](tblprincipal.md)
