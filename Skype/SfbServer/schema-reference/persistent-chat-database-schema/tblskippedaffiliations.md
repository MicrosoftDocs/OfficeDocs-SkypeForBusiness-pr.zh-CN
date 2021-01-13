---
title: tblSkippedAffiliations
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
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations 包含通常由于 Active Directory 域服务访问错误 (无法读取的附属) 。
ms.openlocfilehash: 3061a399de804898d3dc2c616fb3766206c2d624
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831422"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="65ea2-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="65ea2-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="65ea2-104">tblSkippedAffiliations 包含通常由于 Active Directory 域服务访问错误 (无法读取的附属) 。</span><span class="sxs-lookup"><span data-stu-id="65ea2-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="65ea2-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="65ea2-105">**Columns**</span></span>

|<span data-ttu-id="65ea2-106">**列**</span><span class="sxs-lookup"><span data-stu-id="65ea2-106">**Column**</span></span>|<span data-ttu-id="65ea2-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="65ea2-107">**Type**</span></span>|<span data-ttu-id="65ea2-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="65ea2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="65ea2-109">prinID</span><span class="sxs-lookup"><span data-stu-id="65ea2-109">prinID</span></span>  <br/> |<span data-ttu-id="65ea2-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="65ea2-110">int, not null</span></span>  <br/> |<span data-ttu-id="65ea2-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="65ea2-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="65ea2-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="65ea2-112">affDescription</span></span>  <br/> |<span data-ttu-id="65ea2-113">nvarchar (256)，不为 null</span><span class="sxs-lookup"><span data-stu-id="65ea2-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="65ea2-114">标识隶属项的字符串。</span><span class="sxs-lookup"><span data-stu-id="65ea2-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="65ea2-115">格式为： guid：  _{0}_ uri： _{1}_> id：  _{2}_</span><span class="sxs-lookup"><span data-stu-id="65ea2-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="65ea2-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="65ea2-116">updatedBy</span></span>  <br/> |<span data-ttu-id="65ea2-117">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="65ea2-117">int, not null</span></span>  <br/> |<span data-ttu-id="65ea2-p101">更新此行的主体的 ID。该值始终为 1（系统用户），因为 Active Directory 同步是这些条目的唯一来源。</span><span class="sxs-lookup"><span data-stu-id="65ea2-p101">ID of the principal that updated this row. It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="65ea2-120">**Keys**</span><span class="sxs-lookup"><span data-stu-id="65ea2-120">**Keys**</span></span>

|<span data-ttu-id="65ea2-121">**列 ()**</span><span class="sxs-lookup"><span data-stu-id="65ea2-121">**Column(s)**</span></span>|<span data-ttu-id="65ea2-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="65ea2-122">**Description**</span></span>|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |<span data-ttu-id="65ea2-123">主键。</span><span class="sxs-lookup"><span data-stu-id="65ea2-123">Primary key.</span></span>  <br/> |
|<span data-ttu-id="65ea2-124">prinID</span><span class="sxs-lookup"><span data-stu-id="65ea2-124">prinID</span></span>  <br/> |<span data-ttu-id="65ea2-125">其查找包含在 tblPrincipal.prinID 表中的外键。</span><span class="sxs-lookup"><span data-stu-id="65ea2-125">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

