---
title: tblPrincipalMembers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers 包含主体的成员资格。
ms.openlocfilehash: 77151cc245b90fa22d9da426a1448c49866dccc2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="eb605-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="eb605-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="eb605-104">tblPrincipalMembers 包含主体的成员资格。</span><span class="sxs-lookup"><span data-stu-id="eb605-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="eb605-105">**列**</span><span class="sxs-lookup"><span data-stu-id="eb605-105">**Columns**</span></span>

|<span data-ttu-id="eb605-106">**列**</span><span class="sxs-lookup"><span data-stu-id="eb605-106">**Column**</span></span>|<span data-ttu-id="eb605-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="eb605-107">**Type**</span></span>|<span data-ttu-id="eb605-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="eb605-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="eb605-109">prinID</span><span class="sxs-lookup"><span data-stu-id="eb605-109">prinID</span></span>  <br/> |<span data-ttu-id="eb605-110">int，不为空</span><span class="sxs-lookup"><span data-stu-id="eb605-110">int, not null</span></span>  <br/> |<span data-ttu-id="eb605-111">主体标识。</span><span class="sxs-lookup"><span data-stu-id="eb605-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="eb605-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="eb605-112">memberADPath</span></span>  <br/> |<span data-ttu-id="eb605-113">nvarchar (384) 不为空</span><span class="sxs-lookup"><span data-stu-id="eb605-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="eb605-114">成员的可分辨的名称。</span><span class="sxs-lookup"><span data-stu-id="eb605-114">Distinguished name of a member.</span></span> <span data-ttu-id="eb605-115">成员不需要是一个主体 （在 tblPrincipal 表中）。</span><span class="sxs-lookup"><span data-stu-id="eb605-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="eb605-116">**密钥**</span><span class="sxs-lookup"><span data-stu-id="eb605-116">**Keys**</span></span>

|<span data-ttu-id="eb605-117">**列**</span><span class="sxs-lookup"><span data-stu-id="eb605-117">**Column**</span></span>|<span data-ttu-id="eb605-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="eb605-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="eb605-119">\<prinID memberADPath\></span><span class="sxs-lookup"><span data-stu-id="eb605-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="eb605-120">为主键。</span><span class="sxs-lookup"><span data-stu-id="eb605-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="eb605-121">prinID</span><span class="sxs-lookup"><span data-stu-id="eb605-121">prinID</span></span>  <br/> |<span data-ttu-id="eb605-122">在 tblPrincipal.prinID 中查找与外键。</span><span class="sxs-lookup"><span data-stu-id="eb605-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

