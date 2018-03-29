---
title: tblPrincipalAffiliations
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations 包含主体的隶属关系描述的位置，包括 Active Directory 域服务安全组，请在域中的 Active Directory 容器中的成员。
ms.openlocfilehash: 4e5529590a6a636c28c801392953c7fd69e9f649
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="44400-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="44400-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="44400-104">tblPrincipalAffiliations 包含主体的隶属关系描述的位置，包括 Active Directory 域服务安全组，请在域中的 Active Directory 容器中的成员。</span><span class="sxs-lookup"><span data-stu-id="44400-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="44400-105">**列**</span><span class="sxs-lookup"><span data-stu-id="44400-105">**Columns**</span></span>

|<span data-ttu-id="44400-106">**列**</span><span class="sxs-lookup"><span data-stu-id="44400-106">**Column**</span></span>|<span data-ttu-id="44400-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="44400-107">**Type**</span></span>|<span data-ttu-id="44400-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="44400-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="44400-109">principalID</span><span class="sxs-lookup"><span data-stu-id="44400-109">principalID</span></span>  <br/> |<span data-ttu-id="44400-110">int，不为空</span><span class="sxs-lookup"><span data-stu-id="44400-110">int, not null</span></span>  <br/> |<span data-ttu-id="44400-111">相关主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="44400-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="44400-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="44400-112">affiliationID</span></span>  <br/> |<span data-ttu-id="44400-113">int，不为空</span><span class="sxs-lookup"><span data-stu-id="44400-113">int, not null</span></span>  <br/> |<span data-ttu-id="44400-114">表示该隶属关系主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="44400-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="44400-115">每个主体 （除了系统用户类型） 具有自我的隶属关系也。</span><span class="sxs-lookup"><span data-stu-id="44400-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="44400-116">索引</span><span class="sxs-lookup"><span data-stu-id="44400-116">index</span></span>  <br/> |<span data-ttu-id="44400-117">int，不为空</span><span class="sxs-lookup"><span data-stu-id="44400-117">int, not null</span></span>  <br/> |<span data-ttu-id="44400-118">索引。</span><span class="sxs-lookup"><span data-stu-id="44400-118">Index.</span></span> <span data-ttu-id="44400-119">自我的隶属关系的值为-1，并且为其他附属机构会增加按顺序从 1，其中每个\<principalID，affiliationId\>桶。</span><span class="sxs-lookup"><span data-stu-id="44400-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="44400-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="44400-120">updatedBy</span></span>  <br/> |<span data-ttu-id="44400-121">int，不为空</span><span class="sxs-lookup"><span data-stu-id="44400-121">int, not null</span></span>  <br/> |<span data-ttu-id="44400-122">做最新的更新的主体。</span><span class="sxs-lookup"><span data-stu-id="44400-122">Principal that did the latest update.</span></span> <span data-ttu-id="44400-123">这通常是 1，这意味着活动目录同步。</span><span class="sxs-lookup"><span data-stu-id="44400-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="44400-124">**密钥**</span><span class="sxs-lookup"><span data-stu-id="44400-124">**Keys**</span></span>

|<span data-ttu-id="44400-125">**列**</span><span class="sxs-lookup"><span data-stu-id="44400-125">**Columns**</span></span>|<span data-ttu-id="44400-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="44400-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="44400-127">\<principalID、 索引、 affiliationID\></span><span class="sxs-lookup"><span data-stu-id="44400-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="44400-128">为主键。</span><span class="sxs-lookup"><span data-stu-id="44400-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="44400-129">principalID</span><span class="sxs-lookup"><span data-stu-id="44400-129">principalID</span></span>  <br/> |<span data-ttu-id="44400-130">TblPrincipal.prinID 表中查找与外键。</span><span class="sxs-lookup"><span data-stu-id="44400-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="44400-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="44400-131">affiliationID</span></span>  <br/> |<span data-ttu-id="44400-132">TblPrincipal.prinID 表中查找与外键。</span><span class="sxs-lookup"><span data-stu-id="44400-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

