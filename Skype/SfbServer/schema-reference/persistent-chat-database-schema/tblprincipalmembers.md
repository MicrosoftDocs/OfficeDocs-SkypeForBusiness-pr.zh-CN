---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers 包含主体成员身份。
ms.openlocfilehash: 93a012ea82acf071a28752eb79682866c0faa418
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831592"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="628b4-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="628b4-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="628b4-104">tblPrincipalMembers 包含主体成员身份。</span><span class="sxs-lookup"><span data-stu-id="628b4-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="628b4-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="628b4-105">**Columns**</span></span>

|<span data-ttu-id="628b4-106">**列**</span><span class="sxs-lookup"><span data-stu-id="628b4-106">**Column**</span></span>|<span data-ttu-id="628b4-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="628b4-107">**Type**</span></span>|<span data-ttu-id="628b4-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="628b4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="628b4-109">prinID</span><span class="sxs-lookup"><span data-stu-id="628b4-109">prinID</span></span>  <br/> |<span data-ttu-id="628b4-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="628b4-110">int, not null</span></span>  <br/> |<span data-ttu-id="628b4-111">主体 ID。</span><span class="sxs-lookup"><span data-stu-id="628b4-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="628b4-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="628b4-112">memberADPath</span></span>  <br/> |<span data-ttu-id="628b4-113">nvarchar (384)，不为 null</span><span class="sxs-lookup"><span data-stu-id="628b4-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="628b4-p101">成员的可分辨名称。成员不必是主体（在 tblPrincipal 表中）。</span><span class="sxs-lookup"><span data-stu-id="628b4-p101">Distinguished name of a member. A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="628b4-116">**Keys**</span><span class="sxs-lookup"><span data-stu-id="628b4-116">**Keys**</span></span>

|<span data-ttu-id="628b4-117">**列**</span><span class="sxs-lookup"><span data-stu-id="628b4-117">**Column**</span></span>|<span data-ttu-id="628b4-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="628b4-118">**Description**</span></span>|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |<span data-ttu-id="628b4-119">主键。</span><span class="sxs-lookup"><span data-stu-id="628b4-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="628b4-120">prinID</span><span class="sxs-lookup"><span data-stu-id="628b4-120">prinID</span></span>  <br/> |<span data-ttu-id="628b4-121">在 tblPrincipal.prinID 中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="628b4-121">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

