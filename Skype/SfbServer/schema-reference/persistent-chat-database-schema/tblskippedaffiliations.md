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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations 包含无法读取的隶属关系（通常是由于 Active Directory 域服务访问错误）。
ms.openlocfilehash: 8a138993e12a49f72842808d720a5f778195c6ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812010"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="f0487-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="f0487-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="f0487-104">tblSkippedAffiliations 包含无法读取的隶属关系（通常是由于 Active Directory 域服务访问错误）。</span><span class="sxs-lookup"><span data-stu-id="f0487-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="f0487-105">**多**</span><span class="sxs-lookup"><span data-stu-id="f0487-105">**Columns**</span></span>

|<span data-ttu-id="f0487-106">**列**</span><span class="sxs-lookup"><span data-stu-id="f0487-106">**Column**</span></span>|<span data-ttu-id="f0487-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="f0487-107">**Type**</span></span>|<span data-ttu-id="f0487-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="f0487-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f0487-109">prinID</span><span class="sxs-lookup"><span data-stu-id="f0487-109">prinID</span></span>  <br/> |<span data-ttu-id="f0487-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="f0487-110">int, not null</span></span>  <br/> |<span data-ttu-id="f0487-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="f0487-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="f0487-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="f0487-112">affDescription</span></span>  <br/> |<span data-ttu-id="f0487-113">nvarchar （256），not null</span><span class="sxs-lookup"><span data-stu-id="f0487-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="f0487-114">标识隶属关系的字符串。</span><span class="sxs-lookup"><span data-stu-id="f0487-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="f0487-115">格式为： guid： _{0}_ uri： _{1}_> id：_{2}_</span><span class="sxs-lookup"><span data-stu-id="f0487-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="f0487-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="f0487-116">updatedBy</span></span>  <br/> |<span data-ttu-id="f0487-117">int，not null</span><span class="sxs-lookup"><span data-stu-id="f0487-117">int, not null</span></span>  <br/> |<span data-ttu-id="f0487-118">已更新此行的主体的 ID。</span><span class="sxs-lookup"><span data-stu-id="f0487-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="f0487-119">由于 Active Directory 同步是这些条目的唯一源，因此始终为1（系统用户）。</span><span class="sxs-lookup"><span data-stu-id="f0487-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="f0487-120">**标示**</span><span class="sxs-lookup"><span data-stu-id="f0487-120">**Keys**</span></span>

|<span data-ttu-id="f0487-121">**列**</span><span class="sxs-lookup"><span data-stu-id="f0487-121">**Column(s)**</span></span>|<span data-ttu-id="f0487-122">**说明**</span><span class="sxs-lookup"><span data-stu-id="f0487-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f0487-123">\<prinID, affDescription\></span><span class="sxs-lookup"><span data-stu-id="f0487-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="f0487-124">主键。</span><span class="sxs-lookup"><span data-stu-id="f0487-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f0487-125">prinID</span><span class="sxs-lookup"><span data-stu-id="f0487-125">prinID</span></span>  <br/> |<span data-ttu-id="f0487-126">TblPrincipal 表中的 lookup 的外键。</span><span class="sxs-lookup"><span data-stu-id="f0487-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

