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
description: tblPrincipalType 包含要分类 tblPrincipal 表中的主体类型。
ms.openlocfilehash: d5c710e1301344c853ef39aeff3b57f62c630c95
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505123"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="57e95-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="57e95-103">tblPrincipalType</span></span>
 
<span data-ttu-id="57e95-104">tblPrincipalType 包含要分类 tblPrincipal 表中的主体类型。</span><span class="sxs-lookup"><span data-stu-id="57e95-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="57e95-105">**列**</span><span class="sxs-lookup"><span data-stu-id="57e95-105">**Columns**</span></span>

|<span data-ttu-id="57e95-106">**列**</span><span class="sxs-lookup"><span data-stu-id="57e95-106">**Column**</span></span>|<span data-ttu-id="57e95-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="57e95-107">**Type**</span></span>|<span data-ttu-id="57e95-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="57e95-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="57e95-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="57e95-109">ptypeID</span></span>  <br/> |<span data-ttu-id="57e95-110">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="57e95-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="57e95-111">主体类型 id。</span><span class="sxs-lookup"><span data-stu-id="57e95-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="57e95-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="57e95-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="57e95-113">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="57e95-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="57e95-114">类型的说明。</span><span class="sxs-lookup"><span data-stu-id="57e95-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="57e95-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="57e95-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="57e95-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="57e95-116">bit, not null</span></span>  <br/> |<span data-ttu-id="57e95-117">如果类型对应于供内部使用的主体，则为 true。</span><span class="sxs-lookup"><span data-stu-id="57e95-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="57e95-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="57e95-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="57e95-119">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="57e95-119">bit, not null</span></span>  <br/> |<span data-ttu-id="57e95-120">如果类型为用户类型，则为 true。</span><span class="sxs-lookup"><span data-stu-id="57e95-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="57e95-121">**关键字**</span><span class="sxs-lookup"><span data-stu-id="57e95-121">**Key**</span></span>

|<span data-ttu-id="57e95-122">**列**</span><span class="sxs-lookup"><span data-stu-id="57e95-122">**Column**</span></span>|<span data-ttu-id="57e95-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="57e95-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="57e95-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="57e95-124">ptypeID</span></span>  <br/> |<span data-ttu-id="57e95-125">主键。</span><span class="sxs-lookup"><span data-stu-id="57e95-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="57e95-126">**主体值**</span><span class="sxs-lookup"><span data-stu-id="57e95-126">**Principal Values**</span></span>

|<span data-ttu-id="57e95-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="57e95-127">**ID**</span></span>|<span data-ttu-id="57e95-128">**角色**</span><span class="sxs-lookup"><span data-stu-id="57e95-128">**Role**</span></span>|<span data-ttu-id="57e95-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="57e95-129">**Description**</span></span>|<span data-ttu-id="57e95-130">**用户**</span><span class="sxs-lookup"><span data-stu-id="57e95-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="57e95-131">1</span><span class="sxs-lookup"><span data-stu-id="57e95-131">1</span></span>  <br/> |<span data-ttu-id="57e95-132">任何</span><span class="sxs-lookup"><span data-stu-id="57e95-132">Any</span></span>  <br/> |<span data-ttu-id="57e95-133">没有已知类型的通用主体。</span><span class="sxs-lookup"><span data-stu-id="57e95-133">Generic principal with no known type.</span></span> <span data-ttu-id="57e95-134">不使用 tblPrincipal 表中。</span><span class="sxs-lookup"><span data-stu-id="57e95-134">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="57e95-135">2</span><span class="sxs-lookup"><span data-stu-id="57e95-135">2</span></span>  <br/> |<span data-ttu-id="57e95-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="57e95-136">AnyUser</span></span>  <br/> |<span data-ttu-id="57e95-137">用户类型的通用主体。</span><span class="sxs-lookup"><span data-stu-id="57e95-137">Generic principal of user type.</span></span> <span data-ttu-id="57e95-138">不使用 tblPrincipal 表中。</span><span class="sxs-lookup"><span data-stu-id="57e95-138">Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="57e95-139">是</span><span class="sxs-lookup"><span data-stu-id="57e95-139">Yes</span></span>  <br/> |
|<span data-ttu-id="57e95-140">3</span><span class="sxs-lookup"><span data-stu-id="57e95-140">3</span></span>  <br/> |<span data-ttu-id="57e95-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="57e95-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="57e95-142">与语义组的通用主体。</span><span class="sxs-lookup"><span data-stu-id="57e95-142">Generic principal with group semantic.</span></span> <span data-ttu-id="57e95-143">不使用 tblPrincipal 表中。</span><span class="sxs-lookup"><span data-stu-id="57e95-143">Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="57e95-144">4</span><span class="sxs-lookup"><span data-stu-id="57e95-144">4</span></span>  <br/> |<span data-ttu-id="57e95-145">系统用户</span><span class="sxs-lookup"><span data-stu-id="57e95-145">SystemUser</span></span>  <br/> |<span data-ttu-id="57e95-146">持久聊天服务器供内部使用的主体。</span><span class="sxs-lookup"><span data-stu-id="57e95-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="57e95-147">5</span><span class="sxs-lookup"><span data-stu-id="57e95-147">5</span></span>  <br/> |<span data-ttu-id="57e95-148">用户</span><span class="sxs-lookup"><span data-stu-id="57e95-148">User</span></span>  <br/> |<span data-ttu-id="57e95-149">常规用户。</span><span class="sxs-lookup"><span data-stu-id="57e95-149">Regular user.</span></span>  <br/> |<span data-ttu-id="57e95-150">是</span><span class="sxs-lookup"><span data-stu-id="57e95-150">Yes</span></span>  <br/> |
|<span data-ttu-id="57e95-151">8</span><span class="sxs-lookup"><span data-stu-id="57e95-151">8</span></span>  <br/> |<span data-ttu-id="57e95-152">DC</span><span class="sxs-lookup"><span data-stu-id="57e95-152">DC</span></span>  <br/> |<span data-ttu-id="57e95-153">Active Directory 域服务的域控制器。</span><span class="sxs-lookup"><span data-stu-id="57e95-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="57e95-154">9</span><span class="sxs-lookup"><span data-stu-id="57e95-154">9</span></span>  <br/> |<span data-ttu-id="57e95-155">组</span><span class="sxs-lookup"><span data-stu-id="57e95-155">Group</span></span>  <br/> |<span data-ttu-id="57e95-156">Active Directory 安全组。</span><span class="sxs-lookup"><span data-stu-id="57e95-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="57e95-157"> 10</span><span class="sxs-lookup"><span data-stu-id="57e95-157">10</span></span>  <br/> |<span data-ttu-id="57e95-158">文件夹</span><span class="sxs-lookup"><span data-stu-id="57e95-158">Folder</span></span>  <br/> |<span data-ttu-id="57e95-159">Active Directory 容器或组织单位。</span><span class="sxs-lookup"><span data-stu-id="57e95-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="57e95-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57e95-160">See also</span></span>

[<span data-ttu-id="57e95-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="57e95-161">tblPrincipal</span></span>](tblprincipal.md)