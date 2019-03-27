---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations 包含的主体附属关系介绍中位置，包括 Active Directory 容器中以及域中的 Active Directory 域服务安全组的成员身份。
ms.openlocfilehash: c93edb552c63ebd4f7344926a7d43858b42506ae
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30897037"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="1dd72-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="1dd72-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="1dd72-104">tblPrincipalAffiliations 包含的主体附属关系介绍中位置，包括 Active Directory 容器中以及域中的 Active Directory 域服务安全组的成员身份。</span><span class="sxs-lookup"><span data-stu-id="1dd72-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="1dd72-105">**列**</span><span class="sxs-lookup"><span data-stu-id="1dd72-105">**Columns**</span></span>

|<span data-ttu-id="1dd72-106">**列**</span><span class="sxs-lookup"><span data-stu-id="1dd72-106">**Column**</span></span>|<span data-ttu-id="1dd72-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="1dd72-107">**Type**</span></span>|<span data-ttu-id="1dd72-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="1dd72-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1dd72-109">principalID</span><span class="sxs-lookup"><span data-stu-id="1dd72-109">principalID</span></span>  <br/> |<span data-ttu-id="1dd72-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="1dd72-110">int, not null</span></span>  <br/> |<span data-ttu-id="1dd72-111">附属主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="1dd72-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="1dd72-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="1dd72-112">affiliationID</span></span>  <br/> |<span data-ttu-id="1dd72-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="1dd72-113">int, not null</span></span>  <br/> |<span data-ttu-id="1dd72-114">表示隶属项的主体 ID。</span><span class="sxs-lookup"><span data-stu-id="1dd72-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="1dd72-115">（除系统用户类型） 的每个主体具有自我从属关系以及。</span><span class="sxs-lookup"><span data-stu-id="1dd72-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="1dd72-116">索引</span><span class="sxs-lookup"><span data-stu-id="1dd72-116">index</span></span>  <br/> |<span data-ttu-id="1dd72-117">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="1dd72-117">int, not null</span></span>  <br/> |<span data-ttu-id="1dd72-118">索引。</span><span class="sxs-lookup"><span data-stu-id="1dd72-118">Index.</span></span> <span data-ttu-id="1dd72-119">自我隶属项的值为-1，并且其他隶属项的会增加按顺序从 1 中每个\<principalID，affiliationId\>地址散列表元。</span><span class="sxs-lookup"><span data-stu-id="1dd72-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="1dd72-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="1dd72-120">updatedBy</span></span>  <br/> |<span data-ttu-id="1dd72-121">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="1dd72-121">int, not null</span></span>  <br/> |<span data-ttu-id="1dd72-122">执行最新更新的主体。</span><span class="sxs-lookup"><span data-stu-id="1dd72-122">Principal that did the latest update.</span></span> <span data-ttu-id="1dd72-123">这通常是 1，这意味着 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="1dd72-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="1dd72-124">**键**</span><span class="sxs-lookup"><span data-stu-id="1dd72-124">**Keys**</span></span>

|<span data-ttu-id="1dd72-125">**列**</span><span class="sxs-lookup"><span data-stu-id="1dd72-125">**Columns**</span></span>|<span data-ttu-id="1dd72-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="1dd72-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1dd72-127">\<principalID、 索引、 affiliationID\></span><span class="sxs-lookup"><span data-stu-id="1dd72-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="1dd72-128">主键。</span><span class="sxs-lookup"><span data-stu-id="1dd72-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="1dd72-129">principalID</span><span class="sxs-lookup"><span data-stu-id="1dd72-129">principalID</span></span>  <br/> |<span data-ttu-id="1dd72-130">在 tblPrincipal.prinID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="1dd72-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="1dd72-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="1dd72-131">affiliationID</span></span>  <br/> |<span data-ttu-id="1dd72-132">在 tblPrincipal.prinID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="1dd72-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

