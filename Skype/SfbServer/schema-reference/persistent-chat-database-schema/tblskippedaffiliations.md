---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations 包含 （通常因为 Active Directory 域服务访问错误） 无法读取的附属关系。
ms.openlocfilehash: 85fe836e75409a0a6aae22583358f9f88dc8d4e1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924939"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="2359d-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="2359d-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="2359d-104">tblSkippedAffiliations 包含 （通常因为 Active Directory 域服务访问错误） 无法读取的附属关系。</span><span class="sxs-lookup"><span data-stu-id="2359d-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="2359d-105">**列**</span><span class="sxs-lookup"><span data-stu-id="2359d-105">**Columns**</span></span>

|<span data-ttu-id="2359d-106">**列**</span><span class="sxs-lookup"><span data-stu-id="2359d-106">**Column**</span></span>|<span data-ttu-id="2359d-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="2359d-107">**Type**</span></span>|<span data-ttu-id="2359d-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="2359d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2359d-109">prinID</span><span class="sxs-lookup"><span data-stu-id="2359d-109">prinID</span></span>  <br/> |<span data-ttu-id="2359d-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="2359d-110">int, not null</span></span>  <br/> |<span data-ttu-id="2359d-111">主体 id。</span><span class="sxs-lookup"><span data-stu-id="2359d-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="2359d-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="2359d-112">affDescription</span></span>  <br/> |<span data-ttu-id="2359d-113">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="2359d-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="2359d-114">标识隶属项的字符串。</span><span class="sxs-lookup"><span data-stu-id="2359d-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="2359d-115">格式为： guid: _{0}_ uri: _{1}_> id:_{2}_</span><span class="sxs-lookup"><span data-stu-id="2359d-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="2359d-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="2359d-116">updatedBy</span></span>  <br/> |<span data-ttu-id="2359d-117">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="2359d-117">int, not null</span></span>  <br/> |<span data-ttu-id="2359d-118">更新此行的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="2359d-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="2359d-119">由于 Active Directory 同步这些条目的唯一源，它始终是 1 （系统用户）。</span><span class="sxs-lookup"><span data-stu-id="2359d-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="2359d-120">**键**</span><span class="sxs-lookup"><span data-stu-id="2359d-120">**Keys**</span></span>

|<span data-ttu-id="2359d-121">**列**</span><span class="sxs-lookup"><span data-stu-id="2359d-121">**Column(s)**</span></span>|<span data-ttu-id="2359d-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="2359d-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2359d-123">\<prinID affDescription\></span><span class="sxs-lookup"><span data-stu-id="2359d-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="2359d-124">主键。</span><span class="sxs-lookup"><span data-stu-id="2359d-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="2359d-125">prinID</span><span class="sxs-lookup"><span data-stu-id="2359d-125">prinID</span></span>  <br/> |<span data-ttu-id="2359d-126">在 tblPrincipal.prinID 表中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="2359d-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

