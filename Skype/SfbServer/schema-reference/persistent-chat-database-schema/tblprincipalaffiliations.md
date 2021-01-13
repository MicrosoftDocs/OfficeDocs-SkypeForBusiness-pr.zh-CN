---
title: tblPrincipalAffiliations
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
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations 包含描述位置（包括 Active Directory 域服务安全组、Active Directory 容器中的域）中成员身份的主体附属关系。
ms.openlocfilehash: 149bb1b4603fa0f0e1909298659b881000464275
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815862"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="da451-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="da451-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="da451-104">tblPrincipalAffiliations 包含描述位置（包括 Active Directory 域服务安全组、Active Directory 容器中的域）中成员身份的主体附属关系。</span><span class="sxs-lookup"><span data-stu-id="da451-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="da451-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="da451-105">**Columns**</span></span>

|<span data-ttu-id="da451-106">**列**</span><span class="sxs-lookup"><span data-stu-id="da451-106">**Column**</span></span>|<span data-ttu-id="da451-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="da451-107">**Type**</span></span>|<span data-ttu-id="da451-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="da451-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="da451-109">principalID</span><span class="sxs-lookup"><span data-stu-id="da451-109">principalID</span></span>  <br/> |<span data-ttu-id="da451-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="da451-110">int, not null</span></span>  <br/> |<span data-ttu-id="da451-111">附属主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="da451-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="da451-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="da451-112">affiliationID</span></span>  <br/> |<span data-ttu-id="da451-113">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="da451-113">int, not null</span></span>  <br/> |<span data-ttu-id="da451-p101">表示附属关系的主体的 ID。每个主体（系统用户类型除外）还具有自附属关系。</span><span class="sxs-lookup"><span data-stu-id="da451-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="da451-116">index</span><span class="sxs-lookup"><span data-stu-id="da451-116">index</span></span>  <br/> |<span data-ttu-id="da451-117">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="da451-117">int, not null</span></span>  <br/> |<span data-ttu-id="da451-118">索引。</span><span class="sxs-lookup"><span data-stu-id="da451-118">Index.</span></span> <span data-ttu-id="da451-119">自附属关系的值为 -1，对于其他附属关系，该值从每个存储桶中的 1 依次 \<principalID, affiliationId\> 增加。</span><span class="sxs-lookup"><span data-stu-id="da451-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="da451-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="da451-120">updatedBy</span></span>  <br/> |<span data-ttu-id="da451-121">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="da451-121">int, not null</span></span>  <br/> |<span data-ttu-id="da451-p103">进行最新更新的主体。这通常为 1，表示 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="da451-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="da451-124">**Keys**</span><span class="sxs-lookup"><span data-stu-id="da451-124">**Keys**</span></span>

|<span data-ttu-id="da451-125">**Columns**</span><span class="sxs-lookup"><span data-stu-id="da451-125">**Columns**</span></span>|<span data-ttu-id="da451-126">**说明**</span><span class="sxs-lookup"><span data-stu-id="da451-126">**Description**</span></span>|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |<span data-ttu-id="da451-127">主键。</span><span class="sxs-lookup"><span data-stu-id="da451-127">Primary key.</span></span>  <br/> |
|<span data-ttu-id="da451-128">principalID</span><span class="sxs-lookup"><span data-stu-id="da451-128">principalID</span></span>  <br/> |<span data-ttu-id="da451-129">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="da451-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="da451-130">affiliationID</span><span class="sxs-lookup"><span data-stu-id="da451-130">affiliationID</span></span>  <br/> |<span data-ttu-id="da451-131">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="da451-131">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

