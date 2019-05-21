---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations 包含无法读取的隶属关系 (通常是由于 Active Directory 域服务访问错误)。
ms.openlocfilehash: 481bf92a4014bf2af8e1c4794d1793f2c93e7c36
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295151"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="376fe-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="376fe-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="376fe-104">tblSkippedAffiliations 包含无法读取的隶属关系 (通常是由于 Active Directory 域服务访问错误)。</span><span class="sxs-lookup"><span data-stu-id="376fe-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="376fe-105">**多**</span><span class="sxs-lookup"><span data-stu-id="376fe-105">**Columns**</span></span>

|<span data-ttu-id="376fe-106">**列**</span><span class="sxs-lookup"><span data-stu-id="376fe-106">**Column**</span></span>|<span data-ttu-id="376fe-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="376fe-107">**Type**</span></span>|<span data-ttu-id="376fe-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="376fe-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="376fe-109">prinID</span><span class="sxs-lookup"><span data-stu-id="376fe-109">prinID</span></span>  <br/> |<span data-ttu-id="376fe-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="376fe-110">int, not null</span></span>  <br/> |<span data-ttu-id="376fe-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="376fe-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="376fe-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="376fe-112">affDescription</span></span>  <br/> |<span data-ttu-id="376fe-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="376fe-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="376fe-114">标识隶属关系的字符串。</span><span class="sxs-lookup"><span data-stu-id="376fe-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="376fe-115">格式为: guid: _{0}_ uri: _{1}_> id:_{2}_</span><span class="sxs-lookup"><span data-stu-id="376fe-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="376fe-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="376fe-116">updatedBy</span></span>  <br/> |<span data-ttu-id="376fe-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="376fe-117">int, not null</span></span>  <br/> |<span data-ttu-id="376fe-118">已更新此行的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="376fe-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="376fe-119">由于 Active Directory 同步是这些条目的唯一源, 因此始终为 1 (系统用户)。</span><span class="sxs-lookup"><span data-stu-id="376fe-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="376fe-120">**标示**</span><span class="sxs-lookup"><span data-stu-id="376fe-120">**Keys**</span></span>

|<span data-ttu-id="376fe-121">**列**</span><span class="sxs-lookup"><span data-stu-id="376fe-121">**Column(s)**</span></span>|<span data-ttu-id="376fe-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="376fe-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="376fe-123">\<prinID, affDescription\></span><span class="sxs-lookup"><span data-stu-id="376fe-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="376fe-124">主键。</span><span class="sxs-lookup"><span data-stu-id="376fe-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="376fe-125">prinID</span><span class="sxs-lookup"><span data-stu-id="376fe-125">prinID</span></span>  <br/> |<span data-ttu-id="376fe-126">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="376fe-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

