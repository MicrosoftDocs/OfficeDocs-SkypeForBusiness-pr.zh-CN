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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers 包含主体成员身份。
ms.openlocfilehash: c56ab16f96322cb295c4eff6fc63e01ba887dd22
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813940"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="b370b-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="b370b-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="b370b-104">tblPrincipalMembers 包含主体成员身份。</span><span class="sxs-lookup"><span data-stu-id="b370b-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="b370b-105">**多**</span><span class="sxs-lookup"><span data-stu-id="b370b-105">**Columns**</span></span>

|<span data-ttu-id="b370b-106">**列**</span><span class="sxs-lookup"><span data-stu-id="b370b-106">**Column**</span></span>|<span data-ttu-id="b370b-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="b370b-107">**Type**</span></span>|<span data-ttu-id="b370b-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="b370b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b370b-109">prinID</span><span class="sxs-lookup"><span data-stu-id="b370b-109">prinID</span></span>  <br/> |<span data-ttu-id="b370b-110">int，not null</span><span class="sxs-lookup"><span data-stu-id="b370b-110">int, not null</span></span>  <br/> |<span data-ttu-id="b370b-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="b370b-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="b370b-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="b370b-112">memberADPath</span></span>  <br/> |<span data-ttu-id="b370b-113">nvarchar （384），not null</span><span class="sxs-lookup"><span data-stu-id="b370b-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="b370b-114">成员的可分辨名称。</span><span class="sxs-lookup"><span data-stu-id="b370b-114">Distinguished name of a member.</span></span> <span data-ttu-id="b370b-115">成员不必是主体（在 tblPrincipal 表中）。</span><span class="sxs-lookup"><span data-stu-id="b370b-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="b370b-116">**标示**</span><span class="sxs-lookup"><span data-stu-id="b370b-116">**Keys**</span></span>

|<span data-ttu-id="b370b-117">**列**</span><span class="sxs-lookup"><span data-stu-id="b370b-117">**Column**</span></span>|<span data-ttu-id="b370b-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="b370b-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b370b-119">\<prinID, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="b370b-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="b370b-120">主键。</span><span class="sxs-lookup"><span data-stu-id="b370b-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="b370b-121">prinID</span><span class="sxs-lookup"><span data-stu-id="b370b-121">prinID</span></span>  <br/> |<span data-ttu-id="b370b-122">在 tblPrincipal 中查找的外键。 prinID。</span><span class="sxs-lookup"><span data-stu-id="b370b-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

