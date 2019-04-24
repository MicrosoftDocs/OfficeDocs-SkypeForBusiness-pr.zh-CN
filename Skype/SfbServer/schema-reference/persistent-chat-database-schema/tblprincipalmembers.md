---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers 包含主体成员身份。
ms.openlocfilehash: 2b2b9616c76095ec27178887e69dd482bcf6da92
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212486"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="56a10-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="56a10-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="56a10-104">tblPrincipalMembers 包含主体成员身份。</span><span class="sxs-lookup"><span data-stu-id="56a10-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="56a10-105">**列**</span><span class="sxs-lookup"><span data-stu-id="56a10-105">**Columns**</span></span>

|<span data-ttu-id="56a10-106">**列**</span><span class="sxs-lookup"><span data-stu-id="56a10-106">**Column**</span></span>|<span data-ttu-id="56a10-107">**类型**</span><span class="sxs-lookup"><span data-stu-id="56a10-107">**Type**</span></span>|<span data-ttu-id="56a10-108">**说明**</span><span class="sxs-lookup"><span data-stu-id="56a10-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="56a10-109">prinID</span><span class="sxs-lookup"><span data-stu-id="56a10-109">prinID</span></span>  <br/> |<span data-ttu-id="56a10-110">int，不为 null</span><span class="sxs-lookup"><span data-stu-id="56a10-110">int, not null</span></span>  <br/> |<span data-ttu-id="56a10-111">主体 id。</span><span class="sxs-lookup"><span data-stu-id="56a10-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="56a10-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="56a10-112">memberADPath</span></span>  <br/> |<span data-ttu-id="56a10-113">nvarchar (384)，不为 null</span><span class="sxs-lookup"><span data-stu-id="56a10-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="56a10-114">成员可分辨的名称。</span><span class="sxs-lookup"><span data-stu-id="56a10-114">Distinguished name of a member.</span></span> <span data-ttu-id="56a10-115">成员没有要 （在 tblPrincipal 表中） 的主体。</span><span class="sxs-lookup"><span data-stu-id="56a10-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="56a10-116">**键**</span><span class="sxs-lookup"><span data-stu-id="56a10-116">**Keys**</span></span>

|<span data-ttu-id="56a10-117">**列**</span><span class="sxs-lookup"><span data-stu-id="56a10-117">**Column**</span></span>|<span data-ttu-id="56a10-118">**说明**</span><span class="sxs-lookup"><span data-stu-id="56a10-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="56a10-119">\<prinID memberADPath\></span><span class="sxs-lookup"><span data-stu-id="56a10-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="56a10-120">主键。</span><span class="sxs-lookup"><span data-stu-id="56a10-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="56a10-121">prinID</span><span class="sxs-lookup"><span data-stu-id="56a10-121">prinID</span></span>  <br/> |<span data-ttu-id="56a10-122">在 tblPrincipal.prinID 中查找的外键。</span><span class="sxs-lookup"><span data-stu-id="56a10-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

