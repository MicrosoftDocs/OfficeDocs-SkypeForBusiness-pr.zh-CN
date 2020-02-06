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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations 包含描述位置中的成员身份的主体成员，包括 Active directory 域服务安全组，位于 Active Directory 容器中的域中。
ms.openlocfilehash: 542bcc333d815b0577aec1fb11d4070540150d3c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814470"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="78450-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="78450-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="78450-104">tblPrincipalAffiliations 包含描述位置中的成员身份的主体成员，包括 Active directory 域服务安全组，位于 Active Directory 容器中的域中。</span><span class="sxs-lookup"><span data-stu-id="78450-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="78450-105">**多**</span><span class="sxs-lookup"><span data-stu-id="78450-105">**Columns**</span></span>

|<span data-ttu-id="78450-106">**列**</span><span class="sxs-lookup"><span data-stu-id="78450-106">**Column**</span></span>|<span data-ttu-id="78450-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="78450-107">**Type**</span></span>|<span data-ttu-id="78450-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="78450-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="78450-109">principalID</span><span class="sxs-lookup"><span data-stu-id="78450-109">principalID</span></span>  <br/> |<span data-ttu-id="78450-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="78450-110">int, not null</span></span>  <br/> |<span data-ttu-id="78450-111">关联主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="78450-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="78450-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="78450-112">affiliationID</span></span>  <br/> |<span data-ttu-id="78450-113">int，not null</span><span class="sxs-lookup"><span data-stu-id="78450-113">int, not null</span></span>  <br/> |<span data-ttu-id="78450-114">表示隶属关系的承担者的 ID。</span><span class="sxs-lookup"><span data-stu-id="78450-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="78450-115">每个主体（除系统用户类型外）还具有自我隶属关系。</span><span class="sxs-lookup"><span data-stu-id="78450-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="78450-116">食指</span><span class="sxs-lookup"><span data-stu-id="78450-116">index</span></span>  <br/> |<span data-ttu-id="78450-117">int，not null</span><span class="sxs-lookup"><span data-stu-id="78450-117">int, not null</span></span>  <br/> |<span data-ttu-id="78450-118">食指.</span><span class="sxs-lookup"><span data-stu-id="78450-118">Index.</span></span> <span data-ttu-id="78450-119">自隶属关系的值是-1，对于其他隶属关系，在每个\<PrincipalID、affiliationId\>存储桶中，它将按从1开始递增。</span><span class="sxs-lookup"><span data-stu-id="78450-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="78450-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="78450-120">updatedBy</span></span>  <br/> |<span data-ttu-id="78450-121">int，not null</span><span class="sxs-lookup"><span data-stu-id="78450-121">int, not null</span></span>  <br/> |<span data-ttu-id="78450-122">已进行最新更新的主体。</span><span class="sxs-lookup"><span data-stu-id="78450-122">Principal that did the latest update.</span></span> <span data-ttu-id="78450-123">这通常是1，这意味着 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="78450-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="78450-124">**标示**</span><span class="sxs-lookup"><span data-stu-id="78450-124">**Keys**</span></span>

|<span data-ttu-id="78450-125">**多**</span><span class="sxs-lookup"><span data-stu-id="78450-125">**Columns**</span></span>|<span data-ttu-id="78450-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="78450-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="78450-127">\<principalID、index、affiliationID\></span><span class="sxs-lookup"><span data-stu-id="78450-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="78450-128">主键。</span><span class="sxs-lookup"><span data-stu-id="78450-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="78450-129">principalID</span><span class="sxs-lookup"><span data-stu-id="78450-129">principalID</span></span>  <br/> |<span data-ttu-id="78450-130">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="78450-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="78450-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="78450-131">affiliationID</span></span>  <br/> |<span data-ttu-id="78450-132">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="78450-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

