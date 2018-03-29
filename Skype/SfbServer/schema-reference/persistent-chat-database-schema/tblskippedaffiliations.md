---
title: tblSkippedAffiliations
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations 包含无法读取 （通常是因为 Active Directory 域服务访问错误） 隶属关系。
ms.openlocfilehash: 8809e75f7da7f08c3dee9a846cef332d9cba4371
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="cd7f1-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="cd7f1-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="cd7f1-104">tblSkippedAffiliations 包含无法读取 （通常是因为 Active Directory 域服务访问错误） 隶属关系。</span><span class="sxs-lookup"><span data-stu-id="cd7f1-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="cd7f1-105">**列**</span><span class="sxs-lookup"><span data-stu-id="cd7f1-105">**Columns**</span></span>

|<span data-ttu-id="cd7f1-106">**列**</span><span class="sxs-lookup"><span data-stu-id="cd7f1-106">**Column**</span></span>|<span data-ttu-id="cd7f1-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="cd7f1-107">**Type**</span></span>|<span data-ttu-id="cd7f1-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="cd7f1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cd7f1-109">prinID</span><span class="sxs-lookup"><span data-stu-id="cd7f1-109">prinID</span></span>  <br/> |<span data-ttu-id="cd7f1-110">int，不为空</span><span class="sxs-lookup"><span data-stu-id="cd7f1-110">int, not null</span></span>  <br/> |<span data-ttu-id="cd7f1-111">主体标识。</span><span class="sxs-lookup"><span data-stu-id="cd7f1-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="cd7f1-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="cd7f1-112">affDescription</span></span>  <br/> |<span data-ttu-id="cd7f1-113">nvarchar (256) 不为空</span><span class="sxs-lookup"><span data-stu-id="cd7f1-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="cd7f1-114">一个字符串，它标识该隶属关系。</span><span class="sxs-lookup"><span data-stu-id="cd7f1-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="cd7f1-115">格式是： guid: _{0}_ uri: _{1}_> id: _{2}_</span><span class="sxs-lookup"><span data-stu-id="cd7f1-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="cd7f1-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="cd7f1-116">updatedBy</span></span>  <br/> |<span data-ttu-id="cd7f1-117">int，不为空</span><span class="sxs-lookup"><span data-stu-id="cd7f1-117">int, not null</span></span>  <br/> |<span data-ttu-id="cd7f1-118">更新此行的主要用户的 ID。</span><span class="sxs-lookup"><span data-stu-id="cd7f1-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="cd7f1-119">它始终是 1 （系统用户），因为活动目录同步是这些条目的唯一来源。</span><span class="sxs-lookup"><span data-stu-id="cd7f1-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="cd7f1-120">**密钥**</span><span class="sxs-lookup"><span data-stu-id="cd7f1-120">**Keys**</span></span>

|<span data-ttu-id="cd7f1-121">**列**</span><span class="sxs-lookup"><span data-stu-id="cd7f1-121">**Column(s)**</span></span>|<span data-ttu-id="cd7f1-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="cd7f1-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cd7f1-123">\<prinID affDescription\></span><span class="sxs-lookup"><span data-stu-id="cd7f1-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="cd7f1-124">为主键。</span><span class="sxs-lookup"><span data-stu-id="cd7f1-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="cd7f1-125">prinID</span><span class="sxs-lookup"><span data-stu-id="cd7f1-125">prinID</span></span>  <br/> |<span data-ttu-id="cd7f1-126">TblPrincipal.prinID 表中查找与外键。</span><span class="sxs-lookup"><span data-stu-id="cd7f1-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

