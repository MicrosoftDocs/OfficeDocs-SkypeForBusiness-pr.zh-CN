---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers 包含主体成员身份。
ms.openlocfilehash: 12c3bf86b7416665f0f2355af0bfc9f98e3c1f1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295284"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="65b42-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="65b42-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="65b42-104">tblPrincipalMembers 包含主体成员身份。</span><span class="sxs-lookup"><span data-stu-id="65b42-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="65b42-105">**多**</span><span class="sxs-lookup"><span data-stu-id="65b42-105">**Columns**</span></span>

|<span data-ttu-id="65b42-106">**列**</span><span class="sxs-lookup"><span data-stu-id="65b42-106">**Column**</span></span>|<span data-ttu-id="65b42-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="65b42-107">**Type**</span></span>|<span data-ttu-id="65b42-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="65b42-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="65b42-109">prinID</span><span class="sxs-lookup"><span data-stu-id="65b42-109">prinID</span></span>  <br/> |<span data-ttu-id="65b42-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="65b42-110">int, not null</span></span>  <br/> |<span data-ttu-id="65b42-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="65b42-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="65b42-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="65b42-112">memberADPath</span></span>  <br/> |<span data-ttu-id="65b42-113">nvarchar (384), not null</span><span class="sxs-lookup"><span data-stu-id="65b42-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="65b42-114">成员的可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="65b42-114">Distinguished name of a member.</span></span> <span data-ttu-id="65b42-115">成员不必是主体 (在 tblPrincipal 表中)。</span><span class="sxs-lookup"><span data-stu-id="65b42-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="65b42-116">**标示**</span><span class="sxs-lookup"><span data-stu-id="65b42-116">**Keys**</span></span>

|<span data-ttu-id="65b42-117">**列**</span><span class="sxs-lookup"><span data-stu-id="65b42-117">**Column**</span></span>|<span data-ttu-id="65b42-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="65b42-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="65b42-119">\<prinID, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="65b42-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="65b42-120">主键。</span><span class="sxs-lookup"><span data-stu-id="65b42-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="65b42-121">prinID</span><span class="sxs-lookup"><span data-stu-id="65b42-121">prinID</span></span>  <br/> |<span data-ttu-id="65b42-122">在 tblPrincipal 中查找的外键。 prinID。</span><span class="sxs-lookup"><span data-stu-id="65b42-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

