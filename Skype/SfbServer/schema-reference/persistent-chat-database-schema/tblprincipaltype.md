---
title: tblPrincipalType
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
ms.assetid: 32e1c1d6-80f4-4624-bf4e-b4c77d3982fa
description: tblPrincipalType 包含用于对 tblPrincipal 表中的内容进行分类的主体类型。
ms.openlocfilehash: 110818db0fb3c742491adfeed23362a2bcbebab2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831532"
---
# <a name="tblprincipaltype"></a><span data-ttu-id="7ca75-103">tblPrincipalType</span><span class="sxs-lookup"><span data-stu-id="7ca75-103">tblPrincipalType</span></span>
 
<span data-ttu-id="7ca75-104">tblPrincipalType 包含用于对 tblPrincipal 表中的内容进行分类的主体类型。</span><span class="sxs-lookup"><span data-stu-id="7ca75-104">tblPrincipalType contains principal types to categorize what is in the tblPrincipal table.</span></span>
  
<span data-ttu-id="7ca75-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="7ca75-105">**Columns**</span></span>

|<span data-ttu-id="7ca75-106">**列**</span><span class="sxs-lookup"><span data-stu-id="7ca75-106">**Column**</span></span>|<span data-ttu-id="7ca75-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="7ca75-107">**Type**</span></span>|<span data-ttu-id="7ca75-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="7ca75-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7ca75-109">ptypeID</span><span class="sxs-lookup"><span data-stu-id="7ca75-109">ptypeID</span></span>  <br/> |<span data-ttu-id="7ca75-110">smallint，不为 null</span><span class="sxs-lookup"><span data-stu-id="7ca75-110">smallint, not null</span></span>  <br/> |<span data-ttu-id="7ca75-111">主体类型 ID。</span><span class="sxs-lookup"><span data-stu-id="7ca75-111">Principal type ID.</span></span>  <br/> |
|<span data-ttu-id="7ca75-112">ptypeDesc</span><span class="sxs-lookup"><span data-stu-id="7ca75-112">ptypeDesc</span></span>  <br/> |<span data-ttu-id="7ca75-113">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="7ca75-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="7ca75-114">类型描述。</span><span class="sxs-lookup"><span data-stu-id="7ca75-114">Description of the type.</span></span>  <br/> |
|<span data-ttu-id="7ca75-115">ptypeIsSystemUser</span><span class="sxs-lookup"><span data-stu-id="7ca75-115">ptypeIsSystemUser</span></span>  <br/> |<span data-ttu-id="7ca75-116">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="7ca75-116">bit, not null</span></span>  <br/> |<span data-ttu-id="7ca75-117">在类型与供内部使用的主体对应时为 True。</span><span class="sxs-lookup"><span data-stu-id="7ca75-117">True if the type corresponds to the principals that are used for internal purposes.</span></span>  <br/> |
|<span data-ttu-id="7ca75-118">ptypeIsUser</span><span class="sxs-lookup"><span data-stu-id="7ca75-118">ptypeIsUser</span></span>  <br/> |<span data-ttu-id="7ca75-119">bit，不为 null</span><span class="sxs-lookup"><span data-stu-id="7ca75-119">bit, not null</span></span>  <br/> |<span data-ttu-id="7ca75-120">在类型为用户类型时为 True。</span><span class="sxs-lookup"><span data-stu-id="7ca75-120">True if the type is a user type.</span></span>  <br/> |
   
<span data-ttu-id="7ca75-121">**注册表项**</span><span class="sxs-lookup"><span data-stu-id="7ca75-121">**Key**</span></span>

|<span data-ttu-id="7ca75-122">**列**</span><span class="sxs-lookup"><span data-stu-id="7ca75-122">**Column**</span></span>|<span data-ttu-id="7ca75-123">**说明**</span><span class="sxs-lookup"><span data-stu-id="7ca75-123">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7ca75-124">ptypeID</span><span class="sxs-lookup"><span data-stu-id="7ca75-124">ptypeID</span></span>  <br/> |<span data-ttu-id="7ca75-125">主键。</span><span class="sxs-lookup"><span data-stu-id="7ca75-125">Primary key.</span></span>  <br/> |
   
<span data-ttu-id="7ca75-126">**主体值**</span><span class="sxs-lookup"><span data-stu-id="7ca75-126">**Principal Values**</span></span>

|<span data-ttu-id="7ca75-127">**ID**</span><span class="sxs-lookup"><span data-stu-id="7ca75-127">**ID**</span></span>|<span data-ttu-id="7ca75-128">**角色**</span><span class="sxs-lookup"><span data-stu-id="7ca75-128">**Role**</span></span>|<span data-ttu-id="7ca75-129">**说明**</span><span class="sxs-lookup"><span data-stu-id="7ca75-129">**Description**</span></span>|<span data-ttu-id="7ca75-130">"用户"</span><span class="sxs-lookup"><span data-stu-id="7ca75-130">**User**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7ca75-131">1 </span><span class="sxs-lookup"><span data-stu-id="7ca75-131">1</span></span>  <br/> |<span data-ttu-id="7ca75-132">任何</span><span class="sxs-lookup"><span data-stu-id="7ca75-132">Any</span></span>  <br/> |<span data-ttu-id="7ca75-p101">未知类型的通用主体。不用于 tblPrincipal 表。</span><span class="sxs-lookup"><span data-stu-id="7ca75-p101">Generic principal with no known type. Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="7ca75-135">2 </span><span class="sxs-lookup"><span data-stu-id="7ca75-135">2</span></span>  <br/> |<span data-ttu-id="7ca75-136">AnyUser</span><span class="sxs-lookup"><span data-stu-id="7ca75-136">AnyUser</span></span>  <br/> |<span data-ttu-id="7ca75-p102">用户类型的通用主体。不用于 tblPrincipal 表。</span><span class="sxs-lookup"><span data-stu-id="7ca75-p102">Generic principal of user type. Not used in tblPrincipal table.</span></span>  <br/> |<span data-ttu-id="7ca75-139">是</span><span class="sxs-lookup"><span data-stu-id="7ca75-139">Yes</span></span>  <br/> |
|<span data-ttu-id="7ca75-140">3 </span><span class="sxs-lookup"><span data-stu-id="7ca75-140">3</span></span>  <br/> |<span data-ttu-id="7ca75-141">AnyGroup</span><span class="sxs-lookup"><span data-stu-id="7ca75-141">AnyGroup</span></span>  <br/> |<span data-ttu-id="7ca75-p103">组语义的通用主体。不用于 tblPrincipal 表。</span><span class="sxs-lookup"><span data-stu-id="7ca75-p103">Generic principal with group semantic. Not used in tblPrincipal table.</span></span>  <br/> ||
|<span data-ttu-id="7ca75-144">4 </span><span class="sxs-lookup"><span data-stu-id="7ca75-144">4</span></span>  <br/> |<span data-ttu-id="7ca75-145">SystemUser</span><span class="sxs-lookup"><span data-stu-id="7ca75-145">SystemUser</span></span>  <br/> |<span data-ttu-id="7ca75-146">持久聊天服务器内部使用的主体。</span><span class="sxs-lookup"><span data-stu-id="7ca75-146">Principal used internally by Persistent Chat Server.</span></span>  <br/> ||
|<span data-ttu-id="7ca75-147">5 </span><span class="sxs-lookup"><span data-stu-id="7ca75-147">5</span></span>  <br/> |<span data-ttu-id="7ca75-148">用户</span><span class="sxs-lookup"><span data-stu-id="7ca75-148">User</span></span>  <br/> |<span data-ttu-id="7ca75-149">常规用户。</span><span class="sxs-lookup"><span data-stu-id="7ca75-149">Regular user.</span></span>  <br/> |<span data-ttu-id="7ca75-150">是</span><span class="sxs-lookup"><span data-stu-id="7ca75-150">Yes</span></span>  <br/> |
|<span data-ttu-id="7ca75-151">8 </span><span class="sxs-lookup"><span data-stu-id="7ca75-151">8</span></span>  <br/> |<span data-ttu-id="7ca75-152">DC</span><span class="sxs-lookup"><span data-stu-id="7ca75-152">DC</span></span>  <br/> |<span data-ttu-id="7ca75-153">Active Directory 域服务域控制器。</span><span class="sxs-lookup"><span data-stu-id="7ca75-153">Active Directory Domain Services domain controller.</span></span>  <br/> ||
|<span data-ttu-id="7ca75-154">9 </span><span class="sxs-lookup"><span data-stu-id="7ca75-154">9</span></span>  <br/> |<span data-ttu-id="7ca75-155">Group</span><span class="sxs-lookup"><span data-stu-id="7ca75-155">Group</span></span>  <br/> |<span data-ttu-id="7ca75-156">Active Directory 安全组。</span><span class="sxs-lookup"><span data-stu-id="7ca75-156">Active Directory security group.</span></span>  <br/> ||
|<span data-ttu-id="7ca75-157">10 </span><span class="sxs-lookup"><span data-stu-id="7ca75-157">10</span></span>  <br/> |<span data-ttu-id="7ca75-158">Folder</span><span class="sxs-lookup"><span data-stu-id="7ca75-158">Folder</span></span>  <br/> |<span data-ttu-id="7ca75-159">Active Directory 容器或组织单位。</span><span class="sxs-lookup"><span data-stu-id="7ca75-159">Active Directory container or organizational unit.</span></span>  <br/> ||
   
## <a name="see-also"></a><span data-ttu-id="7ca75-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7ca75-160">See also</span></span>

[<span data-ttu-id="7ca75-161">tblPrincipal</span><span class="sxs-lookup"><span data-stu-id="7ca75-161">tblPrincipal</span></span>](tblprincipal.md)
