---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations 包含描述位置中的成员身份的主体成员, 包括 Active directory 域服务安全组, 位于 Active Directory 容器中的域中。
ms.openlocfilehash: cda9827f4a4ab7e17a156cc867e4925c88d06ff3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295312"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="a41fa-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="a41fa-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="a41fa-104">tblPrincipalAffiliations 包含描述位置中的成员身份的主体成员, 包括 Active directory 域服务安全组, 位于 Active Directory 容器中的域中。</span><span class="sxs-lookup"><span data-stu-id="a41fa-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="a41fa-105">**多**</span><span class="sxs-lookup"><span data-stu-id="a41fa-105">**Columns**</span></span>

|<span data-ttu-id="a41fa-106">**列**</span><span class="sxs-lookup"><span data-stu-id="a41fa-106">**Column**</span></span>|<span data-ttu-id="a41fa-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="a41fa-107">**Type**</span></span>|<span data-ttu-id="a41fa-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="a41fa-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a41fa-109">principalID</span><span class="sxs-lookup"><span data-stu-id="a41fa-109">principalID</span></span>  <br/> |<span data-ttu-id="a41fa-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="a41fa-110">int, not null</span></span>  <br/> |<span data-ttu-id="a41fa-111">关联主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="a41fa-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="a41fa-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="a41fa-112">affiliationID</span></span>  <br/> |<span data-ttu-id="a41fa-113">int, not null</span><span class="sxs-lookup"><span data-stu-id="a41fa-113">int, not null</span></span>  <br/> |<span data-ttu-id="a41fa-114">表示隶属关系的承担者的 ID。</span><span class="sxs-lookup"><span data-stu-id="a41fa-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="a41fa-115">每个主体 (除系统用户类型外) 还具有自我隶属关系。</span><span class="sxs-lookup"><span data-stu-id="a41fa-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="a41fa-116">食指</span><span class="sxs-lookup"><span data-stu-id="a41fa-116">index</span></span>  <br/> |<span data-ttu-id="a41fa-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="a41fa-117">int, not null</span></span>  <br/> |<span data-ttu-id="a41fa-118">食指.</span><span class="sxs-lookup"><span data-stu-id="a41fa-118">Index.</span></span> <span data-ttu-id="a41fa-119">自隶属关系的值是-1, 对于其他隶属关系, 在每个\<PrincipalID、affiliationId\>存储桶中, 它将按从1开始递增。</span><span class="sxs-lookup"><span data-stu-id="a41fa-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="a41fa-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="a41fa-120">updatedBy</span></span>  <br/> |<span data-ttu-id="a41fa-121">int, not null</span><span class="sxs-lookup"><span data-stu-id="a41fa-121">int, not null</span></span>  <br/> |<span data-ttu-id="a41fa-122">已进行最新更新的主体。</span><span class="sxs-lookup"><span data-stu-id="a41fa-122">Principal that did the latest update.</span></span> <span data-ttu-id="a41fa-123">这通常是 1, 这意味着 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="a41fa-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="a41fa-124">**标示**</span><span class="sxs-lookup"><span data-stu-id="a41fa-124">**Keys**</span></span>

|<span data-ttu-id="a41fa-125">**多**</span><span class="sxs-lookup"><span data-stu-id="a41fa-125">**Columns**</span></span>|<span data-ttu-id="a41fa-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="a41fa-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a41fa-127">\<principalID、index、affiliationID\></span><span class="sxs-lookup"><span data-stu-id="a41fa-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="a41fa-128">主键。</span><span class="sxs-lookup"><span data-stu-id="a41fa-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a41fa-129">principalID</span><span class="sxs-lookup"><span data-stu-id="a41fa-129">principalID</span></span>  <br/> |<span data-ttu-id="a41fa-130">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="a41fa-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="a41fa-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="a41fa-131">affiliationID</span></span>  <br/> |<span data-ttu-id="a41fa-132">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="a41fa-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

