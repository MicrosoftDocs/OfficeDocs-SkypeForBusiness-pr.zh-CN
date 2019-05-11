---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers 包含主体成员身份。
ms.openlocfilehash: be66ee6124c7b0306583bcb10f7d78b777fcf10c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904158"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="a81b0-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="a81b0-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="a81b0-104">tblPrincipalMembers 包含主体成员身份。</span><span class="sxs-lookup"><span data-stu-id="a81b0-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="a81b0-105">**列**</span><span class="sxs-lookup"><span data-stu-id="a81b0-105">**Columns**</span></span>

|<span data-ttu-id="a81b0-106">**列**</span><span class="sxs-lookup"><span data-stu-id="a81b0-106">**Column**</span></span>|<span data-ttu-id="a81b0-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="a81b0-107">**Type**</span></span>|<span data-ttu-id="a81b0-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="a81b0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a81b0-109">prinID</span><span class="sxs-lookup"><span data-stu-id="a81b0-109">prinID</span></span>  <br/> |<span data-ttu-id="a81b0-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="a81b0-110">int, not null</span></span>  <br/> |<span data-ttu-id="a81b0-111">主体 id。</span><span class="sxs-lookup"><span data-stu-id="a81b0-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="a81b0-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="a81b0-112">memberADPath</span></span>  <br/> |<span data-ttu-id="a81b0-113">nvarchar (384)，不为 null</span><span class="sxs-lookup"><span data-stu-id="a81b0-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="a81b0-114">成员可分辨的名称。</span><span class="sxs-lookup"><span data-stu-id="a81b0-114">Distinguished name of a member.</span></span> <span data-ttu-id="a81b0-115">成员没有要 （在 tblPrincipal 表中） 的主体。</span><span class="sxs-lookup"><span data-stu-id="a81b0-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="a81b0-116">**键**</span><span class="sxs-lookup"><span data-stu-id="a81b0-116">**Keys**</span></span>

|<span data-ttu-id="a81b0-117">**列**</span><span class="sxs-lookup"><span data-stu-id="a81b0-117">**Column**</span></span>|<span data-ttu-id="a81b0-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="a81b0-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="a81b0-119">\<prinID memberADPath\></span><span class="sxs-lookup"><span data-stu-id="a81b0-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="a81b0-120">主键。</span><span class="sxs-lookup"><span data-stu-id="a81b0-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="a81b0-121">prinID</span><span class="sxs-lookup"><span data-stu-id="a81b0-121">prinID</span></span>  <br/> |<span data-ttu-id="a81b0-122">在 tblPrincipal.prinID 中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="a81b0-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

