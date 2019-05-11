---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations 包含的主体附属关系介绍中位置，包括 Active Directory 容器中以及域中的 Active Directory 域服务安全组的成员身份。
ms.openlocfilehash: fb1bd8eb7291ba001a5c23240c2de70aaff048b1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929817"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="b86e6-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="b86e6-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="b86e6-104">tblPrincipalAffiliations 包含的主体附属关系介绍中位置，包括 Active Directory 容器中以及域中的 Active Directory 域服务安全组的成员身份。</span><span class="sxs-lookup"><span data-stu-id="b86e6-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="b86e6-105">**列**</span><span class="sxs-lookup"><span data-stu-id="b86e6-105">**Columns**</span></span>

|<span data-ttu-id="b86e6-106">**列**</span><span class="sxs-lookup"><span data-stu-id="b86e6-106">**Column**</span></span>|<span data-ttu-id="b86e6-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="b86e6-107">**Type**</span></span>|<span data-ttu-id="b86e6-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="b86e6-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b86e6-109">principalID</span><span class="sxs-lookup"><span data-stu-id="b86e6-109">principalID</span></span>  <br/> |<span data-ttu-id="b86e6-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="b86e6-110">int, not null</span></span>  <br/> |<span data-ttu-id="b86e6-111">附属主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="b86e6-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="b86e6-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="b86e6-112">affiliationID</span></span>  <br/> |<span data-ttu-id="b86e6-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="b86e6-113">int, not null</span></span>  <br/> |<span data-ttu-id="b86e6-114">表示隶属项的主体 ID。</span><span class="sxs-lookup"><span data-stu-id="b86e6-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="b86e6-115">（除系统用户类型） 的每个主体具有自我从属关系以及。</span><span class="sxs-lookup"><span data-stu-id="b86e6-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="b86e6-116">索引</span><span class="sxs-lookup"><span data-stu-id="b86e6-116">index</span></span>  <br/> |<span data-ttu-id="b86e6-117">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="b86e6-117">int, not null</span></span>  <br/> |<span data-ttu-id="b86e6-118">索引。</span><span class="sxs-lookup"><span data-stu-id="b86e6-118">Index.</span></span> <span data-ttu-id="b86e6-119">自我隶属项的值为-1，并且其他隶属项的会增加按顺序从 1 中每个\<principalID，affiliationId\>地址散列表元。</span><span class="sxs-lookup"><span data-stu-id="b86e6-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="b86e6-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="b86e6-120">updatedBy</span></span>  <br/> |<span data-ttu-id="b86e6-121">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="b86e6-121">int, not null</span></span>  <br/> |<span data-ttu-id="b86e6-122">执行最新更新的主体。</span><span class="sxs-lookup"><span data-stu-id="b86e6-122">Principal that did the latest update.</span></span> <span data-ttu-id="b86e6-123">这通常是 1，这意味着 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="b86e6-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="b86e6-124">**键**</span><span class="sxs-lookup"><span data-stu-id="b86e6-124">**Keys**</span></span>

|<span data-ttu-id="b86e6-125">**列**</span><span class="sxs-lookup"><span data-stu-id="b86e6-125">**Columns**</span></span>|<span data-ttu-id="b86e6-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="b86e6-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b86e6-127">\<principalID、 索引、 affiliationID\></span><span class="sxs-lookup"><span data-stu-id="b86e6-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="b86e6-128">主键。</span><span class="sxs-lookup"><span data-stu-id="b86e6-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b86e6-129">principalID</span><span class="sxs-lookup"><span data-stu-id="b86e6-129">principalID</span></span>  <br/> |<span data-ttu-id="b86e6-130">在 tblPrincipal.prinID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="b86e6-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="b86e6-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="b86e6-131">affiliationID</span></span>  <br/> |<span data-ttu-id="b86e6-132">在 tblPrincipal.prinID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="b86e6-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

